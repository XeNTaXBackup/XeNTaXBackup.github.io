## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-13T03:45:34+00:00
- Post Title: Grandia 2

Is this game actually 3D? Or did they just make it look 3D with all those shadows and camera positioning and stuff...?
It stores it in afs archives which is recognizable by dragon unpacker (or maybe something else I don't remember) but there are no filenames, so...

I've seen a couple threads from several years ago that wanted to try to mod the game or at least get the models, but I don't think they got any further than just modifying string tables to change names and values and stuff.

EDIT:

ya, it should be this

[http://wiki.xentax.com/index.php/GRAF:AFS_AFS](http://wiki.xentax.com/index.php/GRAF:AFS_AFS)

Damn it no filenames.
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-13T04:04:59+00:00
- Post Title: Grandia 2

Noesis extracts the AFS files it uses and it uses NJCM models that Noesis supports. But the models are lightly compressed. I never got to looking into that, because I have (edit: well, had, at the time... sometime last year I got a decent emulator+debugger setup and became pretty well-versed in SH-4 assembly) no means of debugging Dreamcast games and, while it does seem to be a pretty straightforward form of LZ77, I hate guessing at compression algorithms. I didn't try googling though, maybe someone's got that figured out already.

Edit: Yep, someone already did it. This guy: [http://www.matzone.altervista.org/programmi/](http://www.matzone.altervista.org/programmi/)

This also reminds me that I want to look at the Love Hina DC games. I bet they use some form of proprietary compression as well, but it's just a hunch because that's just what Japanese devs of the era seemed to like doing. New game, new compression method!
## Post #3
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-13T06:33:15+00:00
- Post Title: Grandia 2

I went ahead and took that guy's decompression function and plugged it into Noesis, then added a bit of extra support for these files in particular (they have some custom chunk types I haven't seen before), so this will be in the next version I throw up.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-13T06:54:14+00:00
- Post Title: Grandia 2

Hmm I wonder if the PS2 format is similar.
I looked through the archives and see the NJCM strings, but it doesn't seem like it's compressed there.

Maybe they could afford to leave it uncompressed in PS2? lol
Here's one of the afs files.

I'm guessing it's just texture data at the top followed by the model (didn't look at plugin source)
[c01.7z](https://xentaxbackup.github.io/file/5182_c01.7z)
## Post #5
- Username: shakotay2
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-13T18:28:18+00:00
- Post Title: Grandia 2

In the file you sent there, the texture data is compressed (using the same L62C compression as the Dreamcast port), and it's still PVR. The model data isn't compressed though, if you snip off the header before the NJCM Noesis will load it as-is. The model and textures are identical to the Dreamcast versions.

This is the first PS2/PC game that I've ever seen using Ninja model and texture formats natively. I wonder if Sega provided a cross-platform lib for them to be able to do this. I never heard of any such thing, and in the KATANA SDK the Ninja model stuff was very much embedded, so that you basically fed your data to the API and it handled everything internally including the actual rendering.
## Post #6
- Username: Dazz
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 17, 2011 7:10 pm
- Post datetime: 2012-03-18T13:25:34+00:00
- Post Title: Grandia 2

I've been trying to load these models up, but I'm not getting any textures appear on Noesis. Any advice?

I'm using the PC version, but also have the Dreamcast version. I can load them up seperately, but they aren't loading up together..
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-18T16:29:22+00:00
- Post Title: Grandia 2

lol they have a PC version?
Upload some samples.

I only have PS2 version and it was slightly different already lol
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-18T18:35:22+00:00
- Post Title: Grandia 2

Assuming it's like the DC version, textures and models are in separate bundles. You have to extract the textures and name them njtex000/njtex001/etc. for Noesis to load them.
