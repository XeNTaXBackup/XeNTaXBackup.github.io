## Post #1
- Username: MCDMaker
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 7:55 pm
- Post datetime: 2012-04-01T12:01:45+00:00
- Post Title: combat arms

.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T12:28:34+00:00
- Post Title: combat arms

Just post some .dat files. If the extractor works there's no need to post a rez archive.
I looked at some .dat files but didn't get anything that looks like vertices.

Am I able to create a map file from scratch using these tools?
For example, a simple cube so I can pin-point exactly what I need.

If so, provide a simple map that you have created yourself (either by taking an existing map and just replacing it with something simple). I imagine if you can mod maps with these tools, you could do something like that?
## Post #3
- Username: MCDMaker
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 7:55 pm
- Post datetime: 2012-04-01T12:38:23+00:00
- Post Title: combat arms

Just added one of the .DAT files for download
[http://www.mediafire.com/?jhb1hmbzlb43m0c](http://www.mediafire.com/?jhb1hmbzlb43m0c)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T13:01:35+00:00
- Post Title: combat arms

I am looking at might and magic 9 models and can see that they use different format (based on the first integer).

Anyways onto the file you posted.
Can you post a render of how that rattlesnake map should look? (either in-game screenshot or something)

This is what I've gotten from hardcoding some offsets and plotting some points.
I went to offset 139997 and just picked out all the floats I saw.



It looks like a part of a room with pillars of sorts. Or perhaps it's a building. I don't know.

So that's basically 1152 vertices. I don't know where the indices are, but the overall structure for format 85 follows a very obvious pattern. It's like

```
a bunch of bytes, for example a whole sheet of 0x03's>
a bunch of floats
a bunch of 4-byte integers, possibly face indices>
a nice section of integers mixed in with a bunch of FFFFFFFFFFF everywhere
more floats, this is where I grabbed the vertex coords from

```


It probably is straightforward.

EDIT: here's an outline for rattlesnake, starting at offset 336

```
   dword ?
   dword null
   dword ?
   word nameLen
   char[nameLen] meshName
   dword numVerts?
   dword unkCount1
   dword[7] more counts and stuff, maybe numIdx is there also
   dword count1?
   float[9] ?
   dword texLens
   dword numTex?
   char[texLens] texture paths
   byte[count1] ??
   numVerts { #well, it's numVerts * 12, so...
       float[3]
   }
   unkCount1 {
      dword[2] #0x41, 0x??
   }
   <indices?>
   ...
}

```
## Post #5
- Username: MCDMaker
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 7:55 pm
- Post datetime: 2012-04-01T13:15:18+00:00
- Post Title: combat arms

Thanks for helping btw!

Rattlesnake is a really big map so its kinda hard to take a print screen of the whole map. But here is a video of it:
[http://www.youtube.com/watch?v=GuI8ngsosis](http://www.youtube.com/watch?v=GuI8ngsosis)

Some print screens: (not mine)


OVERVIEW of the map: [http://images.wikia.com/combatarms/imag ... ESNAKE.jpg](http://images.wikia.com/combatarms/images/5/5c/MAP_RATTLESNAKE.jpg)
Extra screens:
[http://www.coptermonkey.com/rattlesnake.jpg](http://www.coptermonkey.com/rattlesnake.jpg)
[http://i301.photobucket.com/albums/nn42 ... rms_23.jpg](http://i301.photobucket.com/albums/nn42/afooflorlove/Combat-Arms_23.jpg)
[http://i301.photobucket.com/albums/nn42 ... s_15-1.jpg](http://i301.photobucket.com/albums/nn42/afooflorlove/Combat-Arms_15-1.jpg)
[http://i301.photobucket.com/albums/nn42 ... s_19-1.jpg](http://i301.photobucket.com/albums/nn42/afooflorlove/Combat-Arms_19-1.jpg)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T13:22:49+00:00
- Post Title: combat arms

Are there any smaller maps (in terms of filesize) around? For comparison
## Post #7
- Username: MCDMaker
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 7:55 pm
- Post datetime: 2012-04-01T13:30:41+00:00
- Post Title: combat arms

The smallest "file size" of the maps is the map Brushwood.

Download link (.DAT): [http://www.mediafire.com/?g6yv95cuvuvrpas](http://www.mediafire.com/?g6yv95cuvuvrpas)

EDIT: This is how the map looks like, video: [http://www.youtube.com/watch?v=jPy98oU8jts](http://www.youtube.com/watch?v=jPy98oU8jts)

Overview of the map: [http://images.wikia.com/combatarms/imag ... SHWOOD.jpg](http://images.wikia.com/combatarms/images/f/fa/MAP_BRUSHWOOD.jpg)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T15:02:54+00:00
- Post Title: combat arms

The overall structure has been parsed except for two structures, the beginning of the file, and a struct I commented with "unk struct4". For the beginning I simply hardcoded it to skip to the start of the mesh section, starting with the numMesh. The one I hardcoded is for rattlesnake.

If anyone can figure out how to get past that section then we can plot all the points and move on to faces.

Basically, it looks like you have the matNum, followed by some integers for the indices.

However, sometimes you have 3 integers, sometimes you have 4 (tri's vs quads?). I am pretty sure that those are the face indices because if you look at the first integer, it is always less than the number of materials, and the largest integer is one less the numVerts.

The first 5 meshes followed the pattern I wrote down nicely, but then the 6th mesh doesn't follow it anymore (it's off by about 200 bytes?)

[http://db.tt/ogpsoZNY](http://db.tt/ogpsoZNY)

If you want to parse more meshes just go to the parse_file method and change the value to numMesh or something. I only wrote down 5 cause I couldn't get past that.

Brushwood meshes start at offset 211
It can parse up to 23 meshes before I run into an error.
It is because of that unk_struct4...
## Post #9
- Username: MCDMaker
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 7:55 pm
- Post datetime: 2012-04-01T15:09:45+00:00
- Post Title: combat arms

waooooooow

that was way to complicated for me to understand :O
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T15:12:14+00:00
- Post Title: combat arms

Hopefully someone will see something I'm not seeing
## Post #11
- Username: MCDMaker
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 7:55 pm
- Post datetime: 2012-04-01T16:53:11+00:00
- Post Title: combat arms

Ya really hope so
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T18:00:01+00:00
- Post Title: combat arms

Still don't know the unknown struct, but I was comparing it with Might and Magic 9 .dat format and it is very similar except they use different datatypes to store certain values (eg: shorts vs bytes). The only values that matter are those 10 integers defined in the mesh header, and most of them seem to be 0's anyways.

So figuring out one should make it easy to figure out the rest.

EDIT: thinking about it some more...that massive seemingly random section of 3's and 4's might actually be the number of indices per face...if I just add up that number and multiply it by the number of faces maybe I can skip the indices completely!

```
   dword matNum
   dword ?
   dword[n] v1, v2, ..., vn
}

```


So if a face has 3 indices, then that face struct is 20 bytes long. If it has 4 indices, then it's 24 bytes long.
## Post #13
- Username: MCDMaker
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 7:55 pm
- Post datetime: 2012-04-01T18:04:12+00:00
- Post Title: combat arms

ya true, do you think you will be avaible to do it ? :<
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T18:52:37+00:00
- Post Title: combat arms

Alright, got the faces sorted out. Sort of looks like what was shown in the video.



Though, no normals or UV's yet. I ignore everything after the meshes section.
Script updated.

The header is still hardcoded though.

What's really silly is that there are some faces with 8 and 12 vertices. Err......I'm not going to bother drawing those...
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T20:27:28+00:00
- Post Title: combat arms

I have updated the script so just download it again and try running them on some other dat files. If they don't work upload them.

I just need the header though, so just copy paste the first 100 KB or something of the file into a new file (make sure the hex is preserved) and upload those. I want the headers from a really large file, a medium size file, and a small file.

I think I have found some pattern to the headers. I have no idea what they are, and I don't know if you actually want to inject new maps into the game or whatever, but at least I can skip them.

```
   dword version
   float[6] skip
   dword[8] null
   dword len
   char[len] some_info
   float[15] skip
   byte ?
   dword count
   byte[3] ?
   count {
       32 bytes?
   }
   byte[11]
}

```
## Post #16
- Username: spartan00j
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Oct 31, 2010 10:57 am
- Post datetime: 2012-04-22T19:44:07+00:00
- Post Title: Re: combat arms

i love combat arms. where's script download
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-21T18:21:40+00:00
- Post Title: Re: combat arms

If someone sends me all of the textures for one of the maps (along with the map, so just upload rattlesnake textures or something) I might look into the UV's.

Also, the textures MUST be readable. I don't know the seemingly compressed dtx format used for floor/wall/ceiling textures. So if noesis can't load the dtx, then you have to convert it to something else like tga, and verify that noesis CAN load it.
## Post #18
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-06-26T13:32:14+00:00
- Post Title: Re: combat arms

> Reply from finale00
>
> If someone sends me all of the textures for one of the maps (along with the map, so just upload rattlesnake textures or something) I might look into the UV's.

Also, the textures MUST be readable. I don't know the seemingly compressed dtx format used for floor/wall/ceiling textures. So if noesis can't load the dtx, then you have to convert it to something else like tga, and verify that noesis CAN load it.

Aren't the maps brush geometry?
## Post #19
- Username: Mrgunforever
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 16, 2012 2:14 am
- Post datetime: 2012-11-12T18:30:06+00:00
- Post Title: Re: combat arms

> Reply from finale00
>
> If someone sends me all of the textures for one of the maps (along with the map, so just upload rattlesnake textures or something) I might look into the UV's.

Also, the textures MUST be readable. I don't know the seemingly compressed dtx format used for floor/wall/ceiling textures. So if noesis can't load the dtx, then you have to convert it to something else like tga, and verify that noesis CAN load it.

Ok, I got something for you : I have all the textures of the map, but in DTX format, the problem is that they are all together, all maps. There is not a folder separate for rattlesnake or warhead... But, the only thing that is 100% from rattlesnake is the sky which comes in a separate folder in order to make difference in the sky between the maps. 
Just tell me and I'll start converting every texture for you. It weighs a bit more than 300mb...
