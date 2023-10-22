## Post #1
- Username: chzhang316
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 05, 2017 11:17 pm
- Post datetime: 2021-06-10T03:44:37+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

Note: both the post and the script is working in progress

UPDATE: a draft level script for ps3 version NGS1 added. This time you can install it as an addon. But that Ctrl+Z crash bug still exist, no idea for the reason. For now, to avoid this, simply click something to make it highlight after importing a file.

For NGS script you got some options to control whether importing the effects or auto rigging the model, so you don't need to edit the script or do yourself. I wish I could find spare time to add these features to NGB script as well.

I put those unnecessary words into a [spread sheet](https://docs.google.com/spreadsheets/d/1840PcFCyNhXsHpPRGckHXYm5akBwyNBgmnu6sEA-Vws/edit?usp=sharing), will make it tidier later.

Before adding more features to the script, I need to go back to indie game translating for a while.



 NGSafs044.zip
(11.71 KiB) Downloaded 68 times



(seems I can only add one attachment, I've uploaded my [old NGB script](https://drive.google.com/file/d/10aEKjr4YLcx4a_Ex034dQS7MlK8kJ9KS/view?usp=sharing) to Google Drive )

----------

(Updated)Special thanks: 

Protocol X27, all start from his Ninja Guts tool, I’m finally able to research the model of Ninja Gaiden series

mariocart64n, without his backing up of a old xpr format spreadsheet by ninja hacker long ago, as a newbie, I would suffer a lot of time figuring out the NGB format without any clue and experience

Author of hex2obj(shakotay2) and ModelResearcher, can’t live without these two programs

Other dudes on Team Ninja games discuss topics, you guys left so much precious knowledge to me

Acewell, I'll never know the texture swizzling used in Ninja Gaiden named "Morton" without looking at his noesis script
## Post #2
- Username: deadsonicmoon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 11, 2021 11:50 pm
- Post datetime: 2021-06-11T16:25:01+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

So on the steam versions of these games the files are packed within a databin file. Haven't found a way to unpack it yet. This is also present on the switch version of the master collection.
## Post #3
- Username: chzhang316
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 05, 2017 11:17 pm
- Post datetime: 2021-06-12T12:01:15+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

> Reply from deadsonicmoon ↑Sat Jun 12, 2021 12:25 am at Sat Jun 12, 2021 12:25 am
>
> 
So on the steam versions of these games the files are packed within a databin file. Haven't found a way to unpack it yet. This is also present on the switch version of the master collection.

EDIT: My bad, I forgot to make the file shared. It should be ok to download now. Let me know if there is any problem.

Here is an [unpacker](https://drive.google.com/file/d/1Xeg5on_zqdsAZFuXs3RcJh4GF583FN67/view?usp=sharing) for all three games, made by a Chinese modder. Put the two files at the same location of databin file and run that the .bat file. The unpacker auto detect and name the TMC and TMCL files, I heard it's the format for NG3RE? Not sure if it works for the Switch version, I don't have any consoles.
## Post #4
- Username: サイ(Sai)
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 15, 2021 5:31 pm
- Post datetime: 2021-06-20T00:51:58+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

Does this script work for maps? I've tested it with a character and got no problem. But when i tried to use it with a map, it marked some errors. 
I think it still extracted some things, but i am not sure.

Also, thank you very much for your efforts!
## Post #5
- Username: chzhang316
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 05, 2017 11:17 pm
- Post datetime: 2021-06-21T16:31:29+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

> Reply from サイ(Sai) ↑Sun Jun 20, 2021 8:51 am at Sun Jun 20, 2021 8:51 am
>
> 
Does this script work for maps? I've tested it with a character and got no problem. But when i tried to use it with a map, it marked some errors. 
I think it still extracted some things, but i am not sure.

Also, thank you very much for your efforts!

Fixed. The script has been updated to 0.51 version, try it.

Yes the script should have worked for area models as well, but I only tested them without texture earlier, and it really has problems... When testing character models, all the objects have at least one texture, so I skipped the texture count checking just to save one line of code… Thus if you import an object that has 0 texture, the error happens. I also fixed some other problems causing the script to raise errors that I haven't met in character models as well, like currently unknown 0x6 type texture in suiro_01 (maybe other water channel maps too) and second pivot in type 0 object for some weapons in cmn.afs.

This time I checked all the files with all the currently available features imported (the importing process froze my 13-year-old computer for nearly 40 minutes, undo it took another 10 minutes, that's why I didn't do this before (つд∩) ), the script should works for all models now, hopefully. 

But still, I can’t make sure if all the models got displayed correctly (like the truck’s UV is incorrect, need to figure out the reason later), I can just make sure the script itself can run correctly. The fix is actually done in another script I generally used that requires manually setting up, and hand-pasting to the released one, so let me know if there's something I missed.
## Post #6
- Username: Planet
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 08, 2020 9:49 pm
- Post datetime: 2021-06-24T12:22:56+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

i hope you can make one for sigma
## Post #7
- Username: chzhang316
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 05, 2017 11:17 pm
- Post datetime: 2021-06-25T16:33:04+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

> Reply from Planet ↑Thu Jun 24, 2021 8:22 pm at Thu Jun 24, 2021 8:22 pm
>
> 
i hope you can make one for sigma

I planned to do but it may take more time than the NGB script (15 evenings) since I still have something else to finish.
## Post #8
- Username: Planet
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 08, 2020 9:49 pm
- Post datetime: 2021-07-01T16:09:24+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

> Reply from chzhang316 ↑Sat Jun 26, 2021 12:33 am at Sat Jun 26, 2021 12:33 am
>
> 
Planet wrote: ↑Thu Jun 24, 2021 8:22 pm
i hope you can make one for sigma


I planned to do but it may take more time than the NGB script (15 evenings) since I still have something else to finish.
take your  time. it seems that  the master collection version has extra outfit, the  red biker one.
## Post #9
- Username: Amin447
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 01, 2017 8:33 pm
- Post datetime: 2021-07-01T16:38:21+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

don't give up man. continue ...
i can't wait to extract ninja gaiden black and sigma models 
i wanna import them into unreal engine and somehow simulate the Dwarku district     
if it be possible to extract animations and poses as well as models it would be super awesome
## Post #10
- Username: サイ(Sai)
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 15, 2021 5:31 pm
- Post datetime: 2021-07-17T00:11:15+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

Hi, just wanted to update: I didn't have much time lately to keep working with the models, but every single model i've tested your script on is working just fine  thank you.
## Post #11
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2021-07-29T23:47:53+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

I haven’t pushed every AFS through, but the ones I have come out perfectly. What you did is amazing—I streamed a little of me messing with it today and gave you as many kudos a man could. I’ve waited a long time for someone to do something like this.  

We did have a couple questions for you, though:

If you can pull the models from the AFS, can you write a script that would pack edited models back in? For example, the locomotive turnstile. Let’s say if I delete the locomotive model, could something be written to allow me to write the changes made to the stage to the kmd or the entire AFS?

A few others asked if you had written a script for Sigma and I told them you set out to do both. 

That was followed by someone asking if you would look at Sigma 2. 

And that was followed by someone asking if you had been tracking tianmuxia’s NGMC scripts. He’s written a couple TMC-to-FBX converters for S2 and RE and it was suggested maybe you could find something in that to help with your own progress.

Please keep us posted, man. This is an incredible contribution.
## Post #12
- Username: THESIERRAMAN
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Jun 06, 2012 4:31 am
- Post datetime: 2021-08-18T04:06:53+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

> Reply from chzhang316 ↑Sat Jun 12, 2021 8:01 pm at Sat Jun 12, 2021 8:01 pm
>
> 
deadsonicmoon wrote: ↑Sat Jun 12, 2021 12:25 am
So on the steam versions of these games the files are packed within a databin file. Haven't found a way to unpack it yet. This is also present on the switch version of the master collection.


EDIT: My bad, I forgot to make the file shared. It should be ok to download now. Let me know if there is any problem.

Here is an unpacker for all three games, made by a Chinese modder. Put the two files at the same location of databin file and run that the .bat file. The unpacker auto detect and name the TMC and TMCL files, I heard it's the format for NG3RE? Not sure if it works for the Switch version, I don't have any consoles.

Do you know how to open those TMC and TMCL for Blender? 
Thanks
## Post #13
- Username: chzhang316
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 05, 2017 11:17 pm
- Post datetime: 2021-08-18T07:46:42+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

> Reply from THESIERRAMAN ↑Wed Aug 18, 2021 12:06 pm at Wed Aug 18, 2021 12:06 pm
>
> 
Do you know how to open those TMC and TMCL for Blender? 
Thanks

It need a specific tool. I haven't started to deal with the pc version yet. The author of that unpacker (search "tianmuxia" on LoversLab) has a TMC2FBX program for pc Sigma1, though the current result is still unsatisfactory.
## Post #14
- Username: maverx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 09, 2013 9:20 am
- Post datetime: 2022-02-22T04:15:57+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

Hi , your work is amazing, I have a question, it is possible to extract the animations from ninja gaiden games and be exported to FBX files ? like the vigoorian flail or lunar attacks  ?  if is possible, could you point me to the right direction to achieve that?
## Post #15
- Username: chzhang316
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 05, 2017 11:17 pm
- Post datetime: 2022-05-21T13:26:41+00:00
- Post Title: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

> Reply from maverx ↑Tue Feb 22, 2022 12:15 pm at Tue Feb 22, 2022 12:15 pm
>
> 
Hi , your work is amazing, I have a question, it is possible to extract the animations from ninja gaiden games and be exported to FBX files ? like the vigoorian flail or lunar attacks  ?  if is possible, could you point me to the right direction to achieve that?

Oh hi, sorry for the late reply. I haven't checked the forum for several months and almost forgot that I posted this thread... About the animation, unfortunately I didn't have any knowledge about the FBX format. But I did have a WIP script for extracting a part of animations directly from the in-game files to Blender, like the model script. It's just there's some technical problems that the extracting process didn't fit my current script so I haven't released it all the way. I've laid aside the research for a while. Not sure if I'm able to finish it. Give me some time.
## Post #16
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2022-11-28T04:10:07+00:00
- Post Title: Re: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

I tried to import “chr_tank.afs from the ps3 version of sigma but no luck. Nothing seems to import on any of the models. What am I doing wrong?
## Post #17
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2022-12-20T01:25:46+00:00
- Post Title: Re: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

> Reply from viperzerofsx ↑Mon Nov 28, 2022 12:10 pm at Mon Nov 28, 2022 12:10 pm
>
> 
I tried to import “chr_tank.afs from the ps3 version of sigma but no luck. Nothing seems to import on any of the models. What am I doing wrong?

I just imported chr_tank just fine. First suspicion is maybe some .afs files were corrupted, assuming you transferred them from a jailbroken console.
## Post #18
- Username: サイ(Sai)
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 15, 2021 5:31 pm
- Post datetime: 2023-03-07T17:15:11+00:00
- Post Title: Re: (20210821 Updated)(WIP) Ninja Gaiden Black/Sigma(ps3) .afs script for Blender

Hi, are there any updates referring to the script?
