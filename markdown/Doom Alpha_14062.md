## Post #1
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-03-07T20:25:54+00:00
- Post Title: Doom Alpha

[out]
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-03-07T23:44:28+00:00
- Post Title: Doom Alpha

DOOMExtract-1.1.zip (includes source code and example mod)
[http://gofile.io/?id=H1C8Aw](http://gofile.io/?id=H1C8Aw)
## Post #3
- Username: iOrange
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2016 10:56 pm
- Post datetime: 2016-05-02T03:09:01+00:00
- Post Title: Doom Alpha

Use this tool - DoomResEx (DooM Resources Explorer)
[https://bitbucket.org/iOrange/doomresex ... Ex_v01.zip](https://bitbucket.org/iOrange/doomresex/downloads/DoomResEx_v01.zip)
## Post #4
- Username: Matsilagi
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Aug 31, 2014 12:39 pm
- Post datetime: 2016-05-04T13:59:57+00:00
- Post Title: Doom Alpha

Does this rip models with skeletons + anims?
## Post #5
- Username: iOrange
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2016 10:56 pm
- Post datetime: 2016-05-11T18:17:21+00:00
- Post Title: Doom Alpha

> Reply from Matsilagi
>
> Does this rip models with skeletons + anims?

Yesm the new version does - [http://www.moddb.com/games/doom-4/downl ... plorer-v03](http://www.moddb.com/games/doom-4/downloads/doom-resources-explorer-v03)
## Post #6
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2016-05-16T00:55:39+00:00
- Post Title: Doom Alpha

reimport possible?
## Post #7
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2016-05-28T03:02:29+00:00
- Post Title: Doom Alpha

> Reply from Ekey
>
> DOOMExtract-1.1.zip (includes source code and example mod)
http://gofile.io/?id=H1C8Aw

I've released DOOMExtract 1.3 a few weeks ago, only major change is that it supports beta (and also retail) resources, and I think 1.1 was missing the file deletion option.

Download: (download 1.4 in the post below)

I tested this with the alpha and beta resources and it can unpack/repack fine, doesn't look like retail has changed resources format so it should work with that too, though I'm not sure if repacking will work properly as they've added a signature/hash check in the form of .verify files (that might just be to stop you playing online with modded files though)

Files might be named weirdly as DOOMExtract appends the fileType field to the filename (eg. instead of allowoverlays.decl it'd be called allowoverlays.decl;renderParm), this is to let you specify the fileType field when repacking.

From the readme:

> DOOMExtract is a tool that lets you extract the gameresources.resources file from the DOOM Closed Alpha and Beta.
>
> It can also repack the resources file, allowing you to modify existing files, add new ones and also delete files.
>
> 
>
> Extraction: DOOMExtract.exe [pathToIndexFile] <destFolder>
>
>   If destFolder isn't specified a folder will be created next to the index file.
>
> 
>
>   Files with fileType != "file" will have the fileType appended to the filename.
>
>   eg. allowoverlays.decl;renderParm for fileType "renderParm"
>
> 
>
>   Example: DOOMExtract.exe C:\DOOM\base\gameresources.index
>
>        will extract the resources into C:\DOOM\base\gameresources\
>
> 
>
>   You should also be able to drag+drop the resources.index file into the DOOMExtract exe.
>
> 
>
> Repacking: DOOMExtract.exe [pathToIndexFile] --repack <repackFolder>
>
>   Will repack the resources with the files in the repack folder.
>
>   Note that files that don't already exist in the resources will be added.
>
>   Files that are replaced/added won't be compressed in the resources file neither, so the filesize of it might increase a bit.
>
> 
>
>   To set a new files fileType append the fileType to its filename.
>
>   eg. allowoverlays.decl;renderParm for fileType "renderParm"
>
> 
>
>   Example: DOOMExtract.exe C:\DOOM\base\gameresources.index --repack C:\DOOM\mods\
>
>        will repack the resources with the files from C:\DOOM\mods\
>
> 
>
> Deleting files: DOOMExtract.exe [pathToIndexFile] --delete [file1] <file2> <file3> ...
>
>   Will delete files from the resources package. Full filepaths should be specified.
>
>   If a file isn't found in the package a warning will be given.
>
> 
>
>   Example: DOOMExtract.exe C:\DOOM\base\gameresources.index --delete generated/buildgame/init.mapresources generated/buildgame/dev/mp_bigbox.mapresources
>
>       will delete generated/buildgame/init.mapresources & generated/buildgame/dev/mp_bigbox.mapresources from the resources package.
## Post #8
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2016-06-01T01:53:40+00:00
- Post Title: Doom Alpha

Another update for DOOMExtract, likely the last unless any other issues come up.

This update fixes a big issue with adding new files to resource packages - if the file you're adding doesn't already exist, and isn't in the root folder, it'll be added to the package as a new entry.. but the path separator character will use Windows' "\" instead of "/" as the game expects, meaning the game would never actually be able to access the file you've added. This has been fixed in 1.4.

If anyone has been working on mods (or trying to port stuff over to the beta/vice versa) and been having issues, it might be worth trying again with this new version.

DOOMExtract 1.4 download (source included): [http://www78.zippyshare.com/v/hIdhc6Ex/file.html](http://www78.zippyshare.com/v/hIdhc6Ex/file.html)
## Post #9
- Username: SporeAltair
- Rank: advanced
- Number of posts: 63
- Joined date: Sun Mar 20, 2016 1:47 am
- Post datetime: 2016-06-08T16:28:27+00:00
- Post Title: Doom Alpha

Regrettably this program (DOOMExtract) is not extract the files from the full version of the game, it crashes on completion of unpacking and removes all the extracted files.
## Post #10
- Username: WonDoe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 28, 2015 10:57 am
- Post datetime: 2016-07-12T08:30:18+00:00
- Post Title: Doom Alpha

No updates on DoomExtract for Vulkan patch?
## Post #11
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2017-02-08T22:04:27+00:00
- Post Title: Doom Alpha

Sorry for the lack of updates lately, but I've just recently gone back to fixing DOOMExtract. The latest release should be able to extract from the final game fine now (no more OutOfMemory errors neither), make sure to extract to a small path name though, eg. a folder on the root of your drive, otherwise you might run into a PathTooLongException as the game has some pretty long filenames.

I've also added support for the .patch/.pindex files too, as well as allowing you to create your own patches. These don't really work like traditional patches, instead they contain full replacement files + any new files, they also kinda act as a replacement filesystem for the game (the filesystem inside patches contains all the file entries from previous patches, but sometimes it might remove files, eg. say patch1 contains a file "xyz.txt", if the filesystem in patch2 doesn't also contain this file it won't be seen by the game at all, despite the data for it still being available in patch1)

Patches also don't have to contain the data for files that are inside previous patches, instead the filesystem can just point to an earlier patch files data (meaning you should only modify the latest patch file, if you change an earlier one these pointers might no longer point to the correct data!)

Hope I explained that well enough... the readme file included with the binary also explains patches a bit more in-depth, but if you have any questions feel free to ask.

Download: [https://github.com/emoose/DOOMExtract](https://github.com/emoose/DOOMExtract) (click the releases tab for compiled binaries)
