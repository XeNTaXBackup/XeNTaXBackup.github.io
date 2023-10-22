## Post #1
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-06-05T20:07:04+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

Could someone open the files?

[https://www.mediafire.com/file/s1jz5ho2 ... rs.7z/file](https://www.mediafire.com/file/s1jz5ho20r2fw7e/Juiced_cars.7z/file)
[https://www.mediafire.com/file/12puil5b ... Ts.7z/file](https://www.mediafire.com/file/12puil5bvmhepss/Juiced_DATs.7z/file)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-06-05T20:49:57+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

You can use offzip to unpack/pack files from these archives
[https://aluigi.altervista.org/mytoolz.htm#offzip](https://aluigi.altervista.org/mytoolz.htm#offzip)


Check also the wiki page
[http://wiki.xentax.com/index.php/Juiced_DAT](http://wiki.xentax.com/index.php/Juiced_DAT)
## Post #3
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-12-02T11:22:14+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

Do Juiced .dat files have filenames or what?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-02T11:38:25+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

> Reply from braveplayer50 ↑Thu Dec 02, 2021 7:22 pm at Thu Dec 02, 2021 7:22 pm
>
> 
Do Juiced .dat files have filenames or what?

No filenames. Only hashes.
## Post #5
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-12-02T13:21:13+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

> Reply from ikskoks ↑Thu Dec 02, 2021 7:38 pm at Thu Dec 02, 2021 7:38 pm
>
> 
braveplayer50 wrote: ↑Thu Dec 02, 2021 7:22 pm
Do Juiced .dat files have filenames or what?


No filenames. Only hashes.

Is there a way to get filenames in dat files?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-02T13:53:25+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

> Reply from braveplayer50 ↑Thu Dec 02, 2021 9:21 pm at Thu Dec 02, 2021 9:21 pm
>
> 
Is there a way to get filenames in dat files?

I have already explained you the method here [viewtopic.php?p=175138#p175138](https://forum.xentax.com/viewtopic.php?p=175138#p175138)
and also on xentax discord server.

Stop asking about the same thing multiple times.
If you need to know the details, just go to tutorials section and try to write a hook function.
Here are links to some articles that may be helpful [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

Btw, getting the filenames is not important if your goal is to only modify the game. You don't need filenames for that.
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-12-03T00:38:06+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

The hashing algorithm is pretty simple, I'll share the code a bit later
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-12-03T18:30:43+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

Unpacker for Juiced

Binaries: [here](https://github.com/Ekey/JCED.DAT.Tool/releases)
Sources: [here](https://github.com/Ekey/JCED.DAT.Tool)
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-12-04T15:45:55+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

Unpacker for Juiced 2: Hot Import Nights

Binaries: [here](https://github.com/Ekey/JCED2.JFS.Tool/releases)
Sources: [here](https://github.com/Ekey/JCED2.JFS.Tool)
## Post #10
- Username: SxnnyB
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 25, 2020 4:15 pm
- Post datetime: 2021-12-06T15:49:41+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

We have a method of finding the names via nulling the hash and watching for "file not found" flags using procmon. This can actually be helpful for modding as more can be done if names are known.

 I have personally logged names for quite a few juiced dats and user mariokart64 has provided us a tool for unpacking, and auto naming once names are logged.

Please join us on the juiced modding discord.
[https://discord.gg/pu2jdxR](https://discord.gg/pu2jdxR)

Edit_1: typo
## Post #11
- Username: SxnnyB
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 25, 2020 4:15 pm
- Post datetime: 2021-12-06T17:26:57+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

Ekey, we would love for you to join us as well. Very interested in the work you've shared. 
The community has recently been working to build a new  modding toolset to work with juiced.
Mariokart64's previously mentioned tool has texture conversion mostly functional and another user "N1ghtmare" has a functional soundtrack replacer going now.

Did you find how the names are stored in relation to the hash values? It's been tedious to log each name manually per dat and I was putting off ui.dat until the end simply for its large amount of files.
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-12-06T19:16:41+00:00
- Post Title: Juiced .dat/Juiced 2 .jfs archives

> Reply from SxnnyB ↑Tue Dec 07, 2021 1:26 am at Tue Dec 07, 2021 1:26 am
>
> 
Did you find how the names are stored in relation to the hash values? It's been tedious to log each name manually per dat and I was putting off ui.dat until the end simply for its large amount of files.
They are formed in different ways, for example in scripts.dat there is a text file with all filenames in this archive > filelist.txt, there is no such file in all the others archives. I was able to find about 9k files, which is about 60-70% of all files. To find 90-95% you need to complete the whole game, but I'm tooooooooooooooooooooo lazy ass 

For JC1, I couldn't make a fully working hook, the game crashes after about 5-10 minutes of playing   . For JC2 the  hook works fine
