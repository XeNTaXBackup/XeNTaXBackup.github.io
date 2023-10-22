## Post #1
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-06-30T22:53:43+00:00
- Post Title: Dark Eye: Chains of Satinav

Just some quick info if anyone wants to try to mod the game.

Game uses Visionaire 3 engine. aluigi updated his quickbms script to support the game: [http://aluigi.org/papers/bms/visionaire.bms](http://aluigi.org/papers/bms/visionaire.bms)

Deniz Oezmen made a tool for another Visionaire 3 game which can correct filenames and decrypt png files: [viewtopic.php?f=10&t=5467](http://forum.xentax.com/viewtopic.php?f=10&t=5467) - It'll work with Dark Eye if you recompile his code with this constant: DefaultKey  = 'af0512966ae16580';

Unfortunately, neither tool correctly unpacks the data.vis which contains the XML file with all the correct filenames and gameplay logic. Without that, modding will be a challenge.
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2012-07-12T23:20:27+00:00
- Post Title: Dark Eye: Chains of Satinav

Hi Sectus,

thanks for the info regarding the new key. It seems like the Visionaire team did a small change regarding the compression of the XML file -- it's still ZLib, but processed in multiple blocks rather than a monolithic file. The decryption has to be applied block-wise as well, since the block headers are plain text.

Anyway, I've hacked some preliminary support into my VISExt application. Since I haven't played the game yet, I don't want to delve to deep into all archives -- could you do some tests?


Thanks,
Deniz
[anb.zip](https://xentaxbackup.github.io/file/5579_anb.zip)
## Post #3
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-12T23:52:15+00:00
- Post Title: Dark Eye: Chains of Satinav

It seems to work fine. I can generate name file from it and then use it on other archives to get the correct names. I did get an error about it not being able to get PNG encryption key from filename, but it got it via brute force nonetheless.

Edit: I'm not sure how I can get the game to load the modified xml file though. If I change config file to point to xml instead of data.vis, I get a black screen when loading. Presumably because it isn't loading the other files from data.vis.
## Post #4
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2012-07-13T17:05:40+00:00
- Post Title: Dark Eye: Chains of Satinav

Hi i use it and i have error ( errors detecting key ) i use like this : VISExt.exe data.vis /generateNames:names.txt  is correct ?
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2012-07-13T22:29:34+00:00
- Post Title: Dark Eye: Chains of Satinav

@Sectus: Thanks for the tests. I fixed the PNG decryption problem -- the key is derived slightly different than before, but nothing major. (Though you are right, the brute force approach should be able to determine the correct key anyway. It's more a cosmetical fix ...)

As I said in the ANB thread, I have never tried using the unpacked XMLs to launch the games myself. I still suspect that the file names within the XML file have to be edited for this to work -- at least those pointing to the files extracted from the data.vis. However, that's just a guess.

@hyndai: Your command line looks fine. Are using the data.vis from "Chains of Satinav" or any other Visionaire game -- and which language version? Are there any other error messages or is this the only one?
## Post #6
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2012-07-16T17:02:25+00:00
- Post Title: Dark Eye: Chains of Satinav

I've updated the archive in my post with the additional the additional key 155c703a508c1c8a (which is also already contained in Luigi's BMS) after a board user sent me a sample of an English data.vis that could not be decrypted using the first key.

@hyndai: Could you test the updated tool versions? Maybe your game copy uses the second key as well.

Interesting fact: If I switch the game lanugage to English in my Steam client, it downloads a new copy of data.vis, but that one can be unpacked using the first key. I suspect there are at least two compiled copies of the game out there, possibly region-controlled via Steam.
## Post #7
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2012-08-16T17:43:58+00:00
- Post Title: Dark Eye: Chains of Satinav

Deniz Oezmen >> oki now works, but seem there are no cxml file in names.txt, i have tired with xplozed tools and i have 1 file *.cxml ( in deponia )...
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2012-08-16T22:04:43+00:00
- Post Title: Dark Eye: Chains of Satinav

> Reply from hyndai
>
> Deniz Oezmen >> oki now works, but seem there are no cxml file in names.txt, i have tired with xplozed tools and i have 1 file *.cxml ( in deponia )...
The XML file does not have its own name, so it will not appear in names.txt. Call 
```
visext data.vis /names:names.txt
```
 next and all files from data.vis (including the XML file) will be extracted.
## Post #9
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-04T15:19:04+00:00
- Post Title: Dark Eye: Chains of Satinav

Thank you so much for the program, Deniz Oezmen, yours was the only which worked for me in extracting assets from data.vis. However, since I'm looking to translate the game, I wonder if you plan a repack function for VISExt?
## Post #10
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2013-10-04T19:35:54+00:00
- Post Title: Dark Eye: Chains of Satinav

Hi Rion,

thanks for your feedback. I do have a utility to create VIS archives. However, it belongs to the group of programs concerning the VIS format that I have not released to the public due to legal concerns. (The full toolchain might be abused to circumvent the copy protection scheme of games built with the Visionaire engine.)

I'll check whether it would be "safe" to release this utility alone ...


Edit: There should also be a possibility to do a translation of the game without repacking the archive. However, it involves unpacking all resources of the game. Would you consider whether this approach would be enough for your purpose?

If yes, you might try the following:

Create an empty directory and place VISExt in there.
Within the directory, place a batch file with the following content:
Code: Select all@echo off

set decospath=PLACE_THE_PATH_TO_THE_GAME_HERE

visext "%decospath%\data.vis" /generatenames:names.txt
visext "%decospath%\data.vis" /names:names.txt /cleanxml
visext "%decospath%\characters\character*" /names:names.txt
visext "%decospath%\scenes\scene*" /names:names.txt

md lua
copy "%decospath%\lua\*" lua

copy "%decospath%\*.exe"
copy "%decospath%\*.dll"
copy "%decospath%\*.ico"
copy "%decospath%\*.ini"
copy "%decospath%\*.jpg"
copy "%decospath%\*.xml"

for /f "delims=# tokens=1,2,3,4" %%i in (names.txt) do if /%%j/==/m/ md "%%~pi" & copy "%decospath%\videos\video.vv%%k" "%%i"

del names.txt
del *.dat

ren data.vis_*.xml data.xml

set decospath=

Launch the batch file you just created. It should unpack all game resources and copy over other files needed to run the game into the new directory.
Edit the file config.ini and change the line Code: Select allFILE=data.vis to Code: Select allFILE=data.xml
Launch the game in the new directory. It should do so by reading the unpacked resources. Any changes you make to the XML file should affect the game.

(I currently don't have the game on my computer, so the above batch might miss some files. Apologies if that is the case ...)
## Post #11
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-05T15:46:18+00:00
- Post Title: Dark Eye: Chains of Satinav

Oh, you're so quick to respond, thank you  I'll give this method a try and respond if it works.

Update: It seems you're right, it does not extract everything (output dir: 4,66 GB, game dir: 5,17 GB), and the data.xml it should extract is missing, too. I tried the GoG version. If you need any file to have a closer look at, I can send them.
## Post #12
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2013-10-05T19:18:35+00:00
- Post Title: Dark Eye: Chains of Satinav

As far as I remember, the uncompressed game might actually get smaller due to files that are duplicated across multiple archives. The missing XML file is odd, though.

I do own the GOG version, but it'll be tomorrow before I can take a look at the game.
## Post #13
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-05T19:34:43+00:00
- Post Title: Dark Eye: Chains of Satinav

Thanks, I'm waiting.
## Post #14
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2013-10-06T16:32:44+00:00
- Post Title: Dark Eye: Chains of Satinav

Okay, I have just tried the unpacking process. On my end, the data.xml file was created successfully. Is there any chance you might have missed it under the bunch of "data.vis_xxxxxxxx.dat" files that get created during the unpacking process?

I've updated the content of the batch file in the post above a bit:
Some additional files are now copied as well, though they are not strictly needed to run the game. Some are used by the configuration tool, while others are auxillary files added by GOG.
The "data.vis_xxxxxxxx.dat" files that get created are removed after unpacking. These files are not needed, since they are leftover dialogue sounds from the german language version of the game.

The reason for the size difference is indeed identical files that are stored in multiple archives. If you run VISExt with the "/unique" parameter, the duplicated files won't overwrite each other and you can see the effect. (The game is not executable in this condition, however.) The duplication is a side effect of the way the game's data gets organized into the archives, so it's not something to worry about when unpacking everything.
## Post #15
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-06T17:56:52+00:00
- Post Title: Dark Eye: Chains of Satinav

Then there must be something weird on my end because even now I get every kind of files, but the only .xml I've got is Language.xml. o.O Don't know if it needed to be run as Admin.

I saved a copy of names.txt, and I can't find any .xml filename in it, but I read that that .xml has not a name on its own, it is given by the program.
## Post #16
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2013-10-06T18:43:13+00:00
- Post Title: Re: Dark Eye: Chains of Satinav

That is odd. Have you placed visext.exe as well as vis.key into the directory? What happens when you execute just this command:

```
visext "path_to_game\data.vis" /generatenames:names.txt
```

Does the program generate names.txt? If yes, what happens when you next run

```
visext "path_to_game\data.vis" /names:names.txt /cleanxml
```

Are there any error messages? Does the program extract at least some files with useful names?

You're correct regarding the name of the XML file -- it doesn't havae a name of its own, so the application chooses one.
## Post #17
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-06T18:57:45+00:00
- Post Title: Re: Dark Eye: Chains of Satinav

I created a folder named S in C:\ root, copied Visext.exe and vis.key (since it contains the keys for decrypting) into folder S, created visextract.bat inside the folder, copied exactly what you have written into the .bat, added the path of game (c:\Games\The Dark Eye - Chains of Satinav, without the last \ since your .bat is already containing it under later command strings), and ran the first command:

visext "c:\Games\The Dark Eye - Chains of Satinav\data.vis" /generatenames:names.txt

It created a names.txt with exactly the same size as before, however running this:

visext "c:\Games\The Dark Eye - Chains of Satinav\data.vis" /names:names.txt /cleanxml

Did nothing. I ran it inside DOS shell (cmd), and it comes up with the proper syntax usage of visext.exe. As if it doesn't recognize the second string as a proper command. Could it be that visext cannot identify too long names for folders?

I'm also getting the suspicion that since I'm using the copy of Visext you shared in your first comment, I'm using an outdated version.
## Post #18
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2013-10-06T19:20:55+00:00
- Post Title: Re: Dark Eye: Chains of Satinav

Thanks for your detailed description!

Your suspicion is absolutely correct. The copy of VISExt.exe in this thread is outdated and does not yet support the "/cleanxml" switch, which is why it displays the usage information instead of processing the archive. You can always get the newest program version here: [http://oezmen.eu/gameresources/files/anb.zip](http://oezmen.eu/gameresources/files/anb.zip).

Sorry that I did not recognize this problem earlier; it's so obvious now ...
## Post #19
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-06T20:45:57+00:00
- Post Title: Re: Dark Eye: Chains of Satinav

Now it creates even the data.xml, thank you! Looks like the modified strings appear only in the game with the extracted resources, not with the original archives. However, there could be some missing textures among the extracted files because in the "extracted" game, the textures of certain characters (Geron's and the fairy guard's in my case) has become completely black.

The game supports all the umlauts needed, however, so I don't have to bother myself about the fonts.
## Post #20
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2013-10-06T22:26:31+00:00
- Post Title: Re: Dark Eye: Chains of Satinav

Sounds better already. 

Are you using savegames from an earlier playthrough? These might not work with the unpacked version of the game. Maybe that's why the characters are missing their textures ...
## Post #21
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-07T09:06:50+00:00
- Post Title: Re: Dark Eye: Chains of Satinav

Yes, I've played past half of the game (I started with Memoria, but I soon realized that I couldn't understand the whole plot without the first game), and the story somehow seized me. Since it is (was) not yet possible to do a localization for it in my language I thought I try my luck here. Thanks to you, I am lucky 

Looks like the only obstacle remaining is that the .mkv videos use internal subtitle files, so the only way to localize them is to replace one of the subtitles (preferably English) with a translated one, but I'm looking for a solution how to make the videos use external subtitles ingame. No luck so far. I just hope it is possible to do a localization without including modified videos which would increase the size to at least 1 GB.
## Post #22
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2013-10-07T20:25:08+00:00
- Post Title: Re: Dark Eye: Chains of Satinav

You're right, knowing Chains of Satinav makes Memoria more enjoyable. Definitely stay along for the ride -- I'm currently playing Memoria, and I find it to be a very enthralling game, quite a bit better than its predecessor. 

I'm not per se an expert on video formats, but shouldn't it be possible to demux the video/audio and subtitle streams from the .mkv files and remux your own subtitles on the fly? That way, you'd only have to distribute your translated subtitles, which is probably also better from a legal point of view (since you wouldn't need to distribute any copyrighted video/audio streams).
## Post #23
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-10T01:56:45+00:00
- Post Title: Re: Dark Eye: Chains of Satinav

I'm not even close to something like an expert in this, but if it's possible to display .srt subtitles for .bik ingame videos with a modified .dll and an accompanying .ini, maybe something similar can do the trick for .mkv-s, too. I'll ask around.

Anyway, I've finished the first game, and I must say there were even in The Longest Journey more "logical" solutions than here. Some of them were so unlikely it felt I should think more like an imaginative child than an adult.
