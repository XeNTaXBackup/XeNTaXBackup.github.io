## Post #1
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-26T23:03:49+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

this would help my current project if their was support for these formats

this rar contains 3 formats .bin .dat and .snd
[http://fmhq.mustangfreak.us/stuff/Bin%2 ... %20MKT.rar](http://fmhq.mustangfreak.us/stuff/Bin%20Dat%20Snd%20MKT.rar)

as this would help me grab sounds and maybe sprites from the files for other needed projects with MK characters
## Post #2
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-28T02:22:00+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

guess no one is interested.....
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-28T02:44:19+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

sure we are interested, we just need some time because we do much more than just working on game archives. We will take a look at this as soon as we can.

Thanks.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-28T03:11:33+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

ok thanks 

this will really help out my up and coming project
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-28T06:12:14+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

> Reply from Acidfmhq
>
> guess no one is interested.....

Patience is a virtue...as they say...
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-28T07:57:22+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

Here is the format of the *.snd files

```
| Mortal Kombat Trilogy *.snd |
+-----------------------------+

4 - Number Of Files

// for each file
  4 - File Offset
```


I couldn't really get anything out of the other files though.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-28T08:13:39+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

well that sux you wasn't able to get ne thing out of the other files 

but at least ya found one of them
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-28T14:21:48+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

OK, here is the script ...

```
Set FNum1 Long FNum ;
Math FNum1 -= 1 ;
For n = 1 to FNum1 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos Next 0 ;
Get FS Long 0 ;
Math FS -= FO ;
GoTo Next 0 ;
Log "" FO FOO FS 0 ;
Next n ;
SavePos FOO 0 ;
Get FO Long 0 ;
GoTo EOF 0 ;
SavePos FS 0 ;
Math FS -= FO ;
Log "" FO FOO FS 0 ;

```


I have compiled the script and attached it to this message, so just use that one rather than fiddling around with the Scriptor. Just load up MexCom and go to Tools-->Use Custom BMS Script (or something like that). Note that I havn't tested it on the actual archive, but it should work OK.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[SND.zip](https://xentaxbackup.github.io/file/200_SND.zip)
## Post #9
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-28T14:47:58+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

well I wouldn't be able to do that till the new MexBinderPlus is released as I can't do Use Custom BMS Script in the current version

and the old one gives me Class does not support Automation or something...

but thanks for helping
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-28T15:18:28+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

Well, you CAN use it, of course...
## Post #11
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-28T15:34:33+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

well I was able to open the .snd file with game extactor and all the files within it are .wav  can get sounds easy now...

so I decided to do the same for the other files but I have no clue what file extension the files are.....

I have attached a rar file with the files from the dat and bin hope you can help thanks in advance
[extract.rar](https://xentaxbackup.github.io/file/201_extract.rar)
## Post #12
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-29T15:08:17+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

ne one going to take a look at those
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-29T15:17:47+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

Look, we are busy men, investigating multiple formats at any given FREE time. OUR free time. 

The files you have attached don't resemble anything I've seen at a quick glance, so file extensions are a little impossible to come up with.
## Post #14
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-29T15:24:30+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

oh ok sorry...

just wondering if ya could help I can still get the gfx the old way I was doing it

at least I can now rip the sounds right from the files
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-29T17:12:11+00:00
- Post Title: Mortal Kombat Trilogy PC 3 files

No problem
## Post #16
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-05-04T09:25:51+00:00
- Post Title: 

well since ya can't get ne thing from the .dat and .bin files I found my copy of MK3 for PC

tryed with game extactor and no go so wanted to share this file to see if you can crack it for me..

[http://fmhq.mustangfreak.us/stuff/kang.rar](http://fmhq.mustangfreak.us/stuff/kang.rar)

its a .ftr file
## Post #17
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-04T11:51:32+00:00
- Post Title: 

Hey,

Yeah, those other file pieces you sent me were still no more helpful 

Anyway, I will take a look at the ftr archive - I already have most of the specs for it so shouldn't be too hard.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #18
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-05-04T14:20:14+00:00
- Post Title: 

yea I seen that it was red meaning that it was not tested on your site

I tryed emailing you but it didn't send for some reason 

ne way hope that file helps you out
## Post #19
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2005-05-04T23:35:44+00:00
- Post Title: 

For Kang.ftr
4 bytes (header)
2 bytes (number of files)
2 bytes (?)
4 bytes (offset to directory) skip 32 bytes (starts off directory) to get data contained

Then in the files 
First 16 bytes not sure. Byte 6 is different than file.
Then starting at byte 17:
4 bytes File offset
4 bytes size  (size needs 32 bytes added, except 1st entry?)
