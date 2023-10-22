## Post #1
- Username: SCGame
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 13, 2009 8:41 am
- Post datetime: 2009-07-16T01:40:15+00:00
- Post Title: X-Blades .ddsx .grp .bin file, need help to extract

I tried to extract some file from the game X-Blades.

I found three kinds of file that have file extension  .ddsx .grp and .bin, such as menu.ddsx, fonts.720.bin, and weapons.grp.

Any body can help me to extract those file? 

I have uploaded some of those file, you guys can try if you can extract it and tell me how.

thanks every body~!  

[http://www.yourfilelink.com/get.php?fid=501613](http://www.yourfilelink.com/get.php?fid=501613)
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-07-16T06:38:36+00:00
- Post Title: X-Blades .ddsx .grp .bin file, need help to extract

fonts.720.bin: contain some data, and an uncompressed DDS font image
menu.ddsx: maybe a DDS image, but definitely compressed with zlib
weapons.grp: some data (maybe header with the inner filenames), and compressed data with zlib, maybe DDS

Sorry, but right now I can't uncompress the zlib datas to see what inside them.
## Post #3
- Username: SCGame
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 13, 2009 8:41 am
- Post datetime: 2009-07-16T07:38:37+00:00
- Post Title: X-Blades .ddsx .grp .bin file, need help to extract

> Reply from evin
>
> fonts.720.bin: contain some data, and an uncompressed DDS font image
menu.ddsx: maybe a DDS image, but definitely compressed with zlib
weapons.grp: some data (maybe header with the inner filenames), and compressed data with zlib, maybe DDS

Sorry, but right now I can't uncompress the zlib datas to see what inside them.
Thanks for telling me those information.
Right now I am finding a way to uncompress those file to see if I can find some text files.
I would like to translate this game.
Thanks for help
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-16T09:58:26+00:00
- Post Title: X-Blades .ddsx .grp .bin file, need help to extract

offzip extracts the data but there is a very weird format here it uses weird compressed headers before the data. I converted one of the images.
they seem to be dxt 5 images with no mip maps.
## Post #5
- Username: SCGame
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 13, 2009 8:41 am
- Post datetime: 2009-07-25T01:26:15+00:00
- Post Title: X-Blades .ddsx .grp .bin file, need help to extract

So, how do you extract the files, chrrox? Can you tell me? Please.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-25T01:43:35+00:00
- Post Title: X-Blades .ddsx .grp .bin file, need help to extract

download the program offzip from [http://aluigi.org/mytoolz.htm](http://aluigi.org/mytoolz.htm)
then just do offzip.exe -a myfiletotextract outputdirectory 0x0
this will extract the archive without names
then I looked at the dds files in a hex editor and just pasted a valid dds header over it which was dxt5 and no mip maps.
## Post #7
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-09-07T21:43:54+00:00
- Post Title: X-Blades .ddsx .grp .bin file, need help to extract

Thanks, guys, for starting and working with this game... I just recently got a hold of it, for PC, and I also want to extract models and textures. I would like to put the ayumi model into 3ds max, with textures. Would someone be willing to create a tool for this? I can give you the files that I think contain the model(s) I need. Thanks. Or, could someone show me how to do it myself... I have no knowledge of hex editor (and frankly, I suck at offzip, I can't make it work for me, I just can't figure out command prompt)?

Here are the two files I think contain the model of ayumi with her textures...

EDIT: Xentax is being a pain, and crashing when I try to upload the files. I can't upload them, even when I zipped them. SCgame, could you share those files? They are ayumi.grp and ayumimodel.grp found in the "res" folder.
## Post #8
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2011-09-09T21:39:39+00:00
- Post Title: X-Blades .ddsx .grp .bin file, need help to extract

game text is in the file ob.vromfs.bin  (compression zlib)
