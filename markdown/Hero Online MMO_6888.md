## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-01T18:46:58+00:00
- Post Title: Hero Online MMO

Here are some character models from [Hero online](http://hero.netgame.com/).

The items were straightforward to figure out, but I don't know what kind of data a character might have.
Maybe someone can look at it so I can look at what kinds of things there are for future reference?

Maybe the bones are stored in a separate file (.n3joint). The meshes are stored in .n3cskins
The other files just specify what needs to be loaded.
[Hero.7z](https://xentaxbackup.github.io/file/4410_Hero.7z)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-01T18:54:16+00:00
- Post Title: Hero Online MMO

All non-character models (items, map assets, etc) are stored in n3pmesh files.
n3shape files specify the model name, the texture used, and n3pmesh that should be loaded.
n3object files specify which n3shape file to load.

Format of n3pmesh is straightforward

```
length mesh_name

dword_4 ???
dword vertNum
dword faceNum * 3

struct vertex {
   float_3 vx, vy, vz
   float_3 nx, ny, nz (just guessing)
   float_2 tu, tv
}
struct face {
   word_3 v1, v2, v3
}
dword_4 ???

```


Some samples attached for those that want to try it.
[items.7z](https://xentaxbackup.github.io/file/4413_items.7z)
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-07-02T10:28:37+00:00
- Post Title: Hero Online MMO

Did you read this thread ?   

[viewtopic.php?f=10&t=5464](http://forum.xentax.com/viewtopic.php?f=10&t=5464)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-02T12:40:17+00:00
- Post Title: Hero Online MMO

lol, didn't know it had a different name
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-07-02T16:31:29+00:00
- Post Title: Hero Online MMO

I think these games are use same formats.

I did find 2 different .n3pmesh formats in the Knight Online game.
The first is same with your description, but the second is different.

Here I uploaded some sample files. Can you look into these files ?
[n3pmesh_bad.zip](https://xentaxbackup.github.io/file/4419_n3pmesh_bad.zip)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-02T21:49:19+00:00
- Post Title: Hero Online MMO

Hmm after the mesh name there 6 dwords.
The one I wrote up there assumed that the last 2 dwords are the vertNum and faceNum, but for the ones you posted the 3rd seem to be the vertNum and the 4th is the faceNum.

I looked at a couple hero meshes and noticed that 3-4 are the same as 5-6, so perhaps 3-4 are the ones we want.

Revised format (still works for hero n3dpmesh)

```
length mesh_name

dword_4 ???
dword vertNum
dword faceNum * 3

struct vertex {
   float_3 vx, vy, vz
   float_3 nx, ny, nz (just guessing)
   float_2 tu, tv
}
struct face {
   word_3 v1, v2, v3
}

/* unclear what this section is, will need more samples */
dword ??? (in hero online, value always 2, while the knights samples has value 6)
struct ??? { (does not exist if value == 2)
   dword ???
}
dword_4 ???

```


Will need some more samples to confirm what they are. Preferably ones that are obvious what they should be (like a weapon or a bag)

btw, can you tell me how to convert the dxt files? I want to texture these lol
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-07-03T16:28:34+00:00
- Post Title: Hero Online MMO

> can you tell me how to convert the dxt files? I want to texture these lol

You can download the tool using this link:
[url]http://www.kz_3d.tvn.hu/N3TexViewer.zip[/url]
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-07-03T16:34:58+00:00
- Post Title: Hero Online MMO

> Hmm after the mesh name there 6 dwords.
>
> The one I wrote up there assumed that the last 2 dwords are the vertNum and faceNum, but for the ones you posted the 3rd seem to be the vertNum and the 4th is the faceNum.
>
> I looked at a couple hero meshes and noticed that 3-4 are the same as 5-6, so perhaps 3-4 are the ones we want.

My problem is the following with the uploaded files:

I can load the vertices correctly, but when I use the face datas (3 x 2bytes_Word) I got a wrong mesh.
I exported these files into Wavefront .obj/mtl formats and I attached a screenshots also.
I am going crazy, because I don't know what is the problem with these files.
[knight_bad_2.zip](https://xentaxbackup.github.io/file/4429_knight_bad_2.zip)
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-04T02:58:05+00:00
- Post Title: Hero Online MMO

I got the same thing. Not sure where the problem could be.
If it's just those files then it probably isn't too big a deal...lol

Thanks for the tex converter. As long as something can work with the files anything is fine.
