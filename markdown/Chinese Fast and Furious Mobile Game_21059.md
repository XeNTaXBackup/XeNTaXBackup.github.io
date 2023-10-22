## Post #1
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2019-09-01T12:01:22+00:00
- Post Title: Chinese Fast and Furious Mobile Game

Hey Guys,

i found this Chinese the Fast and the Furious Mobile Game

[http://www.9game.cn/sdyjq8/](http://www.9game.cn/sdyjq8/)

the carlist is pretty common these days but unbranded - rocketbunny brz, shaws f-type, lettys corvette c2, rallyfighter - but they do have the ripsaw ev2, they also do have some characters in the game (letty, tej, roman, hobbs and shaw)

[https://imgur.com/a/nA1j9fx](https://imgur.com/a/nA1j9fx)

i was able to get the ripsaw using ninja ripper and nox, but sadly the characters are not in t-pose

[http://www.mediafire.com/file/oj79x9ybw ... 6.rar/file](http://www.mediafire.com/file/oj79x9ybwfxp01e/Fast8_1.3.6.rar/file)

the game is using ucgamesdk - unity? but using other files

*.zc files seems to be the meta file to find everything
*.zda files are animations
*.zdo files are meshes
*.zdp files are textures

i was not able to get something usefull out of it, maybe someone of you could take a look

cheers!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-01T13:03:23+00:00
- Post Title: Chinese Fast and Furious Mobile Game

using hex2obj (view link in my sig):
.



wheel-zdo.png (108.47 KiB) Viewed 283 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-01T13:16:09+00:00
- Post Title: Chinese Fast and Furious Mobile Game

ferrari458.png (109.42 KiB) Viewed 281 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-01T13:34:27+00:00
- Post Title: Chinese Fast and Furious Mobile Game

interior:
.



ferrari458_interior.png (85.22 KiB) Viewed 281 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-01T14:43:14+00:00
- Post Title: Chinese Fast and Furious Mobile Game

letty:
.



letty.png (122.2 KiB) Viewed 275 times



H2O file of her hair:

0x19D74 2039
Vb1
12 99
0x16344 532
020100
0x188AC 4
## Post #6
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2019-09-02T19:05:05+00:00
- Post Title: Chinese Fast and Furious Mobile Game

Guki, can you make a car list for this game?  
I wonder if there's something interesting
## Post #7
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2019-09-02T22:44:05+00:00
- Post Title: Chinese Fast and Furious Mobile Game

thank you shakotay2! you are awesome

but i got a few issues
the link in your signature doesn't work for me, because zippyshare blocked germany.
i was able to download version 0.24d and 0.24e somewhere else but on both versions wordpad.exe, the glut32.dll and mesh_viewer.exe are missing. 
i copied wordpad.exe from windows - found the glut32.dll online - but where do i find the meshviewer?

anyway

i can find the face indices start of each mesh, i can find the vertices start, but i still struggle to find the uv start.
also, the tool somehow disables some options, like in your screenshots i set step 2 to vertex block - but this disables go3?


@amg

the car list is not licensed,
audi r8, bentley continental ss, bugatti veyron, chevrolet camaro, chevrolet corvette c2, dodge challenger, ferrari 458, ferarri enzo, gumpert apollo, hobbs armored vehicle mxt, jaguar f-type, koenigsegg ccx, lamborghini murcielago, local motors rallyfighter, mclaren f1, mclaren p1, mercedes amg sls, nissan gtr r35 bensopra, pagani huayra, porsche 911 gt, plymouth cuda, plymouth gtx, ripsaw ev2, subaru brz rocketbunny, wmotors lykan hypersport
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-03T16:42:07+00:00
- Post Title: Chinese Fast and Furious Mobile Game

> Reply from guki ↑Tue Sep 03, 2019 6:44 am at Tue Sep 03, 2019 6:44 am
>
> the link in your signature doesn't work for me, because zippyshare blocked germany.thanks for reporting! I added an uploadMB link with version 0.24e, all dlls and exes contained.

> but i still struggle to find the uv start.yeah, that's the only reason why you still do need me, do you? 
uvaddress= vertexstart + vertexcount x 18
(works for the few models I've checked)

> also, the tool somehow disables some options, like in your screenshots i set step 2 to vertex block - but this disables go3?yep, an "inner" logic, go3 is reserved for sequential mode, afair.

(There might be a "greyed out" bug for the start uvb editbox, which you can solve by pressing the VB button twice.)
## Post #9
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2019-09-03T20:15:46+00:00
- Post Title: Chinese Fast and Furious Mobile Game

> Reply from shakotay2 ↑Wed Sep 04, 2019 12:42 am at Wed Sep 04, 2019 12:42 am
>
> 
...

thanks for uploading the tool again and thanks for the uv adress this works like a charm 
i "fixed" the go3 "bug" opening a file, switch to vb and reopen the same file


for anyone else who is interested - maybe this file format is used in other games too
the textures are saved as zbp, hex edit the file remove the first digits to bpg
then use this tool to convert bpg to png or jpg
[http://www.romeolight.com/products/bpgconv/](http://www.romeolight.com/products/bpgconv/)
## Post #10
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2019-09-22T11:37:11+00:00
- Post Title: Chinese Fast and Furious Mobile Game

Thank you for your post about the bpgconv application.

I have added the Fast and Furious 8 .zbp to Better Portable Graphics .bpg converter to the 'Tools/Texture converters...' module and the Fast and Furious 8 .zdo loader module to the 3D Object Converter v7.010 and I have released the 3D Object Converter v7.010 as a web update.

How to get the 3D Object Converter v7.010:
Download the 3D Object Converter from [http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.

After it just use the Help/Check for updates... function to get the v7.010.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-18T15:11:35+00:00
- Post Title: Chinese Fast and Furious Mobile Game

well, well, some necro "update" for bmw_m2.zdo:
.



bmw_m2-zdo.png (91.16 KiB) Viewed 107 times


(2nd sub mesh)

Remember for the uv start address (see some posts above):
uvaddress= vertexstart + vertexcount x 18
(works for the few models I've checked)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-18T19:22:32+00:00
- Post Title: Chinese Fast and Furious Mobile Game

All 3 sub meshes:
.



bmw_m2.png (248.6 KiB) Viewed 95 times



H2O files, 1st sub mesh:

0x272A8 24792
Vb1
12 99
0x708 4957
020100
0x1B106 4

and window screens:

0x68B44 522
Vb1
12 99
0x67C2C 138
020100
0x682A4 6
## Post #13
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-09-04T17:27:54+00:00
- Post Title: Chinese Fast and Furious Mobile Game

I have updated the .zdo loader module in the following programs:

- 3D Object Converter v8.011	(Windows)
- i3DConverter v4.101		(macOS)
- i3DConverter v2.101		(Linux)

How to get the 3D Object Converter v8.011:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v8.011.

How to get the i3DConverter macOS v4.101:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v4.101.

How to get the i3DConverter Linux v2.101:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v2.101.
