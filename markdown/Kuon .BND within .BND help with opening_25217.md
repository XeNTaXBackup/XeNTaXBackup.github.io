## Post #1
- Username: whombrell
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 02, 2022 9:57 pm
- Post datetime: 2022-04-02T14:08:32+00:00
- Post Title: Kuon .BND within .BND help with opening

I'm trying to extract models from Kuon and have got as far as extracting ALL.BND, which shows all files for the game. A lot of those are also BND files, but they seem to be different? I tried using the same BMS script on c001.bnd but after checking it in a hex editor on the resulting files (a c001.dss file that's bigger than the bnd, as well as 2 1kb files) it doesn't seem to have extracted correctly.

When opening c001.bnd in a hex editor I can see the names of files like c001.mdl (and starting at line 00003350 when opened in a hex editor there seems to be bone names, so the model is in there) but I'm not sure how to extract them.

c001.bnd: [https://drive.google.com/file/d/1mXwiVO ... mM8G3/view](https://drive.google.com/file/d/1mXwiVOjIfNgnwEGtYEr1DsJXowxmM8G3/view)

Here's the script I used

```
#by chrrox
#quickbms script
goto 0xC
get FILES long
savepos TMP
for i = 0 < FILES
goto TMP
get ID long
get OFFSET long
get SIZE long
get NOFF long
savepos TMP
goto NOFF
get NAME string
log NAME OFFSET SIZE
next i
```


Thanks for any help.
## Post #2
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-04T19:43:32+00:00
- Post Title: Kuon .BND within .BND help with opening

You have all you need, except extracted files are just holders for another type plus small header (what kind of data is it) used by game engine.
## Post #3
- Username: whombrell
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 02, 2022 9:57 pm
- Post datetime: 2022-04-05T20:15:54+00:00
- Post Title: Kuon .BND within .BND help with opening

> Reply from VendorX ↑Tue Apr 05, 2022 3:43 am at Tue Apr 05, 2022 3:43 am
>
> 
You have all you need, except extracted files are just holders for another type plus small header (what kind of data is it) used by game engine.
I can tell it's some kind of holder as I can see some text strings in a hex editor, but the BMS script I have is not correctly extracting this smaller file and I can't figure out what to change in order for it to do so.
## Post #4
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-06T10:07:39+00:00
- Post Title: Kuon .BND within .BND help with opening

Below "mess" (most probably) will work only if the data like *.dss and *.prm are the last ones.

```
goto 0xC
get FILES long

get ID long
get OFFSET long

do
  goto OFFSET

  get TOFFSET long

  if TOFFSET != 32
    break
  endif

  get Unk00 long
  get Unk01 long
  get NOFFSET long
  get DOFFSET long

  get DSIZE long
  get BSIZE long
  get Unk02 long
  getdstring FileType 16
  getdstring FileName 16

  savepos DOFFSET
  log FileName DOFFSET DSIZE
  xmath OFFSET "DOFFSET + DSIZE"

while TOFFSET == 32

```


Anyway, you can learn the structure of the *.mdl, *.tex and *.anm files - didn't care about the last two (i suppose it's NI). To optmise reading you can put all the offsets from the header to an array and depends on data type choose the way this data need to be exported ( .mdl holds two .vmd - .tex tree .t32 - .anm one .an - dnno the rest ...). I give up  when  saw how an array is implemted.

BTW: Dunno how you ppl can work with this messed up scripting - no info about syntax or even debugging possibility. Not to mention 'while' loop ...
Writting cpp app took me 5 min, translating to bms 50 min ... GEEZ!
## Post #5
- Username: whombrell
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 02, 2022 9:57 pm
- Post datetime: 2022-04-06T12:38:23+00:00
- Post Title: Kuon .BND within .BND help with opening

Thanks so much for that. I really have no idea what I'm doing so it's a big help. I still have to figure out how to convert the model and textures though.

> Reply from VendorX ↑Wed Apr 06, 2022 6:07 pm at Wed Apr 06, 2022 6:07 pm
>
> 
 .mdl holds two .vmd

I only got one vmd out of it, so I hope it is actually working correctly.
## Post #6
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-06T13:58:39+00:00
- Post Title: Kuon .BND within .BND help with opening

