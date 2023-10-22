## Post #1
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2007-12-17T09:13:23+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2007-12-19T05:10:51+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

i can upload bigger files if needed but dunno if it can help better cause of the size.
And i found the guide in pdf so i learn how this work but cant start with xbox files to much complicated    pretty guide by the way ! .
Hope someone can take a look at one of the files and i think the most important is the isb one.. if it content the model file cause its what i want to get.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-19T07:05:08+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

Will take a look at them tonight.
## Post #4
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2007-12-19T10:46:16+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

Ty so much Mr.Mouse i hope you find something
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-19T19:34:32+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

[http://wiki.xentax.com/index.php/Psychonauts_ISB](http://wiki.xentax.com/index.php/Psychonauts_ISB)

Did you check our GFFC?? It seems this is a known format there. Check Psychonaut Explorer.

Oh and .jnk probably stands for JUNK. The file is completely filled with 0's.
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-19T23:46:03+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

> Reply from Hevon
>
> ps:i try and want to learn how watch in a file what the content, where i need to look what i need to keep and use for make a file for exctract.. so if one of you have some link of tutorial just send in MP ( sorry for my bad english im french    )
Pas de problème 
Well don't know if this is correct, it's been 4 years since my last french lesson 

I already opened a topic about creating tutorials for the community to help people get into the process of figuring out file formats:
[viewtopic.php?t=2867](http://forum.xentax.com/viewtopic.php?t=2867)

Also uploaded a rough draft of my first tutorial there.

> And i found the guide in pdf so i learn how this work but cant start with xbox files to much complicated  pretty guide by the way!
Yeah it's a good and comprehensive reference.
## Post #7
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2007-12-20T06:07:30+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

Oh    i'm sorry Mr Mouse i didnt take a look there before.
I used PsychonautsExplorer1.3 and its wav files only and i cant read the wav i installed the codec for it and still weird sound.
But anyway the 3D model arent there so i guess they are in the *.xxx files and dunno if you can look at it.
I have a ini files from the game with directory line so perhaps more easy for find the files in the *.xxx.
really hope you find a away for open them so i can finally mod.
Rheini ty a lot i'm gonna take a look    it's pretty hard to start with all the numbers and stuff but just really wnt to learn when i see what i can do next for mod games.
[Coalesced.rar](https://xentaxbackup.github.io/file/1412_Coalesced.rar)
## Post #8
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2007-12-20T14:04:28+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-12-28T12:08:28+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-28T14:22:44+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

Nice work, Silver.
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-28T17:33:35+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

> Reply from Silver
>
> This file looks compressed with LZO compression.
Has anyone tested it?

EDIT: Maybe [http://www.lzop.de](http://www.lzop.de) is appropriate for that.
## Post #12
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-12-29T19:59:23+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

> Reply from Rheini
>
> Silver wrote:This file looks compressed with LZO compression.
Has anyone tested it?

EDIT: Maybe http://www.lzop.de is appropriate for that.

I'm not sure that'll do the trick. The Gears of War thread has a decompressor attached in there... I have not tried it but that would be more suitable.

I used some existing code in a project to test it,

Based on the .xxx file provided above from data at
0x1EB0D
Based on syntax above:
file size = 34901 bytes
Decompressed size = 65536 bytes

So input = data from 0x1EB0D to 0x27362
and after decompression output = 65536 bytes

Works for me,
cheers
[LZO_TEST.zip](https://xentaxbackup.github.io/file/1414_LZO_TEST.zip)
## Post #13
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2007-12-30T06:36:46+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

Wow nice job Ty for taking a look a it.
I understand only 30% of what was said.. i still learn how to look into a file etc..
Do you think it's possible to make an extractor/replace file ? like the other file from the unreal engine its encrypted    just hope one of you find a way for get the file inside.
Thanks again
## Post #14
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2008-01-24T04:30:18+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

Hi all   
I'm still trying to find how to extract and too much complicated for me i think    i'm learning slowly how to check file format and what is inside etc..
Did someone found a way for extract and replace the files ? or if some one already made an extractor for *.xxx files of Gear of war so perhaps can work with this one.
Thanks for the one who take a look already i wish i can mod the game soon .. long time i wait for do this.
## Post #15
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2008-03-21T08:47:25+00:00
- Post Title: [Xbox360] Mass Effect .xxx .isb and .jnk files

Hello !! long time i didnt come here hehe
Well i took a lot of time for find a way to extract the files and hard cause busy too :s
So i kinda stopped cause its a kind of files to much complicated for me im really a beginner.
I just hopped to see someone find a way and make something for let me extract and replace the files cause i would love to mod this game.
If someone can find .. i thanks a lot. ( sorry for my bad english )
## Post #16
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-04-03T10:45:33+00:00
- Post Title: Re: [Xbox360] Mass Effect .xxx .isb and .jnk files

Mass Effect is based on Unreal 3 engine.
Though, extraction of data can be done, you cant replace it, because *.xxx files are signed with SHA-1 shecksum, and checksums are situated in default.xex file.
As we all know, .xex files can not be modified right now.
## Post #17
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-04-03T22:05:17+00:00
- Post Title: Re: [Xbox360] Mass Effect .xxx .isb and .jnk files

Correct me if im wrong, but SHA1 doesent use any type of keys. So we could simply decompile the .xex in IDA and find the algorithim. Then we could simply recalculate it via an app.
## Post #18
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-06-30T05:58:37+00:00
- Post Title: Re: [Xbox360] Mass Effect .xxx .isb and .jnk files

> Reply from grimdoomer
>
> Correct me if im wrong, but SHA1 doesent use any type of keys. So we could simply decompile the .xex in IDA and find the algorithim. Then we could simply recalculate it via an app.

After we recalculate them, wee need to patch default.xex because checksums table is situated in default.xex
That is not possible
## Post #19
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2008-07-02T21:04:39+00:00
- Post Title: Re: [Xbox360] Mass Effect .xxx .isb and .jnk files

yes sha1 is only a simple hash algorithm and can be recalclulated if something is patched. but if they check this hash value, you can make it.
## Post #20
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-03-12T07:16:09+00:00
- Post Title: Re: [Xbox360] Mass Effect .xxx .isb and .jnk files

how do you extract from xx files, not really interested in recompiling the files. Is there an extractor built which can do this?
## Post #21
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-04-24T08:27:48+00:00
- Post Title: Re: [Xbox360] Mass Effect .xxx .isb and .jnk files

The problem about UT3 xxx files is generally that they are very variable. Nearly every Ut3 Engine game has a other size for the Header and the header i also very variable. Anyway what did you want to extract plodtrew?
