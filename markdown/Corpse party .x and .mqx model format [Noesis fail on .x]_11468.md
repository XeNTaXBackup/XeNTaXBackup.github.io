## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-04-29T16:16:30+00:00
- Post Title: Corpse party .x and .mqx model format [Noesis fail on .x]

Hey Guys

I was wondering if anyone would be able to help me in opening/exporting the .x and .mqx file formats from the game 'Corpse Party Dead Patient', I've placed the files in my dropbox [here](https://www.dropbox.com/sh/azf19y7homu8qnj/u-JOQibN1q).

I know that theres a .x plugin for noesis, however for these files it doesn't work, noesis says it can't open them and I have no idea what a .mqx file is, if I attempt to open the files in Direct X's official viewer I get this:


If I had to make a guess, I'd say perhaps they're compressed .x files, but I couldn't really say, pretty sure they must contain animation though, as the .x viewer from the Direct X SDK goes crazy, the model moves about in a weird jerky manner, but I can't tell if thats actual animation or it just not being sure how to read it.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-29T20:20:04+00:00
- Post Title: Corpse party .x and .mqx model format [Noesis fail on .x]

> Reply from lionheartuk
>
> If I had to make a guess, I'd say perhaps they're compressed .x files,yep.
read this thread: [viewtopic.php?f=16&t=11334](http://forum.xentax.com/viewtopic.php?f=16&t=11334)



model_x.JPG (41.05 KiB) Viewed 200 times



If you want the uncompressed binary .x file to be viewed in the DirectX viewer you could convert it into txt using MeshConvert /xt /a (MS DirectX SDK). (But my version of MeshConvert doesn't seem to care for frames.)

The.mqx is an xml file. Add .xml as an extension and open it in wordpad or notepad+.
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-04-30T20:23:56+00:00
- Post Title: Corpse party .x and .mqx model format [Noesis fail on .x]

> Reply from shakotay2
>
> lionheartuk wrote:If I had to make a guess, I'd say perhaps they're compressed .x files,yep.
read this thread: viewtopic.php?f=16&t=11334
model_x.JPG

If you want the uncompressed binary .x file to be viewed in the DirectX viewer you could convert it into txt using MeshConvert /xt /a (MS DirectX SDK). (But my version of MeshConvert doesn't seem to care for frames.)

The.mqx is an xml file. Add .xml as an extension and open it in wordpad or notepad+.

Ah great, thankyou.

I can decompress them fine now, Unfortunately the .x importer for 3ds max 2013, along with the .x plugin for noesis, neither will open the file still.
3ds max just crashes at 10% in for some reason.
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-05-08T15:46:02+00:00
- Post Title: Corpse party .x and .mqx model format [Noesis fail on .x]

> Reply from shakotay2
>
> lionheartuk wrote:
If you want the uncompressed binary .x file to be viewed in the DirectX viewer you could convert it into txt using MeshConvert /xt /a (MS DirectX SDK). (But my version of MeshConvert doesn't seem to care for frames.)

The.mqx is an xml file. Add .xml as an extension and open it in wordpad or notepad+.

I can't seem to get the the Mesh converted to work correctly

My command is the same as yours, ending in the .x file I intend to convert, but I get a constant  cannot load the file specified' in the cmd output.

I'm using the DirectX SDK 2009, not 2010 (as 2010 doesn't come with the viewer for some reason).

Is it possible to convert these files using the hex to obj tool of yours?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-08T19:20:43+00:00
- Post Title: Corpse party .x and .mqx model format [Noesis fail on .x]

> Reply from lionheartuk
>
> I can't seem to get the the Mesh converted to work correctly

My command is the same as yours, ending in the .x file I intend to convert, but I get a constant  cannot load the file specified' in the cmd output.Are your file access right sufficient? If so try the MeshConvert.exe I use:
[http://www.uploadmb.com/dw.php?id=1399575935](http://www.uploadmb.com/dw.php?id=1399575935) (a MS redistributable package might be required to run it on your system)

> Is it possible to convert these files using the hex to obj tool of yours?
Using this version:
[viewtopic.php?f=16&t=11404&p=93819&hilit=hex2obj#p93819](http://forum.xentax.com/viewtopic.php?f=16&t=11404&p=93819&hilit=hex2obj#p93819)
(with a face offset of 4)



model_x(binary).JPG (43.1 KiB) Viewed 148 times



mofo's XPorter for 3dsmax would be the better choice imho.

As you said it crashes I guess your using it on Win7?
Iirc there was an error message on XP, too, but finally the model loaded.
So maybe try starting 3dsmax in XP compatibility mode?
