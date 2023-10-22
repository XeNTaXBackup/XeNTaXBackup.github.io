## Post #1
- Username: ExPlOrER
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Apr 04, 2011 6:27 pm
- Post datetime: 2011-04-05T11:22:56+00:00
- Post Title: 3d models from PS2 Game

Please, help with extracting 3d models from 

Legend of Spyro:A New Beginning(PS2)
format 3d model  *.mdg
[http://megaupload.com/?d=YOWIKQU8](http://megaupload.com/?d=YOWIKQU8)
## Post #2
- Username: ExPlOrER
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Apr 04, 2011 6:27 pm
- Post datetime: 2011-04-11T11:28:32+00:00
- Post Title: 3d models from PS2 Game

here may have, a description of the format
[http://ps23dformat.wikispaces.com/Legen ... yro+Series](http://ps23dformat.wikispaces.com/Legend+of+Spyro+Series)
## Post #3
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-04-12T08:29:52+00:00
- Post Title: 3d models from PS2 Game

have you tried 3d ripper DX while running the game on an emulator? it's a kind of desperation method, but if your hardware allows it to work (mine doesn't  ) it could save you a lot of trouble.
## Post #4
- Username: ExPlOrER
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Apr 04, 2011 6:27 pm
- Post datetime: 2011-04-12T09:27:17+00:00
- Post Title: 3d models from PS2 Game

> Reply from Devilot
>
> have you tried 3d ripper DX while running the game on an emulator? it's a kind of desperation method, but if your hardware allows it to work (mine doesn't  ) it could save you a lot of trouble.
I've already done that, but received only the texture.