Oops! It suppose to be '*.vmd' and '*.vms'. Check if this is the case for different files.
I found some info about animation format, but I don't remember the link.
## Post #7
- Username: whombrell
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 02, 2022 9:57 pm
- Post datetime: 2022-04-06T14:00:02+00:00
- Post Title: Kuon .BND within .BND help with opening

> Reply from VendorX ↑Wed Apr 06, 2022 9:58 pm at Wed Apr 06, 2022 9:58 pm
>
> 
Oops! It suppose to be '*.vmd' and '*.vms'. Check if this is the case for different files.
I found some info about animation format, but I don't remember the link.
I have the .vmd and .vms so it is working. I think the vms file is the shadow for the regular model, as the name ends in kage which is apparently shadow in Japanese.
## Post #8
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-06T14:39:42+00:00
- Post Title: Kuon .BND within .BND help with opening

Info from headers:

MDL:
#MODEL (*.vmd)
#SHADOW_MODEL (*.vms)

TEX:
#TEXTURE (3 x *.t32)
Note: probably MipMaps

ANM
#MI2EDIT (*.ani)

DSS and PRM:
Binary data

First tree types has the same headers so script will fail if order is different than abow - need optimisation
## Post #9
- Username: whombrell
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 02, 2022 9:57 pm
- Post datetime: 2022-04-06T15:12:34+00:00
- Post Title: Kuon .BND within .BND help with opening

I used it on two more models which seemed to work, showing similar files (but 4 .t32 files instead of 3. Additionally, the t32 files did not get progressively smaller on one model making me think they might not be mipmaps). 

Do you know anything about converting models and textures?
## Post #10
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-06T16:48:42+00:00
- Post Title: Kuon .BND within .BND help with opening

1st you need to RW original mesh/animation/texture format then try to convert it to more readable equivalent (like fbx/dds or tga).
A: Basically, no mather of mesh format (with some exceptions), mesh data holds info about used texture/material - it could be an ID or the name of the texture/material. I saw the bones names, so it shouldn't be difficult...
Finding info would be much easy if you know which kind of engine this game is using - maybe game/engine was leakt at some point.

Have fun. 

Update:
There is publicly available an Alpha version: Kuon (Aug 2, 2004 prototype). What is interesting, it holds debug strings.
## Post #11
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-04-08T06:49:44+00:00
- Post Title: Kuon .BND within .BND help with opening

For what I can see textures .t32 are similar to .tm2 format so I was able to convert them to .PNG
I used the tool "Console texture explorer" to convert them to .tm2 and then Noesis to convert them to .PNG

Here are the textures:

EDIT: I can't attach all textures so here is a DOWNLOAD link:
[https://www.mediafire.com/file/dzljavdb ... 1.rar/file](https://www.mediafire.com/file/dzljavdbsm0jo66/c001.rar/file)
[c001_1out.png](https://xentaxbackup.github.io/file/22067_c001_1out.png)
## Post #12
- Username: whombrell
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 02, 2022 9:57 pm
- Post datetime: 2022-04-08T15:54:15+00:00
- Post Title: Kuon .BND within .BND help with opening

Thanks for the help, both of you. However I've still been unable to convert the models. My knowledge of model formats and programming is too limited for this task.
## Post #13
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-08T18:08:02+00:00
- Post Title: Kuon .BND within .BND help with opening

Don't give up so easily, it's an old game, check the net for files extensions maye someone already wrote some tools or published its structure.
Besides, I'm not sure, but on this you can find tutorials how to RE models/textures/archives. It's a good way to learn something.

Check:
- [Open MMD/PMX/VMD Model/Animation Dance Files in Blender (Working Miko Miko Dance Import)](https://www.youtube.com/watch?v=1xUPmWWDdfw)
- [MMD_Tools](https://mmd-blender.fandom.com/wiki/MMD_Tools)

- Look there is even editor: [how to make mmd model EASY](https://www.youtube.com/watch?v=KdVrjJT-wQw)
 in the descyption is link to it.
BTW: don't follow this kid steps - he doesn't really know what hes doing.

Most probably the code needs to be adapted to this game, but because it's a Blender plugin you can export models/anims to the more friendly formats.
