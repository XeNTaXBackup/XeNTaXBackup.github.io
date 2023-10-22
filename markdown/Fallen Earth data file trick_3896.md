## Post #1
- Username: Thandalar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 26, 2009 4:32 am
- Post datetime: 2009-11-26T04:21:40+00:00
- Post Title: Fallen Earth data file trick

I have been wanting some updated maps for Fallen Earth for a couple months now. The ones I have found online appear to be from Beta and are not accurate. So, I started playing with the game directory trying to find the files. As many of you know .. nothing. There is a data.ifs file that is the only thing that updates each day, so it must be in there somewhere. That is where XenNTaX came in. This is the only forum I could find talking about the data file. I joined today; thanks for accepting me so soon. I read all the posts about FE and went through the tutorial for QuickBMS.

I must have opened a file Mythic doesn't want you to edit, because upon reload of the game I saw a message saying "checking the ifs game files" and I had to download all the files ... 40,159 of them. Well, I'm a fat redneck so that sounds like an invitation for dinner at Texas Roadhouse to me. Upon return, the download had frozen and stopped at around 8000 files. I reopened FE and it started "installing" the files I had downloaded. While that was happening I started trolling through the FEUpdater folder. I found a treasure trove of directories and files ... including one named maps that included a ton of .tga files. I started looking for the files I wanted and they started disappearing on me. Once it finished installing, it started downloading again. I checked the folders again and many of them were empty, but a few were getting new files. So, the installation process deleted the previously downloaded files after they had been compiled into the data.ifs file and started downloading the new ones. This makes sense, updates would need to be downloaded and installed and deleted too.

Ok, enough with the story and on with the trick .. after all that is it pretty easy to figure out. Delete your data.ifs folder and eveything in your FEUpdater\download file, reopen FE and watch it download all the files you have been looking for in the data.ifs file TA-DA.

** WARNING **
Don't do this if you want to play the game tonight/today. I have been updating now for two hours and I am at 16,500 files.

Notes:
*The files appear to download according to thier creation date .. all the way down the seconds.
*The installation\deletion takes place immediately after the download. You cannot wander off and wait for it to finish.
*I forsee one problem getting all the files: the download, installation and deletion happen so fast it will be difficult to capture the last files. I hope the installation order will be the same as the download process and maybe I will be able to copy the last files.


I know I don't know enough to get all the info I need, so this post is also me asking for help. The TGA files I already have won't load and there are tons of extensions I don't know how to deal with ... yet. I am happy to share info and help anyone else who is trying to get more info on this game. Once I finish with the download and have all the files, I will reply and tell you anything else I have discovered.

Thandalar
## Post #2
- Username: lanthas
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 15, 2009 7:43 pm
- Post datetime: 2009-11-26T19:47:02+00:00
- Post Title: Fallen Earth data file trick

> Reply from Thandalar
>
> *I forsee one problem getting all the files: the download, installation and deletion happen so fast it will be difficult to capture the last files. I hope the installation order will be the same as the download process and maybe I will be able to copy the last files.
Attach a debugger to the installer and patch a ret at the DeleteFile win32 function so that it is powerless to delete anything
## Post #3
- Username: Thandalar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 26, 2009 4:32 am
- Post datetime: 2009-11-26T20:09:53+00:00
- Post Title: Fallen Earth data file trick

Aftermath:
There were two downloads. After the downloading process got to around 36k files, it started installing ... but only for a second before I clicked "cancel". I closed FE made a copy of the download folder and  opened FE again. It installed and deleted then resumed downloading 3k files. I stopped the install process and made another copy of the download folder. From the original total of 40,159 files I have 40,133 between the two folders .. not bad.

If anyone wants info on any specific area (I'll include a top level directory list), let me know and I can upload files for your inspection. I know at least two of you were looking to play with these files. 

So, back to my desire to have accurate maps of the game. There is a maps directory, but almost all the files are in sets of around eight files. Each file in the set has different extensions and so each has a different function. I know there should be a file that is the map itself and then a  file that is the x,y coords of where NPC are. I would like to have both .. if possible. I uploaded the smallest set I could find. In the upload I also included a .tga file that is compressed or encrypted - I have no idea. DXTBmp will not open the .dds files or the .tga files I downloaded. I am hoping someone can tell me which tool or script will open these.


[GhostClinic.rar](http://www.sendspace.com/file/2hhggk)

FEUpdater\Downloads: (directories only)
11/26/2009	12:33	AM	<DIR>		actors
11/26/2009	1:02	AM	<DIR>		bolton
11/26/2009	1:02	AM	<DIR>		collections
11/26/2009	1:02	AM	<DIR>		eco
11/26/2009	1:02	AM	<DIR>		effects
11/26/2009	12:33	AM	<DIR>		envgrfx
11/26/2009	1:02	AM	<DIR>		fonts
11/26/2009	12:33	AM	<DIR>		gunsights
11/26/2009	1:03	AM	<DIR>		icons
11/26/2009	1:03	AM	<DIR>		images
11/26/2009	12:33	AM	<DIR>		int_data
11/26/2009	12:33	AM	<DIR>		maps
11/26/2009	1:02	AM	<DIR>		objects
11/26/2009	1:02	AM	<DIR>		portal
11/26/2009	1:03	AM	<DIR>		scripts
11/26/2009	1:02	AM	<DIR>		textures
11/26/2009	12:34	AM	<DIR>		tiles
11/26/2009	1:05	AM	<DIR>		trees
11/26/2009	1:02	AM	<DIR>		vehicles
11/26/2009	12:34	AM	<DIR>		watertest
## Post #4
- Username: Thandalar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 26, 2009 4:32 am
- Post datetime: 2009-11-26T20:12:20+00:00
- Post Title: Fallen Earth data file trick

> Reply from lanthas
>
> Attach a debugger to the installer and patch a ret at the DeleteFile win32 function so that it is powerless to delete anything

Well dang, that would have worked. Where were you last night at 3AM when I needed you? ;p
## Post #5
- Username: matshorics
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 18, 2010 11:16 am
- Post datetime: 2010-03-18T13:47:13+00:00
- Post Title: Fallen Earth data file trick

Sorry to bump an old thread, but just wondering if any luck has been made with extracting the maps?
## Post #6
- Username: JamesWhite
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 18, 2010 1:20 pm
- Post datetime: 2010-03-31T10:37:39+00:00
- Post Title: Fallen Earth data file trick

Hi everyone
 I am new to this community and happy to be part of it. I am a software engg working in a organization since 4yrs. I love to play online internet game.  Well do not mind but right now I don't have sufficient information but If in future I got than definitely I will share with you guys. I have news for the people those are interested in video game. There is site lunch for game called [Jocuri Sport](Jocuri%20Sport) in the web site [http://monstergames.ro/](http://monstergames.ro/). Just play once and take the new experience and enjoy the fun. 

Thanks
