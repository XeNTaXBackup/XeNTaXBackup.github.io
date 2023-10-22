## Post #1
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-09-07T18:39:40+00:00
- Post Title: Tachyon model PAK format circa 1999

Trying to get a legitimate method of extracting models from Tachyon's
combination model + texture format PAK. I've been trying to get a Freespace 2 mod
off the ground for 6 years, and I'm finally back to looking for a way to use the original
objects.  I'd be more than happy to make a Xentax donation if we can get good exports.


Basic Info:

Game: Tachyon the Fringe
Info Link: [http://www.gamespot.com/pc/sim/tachyont ... index.html](http://www.gamespot.com/pc/sim/tachyonthefringe/index.html)   or   [http://pc.ign.com/objects/011/011519.html](http://pc.ign.com/objects/011/011519.html)
Produced: 1999 - Novalogic
Similar - F22 Lightning/Raptor, Delta Force games of the same period.
Ancient Buggy Demo - [http://files.fringespace.org/jgz/Xentax/TTFDEMO.zip](http://files.fringespace.org/jgz/Xentax/TTFDEMO.zip)  (game files are in an archive format I can open if you need it)

Archive Info:
PAK was used for a lot of Novalogic games, but each one needed it's own extractor, ie. Delta
Force PAKs don't appear to be the same as Tachyon PAKs and vice versa, as the extractors never produce
anything.  It's a format that contains an unknown model format, including LODs, and PCX type textures always
in a power of 2. The models were produced with 3DS Max 3, but that's all I know.

There was a fan made model exporter, but the creator went MIA before it was bug fixed. As a result, some
models are partially missing LODs, vertex indexs won't import, nearly all have geometry problems of some sort, the 
textures are "most" of the time usable, the UV maps are always destroyed, it's simply not a practical solution. Everything 
it spits out, we have to fix in some fashion - and I don't mean because they are old models. Fortunately I have the 
author's development blog saved, which lists what he found in the files and where in hex.

Sample PAKs:  
[http://files.fringespace.org/jgz/Xentax/Models/PAKs.zip](http://files.fringespace.org/jgz/Xentax/Models/PAKs.zip)    1.9 MB

Fan Made Extractor:
[http://files.fringespace.org/jgz/Xentax ... ractor.zip](http://files.fringespace.org/jgz/Xentax/Models/pak_extractor.zip)  22 KB

Development Log (read from bottom up):
[http://files.fringespace.org/jgz/Xentax ... ournal.zip](http://files.fringespace.org/jgz/Xentax/Models/DevJournal.zip)   38 KB

5 Sample Extractions:
[http://files.fringespace.org/jgz/Xentax ... xports.zip](http://files.fringespace.org/jgz/Xentax/Models/PAKexports.zip)   1.9 MB

Typically, anything that comes out of the exporter has to be run through Deep Exploration, as it seems to be one of the only programs
that will work with the messy .OBJ content. We usually batch save this to .3DS and work on it from there. I included both the OBJ and 3DS files
in the sample extractions above. If you use the exporter in debug mode, you can also see a lot of offset and other specific information about
the resource file.

I have also tried every DirectX 3D ripper I could lay hands on, but it appears that being based on DX6, almost nothing will
work with Tachyon. 3D RipperDX is close, but every capture is missing around 60% of the model, if I get that much. The author
of that program isn't actively working on it to fix older DirectX compatibility either, so again I'm stuck. If you want an example
of a rip, here one is:

3D Ripper DX Rip: 
[http://files.fringespace.org/jgz/Xentax ... Frames.zip](http://files.fringespace.org/jgz/Xentax/Models/Frames.zip)   69 KB

Textures from the rip:
[http://files.fringespace.org/jgz/Xentax ... xtures.zip](http://files.fringespace.org/jgz/Xentax/Models/Textures.zip)   1.2 MB

Note that there's 12 MB of textures in the zip, 98% is likely unrelated to the ship model, but trying to pick out 25 textures out of 400
wouldn't be very efficient. So these are offered only if you want to see that yes, the textures are applied correctly in the rip (3dr only).

Recommended rip import settings (Max/ 3dr) -
FOV 42.7
Monitor Aspect Ration 16:10
Check - Merge into single mesh.
Check - Remove faces drawn first.
Check everything except "remove degenerate faces" "ignore if rendered  to rendertarget" "ignore if rendered to backbuffer"


So what am I hoping for here?

I'm hoping that someone here has seen something similar before, and can write a extraction/conversion script without a lot of hassle.
Honestly I'm not sure what can be done with what we've got, so I'm looking for solutions to a 6 year old problem at this point.

I've got all the mod tools and information from every Tachyon modder before me, and have edited just about every "other"
file in the game at one point or another, so if there's some help or info I can provide I'll be happy to assist.

Thanks.

(Note I had this posted in the 3D/2D models section over a month ago, but I've removed that post in hope that
more people with the right knowledge would see it in this section, since it is a archive format of sorts).
## Post #2
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-09-08T17:58:04+00:00
- Post Title: Tachyon model PAK format circa 1999

Based on some new information, using Max 3 exports, we're guessing the original model format 
could be .ASE. Our other candidate is probably .3DS.  There's not much in the way of export 
options in Max 3, so we narrowed it down a little anyway.

There still could have been an intermediate converter in between the model export and it ending up as a PAK however.
