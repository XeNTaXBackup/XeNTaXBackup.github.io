## Post #1
- Username: Riz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 15, 2017 11:24 pm
- Post datetime: 2017-01-15T16:59:39+00:00
- Post Title: Help extract texture from "Atelier Shallie plus"(.g1t)

Hey guys!

Now I'm trying to extract texture of from "Atelier Shallie Plus: Alchemists of the Dusk Sea for PlayStation Vita".

What I have already tried is similar way to texture extraction for PS3. The method is below.

1. Extract ".elixir.gz" from ".vpk file".
2. Unpack ".cra file" from ".elixir.gz" by using Offzip.
3. Open ".g1t file" by using TextureFinder.

At a glance, it seems that the texture data is compressed by DXTC and other format. 

the part of Texture data that compressed by DXTC looks swizzled and scrambled.

I guessed that another part of texture data may be compressed by PVRTC and any other format.

Then, I try extracting a part of data to certain sizes that seemed to be proper, and added pvr header. But, the result was somewhat of blurred image.

sample:
[http://www.mediafire.com/file/eu0t06rkk ... _MODEL.g1t](http://www.mediafire.com/file/eu0t06rkk7obuju/PC20_MODEL.g1t)
