## Post #1
- Username: phlyingpig
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 21, 2010 1:51 am
- Post datetime: 2010-10-20T19:04:20+00:00
- Post Title: Problems in extracting wii files.

These are some files I'm trying to extract. 
I have read the QUICKBMS GUIDE but still can't find the rules of the .arc files.
The path name in the header is clear but I have no idea of the other fields.

Could anybody give some advice of extracting?

And there is no filename extension  in the path. How could I know the format of the models?
[pl000.zip](https://xentaxbackup.github.io/file/3545_pl000.zip)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-20T20:08:28+00:00
- Post Title: Problems in extracting wii files.

what wii game is it. if its an arc there is a nintendo game there is an arc extractor on the internet
## Post #3
- Username: phlyingpig
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 21, 2010 1:51 am
- Post datetime: 2010-10-21T01:03:27+00:00
- Post Title: Problems in extracting wii files.

Sengoku basara 3 
A Capcom game.

I have tryied many tools to extract but no one works. Include some extractor for Capcom's  PC games.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-21T02:01:06+00:00
- Post Title: Problems in extracting wii files.

same as ps3 archive and same as re5 archive this will extract the files.

> endian big
>
> get idstring long
>
> get version short
>
> get files short
>
> comtype zlib_noerror
>
> for i = 0 < files
>
> getdstring name 0x40
>
> get type long
>
> string name + .
>
> string name + type
>
> get zsize long
>
> get size long
>
> get offset long
>
> clog name offset zsize size
>
> next i
## Post #5
- Username: phlyingpig
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 21, 2010 1:51 am
- Post datetime: 2010-10-21T03:12:24+00:00
- Post Title: Problems in extracting wii files.

Thank you so much for your help.
Have been troubled for a few weeks since the game released.

Now I'm trying to convert it to some format that 3ds can open.
Is there any rules in this kind of files or tools to convert?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-21T03:29:47+00:00
- Post Title: Problems in extracting wii files.

not yet i am working on the ps3 models.
I do not plan to support wii models unless they are the same format.
## Post #7
- Username: phlyingpig
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 21, 2010 1:51 am
- Post datetime: 2010-10-21T03:53:33+00:00
- Post Title: Problems in extracting wii files.

what does the format relate to?
the platform? or the company which made the game?

ummmmm....
I have seen the models of wii games you have posted on another forum. So I think maybe there is some experience you could share.

This is a wii/ps3 game. Does it mean anything?
## Post #8
- Username: phlyingpig
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 21, 2010 1:51 am
- Post datetime: 2010-10-21T05:08:17+00:00
- Post Title: Problems in extracting wii files.

done. they are brmdl files.
## Post #9
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2010-10-21T15:38:53+00:00
- Post Title: Problems in extracting wii files.

yes, they are brmdl, so they can be easily extracted with different tools, but  Wii models have a lower quality than the ps3 ones.
## Post #10
- Username: phlyingpig
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 21, 2010 1:51 am
- Post datetime: 2010-10-24T14:29:30+00:00
- Post Title: Problems in extracting wii files.

The brres viewer for wii is perfect now but I couldnt find any tools to view the models in ps3 games.

the directory tree of the both edition are the same and i can extract the ps3 files with the same script but i cant view the models. Is there any tools released at present to view ps3 models?
