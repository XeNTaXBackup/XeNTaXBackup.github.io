## Post #1
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-03-04T14:38:49+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

if posible could anyone make a script or tool, to unpack and repack the json files inside mass effect 3's coalesced so they can be edited.

someone made a tool for the demo but it dosnt work correctly on the full game. (unless im missing a checksum in the xex but there isnt one in the TOC)

heres there coalesced.bin 


thanks to anyone that has a look.
## Post #2
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-03-04T18:19:19+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

Here's what you need:
[http://blog.gib.me/2012/02/16/mass-effe ... -bin-tool/](http://blog.gib.me/2012/02/16/mass-effect-3-coalesced-bin-tool/)

Enjoy!
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-04T18:49:12+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

If anybody interested heres Rick's Mass effect 3 SVN

[http://svn.gib.me/public/masseffect3/trunk/](http://svn.gib.me/public/masseffect3/trunk/)

Still WIP
## Post #4
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-03-04T19:43:23+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

> Reply from Herdell
>
> Here's what you need:
http://blog.gib.me/2012/02/16/mass-effe ... -bin-tool/

Enjoy!

that tool dosnt repack correctly, it messes up the colesced size makes it unreadable by game once repacked.
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-04T22:38:44+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

i have working tool here  Tested by me all works on X360!!

```
http://dl.dropbox.com/u/38234344/ME3%20Tool.rar
```
## Post #6
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-03-04T23:44:06+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

> Reply from michalss
>
> i have working tool here  Tested by me all works on X360!!
Code: Select allhttp://dl.dropbox.com/u/38234344/ME3%20Tool.rar

thanks
edit: is mass effect 2 tool =( , how did you get it working for ME3?
## Post #7
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-03-05T02:55:59+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

Can't do anything about size changes. I cannot reproduce Bioware's huffman encoder perfectly. If the 360 can't handle size changes then well, tough shit?
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-05T05:48:39+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

> Reply from Rick
>
> Can't do anything about size changes. I cannot reproduce Bioware's huffman encoder perfectly. If the 360 can't handle size changes then well, tough shit?

You are 100% right Rick. Size will be always biggere then original. You can't reproduce the same file size as original, that is impossible with huffman. I did not tested your tool yet but ppl complaint it does not work, so might there is some other problem, which i dont thinks so  . Of course X360 can hadle the different size of the file, there is no doubs, becase i tested a few times and it works perfectly on JTAG/RGH, there is not even crc check in this game. So that person who said it does not work doing someting really wrong
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-05T05:49:41+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

> Reply from nickx
>
> michalss wrote:i have working tool here  Tested by me all works on X360!!
Code: Select allhttp://dl.dropbox.com/u/38234344/ME3%20Tool.rar

thanks
edit: is mass effect 2 tool =( , how did you get it working for ME3?

Well normally working same hufmann as ME3, not really suprising! Different is only this PC is little endianness and X360 is big endiannes - and again nothing unussual.
## Post #10
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-03-05T12:31:21+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

I took another look and it looks like I didn't specify the correct endian for a single value write.

Try r8, if it still doesn't work I can't help you.

[http://svn.gib.me/builds/masseffect3/](http://svn.gib.me/builds/masseffect3/)
## Post #11
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-03-05T18:09:33+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

> Reply from Rick
>
> I took another look and it looks like I didn't specify the correct endian for a single value write.

Try r8, if it still doesn't work I can't help you.

http://svn.gib.me/builds/masseffect3/

i got it working in R8, fail on my part for not using latest revision, thanks.
## Post #12
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-03-06T14:35:26+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

friends within the coalesced are all texts of the games?

is a tool that helps in editing the. json?
## Post #13
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-03-08T13:24:46+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

> Reply from timartinelli
>
> friends within the coalesced are all texts of the games?

is a tool that helps in editing the. json?

subtitles and text are not in the coalesced on this game, i belived they are located in Biogame\CookedXenon\biogame_int.tlk, Biogame\CookedXenon\biogame_en-us.gfc etc.
## Post #14
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-08T17:06:46+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

> Reply from nickx
>
> timartinelli wrote:friends within the coalesced are all texts of the games?

is a tool that helps in editing the. json?

subtitles and text are not in the coalesced on this game, i belived they are located in Biogame\CookedXenon\biogame_int.tlk, Biogame\CookedXenon\biogame_en-us.gfc etc.

Correct u can see ma prew post i uploaded editor for it....
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-08T17:27:42+00:00
- Post Title: Mass Effect 3 coalesced.bin json unpack/repack

Is audio extraction with proper names being worked on as well?
## Post #16
- Username: Xoza
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 11, 2012 3:49 am
- Post datetime: 2012-03-13T20:35:38+00:00
- Post Title: Re: Mass Effect 3 coalesced.bin json unpack/repack

> Reply from OrangeC
>
> Is audio extraction with proper names being worked on as well?

Have you been able to extract SFX, even if misnamed? (not dialogs)
## Post #17
- Username: chakallaska
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 26, 2012 12:13 am
- Post datetime: 2012-03-25T16:20:29+00:00
- Post Title: Re: Mass Effect 3 coalesced.bin json unpack/repack

hello, I'm on a project to translate the Mass Effect 3 for languages ​​that do not have by default, you said that the texts are in Biogame \ CookedXenon \ biogame_en-us.gfc but which program use to open and edit the file biogame_en-us.GFC ?

Send the program to my email please [thiago.msm@gmail.com](mailto:thiago.msm@gmail.com) you will help many people.
## Post #18
- Username: mmm273
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Apr 14, 2012 9:30 pm
- Post datetime: 2012-04-20T17:34:34+00:00
- Post Title: Re: Mass Effect 3 coalesced.bin json unpack/repack

> Reply from chakallaska
>
> hello, I'm on a project to translate the Mass Effect 3 for languages ​​that do not have by default, you said that the texts are in Biogame \ CookedXenon \ biogame_en-us.gfc but which program use to open and edit the file biogame_en-us.GFC ?

Send the program to my email please thiago.msm@gmail.com you will help many people.

You dont do this... You must take BIOGame_XXX.TLK (XXX means for lang you have to replace, eg.  INT, FRJ etc.)

Then take Mass Effect 2 TLK Tool ... run it, click load tlk, browse to TLK, click EDIT and change for X360, click RUN/START ... After that you have .xml file... this you can translate, and then back pack them with this, but dont select load tlk... select Create TLK ( for X360 ) and finish...

Sorry for my bad ENG, im from Slovakia...
