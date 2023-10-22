## Post #1
- Username: Rkpaarsa
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 20, 2018 11:58 pm
- Post datetime: 2020-06-05T19:32:06+00:00
- Post Title: How To create .PALN Image

Hey everyone 
I need some help about a graphic or maybe an image format called  .PALN  the file is from a game called Freedom fighter i was able to view the PALN images using Dragon Unpacker 5 and it also converts the PALN image to TGA With Alpha and without alpha, what im saying is how to make PALN File Here are some PALN File. 
Please look at them at least for once cause i need it very much. 
thanks and sorry for my bad English.


PALN FILE Samples 

[https://mega.nz/file/LeIQxaKZ#Do8nduybq ... XUbr__KSl0](https://mega.nz/file/LeIQxaKZ#Do8nduybqWCJzCdjHEfE-aNInXm5DbND_XUbr__KSl0)
[Capture.JPG](https://xentaxbackup.github.io/file/18274_Capture.JPG)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-22T16:14:14+00:00
- Post Title: How To create .PALN Image

This is the structure of the files.

```
long64	Sig // "PALNPALN"
long	fileID
short	width
short	height
long	unknown1 // 1
long64	Null
long	unknown2
string	fileName
long	pixelSize
byte	pixelIndices[pixelSize]
long	paletteNum
byte	palette[paletteNum][4]

```

There're still some unknown fields (unknown1, unknown2) which might be significant to the format. It's not possible to produce a PALN file without known how these unclear fields are generated. Buf if you simply want to replace the images there might be a way.
## Post #3
- Username: Rkpaarsa
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 20, 2018 11:58 pm
- Post datetime: 2020-08-16T03:36:28+00:00
- Post Title: How To create .PALN Image

> Reply from Bigchillghost ↑Tue Jun 23, 2020 12:14 am at Tue Jun 23, 2020 12:14 am
>
> 
This is the structure of the files.
Code: Select alllong	fileSize
long64	Sig // "PALNPALN"
long	fileID
short	width
short	height
long	unknown1 // 1
long64	Null
long	unknown2
string	fileName
long	pixelSize
byte	pixelIndices[pixelSize]
long	paletteNum
byte	palette[paletteNum][4]

There're still some unknown fields (unknown1, unknown2) which might be significant to the format. It's not possible to produce a PALN file without known how these unclear fields are generated. Buf if you simply want to replace the images there might be a way.

I just want to replace image. 
How can I do that?
Any idea
