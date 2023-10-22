## Post #1
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2007-11-01T16:09:55+00:00
- Post Title: Tianji model file ^^

Here is model file from Tianji game (tj.ferrygame.com)
Believed that format is modified from mdx and m2 of WoW, someone pls help me figure out their format 
[http://www.bibabibo.net/yishou.zip](http://www.bibabibo.net/yishou.zip)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-11-05T18:00:18+00:00
- Post Title: Tianji model file ^^

warcraft & WOW models are tag based. So they are very easy to understand! I spent ten minutes to come up with these:

```
char[4]     tag
dword       tagLength
<data>

```


The geometry data was in "geom" tag. and each geometry(3d model) could have many "chks"(chunks/parts).

```
char[4]     tag              //"chks"
dword       tagLength
dword       nVerts
dword       nFaces
dword       nMaterialIndex
struct Vert {
float X 3   pointXYZ
} Vert[nVerts]
struct Normal {
float X 3   pointXYZ
} Normal[nVerts]
struct UV {
float X 2   textureUV
} UV[nVerts]
struct BoneVert {
dword       boneIndex
} BoneVert[nVerts]
struct Face {
word X 3   faceIndex
} Face [nFaces]
...
another tag
...

```
## Post #3
- Username: CakeIsALie
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 05, 2007 4:04 am
- Post datetime: 2008-04-15T17:47:20+00:00
- Post Title: Tianji model file ^^

Thanks for this!
This helped me too.

Lol 666 posts
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2008-04-21T14:59:35+00:00
- Post Title: Tianji model file ^^

CakeIsALie,

Did you read the PM I sent to you 2 days ago ?
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2008-04-25T17:41:57+00:00
- Post Title: Tianji model file ^^

CakeIsALie,

Did you see this little gallery ?

[http://web.t-online.hu/karpo/gallery_tianji_online.html](http://web.t-online.hu/karpo/gallery_tianji_online.html)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-12T01:19:56+00:00
- Post Title: Tianji model file ^^

These models are pretty nice 

But it looks like the words are mirrored again.
There is something inherently wrong with how I am parsing the files cause all of my words are constantly mirrored! Though I guess I can just flip the x-value for the coordinate to mirror the model.

It seems like there are more meshes than there are materials too.
[tianjiHouse.jpg](https://xentaxbackup.github.io/file/4614_tianjiHouse.jpg)
