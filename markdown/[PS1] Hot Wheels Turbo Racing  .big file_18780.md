## Post #1
- Username: matty45
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 06, 2018 7:29 am
- Post datetime: 2018-09-07T22:08:25+00:00
- Post Title: [PS1] Hot Wheels Turbo Racing : .big file

I have never seen anyone trying to reverse engineer the file formats of this game before.

The game stores most of its assets except music inside a file called "CCPSX.7z"
The file cannot be opened by most file unpackers. 

However the only thing that i have managed to extract from it are its images using jpsxdec and tim2view.

I cant seem to find any magic headers within the archive but the filenames are there.

Hex Preview: [https://i.imgur.com/8REdOL1.png](https://i.imgur.com/8REdOL1.png)

File: [https://mega.nz/file/yVpiRQSR#gWD9X-vEe ... S4fyE2bbcM](https://mega.nz/file/yVpiRQSR#gWD9X-vEe-KgBb7sfwt4-mSAFVh1MDDtpS4fyE2bbcM)
## Post #2
- Username: matty45
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 06, 2018 7:29 am
- Post datetime: 2020-05-12T16:58:59+00:00
- Post Title: [PS1] Hot Wheels Turbo Racing : .big file

Ive tried all sorts of game archive unpackers including, dragon unpacker, and some quickbms scripts to no avail, been looking at the games code myself to figure it out but so far, ive found nothing.
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-05-12T19:24:35+00:00
- Post Title: [PS1] Hot Wheels Turbo Racing : .big file

You can use the attached QuickBMS script to extract the files from the .BIG archive - it should work for both the NTSC and PAL versions (CCCPSX.BIG and CCCPSXP.BIG)

As far as I can tell, the archive doesn't separate the file extension from the filename.  I don't know what most of the extracted files are, except for VH for audio header info and VB for audio data.
[hwtr_big.zip](https://xentaxbackup.github.io/file/18138_hwtr_big.zip)
## Post #4
- Username: matty45
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 06, 2018 7:29 am
- Post datetime: 2020-05-12T19:40:39+00:00
- Post Title: [PS1] Hot Wheels Turbo Racing : .big file

It works!, Thanks for the help!

Ill see what i can do with those extracted files and hopefully get some results.
