## Post #1
- Username: asper
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 11, 2015 3:11 am
- Post datetime: 2016-03-13T16:38:15+00:00
- Post Title: Help extracting Mario Party 10 (WiiU) 3D models

I found out the files inside the game structure containing the 3D models, here it is Mario model file: [https://www.sendspace.com/file/01koo2](https://www.sendspace.com/file/01koo2)
The file is a container with .bin extension but PAC header, you can clearly see the contained file names at offset 0x00018C80; can someone help me with a script to extract the content ?

Thank you very much !
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-03-14T21:45:28+00:00
- Post Title: Help extracting Mario Party 10 (WiiU) 3D models

I already made an unpacker/importer a while back, but here it is since I haven't posted it here before:



Use [this QuickBMS script](https://dl.dropboxusercontent.com/u/27874399/MP10-Unpacker.bms) to unpack the *.BIN files, and then use [this MaxScript](http://www.mediafire.com/?yl852ebg2iri718) to import the *.BNFM files afterwards. The models will import with their original bone structures and rigging, but you'll have to apply the textures manually for now (but that's not a problem since most models in MP10 only have one or two each). The textures are using the Wii U's common *.GTX format, there are a bunch of guides out there to convert those to DDS.

I haven't tested this with many stage models, but it should work for all (or at least most of) the character models.
## Post #3
- Username: asper
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 11, 2015 3:11 am
- Post datetime: 2016-03-15T12:45:55+00:00
- Post Title: Help extracting Mario Party 10 (WiiU) 3D models

> Reply from RandomTBush
>
> I already made an unpacker/importer a while back, but here it is since I haven't posted it here before:
....
I haven't tested this with many stage models, but it should work for all (or at least most of) the character models.

Superb work my friend ! Thank you !! So they are not more than a zip file ?
## Post #4
- Username: kavid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 13, 2017 1:25 pm
- Post datetime: 2017-06-13T09:52:10+00:00
- Post Title: Help extracting Mario Party 10 (WiiU) 3D models

pls, menuxx.bin can be extrated to .arc files.

but when i reimport 30+ files into .bin files, i get a freezon.

i found it viewtopic.php?f=16&t=14084 

With Quickbms Reimport function, can not make the game 100% work properly

Is there a way to package Mario Party 10 / Wii Party U's .bin file?

I searched for a long time and did not find a tool

I am trying to translate the two games into Chinese, the current text is completed



Sent a modified picture with the font re-packet


Who can help create a script for import？
[https://mega.nz/#!c44k1AoL!kQfcN7QK7pBU ... Q2aalKy-Yg](https://mega.nz/#!c44k1AoL!kQfcN7QK7pBUKkKt_W_SuvCzD3P4_nQzDQ2aalKy-Yg)
this wii party u ororgin file。

Thank
## Post #5
- Username: fred561
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 06, 2017 8:36 am
- Post datetime: 2017-07-06T00:41:16+00:00
- Post Title: Help extracting Mario Party 10 (WiiU) 3D models

> Reply from kavid
>
> pls, menuxx.bin can be extrated to .arc files.

but when i reimport 30+ files into .bin files, i get a freezon.

i found it viewtopic.php?f=16&t=14084 

With Quickbms Reimport function, can not make the game 100% work properly. It was mentioned above that it is not of use so I wanted to ask here. That was the reason that they mentioned you be careful about slip and fall accidents, otherwise, it could cause an accident and you might end up falling. If someone were to come here and here and it says they might be able to find some information regarding the topic. 

Is there a way to package Mario Party 10 / Wii Party U's .bin file? I believe I  was reading something about this somewhere but now I have lost the page and cannot find it, I did not bookmark it so I don't know what it was. 

I searched for a long time and did not find a tool

I am trying to translate the two games into Chinese, the current text is completed

Hello,
How do I import the .bin file?


Sent a modified picture with the font re-packet


Who can help create a script for import？
https://mega.nz/#!c44k1AoL!kQfcN7QK7pBU ... Q2aalKy-Yg
this wii party u ororgin file。

Thank
