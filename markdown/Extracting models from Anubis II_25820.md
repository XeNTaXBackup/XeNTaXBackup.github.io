## Post #1
- Username: bonkmaykr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 23, 2022 2:54 am
- Post datetime: 2022-09-19T22:55:12+00:00
- Post Title: Extracting models from Anubis II

Hello. A friend of mine asked me to extract the models for the player character in Anubis II. The game runs on Renderware 3, and all models are stored in the DFF binary format (except for a couple of duplicates which were left in .LWO Lightwave format, probably leftover from the artists before conversion). I've acquired the official RW 3.7 SDK for Windows and dumped the game's WAD using Watto GameExtractor, but the Clump Viewer will not open any of the model files I feed to it. No error messages are displayed.

The relevant model files are 177928c6.dff, 6811fa11.dff, and eef9e36d.dff. They all share a single BMP texture.

Am I just using the SDK wrong or are these files custom? I've tried CLI arguments, clmpview.ini, and even drag and drop. Only the example models included with the SDK will open.
[xentax_post_modelfiles.rar](https://xentaxbackup.github.io/file/22834_xentax_post_modelfiles.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-20T14:07:08+00:00
- Post Title: Extracting models from Anubis II

> Reply from bonkmaykr ↑Tue Sep 20, 2022 6:55 am at Tue Sep 20, 2022 6:55 am
>
> 
Hello. ...

Am I just using the SDK wrong or are these files custom?I have no idea. This model looks simple (used auto created face to ease the process)
.



177928c6-dff.jpg (64.92 KiB) Viewed 52 times

(Checked one sub mesh only, as almost always.)
## Post #3
- Username: bonkmaykr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 23, 2022 2:54 am
- Post datetime: 2022-09-29T01:47:40+00:00
- Post Title: Extracting models from Anubis II

That looks to be part of the Body mesh, which I do have a duplicate copy of in LWO format as left in the game by the developers. I cannot seem to view the Head mesh though.


I've been using AccuTrans 3D and Blender w/ the DragonFF plugin so far, I'll try that hex2obj tool instead.
