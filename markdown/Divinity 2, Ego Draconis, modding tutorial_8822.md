## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-04-23T23:26:19+00:00
- Post Title: Divinity 2, Ego Draconis, modding tutorial

This short tutorial is intended to give a startup for modding Divinity 2, Ego Draconis. 
I'll try to explain as simple as possible but it's not aimed at modding beginners.

I will not upload any copyrighted assets (models and so on) and you are severely asked not to do so, too. 
Only use this tut for your own private requirements.

And never, never waste Larians time sending them "bug reports" due to problems
which might arise from the use of the knowledge provided here.

Prelude
I started a first modding approach 9 month ago after having bought a 10€ budget version of Ego Draconis. I got the internal console working and made some investigations on item and inventory prototypes ("XMLs") and coded some obj-exporter (unfinished).

FAQ: isn't this all too late? -> Yes, maybe. But this game has some interesting aspects that make it worth to have a look on (I'm not speaking of these annoying "arcade" wyverns;-) 

Although I'm not a texture modder I will start  with this. And do not blame me for not covering TexMod.

Preparations, tools

Handling of packed dv2 files:
the tools u need: dv2_u.exe, unpacker, Author: IvanAls
old version? [viewtopic.php?p=30834](http://forum.xentax.com/viewtopic.php?p=30834)

Latest version should be 0.02 from 7/31/2009:
packer and unpacker
[viewtopic.php?f=10&t=5363&p=45146&hilit ... ity#p45146](http://forum.xentax.com/viewtopic.php?f=10&t=5363&p=45146&hilit=tool+from+divinity#p45146)

hint. for DKS you'll need the BMS script from bacter (some posts up):
[viewtopic.php?f=10&t=5363&p=45170&hilit ... y+2#p45170](http://forum.xentax.com/viewtopic.php?f=10&t=5363&p=45170&hilit=divinity+2#p45170)

(Because I don't owe DKS I won't cover this.All explanations refer to DIV2, Ego Draconis, version 1.3.15.112)

Handling of texture files (dds embedded in nif): python and PyFFI.
As a modder you should be familiar with these.
I use python 2.6 and PyFFI-py3k-2.2.0.
The important script is niftoaster.py (11/26/2011), the "spells" dump_pixeldata and dump.

Details will follow. Use of NifScope is not required for the dds but we will need a hex editor
(HexEdit from Andrew W. Phillips or Mirkes TinyHexer or your preferred tool).

Handling of model data: NifScope 1.0.22 (in my experience actual versions such as 1.1.0-RC5 do not work)


Preparations, Changing textures
(And 'yes': not all is "step by step"; the modifing of the texture is explained at the very end of this post.)

Beginners (if any) might skip the following re-organisation of dv2 -files but it will save you a lot of time.
Why "re orga"? Because we don't want to pack 1 Gig of data for the chance of a handfull of textures.

Like to skip reorganisation then continue at "testing only" please.

Reorganisation
In DIV2 version 1.3.15.112 three files are concerned: Patch.dv2, Textures2.dv2, Textures.dv2

They contain 1606, 1424 and 8858 texture files (nif with dds contained).

For example NPC_Sassan_Upper_DM.nif is contained in all three files. (DM=Diffuse map)
(In textures.dv2 it's the lowRes version (171 kB) in the  others hiRes (684 kB).)

Patch.dv2 has highest priority, means its NPC_Sassan_Upper_DM.nif is used by the engine.

Changing this nif would require to repack a 1.5GB file. Takes 3 min on a 3 GHz dual core
but we'd prefer packing our 3 or 4 modified nifs only, don't we?

So here we go: unpack all three dv2 files:in 3 directories "test1", "test2", "test3"
 dv2_u Patch.dv2,  dv2_u Texture2.dv2,  dv2_u Texture.dv2

subdirs win32\Textures containing unpacked files are generated.

Now we cut and paste all Textures2-nifs from test2\win32\textures to test3\win32\textures
'yes' to "override all?"
(mark win32 in test2, ctrl-x, then mark test3, ctrl-v)

Then cut and paste  all Patch-nifs from test1\win32\textures to test3\win32\textures
'yes' to "override all?"

Before continuing Be aware NOT to erase the original dv2-files:
rename Patch.dv2 to Patch.dxv2, textures2.dv2 to textures2.dxv2
and  textures.dv2 to textures.dxv2

If the test-dirs are located in root then execute there (at C:\> or D:\> or...)
div2_pak -a test1\  Patch.dv2
div2_pak -a test3\  Textures.dv2

(-a means alignment, should work without it but that's not recommended)

copy your modified nifs to test2\win32\textures, then execute
div2_pak -a test2\  Textures2.dv2

The advantage is that we don't need to touch Patch.dv2 and textures.dv2 any more.

All our modified textures (nifs) can be packed in some seconds into textures2.dv2.
(They have higher priority than the ones in Textures.dv2 and are used by the engine,
because Patch.dv2 doesn't contain nifs of the same name any more.)

Reorganisation, end
continue with modifing; skip testing only part.


testing only:  unpack Texture2.dv2 for example to get some texture files (nifs with dds contained):  dv2_u Texture2.dv2
rename Patch.dv2 to Patch.dxv2 and textures2.dv2 to textures2.dxv2

testing only,end


modifing nifs

Taking NPC_Sassan_Upper_DM.nif from unpacked texture2.dv2 (testing only)
or from test3-dir (reorganisation).

copy it to your python dir. There should exist a subdir scripts. There the niftoaster.py
file should exist.

Then invoke  a cmd window (start menue, execute, cmd).

(Maybe on win7 admin rights are required.
You could created a link to C:\WINDOWS\system32\cmd.exe, right click the icon,
run as, choosing account with admin rights. It's the path in XP, same for Win7?)

In this window type 
python.exe scripts\niftoaster.py dump_pixeldata NPC_Sassan_Upper_DM.nif  

if no dds is created you can get an error log by appending this to the upper line:
 > log.txt:

log.txt might contain:

pyffi.toaster:INFO:toasting with 2 threads in chunks of 64 files
pyffi.toaster:4972:INFO:=== BV3_Rocks_B_NM.nif ===
pyffi.toaster:4972:INFO:  --- dump_pixeldata ---
pyffi.toaster:4972:INFO:    ~~~ NiPersistentSrcTextureRendererData [] ~~~
pyffi.toaster:4972:INFO:      found pixel data (format 6)
pyffi.toaster:4972:INFO:      saving as bv3_rocks_b_nm.dds
pyffi.toaster:4972:ERROR:TEST FAILED ON BV3_Rocks_B_NM.nif

So, yes, sry, pixel data format 6 (DXT 5) seems not to be supported by PyFFI so far.

But in our example npc_sassan_upper_dm.dds should be created.

We can modify it using a suitable tool as gimp or paint net for example.
(You might have to install a ddsplugin.).

Save your modification as dds, compression BC1/DXT1,
generate mipmaps to be selected.

The file size must be maintained else you did something wrong.

Now copying the dds into the nif is the harder part. Just realized I used the lowREs nif
but should work with the hiRes, too.

We have to copy the dds without its header into the nif. The dds header size is 128 bytes,
means starting address is at 0x80. Have a look at the last 6 bytes and keep them in mind.

The starting point in the nif?

ok, with me it was 0x13D. If you copy the dds without header block at this address you should have a look at the end of the nif and identify the 6 bytes we talked about. There has to follow a 01 and a 7 zeroes sequence else you have to adjust the starting point.

After having copied the nif to test2\win32\textures and performing dv2_pak we copy
Textures2.dv2 to [Drive]:\Divinity II - Ego Draconis\Data\Win32\Packed
We can start the game and hopefully see something like this:

[http://www7.pic-upload.de/24.04.12/iv8n3dh3g4p.jpg](http://www7.pic-upload.de/24.04.12/iv8n3dh3g4p.jpg)

(to be continued)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-04-23T23:29:47+00:00
- Post Title: Divinity 2, Ego Draconis, modding tutorial

models

For extracting the models you can use Nifscope 1.0.22 or blender with Niftools.
I started using NifScope on buildings and exported them as (wavefront) obj.

Since nif is a very complex format there were some minor problems
so blender refused to load the obj.
(import_obj.py by Campbell Barton, Jiri Hnidek, Paolo Ciccone)

As you may know obj files contain v,vt,vn and f (vertices, tex coords, normals, faces)
The faces come like this v/vt/vn for example f 1/1/1 2/2/2 3/3/3, means the vertices
1, 2 and 3 build the corners of the first triangle (face).

Some obj groups exported by NifScope 1.0.22 don't contain texture coordinates. 
Not that bad but the faces look like this 1//1 2//2 3//3. 
The import_obj.py doesn't like this so you have to exchange the // by / using a fast text editor.

The importer also can't deal with exponents (e-07) in floating point values.
Means all values like 3.123456 e-07 have to be replaced by 0.0

(The UV map seems to miss some faces compared to the one created by NifTools.)

remarkon buildings:
There are often several texture coord blocks (channels?) and the first one nether fits.
But with obj you have we advantage of being able do delete them manually
until you hit the right one.


NifTools

As you may know with blender 2.5 there was  a change from Python 2.x to 3.0.
(This required a rewrite of many py scripts due to some function changes. 
So you can't use python 2.x scipts with blender >= 2.5)

I didn't investigate on NifTools for blender > 2.49b so you will have to do this for yourself 
or install blender 2.49b.

I use NifTools version called Blender NIF Scripts v2.5.8.
First confusion on version numbering. But be assured: this NIF Scripts are for blender 2.49b.

requirements:
    Blender 2.49b.
    Python 2.6 or higher (but not Python 3.0 or higher).
    PyFFI 2.1.9 or higher (but not PyFFI 2.2.0 or higher).

2nd confusion: as mentioned earlier I'm using PyFFi 2.2.0.
Maybe some of my minor problems arise from that?
(Don't know. Will only investigate on this if problems are getting harder;-)
So actually I use python 2.6.6 and import_nif.py dated 10/30/2011.)

Importing of nifs does take some minutes (especially on buildings).

Damian and Sassan could be imported without problems and with fitting UV maps.
Texturing was no problem as can be seen at the pics.

ATM I'm trying to get the 28 textures for the watermill and will come back after having it fully
(or more or less) textured.



Sassan_Tex.JPG (36.12 KiB) Viewed 171 times


[](http://www.pic-upload.de/view-13905433/Damian.jpg.html)

[](http://www.pic-upload.de/view-13905431/Watermill.jpg.html)

edit: now the watermill is textured inside; but I have no clue how to texture the outside walls.
//Watermiill_inner_tex2.jpg.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-04-23T23:30:17+00:00
- Post Title: Divinity 2, Ego Draconis, modding tutorial

new results to come: it is possible to insert objects into the game.

First approach was to move a bed, a table. The collision shapes did rest on their old position.
I was too lazy to investigate on this and focussed on chests:

[](http://www.pic-upload.de/view-14220871/DZ1_HighHalls_B_moved_chest.jpg.html)

The next step was to insert new (i.e. cloned) ones:

[](http://www.pic-upload.de/view-14220890/new_chests_for_Aleroth.jpg.html)

The disadvantage is that you'll have to start a new game because interactive objects are stored in the savegames as soon as you entered the region where they reside.

Next I would try to insert some weaponry but who really wants to start a new game for getting a cloned sword? 

So I think the more interesting part will be using lua script. I don't know whether spawning of items will be possible. At least I managed to teleport Raze into the barracks where I could get rid of him easily.

Done by a simply change of Raze_Raze.lua:

```
				if (MeleePossible) then
>>>					Script.TeleportToTrigger("BV_Barracks_SitPoint") --xx
				else
					Script.Flee(SightRange * 0.5, 3)
				end
			end
```


(Naturally all changed files have to be repacked.)

edit: the NPCs and their lua scripts are "connected" via an entry in a CharacterFile.xml, for example
MainDataStub\Episodes\Episode_1\Characters\BV_Main_Village_Area_characterfile.xml:

0x63b: Default_Female BV_Female_Gossip_NPC_00 BrokenValley_2 Main BV_female2.lua 
           BrokenValley_Female_Villager_Gossip <>Peggy F_Citizen_A 0 1 F_Citizen_B2 <>
70 0 1 1 1 0 0 1 0 1 0 1 0 0 152.319 462.65 -13.463

So we might change in BV_female1.lua Script.PlayAnimation("CF_Fidget_High_01") for example
to Script.PlayAnimation("Die_Fire_01").

Changing the NPCs coordinates appeared to be a little hurdle (as you might remember changing coords in xmls not always applies for several reasons).

I couldn't find Peggy's coords in any other file (to be honest: did not unpack all the 001_XMLs.dv2) so I had to change them directly in RAM (brute force;-).

This is the result: 
[](http://www.pic-upload.de/view-14309538/DerkAndTheGossipGirls.jpg.html)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-04-23T23:31:03+00:00
- Post Title: Divinity 2, Ego Draconis, modding tutorial

place holder 2
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-05-11T22:04:39+00:00
- Post Title: Divinity 2, Ego Draconis, modding tutorial

Nice going.
