## Post #1
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-14T17:34:02+00:00
- Post Title: Alone in the dark .XMG models

hello, i'm trying to get the models from a alone in he dark 2008, a survival horror game. i've extracted the files from fat+big archives using the script by qwerty, model format is XMG and texture format is XMT, now both are very very simple and you can see in a hex editor all coordinates and bone names and texture information and it would be nice to get a script to open them, thanks! 

SAMPLES : 

XMG ' model file ' : [https://www.sendspace.com/file/xpmhmw](https://www.sendspace.com/file/xpmhmw)

XMT ' texture file ' : [https://www.sendspace.com/file/oubfjk](https://www.sendspace.com/file/oubfjk)
## Post #2
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-15T12:56:51+00:00
- Post Title: Alone in the dark .XMG models

those files are from the PC version by the way, bones look like they were simply made as biped is 3dsmax as there are many 3ds max files in the files and biped references in hex. xmt textures are no problem as of now using texture finder but still some graphical errors on top : 


only thing left is XMG model, it would be very appreciated if someone took a look at it. thanks.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-15T20:11:37+00:00
- Post Title: Alone in the dark .XMG models

point cloud of policeman_ragdollbase_4647DAEE90C7AF.xmg  



policeman_ragdollbase_xmg.png (15.64 KiB) Viewed 231 times



the vertex data is big-endian and the face indices are little-endian
so you can't display the results in Hex2obj because there is no option
to set independent endianness on different data types, but this is 
only the second time i've seen this anyway.  

all of the submeshes run together but i don't think you can
read them all into a single array, you must find the table with
start/end info for each.


the image header starts at 0x200 in those xmt files
and the image data starts at 0x1000
0x20c - image width
0x210 - image height
0x21c - image format(?) dxt1 - 0x0B, dxt5 - 0x0F
## Post #4
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-15T20:35:14+00:00
- Post Title: Alone in the dark .XMG models

great thanks for the info Acewell!

found the offsets, though any way to convert them to a readable format ?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-15T22:27:24+00:00
- Post Title: Alone in the dark .XMG models

> Reply from AceWell
>
> the vertex data is big-endian and the face indices are little-endian
so you can't display the results in Hex2obj because there is no option
to set independent endianness on different data types,yeah, I won't support insane developers.  

You can save vertices and FIs independently, though, then combine the resulting test.obj files.

Sadly face culling (F4) doesn't help:



head_cullme.jpg (101.3 KiB) Viewed 209 times
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-16T02:05:08+00:00
- Post Title: Alone in the dark .XMG models

here is Noesis python plugin to open your xmt texture samples  


 tex_AloneInTheDark_PC_xmt.zip
(752 Bytes) Downloaded 24 times


supports dxt1 and dxt5 because those were the only types in the samples



> Reply from shakotay2
>
> yeah, I won't support insane developers.
i hear that   

i started to assemble a python script for Noesis based
on your Hex2obj program with many of the same features
and some additional ones that can get around those crazy
devs, i call it Hex2mesh for now.  

this is what i get for the first submesh
face indices count = 10401
anything more in the array will make stray triangles
## Post #7
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-16T09:35:49+00:00
- Post Title: Alone in the dark .XMG models

thanks! works perfectly on almost all textures :



however...some textures display this error but only SOME textures pretty much everything works fine : 



sample of a texture that displays the error : 

[https://www.sendspace.com/file/felg0r](https://www.sendspace.com/file/felg0r)
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-16T16:56:01+00:00
- Post Title: Alone in the dark .XMG models

okay i updated the texture script in the previous post
## Post #9
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-16T17:23:34+00:00
- Post Title: Alone in the dark .XMG models

Acewell , how do you know texture coordinates like that in hex ? is there a special hex number for width, height, format ? they just look like dots to me...
and do all game texture formats have that "TEXT" header ?
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-16T19:29:38+00:00
- Post Title: Alone in the dark .XMG models

> Reply from Naroax
>
> .. how do you know texture coordinates like that in hex ? is there a special hex number for width, height, format ?
i start by opening the unknown texture in TextureFinder and seeing what the size and format is
then i search that file in a hex editor for where that width and height is stored and compare multiple
files to see if the data is consistent, and set the script to read that data as it it stored.
the formats are usually stored as flags and i just compare the contents of different formats
to determine what the flag is by seeing what changes from one file to the next. 

> and do all game texture formats have that "TEXT" header ?
no it depends on what the developers decide to use, they could put "willywonka" there if they wanted
## Post #11
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-16T19:40:00+00:00
- Post Title: Alone in the dark .XMG models

> no it depends on what the developers decide to use, they could put "willywonka" there if they wanted
 good one

about noesis, it looks like you wrote that python script easily! would you tell me how did you learn noesis scripting ? did you learn python first ? and did you follow chrrox's noesis tutorials ? generally on your personal experience what did you do ?
## Post #12
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-16T21:38:42+00:00
- Post Title: Alone in the dark .XMG models

> Reply from AceWell
>
> 
the vertex data is big-endian and the face indices are little-endian
so you can't display the results in Hex2obj because there is no option
to set independent endianness on different data types, but this is 
only the second time i've seen this anyway.
Damn! Who does that? (guess they do)
## Post #13
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-17T17:29:32+00:00
- Post Title: Alone in the dark .XMG models

any update on xmg anyone ?
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-17T20:06:46+00:00
- Post Title: Alone in the dark .XMG models

this is all i have seen so far   
all data is little-endian except the vertex data

0x10 - pointer to COLL chunk
0x658 - total number of vertices
0x65c - number of submeshes(?)

vertex data table (16 byte blocks * number of submeshes)
0x6b5 - first submesh offset relative from 0x708
0x6b9 - vertex stride for first submesh
0x6c5 - second submesh offset relative from 0x708
0x6c9 - vertex stride for second submesh
0x6d5 - third submesh offset relative from 0x708
0x6d9 - vertex stride for third submesh
0x6e5 - fourth submesh offset relative from 0x708
0x6e9 - vertex stride for fourth submesh 
0x6f5 - fifth submesh offset relative from 0x708
0x6f9 - vertex stride for fifth submesh

0x708 - start big-endian vertex block

0x4de40 - start of face indices table (80 byte blocks * number of submeshes)
0x4de50 - first submesh face count, * 3 to get real count then * 2 to get buffer length
0x4dea0 - second submesh face count, * 3 to get real count then * 2 to get buffer length
0x4def0 - third submesh face count, * 3 to get real count then * 2 to get buffer length
0x4df40 - fourth submesh face count, * 3 to get real count then * 2 to get buffer length
0x4df90 - fifth submesh face count, * 3 to get real count then * 2 to get buffer length

0x4dfd0 - start face indices block





> Reply from Naroax
>
> .. would you tell me how did you learn noesis scripting ?
i started out with something easy like a texture script and i always try to keep it simple,
my only goal is that it works, i don't care how it looks or how fast/slow it is. 
i always recycle working parts of scripts because if it ain't broke don't fix it. 
i'd like to think my scripts are as basic as you can get, so if you are like me
and have no programming experience you can at least do what i do.   

> did you learn python first ? and did you follow chrrox's noesis tutorials ? 
>
> generally on your personal experience what did you do ?
i had to learn a little of both at the same time, 
i read tutorials and posts here on Xentax,
the NPReadMe.txt that came with Noesis,
[http://www.tutorialspoint.com/python](http://www.tutorialspoint.com/python) ,
documentation at [https://docs.python.org/3.2/library/functions.html](https://docs.python.org/3.2/library/functions.html) ,
looked up specific questions on [http://stackoverflow.com/](http://stackoverflow.com/) ,
and looked through scripts made by others to see how stuff was used.
my style is mostly "type it up and hope it works"
