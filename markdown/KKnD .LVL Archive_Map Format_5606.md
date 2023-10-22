## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-12-22T15:14:59+00:00
- Post Title: KKnD .LVL Archive\Map Format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2011-05-22T13:04:45+00:00
- Post Title: KKnD .LVL Archive\Map Format

44 41 54 41 //HEADER
XX XX XX XX //FOOTER OFFSET
XX XX XX XX //CONTENT TYPE TABLE OFFSET

//RAW FILES WITHOUT SEPERATOR

1:n { //CONTENT FILES TABLE
XX XX XX XX //FILEOFFSET REVERSED
}

1:n { //CONTENT TYPE TABLE
XX XX XX XX //SOUN | MOBD | MAPD | CPLC | BOXD itendifier
XX XX XX XX //REVERSED OFFSET TO A CONTENT FILES TABLE
}

00 00 00 00 00 00 00 00 //LONG SEPERATOR - maybe not. something below in the UNK is pointing here, but its always a list of 0
52 52 4C 43 //FOOTER
//UNKNOWN - looks like it is not needed for file extraction, could be some info for the game engine
00 //END OF FILE

just to answer your question. for more: im working here: [http://www.sleipnirstuff.com/forum/view ... 83&t=15158](http://www.sleipnirstuff.com/forum/viewtopic.php?f=83&t=15158)
how do you know about "8 bit RAW graphics, 3 bytes per colour, BlackBody-style palete" are you sure with this information?
## Post #3
- Username: micha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 13, 2011 7:00 pm
- Post datetime: 2011-07-13T11:30:32+00:00
- Post Title: KKnD .LVL Archive\Map Format

Hello,

I am working on a similar topic.

- I extracted the sounds by the script of IceReaper. 
- I can play the videos but the sound is a little bit asynchronous.
- I can extrace the images but I don't know the color lookup table(s).

An image file ( for example 3.MODB of SUPSPR.LVL ) contains:
- At the beginning some unknown stuff. This could be the color lookup table?!
- A list of TPRS paragraphs (Could be an identifier/offeset for each image).
- Images: 
    C0 01 00 00 // 448 (width)
    CB 00 00 00 // 203 (height)
    ................ // raw image data ( the main menu image background )
    separator ( I think there was an separator... but I have to look on my other computer )
    next image ( button )

Please let me know if you discovered more details.
## Post #4
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2011-07-20T03:18:13+00:00
- Post Title: KKnD .LVL Archive\Map Format

i actualy cant find anything valueable. so i started random tries...
this is what i found out about whats inside the files (should help searching)

0.mobd (research progressbar)

1.mobd (unk)

2.mobd (unk)

3.mobd (buttons, backgrounds)
448 (width) - shows a large image
32 (width) - shows some build-menu stuff

4.mobd (unk)

5.mobd font on buttons like mapnames

6.mobd (mainmenu-button-text)

7.mobd (font-map)
## Post #5
- Username: helltone
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 04, 2011 4:26 pm
- Post datetime: 2011-10-07T20:07:14+00:00
- Post Title: KKnD .LVL Archive\Map Format

Hey any progress on this?
## Post #6
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-06-06T16:03:34+00:00
- Post Title: KKnD .LVL Archive\Map Format

If anyone can help, PM for getting files for tests and research.
## Post #7
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2012-10-13T00:41:54+00:00
- Post Title: KKnD .LVL Archive\Map Format

Just for the interested guys, i remembered writing this topic a while ago  Im still working on this - thrown over the progress, some reallife things, couldn't find help, etc..

Im currently working on my own game engine and building kknd1 and kknd2 extractors for all resources inside of the files. Currently im working on reverse-engeneering the KKND2 ones - they are havily obfuscated, however im at about 90% de-obfuscating them - can clearly read a large part of the files after the third obfuscation layer. If anyone is interested, write me in icq: 137122058 - i wrote this post just because i came across this forum when using google.

KKND1 and KKND2 are using a mostly the same format, while KKND2 has its protection / obfuscation on the package files, but if you remove it (where im working on), a KKND1 like package file comes out. - So if anyone is interested in helping, i would be very thankfull. (its realy a hard puzzeling job!)
## Post #8
- Username: micha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 13, 2011 7:00 pm
- Post datetime: 2014-02-13T15:17:28+00:00
- Post Title: KKnD .LVL Archive\Map Format

Hello icereaper
I started to develop a java tool which extracts the file content. 
Do you know the meaning of all file parts?

I extracted the level graphics, the sounds and almost all sprites.
But there are some small unknown parts. CPLC for example.
Additionally I am able to play the videos with ffmpeg. 

It would be nice to support you to create a new version of KKND.

Do you have a public code repository?

Michael
