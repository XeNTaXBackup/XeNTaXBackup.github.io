## Post #1
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-10-31T00:12:24+00:00
- Post Title: [HOWTO] Extracting Fallout 3 archives

Hey guy  

If anybody if interested how to extract a BSA files from fallout3 then I can help you...

This game uses new version of archives,but this change is applied only on textures.bsa archive.

So how to unpack remaining archives ? just open any archive in hex editor,go to offset 4 and change value from $68 to $67. They you open this archive in any BSA extractor (BSAUnpack,BSA Commander and so on...) and extract all files (game should work with extracted files 

So whats changed in textures.bsa ?
This archive has before raw zlib stream saved a name of file (with full path),so you just need to skip this string to start offset of zlib stream.

If anybody is interested,then I can make a tool to convert textures.bsa to normal archive (v103),because its not so easy as changing only one byte 

So happy modding guys
## Post #2
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2008-10-31T06:59:06+00:00
- Post Title: [HOWTO] Extracting Fallout 3 archives

only different is version number fallout3 is 0x68,Oblivion is 0x67.
so open with hexwork change byte 5 from 68 to 67.
## Post #3
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-10-31T18:43:15+00:00
- Post Title: [HOWTO] Extracting Fallout 3 archives

> Reply from titanic
>
> only different is version number fallout3 is 0x68,Oblivion is 0x67.
so open with hexwork change byte 5 from 68 to 67.

Are you dumb or lame ?:P I told you this trick and you tell me that backward ? Did you already tried to extract textures.bsa ? probably not because then you will know that its changed in a way I described in this thread...
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2008-10-31T23:04:23+00:00
- Post Title: [HOWTO] Extracting Fallout 3 archives

> Reply from Crypton
>
> Hey guy  
If anybody is interested,then I can make a tool to convert textures.bsa to normal archive (v103),because its not so easy as changing only one byte

So, I'm the first one who's interested  And maybe not the last one. Can you make that tool, please?
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2008-11-01T16:54:35+00:00
- Post Title: [HOWTO] Extracting Fallout 3 archives

And I got a question. How to edit Fallout 3 .esp files? Does anybody know?
## Post #6
- Username: srcs34k
- Rank: n00b
- Number of posts: 14
- Joined date: Wed May 23, 2012 11:45 pm
- Post datetime: 2013-12-21T04:44:52+00:00
- Post Title: [HOWTO] Extracting Fallout 3 archives

BSA Unpacker 
[http://www.playground.ru/cheats/bsa_unpacker-11055/](http://www.playground.ru/cheats/bsa_unpacker-11055/)

> BSAUnpack by Timeslip
>
> http://timeslip.chorrol.com
>
> 
>
> Requires .NET 1.1!
>
> 
>
> ***********
>
> ** Usage **
>
> ***********
>
> 
>
> This is a utility for viewing the files contained within an oblivion bsa archive and
>
> unpacking them. To use, just run the exe file. Click open and select the bsa archive you
>
> want to extract. A list of files contained within the archive will be displayed. You can
>
> extract a single file by double clicking on it, extract multiple files by selecting them
>
> and then clicking extract, or extract the whole archive by clicking extract all. You can
>
> also sort the files contained in the archive using the combo box to the right. Select
>
> the variable you wish to sort by, and click sort. (It isn't kept sorted automatically,
>
> because otherwise it takes several minutes to open large BSA archives, such as the
>
> compressed textures archive.)
>
> 
>
> *****************
>
> ** Limitations **
>
> *****************
>
> 
>
> This is a standalone version of a utility from oblivion mod manager, and may not be kept
>
> up to date. (This particular version was taken from somewhere between obmm 0.6 beta 1
>
> and beta 2)
>
> 
>
> obmm is a .NET 2.0 application, and some features needed to be removed from this BSA
>
> browser in order to retarget it at .NET 1.1. Most notably, there is no progress bar when
>
> unpacking archives, and you cannot view the sizes of files before extracting them.
>
> 
>
> *************
>
> ** Credits **
>
> *************
>
> 
>
> I played no part in decoding the BSA file format. I believe ghostwheel was the first to
>
> do it, although according the uesp wiki history, the information was entered by rick.
>
> This utility is based entirally on the data taken from uesp, so whoever originally
>
> worked out the information, thanks.
[BSA_unpacker-3117.7z.zip](https://xentaxbackup.github.io/file/6868_BSA_unpacker-3117.7z.zip)
