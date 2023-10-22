## Post #1
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2014-11-26T03:18:05+00:00
- Post Title: Legend of Dragoon model extraction

Hi guys,
 This is avery old game since 2000, but i really love it, i hope someone can help me extract the model from this game.
I have followed this post and use aluigi bms script to extract the bin file, then i go many dat , cl5, and mrg files.
[viewtopic.php?f=10&t=6276](http://forum.xentax.com/viewtopic.php?f=10&t=6276)

 Here a sameple of mrg file, hope someone can help me with this.
 Really thanks.

[https://www.dropbox.com/s/o94djm8d5fq85 ... b.mrg?dl=0](https://www.dropbox.com/s/o94djm8d5fq85e5/0000000b.mrg?dl=0)
## Post #2
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2014-11-30T16:20:11+00:00
- Post Title: Legend of Dragoon model extraction

Can anyone help me with this game? @@
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-30T17:56:21+00:00
- Post Title: Legend of Dragoon model extraction

Couldn't find face indices in your uploaded mrg file nor a decent point cloud.
Also the last 69% of the file are filled with zeroes.
Guess this is not a model file.
## Post #4
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2014-12-02T13:39:24+00:00
- Post Title: Legend of Dragoon model extraction

Thanks for ur reply,
 I dont know, that is the most big files among those i have extracted, ill upload the iso of disk image. Hope you can spare some time for take a look when u have time.
[https://www.dropbox.com/s/0t1ju8rlp79o4 ... 1.rar?dl=0](https://www.dropbox.com/s/0t1ju8rlp79o4wq/Legend%20of%20Dragoon%20disk%201.rar?dl=0)

 Really thanks
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-02T15:32:18+00:00
- Post Title: Legend of Dragoon model extraction

when I try aluigi's script I get this error:

```
--------------------------------------

- signature of 4 bytes at offset 0x00000000 doesn't match the one
  expected by the script:

  this one: ""
  00 ff ff ff                                       ....

  expected: "MRG→"
  4d 52 47 1a                                       MRG.

- 0 files found in 0 seconds
  coverage file 0     0%   4          484951824

Press RETURN to quit
```


There are 7276 occurences of 4d 52 47 1a in the bin file
but I don't have the time to fiddle around with this.
(I will try it with the first section cut off 'til the first pattern occurence)

well, told me again: "0 files found"

edit: ok, had to cut off the first two sections:


```
--------------------------------------
  0000f000 26832      00000000.dat
  00016000 34848      00000001.dat
  0001f000 7156       00000002.dat
  00021000 14296      00000003.dat
  ...
  00422000 6976       000000fd.dat
  00424000 27856      000000fe.dat
  396e0800 3108859441 000000ff.dat

Error: incomplete input file number 0, can't read 64 bytes.
```


But it's only .dat files and it's very tedious to proceed in that way, so:
how did you extract that bin?
## Post #6
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2014-12-02T15:59:03+00:00
- Post Title: Legend of Dragoon model extraction

Hi,
 I use QuickBMS 0.5.28 and it work with no problem.
[https://www.dropbox.com/s/3aak23tyggu2p ... 9.png?dl=0](https://www.dropbox.com/s/3aak23tyggu2ph3/SNAG-0269.png?dl=0)
 Ill try compress all files and upload to dropbox.
  Thanks
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-02T16:10:22+00:00
- Post Title: Legend of Dragoon model extraction

hmm, I'm using qickbms 0.6, strange
Is this the bms script you're using?

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "MRG\x1a"
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    math OFFSET *= 0x800
    log "" OFFSET SIZE
next i
```


You don't need to upload all 7611 files  (which seem to be of type .dat only?)
I've got some .dats as you can see from my previous post, would need the biggest one only.

Also 3 to 5 of each other type would be nice, varying in sizes
## Post #8
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2014-12-03T01:31:23+00:00
- Post Title: Legend of Dragoon model extraction

Yes im using the same script.
 btw im already uploaded some files here, there are 5 file type, mcq, mrq, dat, cl5, and tes .
[https://www.dropbox.com/s/5ny1vujkggo7b ... s.rar?dl=0](https://www.dropbox.com/s/5ny1vujkggo7b0t/files.rar?dl=0)
 Pls take a look.
 Thank you
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-03T21:24:42+00:00
- Post Title: Legend of Dragoon model extraction

well, on a review of these files I sadly found near to nothing:

mrgs might contain textures:



mrg.JPG (92.14 KiB) Viewed 137 times


For .dats and .mcq the result was the same as before:

> Couldn't find face indices in your uploaded files nor a decent point cloud.
## Post #10
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2014-12-04T00:06:03+00:00
- Post Title: Legend of Dragoon model extraction

Oh i see.
 Thanks for your help anyways, you re really kind ^^
## Post #11
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2014-12-04T12:23:14+00:00
- Post Title: Legend of Dragoon model extraction

How do you recognize a "point cloud"? Maybe I can help here... Not to find the format, but in finding a useful file.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-04T16:44:30+00:00
- Post Title: Legend of Dragoon model extraction

> Reply from CheloXL
>
> How do you recognize a "point cloud"? Maybe I can help here... Not to find the format, but in finding a useful file.That's a kind suggestion but it's not too easy. In the end you won't get a point cloud without knowing the format.
The endian is little endian for PC and PS files, big endian for console games (for XBOX for example).

Face indices start and count are not required
but you need to know where the vertices reside in the file
and whether they are floats, half floats or (signed) shorts.

For floats it's rather simple because they have characteristic patterns (containing 3E,3F..45, 80)
but for half floats and shorts it's more difficult.

You just have to try out different formats and start addresses.
As vertex count a value of 100 or 500 makes sense.
Then press the 'mesh' button in hex2obj with PtCld button active.

If 'vertex block mode' is used instead of "sequential" it's even harder because you've got another paramter to vary.

good luck.

example point cloud of another game:



wsx-PointClouds.JPG (29.82 KiB) Viewed 119 times
