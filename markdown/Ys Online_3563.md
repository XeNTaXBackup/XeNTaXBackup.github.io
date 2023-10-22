## Post #1
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2009-07-01T20:56:27+00:00
- Post Title: Ys Online

Hiya!

Recently, a new MMORPG has entered open beta: [Ys Online](http://www.ysonline.com/).

I think the 3D models are inside the XAC/XSM format. A quick search on google showed that some sim city game also uses an XAC format, but I didn't find any suitable viewer to try out. Maybe someone else can help out.

I uploaded a sample of some XAC/XSM files extracted from the data files here:
[http://www.filefactory.com/file/ahah01b/n/xac_xsm_zip](http://www.filefactory.com/file/ahah01b/n/xac_xsm_zip) 
There's also a Total Commander plugin to unpack the *.yfm files inside to extract all the other data as well.

Would be nice to know if anyone has ever encountered a viewer for those file types.

-Darkstar
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-08-08T12:25:19+00:00
- Post Title: Ys Online

I didn't look deep into the format but the basic format are CHUNK based like:

```
dword   ResVersion  // 1.0.0.1 ??
struct YSOChunk {
   dword    ChunkID             
   dword    ofsDataSize         
   dword    ChunkVersion    
   <data>
}
```


XSM is animation file and XAC is mesh!

chunk id 0 is node chunk; contains coordinate and name(maybe more) data.
chunk id 1 is geometry chunk
chunk id 8 is contains another XAC files
chunk id 0xC8 is animation data chunk
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2013-11-14T01:03:37+00:00
- Post Title: Ys Online

Finally i found the client installer, but the format its .ysf, so far anyone can writhe please .BMS to unpack the data?. I cant found a unpacker in the net.
