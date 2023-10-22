## Post #1
- Username: CrookshankS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 10, 2009 12:05 am
- Post datetime: 2013-08-26T05:20:34+00:00
- Post Title: istanbul kiyamet vakti how to .dat extract?

Hi guys.

Istanbul kiyamet vakti . dat file is protected. Now will give you the example file.
Here example : Textures_4.dat size 35.2 mb
[http://dosya.co/y4f5bwxgq1b7/textures_4.DAT.html](http://dosya.co/y4f5bwxgq1b7/textures_4.DAT.html)

i how to extract istanbul kiyamet vakti dat files? Please Help me. 

Here original game site :
[http://www.istanbuloyun.com](http://www.istanbuloyun.com)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-26T21:57:28+00:00
- Post Title: istanbul kiyamet vakti how to .dat extract?

quickbms script.

```
goto 0x48
get files short
for i = 0 < files
getdstring NAME 0x80
get offset long
get size long
log name offset size
next i

```
## Post #3
- Username: CrookshankS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 10, 2009 12:05 am
- Post datetime: 2013-08-28T05:43:10+00:00
- Post Title: istanbul kiyamet vakti how to .dat extract?

wow thank you so much man,its worked. İ have more  question...

1 - Bms how to write code ?

2 - Anather .dat file. contains in 3d models. How to open .dat? 
File : 
[http://www.filedropper.com/objects](http://www.filedropper.com/objects)
3 -With a hex editor. Dat file opened and its extensions .adf saw that.
Question .Adf file how to .Obj convert?
can you help me?
thanks. Sorry for my bad English.
