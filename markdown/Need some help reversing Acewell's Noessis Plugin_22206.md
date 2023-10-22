## Post #1
- Username: connorwalks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 17, 2020 3:25 am
- Post datetime: 2020-05-26T22:08:54+00:00
- Post Title: Need some help reversing Acewell's Noessis Plugin

I've been using Acewell's version of the Noessis XPR plugin found [here](https://forum.xentax.com/viewtopic.php?f=18&t=8102&start=15) to convert the XPR2 files to DDS from an XBOX 360 game I am modding. My issue now is that I need to convert these DDS files back to their original XPR2 format so I can reimport them into the game. Sorry if I'm missing an obvious way to do this, I don't have much experience with Noessis. Thank you so much in advance, there's a large community for this game that is very grateful for any help! Script and sample XPR are included below

[Here is the plugin from Acewell](https://www109.zippyshare.com/v/Kyl0dxKR/file.html)



 SAMPLE XPR.7z
Sample XPR (37.96 KiB) Downloaded 18 times
## Post #2
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2020-05-27T22:35:04+00:00
- Post Title: Need some help reversing Acewell's Noessis Plugin

You can use UnBundler/Bundler tools found in xbox360 SDK (neighborhood) to unpack/pack xpr resources. Drag xpr to unbundler and you got tga and rdf description file. Use bundler.exe and rdf file to make xpr from tga source -> ”bundler.exe test.rdf -o test.xpr”.

There is no simple script to convert dds to xpr because xbox 360 uses texture tiling. Noesis can handle untiling textures but I don’t know the code for re-tiling so the only way I know is use bundler.
## Post #3
- Username: connorwalks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 17, 2020 3:25 am
- Post datetime: 2020-05-29T06:23:08+00:00
- Post Title: Need some help reversing Acewell's Noessis Plugin

Thanks so much for the reply, as it turns out simply changing the file extension so they would reimport to quickBMS seems to be working, but that's only tested on Xenia. If I run into issues on actual Xbox hardware I'll give the bundler a shot. Thanks again!
