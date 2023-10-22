## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-09-08T05:09:58+00:00
- Post Title: Mortal Kombat 9 Tiled Textures - Xbox 360: Solved

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2011-09-19T15:34:28+00:00
- Post Title: Mortal Kombat 9 Tiled Textures - Xbox 360: Solved

any news on this yet?
## Post #3
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-19T18:44:37+00:00
- Post Title: Mortal Kombat 9 Tiled Textures - Xbox 360: Solved

I've used Frosty's code from his [GTA IV X360 Texture viewer](http://forum.xentax.com/blog/?p=302) on Need for Speed Hot Pursuit X360 textures. It worked - just big endian -> little endian conversion was necessary

DXTDecoder.ConvertToLinearTexture() is the function you're looking for. You just need to know what type of texture it is (DXT1/3/5), and size of it.

However, I don't guarantee the result - just try it out.
## Post #4
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-09-22T05:15:27+00:00
- Post Title: Mortal Kombat 9 Tiled Textures - Xbox 360: Solved

> Reply from mnn
>
> I've used Frosty's code from his GTA IV X360 Texture viewer on Need for Speed Hot Pursuit X360 textures. It worked - just big endian -> little endian conversion was necessary

DXTDecoder.ConvertToLinearTexture() is the function you're looking for. You just need to know what type of texture it is (DXT1/3/5), and size of it.

However, I don't guarantee the result - just try it out.

Dude, you're a star     The function worked perfectly. The only thing is that it seems to lose the colour information when the texture has mip maps. Do I need to run the function on each mip map seperately?
## Post #5
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-22T08:41:00+00:00
- Post Title: Mortal Kombat 9 Tiled Textures - Xbox 360: Solved

plodtrew: I guess you need to try it out.
## Post #6
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2011-09-25T18:51:05+00:00
- Post Title: Mortal Kombat 9 Tiled Textures - Xbox 360: Solved

awesome... can't wait for more info
## Post #7
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-09-26T10:02:05+00:00
- Post Title: Mortal Kombat 9 Tiled Textures - Xbox 360: Solved

@mnn, I had to byte swap and detile each mip map seperately but it works perfectly now.   

Anyone with a jtag want to assist me to test the functionality? I'm a bit busy with work at the moment.
## Post #8
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-26T11:08:45+00:00
- Post Title: Mortal Kombat 9 Tiled Textures - Xbox 360: Solved

I forgot about mipmaps sorry
## Post #9
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-09-28T11:09:04+00:00
- Post Title: Mortal Kombat 9 Tiled Textures - Xbox 360: Solved

Updated my X-Packer app to include support for the xbox version of the game. Grab it from my site. 

Let the texture mods begin.
