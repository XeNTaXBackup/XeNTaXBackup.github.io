## Post #1
- Username: Kataah
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-07T18:57:26+00:00
- Post Title: QUICKBMS GUIDE

I am going to make a tutorial for using quickbms for extracting archives that are no extractors for.
I am going to start off easy then add more and more difficult archives so you can learn and write your own scripts.
the tools you need are just 4 things.
1. A HEX editor I use HxD
2.Quick BMS [http://aluigi.org/papers/quickbms.zip](http://aluigi.org/papers/quickbms.zip)
3. a text editor like wordpad
4. a calculator that supports hex like the one built into windows.
We will start with a game called FEZ (Fantasy Earth Zero)
this is a great archive format for someone to learn bms scripting from.
I attached a sample.
website [http://tw.fez.gamania.com/](http://tw.fez.gamania.com/)
installer [http://tw.dl.gamania.com/fez/FEZ_1103.exe](http://tw.dl.gamania.com/fez/FEZ_1103.exe)
this game uses textures with wrong headers mainly dds and some tga and some kind of .mdl format.

ok so you can download the full installer
ok so open the file up in your hex editor so you see what I have open here
[](http://img357.imageshack.us/i/tutorial1.jpg/)
so if you look to the right you will notice some readable text 
Etc\aura.tex , Etc\cursor.tex , Etc\mahoujin.tex , Etc\env2.tex , and Etc\kaze.tex .
so just looking with out eyes we now know that there are at least 5 files in this bin file and after we extract them they will be placed in a folder called Etc.
so lets start looking at the other parts of the header in this file we will start with the first 4 bytes
[](http://img413.imageshack.us/i/tutorial2.jpg/)
well we have 05 00 00 00
whenever you are working with archives for computer games 99% of the time you read the values in reverse so the above number
would not be 5,000,000 but instead would be read as 00 00 00 05 or 5
Well if we remember from earlier we saw 5 file names and our first 4 bytes of our file are equal to 5 so there is a good chance we just discovered where the file count is stored in this archive.
data is stored in groups of 4 bytes " a long" 2 bytes " a short" or 1 byte "a byte" so we have our first part of our script
get FILES long
this tells quickbms to read a long value "aka 4 bytes" and store it as the variable FILES.
ok the next 4 bytes 74 00 00 00 are not needed in order for quickbms to extract our files but it represents the total size of our header.
[](http://img14.imageshack.us/i/tutorial3u.jpg/)
so I will write the next line of code for quickbms
get HEADERSZ long 
this stores the header size in the variable HEADERSZ
ok now we have 2 more bytes before the file name
so that is 0C 00 well 2 bytes is know as a short. but what does 00 0C stand for?
if we highlight the whole name of the file in out hex editor it shows us a length of C 
we found the name length so we would write that as
get NSIZE short
this stores the 2 bytes in the variable NSIZE representing the length of the name

well next comes the name so to store that as a word in bms language we will write the next line
getdstring NAME NSIZE
this is saying store a string "aka a word" in the variable NAME and its length is equal to the variable NSIZE.
ok now we have another 4 bytes after the name 7C 00 00 00
well we already know the name of the file so now to extract the file we need to know its size and location in the archive.
7C is not a very big number for the size of the file to lets see what happens if we go to offset 7C
in HxD press ctrl +E and type in 7c for the start and end then click ok.

you should look like this after clicking ok

hmm this looks good it looks like a file header IMG0 so we will write out line saying that is the start of the file
get OFFSET long
this stores the 4 bytes as the variable OFFSET
ok the next 4 bytes are 70 10 00 00 well that looks bigger so lets see if that is the size of out file so it will translate into 00 00 10 70 or 1070
so lets go to our offset 7C and then we will add in the length column 1070

wow look at that I see TRUEVISION-XFILE that is a classic tga ending and we also end just before IMG0 which was the start of our first file

so that means we found our size 
we write that as 
get SIZE long
this stores the 4 bytes in the variable SIZE
ok now we have 2 bytes then the next file name hmm that seems familiar 
lets see 0E 00so that means it translates into 00 0E or E
well the last 2 bytes we had before a name was the name size lets see if it still holds true

it does the name length is E 
so that means we found where the pattern in the header repeats and we identified all that we need to extract the files so now we can finish our script and our extractor.
whenever the pattern starts you want to begin a loop so it will keep cycling through it until there are no files left. the easiest way to write that is.
for i = 0 < FILES
this means run the following commands until i = 0 and set i = FILES
so we will put that before our NSIZE variable because that is where the pattern starts.
next you want it to write out the file and we do that with the log command in the following format
log NAME OFFSET SIZE
this says write the file name and fill it with the data starting at the variable OFFSET and a length of SIZE.
now this is great but we want it to keep repeating the loop till there are no more files so we must add
next i
at the end so the loop continues.
ok so now save the file we created as extract.bms
and put Etc.pac extract.bms and quickbms.exe all in the same folder for wthis demo we will say c:\temp
so now at the command prompt change to that directory and type
quickbms.exe -l extract.bms Etc.pac .
this will list the the file contents and size or give you an error if your script is not correct.
Yay it worked 

now lets try extracting them create a folder in c:\temp called extracted
now type the command 
quickbms.exe extract.bms Etc.pac extracted
yes it worked now they are in the filder and extracted.


```
get HEADERSZ long
for i = 0 < FILES
get NSIZE short
getdstring NAME NSIZE
get OFFSET long
get SIZE long

log NAME OFFSET SIZE
next i
```

Let me know what you think of this tutorial and if you want me to continue on with more examples and more compex scripts.
## Post #2
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-06-07T20:40:43+00:00
- Post Title: QUICKBMS GUIDE

Excellent tutorial mate! I'm no genius, but this guide for dummies like me is EXCELLENT!

The only problem would be the 'format' of the tutorial, it's...abit messy, but still readable.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-07T21:16:53+00:00
- Post Title: QUICKBMS GUIDE

well done chrrox and just in time for the [new version](http://aluigi.org/papers.htm#quickbms) of QuickBMS with (experimental) support for the recursive functions :)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-07T22:00:56+00:00
- Post Title: QUICKBMS GUIDE

Good job, but it's a bit messy as already has been said.
Maybe you should use something like LaTeX and create a neat little pdf file
## Post #5
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-06-07T23:53:15+00:00
- Post Title: QUICKBMS GUIDE

Yeah great tut thx a lot for it.
Thats exactly what newbies needs - maybe a few more and different examples - then i think many people can help other guys to unpack simple containers
## Post #6
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-06-08T03:46:07+00:00
- Post Title: QUICKBMS GUIDE

Really good job!
I　ｗａｎｔ　ｔｏ　ｓｅｅ　more ａ　ｂｉｔ　ｃｏｍｐｌｅｘ　ｓａｍｐｌｅ．
## Post #7
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-08T14:19:10+00:00
- Post Title: QUICKBMS GUIDE

thanks chrrox , you are realy benevolence   
i realy need this tutorial @
is it possible to learn us some methods for recognizing of vertex and faces in 3d extracted files too , i think it is related to ability of working with IDA pro or HEXRAY !
i hope i don't be avaricious !
## Post #8
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-10T14:10:58+00:00
- Post Title: QUICKBMS GUIDE

> whenever you are working with archives for computer games 99% of the time you read the values in reverse so the above number
whether you mean the 99% of them are "little endian" ?
## Post #9
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-11T21:56:48+00:00
- Post Title: QUICKBMS GUIDE

This is little endian
You read the numbers from right to left so 01 00 00 00 would be equal to 00 00 00 01 or the number 1
while if it was big endian you would read the above number as
01 00 00 00 would be equal to 0x1000000 and in decimal that would be 16777216

[http://en.wikipedia.org/wiki/Endianness](http://en.wikipedia.org/wiki/Endianness)

If you want to be able to view / edit the tga files you extracted in this lesson just delete the first 0x40 bytes of the file and then save it.
now it is a normal tga file.
## Post #10
- Username: shekofte
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-12T03:19:42+00:00
- Post Title: QUICKBMS GUIDE

Don't ever care. Most normal formats are in little endian while most console formats are in big endian.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-28T21:51:49+00:00
- Post Title: QUICKBMS GUIDE

finally I have written a bit of documentation about all the available commands of QuickBMS.
tell me if you have doubts so I can improve it (although I'm very lazy ih ih ih):
[http://aluigi.org/papers/quickbms.txt](http://aluigi.org/papers/quickbms.txt)
## Post #12
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2010-02-05T14:34:33+00:00
- Post Title: QUICKBMS GUIDE

hmm seems i can't use this tutorial for my files...
[viewtopic.php?f=13&t=4118](http://forum.xentax.com/viewtopic.php?f=13&t=4118)
## Post #13
- Username: NMCM
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Apr 15, 2009 2:02 pm
- Post datetime: 2010-06-13T00:38:12+00:00
- Post Title: QUICKBMS GUIDE

I would really like one using one of the SD!2 Pac files. I've been trying to do this for the longest.
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-13T08:31:44+00:00
- Post Title: QUICKBMS GUIDE

> Reply from NMCM
>
> I would really like one using one of the SD!2 Pac files. I've been trying to do this for the longest.

Wrong thread.
## Post #15
- Username: NMCM
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Apr 15, 2009 2:02 pm
- Post datetime: 2010-06-14T14:39:23+00:00
- Post Title: QUICKBMS GUIDE

What I meant was, that I would like to see more examples, but using a .pac file from SD!2.
## Post #16
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2010-10-19T15:52:12+00:00
- Post Title: Re: QUICKBMS GUIDE

Hi ... Please more Tutorials on well-known (Games) files ... Thanks  
Incidentally nice tutorial ... It takes more tutorials
## Post #17
- Username: Republica
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 20, 2011 10:01 am
- Post datetime: 2011-02-20T08:27:20+00:00
- Post Title: Re: QUICKBMS GUIDE

> Reply from chrrox
>
> 

ok the next 4 bytes 74 00 00 00 are not needed in order for quickbms to extract our files but it represents the total size of our header.
Forgive me for my ignorance, but it seems I lost you there.
How did you come to the conclusion that (74 00 00 00) is the size of the header?
And when I start "Quick BMS" it asks me to choose a plugin, which one to choose and where to locate it?
All and all, I thank you for taking the time to share your expertise and writing such helpful tutorials.
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-21T23:38:07+00:00
- Post Title: Re: QUICKBMS GUIDE

calculating the size of a block of data is a job for the hex editor, so if he had 0x74 (74 00 00 00 in little endian) then he proabably saw 74 bytes of data, which are also easy to count due to the 16 bytes alignment usually in use in the hex editor (for example 7 rows plus 4 columns).

the script that quickbms needs is just the set of textual instructions for extracting the archives of a specific game.
you can find them surfing on the forum and I have some scripts collected [here](http://aluigi.org/papers.htm#quickbms)
## Post #19
- Username: Republica
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 20, 2011 10:01 am
- Post datetime: 2011-02-22T08:45:57+00:00
- Post Title: Re: QUICKBMS GUIDE

> Reply from aluigi
>
> calculating the size of a block of data is a job for the hex editor, so if he had 0x74 (74 00 00 00 in little endian) then he proabably saw 74 bytes of data, which are also easy to count due to the 16 bytes alignment usually in use in the hex editor (for example 7 rows plus 4 columns).

the script that quickbms needs is just the set of textual instructions for extracting the archives of a specific game.
you can find them surfing on the forum and I have some scripts collected here
Ugh..
Thank you, Aluigi.
I was starting to lose hope.
Currently, I'm reading a book, To familiarize myself with reverse engineering and not to embarrass myself asking such silly questions. at least I think it was a silly question.. because I still don't quite get it.
It's probably 'cause I'm not experienced enough to the extent that you are.

I'll give it more time and study it more.
## Post #20
- Username: reboot31
- Rank: MIT cheater
- Number of posts: 10
- Joined date: Mon Apr 18, 2011 2:41 pm
- Post datetime: 2011-04-20T14:30:11+00:00
- Post Title: Re: QUICKBMS GUIDE

thanks chroxx for this tutorial... you are a genius...
## Post #21
- Username: lagun2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 20, 2012 4:51 am
- Post datetime: 2012-02-20T19:39:44+00:00
- Post Title: Re: QUICKBMS GUIDE

Hi...I want "open" a file with extension sds. It's a file of the EA (fifa 2012). Can you help me?
## Post #22
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-09T19:26:37+00:00
- Post Title: Re: QUICKBMS GUIDE

Can u please upload the files for all yr QBMS tuts again? All are dead...
## Post #23
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-09-16T10:21:39+00:00
- Post Title: Re: QUICKBMS GUIDE

I am trying to understand Chroxx's BMS for Dark Souls BDT files, so I may unpack a ps3 version of that file type. I am a bit lost here and thinking this is what i need to modify:

```
TYPE == 0x44435800 math OFFSET + 0x4C getdstring NULL 0x18 1
```


when using the Xbox version, everything is parsed very nicely - how does that happen? 

Could you please explain this code as a string of actions?

thanks!
## Post #24
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-22T07:45:24+00:00
- Post Title: Re: QUICKBMS GUIDE

I was wondering if anyone could help me, is there a way in quickbms to return a string up to the point where the byte becomes 00, and stop there?

Edit: Nevermind I've realised if you just go over the byte it will stop there automatically anyway, it seems to work. Hopefully there's no problem with just doing it this way though.
## Post #25
- Username: dnmnbg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 14, 2010 4:22 am
- Post datetime: 2013-01-08T19:13:10+00:00
- Post Title: Re: QUICKBMS GUIDE

like the tut can you post more tuts . what about files that may be encrypted?


im a total noob with hex code  but would like to learn more if possible
## Post #26
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-08T19:36:11+00:00
- Post Title: Re: QUICKBMS GUIDE

just post your game in the game archive section for help.
## Post #27
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2013-04-07T05:37:43+00:00
- Post Title: Re: QUICKBMS GUIDE

Fantastic tutorial. I've been wanting to learn to reverse engineer for so long, but it seems like there are so few tutorials out there to help. I've been programming off and on for multiple years, but never found a resource to learn this.

Last I tried to do this I was building code in C++ or Java to parse the contents of a file, but now with QuickBMS I feel like things are much easier.

Hope to see more tutorials in the future, hopefully one for Unreal engine files since so many games are built on that. Gildor's tools are awesome, but I wish there was a QuickBMS version of his tools so I could just modify it for other Unreal engine games when needed.
## Post #28
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-07T10:44:21+00:00
- Post Title: Re: QUICKBMS GUIDE

gildor has an unreal package decompressor.
unreal will read the uncompressed files it outputs and you can modify them to your hearts content.
this is how people are modding mortal kombat.
## Post #29
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2013-07-26T16:06:07+00:00
- Post Title: Re: QUICKBMS GUIDE

This tutorial is great and I tried to used to for my files but I have a little problem. The "archives" I currently investigate have no header.
The archive starts with file count, then comes the name size of the following string and after that just the length/size of the file which ends directly before the name size of the next file.

So how do I get the log function to start right after NSIZE? Thanks.

Edit2 : Got it to work.
## Post #30
- Username: blackjack4494
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 28, 2013 11:32 pm
- Post datetime: 2013-07-29T00:00:12+00:00
- Post Title: Re: QUICKBMS GUIDE

rly nice tut 
It helped me a lot. But unfortunately I found this (and a complete script for my archive in this board/forum) after I already made a bms script on my own which took about a week to come on with syntax, hex code reading etc.
## Post #31
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-08-17T07:11:24+00:00
- Post Title: Re: QUICKBMS GUIDE

But that is good then, so you taught yourself!
## Post #32
- Username: Bringbackfez
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 04, 2014 12:22 am
- Post datetime: 2014-09-04T18:42:33+00:00
- Post Title: Re: QUICKBMS GUIDE

Looking for the fantasy earth Zero files since they are open for the taking cause Gamepot USA is a worthless company that dropped the ball on this game & no longer has rights to it. Please message me Sephy @ BringbackFEZ or hit us up on facebook @ Bring Back Fantasy Earth Zero.
## Post #33
- Username: Saeid0034
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 13, 2020 11:54 pm
- Post datetime: 2020-03-21T10:04:03+00:00
- Post Title: Re: QUICKBMS GUIDE

> Reply from chrrox ↑Mon Jun 08, 2009 2:57 am at Mon Jun 08, 2009 2:57 am
>
> 
I am going to make a tutorial for using quickbms for extracting archives that are no extractors for.
I am going to start off easy then add more and more difficult archives so you can learn and write your own scripts.
the tools you need are just 4 things.
1. A HEX editor I use HxD
2.Quick BMS http://aluigi.org/papers/quickbms.zip
3. a text editor like wordpad
4. a calculator that supports hex like the one built into windows.
We will start with a game called FEZ (Fantasy Earth Zero)
this is a great archive format for someone to learn bms scripting from.
I attached a sample.
website http://tw.fez.gamania.com/
installer http://tw.dl.gamania.com/fez/FEZ_1103.exe
this game uses textures with wrong headers mainly dds and some tga and some kind of .mdl format.

ok so you can download the full installer
ok so open the file up in your hex editor so you see what I have open here

so if you look to the right you will notice some readable text 
Etc\aura.tex , Etc\cursor.tex , Etc\mahoujin.tex , Etc\env2.tex , and Etc\kaze.tex .
so just looking with out eyes we now know that there are at least 5 files in this bin file and after we extract them they will be placed in a folder called Etc.
so lets start looking at the other parts of the header in this file we will start with the first 4 bytes

well we have 05 00 00 00
whenever you are working with archives for computer games 99% of the time you read the values in reverse so the above number
would not be 5,000,000 but instead would be read as 00 00 00 05 or 5
Well if we remember from earlier we saw 5 file names and our first 4 bytes of our file are equal to 5 so there is a good chance we just discovered where the file count is stored in this archive.
data is stored in groups of 4 bytes " a long" 2 bytes " a short" or 1 byte "a byte" so we have our first part of our script
get FILES long
this tells quickbms to read a long value "aka 4 bytes" and store it as the variable FILES.
ok the next 4 bytes 74 00 00 00 are not needed in order for quickbms to extract our files but it represents the total size of our header.

so I will write the next line of code for quickbms
get HEADERSZ long 
this stores the header size in the variable HEADERSZ
ok now we have 2 more bytes before the file name
so that is 0C 00 well 2 bytes is know as a short. but what does 00 0C stand for?
if we highlight the whole name of the file in out hex editor it shows us a length of C 
we found the name length so we would write that as
get NSIZE short
this stores the 2 bytes in the variable NSIZE representing the length of the name

well next comes the name so to store that as a word in bms language we will write the next line
getdstring NAME NSIZE
this is saying store a string "aka a word" in the variable NAME and its length is equal to the variable NSIZE.
ok now we have another 4 bytes after the name 7C 00 00 00
well we already know the name of the file so now to extract the file we need to know its size and location in the archive.
7C is not a very big number for the size of the file to lets see what happens if we go to offset 7C
in HxD press ctrl +E and type in 7c for the start and end then click ok.

you should look like this after clicking ok

hmm this looks good it looks like a file header IMG0 so we will write out line saying that is the start of the file
get OFFSET long
this stores the 4 bytes as the variable OFFSET
ok the next 4 bytes are 70 10 00 00 well that looks bigger so lets see if that is the size of out file so it will translate into 00 00 10 70 or 1070
so lets go to our offset 7C and then we will add in the length column 1070

wow look at that I see TRUEVISION-XFILE that is a classic tga ending and we also end just before IMG0 which was the start of our first file

so that means we found our size 
we write that as 
get SIZE long
this stores the 4 bytes in the variable SIZE
ok now we have 2 bytes then the next file name hmm that seems familiar 
lets see 0E 00so that means it translates into 00 0E or E
well the last 2 bytes we had before a name was the name size lets see if it still holds true

it does the name length is E 
so that means we found where the pattern in the header repeats and we identified all that we need to extract the files so now we can finish our script and our extractor.
whenever the pattern starts you want to begin a loop so it will keep cycling through it until there are no files left. the easiest way to write that is.
for i = 0 < FILES
this means run the following commands until i = 0 and set i = FILES
so we will put that before our NSIZE variable because that is where the pattern starts.
next you want it to write out the file and we do that with the log command in the following format
log NAME OFFSET SIZE
this says write the file name and fill it with the data starting at the variable OFFSET and a length of SIZE.
now this is great but we want it to keep repeating the loop till there are no more files so we must add
next i
at the end so the loop continues.
ok so now save the file we created as extract.bms
and put Etc.pac extract.bms and quickbms.exe all in the same folder for wthis demo we will say c:\temp
so now at the command prompt change to that directory and type
quickbms.exe -l extract.bms Etc.pac .
this will list the the file contents and size or give you an error if your script is not correct.
Yay it worked 

now lets try extracting them create a folder in c:\temp called extracted
now type the command 
quickbms.exe extract.bms Etc.pac extracted
yes it worked now they are in the filder and extracted.

Code: Select allget FILES long
get HEADERSZ long
for i = 0 < FILES
get NSIZE short
getdstring NAME NSIZE
get OFFSET long
get SIZE long

log NAME OFFSET SIZE
next i
Let me know what you think of this tutorial and if you want me to continue on with more examples and more compex scripts.

hi, sorry for get this old topic up
do you have any new GUIDE for quickbms?
## Post #34
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2020-11-24T09:52:18+00:00
- Post Title: Re: QUICKBMS GUIDE

[https://drive.google.com/file/d/1p7Mh5I ... mKy-z/view](https://drive.google.com/file/d/1p7Mh5I6LwPmOWqXcXr7g23r4WYkmKy-z/view)
can you help me if this file has any model?
