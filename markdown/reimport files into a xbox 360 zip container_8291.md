## Post #1
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T14:50:14+00:00
- Post Title: reimport files into a xbox 360 zip container?

i extracted a zip file from a game perfectly but now i need to reimport a file into the zip container, how would i do this using quickBMS? or any other tool that offers this.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-15T16:43:52+00:00
- Post Title: reimport files into a xbox 360 zip container?

read section 3 of quickbms.txt, the Xmemcompressed mode is supported in both compression and decompression so you can adobt this method:
[http://aluigi.org/papers/quickbms.txt](http://aluigi.org/papers/quickbms.txt)
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-15T16:44:56+00:00
- Post Title: reimport files into a xbox 360 zip container?

> Reply from wkdwilliams
>
> i extracted a zip file from a game perfectly but now i need to reimport a file into the zip container, how would i do this using quickBMS? or any other tool that offers this.

what game ?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-15T16:51:47+00:00
- Post Title: reimport files into a xbox 360 zip container?

as far as I know only Forza Motorsport uses zip archives with xmemcompression instead of deflate, right?
## Post #5
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T17:44:20+00:00
- Post Title: reimport files into a xbox 360 zip container?

> Reply from aluigi
>
> read section 3 of quickbms.txt, the Xmemcompressed mode is supported in both compression and decompression so you can adobt this method:
http://aluigi.org/papers/quickbms.txt
ok, this is what i dont get:

quickbms -w -r script.bms archive.pak output_folder

what script do i use? and why do i specify a output_folder if im importing?
## Post #6
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T17:58:24+00:00
- Post Title: reimport files into a xbox 360 zip container?

> Reply from aluigi
>
> as far as I know only Forza Motorsport uses zip archives with xmemcompression instead of deflate, right?
so every game uses deflate instead of forza? so i could just compress this zip with winrar?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-15T18:44:54+00:00
- Post Title: reimport files into a xbox 360 zip container?

the question is:
why you can't open that zip files with winrar/7zip/winzip/any_other_tool?

if you can open the zip file with a normal zip program then you can recompress it with the same programs.

only forza motorsport uses a particular compression algorithm that is supported only in quickbms and that's why it's necessary zip.bms to handle these files
## Post #8
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T18:59:35+00:00
- Post Title: reimport files into a xbox 360 zip container?

> Reply from aluigi
>
> the question is:
why you can't open that zip files with winrar/7zip/winzip/any_other_tool?

if you can open the zip file with a normal zip program then you can recompress it with the same programs.

only forza motorsport uses a particular compression algorithm that is supported only in quickbms and that's why it's necessary zip.bms to handle these files
ok, so all i need is zip.bms to rebuild this zip file?
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-15T19:11:21+00:00
- Post Title: reimport files into a xbox 360 zip container?

yes, if no other program can open these zip files.
follow the simple instructions in section 3 and it will work.

you can use the reimport.lnk link or create one by yourself, so no need to use the command-line
## Post #10
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T19:14:31+00:00
- Post Title: reimport files into a xbox 360 zip container?

> Reply from aluigi
>
> yes, if no other program can open these zip files.
follow the simple instructions in section 3 and it will work.

you can use the reimport.lnk link or create one by yourself, so no need to use the command-line
and where would i get the zip.bms?
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-15T19:21:14+00:00
- Post Title: reimport files into a xbox 360 zip container?

ehmmm seriously do you know about what you are talking or what?

you want to reimport something that can be extracted only with quickbms and zip.bms so you have already used them (otherwise there is no sense in your thread) BUT you don't know where is zip.bms to reimport it???

sorry I will no longer help you.
## Post #12
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T19:27:58+00:00
- Post Title: reimport files into a xbox 360 zip container?

> Reply from aluigi
>
> ehmmm seriously do you know about what you are talking or what?

you want to reimport something that can be extracted only with quickbms and zip.bms so you have already used them (otherwise there is no sense in your thread) BUT you don't know where is zip.bms to reimport it???

sorry I will no longer help you.
but to reimport something it asks for a bms script and i dont know where to get that script from... makes sense to me.
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-15T19:55:20+00:00
- Post Title: reimport files into a xbox 360 zip container?

> Reply from wkdwilliams
>
> aluigi wrote:ehmmm seriously do you know about what you are talking or what?

you want to reimport something that can be extracted only with quickbms and zip.bms so you have already used them (otherwise there is no sense in your thread) BUT you don't know where is zip.bms to reimport it???

sorry I will no longer help you.
but to reimport something it asks for a bms script and i dont know where to get that script from... makes sense to me.

Man really ? just cannot believe aluigi helped you on the first place. U not making any sence at all. Read the manual for QuickBMS or use my GUI!
## Post #14
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T20:05:22+00:00
- Post Title: reimport files into a xbox 360 zip container?

> Reply from michalss
>
> wkdwilliams wrote:aluigi wrote:ehmmm seriously do you know about what you are talking or what?

you want to reimport something that can be extracted only with quickbms and zip.bms so you have already used them (otherwise there is no sense in your thread) BUT you don't know where is zip.bms to reimport it???

sorry I will no longer help you.
but to reimport something it asks for a bms script and i dont know where to get that script from... makes sense to me.

Man really ? just cannot believe aluigi helped you on the first place. U not making any sence at all. Read the manual for QuickBMS or use my GUI!
your GUI says the same, i want to import something but it asks for a OUTPUT folder? and i need a bms script... the game is left 4 dead 2 and im working on the zip0 file.
## Post #15
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T20:23:30+00:00
- Post Title: reimport files into a xbox 360 zip container?

> Reply from aluigi
>
> ehmmm seriously do you know about what you are talking or what?

you want to reimport something that can be extracted only with quickbms and zip.bms so you have already used them (otherwise there is no sense in your thread) BUT you don't know where is zip.bms to reimport it???

sorry I will no longer help you.
actually ive never extracted anything with quickBMS, i use XZIP.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T20:27:06+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

> i use XZIP.

So then try using xzip to re-pack?
## Post #17
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T20:43:46+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

> Reply from finale00
>
> i use XZIP.

So then try using xzip to re-pack?
it only has a extract feature. this whole thing is killing me, im really confused on what to do, i read the instructions hundreds of times for quickBMS but i cant get it to work.
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T20:49:25+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

Just double click quickbms and it will ask you to select a bunch of files.
I don't think it is that hard.

If you need bms scripts go check aluigi's site.
## Post #19
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T20:54:24+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

> Reply from finale00
>
> Just double click quickbms and it will ask you to select a bunch of files.
I don't think it is that hard.

If you need bms scripts go check aluigi's site.
i know im sorry this is so easy to do but for some reason i dont understand it. ill tell you what im doing:

1. i double click quickbms.exe
2. it asks me for a script... what script?
3. it asks me for a archive, i presume its the game archive, so i click that.
4. it asks for a output folder  i just click desktop...

could you provide me with a script for importing?
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T21:03:38+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

> 2. it asks me for a script... what script?

The script that you want to use.

Haven't you been reading what aluigi was telling you?
## Post #21
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T21:06:12+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

> Reply from finale00
>
> 2. it asks me for a script... what script?

The script that you want to use.

Haven't you been reading what aluigi was telling you?
do i need to download the script?
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T21:24:04+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

Do you think you should?
## Post #23
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-15T21:25:42+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

> Reply from finale00
>
> Do you think you should?
yes, where from?
## Post #24
- Username: wkdwilliams
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 15, 2012 8:32 am
- Post datetime: 2012-02-16T03:09:22+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

ok i have zip.mbs and i tried to reimport but i get this:

   offset      filesize    filename
-  SCRIPTS  MESSAGE

   Error: unkown ZIP signature 28672 at offset 6324224
            if the other files have been extracted correctly it's all ok

- 0 files reimported in 0 seconds

Press RETURN to quit
## Post #25
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-02-18T01:46:20+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

It's great to know my site isn't the only place that gets people who can't read anything.  They're everywhere.
## Post #26
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-02-18T15:15:08+00:00
- Post Title: Re: reimport files into a xbox 360 zip container?

Hilarious, people! Hilarious! 

It seems reading is not everyone's strongest point. To say the least. 
A classic RTFM. Way to go destroying any goodwill of the authors of tools.
