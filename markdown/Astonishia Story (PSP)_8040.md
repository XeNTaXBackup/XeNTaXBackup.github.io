## Post #1
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-13T01:22:20+00:00
- Post Title: Astonishia Story (PSP)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-13T10:01:26+00:00
- Post Title: Astonishia Story (PSP)

at a first look I can't see anything useful inside here. Can you provide the (unencrypted) executable or some other smaller file inside the iso?
## Post #3
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-13T11:05:32+00:00
- Post Title: Astonishia Story (PSP)

> Reply from Vash
>
> at a first look I can't see anything useful inside here. Can you provide the (unencrypted) executable or some other smaller file inside the iso?

excuatable of what? since this is a PSP game, you mean an unencrypted eboot? I doubt this will help or will it ?
also as I mentioned above, this is the only file in the ISO, there are no smaller .dat
also this is the complete structure of the ISO:

[http://i.imgur.com/Sdxh5.png](http://i.imgur.com/Sdxh5.png)

And inside the folders another not-so-useful files (except in translation of course(changing the font))
data\font\kor0.fnt
data\font\kor1.fnt
data\movie_psp\opening.pmf [Playable video using MPC]
data\movie_psp\staffroll.pmf [Playable video using MPC]

Thanks for taking a look!
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-13T12:33:52+00:00
- Post Title: Astonishia Story (PSP)

With executable, yes, I meant the EBOOT. In many games pointers to the big archives are inside there but while waiting I took it myself and I think that there's nothing useful in there. So far I have good news and bad news. 
The good news is that I recognized the compression, it's probably LZSS with some strong variant so nothing standard (IMHO, still have to check with some code) but not even impossible to crack by hand.
The bad news is that you don't have filenames/dirnames so if I or someone else manage to crack this format you will have many many little files without extension and you will go crazy identify them, especially if are thousands of them.

About pointers, I have some ideas, still testing them

btw, those fonts are just the psp standard korean ones, so I don't think will turn useful for some translations
## Post #5
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-13T13:05:37+00:00
- Post Title: Astonishia Story (PSP)

> Reply from Vash
>
> With executable, yes, I meant the EBOOT. In many games pointers to the big archives are inside there but while waiting I took it myself and I think that there's nothing useful in there.

What do you usually expect when looking for pointers? when looking in 01editor(the program I use) it's hard to distinguish between int/string/unicode and real pointers isn't it??
also can't they be encrypted as well or it's not technically possible to encrypt such info?
(sorry for the not-so-smart question   )

> The bad news is that you don't have filenames/dirnames so if I or someone else manage to crack this format you will have many many little files without extension and you will go crazy identify them, especially if are thousands of them.

Sure, it's annoying, perhaps I (we) can make a header reading program and move the files to temporary folders where we can use them and if I (we) want to modify the game somehow, we'll reverse the opration, move the files again and re-insert them and compress them again...thought it's a lot of work, especially with headerless and similar files..hmmm

> btw, those fonts are just the psp standard korean ones, so I don't think will turn useful for some translations

Oh didn't know that, then they aren't useful for translations

Thanks again!
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-13T13:21:43+00:00
- Post Title: Astonishia Story (PSP)

> What do you usually expect when looking for pointers? when looking in 01editor(the program I use) it's hard to distinguish between int/string/unicode and real pointers isn't it??
>
> also can't they be encrypted as well or it's not technically possible to encrypt such info?
>
> (sorry for the not-so-smart question   )

it's hard to explain what to expect since there is no standard in this kind of thing, I just have a trained eye. They could be encrypted/compressed or whatever, I just don't think so (explanation is at the bottom)

> Sure, it's annoying, perhaps I (we) can make a header reading program and move the files to temporary folders where we can use them and if I (we) want to modify the game somehow, we'll reverse the opration, move the files again and re-insert them and compress them again...thought it's a lot of work, especially with headerless and similar files..hmmm

yes, IF there are some headers  but this problem is secondary I'd say



anyhow, while taking a deeper look I'm starting to think that there are no pointers, are just some data with some info before the actual stream.

for example, the first bytes are 

0x1620 
0x0000 (or simply 0x00001620)
0x0900 
0x1004. 

I can't say I understand them BUT if you go at 0x1004 (SEEK_SET) you can find a similar pattern: 

0x3C20
0x0000 (or simply 0x00003C20)
0x0400
0x1004

which doesn't really apply for the next file (a.k.a if you go to 0x2008 - 0x1004+0x1004 - you will land in the middle of some text)

I'll keep on looking while I can but if someone else is luckier, please write
## Post #7
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-13T13:31:22+00:00
- Post Title: Astonishia Story (PSP)

> Reply from Vash
>
> it's hard to explain what to expect since there is no standard in this kind of thing, I just have a trained eye. They could be encrypted/compressed or whatever, I just don't think so (explanation is at the bottom)

ok

> anyhow, while taking a deeper look I'm starting to think that there are no pointers, are just some data with some info before the actual stream.
>
> 
>
> for example, the first bytes are 
>
> 
>
> 0x1620 
>
> 0x0000 (or simply 0x00001620)
>
> 0x0900 
>
> 0x1004. 
>
> 
>
> I can't say I understand them BUT if you go at 0x1004 (SEEK_SET) you can find a similar pattern: 
>
> 
>
> 0x3C20
>
> 0x0000 (or simply 0x00003C20)
>
> 0x0400
>
> 0x1004
>
> 
>
> which doesn't really apply for the next file (a.k.a if you go to 0x2008 - 0x1004+0x1004 - you will land in the middle of some text)
>
> 
>
> I'll keep on looking while I can but if someone else is luckier, please write

hmm, not really useful, thought it's start, i'll look for patterns in the file, but because of compression it'd be futile..
## Post #8
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-13T13:38:52+00:00
- Post Title: Astonishia Story (PSP)

no it won't, the compression is not applied to the whole file but to every each subfile, that's why we need to understand how are they disposed. For it's nature the LZ algorythms need the Compressed Length and the Decompressed Length to be passed, so those 2 values need to be there somehwere
## Post #9
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-13T13:41:05+00:00
- Post Title: Astonishia Story (PSP)

> Reply from Vash
>
> no it won't, the compression is not applied to the whole file but to every each subfile, that's why we need to understand how are they disposed.
Ok, i'll see what I can do

> For it's nature the LZ algorythms need the Compressed Length and the Decompressed Length to be passed, so those 2 values need to be there somehwere
Ok
## Post #10
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-14T23:40:22+00:00
- Post Title: Astonishia Story (PSP)

my 01editor trial expired    , i'll try once I find an alternative that suits me.
[http://i.imgur.com/NAr6n.jpg](http://i.imgur.com/NAr6n.jpg)
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-15T01:14:57+00:00
- Post Title: Astonishia Story (PSP)

I don't think it's compressed.
I think the file is just scrambled (no particular technical term)

at offset 0x2CDE21E you can see something that looks like an index buffer, though that could be coincidence, or just something entirely different.

At the beginning of the file you can see "hun ter suit", except there's a null char after the "hun"

If it's an archive, then maybe it's just the file table that's scrambled?

Expired? Registry. dot dot dot
## Post #12
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-15T12:04:11+00:00
- Post Title: Astonishia Story (PSP)

> Reply from finale00
>
> 
at offset 0x2CDE21E you can see something that looks like an index buffer, though that could be coincidence, or just something entirely different.

I don't know what an index buffer is, but a search says that it's something to do with 3d models?

> At the beginning of the file you can see "hun ter suit", except there's a null char after the "hun"

Perhaps this where LZ77(SS) kicks in?

> If it's an archive, then maybe it's just the file table that's scrambled?

Let me try   :
Filenames ? ->  02EAB60A,02EA6E0E
Similar pattern: 02EA6C01(and Above) perhaps it's their way of padding? ([http://i.imgur.com/At1mq.jpg](http://i.imgur.com/At1mq.jpg))
encrypted directory (and file) -> 0179C1AF (similar encryption to DGTEFF's PainKiller?)
## Post #13
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-15T13:22:58+00:00
- Post Title: Astonishia Story (PSP)

the files are definitely compressed, I compared ram and some text, it's LZsomething.

at those address there's nothing useful, it's probably something that has to do with the fonts, just that
## Post #14
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-16T14:12:56+00:00
- Post Title: Astonishia Story (PSP)

hello again, looks like I picked the wrong game to explore,
anyway, once I improve on exploring file formats, i'll return back to xentax
thanks to all who helped
