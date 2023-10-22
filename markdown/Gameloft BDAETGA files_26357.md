## Post #1
- Username: fengye
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 17, 2021 1:49 pm
- Post datetime: 2023-01-30T02:40:53+00:00
- Post Title: Gameloft BDAE/TGA files

Hi, friends.Does anyone know how to read the bdae file of gameloft with it tga format textures？I saw a lot of related content on the forum, but it seems that it doesn't match this version of bdae.
Most textures in this game are 2D, at first I thought this kind of file was a skel file similar to lived2d,but the final load failed.
The TGA file can be decompressed, and then use pvrtool to read the extracted ktx file.
Here are some samples [https://drive.google.com/file/d/109p2pm ... p=drivesdk](https://drive.google.com/file/d/109p2pmMljvrL2a4NDNXOKHoPrU81q1St/view?usp=drivesdk)
Two models, two textures, two action files, and one file called MaskedRgbVertexTextureAnim.bdae(I think this file may be useful:) ）
thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-30T16:26:27+00:00
- Post Title: Gameloft BDAE/TGA files

> Reply from fengye ↑Mon Jan 30, 2023 10:40 am at Mon Jan 30, 2023 10:40 am
>
> I saw a lot of related content on the forum, but it seems that it doesn't match this version of bdae.Hi, using hex2obj usually matches for bdae  :
(first sub mesh only)



dragon_ancient_divine_energy-bdae.png (46.75 KiB) Viewed 177 times


It's relative face indices here, so some more work to do...
(Means next FI block starts with 0000 0100 0200 again.)
## Post #3
- Username: fengye
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 17, 2021 1:49 pm
- Post datetime: 2023-01-31T00:13:07+00:00
- Post Title: Gameloft BDAE/TGA files

> Reply from shakotay2 ↑Tue Jan 31, 2023 12:26 am at Tue Jan 31, 2023 12:26 am
>
> 
(Means next FI block starts with 0000 0100 0200 again.)
Wow, this is really shocking. I made some mistakes before. I didn't know these until I saw this. Thank you



Is there a way to load 2d texture? The bdae file seems to have referenced all the required textures once. But I don't understand how the file in tga format is loaded
I'm sorry I'm very noob on this
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-31T15:46:39+00:00
- Post Title: Gameloft BDAE/TGA files

Usually I don't care for textures; doesn't look like original "Tga" ("PK" in the file header, packed?)
(You could try out to give it a proper tga header.)

Or you'll need to trick around with tools that support raw data format, TextureFinder, or similar.
.



dragon_ancient_dev_energy.jpg (202.92 KiB) Viewed 148 times


(If you look at file offset 0x2AB8A you could guess to split the file here and handle the parts separately.)
## Post #5
- Username: fengye
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 17, 2021 1:49 pm
- Post datetime: 2023-02-01T05:50:58+00:00
- Post Title: Gameloft BDAE/TGA files

> Reply from shakotay2 ↑Tue Jan 31, 2023 11:46 pm at Tue Jan 31, 2023 11:46 pm
>
> 
doesn't look like original "Tga" ("PK" in the file header, packed?)
(You could try out to give it a proper tga header.)
The TGA file can be decompressed, and then use pvrtool to read the extracted ktx file.（but also some else can not read）
Anyway,really thanks for your answer. - I will try
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-02-01T08:41:15+00:00
- Post Title: Gameloft BDAE/TGA files

> Reply from fengye ↑Wed Feb 01, 2023 1:50 pm at Wed Feb 01, 2023 1:50 pm
>
> The TGA file can be decompressed, and then use pvrtool to read the extracted ktx file.（but also some else can not read）See. Fine. I don't support people who get impertinent. Cheers...
Then why did you ask:

> Is there a way to load 2d texture? The bdae file seems to have referenced all the required textures once. But I don't understand how the file in tga format is loaded
## Post #7
- Username: fengye
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 17, 2021 1:49 pm
- Post datetime: 2023-02-01T11:22:56+00:00
- Post Title: Gameloft BDAE/TGA files

> Reply from shakotay2 ↑Wed Feb 01, 2023 4:41 pm at Wed Feb 01, 2023 4:41 pm
>
> 
Then why did you ask:
Is there a way to load 2d texture? The bdae file seems to have referenced all the required textures once. But I don't understand how the file in tga format is loaded
That might an expression error I made.Sorry for that and I mean to load the tga file into the bdae model.
The structure of the tga file is very similar to the lived2d file I studied before.I think the loading method will be similar. - But that's wrong.
the bdae file references all the required textures. I think I need to spend some time figuring out how these things are loaded.
## Post #8
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2023-05-06T16:47:50+00:00
- Post Title: Gameloft BDAE/TGA files

both of the ktx files work using pvrtextool
[https://i.imgur.com/DF4lbGp.png](https://i.imgur.com/DF4lbGp.png)
[https://i.imgur.com/LM02C8O.png](https://i.imgur.com/LM02C8O.png)
but you gotta combine the textures to have proper alpha
