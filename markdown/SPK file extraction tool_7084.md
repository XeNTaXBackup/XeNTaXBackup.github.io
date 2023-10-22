## Post #1
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-07-30T12:30:42+00:00
- Post Title: SPK file extraction tool

I need this tool, help me find you, thank you!
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T12:35:53+00:00
- Post Title: SPK file extraction tool

For what game.

Try here: [viewforum.php?f=10](http://forum.xentax.com/viewforum.php?f=10)
## Post #3
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-07-30T12:46:51+00:00
- Post Title: SPK file extraction tool

> Reply from finale00
>
> For what game.

Try here: viewforum.php?f=10
PS3 bleach SPK in compression of the model I want to extract, you can help me
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-30T12:54:04+00:00
- Post Title: SPK file extraction tool

spk is not compressed at all its easy to extract.

```
print "%start%"

goto start
endian big
set i 0
for i
savepos offset
get name basename
string name + _
string name + i
string name + .unk
getdstring one 0x14
get size long
math size + 0x20
log name offset size
math offset + size
goto offset
next i 
```
## Post #5
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-07-30T12:57:05+00:00
- Post Title: SPK file extraction tool

> Reply from chrrox
>
> spk is not compressed at all its easy to extract.
Code: Select allfindloc start string "\x0\x0\x0\x1"
print "%start%"

goto start
endian big
set i 0
for i
savepos offset
get name basename
string name + _
string name + i
string name + .unk
getdstring one 0x14
get size long
math size + 0x20
log name offset size
math offset + size
goto offset
next i
Thank you very much, but I want to how to use the code to extract
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-07-30T13:31:42+00:00
- Post Title: SPK file extraction tool

That is a script for [QuickBMS](http://aluigi.org/quickbms.htm).
## Post #7
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-07-30T13:47:58+00:00
- Post Title: SPK file extraction tool

> Reply from merlinsvk
>
> That is a script for QuickBMS.
That the script to how to use it 
I will not use any C language and assembly
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T14:52:18+00:00
- Post Title: SPK file extraction tool

Read the instructions on how to use quickBMS on your own.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-07-31T09:28:13+00:00
- Post Title: SPK file extraction tool

[http://www.youtube.com/watch?v=9afcbJxNvcE](http://www.youtube.com/watch?v=9afcbJxNvcE) Might also help if you have MultiEx Commander.
## Post #10
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-07-31T11:38:22+00:00
- Post Title: SPK file extraction tool

> Reply from finale00
>
> Read the instructions on how to use quickBMS on your own.
But I do not understand
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-31T11:55:40+00:00
- Post Title: SPK file extraction tool

save what i posted as a text file then run quickbms by double clicking on it and follow the prompts.
## Post #12
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-07-31T12:30:06+00:00
- Post Title: SPK file extraction tool

> Reply from chrrox
>
> save what i posted as a text file then run quickbms by double clicking on it and follow the prompts.
I do follow your tips, can be extracted out of all UNK files, how to view UNK documents
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-31T15:27:00+00:00
- Post Title: SPK file extraction tool

Viewing UNK files is different from extracting files from an SPK.
## Post #14
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-08-01T11:30:58+00:00
- Post Title: SPK file extraction tool

> Reply from finale00
>
> Viewing UNK files is different from extracting files from an SPK.
Why do I still UNK file after extraction, there is no tool to do file view UNK
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-01T14:18:28+00:00
- Post Title: SPK file extraction tool

That's because the SPK is an archive and it happens to contain UNK files.
There is no tool to view UNK files because probably no one wrote one.
## Post #16
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-08-02T11:08:18+00:00
- Post Title: Re: SPK file extraction tool

> Reply from finale00
>
> That's because the SPK is an archive and it happens to contain UNK files.
There is no tool to view UNK files because probably no one wrote one.
I see the forum have extracted bleaching paste model, I do want to know how he's
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-02T13:29:21+00:00
- Post Title: Re: SPK file extraction tool

Then ask him. Maybe he will share.
## Post #18
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-08-02T13:51:01+00:00
- Post Title: Re: SPK file extraction tool

> Reply from finale00
>
> Then ask him. Maybe he will share.
But I do not know how to get in touch with him, you can do to help me contact him
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-02T15:28:59+00:00
- Post Title: Re: SPK file extraction tool

Just post it in the thread and maybe he will see it. Or you can PM him.
## Post #20
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-08-03T11:34:19+00:00
- Post Title: Re: SPK file extraction tool

> Reply from finale00
>
> Just post it in the thread and maybe he will see it. Or you can PM him.
Yes, I try
## Post #21
- Username: demork
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 29, 2011 11:21 pm
- Post datetime: 2011-08-29T15:27:58+00:00
- Post Title: Re: SPK file extraction tool

What should we do with unks files???
## Post #22
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-03T02:50:35+00:00
- Post Title: Re: SPK file extraction tool

That's the only problem left, to get it in max.
## Post #23
- Username: the101gamer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 11, 2017 10:51 pm
- Post datetime: 2017-08-15T22:05:22+00:00
- Post Title: Re: SPK file extraction tool

> Reply from chrrox
>
> spk is not compressed at all its easy to extract.
Code: Select allfindloc start string "\x0\x0\x0\x1"
print "%start%"

goto start
endian big
set i 0
for i
savepos offset
get name basename
string name + _
string name + i
string name + .unk
getdstring one 0x14
get size long
math size + 0x20
log name offset size
math offset + size
goto offset
next i
Do you by any chance know of a way to pack the extracted unk files back into spk?
