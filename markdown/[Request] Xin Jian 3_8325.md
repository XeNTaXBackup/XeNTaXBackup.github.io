## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T04:03:48+00:00
- Post Title: [Request] Xin Jian 3

Ok guys with script of bms I unpack the files and well this is what I get, all uknown formats, so maybe somebody can take a look into this files.

[Xin Jian 3](http://jx3.xoyo.com/)
[Client](http://jx3.client.cdn.kingsoft.com/JXOnline3-v2.2.1.3619/JXOnline3-v2.2.1.3619.rar)

[Xin Jian 3 2D-3D Samples](http://www.mediafire.com/download.php?lrabdzrynyqriig)
## Post #2
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-18T06:13:31+00:00
- Post Title: [Request] Xin Jian 3

Headers show alot of .dds, riff, id3 ([www.cyberweaver.net](http://www.cyberweaver.net)), KSword3D for the models, LTAM - material file.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T06:18:09+00:00
- Post Title: [Request] Xin Jian 3

Ya, the files aren't too useful until we can get filenames.
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T06:23:46+00:00
- Post Title: [Request] Xin Jian 3

so I download 8GB for nothing xX, damn I sicked.
## Post #5
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-18T06:35:44+00:00
- Post Title: [Request] Xin Jian 3

Nah, you script needs changing to output the names based on the first 3 chars in the file. 
.eek for headers with 0 0 0  
Just use windows search for files containing dds, riff, KSword3D, then cut and paste to new folders, then go to dos, navigate to folders then  rename *.* *.whatever

edit. be careful, it lists some >2mb files as dds when they isn't.
edit 2. the ksword3d models look static - very simple, vertices 3 floats, normals 3 floats, UV 2 floats + 1 long, triangle strips?
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T06:39:22+00:00
- Post Title: [Request] Xin Jian 3

The script is long and confusing with chunks and offsets everywhere!
## Post #7
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-18T20:00:49+00:00
- Post Title: [Request] Xin Jian 3

Wasn't even triangle strips, just lots of reused vertices.
Pity the materials are in separate files.


I renamed the models .ksw for now and atempted a noesis plugin.
[http://pastebin.com/SpgtS0Qa](http://pastebin.com/SpgtS0Qa)
## Post #8
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2019-10-17T04:18:00+00:00
- Post Title: [Request] Xin Jian 3

> Reply from Ninja ↑Sun Feb 19, 2012 4:00 am at Sun Feb 19, 2012 4:00 am
>
> 
Wasn't even triangle strips, just lots of reused vertices.
Pity the materials are in separate files.


I renamed the models .ksw for now and atempted a noesis plugin.
http://pastebin.com/SpgtS0Qa

Hi Ninja, I added the bone parsing part in addition to your script. However, I am in trouble with the bone weights part since I could not understand the example of this part in Noesis. Hoping that you or anyone could help a hand. Thanks.
The structure of bone part is below:

```
char bone-name 30 bytes
char parent-bone-name 30 bytes
int number of child bones 4 bytes
char child-bone-name[] 30 bytes
float transform-matrix[4][4] 64 bytes //need to be inversed
int number of vertex connected to this bone 4 bytes 
int vertex id[] 4 bytes 
float weight[] 4 bytes // weighting information corresponding to vertex id
//final 252 bytes 
int unk4 4 bytes
char unk5 30 bytes
float matrix[4][4] 64 bytes
char unk6 30 bytes
float matrix[4][4] 64 bytes
4 bytes end
```


Here is the customzized script:
[https://pastebin.com/vTbzXe8A](https://pastebin.com/vTbzXe8A)

And a model file:
[https://drive.google.com/open?id=14G-9x ... 5HGQDnnPoB](https://drive.google.com/open?id=14G-9xR_QSdagUPpa5hV7VF5HGQDnnPoB)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-17T20:30:25+00:00
- Post Title: [Request] Xin Jian 3

yeah, another brave hearted rider of dead horses - welcome to the club!  

See, you're dealing with NoeFlatWeights()? Your  base is example_bonemaps.py from MrAdults, I guess?
To be honest: always wondered how to get this working, but didn't find a noepy model sample.
(Idea was to use the def noepyWriteModel(mdl, bs), but guess it requires such model to be loaded before?)

Seems the weights are not bound to the model somehow.
Your lists look ok, afaiks:
(boneID, boneName, w_addr, vertexcount, vids[])

```
12 Bip01 R Foot 0x933c 56 [131, 132, 133, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 150, 151, 152, 153, 154, 155, 158, 161, 163, 174, 175, 231, 232, 233, 234, 235, 253, 433, 434, 435, 437, 440, 441, 444, 445, 446, 447, 448, 452, 453, 454, 455, 456, 457, 458, 459, 460, 461, 462, 463, 467, 468, 469]
13 Bip01 L Toe0 0x952e 12 [176, 188, 192, 193, 238, 240, 241, 483, 484, 486, 489, 491]
14 Bip01 L Foot 0x9720 56 [177, 178, 179, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 202, 206, 207, 208, 209, 211, 237, 239, 242, 243, 244, 245, 255, 256, 480, 481, 482, 485, 487, 488, 490, 492, 493, 494, 495, 498, 499, 500, 501, 502, 503, 504, 505, 506, 507, 508, 509, 513, 514, 515]
```


When exporting to dae there's no such line in it: <vertex_weights count="xxxx"> 
as should be, shouldn't it?

Only hint I can give is to restructure your script, as a test use less defs, so that it resembles the base script.
(as soon as you've found the fault you could split it up again into more defs)

Or do a rewrite without using the class SanaeParser() (I remember having solved some referencing problem I had ages ago by getting rid of Sanae.)
## Post #10
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2019-10-18T14:25:00+00:00
- Post Title: [Request] Xin Jian 3

> Reply from shakotay2 ↑Fri Oct 18, 2019 4:30 am at Fri Oct 18, 2019 4:30 am
>
> 
yeah, another brave hearted rider of dead horses - welcome to the club!  

See, you're dealing with NoeFlatWeights()? Your  base is example_bonemaps.py from MrAdults, I guess?
To be honest: always wondered how to get this working, but didn't find a noepy model sample.
(Idea was to use the def noepyWriteModel(mdl, bs), but guess it requires such model to be loaded before?)

Seems the weights are not bound to the model somehow.
Your lists look ok, afaiks:
(boneID, boneName, w_addr, vertexcount, vids[])
Code: Select all11 Bip01 R Toe0 0x914a 12 [127, 128, 129, 130, 141, 145, 146, 436, 438, 439, 442, 443]
12 Bip01 R Foot 0x933c 56 [131, 132, 133, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 150, 151, 152, 153, 154, 155, 158, 161, 163, 174, 175, 231, 232, 233, 234, 235, 253, 433, 434, 435, 437, 440, 441, 444, 445, 446, 447, 448, 452, 453, 454, 455, 456, 457, 458, 459, 460, 461, 462, 463, 467, 468, 469]
13 Bip01 L Toe0 0x952e 12 [176, 188, 192, 193, 238, 240, 241, 483, 484, 486, 489, 491]
14 Bip01 L Foot 0x9720 56 [177, 178, 179, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 202, 206, 207, 208, 209, 211, 237, 239, 242, 243, 244, 245, 255, 256, 480, 481, 482, 485, 487, 488, 490, 492, 493, 494, 495, 498, 499, 500, 501, 502, 503, 504, 505, 506, 507, 508, 509, 513, 514, 515]

When exporting to dae there's no such line in it: <vertex_weights count="xxxx"> 
as should be, shouldn't it?

Only hint I can give is to restructure your script, as a test use less defs, so that it resembles the base script.
(as soon as you've found the fault you could split it up again into more defs)

Or do a rewrite without using the class SanaeParser() (I remember having solved some referencing problem I had ages ago by getting rid of Sanae.)

Yeah, may be I will try to re-write this script, I just have learn to write python for 1 week   . When exporting to .fbx, the bones was rotated 180 degrees in spite of displaying good in Noesis? Do you know how to fix it? Also, animations are in separated files, I wonder how to load model and apply animations from others. Nice weekend!
## Post #11
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-10-18T16:16:59+00:00
- Post Title: [Request] Xin Jian 3

Hi, friend, does the unpacked model file name of jx3 match the map file name?
