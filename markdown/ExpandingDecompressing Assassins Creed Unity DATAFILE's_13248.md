## Post #1
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-08-27T20:34:00+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

Hey guys, I have extracted DATAFILE from AC Unity's forge files

I need your help in expanding/decompressing (not extract) "datafiles" of AC unity, or in other words, removing the LZO compression from the "datafile".

Here is the extracted sample :-

```
https://dl.dropboxusercontent.com/u/33463092/TitleScreenFPP.7z
```


Can anyone pls help me with this ? Or make a decompressor which firsts extracts the header and then writes the decompressed data separately ?

I have tried ArchiveNEXT created by MichaelDarkAngel but datafile's expanded/decompressed by it lack something in headers and hence not getting supported by AC Unity (I know the main purpose of ArchiveNEXT is not this).
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-08-27T21:32:31+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

try my AC Repacker, not sure if does it work ro Unity, but it work for ACR and ACHDL, so it could work for ACU as well...
## Post #3
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-08-27T21:54:14+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from michalss
>
> try my AC Repacker, not sure if does it work ro Unity, but it work for ACR and ACHDL, so it could work for ACU as well...

Sorry bro but its not working with AC Unity, I want to decompress/expand these files not extract as files are already extracted.
## Post #4
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-08-27T22:09:30+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

