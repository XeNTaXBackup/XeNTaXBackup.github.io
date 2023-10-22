## Post #1
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2011-12-27T04:18:16+00:00
- Post Title: Gothic 4 .bakedgeom

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: jacquel
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 29, 2011 5:21 pm
- Post datetime: 2012-01-06T18:16:35+00:00
- Post Title: Gothic 4 .bakedgeom

what is this model tools?  
thanks
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-06T21:51:29+00:00
- Post Title: Gothic 4 .bakedgeom

And do they come with source. The format looks pretty straightforward but that's because I'm skipping over lots of stuff.
## Post #4
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-01-07T00:17:50+00:00
- Post Title: Gothic 4 .bakedgeom

Sorry, I was working with Two Worlds 2 files at the same time as the Arcania stuff and got mixed up with Szkaradek123's TW2 tools. I was working with too many meshes to keep them all straight. Karpati's 3D model Converter is the only tool that I know of that can convert Arcania .model files, but there is no skeletal mesh information, and the .bakedgeom static meshes are not supported. Excellent work, finale00!
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-07T04:00:58+00:00
- Post Title: Gothic 4 .bakedgeom

Upload the textures for these models.
Or at least, upload some models along with their textures.

After that, there's just one section I'm completely skipping but it looks like it gets the geometry out properly.
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-01-07T08:10:13+00:00
- Post Title: Gothic 4 .bakedgeom

great work finale00,
also, there is any way to convert bones/weights along with the models?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-07T13:19:09+00:00
- Post Title: Gothic 4 .bakedgeom

I'm assuming when it says "staticmesh" it means there are no bones.
I don't know what the other file is like.
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-01-07T14:39:50+00:00
- Post Title: Gothic 4 .bakedgeom

