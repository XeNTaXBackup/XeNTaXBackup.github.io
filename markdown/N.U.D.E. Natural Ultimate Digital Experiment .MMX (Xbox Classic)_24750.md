## Post #1
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2021-11-19T14:40:47+00:00
- Post Title: N.U.D.E. Natural Ultimate Digital Experiment .MMX (Xbox Classic)

This is an obscure game released only in Japan so naturally, it doesn't have any tools for its models, luckily the package files can be unpacked with this script:
[https://zenhax.com/viewtopic.php?t=2826&start=40](https://zenhax.com/viewtopic.php?t=2826&start=40)

The models are in this format called MMX but I couldn't find anything about it so I'mma leave some samples, the ZIP has all the files that make up the only 3D character in the game, a few animations, and some static objects in case anyone wants to give these a try.

[https://drive.google.com/file/d/1yLXw-w ... _24CVWbMXk](https://drive.google.com/file/d/1yLXw-wepzns4uh_GibDIKN_24CVWbMXk)

Not expecting much but would be nice to have the original rigging 'n all
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-19T19:29:53+00:00
- Post Title: N.U.D.E. Natural Ultimate Digital Experiment .MMX (Xbox Classic)

Usually I don't care for the rigging, this is what I get so far (only some of 192 (?) sub meshes):
.



FL_Base-MMX.png (26.14 KiB) Viewed 208 times


(From the point cloud I thought this were a frog...  )
## Post #3
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2021-11-19T21:25:53+00:00
- Post Title: N.U.D.E. Natural Ultimate Digital Experiment .MMX (Xbox Classic)

> Reply from shakotay2 ↑Sat Nov 20, 2021 3:29 am at Sat Nov 20, 2021 3:29 am
>
> 
Usually I don't care for the rigging, this is what I get so far (only some of 192 (?) sub meshes):
.
FL_Base-MMX.png
(From the point cloud I thought this were a frog...  )

Nice to see that the data can read just fine, thought there would be some wacky obfuscation or encryption in these files.
## Post #4
- Username: AgentCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 02, 2023 9:27 pm
- Post datetime: 2023-01-19T06:25:15+00:00
- Post Title: N.U.D.E. Natural Ultimate Digital Experiment .MMX (Xbox Classic)

My mother tongue is not English, so the following words may look strange。

Most of the files in "PASS.tfs" are encrypted/obfuscations character models, and the map files are in "FACE. tfs". After decompressing with BMS, these files can be divided into "ndbm, ndfm, ndmv and others" according to the prefix. NDBM is the character model, and NDFM may be the same. ndmv is the in-game cut-out animation, and some other files are models of character hair. Open the model file with the hex editor. The fifth and sixth bytes represent the data length (little ending,the difference is 8 from the hex editor report). I guess the following code is a reading rule.

I don't understand disassembly , which is the limit of what I can do, so I want to get help here, otherwise I can only hope that "Cxbx-Reloaded" can simulate "Xbox communicator"  

PS: There is very little information about this game, and it is not even introduced on the website of the production company. I learned from a magazine that introduced the development process that the game model was made using 3Ds Max and the LightWave was used to make animation effects
## Post #5
- Username: AgentCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 02, 2023 9:27 pm
- Post datetime: 2023-01-23T06:08:28+00:00
- Post Title: N.U.D.E. Natural Ultimate Digital Experiment .MMX (Xbox Classic)

I'm back again
Use IDA Pro "default.xbe" (this is the startup file of the game) is analyzed, and the decryption key is probably in this file.
[/img]20230123133607.png[/img]
[20230123133607.png](https://xentaxbackup.github.io/file/23337_20230123133607.png)
## Post #6
- Username: AgentCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 02, 2023 9:27 pm
- Post datetime: 2023-02-11T11:27:29+00:00
- Post Title: N.U.D.E. Natural Ultimate Digital Experiment .MMX (Xbox Classic)

Hmmmmmm…
I think I may have gone the wrong way.
Anyway, I will verify the other one and then come back to share my experience.
## Post #7
- Username: AgentCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 02, 2023 9:27 pm
- Post datetime: 2023-02-23T00:19:54+00:00
- Post Title: N.U.D.E. Natural Ultimate Digital Experiment .MMX (Xbox Classic)

new post:[viewtopic.php?t=26500&sid=f0106573ea9f4 ... 89b5687444](https://forum.xentax.com/viewtopic.php?t=26500&sid=f0106573ea9f48617230f089b5687444)
## Post #8
- Username: AgentCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 02, 2023 9:27 pm
- Post datetime: 2023-02-25T11:29:35+00:00
- Post Title: N.U.D.E. Natural Ultimate Digital Experiment .MMX (Xbox Classic)

It took me two days to make an index table (vertex-face) of all the models in FL_BASE, and then I can export the models I am interested in for secondary production.
The production team even made an independent model for the toe……

PS:If anyone is interested in this, please PM me and leave an email
