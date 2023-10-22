## Post #1
- Username: Gistix
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Dec 20, 2010 5:45 am
- Post datetime: 2013-12-21T21:30:34+00:00
- Post Title: Sonic The Hedgehog - 2006 [Stages Meshes UV problem]

Hello xentax people, so, some years ago, this game 3D model format was cracked and then a converter was created by Volthron and Link, wich is .XNO, some while ago, a guy named ItsEasyActually (darkspines35/Brooks), created a 3DS Max importer plugin, but the plugin also suffer from the same desire of the old converter, If the mesh had 2 (or more I suppose) UV Sets/Channels, the importer would import the "wrong" Set/Channel (the one supposed for the shadow mapping), I spent my whole day till now trying to workaround on this thing, but no luck, so... I trougth I could ask here for help.

The problem is: The importer is importing the wrong UV Set/Channel.(If another one is present)

Here's how It look with Diffuse and the Shadow map


Some sample files 
[https://www.mediafire.com/?7l1lttng0fo6q2z](https://www.mediafire.com/?7l1lttng0fo6q2z)
(The .rar contains, Three models, one with this 2º UV Set, and the others without, and the .ms Importer)

> Max doesn't load the custom functions into memory for some reason. So just run it through the MaxScript Editor and it'll import the models just fine.

Ps. The Shadow Mapped/2º UV Channeled vertices contain a VertSize of 0x2C (line 392), models start at NXOB, .ms Importer created by ItsEasyActually

Thanks for your attention!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-22T01:20:19+00:00
- Post Title: Sonic The Hedgehog - 2006 [Stages Meshes UV problem]

> Reply from Gistix
>
> [...], I spent my whole day till now trying to workaround on this thing, but no luck, so... I trougth I could ask here for help.It would help if you wrote what you tried...

Also it's not clear for which vertex block sizes shadow map values are assumed to be contained.

Anyway from this pic [](http://www.pic-upload.de/view-21697172/tex_channels.jpg.html)

you can see why there's an fseek f 0x04#seek_cur for a vertex block size of 24 (it's for skipping the FF FF FF FF).

For a vertex block size of 44 I would suggest a) fseek f 0x0#seek_cur or b) fseek f 0x04#seek_cur, too (instead of 0x18). (yes, fseek f 0x0 doesn't make much sense, it's just for explanation)

After the lines
tu = ReadFloat f
tv = ReadFloat f*-1

fseek f 0x18#seek_cur (case a) or fseek f 0x14#seek_cur (case b) might be required.

edit: didn't test this - it's just a wild guess.
## Post #3
- Username: Gistix
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Dec 20, 2010 5:45 am
- Post datetime: 2013-12-22T02:47:35+00:00
- Post Title: Sonic The Hedgehog - 2006 [Stages Meshes UV problem]

Well, I got the 44 bytes one working by skipping these F9 F9 F9 FF.

And now its like

fseek f 0x10#seek_cur
tu = ReadFloat f
tv = ReadFloat f*-1
fseek f 0x08#seek_cur

Thanks, It really helped me out!
[http://puu.sh/5Utdj.jpg](http://puu.sh/5Utdj.jpg) (The image is too big, It'll look like spam If [img] was used.)

Edit: Is basicaly that, It is just skipping the first UV, If it loads the wrong UV, I just do It -8, this will lead the importer to the first UV set, Thank you so much shakotay2
