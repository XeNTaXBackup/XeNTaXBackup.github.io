## Post #1
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-09T18:36:14+00:00
- Post Title: /PC/ Beat Hazard

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-09T21:31:24+00:00
- Post Title: /PC/ Beat Hazard

Open game exe with hex editor and, search as string "Use Windows Browser" you will find texts of game.
Some texts are in different place of .exe file, for example "Select Language" in different place.
## Post #3
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-03-03T12:14:35+00:00
- Post Title: /PC/ Beat Hazard

I found the texts for the game but when i try to translate all the text my Hex Editor shows that the file size is changed and when i click "Yes" and try to start the game from BeatHazard.exe it says that the .exe is not a valid Win32 application.

What i'm doing wrong and is there a way to translate the text without Hex editor?
## Post #4
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-03-03T23:10:22+00:00
- Post Title: /PC/ Beat Hazard

You should keep the same number of characters of the original text.
## Post #5
- Username: Controller
- Rank: n00b
- Number of posts: 11
- Joined date: Mon May 25, 2009 8:44 am
- Post datetime: 2021-07-22T18:20:52+00:00
- Post Title: /PC/ Beat Hazard

Already covered in the zip password topic, but for completeness:

To extract game.dat and game2.dat:
Patch all bytes by substracting 0x35, and save it as .zip files (Other topics say to XOR with 0x35, which didn't work on my version of Beat hazard)

Extract with this password:
8sF32UfxK97j#@$J£$[]soIumMWL;ASOMVPW{QOE<LDSAMKFD

So in theory, it should be reversable... (reimport)...
## Post #6
- Username: L33THAK0R
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 13, 2021 2:48 pm
- Post datetime: 2023-01-14T23:45:43+00:00
- Post Title: /PC/ Beat Hazard

I'm not sure if I understand correctly but by subtracting 0x35, do you mean removing the first 35 bytes from the file? I can't seem to figure out how to transform the ".dat" files into valid zip archives.
## Post #7
- Username: Controller
- Rank: n00b
- Number of posts: 11
- Joined date: Mon May 25, 2009 8:44 am
- Post datetime: 2023-01-16T18:51:07+00:00
- Post Title: /PC/ Beat Hazard

By subtracting I mean patching each byte. This involves an advanced hex-editor or programming skills.
