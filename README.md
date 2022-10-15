# writeup_corridor_ctf_thm
Writeup for TryHackMe's Corridor room
Created by tryhackme, JohnHammond, cmnatic, timtaylor

--------------------------------------

This is a web based challenge showcasing basic IDOR vulnerabilities.
Portswigger has a concise resource here: https://portswigger.net/web-security/access-control/idor

--------------------------------------

1. Open the given URL in your browser and you'll find yourself in a room full of doors.
Clicking on any of the doors will take us to a new empty room (no flags), however in those rooms the address bar or URL has some strange character set.

2. Noting the challenge information carefully -- "Examine the URL endpoints you access as you navigate the website and note the hexadecimal values you find (they look an awful lot like a hash, don't they?)" -- we learn the URL endpoints or the last part of the address in the address bar above is an MD5 hash that we'll need to crack!

3. Time to pick up our hoody from the floor, search Youtube for some Blade Runner themed hacking music and set our fancy-schmancy new LED's to flash red and blue. We're all hackers from here on in, Johnny.

4. The easiest solution to crack MD5 hashes is to use what are called Rainbow Tables which will compare our hashes to known words or number combinations. Here's an online tool to make things quicker: https://crackstation.net/

5. Pasting in our hash and clicking "I'm not a robot" if you're positive you're not, we can crack it.
e.g. 8f14e45fceea167a5a36dedd4bea2543 will reveal the number 7.

6. Now we know the rooms are numbered. The hint we'll need is "Can you find your way back to where you came?"
This refers to the number zero (the beginning) which we'll need to convert to an MD5 hash as per original room addresses or URLS.

7. I used Cyberchef for this https://gchq.github.io/CyberChef/
- In the 'Operations' panel search for 'md5'
- In the 'Input' panel type a '0' for zero
- Copy the hash in the 'Output' panel
- Go back to the 'Corridor' web site and paste the hash at the end of the home address e.g. "10.10.10.10/8f14e45fceea167a5a36dedd4bea2543" (Not a real address)

8. Your flag will be revealed. Time to fire up the Xbox, tear open some snacks and rest on your laurels 'cause you're a real hacker now, Johnny.

------------------------------

by Antomatron (Anthony Paul Sullivan)

