## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-14T00:53:24+00:00
- Post Title: XT Online (仙途 Online)

Hello guys, well with small help of Ekey aka Hax0r I unpack the game, I get a lot files, I leave here a small info about this files.
MDL= Mesh
DDS= Texture
FMV= Animations
[https://www.dropbox.com/s/h61i2369wm9wb ... 0Online.7z](https://www.dropbox.com/s/h61i2369wm9wbys/XT%20Online.7z)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-03-14T20:47:42+00:00
- Post Title: XT Online (仙途 Online)

The model format is something like this:

```
  char[4]       Game_ID
  dword         Version
  char[4]       Resourse_ID
  word          Object_Type
  word          ?
)

struct ObjectInfo (
  dword         ofs_Material
  dword         Size_Material_Block
  dword         ofs_Unknown
  dword         Size_Unknown_Block
  dword         ofs_Mesh_Info
  dword         Size_Mesh_Info_Block
  dword         ofs_Vertices
  dword         Size_Vertices_Block
  dword         ofs_Faces
  dword         Size_Faces_Block
  *dword        ofs_DUMMY               //Type 2 only
  *dword        Size_DUMMY_Block
  ...
)

Struct Vertex (
 float[3]       Coordinate_XYZ
 float[3]       Normal_XYZ
 float[2]       Texture_UV
)

struct Face {
 word[3]        Index_XYZ
}
```
## Post #3
- Username: peto1488
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Jan 28, 2012 7:26 am
- Post datetime: 2014-03-18T19:02:50+00:00
- Post Title: XT Online (仙途 Online)

and download client or link on website?
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-18T21:04:18+00:00
- Post Title: XT Online (仙途 Online)

> Reply from peto1488
>
> and download client or link on website?I put original name in chinese, why don't copy it and paste in google? maybe you got something   

[http://xt.ztgame.com/](http://xt.ztgame.com/)
## Post #5
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2014-03-18T21:05:18+00:00
- Post Title: XT Online (仙途 Online)

[http://xt.ztgame.com/download/index.shtml](http://xt.ztgame.com/download/index.shtml)
## Post #6
- Username: peto1488
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Jan 28, 2012 7:26 am
- Post datetime: 2014-03-19T17:10:06+00:00
- Post Title: XT Online (仙途 Online)

thank you Modman69

ps:
not really?...xt online,xt online game and other XT
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-19T18:04:38+00:00
- Post Title: XT Online (仙途 Online)

yah sure -.-
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-03-19T18:15:35+00:00
- Post Title: XT Online (仙途 Online)

Google results are personalized.
You need to search "仙途 Online"
## Post #9
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2014-03-22T09:21:55+00:00
- Post Title: XT Online (仙途 Online)

CriticalError,how to unpack it,do you have the BMS script
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-22T13:10:12+00:00
- Post Title: XT Online (仙途 Online)

> Reply from glcat
>
> CriticalError,how to unpack it,do you have the BMS script
yes I have bms script.
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-22T14:00:10+00:00
- Post Title: XT Online (仙途 Online)

> Reply from glcat
>
> CriticalError,how to unpack it,do you have the BMS script
[here](http://forum.xentax.com/viewtopic.php?p=89598#p89598)
## Post #12
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2014-03-24T05:13:00+00:00
- Post Title: XT Online (仙途 Online)

> Reply from Ekey
>
> glcat wrote:CriticalError,how to unpack it,do you have the BMS script 
here

thank，Ekey
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-05-04T02:22:03+00:00
- Post Title: XT Online (仙途 Online)

bump, nobody can provide some help apart of fatduck?
