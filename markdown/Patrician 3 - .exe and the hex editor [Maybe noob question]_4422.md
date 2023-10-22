## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-05-03T22:00:51+00:00
- Post Title: Patrician 3 - .exe and the hex editor [Maybe noob question]

Hi again,

So I found out, that the Patrician3.exe (the main exe) has all the English texts in it. I tried to edit it with several hex editors, but when I change the texts (translating it), and save it, the exe says "Patrician3.exe is not a valid Win32 application".

Is there a way to edit the strings in it, avoiding the corruption of the exe?

Thanks in advance.
## Post #2
- Username: Ernegien
- Rank: mega-veteran
- Number of posts: 160
- Joined date: Wed Mar 24, 2010 1:27 pm
- Post datetime: 2010-05-03T22:33:17+00:00
- Post Title: Patrician 3 - .exe and the hex editor [Maybe noob question]

My guess would be that you're changing the length of these strings, which isn't good practice in an executable 

To answer your question, yes there is a way to edit strings without corrupting the executable.  Keep your edits just as long, or smaller, just make sure to add the character delimiter after you're done.  If you want to go nuts and change lots of strings around, you'll need to open up the exe in a disassembler and find all references to those strings, throw your new strings somewhere, then update accordingly...
## Post #3
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-05-03T22:45:31+00:00
- Post Title: Patrician 3 - .exe and the hex editor [Maybe noob question]

Thank you for the fast reply. What exactly is a character delimiter?
## Post #4
- Username: Ernegien
- Rank: mega-veteran
- Number of posts: 160
- Joined date: Wed Mar 24, 2010 1:27 pm
- Post datetime: 2010-05-03T22:49:12+00:00
- Post Title: Patrician 3 - .exe and the hex editor [Maybe noob question]

Strings are usually null-terminated by a byte or word of 0's, depending on whether it's ascii or unicode you're working with.  They can also sometimes prefixed with an integer value indicating their length, but null-terminated strings are usually more common.
