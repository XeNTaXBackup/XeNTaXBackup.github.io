## Post #1
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-08-20T15:09:22+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

Hello!!

I would like to ask for some help.
I worked time ago in what was called "neogeo injections" (change the game form a genuine vc game to another)
[http://www.wiiso.com/mu-all-possible-t19984.html](http://www.wiiso.com/mu-all-possible-t19984.html)
[http://www.youtube.com/watch?v=5i1W9aLbjRw](http://www.youtube.com/watch?v=5i1W9aLbjRw) (old video)
I was able to do "all possible" (they have a maximum file size), but now, in new genuine games, appeared the "game file" compressed (game.bin  ->game.bin.z)

File
[http://uppit.com/0jbjnc01ebuo/file_to_unpack.rar](http://uppit.com/0jbjnc01ebuo/file_to_unpack.rar)


The "problem" was the game.bin.z file. And Stev418 and GameZelda suggest a Zlib compresion.



Last week i could decompress that file using offzip (Luigi Auriemma):
[http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)
I renamed game.bin.z to game.z and then:
"offzip -A game.z game 0x0" (where "game" is the directory where i what to extract the file)


> Offset file unzipper 0.3.3 (offzip)
>
> a very useful tool to unpack the zip (zlib/gzip/deflate) data contained in any type of file included raw files, packets, zip archives, executables and anything else.
>
> it's needed only to specify the offset where the zip data starts or using the useful -S search options able to find any possible zip block contained in the provided file.
>
> naturally there are also other options for extracting all the zip blocks which have been found or dumping them as in their original compressed form.
>
> it's also possible to choose a windowBits value for scanning both the zlib (RFC1950) and deflate (RFC1951) blocks (for example -z -15 for common zip files and so on).

I got a file called "00000000.dat" with good data insite, its not a corrupted file (i recognice the content because its more or less the same form "old files", with some modifications)

Now, after the study of 00000000.dat file, i need to compress a new file... (with diferent data in it)

Could you please help me with this?

Thanks in advance.

Sr Corsario
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-20T16:54:58+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

did you try -a -z -15
## Post #3
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-08-20T17:09:09+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

I need to repack/recompress but the zlib compresion its not standard.

Have you got any idea?
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-08-20T17:10:24+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

is the file you want to unpack the game.bin.z? or did i miss something?
since the game.bin unpacks fine here using zlib decompression, it depacks into a 50MB ROM file.

Edit: aha, you need to recompress it aswell. now i understand.
## Post #5
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-08-20T17:40:02+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

Thanks for having a look!!

Thats important for me, because this could be the missed step for big neogeo games injections... (in case wii can support it... its difficult to explain)

Thanks

Sr Corsario
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-20T21:02:36+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

i wrote a quick program to handle your .z files (with maximum compression) - its a 7z archive within a zip so i could upload it

not sure if this was your question ?
[zlib.zip](https://xentaxbackup.github.io/file/3360_zlib.zip)
## Post #7
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-08-20T21:41:40+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

> Reply from WRS
>
> i wrote a quick program to handle your .z files (with maximum compression) - its a 7z archive within a zip so i could upload it

not sure if this was your question ?

EDit:Something is wrong, the compressed and "re-compressed" are differents.
I will continue testing this afternoon and post results. 

Thanks a lot!!



Sr Corsario
## Post #8
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-08-21T12:43:38+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

Sorryyyy!!


There are a problem!!

When i Repack the file it is smaller than the original compresed file 

The last 56.145bytes are missing  but all the other data is perfect!





I tried with another game.bin.z file (from another game) and i got the same problem!! in that case the last 56.069bytes are missing


Thanks again
## Post #9
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-08-23T13:59:25+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

Sorry for insist... but i cant do anything else if i cant repack the file properlly 


Pleeeeaseee!! Are you on hollidays? xD

Thanks again!
## Post #10
- Username: lavers
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 25, 2009 12:58 pm
- Post datetime: 2010-08-25T02:49:11+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

hey there, try xpert2 and the buit in zlib de/compressor worked perfectly for me - i pmd you also on gbatemp
## Post #11
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-08-25T13:27:02+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

thats working perfect!!

Thanks!!

I hope it will works for my purpouse 

Sr Corsario
## Post #12
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-28T12:48:29+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

i was away but im glad you found one that works
## Post #13
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-09-07T15:42:06+00:00
- Post Title: Wii - VC - Neogeo - Game.bin.z file -decompress and compress

> Reply from WRS
>
> i was away but im glad you found one that works

Thanks for your help anyway. 

Im preparing another request... xD this time about audio encoding xD  (GCA files)
I will formalice the request when i compile all the information.

Thanks
