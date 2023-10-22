## Post #1
- Username: product
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Jun 14, 2006 4:08 am
- Post datetime: 2007-07-03T03:50:56+00:00
- Post Title: Fire Pro Returns.. .ROM

OK, as best i can tell, all the textures are going to be inside FPR.ROM (740 MB) as other then that there are only a couple of .IRX files (all under 1MB).. is this file type supported by multiex and i've just missed it? or is it something you guys could look into? I'd love to get inside the game and see what there is in there...
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-03T05:46:48+00:00
- Post Title: Fire Pro Returns.. .ROM

Well, it's not supported yet. If you could cut up the 740 MB file into pieces of 512 KB- 1 MB using the filecutter, we might be able to take a look at it.
## Post #3
- Username: product
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Jun 14, 2006 4:08 am
- Post datetime: 2007-07-06T05:26:09+00:00
- Post Title: Fire Pro Returns.. .ROM

ok, as the .rom archive was quite possibly going to be a lot of hassle at the size it was i was wondering if you could possibly take a look at this .bin from king of colloseum green? this was something else i was thinking about anyway, so it's probably makes more sense to go with this considrng he file sizes.

11mb RAR archive cotaining 20mb BIN:
[http://www.hostmyfile.co.uk/?code=73c23 ... 2647db80b4](http://www.hostmyfile.co.uk/?code=73c23b0065b5e726627e2d2647db80b4)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-07T21:13:39+00:00
- Post Title: Fire Pro Returns.. .ROM

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: product
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Jun 14, 2006 4:08 am
- Post datetime: 2007-07-07T22:36:40+00:00
- Post Title: Fire Pro Returns.. .ROM

It downloaded fine for me, but i've had similar issues with file hosts before. hpe this one wrks a little better.

[http://www.megaupload.com/?d=Z6SQT7GQ](http://www.megaupload.com/?d=Z6SQT7GQ)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-08T00:03:31+00:00
- Post Title: Fire Pro Returns.. .ROM

Okay, good, now I got the file. 

This is it: 

```
Get FileNum Long 0 ;
Set Start Long FileNum ;
Math Start *= 16 ;
Math Start /= Padding ;
Math Start += 1 ;
Math Start *= Padding ;
Set FN String "file" ;
Set EXT String ".bin" ;
Set Count Long 0 ;
For T = 1 To FileNum ;
Get ROff Long 0 ;
Math ROff += Start ;
Get FSizeP Long 0 ;
Get FSize Long 0 ;
Get U Long 0 ;
Set FName String FN ;
String FName += Count ;
String FName += EXT ;
Log FName ROff FSize 0 0 ;
Math Count += 1 ;
Next T ;
 
```


The archive is padded in 2048 bytes blocks. The script will take heed of the padding size and then extract all of the files. There are no filenames, so I've just made them have a name like "file0.bin" "file1.bin" etc. 
It's up to you to see what they represent. 

Cheers.
## Post #7
- Username: product
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Jun 14, 2006 4:08 am
- Post datetime: 2007-07-09T01:21:10+00:00
- Post Title: Fire Pro Returns.. .ROM

thaks for the help mate, it's gonna take me a while to figure out what's what, but it's easilly done, but time consuming lol.
