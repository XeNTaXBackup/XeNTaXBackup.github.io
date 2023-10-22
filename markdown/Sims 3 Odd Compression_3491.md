## Post #1
- Username: JMPescado
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 18, 2009 10:10 pm
- Post datetime: 2009-05-18T17:03:55+00:00
- Post Title: Sims 3 Odd Compression

I posit the following question here to see if anyone here might have any idea what the heck this is.
We know that it's the scripts package from The Sims 3. However, it does not appear using the standard zlib compression that all the other Sims packages are using: Instead, it is some sort of unknown compression, encryption, or both, as the patterns of data show a distinctly compressed or encrypted form, with practically no repeating strings that are typical of bytecodes or text script, except at the very end of the file (which is sometimes filled out with zeroes). We have been unable to discern the algorithm or method used and figured someone here might have more experience and insight into the matters.

Interesting things we've noticed so far is that all of the files share the same ~5-byte starting header, but that's about it. Additional samples can be made available on request.

[Linked here](http://www.moreawesomethanyou.com/horror/scripts.zip), because the file exceeds the 256k limit here, are some samples of the files extracted from the packages, which are/were a standard DBPF v2 similar to those used in Spore, which we have managed to decipher.

[scripts.zip](http://www.moreawesomethanyou.com/horror/scripts.zip)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-18T20:29:14+00:00
- Post Title: Sims 3 Odd Compression

Dude, wtf, you are fast 
I didn't even know Sims 3 was leaked until now.

Edit: These files seem to be encrypted. What kind of scripts do they use?
Edit2: What's the format of the package files?
## Post #3
- Username: JMPescado
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 18, 2009 10:10 pm
- Post datetime: 2009-05-18T23:34:20+00:00
- Post Title: Sims 3 Odd Compression

> Reply from Rheini
>
> Edit: These files seem to be encrypted. What kind of scripts do they use?We do not know. We believe they may be LUA, because LUA is hinted it at in the executables, yet we cannot find its use anywhere, but it could be anything from LUA, either compiled or uncompiled, to another homebrew bytecode language similar to that used on TS1 and TS2.

> Reply from Rheini
>
> Edit2: What's the format of the package files?The package files are DBPF v2 files, a format that we consider to be well-understood at this stage. I can't find where the extractor is being held at the moment because their site appears to be down, but I have already extracted them from the DBPF file. That particular file represents the contents of the scripts.package file, and the wrapper itself contained no edifying information of any kind.

UPDATE: Edited to add that someone on our team has solved this issue now, although the picture is rather grim as a result. You may close this now.
## Post #4
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-19T18:41:34+00:00
- Post Title: Sims 3 Odd Compression

has anyone found out how to unpack this format yet?