Is this for the PC version of the game?  If so, you could check out my [Wiki](http://wiki.tbotr.net/index.php?title=Assassins_Creed:File_Formats) pages on the file formats.  If you run into any problems, let me know so I can fix them.

--MDA
## Post #5
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-08-28T03:22:57+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from MichaelDarkAngel
>
> Is this for the PC version of the game?  If so, you could check out my Wiki pages on the file formats.  If you run into any problems, let me know so I can fix them.

--MDA

Yes bro its for the PC version of the game. Can you please be so kind and write a simple decompressor which could expand the "datafiles" or a tool which can extract the ".header" & ".data (decompressed)" files since you have already done it for ArchiveNEXT, just need to correct some headers or something which is preventing the game to load those files. I can give examples of AC 4: Black Flag if that helps you a bit.
## Post #6
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-08-29T02:05:53+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from TheRanger
>
> Yes bro its for the PC version of the game. Can you please be so kind and write a simple decompressor which could expand the "datafiles" or a tool which can extract the ".header" & ".data (decompressed)" files since you have already done it for ArchiveNEXT, just need to correct some headers or something which is preventing the game to load those files. I can give examples of AC 4: Black Flag if that helps you a bit.

Why would I need and example file from AC4? (The compressed sections of AC4 and ACU are different)

Not entirely sure what it is you are trying to do.  ARchive_neXt already does what you initially asked for.  Start ARchive_neXt, select Options -> Preferences.  Uncheck "Show Only Known Files" (not really necessary, but this will let you know when a 'datafile' has been decompressed).  Save Changes.  Open an AC:Unity forge file, open a 'datafile'.  Leaving ARchive_neXt running, switch to File Explorer.  Browse to your Documents/TBotR/ARchive_neXt/Temp directory.  There you will find folders for any forge files you have opened.  Inside those folders will be any 'datafiles' you have expanded.  These are the uncompressed datafiles.

If you were to uncheck "Delete Temp folder when exiting", you could expand anything you wanted, close ARchive_neXt and the Temp folder would remain intact.

--MDA
## Post #7
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-08-29T03:40:28+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from MichaelDarkAngel
>
> TheRanger wrote:Yes bro its for the PC version of the game. Can you please be so kind and write a simple decompressor which could expand the "datafiles" or a tool which can extract the ".header" & ".data (decompressed)" files since you have already done it for ArchiveNEXT, just need to correct some headers or something which is preventing the game to load those files. I can give examples of AC 4: Black Flag if that helps you a bit.

Why would I need and example file from AC4? (The compressed sections of AC4 and ACU are different)

Not entirely sure what it is you are trying to do.  ARchive_neXt already does what you initially asked for.  Start ARchive_neXt, select Options -> Preferences.  Uncheck "Show Only Known Files" (not really necessary, but this will let you know when a 'datafile' has been decompressed).  Save Changes.  Open an AC:Unity forge file, open a 'datafile'.  Leaving ARchive_neXt running, switch to File Explorer.  Browse to your Documents/TBotR/ARchive_neXt/Temp directory.  There you will find folders for any forge files you have opened.  Inside those folders will be any 'datafiles' you have expanded.  These are the uncompressed datafiles.

If you were to uncheck "Delete Temp folder when exiting", you could expand anything you wanted, close ARchive_neXt and the Temp folder would remain intact.

--MDA

Yes bro but expanded datafiles extracted using ArchiveNEXT are not supported by the game, when I repack those expanded datafiles into forge files with my rough&dirty forge file repacker, the game just crashes. An example of AC 4 decompressed datafile was just to give an example of how the expanded datafile should be so that the game loads it fine. Since you have already done "datafile expander" for your ArchiveNEXT, it shouldn't be hard to modify a bit and create an expander which can be supported by the game as in "michaelss" tool.
## Post #8
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-08-29T04:13:28+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from TheRanger
>
> Yes bro but expanded datafiles extracted using ArchiveNEXT are not supported by the game, when I repack those expanded datafiles into forge files with my rough&dirty forge file repacker, the game just crashes. An example of AC 4 decompressed datafile was just to give an example of how the expanded datafile should be so that the game loads it fine. Since you have already done "datafile expander" for your ArchiveNEXT, it shouldn't be hard to modify a bit and create an expander which can be supported by the game as in "michaelss" tool.

As I stated before, the compressed sections of AC4 and ACU are different.  If your re-packer works for AC4, the same re-packer will not work for ACU.  You need to re-pack the files correctly for the game they belong to.

--MDA
## Post #9
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-08-29T05:46:58+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from MichaelDarkAngel
>
> TheRanger wrote:Yes bro but expanded datafiles extracted using ArchiveNEXT are not supported by the game, when I repack those expanded datafiles into forge files with my rough&dirty forge file repacker, the game just crashes. An example of AC 4 decompressed datafile was just to give an example of how the expanded datafile should be so that the game loads it fine. Since you have already done "datafile expander" for your ArchiveNEXT, it shouldn't be hard to modify a bit and create an expander which can be supported by the game as in "michaelss" tool.

As I stated before, the compressed sections of AC4 and ACU are different.  If your re-packer works for AC4, the same re-packer will not work for ACU.  You need to re-pack the files correctly for the game they belong to.

--MDA

But my re-packer is working fine for all AC games after AC revelations, if I repack non-expanded/non-decompressed datafiles into forge files of AC Unity then game work fine but when I repack expanded datafiles which I got from ArchiveNEXT then game crashes. Take example of AC 4, if I repack expanded datafiles of AC4 extracted using michaelss tool then it works fine but when I repack expanded datafiles of AC4 extracted using ArchiveNEXT then game crashes, pointing out that expanded datafiles by ArchiveNEXT have something bit different which causes the game to crash. And since michaelss tool can't expand/decompress AC Unity datafiles, its only your ArchiveNEXT which is able to expand it, just need to be corrected a bit for the game to load it.
## Post #10
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-08-29T06:24:38+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

Our tools do not extract/decompress the datafiles the same way.  My decompressed datafile is the complete datafile, michalss' does not have the header section (file count and an index of the details of each file [file ID, file size, and an unknown short]).  In the case of michalss' tool, that's perfectly fine.  If you plan on re-packing you're going to rebuild that index table anyway.

You can still use the uncompressed datafiles from ARchive_neXt, you just need to remove the index table.

--MDA
## Post #11
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-08-29T06:34:55+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from MichaelDarkAngel
>
> Our tools do not extract/decompress the datafiles the same way.  My decompressed datafile is the complete datafile, michalss' does not have the header section (file count and an index of the details of each file [file ID, file size, and an unknown short]).  In the case of michalss' tool, that's perfectly fine.  If you plan on re-packing you're going to rebuild that index table anyway.

You can still use the uncompressed datafiles from ARchive_neXt, you just need to remove the index table.

--MDA

Sir can't you please write a tool to remove the index tables from the expanded datafiles or a tool which decompresses exactly the same way as michaelss' ? It will be really hard for me to do it one by one as there are many files. Please sir... I will be really grateful to you.
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-08-29T17:02:28+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

Also header is compressed, just like raw data.
## Post #13
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-08-31T00:59:09+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from TheRanger
>
> Sir can't you please write a tool to remove the index tables from the expanded datafiles or a tool which decompresses exactly the same way as michaelss' ? It will be really hard for me to do it one by one as there are many files. Please sir... I will be really grateful to you.
[ACUnity_Extractor](http://www.tbotr.net/Downloads/ACUnity_Extractor.zip)

Most likely this will only work with AC:Unity.

Enjoy

--MDA
## Post #14
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-09-04T11:39:10+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from MichaelDarkAngel
>
> TheRanger wrote:Sir can't you please write a tool to remove the index tables from the expanded datafiles or a tool which decompresses exactly the same way as michaelss' ? It will be really hard for me to do it one by one as there are many files. Please sir... I will be really grateful to you.
ACUnity_Extractor

Most likely this will only work with AC:Unity.

Enjoy

--MDA

Thanks but problem is still the same because after combining the header and data, it gives the exact same file which ARchive_neXt gives and hence game doesn't works with it. I have also tried by just importing the data file without header and and by importing both header+data file (combined), but none works. There is something different between the files decompressed using michaelss' tool and your's.
## Post #15
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-09-04T22:47:33+00:00
- Post Title: Expanding/Decompressing Assassins Creed Unity DATAFILE's

Are you compressing them properly?  Are you using the correct format?  You keep talking about michalss' tool, but michalss' tool does not work with Unity.  So you are comparing apples to oranges.  If michalss' tool had worked with Unity, you would not have needed me to write a de-compressor for you.

--MDA
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-09-05T09:22:00+00:00
- Post Title: Re: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from TheRanger
>
> MichaelDarkAngel wrote:TheRanger wrote:Sir can't you please write a tool to remove the index tables from the expanded datafiles or a tool which decompresses exactly the same way as michaelss' ? It will be really hard for me to do it one by one as there are many files. Please sir... I will be really grateful to you.
ACUnity_Extractor

Most likely this will only work with AC:Unity.

Enjoy

--MDA

Thanks but problem is still the same because after combining the header and data, it gives the exact same file which ARchive_neXt gives and hence game doesn't works with it. I have also tried by just importing the data file without header and and by importing both header+data file (combined), but none works. There is something different between the files decompressed using michaelss' tool and your's.

You have to understand that if you want to compress files and use my repacker, it wont work, since i never did adler + crc check, reason for that is simple, you dont need to since game take files also in uncompress state! Also if you check my system you can see im separating header and data during the extraction, which is logical choice if you want to repack them back
## Post #17
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-09-05T14:14:02+00:00
- Post Title: Re: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from michalss
>
> You have to understand that if you want to compress files and use my repacker, it wont work, since i never did adler + crc check, reason for that is simple, you dont need to since game take files also in uncompress state! Also if you check my system you can see im separating header and data during the extraction, which is logical choice if you want to repack them back

Yes, I just want to put those files back in their uncompressed state. What I do is that, I extract&decompress files using ARchive_neXt (since I can't do that using your tool for AC Unity) and re-import them back, but when I start game, it crashes. This is the case with AC Unity, and with AC 4 Black Flag :-

1) I extract&decompress files using ARchive_neXt, re-import them back, game crashes. But

2) When I extract&decompress files using your tool, re-import them back, game works.
## Post #18
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-09-07T06:41:29+00:00
- Post Title: Re: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from TheRanger
>
> michalss wrote:You have to understand that if you want to compress files and use my repacker, it wont work, since i never did adler + crc check, reason for that is simple, you dont need to since game take files also in uncompress state! Also if you check my system you can see im separating header and data during the extraction, which is logical choice if you want to repack them back

Yes, I just want to put those files back in their uncompressed state. What I do is that, I extract&decompress files using ARchive_neXt (since I can't do that using your tool for AC Unity) and re-import them back, but when I start game, it crashes. This is the case with AC Unity, and with AC 4 Black Flag :-

1) I extract&decompress files using ARchive_neXt, re-import them back, game crashes. But

2) When I extract&decompress files using your tool, re-import them back, game works.

