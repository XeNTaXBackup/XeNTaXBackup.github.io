## Post #1
- Username: DarkStrife7
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 02, 2014 11:03 am
- Post datetime: 2023-02-21T20:05:30+00:00
- Post Title: [PC] Dragon Ball Zenkai Battle (.scz files)

[https://www.youtube.com/watch?v=dTGuWCYpkfI](https://www.youtube.com/watch?v=dTGuWCYpkfI)

Hello community! I bring a likely long awaited game by many. I will share as many sample files I can once a extraction solution is found, If someone has any knowledge how to extract this, or create one it would be most appreciated. This file extension is from a PS3 Japan arcade port game, which seems to be in demo form and releasing fully next month. Further analysis suggests these models are inside a pak, possibly revealing the true 3D model inside. 

This photo provides where these models are contained ;



I will post two model files for research and continue to post the folder as more progress is made. I hope we can get some form of plugin to extract these, or a script for noesis/quickbms would be very crucial. I look forward to someone with expertise in the forums finding anything. Thanks!

- Added Ioram for both characters in case either file type is textures or mesh data.

[https://drive.google.com/file/d/14z9jId ... share_link](https://drive.google.com/file/d/14z9jIdPruzfU8JI1UBQNGBb628cpkFQG/view?usp=share_link)

[https://drive.google.com/file/d/10Lbrnt ... share_link](https://drive.google.com/file/d/10LbrntSXX1VSyh5H8hPA8cx1zjx6hGFN/view?usp=share_link)

[https://drive.google.com/file/d/1ZkRbTy ... share_link](https://drive.google.com/file/d/1ZkRbTytmMl4GOZKmCRJ2Okd1OlGELK6k/view?usp=share_link)

[https://drive.google.com/file/d/1VcbH_5 ... share_link](https://drive.google.com/file/d/1VcbH_5y5I0puQIroKezEnheBFxDlJTu7/view?usp=share_link)
## Post #2
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2023-02-25T06:13:10+00:00
- Post Title: [PC] Dragon Ball Zenkai Battle (.scz files)

Hi, so looking at them at first I thought they were the same format as Raging Blast 2 ZPAK, so I ran the samples through the Raging Tools, but they produce incomplete uncompressed files, at some point they're filled with 0x00 bytes.

Please note that the following ramble is purely speculative as I know nothing about comporession.

Zenkai SCZ file


RB2 ZPAK file


Incomplete Zenkai STPK


0x00 bytes


Trying to understand why, I found that the Zenkai SCZ file includes a second ID Tag that's not in the RB2 files.

HCLS
0HCS


Those tags alongside the regular 0LCS tag could be some sort of chunks identifier, because they repeat throughout the compressed files.
The Krillin files even begin with the HCLS tag instead of 0LCS and Raging tools produce a complete blank file.


This is the exact same issue I had when extracting the J-Stars models, they use a $CMP header similar to Burning Blood or OPM AHNK, but those games only use the $CL0 tag for the chunks.

$CL0


While J-Stars use a second tag similar to Zenkai

$CLH
$CH0


So, after using the [cmp_scz bms script](http://aluigi.altervista.org/bms/cmp_scz.bms) on the J-Stars files and producing incomplete files I decided to do a memory dump of RPCS3 and I could get the complete STPK files, at least for the characters (couldn't get UI or maps).

I see that Aluigi updated the cmp_scz script to work with [Ultimate Tenkaichi](https://www.zenhax.com/viewtopic.php?t=12577), maybe you can create a post on Zenhax and share these findings and request to update the script for Zenkai compatibility

You also could share the files with the RB2 Modding community, so that the developer of Raging Tools can add Zenkai support, but I guess that would be better when the game is actually playable on that new RPCS3 fork.

Another option would be to see if you can get the uncompressed files from a RAM Dump, similar to how I got the J-Stars files.

That's all the insight I can share from those 4 samples.

If you plan on doing any of those recommendations please let me know so I can request some J-Stars support.
## Post #3
- Username: DarkStrife7
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 02, 2014 11:03 am
- Post datetime: 2023-02-25T07:48:58+00:00
- Post Title: [PC] Dragon Ball Zenkai Battle (.scz files)

Josou, thanks a ton for this super knowledgeable reply. I'm amazed at the information you found and it's awesome to know these files are in familiar territory to those games. 

Pretty sure we can get Aluigi to help out with some dedicated script. Seems pretty doable, the explanations and comparisons between the files really helped me understand alot about the file structure.

Also, very interesting the way some of these files are so similar to each other yet completely different games. 

I'm extremely thrilled seeing the file dissected by you, that's my favorite part. I can see the names of the model pieces in there for sure and that made me smile. 

I'm going to keep analyzing your post as there's tons of valuable information and of course head over to Aluigi for the next push, we'll get this working. Also please do ask for Jstar support. 

PS; I'm also wondering about the Ram Dump, that could possibly be another step. I've sent you some other info in your inbox so you can further analyze. 

Thanks for analyzing these two files so far, Jasou, you're extremely wise and I hope we get to final solution for these files.
## Post #4
- Username: Dippergames420
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 23, 2019 8:42 am
- Post datetime: 2023-03-05T08:08:37+00:00
- Post Title: [PC] Dragon Ball Zenkai Battle (.scz files)

Hello there!

Did some research on my own for some of these files and as it would turn out, the model seen here is a different one to what's used in the three-level demo. Turns out this is a costume for an illustration from cover of the World of Akira Toriyama book. I did some file swapping to show you what I mean.

Here's what I got with the file posted (model31):


And here's the demo costume (model1):


And here's a video of me demonstrating another model swap I did (model2 over model1): [https://www.youtube.com/watch?v=3iOefXBZGlk](https://www.youtube.com/watch?v=3iOefXBZGlk)

Also found some evidence of unused content while digging around in the files, for instance a gap in between character 05 (Tien/Tenshinhan) and 07 (Vegeta.) No idea who 06 was originally going to be, but my best guess is maybe Chaozu..? No idea there, since nothing remains of him in the game. But, slot 50 (also unused) does carry information on another cut character, Chi-Chi. Her parameter file can be found in the 17,01 directory, but there are no models associated with her, so no idea which version of Chi-Chi was planned. Either/or, here's her file: [https://drive.google.com/file/d/1u6Zf5c ... sp=sharing](https://drive.google.com/file/d/1u6Zf5cI7xioe5iwvUeuco8MyMRBHfXcM/view?usp=sharing)

Wish you guys the best of luck with decompressing these files!

EDIT (3/5/2023 4:01 A.M.): More Alts for Goku

Model4 (Green Alt; Standard Costume):


Model9 (Yellow Alt; Yardrat Costume):


Model20 (White Alt; End of Z Costume):


EDIT (3/5/2023 4:33 A.M.): Two more alts

Model15 (Blue Alt; Damaged Costume):


Model26 (Red Alt; Casual Clothing):
## Post #5
- Username: DarkStrife7
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 02, 2014 11:03 am
- Post datetime: 2023-03-06T21:43:24+00:00
- Post Title: [PC] Dragon Ball Zenkai Battle (.scz files)

Thanks to Josou and Dipper for their awesome findings.

Truly awesome research from both Josou and Dipper. I appreciate the research and effort going into this. I initially wanted the 3D models to be extracted or a viewer made for them, but seeing their costumes being displayed is incredible. 

I'm surprised that the original file I posted was costume 31 the Akira Toriyama outfit. Super awesome. Thanks Dipper for letting me know over through Discord. I felt silly but kind of unique now!   

There's an update for the community interested.

Please Refrain From Downloading The Emulator being leaked online for Zenkai Battle. Josou, Dipper, and I have discovered that the emulator which launches this game has a keylogger embedded into the emulator. You may see posted leaks on YouTube about how to get this emulator, refrain from doing so at all times.

Your safest way is to examine to files individually as I did on the first post of this thread. Refrain from displaying the game through any leaked source. 

Please refer to the following link for a full description by the DEV for project OMED which is set to release this month:
[https://www.arcade-projects.com/threads ... 787/page-3](https://www.arcade-projects.com/threads/namco-system-357-emulation-maybe-project-omed-2023.23787/page-3)

Besides these news, Josou has gotten in touch with Revelation from our very own Xentax forums, he has managed to decompress the files. We're now awaiting to hear back for any further updates.
