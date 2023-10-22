## Post #1
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2014-12-01T09:12:22+00:00
- Post Title: Motorcycle Club .PAC files

I need help to extract these files, or at least load the motorcycle models into MAX or any other program (but i prefer MAX).
The game uses .PAC files entirely for model files, and .PAF for sound (maybe?)
Well, if someone is willing to help me, these are the files :

[http://www.mediafire.com/download/r4udi ... toClub.zip](http://www.mediafire.com/download/r4udihhblbsyvlb/MotoClub.zip)

The ZIP includes both .PAF and .PAC files. Good luck to the ones who's willing to help
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-01T13:22:32+00:00
- Post Title: Motorcycle Club .PAC files

rename *.pac to *.7z for example and unpack the contained *.tmp file.

Used hex2obj (view link in my sig) to extract one submesh (of ten?):



MCclub_Kawa.JPG (245.99 KiB) Viewed 111 times



Normals might be no normals (other than stated).
As you might know I always ignore them to keep things simple with hex2obj. 
(If required let them to be autocalculated by blender for example.)
## Post #3
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2014-12-01T14:10:38+00:00
- Post Title: Motorcycle Club .PAC files

Whoa nice. Gonna try this tomorrow (since it's late here and i still have exams tmr)
Btw, i'm kinda confused on how this hex2obj tool works, and i have no knowledge in hex numbers too .-.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-01T14:20:48+00:00
- Post Title: Motorcycle Club .PAC files

> Reply from REDZOEU
>
> Whoa nice. Gonna try this tomorrow (since it's late here and i still have exams tmr)
Btw, i'm kinda confused on how this hex2obj tool works, and i have no knowledge in hex numbers too .-.
After your exams trying out the hex2obj tutorial sample should gonna going to be rather relaxing... 

well, hex numbers, this could appear to be a "plot stopper"  

Other than the decimal system with a base of ten there's 16 "numbers"
in the hexadecimal system: 0,..,9,A,B,C,D,E,F (with a preceeding 0x to indicate that we have a hexedecimal number).

But it's not too hard - you only should know how to convert between the two systems:
0x100 = 256 for example

(you could use windows' calculator.exe)

Last not least be informed that hex2obj is intended to be a helper tool
for a quick format reversing. It's not a one-click-solution.

Once you know how to get a (sub) mesh it would make sense
to create a maxscript for importing models.