Then my tools does not do correct repack for ACU... Nothing you can do about it...
## Post #19
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-09-07T08:06:08+00:00
- Post Title: Re: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from michalss
>
> Then my tools does not do correct repack for ACU... Nothing you can do about it...

But what about AC 4 Black Flag/Rogue ? If I re-import decompressed files of Archive_Next then game doesn't works and if I re-import decompressed files of your tool, game works. I just want to say that there is a difference in files decompressed using Archive_Next, your tool works fine.
## Post #20
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-09-07T10:28:09+00:00
- Post Title: Re: Expanding/Decompressing Assassins Creed Unity DATAFILE's

ok ten send me some example from ACU i will compare outputs... coz MDA cannot help you anymore..
## Post #21
- Username: TheRanger
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-09-07T11:18:02+00:00
- Post Title: Re: Expanding/Decompressing Assassins Creed Unity DATAFILE's

> Reply from TheRanger
>
> But what about AC 4 Black Flag/Rogue ? If I re-import decompressed files of Archive_Next then game doesn't works and if I re-import decompressed files of your tool, game works. I just want to say that there is a difference in files decompressed using Archive_Next, your tool works fine.
[](http://forum.xentax.com/viewtopic.php?p=109157#p109157)
> Reply from MichaelDarkAngel
>
> Our tools do not extract/decompress the datafiles the same way.  My decompressed datafile is the complete datafile, michalss' does not have the header section (file count and an index of the details of each file [file ID, file size, and an unknown short]).

I have already explained to you the reason why you cannot use ARchive_neXt files with the ACR Repacker.

THEY ARE NOT COMPATIBLE!!!

--MDA
## Post #22
- Username: TheRanger
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-09-07T15:39:53+00:00
- Post Title: Re: Expanding/Decompressing Assassins Creed Unity DATAFILE's

I updated my tool but never tested! Neverless this topic is not helpfull.. LOCK
