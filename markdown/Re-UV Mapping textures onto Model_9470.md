## Post #1
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-14T04:34:55+00:00
- Post Title: Re-UV Mapping textures onto Model

So, I need to re uv map Shaundi's uv map onto the model, uhhh any ideas. Lol.


Update using solid colors, adding on textures later:
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-14T04:39:49+00:00
- Post Title: Re-UV Mapping textures onto Model

those are level of details; you have to manually remove them. note that the highest LOD is not necessarily the lowest surface numbers; some level-0 hair LODs are surfaces_02X or greater. this is game archive research forum so i tend to extract as much as i can so people can learn.
## Post #3
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-14T04:43:48+00:00
- Post Title: Re-UV Mapping textures onto Model

> Reply from howfie
>
> those are level of details; you have to manually remove them. note that the highest LOD is not necessarily the lowest surface numbers; some level-0 hair LODs are surfaces_02X or greater. this is game archive research forum so i tend to extract as much as i can so people can learn.

the thing is i cant apply any textures to certain parts, at least they not showing up... there only one texture for the body along with a normal map

so what do i do? lol
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-14T04:58:25+00:00
- Post Title: Re-UV Mapping textures onto Model

i am not a blender expert, but you have to delete the LODs and apply textures to surface_000 - surface_006 (or was it 007) for shaundi. i deleted the game content from my computer so i can't check for sure, but if i remember right, not all LODs had UVs. [rexil](http://xnamodels.blogspot.com/) used blender as well.
## Post #5
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-14T05:04:07+00:00
- Post Title: Re-UV Mapping textures onto Model

wow, thats pretty bull... i mean i have to select these polygons piece by piece after coloring them.. -_-
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-14T05:05:55+00:00
- Post Title: Re-UV Mapping textures onto Model

oh no no no... surface by surface (there are 6 or 7 for shaundi). rexil would know more about the blender side of things. btw, sr3 still isn't model moddable yet... there is still too much unknown about the model format.
## Post #7
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-14T05:10:16+00:00
- Post Title: Re-UV Mapping textures onto Model

> Reply from howfie
>
> oh no no no... surface by surface (there are 6 or 7 for shaundi). rexil would know more about the blender side of things. btw, sr3 still isn't model moddable yet... there is still too much unknown about the model format.

I'm using light waved object format, so it's in blender, i dont see why its not moddable. i just need to know how to uv map this f*****, really? and theres 27 material layers... and one texture for the model not counting its normal map... -_-
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T05:15:22+00:00
- Post Title: Re-UV Mapping textures onto Model

> Reply from soulslayerzx
>
> 
I'm using light waved object format, so it's in blender, i dont see why its not moddable. i just need to know how to uv map this f*****, really? and theres 27 material layers... and one texture for the model not counting its normal map... -_-

Modding typically refers to putting it back in the game.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-14T05:20:33+00:00
- Post Title: Re-UV Mapping textures onto Model

there are actually two textures, an upper and a lower. it may go something like this:
surface000 -> lower texture
surface001 -> lower texture
surface002 -> upper texture
surface003 -> upper texture
surface004 -> upper texture
surface005 -> lower texture
surface006 -> lower texture
surface to texture is not always a 1-to-1 mapping. if i understood you correctly you are wondering how to fit 27 surfaces to 1 texture. but anyways, i'll leave this to the blender experts to come in and help you he he he.
## Post #10
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-14T05:21:04+00:00
- Post Title: Re-UV Mapping textures onto Model

> Reply from finale00
>
> soulslayerzx wrote:
I'm using light waved object format, so it's in blender, i dont see why its not moddable. i just need to know how to uv map this f*****, really? and theres 27 material layers... and one texture for the model not counting its normal map... -_-

Modding typically refers to putting it back in the game.

I know a tutorial on how to, im just saying, like i said in pm if you got an instant messenger, would be great, i mean you seem like a modeler, although we may use diff programs or you at least have some knowledge on this crap, i gotta few issues and maybe you can help me solve them, i mean seriously all i need to do is f***ing delete this lod crap so it can uv map.

im having another issue with the uv mapping i applied the head.dds to the head mesh and it doesn't do it correctly, instead the texture is super small and spams all over the head, i remember i had to configure a setting to fix this. 

okay, in the end i just need someone to tell me wtf is the lod and how to get rid of it....


EDIT: My bad, yes there are two textures and upper for torso and lower for pants and shoes. so how do i do not 1 to 1??
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T06:06:29+00:00
- Post Title: Re-UV Mapping textures onto Model

Nope I have never touched any modeling program nor do I know how to make a model or edit one I can only try to load one up lol
## Post #12
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-14T06:19:01+00:00
- Post Title: Re-UV Mapping textures onto Model

i was talking to howie, but man some blender people say it's not lod and just a mess.
## Post #13
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-14T19:28:32+00:00
- Post Title: Re-UV Mapping textures onto Model

Uhm. Anyone?
