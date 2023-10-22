## Post #1
- Username: AgnusDei
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 20, 2021 1:32 am
- Post datetime: 2023-05-02T05:08:06+00:00
- Post Title: Ace Combat X: Skies of Deception .PMD and .ANM files

Hello, I've managed to extract files from the ACX's REGFILE.CDI thanks to a tool named "Nemesis" made by Ret-HZ
And so, i've analyzed most of them, and found out PDW files which are textures, PMD and ANM files which i suspect they're model + skeleton and Animation respectively.
I've tried to find a way to make the PMD and ANM files readable for Blender, without any success. I will proceed to send some sample in hopes that someone might help me.

Postdata: I don't think they are encrypted, or compressed.


 FH00.rar
FENRIR PMD and ANM files. (41.78 KiB) Downloaded 21 times
## Post #2
- Username: AgnusDei
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 20, 2021 1:32 am
- Post datetime: 2023-05-02T05:10:08+00:00
- Post Title: Ace Combat X: Skies of Deception .PMD and .ANM files

For some reason I can't send multiple attachments at once.
I will send another here.


 FH04.rar
RAFALE M PMD and ANM files. (22.64 KiB) Downloaded 23 times
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-05-02T12:28:10+00:00
- Post Title: Ace Combat X: Skies of Deception .PMD and .ANM files

> Reply from AgnusDei ↑Tue May 02, 2023 1:08 pm at Tue May 02, 2023 1:08 pm
>
> 
i've analyzed most of them...
Analyze how?  

Interesting format though...



PMDs.png (54.5 KiB) Viewed 203 times
## Post #4
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2023-05-02T17:29:38+00:00
- Post Title: Ace Combat X: Skies of Deception .PMD and .ANM files

> Reply from Bigchillghost ↑Tue May 02, 2023 8:28 pm at Tue May 02, 2023 8:28 pm
>
> 
Interesting format though...

What face generation did you use ? I've tried Implicit Storage for Triangle and Triangle Strip in AXE, and it did not give the correct result. This is the only thing blocking me at the moment since I already found the submeshes vertex buffers, and I didn't notice any of them having a reset for the face generation.
## Post #5
- Username: AgnusDei
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 20, 2021 1:32 am
- Post datetime: 2023-05-02T21:54:22+00:00
- Post Title: Ace Combat X: Skies of Deception .PMD and .ANM files

> Reply from Bigchillghost ↑Tue May 02, 2023 8:28 pm at Tue May 02, 2023 8:28 pm
>
> 
AgnusDei wrote: ↑Tue May 02, 2023 1:08 pm
i've analyzed most of them...

Analyze how?  

Interesting format though...
PMDs.png
As in, attempting to open the files via hex, and learning about hex2obj, I just got blocked on what and how to proceed. Also because I was busy with university exams.

Could you please share your method or script to import the models, please?
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-05-02T22:06:06+00:00
- Post Title: Ace Combat X: Skies of Deception .PMD and .ANM files

> Reply from AgnusDei ↑Wed May 03, 2023 5:54 am at Wed May 03, 2023 5:54 am
>
> 
Could you please share your method or script to import the models, please?
i made plugin for Noesis



FIG00H.PMD.png (13.49 KiB) Viewed 131 times


[fmt_PMD.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_PMD.py)
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-05-02T23:21:05+00:00
- Post Title: Ace Combat X: Skies of Deception .PMD and .ANM files

> Reply from GreenTrafficLight ↑Wed May 03, 2023 1:29 am at Wed May 03, 2023 1:29 am
>
> 
What face generation did you use ?
It's triangle strip but you can use both in some circumstances:



AXE_implict_strips.jpg (182.11 KiB) Viewed 123 times



It's consist of a bunch of triangle strips but fortunately not much work for AXE. You can find the vertex count of each strip and the count of strip groups using that many vertices, as UInt16 just before the vertex buffer.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-05-03T00:30:55+00:00
- Post Title: Ace Combat X: Skies of Deception .PMD and .ANM files

> Reply from AgnusDei ↑Wed May 03, 2023 5:54 am at Wed May 03, 2023 5:54 am
>
> 
Could you please share your method or script to import the models, please?
Well, turns out vertex normals are OK so guess will have to reverse the face winding then. Noesis script here:


 fmt_AceCombatXSkiesOfDeception_PMD.zip
(1 KiB) Downloaded 26 times