[viewtopic.php?f=16&t=5098&hilit=blade+kitten](http://forum.xentax.com/viewtopic.php?f=16&t=5098&hilit=blade+kitten)
Here is a script for 3DS max, but it does not work (error "Unable to convert: undefined to type: Integer").
Tested this script on the 3d models from the mentioned in the forum thread (Blade Kitten (PC)) the same result, I think an error somewhere in the script.
## Post #5
- Username: ExPlOrER
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Apr 04, 2011 6:27 pm
- Post datetime: 2011-04-23T13:01:47+00:00
- Post Title: 3d models from PS2 Game

```

chunk_id = 0x6c028000
chunk_end_id = 0x14000000
chunk_size = 0xcc

verts_count = 0;
ids_count = 0;

vertex_array = #()
face_array = #()

file_name = getOpenFileName \
  caption:"Legend of Spyro Model File" \
  types:"Legend of Spyro Model File(*.mdg)|*.mdg" \
  historyCategory:"Legend of SpyroObjectPresets"

if file_name != undefined then
  f = fopen file_name "rb"

if f != undefined then (
  fseek f 0 #seek_end
  size = ftell f
  fseek f 40 #seek_set
  while size > ftell f do (
    while ReadLong f #unsigned == chunk_id do (
      verts_count = ReadLong f #unsigned
      weight = ReadFloat f
      fseek f 32 #seek_cur
      for i = 1 to verts_count do (
        x = ReadFloat f
        y = ReadFloat f
        z = ReadFloat f
        append vertex_array [x, z, y]
      )
      ids_count = ids_count + verts_count
      
      while ReadLong f #unsigned != chunk_end_id do ()
    )
    
    if ids_count != 0 do (
      for i = 1 to ids_count - 2 do
        append face_array [ i , i + 1 , i  + 2 ]
      
      new_mesh = mesh vertices:vertex_array faces:face_array
      
      ids_count = 0;
      vertex_array = #()
      face_array = #()
    )
  )
  fclose f
)

```

The script doesn't work quite right. 
How can I fix the script?

Screenshot 3d models. 
[http://www.megaupload.com/?d=Y81EZ1RS](http://www.megaupload.com/?d=Y81EZ1RS)
## Post #6
- Username: abdyla
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 30, 2011 6:29 am
- Post datetime: 2011-04-27T01:12:06+00:00
- Post Title: 3d models from PS2 Game

Here that occurs when I load .mdg a format in 3Ds Max9.


p.s.:Mine.mdg file from Star Wars The Force Unleashed [PS2]
## Post #7
- Username: ExPlOrER
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Apr 04, 2011 6:27 pm
- Post datetime: 2011-04-27T01:44:19+00:00
- Post Title: 3d models from PS2 Game

script was written based description of the format of this site
[http://ps23dformat.wikispaces.com/Legen ... yro+Series](http://ps23dformat.wikispaces.com/Legend+of+Spyro+Series)

There is another version of the script, but it loads only the first mesh of the model. But most importantly, this first mesh is obtained without distortion

```

chunk_id = 0x6c028000
chunk_end_id = 0x14000000
chunk_size = 0xcc

verts_count = 0;
ids_count = 0;

vertex_array = #()
face_array = #()

function skip file offset = fseek file offset #seek_cur

file_name = getOpenFileName \
  caption:"Legend of Spyro Model File" \
  types:"Legend of Spyro Model File(*.mdg)|*.mdg" \
  historyCategory:"Legend of SpyroObjectPresets"

if file_name != undefined then
  f = fopen file_name "rb"

if f != undefined then (
  skip f 40
  while ReadLong f #unsigned == chunk_id do (
    verts_count = ReadLong f #unsigned
    weight = ReadFloat f
    skip f 32
    for i = 1 to verts_count do (
      x = ReadFloat f
      y = ReadFloat f
      z = ReadFloat f
      append vertex_array [x, z, y]
    )
    ids_count = ids_count + verts_count
      
    while ReadLong f #unsigned != chunk_end_id do ()
  )
  fclose f
  
  for i = 2 to ids_count - 1 do (
    append face_array [ i-1, i, i + 1 ]
  )
  
  new_mesh = mesh vertices:vertex_array faces:face_array
)

```

Is it possible on their basis, to write a working script.
These scripts were not written by me.

This script only works with models of the Legend of Spyro.
Maybe formats of 3d models from various games may be different
## Post #8
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-04-30T15:03:36+00:00
- Post Title: 3d models from PS2 Game

This format, like most of the other formats documented on that site, use ps2 vif tags.  The "chunk_id" in this instance is not going to be constant throughout the file, as it is actual a bitfield with a number of values determining how to process the data that follows it.

i explain a bit about the format in this post: [viewtopic.php?p=52244#p52244](http://forum.xentax.com/viewtopic.php?p=52244#p52244)

Although it can be done with brute force in some cases, a far more robust solution is to properly handle the vif tags and parse the resulting unpacked data.
## Post #9
- Username: ExPlOrER
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Apr 04, 2011 6:27 pm
- Post datetime: 2011-05-01T22:52:53+00:00
- Post Title: 3d models from PS2 Game

> Reply from revelation
>
> This format, like most of the other formats documented on that site, use ps2 vif tags.  The "chunk_id" in this instance is not going to be constant throughout the file, as it is actual a bitfield with a number of values determining how to process the data that follows it.

i explain a bit about the format in this post: viewtopic.php?p=52244#p52244

Although it can be done with brute force in some cases, a far more robust solution is to properly handle the vif tags and parse the resulting unpacked data.

Thank you!
As will be free time to try to understand
## Post #10
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-07-07T20:12:17+00:00
- Post Title: 3d models from PS2 Game

Maybe you did not see this:
[http://ps23dformat.wikispaces.com/file/ ... ractor.zip](http://ps23dformat.wikispaces.com/file/view/SpyroENmodelextractor.zip)
Included is first a Python3 (you Must install a version of Python3, Python2 will give you errors)
script that will extract the RKV file into subfiles (the subfiles will come out a bigger size then the Whole RKV, because of some nesting, but nothing is compressed)
Then their is a Python3 Script to batch convert all of the .MDG3 models. It will convert all of the MDG3 models, but not the level terrain models as those are a different extension and format, but yes all of the characters models will each be converted into .3ds files. Depending on what software you use to open the .3ds files, you might get an error of Null vertexes, ignore that, and just delete the null and extra vertexes at position 0,0,0 and your mesh will look fine.
So far I do not think anyone has downloaded it, but I can ask the programmer of it, using my descriptions to make meshes double sided, and add UVs if anyone is interested. Remember Python2 which is what blender uses will not work with this script, only Python3. If you have any questions please contact me or the programmer using his email address inside the script.

But yes me and him will add animations and rigged meshes, including the script based animations (in the game their are regular animations with are binary, and also scripted animations which use ASCII, and interact with the environment like mouth_open rotation speed, walk to location 3.1,4.5,.09 and play sound feet_walking.