> Reply from finale00
>
> I'm assuming when it says "staticmesh" it means there are no bones.
I don't know what the other file is like.
sorry, my mistake, if you can please take a look on the [characters models](http://dl.dropbox.com/u/9919707/blogs/xentax.com/arcania-pc/modular_characters.zip) too

p.s.: if need i can make new theme.
## Post #9
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-01-07T16:53:11+00:00
- Post Title: Gothic 4 .bakedgeom

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T01:45:34+00:00
- Post Title: Gothic 4 .bakedgeom

Hmm so first, the skeletalmesh is fortunately a completely different format but OBJ versions are there so I'm guessing it's been done (I would like source for that so I don't have to look at it myself). The format is not hard but I don't understand bones ATM so I can only parse it, get the geometry out, and do nothing with the bones but leave it there in a method and hope that will be filled out in the future.

Second, the staticmesh.



[http://db.tt/7qodb3eF](http://db.tt/7qodb3eF)

Noesis plugin. Will need Sanae3D package in sig (although I don't think I actually used anything from it this time besides initializing some variables that aren't used anyways). Only so that I don't have to remove a couple lines of code and re-write a couple lines of code myself.

There seems to be issues trying to apply a really large texture.

I don't really understand materials so not sure what normal and specular textures do, but added them to the materials. They don't seem to be loading up though (I think)

There are different vertex types for the bakedgeom. So far I've found two from the samples provided (32 and 36 bytes), but don't know if there are more. If there are more, noesis will either crash or give you an error. If it crashes send the model to me (or just figure out the vertType and add it yourself if it's faster)

If you look at the parse_mesh method, you'll notice I skipped 260 bytes.
I'm not sure if that applies to all models, nor do I know what it is.

I have also flipped the y/z axis (I think that's what the transformation does) in the parse_vertices method.
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-02-20T02:30:39+00:00
- Post Title: Gothic 4 .bakedgeom

finale00, can you explain how to load py for arcania in noesis, every time I'm getting Sanae error, but i have Sanae.py in my "noesis\plugins\python" directory

thanks
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-20T02:44:06+00:00
- Post Title: Gothic 4 .bakedgeom

you need create a folder called Sanae3D into python path for make it work, gl
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-02-20T03:32:33+00:00
- Post Title: Gothic 4 .bakedgeom

> Reply from CriticalError
>
> you need create a folder called Sanae3D into python path for make it work, glthanks, it works now
but without uv?
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T03:39:23+00:00
- Post Title: Gothic 4 .bakedgeom

Here try this one. I've removed the dependence on Sanae3D package.
Textures assumed to be stored in the same folder as the model.

[http://db.tt/7qodb3eF](http://db.tt/7qodb3eF)
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-02-20T04:22:08+00:00
- Post Title: Gothic 4 .bakedgeom

> Reply from finale00
>
> Here try this one. I've removed the dependence on Sanae3D package.
Textures assumed to be stored in the same folder as the model.

http://db.tt/7qodb3eFanyway i can't load uv, trying [this objects](http://dl.dropbox.com/u/9919707/blogs/xentax.com/arcania-pc/objects_outside.zip)
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T04:48:13+00:00
- Post Title: Re: Gothic 4 .bakedgeom

The normals also look kind of funny.
Upload the textures as well.
## Post #17
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-02-20T04:56:08+00:00
- Post Title: Re: Gothic 4 .bakedgeom

> Reply from finale00
>
> The normals also look kind of funny.
Upload the textures as well.[some of them](http://dl.dropbox.com/u/9919707/blogs/xentax.com/arcania-pc/objects_outside_textures.zip), for barrels and boat
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T05:15:43+00:00
- Post Title: Re: Gothic 4 .bakedgeom

Seems to load fine for me.
## Post #19
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-02-20T05:21:15+00:00
- Post Title: Re: Gothic 4 .bakedgeom

> Reply from finale00
>
> Seems to load fine for me.for me too, but without UV, will be great if script can load texture coordinates too, 'cause i can't correct see any textures on the models
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T05:28:04+00:00
- Post Title: Re: Gothic 4 .bakedgeom

I wouldn't know what the issue might be.

Noesis seems to be loading the textures path as (on my computer)

```

```


Don't know if two forward-slashes might be causing a problem, though I'm not sure why there are two of them.
## Post #21
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-02-20T05:37:32+00:00
- Post Title: Re: Gothic 4 .bakedgeom

> Reply from finale00
>
> I wouldn't know what the issue might beoh man, please try to understand, i don't have any problem with loading textures, but textures looks incorrect on the models, I think it's because uv is missing
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T06:01:21+00:00
- Post Title: Re: Gothic 4 .bakedgeom

There's a whole section of text that describes things like bump maps, granular colors, and lighting and stuff.
I don't know what to do with that, nor am I sure if it affects how the model looks.

Maybe the vertices are parsed wrong or I'm not assigning the correct values. Someone else will have to look into it cause there really aren't any unknowns in this format left.
## Post #23
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-23T23:17:20+00:00
- Post Title: Re: Gothic 4 .bakedgeom

> Reply from finale00
>
> Maybe the vertices are parsed wrong or I'm not assigning the correct values. Someone else will have to look into it cause there really aren't any unknowns in this format left.

The UVs are halffloats.

```
rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, 32, 12) // type 9

Don't set rpgBindNormalBufferOfs

```
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-24T08:51:50+00:00
- Post Title: Re: Gothic 4 .bakedgeom

Damn half-floats lol
## Post #25
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-08-24T09:01:40+00:00
- Post Title: Re: Gothic 4 .bakedgeom

hope is back!
## Post #26
- Username: ExPlOrER
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Apr 04, 2011 6:27 pm
- Post datetime: 2012-08-25T14:44:41+00:00
- Post Title: Re: Gothic 4 .bakedgeom

What did you use to unpack the game?
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-09-29T15:30:22+00:00
- Post Title: Re: Gothic 4 .bakedgeom

> Reply from ExPlOrER
>
> What did you use to unpack the game?John Doe's Datablock extractor.

Didn't test this one [http://www.xentax.com/uploads/author/jo ... Blocks.zip](http://www.xentax.com/uploads/author/johndoe/ExtractDataBlocks.zip) - should be the same.

Very funny that someone is busy with this game.

Here's a mesh extractor for character  and weapon models. Maybe it's helpful.

[http://www.megafileupload.com/en/file/3 ... r-zip.html](http://www.megafileupload.com/en/file/369151/ArcamiA-MeshExtractor-zip.html)

It's in german but you only need 'the code'; for example  '001' for
..\block421412\models\modular_characters\
head_generic_female_wilma.model

(You can ignore the accompanying tools; they were for converting the (weapon) objs to Gothic3 meshes (xcmsh) using my G3-ObjFaker.)

This is Ivy (with some hair/texture probs):

[](http://www.pic-upload.de/view-16241174/Ivy_upps.jpg.html)
[http://www10.pic-upload.de/29.09.12/fwvl2u69o8ha.jpg](http://www10.pic-upload.de/29.09.12/fwvl2u69o8ha.jpg)
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-03-20T11:46:44+00:00
- Post Title: Re: Gothic 4 .bakedgeom

Even if you don't like to play this game: its models are awful.
(So I got it for 6 € lately-)



ArcaniA_silver_lake_castle_.jpg (200.71 KiB) Viewed 43 times


[](http://www.pic-upload.de/view-18590988/ArcaniA_silver_lake_castle_insight_blender.jpg.html)
