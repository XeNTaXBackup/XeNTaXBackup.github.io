## Post #1
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2011-06-15T19:29:17+00:00
- Post Title: Duke Nuken Forever .bin file

I was stuck in extracting the "Text Files" ... I do not know how to read the 3 bytes there was not part of "42 01 09" make me give meaningful data for the pull ...
Excuse my English is bad

.bin File here -> 
```
http://koukej.707.cz/obrazky/PS3_Coalesced_int.rar
```
## Post #2
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2011-06-17T12:31:32+00:00
- Post Title: Duke Nuken Forever .bin file

Anyone?
## Post #3
- Username: MrDeviance
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 27, 2008 12:05 pm
- Post datetime: 2011-06-19T06:20:29+00:00
- Post Title: Duke Nuken Forever .bin file

> Reply from Venushja
>
> Anyone?
For a forum that has Duke Nukem in it's banner, they don't seem give a shit about DNF's file formats it seems.
That's so lame...
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-19T07:42:13+00:00
- Post Title: Duke Nuken Forever .bin file

considering that this is not even an archive (aka off-topic) and can be edited with a simple hex editor I find perfectly correct how the thread has been "not" handled (aka ignored), DNF or not.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-19T07:54:23+00:00
- Post Title: Duke Nuken Forever .bin file

I was forgiving that I have in mind something for quickbms to help who is not comfortable with the editing of text data with the hex editor but it's not clear yet how to do it (I mean format and reimporting).

for example if instead of using the hex editor you can use notepad although you can't write more chars than the originals would it be ok?
would you be comfortable with a similar solution?

for example editing a file like the following:

```
00001281 this is the another string
```
I need feedback otherwise I don't waste time implementing it
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-19T08:10:04+00:00
- Post Title: Duke Nuken Forever .bin file

> Reply from aluigi
>
> I was forgiving that I have in mind something for quickbms to help who is not comfortable with the editing of text data with the hex editor but it's not clear yet how to do it (I mean format and reimporting).

for example if instead of using the hex editor you can use notepad although you can't write more chars than the originals would it be ok?
would you be comfortable with a similar solution?

for example editing a file like the following:
Code: Select all00001234 this is the original text string!
00001281 this is the another stringI need feedback otherwise I don't waste time implementing it

I'm glad to try it out, but not sure what exactly you mean ?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-19T08:20:32+00:00
- Post Title: Duke Nuken Forever .bin file

I mean:
- extracting a textual version with quickbms
- modifying a text file with a normal editor instead of using a hex editor on a binary file
- reimporting the next text with quickbms

the only limitation will be the same of any reimporter, so the length of the text can't be greater than the original but you will have the advantage of using a text editor instead the hex one.

how it sounds?
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-19T09:52:18+00:00
- Post Title: Duke Nuken Forever .bin file

> Reply from aluigi
>
> I mean:
- extracting a textual version with quickbms
- modifying a text file with a normal editor instead of using a hex editor on a binary file
- reimporting the next text with quickbms

the only limitation will be the same of any reimporter, so the length of the text can't be greater than the original but you will have the advantage of using a text editor instead the hex one.

how it sounds?

I'm so sorry but i really dont get this  "extracting a textual version with quickbms" - what is it?
There is no such a script i guess.

And yes i can try modifiy this with notepad++ and wil let you know.
## Post #9
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-06-19T15:03:46+00:00
- Post Title: Duke Nuken Forever .bin file

It would help me Luigi, you can do this script?

I am carrying the translation on my tongue.

I look forward to.

Hug.
## Post #10
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-20T09:43:58+00:00
- Post Title: Duke Nuken Forever .bin file

This file seems to be broken somehow. I have tool to fully read and extract coalesced archives and content of this file makes no sense to me.

At offset 0x9f there is key name ";	(MapName" and next is expected value. But there is 0x52 followed by 0x02 value. It is wrong. There should be just 1B value contains length of followed text. Nothing more. But next text is 0x92 long. But maybe this is another screwed version of coalesced archive.
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-20T12:12:16+00:00
- Post Title: Duke Nuken Forever .bin file

> Reply from XRaptor
>
> This file seems to be broken somehow. I have tool to fully read and extract coalesced archives and content of this file makes no sense to me.

At offset 0x9f there is key name ";	(MapName" and next is expected value. But there is 0x52 followed by 0x02 value. It is wrong. There should be just 1B value contains length of followed text. Nothing more. But next text is 0x92 long. But maybe this is another screwed version of coalesced archive.

Hi can you try your method on this one pls ? Might possible post the quickbms script ?
PS3 is kinda strange 

```
http://loadfiles.in/qahiv2k7xvtg/XBOX_Coalesced_int.bin
```
## Post #12
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-20T12:40:40+00:00
- Post Title: Duke Nuken Forever .bin file

It is almost the same. I'll try to find out what the hell it is  It seems that just some values are saved as 1B and some values as 2B.
## Post #13
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-23T13:18:21+00:00
- Post Title: Duke Nuken Forever .bin file

Bleh, it is really very strange file. I thought I'm able to fully read it, but there is 1 problem and it is dynamic length of arrays. I normal way, there is always byte value for counts (files, sections, key-value pairs). But in this file it is 1st time I see more then 255 key-value pairs in section, so there is 2B value with count. Offset 0x1996, value 0x863. And it is problem. Because it is only 1 file with this, I'm not able to find out how to check if value is 1B or 2B and then count correct number. When reading string length, it is easy. It is dynamic value too, but it is not problem to test it. But with this count value, it is strange. I thing I will have to find more files with this values and check it or simply debug exe to findout reading mechanism.
## Post #14
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-30T09:46:15+00:00
- Post Title: Duke Nuken Forever .bin file

Do you have PS3_Coalesced_int.bin file from full version? That one you posted is from demo.
## Post #15
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-06-30T13:03:21+00:00
- Post Title: Duke Nuken Forever .bin file

Friend,

here are. bin update the game, these are the files used in the game.
[Localization.rar](https://xentaxbackup.github.io/file/4404_Localization.rar)
