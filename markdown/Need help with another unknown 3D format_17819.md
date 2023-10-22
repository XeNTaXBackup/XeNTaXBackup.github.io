## Post #1
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2018-03-14T10:10:07+00:00
- Post Title: Need help with another unknown 3D format

After my last adventure with the Xbox Design Lab's controller models, I've found a new challenge: 
The models used by the achievement badges in the iOS Activity app.
If anyone's curious, they can be found inside of FitnessUIAssets.bundle inside the iOS IPSWs, but here's an example file: [https://bubbelsearch.de/files/BadgeModel.bdg](https://bubbelsearch.de/files/BadgeModel.bdg)

I've written a simple (but currently, totally broken) converter script for it: [https://gist.github.com/SamusAranX/aa0e ... 6758b861bf](https://gist.github.com/SamusAranX/aa0e35e1de3057e3863ad86758b861bf)
...but the output is obviously wrong:

(The .obj file from the screenshot is here: [https://bubbelsearch.de/files/BadgeModel.obj](https://bubbelsearch.de/files/BadgeModel.obj))

Instead, it's supposed to look something like this:


As far as I can tell, the "header" consists of 9 integers, then comes a bunch of floats (which my script interprets as vertices), and the rest seems to be all integers again (vertex indices?).
In the resulting .obj file, you can even make out the round shape of the expected model, but with a lot of seemingly random crap around it.

My guess is that there's other stuff in the .bdg file, like normals and whatnot, but the numbers from the "header" don't really tell me where those are.

When working on the Xbox controller models, I caught a lucky break when I found a human-readable file containing literally all of the offsets, but with these models, there's nothing.
Any help is greatly appreciated.
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-14T13:24:33+00:00
- Post Title: Need help with another unknown 3D format

The vertex data you are reading in your script isn't just vertex positions. There are also normals and uvs there. 3 floats for vertex positions, 3 floats for normals, 2 floats for uvs.

So if you just want the positions, you would start from offset 36. Read 12 bytes (3 floats) for positions, then skip 20 bytes (12 for normals, 8 for uvs). You are reading the indices correctly.

It ends up like this
## Post #3
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2018-03-14T14:37:08+00:00
- Post Title: Need help with another unknown 3D format

Yeah, I figured there was something else since the seemingly random vertices everywhere had a pattern to them.
I managed to figure out what exactly by catching another lucky break and finding Apple's documentation for this format:
[https://developer.apple.com/documentati ... etrysource](https://developer.apple.com/documentation/scenekit/scngeometrysource)
They call it "interleaved data", which it basically is.
I've updated the Gist with a script that works: [https://gist.github.com/SamusAranX/aa0e ... 6758b861bf](https://gist.github.com/SamusAranX/aa0e35e1de3057e3863ad86758b861bf)
There's still some weirdness going on (like with the holes in the model on the following screenshot), but that's nothing I can't fix in Blender.


Edit: Okay, I got my hopes up too soon. Turns out I'm not quite done yet.
There are apparently (at least) two other types of .bdg file that my script can't handle. First, this one: [https://bubbelsearch.de/files/BadgeModel_2017_12.bdg](https://bubbelsearch.de/files/BadgeModel_2017_12.bdg)
It's supposed to look like this:

but my script instead outputs this:

Any idea what I might be doing wrong?

Then there's this one: [https://bubbelsearch.de/files/BadgeModel2.bdg](https://bubbelsearch.de/files/BadgeModel2.bdg)
That one crashes my script because its "header" is apparently only 20 bytes long.
I took a quick look with a hex editor and apart from the smaller header, it seems to be built the same way as all the other files. You wouldn't happen to have an idea about what the header could contain?
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-15T02:06:40+00:00
- Post Title: Need help with another unknown 3D format

i would say it goes something like this  

```
4 bytes - face count * 3
4 bytes - num material groups
for i in material groups
    4 bytes - texture index for this group
for i in material groups
    4 bytes - count * 3 for that face group
vertex block (32 byte stride)
face data (dwords)
```
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-15T02:26:49+00:00
- Post Title: Need help with another unknown 3D format

> Reply from GordenF
>
> 
Any idea what I might be doing wrong?

You are using the vertex count instead of the index count in your script. Probably a typo. Change "header[0]" to "header[1]" on line 40. Also multiply it with 3, since header[1] is the face count.
## Post #6
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2018-03-15T09:33:47+00:00
- Post Title: Need help with another unknown 3D format

> Reply from akderebur
>
> You are using the vertex count instead of the index count in your script. Probably a typo.I probably copy-pasted that part and never went back to correct it. Welp

> Reply from AceWell
>
> i would say it goes something like thisNice, I never would've guessed that material group part.
Based on your info, I've modified my script to correctly parse the header, and now it works flawlessly: [https://gist.github.com/SamusAranX/aa0e ... 6758b861bf](https://gist.github.com/SamusAranX/aa0e35e1de3057e3863ad86758b861bf)
Just look at this beauty:


Thank you both for your help!
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-25T02:57:20+00:00
- Post Title: Need help with another unknown 3D format

here is a Noesis python script just for fun too 


 fmt_iOSActivityApp_bdg.zip
(680 Bytes) Downloaded 24 times


the models are split into submeshes according to their material groups
