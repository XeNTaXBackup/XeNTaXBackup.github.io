## Post #1
- Username: rauldj
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 12, 2017 7:39 pm
- Post datetime: 2017-09-20T22:02:50+00:00
- Post Title: CRIWARE CRI GT2, supposed graphics middleware?

I'm trying to extract some models and textures from the PS Vita game "Ciel noSurge" from Gust. According to the files themselves and to this japanese source: [http://www.cri-mw.co.jp/product/intervi ... index.html](http://www.cri-mw.co.jp/product/interview/2012/ciel/index.html) (an interview with Akira Tsuchiya), for the game graphics they used a PC middleware that CRIWARE had, the so called "CRI GT2", and adapted it to the Vita. Hre are some example files:

A texture file: [https://my.mixtape.moe/mdjqjv.gtx](https://my.mixtape.moe/mdjqjv.gtx)
A model file: [https://my.mixtape.moe/vltsgv.gmd](https://my.mixtape.moe/vltsgv.gmd)
An esqueleton file: [https://my.mixtape.moe/osgcrr.gsk](https://my.mixtape.moe/osgcrr.gsk)
An animation file: [https://my.mixtape.moe/geelac.gan](https://my.mixtape.moe/geelac.gan)

I can't find absolutely nothing about this software on the Internet except that interview so hopefully someone will be able to help.

Thank you very much in advance.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-21T08:37:53+00:00
- Post Title: CRIWARE CRI GT2, supposed graphics middleware?

using hex2obj (view link in my sig):



vltsgv-gmd.jpg (215.65 KiB) Viewed 141 times


(don't be confused about uv pos, should be 24 here, but the FVF starts with normals, so we've an offset of 12 bytes for the vertices startaddress which the uvpos refers to)
## Post #3
- Username: rauldj
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 12, 2017 7:39 pm
- Post datetime: 2017-09-21T10:31:21+00:00
- Post Title: CRIWARE CRI GT2, supposed graphics middleware?

Wow, thank you for your tool! Now at least I have were to begin.
## Post #4
- Username: rauldj
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 12, 2017 7:39 pm
- Post datetime: 2017-09-22T00:33:26+00:00
- Post Title: CRIWARE CRI GT2, supposed graphics middleware?

Well, after a long day of trial and error, I finally managed to get almost all the models I wanted:




However, several problems appeared:

The first of all was the quite impresive amount of "random" triangles these things have: I don't know if this is because I'm not using the tool correctly (even though on your side it seems to have the same problem) or it's just laziness from the developer side or what. I just removed them.

The second one is that every time I try to put texture on some surface on 3ds Max or load the UV map, the software just crashes, so even if I somehow manage to extract the damn textures, I think I wouldn't be able to use them. Dropping materials seems to work.

Thanks again.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-22T06:28:13+00:00
- Post Title: CRIWARE CRI GT2, supposed graphics middleware?

> Reply from rauldj
>
> Well, after a long day of trial and error, I finally managed to get almost all the models I wanted:that's great! Most people don't understand how to use the tool.  

> The first of all was the quite impresive amount of "random" triangles these things have: I don't know if this is because I'm not using the tool correctly (even though on your side it seems to have the same problem)should be a matter of the format; you could add some grouping lines into the obj output of hex2obj such as
g sm0, g sm1, and so on all 500 facelines starting with

g sm0
f 75/75 333/333 77/77
f 77/77 333/333 335/335
f 200/200 189/189 38/38
[...]
to see where the superfluous triangles appear:



vltsgv-submesh.jpg (206.9 KiB) Viewed 119 times



> The second one is that every time I try to put texture on some surface on 3ds Max or load the UV map, the software just crashes,using the above mentioned method should allow to apply textures group per group (don't have textures so could not try).
## Post #6
- Username: rauldj
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 12, 2017 7:39 pm
- Post datetime: 2017-09-22T09:14:13+00:00
- Post Title: CRIWARE CRI GT2, supposed graphics middleware?

Thank you very much again for you help.

> Reply from shakotay2
>
> should be a matter of the format; you could add some grouping lines into the obj output of hex2obj such as
g sm0, g sm1, and so on all 500 facelines starting with

g sm0
f 75/75 333/333 77/77
f 77/77 333/333 335/335
f 200/200 189/189 38/38
[...]
to see where the superfluous triangles appear:
vltsgv-submesh.jpg

By reading that, I understand that I'm able to group several faces of the 3D model, and modify them separately on the software, but I don't know at what points should I make those separations, neither what is their purpose regarding the "extra" random triangles I have. If its purpose is "just" seeing were the "extra" triangles are, I think I can see them already even with the unseparated 3D model.

3ds keeps crashing when trying to do anything UV map related no matter how many groups I make though...

EDIT: Oh, I see... It seems that killing every single random extra triangle makes 3ds Max NOT to crash when trying to edit the UV map. I need further testing.

EDIT 2: OK, I think I got everything back and after deleting almost all the strange triangles I get no crashes anymore when opening the UV maps, thanks again. Regarding the textures: should I look for help on Graphic file formats too?
## Post #7
- Username: rauldj
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 12, 2017 7:39 pm
- Post datetime: 2017-09-24T21:17:51+00:00
- Post Title: CRIWARE CRI GT2, supposed graphics middleware?

Regarding to the textues, none of the Vita PowerVR related tools I tried worked for me, so this is the best I can get out of them, and they looks swizzled as f****:



It should look like this, or at least I think this is the related image in the game:
