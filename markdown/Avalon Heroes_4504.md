## Post #1
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2010-05-24T09:48:05+00:00
- Post Title: Avalon Heroes

This is a free to play game, game client website: [http://avalonheroes.en.alaplaya.net/](http://avalonheroes.en.alaplaya.net/)
I really like the models. So, I want to extract the files off this game, unfortunately, I am no good in coding/programming.
The farthest I got was to just open the files using a hex editor. They seem to be archives holding the actual files inside.

.ani - animation archive, contains .ani files.
.mdl - I think this contains the links between the files (what animations, mesh, skeleton are used together).
.msh - mesh archive, contains .msh files.
.skl - skeleton archive, contains .skl files.
.pkg - not sure about this one.
.snd - sound file archive containing more .snd files inside.

Sample File Link: [http://www.mediafire.com/?mzammzmiczy](http://www.mediafire.com/?mzammzmiczy)

Help would be really appreciated.
## Post #2
- Username: Zazz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 25, 2010 2:39 pm
- Post datetime: 2010-05-26T16:58:35+00:00
- Post Title: Avalon Heroes

If you look at the _NPC.* files in a Hex editor, you can figure out the embedded header that the file uses:

[IDSTRING "KCAP"] [NUMFILES long]

then for each file:

[NAMESIZE long] [NAME string] [SIZE long] [file]

```

Get NUMFILES long

For I = 0 < NUMFILES
	Get NAMESIZE long
	GetDString NAME NAMESIZE
	Get SIZE long
	SavePos OFFSET
	Log NAME OFFSET SIZE
	Math OFFSET += SIZE
	GoTo OFFSET
Next I
```

Execute this BMS script using quickbms on your _NPC.* file of choice. I managed to play the dumped .SND files, so the model and other files should be usable. I haven't looked into the *.pkg files.
## Post #3
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2010-05-26T19:57:46+00:00
- Post Title: Avalon Heroes

Thank you very much for answering.  
I'm really excited to get this working.

Unfortunately, I'm having a problem at the moment, quickbms.exe gives me an error.

> error in src\quickbms.c line 7710: myalloc()
>
> Error: Not enough space
I just downloaded it today (QuickBMS generic files extractor 0.4.4).
Is this the same version that you're using?
Oh, and if it helps, I'm using a Vista 32-bit OS.
## Post #4
- Username: Zazz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 25, 2010 2:39 pm
- Post datetime: 2010-05-26T19:59:48+00:00
- Post Title: Avalon Heroes

Which file were you trying to extract? I ran into a similar error due to a bug which I subsequently fixed. Does that happen for every file? Also test it on the same sample files you provided me.

I'm using the latest quickBMS version, I downloaded it yesterday.
## Post #5
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2010-05-26T20:12:55+00:00
- Post Title: Avalon Heroes

FIXED (Ignore): I tried it first on the sound file, since you said you were able to play them after dumping, unfortunately, everything gives off that error. So I can't extract anything yet. I wonder what is causing the problem.

EDIT: Got it working, I'm really sorry for troubling you, I checked the codes, and I accidentally left out the first line.

```
IDString "KCAP"
```

I feel so stupid for leaving it out. Thank you man, I'm gonna try it out on the other files.

By the way, what player did you use to play the sound files?
## Post #6
- Username: Zazz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 25, 2010 2:39 pm
- Post datetime: 2010-05-26T20:32:49+00:00
- Post Title: Avalon Heroes

Heh, no problem 

I managed to open them up in an older program named Cool Edit Pro 2.0 (which adobe bought a while ago and turned it into Audition).
## Post #7
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2010-05-26T23:10:14+00:00
- Post Title: Avalon Heroes

Anyway, using Zazz' script, here is a sample of the individual files contained on it.  
I cannot open the model files (mesh, skeleton, textures).
I'm not sure if I should post this here or if I must make another thread somewhere else like on 3D/2D models or Graphic file formats for this.

Here is the sample file link: [http://www.mediafire.com/?lmmwnzwmtyn](http://www.mediafire.com/?lmmwnzwmtyn)

Maybe someone could look up on it to see how it could be opened.
I would really like to open it using 3DS Max 8 or Blender.
I'm actually planning on replacing another game's model with these for personal use but I would like to keep the animations intact.
Opening it with a Hex Editor, like the .skl file, it contains the default biped names which is really convenient. (Bip01 Pelvis, Bip01 Spine, etc.)
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-08-31T18:09:16+00:00
- Post Title: Avalon Heroes

windfury,

I added the compressed (like _npc.msh) and the uncompressed .msh and the uncompressed .tex loader module to the 3D Object Converter and I released the v4.422 now.

You can install or use the portable v4.40.
[http://web.t-online.hu/karpo](http://web.t-online.hu/karpo)

After that you can update your installed (or portable) application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates…) to get the latest version of the 3D O. C.
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-11-08T19:44:09+00:00
- Post Title: Avalon Heroes

In the last days I developed the new FREE internal export module called 'Tools/Export the material table's textures to .bmp files'. that supports the Avalon Heroes .tex format.

See the Supported texture file formats: 
[http://web.t-online.hu/karpo/features.html](http://web.t-online.hu/karpo/features.html)

I released the 3D O. C. V4.429 update package now.
You can update your installed application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates…).
