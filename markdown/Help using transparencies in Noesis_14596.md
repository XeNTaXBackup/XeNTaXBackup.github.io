## Post #1
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-07-04T05:27:52+00:00
- Post Title: Help using transparencies in Noesis

I was wondering if someone could give me a few tips as to how to apply transparency to textures/materials using Noesis. I am new to materials in 3D graphics but I have managed to get some very basic understanding of how it works. I am unfamiliar with most terms like alpha blending and alpha test, but I'm trying to learn and have gone as far as creating basic materials in Noesis, using diffuse and normal textures. However, I would also like to apply transparencies to some of my materials.

For example, say I applied a diffuse texture to my NoeMaterial, and this texture is a NoeTexture instance:

> mat = NoeMaterial(matName, diffuseTexName)
>
> tex = rapi.loadExternalTex(diffuseTexFile)
>
> tex.name = diffuseTexNameAnd say that each of this texture's pixels whose color is #000000 (black) were intended to be rendered as transparent. The way I'm loading my textures/materials so far renders those pixels as is, as black-colored pixels on the material, where ideally, black pixels should be rendered as fully transparent instead. How would I tell Noesis that it should render this color as transparent? If this would be the wrong approach to applying transparencies then what would be the correct way?

P.S.
If it helps, I am also given a float called a material alpha mask value but am not sure what to do with it.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-07-04T12:02:01+00:00
- Post Title: Help using transparencies in Noesis

when you read the texture in just set that to the alpha channel and noesis will auto use it.
## Post #3
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-07-04T16:33:36+00:00
- Post Title: Help using transparencies in Noesis

Thanks for your reply. What would be the name of the function that would let me do this? (Assuming it's a function.)
## Post #4
- Username: errno
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-07-04T22:14:34+00:00
- Post Title: Help using transparencies in Noesis

texData = rapi.imageDecodeRaw(texData, len, width, "b8g8r8a8")
just set the components where they should be and how many bytes in each
b8
g8
r8
a8

its also a lot easier to help if game details are given.
## Post #5
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-07-05T14:31:04+00:00
- Post Title: Help using transparencies in Noesis

Thanks again for your help. So I tried a few things with that function but I seem to be misunderstanding something because the only thing I was able to get to work correctly was making it return the same texture I passed to it, which still has the pixels that are supposed to be translucent being rendered as opaque. Here is what I tried:

```
mat = NoeMaterial(matName, diffuseTexName)
tex = rapi.loadExternalTex(diffuseTexFile)
tex.name = diffuseTexName

#New code attempting to add transparency:
texData = rapi.imageDecodeRaw(tex.pixelData, tex.width, tex.height, "r8 g8 b8 a8") #returns exact same image, transparencies not working
tex.pixelData = texData
```

I'm not sure if the parameters I'm passing to imageDecodeRaw are the ones it wants. Giving it the string "r8 g8 b8 a8" was the only one that returned an image that didn't look corrupted. I tried this on a texture from a random model of the game I'm working on. This texture file is a .dds of type DXT1, which to the best of my knowledge contains the normal map in the channels Red and Green, and the Blue channel seems to contain the alpha mask texture. So for this I attempted to make the Blue channel be read as the alpha channel by using the string "r8 g8 a8 p8", but the result of this is a corrupted-looking texture in Noesis, and the areas that should be transparent are still opaque. I lack the experience of working with textures/materials to understand what I might be doing wrong, but if I had to guess, I would say I may be passing the wrong parameters to imageDecodeRaw?

If it helps, the game I'm working on is DragonaEU, the game can be downloaded for free legally so I guess there's no problem linking to the download page in this forum: [http://dragonaeu.flamegames.hu/?page=download](http://dragonaeu.flamegames.hu/?page=download)
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-07-05T21:11:54+00:00
- Post Title: Help using transparencies in Noesis

you will need to see if they set the transparency as 1 byte.
[http://www.fsdeveloper.com/wiki/index.p ... with_alpha](http://www.fsdeveloper.com/wiki/index.php?title=DXT_compression_explained#DXT1_with_alpha)
you are better off loading the dxt manually and setting the read mode.
you will need to look in a hex editor and see how they set the alpha.
so it might be
r8g8b8a1p7
or something like that
basically figure out how to separate the alpha and use that to load it.
I am no expert on dxt1 alpha channels so there might be more i do not know.

might help to post an example texture.
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-07-05T21:59:07+00:00
- Post Title: Help using transparencies in Noesis

You need to ensure the material for the texture is set to the default blend mode if you want alpha testing, or explicitly set an alpha test ref value. If you aren't actually providing materials and are allowing them to be created for you by the rpgeo interface, alpha testing will be enabled by default.

DXT1 only supports 1-bit alpha by way of a special case where a given block's dword representation of color0 is <= color1. The Noesis software DXT decoder supports and respects this, and will hand you back appropriate alpha values when decoding a DXT1. Your hardware GL implementation, on the other hand, may or may not choose to respect it when Noesis uploads the DXT data directly for rendering. You can always decode the DXT data into RGBA32 data (via rapi.imageDecodeDXT) if you want the Noesis software DXT decoder to set the standard for you.

You should note, however, that black != transparent for DXT1. This special block mode is merely a way of saying the fourth block color is transparent-black. You might also be looking for additive blending instead of alpha blending here.
## Post #8
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-07-07T19:10:25+00:00
- Post Title: Help using transparencies in Noesis

I'm starting to think additive blending is what I need too but my knowledge as to how to apply this is limited. After looking at a few textures I'm starting to think that these DXT1 textures don't actually have any alpha information encoded in them at all and instead a transparency mask is provided on the Blue channel of the normal-map texture.

Here is an example:

Both of the textures I've uploaded ([click to download raw DDS files](http://www.filedropper.com/dds_1)) are of type DXT1. One is the diffuse map, nothing to see here other than it seems to contain no alpha information encoded in it. The other texture is the normal-map, which from what I can tell is two textures in one, the Red and Green channels of this file seem to contain the normal map, while the Blue channel seems to contain a mask for the transparency.

This is the texture file containing the normal-map and possibly the alpha mask (Red Green and Blue channels all enabled):

This is that same file but without the Blue channel. This seems to be the normal-map, which is found in the Red and Green Channels:

And this is the same file again but now I removed the Red and Green channels and just left the Blue channel. It seems to be an alpha mask?:

So now I'm wondering what are the commands needed to first extract the Blue channel and then use it as an alpha mask on the diffuse. Would this be the correct way to proceed?
