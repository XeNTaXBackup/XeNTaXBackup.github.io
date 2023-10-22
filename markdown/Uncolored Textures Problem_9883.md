## Post #1
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-17T14:30:18+00:00
- Post Title: Uncolored Textures Problem

Hello,

I'm building a Noesis script to extract the contents from the game Naruto Shippuden: Ultimate Ninja Storm.
I've been able to extract the models successfully but I'm having a problem with the textures.
On each set of object I have 3 files that represent the level of detail (sa 00 aa lod 0/1/2), 0 being the highest level of detail.
The problem is that some textures are grey.
I don't have any experience with how textures work but my guess would be that the color inputs are swapped as I read somewhere. (Maybe red with alpha or something like that).
If that's the case, how can I turn them into how the actual texture should look like?

Here is the texture sheet for this set of objects:



Thank you in advance for any help.

Edit: Sample texture added
[ntxr003.rar](https://xentaxbackup.github.io/file/6004_ntxr003.rar)
## Post #2
- Username: fierce
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-11-18T19:55:15+00:00
- Post Title: Uncolored Textures Problem

You can use rapi.imageDecodeDXT to decode raw DXT data in any supported format to RGBA32, and from there you can do whatever you want with the pixel data, such as swapping and deriving channels. You can also use rapi.imageNormalSwizzle on your RGBA32 data to perform a variety of common normal map swapping/derivation techniques.
## Post #3
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-25T04:10:06+00:00
- Post Title: Uncolored Textures Problem

I tried using:

```
texture = NoeTexture(id, imgWidth, imgHeight, data, NOESISTEX_DXT1)
texList.append(texture)
material = NoeMaterial("ntxr_"+str(tid), "")
material.setTexture(tid)
matList.append(material)

mdl.setModelMaterials(NoeModelMaterials(texList, matList))
```


But I always get:
WARNING: Could not parse texture attributes!

Maybe I'm doing something wrong or inputing the wrong amount of data for the texture. I'm not inputing the header on the data.
What data do I need to input?
How do I know for example how much bytes should a 64x64 texture have?

Edit: repr output: (NoeTexture: w:64 h:64 p:5 f:0 n:0)
## Post #4
- Username: fierce
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-25T05:03:21+00:00
- Post Title: Uncolored Textures Problem

you should look at the bullet witch example included with noesis.
rapi.imageDecodeDXT   returns a plain rbga texture
so the format after that is
texFmt = noesis.NOESISTEX_RGBA32
example
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 
		data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_DXT1NORMAL)
		texFmt = noesis.NOESISTEX_RGBA32
return NoeTexture(entry.name, imgWidth, imgHeight, data, texFmt)
## Post #5
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-25T05:47:31+00:00
- Post Title: Uncolored Textures Problem

> Reply from chrrox
>
> you should look at the bullet witch example included with noesis.
rapi.imageDecodeDXT   returns a plain rbga texture
so the format after that is
texFmt = noesis.NOESISTEX_RGBA32
example
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 
		data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_DXT1NORMAL)
		texFmt = noesis.NOESISTEX_RGBA32
return NoeTexture(entry.name, imgWidth, imgHeight, data, texFmt)

I did look at that example, and I did try that, and a lot of other different options, but I always get:
WARNING: Could not parse texture attributes!
The materials appear on the Data Viewer, but not the textures

Edit: Attached the sample. 64x64. Size of the data that I'm inputting: 2728
Edit2: Sometimes using rapi.swapEndianArray(data, 2) makes my Noesis crash
Edit3: I think I found what the problem was, I was using 0,1,2,3.. on the texture ID, tried prefixing it with a name and its working now
[tsample.rar](https://xentaxbackup.github.io/file/6027_tsample.rar)
## Post #6
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-12-04T10:05:39+00:00
- Post Title: Uncolored Textures Problem

Hello again,

I've tried working with all or at least almost all Noesis functions regarding image handling and I got nowhere on those grey textures, the further I went is to have a colored texture, but its always one color, like light red instead of grey.
The grey textures fit the UV's perfectly but I also thought there could be the same exact textures on some other file on the same folder but I didn't find any textures similar to those grey ones.

Can any one give me an explanation on what those textures are and if they are indeed supposed to be normal textures?

Thank you in advance for any help.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-12-04T11:10:08+00:00
- Post Title: Uncolored Textures Problem

They look like your typical diffuse, specular and bump maps to me.
## Post #8
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-12-04T11:27:44+00:00
- Post Title: Uncolored Textures Problem

Are you saying that its not a "real" texture?

They are textures for objects and buildings. I'm new to 3D design but from reading:
Diffuse map = A normal, flattened texture
Specular map = A map that represents where the texture should be more shinny/highlighted 
Bump map = A map of effects to add to the texture, like rust or dirt
Am I right? If those are just specular/bump maps the "real" texture should be somewhere, but I cant seem to find it. I'm going to search more and see if I can come up with something.

Thank you for the help
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-12-04T11:37:37+00:00
- Post Title: Uncolored Textures Problem

They're all real textures, just with a different purpose. They are combined at runtime in the game engine to produce the final rendered result. The diffuse(color) texture is your main one.
## Post #10
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-12-04T12:13:02+00:00
- Post Title: Uncolored Textures Problem

I think I just figured everything out.
I wasn't finding a texture because I was thinking that the specular map UVs were the diffuse map UVs. And also because each mesh is separated by groups and I was putting the UV maps all together (they didnt seem to make sense), I tried each group UVs separately and now they make sense and I found the textures that are supposed to go there.

Thank you for the help
