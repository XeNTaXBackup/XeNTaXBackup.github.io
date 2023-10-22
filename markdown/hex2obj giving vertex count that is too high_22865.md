## Post #1
- Username: kgal104
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 20, 2020 3:38 am
- Post datetime: 2020-10-19T21:42:51+00:00
- Post Title: hex2obj giving vertex count that is too high?

So I have been successfully extracting multiple models from pinshape and their .bingeom files. However, I have one file I cant seem to properly extract. It is the first file on this page: [https://pinshape.com/items/55281-3d-pri ... ns-upgrade](https://pinshape.com/items/55281-3d-printed-gameboy-advance-sp-custom-shell-l-r-buttons-upgrade) which gives the following hex file: [https://cdn.threehub.com/resources/9ae4 ... e1.bingeom](https://cdn.threehub.com/resources/9ae4e9098dfe3b50e17e615b17462d4fz?filename=1617339-eb58cee3d0705b63fc1934cc26a39f569b0a1ae1.bingeom)
However, running this through hex2obj using the method that has worked thus far gives the following result

The vertex count is clearly too high, but I cannot seem to determine why that is. Any help on this would be appreciated.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-10-21T18:41:11+00:00
- Post Title: hex2obj giving vertex count that is too high?

Hi kgal104,

the face indices are bytes for the file you posted which hex2obj doesn't support. (maximum face index=182 -> vertexcount )

You may try out the tools from Bigchillghost or Lazov which should have that option.

Here*s the obj file with "manually" created  face indices:
.


 test_bingeom.zip
(2.88 KiB) Downloaded 17 times
## Post #3
- Username: thes33k3r
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2018 2:57 am
- Post datetime: 2021-01-22T14:01:43+00:00
- Post Title: hex2obj giving vertex count that is too high?

I'm having the exact same issue. I tried applying what little I knew about hex2obj to 3d model researcher and advanced mesh reaper to try to learn how tey operate and maybe then progress to this newer version of the bigeom files, but I'm not there yet. Can anyone point in the right direction? How to use any of these utilities to extract the 3d model? Either version of the bigeom files would be greatly appreciated.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-22T19:14:08+00:00
- Post Title: hex2obj giving vertex count that is too high?

bingeom from the opening post in AMR:
.



byte-face-indices-in-AMR.png (88.56 KiB) Viewed 128 times


(You'll need  ViewScene.exe and dlls to be put in AMR.exe folder to display the mesh using the "Proceed" button.)
## Post #5
- Username: thes33k3r
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2018 2:57 am
- Post datetime: 2021-01-23T00:41:13+00:00
- Post Title: hex2obj giving vertex count that is too high?

Thank you so much, it seems that I finally wrapped my head around this ( or at least I like to think so). I applied your new information and I correctly opened the above file, next I went to other targets namely the ones that I used to open with hex2obj. With these I had to do the following:

Example file
[https://cdn.threehub.com/resources/1b13 ... fd.bingeom](https://cdn.threehub.com/resources/1b138b5f56df328c50a32be786cf3442z?filename=772687-0c2cdfda3ce61b097b72aa10935303fd882efbfd.bingeom)

subtract 4 from the address, divide it by 2, convert to decimal and set the data type = uint16



1b.png (76.61 KiB) Viewed 118 times
## Post #6
- Username: thes33k3r
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2018 2:57 am
- Post datetime: 2021-01-23T00:45:08+00:00
- Post Title: hex2obj giving vertex count that is too high?

The interesting thing is that I found another variation. It seems that depending on the filesize there are difference on how they are saved:

Example file
[https://cdn.threehub.com/resources/2a49 ... ae.bingeom](https://cdn.threehub.com/resources/2a4951f2c7c8c4564e2d261376089b39z?filename=772690-4d4f8ffdf07d758495057087592e6459f5a342ae.bingeom)

subtract 4 from the address, divide it by 4, convert to decimal and set the data type = int32



2a.png (76.09 KiB) Viewed 118 times
## Post #7
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-01-23T01:20:33+00:00
- Post Title: hex2obj giving vertex count that is too high?

Some more info: if you look at the end of the file, there is some text info that tells you how the data is stored.  So in the attachment in the first post, you have this:

{"type":"PolyMesh","faces":{"o":0,"l":1092,"b":1},"faceCount":{"o":1092,"l":4},"positions":{"o":1096,"l":2184},"colorMaps":{},"uvMaps":{},"blendShapes":{}} 

It tells you that the faces start at 0, 1092 entries, size is 1 byte per entry, etc. - "o" is the start offset and "l" is the length in bytes, "b" is the size of each entry.

The very end of the file gives you the size of this text data, so you can go back that amount of bytes to get the start of it.
## Post #8
- Username: thes33k3r
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2018 2:57 am
- Post datetime: 2021-01-23T01:58:37+00:00
- Post Title: hex2obj giving vertex count that is too high?

Doh! Prime example of being so fixed in the details that one misses the solution right in front of you. Well at least now I'm a little more familiar with these things, live and learn.
It shouldn't be too hard to code a script for noesis and automate this all process.
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-01-23T03:13:19+00:00
- Post Title: hex2obj giving vertex count that is too high?

Here's an initial basic Noesis script that should read the vertices and faces correctly from the text info supplied in the file.

You'll need to rename the files as *.bingeom for the script to work.
[fmt_pinshape.zip](https://xentaxbackup.github.io/file/19371_fmt_pinshape.zip)
## Post #10
- Username: thes33k3r
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2018 2:57 am
- Post datetime: 2021-01-23T09:10:14+00:00
- Post Title: hex2obj giving vertex count that is too high?

Works perfectly  
Probably the first time that I opened a noesis script and could actually understand what it was doing just by reading it all.
