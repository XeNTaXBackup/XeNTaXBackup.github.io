## Post #1
- Username: Gon009
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 19, 2021 2:10 am
- Post datetime: 2021-01-18T18:25:26+00:00
- Post Title: The Legend of Spyro: The Eternal Night models extraction

Hello!
I need to extract some models from TLoS. I spent some time with ninja ripper, PCSX2 snapshots and so far extracting .mdg files directly gave me the biggest success so far. The problem is that I am stuck now.

I found that there was a website once having all models of the game available, however it does not exist anymore.
Here is archive.org link: [https://web.archive.org/web/20171221103 ... yro+Series](https://web.archive.org/web/20171221103514/http://ps23dformat.wikispaces.com/Legend+of+Spyro+Series)
Unfortunately none of the files were archived, only the link.

I found the script on this website([viewtopic.php?t=6360](https://forum.xentax.com/viewtopic.php?t=6360)), unfortunately it does not work properly.

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


Here is the result of that script:
[https://imgur.com/a/om9DDI6](https://imgur.com/a/om9DDI6)

For me it looks like vertexes are OK but faces are wrong.

I would be extremely grateful for any help. I only need to be able to get proper models somehow. 
Thank you.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-01-18T19:39:32+00:00
- Post Title: The Legend of Spyro: The Eternal Night models extraction

Can you upload 1 or 2 examples of the model files?
## Post #3
- Username: Gon009
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 19, 2021 2:10 am
- Post datetime: 2021-01-18T22:15:12+00:00
- Post Title: The Legend of Spyro: The Eternal Night models extraction

> Reply from DKDave ↑Tue Jan 19, 2021 3:39 am at Tue Jan 19, 2021 3:39 am
>
> 
Can you upload 1 or 2 examples of the model files?

Sure, these are two .mdg models, first is the one from screenshot:
[https://drive.google.com/file/d/1eJ3_2j ... sp=sharing](https://drive.google.com/file/d/1eJ3_2j4igce9S-Iu0M6JQZQNmyH5iyCN/view?usp=sharing)
[https://drive.google.com/file/d/1FmZN2f ... sp=sharing](https://drive.google.com/file/d/1FmZN2fjkxHGYvnMJI_UKtXjRGpG_zTmv/view?usp=sharing)
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-01-19T13:09:19+00:00
- Post Title: The Legend of Spyro: The Eternal Night models extraction

Here's my crappy initial Noesis script which should get the basic model data, with the faces.  The file probably needs extensive parsing of the PS2's VIF data to get the full thing, for UVs and normals, etc.  It's not perfect, but it's a start...  It works similar to that Blender one, just as a test of the format.


[fmt_spyro.zip](https://xentaxbackup.github.io/file/19328_fmt_spyro.zip)
## Post #5
- Username: Gon009
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 19, 2021 2:10 am
- Post datetime: 2021-01-19T15:09:02+00:00
- Post Title: The Legend of Spyro: The Eternal Night models extraction

Thank you so much! UVs and normals doesn't bother me that much, I want models for 3D printing so I don't need to put any textures on them. I found only Ignitus model before and with some editing I was able to 3D print him. You script is probably all I need, everything else I can probably fix in blender by myself when preparing the model.
Thank you so much again!
