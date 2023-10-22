## Post #1
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-06-24T17:20:14+00:00
- Post Title: Project Cars 2

Game is very old, sequel will be on 28 August but PC2 still didn't have tools. In topic of GT6 daemon1 one year ago said: "Project cars 2 decryption tool was made about 4 month ago. I'm not publishing it to keep the method safe." Maybe someone here can make tools for this game? Here is some samples (after decompress using Quick BMS script for Shift):
[https://mega.nz/file/S01AyQDK#YiUcYHGBU ... 5QjUPSq85E](https://mega.nz/file/S01AyQDK#YiUcYHGBUV8IzuOaKtnVwz8Vfvo4AaNqg5QjUPSq85E)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-25T05:23:46+00:00
- Post Title: Project Cars 2

The 1st components of the positions look weird, if it's decrypted correctly.



Ferrari F355 Challange_005426e0_meb_pos.jpg (141.36 KiB) Viewed 426 times



UV is OK though.
## Post #3
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-06-25T10:32:11+00:00
- Post Title: Project Cars 2

> Reply from zimex25 ↑Thu Jun 25, 2020 1:20 am at Thu Jun 25, 2020 1:20 am
>
> 
Game is very old, sequel will be on 28 August but PC2 still didn't have tools. In topic of GT6 daemon1 one year ago said: "Project cars 2 decryption tool was made about 4 month ago. I'm not publishing it to keep the method safe." Maybe someone here can make tools for this game? Here is some samples (after decompress using Quick BMS script for Shift):
https://mega.nz/file/S01AyQDK#YiUcYHGBU ... 5QjUPSq85E

Cars from PC2 might be have this same format like Shift 1 and 2, PC1 but files are protect so 3DSimED can't open models.
## Post #4
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2020-06-27T11:31:58+00:00
- Post Title: Project Cars 2

> Reply from Bigchillghost ↑Thu Jun 25, 2020 1:23 pm at Thu Jun 25, 2020 1:23 pm
>
> 
Seems like mesh vertex positions are downscaled by one of axis.
For example:
Original positions may be like this: 123.01, 123.02, 2.123
Positions stored in file may be like this: 0.0012301, 123.02, 2.123
It may caused by result of math operation on vertex position (substraction or xor, i don't know).
Need to make some experiments with data.
Sorry if I'm wrong, these are just my assumptions.
## Post #5
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2020-06-27T19:18:37+00:00
- Post Title: Project Cars 2

the files have the X coordinate obfuscated, easy fix is to get those from the ram when opening the game, the virtualization will unpack that in the ram, you just need to search for the coordinates that are not obfuscated and youll find the missing vertex coordinate
## Post #6
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-09-05T12:27:56+00:00
- Post Title: Project Cars 2

Here is examples from Project Cars 3 and Fast and Furious Crossroads, PC3 and FFC probably have this same format of mesh but textures now is in .tex format.
PC3: [https://mega.nz/file/exsjABKR#Hdd7SQAFP ... 8JG-PynC48](https://mega.nz/file/exsjABKR#Hdd7SQAFPF2xeJs8TsUotFcs4YqGotV5m8JG-PynC48)
FFC: [https://mega.nz/file/Ok1yAIgY#kuu9PzRa8 ... D4fDab5uig](https://mega.nz/file/Ok1yAIgY#kuu9PzRa8OUbZrCF_glxrtdALHsashPTSD4fDab5uig)
## Post #7
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-09-13T00:51:43+00:00
- Post Title: Project Cars 2

Wondering that too. Is there a way to get model and textures?
## Post #8
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-09-13T01:35:26+00:00
- Post Title: Project Cars 2

nvm the textures are already in common format. But how do I get models?
## Post #9
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2021-01-04T14:29:37+00:00
- Post Title: Project Cars 2

Hi Guys! I´ve unpacked files from PC2. There are .meb files and some texture files. What to do with these files next? 3d files are encrypted, its possible to decrypt this files?

Somehow the models open up and can be converted to Assetto corsa, GTA 5, GTA 4....

Models from PC2: [https://gamemodels.ru/files/category/12 ... ct-cars-2/](https://gamemodels.ru/files/category/1241-project-cars-2/)

maybe people who know to unload this encrypted cars models?


Happy new year!!!!!!
## Post #10
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-04T21:08:58+00:00
- Post Title: Project Cars 2

> Reply from MichaelBFS ↑Mon Jan 04, 2021 10:29 pm at Mon Jan 04, 2021 10:29 pm
>
> 3d files are encrypted, its possible to decrypt this files?
...
maybe people who know to unload this encrypted cars models?
...
On PC yes, you are correct, but not the PS4 one, might as well download the PS4 game and everything works in 3ds max with old script.
## Post #11
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2021-01-05T23:22:57+00:00
- Post Title: Project Cars 2

> Reply from MichaelBFS ↑Mon Jan 04, 2021 10:29 pm at Mon Jan 04, 2021 10:29 pm
>
> 
Hi Guys! I´ve unpacked files from PC2. There are .meb files and some texture files. What to do with these files next? 3d files are encrypted, its possible to decrypt this files?

Somehow the models open up and can be converted to Assetto corsa, GTA 5, GTA 4....

Models from PC2: https://gamemodels.ru/files/category/12 ... ct-cars-2/

maybe people who know to unload this encrypted cars models?


Happy new year!!!!!!
Way How convert cars from PC2 (and maybe PC3) was few time ago knew but If you have lucky, you can find tutorial, if you not have, you never know how get this models... Nobody on this forum care about racing games and models or didn't have time for making tools.
## Post #12
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-06T01:31:49+00:00
- Post Title: Project Cars 2

> Reply from zimex25 ↑Wed Jan 06, 2021 7:22 am at Wed Jan 06, 2021 7:22 am
>
> Way How convert cars from PC2 (and maybe PC3) was few time ago knew but If you have lucky, you can find tutorial, if you not have, you never know how get this models... Nobody on this forum care about racing games and models or didn't have time for making tools.
Your doing that thing again where you talk nonsense before actually doing a bit of research, every time you mention a racing game and that there is no love for them, your wrong, wrong and wrong again, you didn't even pay attention to my response above.
## Post #13
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2021-01-06T12:29:52+00:00
- Post Title: Project Cars 2

> Reply from mono24 ↑Wed Jan 06, 2021 9:31 am at Wed Jan 06, 2021 9:31 am
>
> 
zimex25 wrote: ↑Wed Jan 06, 2021 7:22 amWay How convert cars from PC2 (and maybe PC3) was few time ago knew but If you have lucky, you can find tutorial, if you not have, you never know how get this models... Nobody on this forum care about racing games and models or didn't have time for making tools.

Your doing that thing again where you talk nonsense before actually doing a bit of research, every time you mention a racing game and that there is no love for them, your wrong, wrong and wrong again, you didn't even pay attention to my response above.

Maybe, but I'm so frustrated when tools for PC2/3, NFS No Limits and RaceRoom don't exist or If exist, some people have monopol for using and share models. I don't want hurt somebody, If I did, I'm so sorry.
## Post #14
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-06T21:04:14+00:00
- Post Title: Project Cars 2

> Reply from zimex25 ↑Wed Jan 06, 2021 8:29 pm at Wed Jan 06, 2021 8:29 pm
>
> Maybe, but I'm so frustrated when tools for PC2/3, NFS No Limits and RaceRoom don't exist or If exist, some people have monopol for using and share models. I don't want hurt somebody, If I did, I'm so sorry.
The reversers decide what they do with their code, its their hard work, no one else's, why so many still whine about it it baffles me, and as for those who share models, well, its their doing not the reverser.
And no you didn't hurt anyone, just do a better search next time
## Post #15
- Username: MeIRL
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 17, 2018 4:01 pm
- Post datetime: 2021-01-09T15:41:26+00:00
- Post Title: Project Cars 2

[https://cloud.mail.ru/public/RhEe/i3Mrmir9o](https://cloud.mail.ru/public/RhEe/i3Mrmir9o)

PCARS 3 Exemple
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-01-10T15:54:40+00:00
- Post Title: Re: Project Cars 2

> Reply from MeIRL ↑Sat Jan 09, 2021 11:41 pm at Sat Jan 09, 2021 11:41 pm
>
> 
PCARS 3 Exemple
Got it.
(0006c600.meb)
[](https://ibb.co/k5Nj1z2)
## Post #17
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-10T19:59:06+00:00
- Post Title: Re: Project Cars 2

> Reply from Bigchillghost ↑Sun Jan 10, 2021 11:54 pm at Sun Jan 10, 2021 11:54 pm
>
> Got it.
Does that mean you extract the unencrypted part and just mirror everything, or...?
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-01-11T00:17:25+00:00
- Post Title: Re: Project Cars 2

Just an attempt to restore the X factor based on the overlapped top projection and use the UV to determine the sign. Also need to remap the factor to its original boundary since it uses a different scale.
## Post #19
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2021-01-11T18:33:30+00:00
- Post Title: Re: Project Cars 2

> Reply from Bigchillghost ↑Sun Jan 10, 2021 11:54 pm at Sun Jan 10, 2021 11:54 pm
>
> 
MeIRL wrote: ↑Sat Jan 09, 2021 11:41 pm
PCARS 3 Exemple

Got it.
(0006c600.meb)

Did you tring with Fast and Furious samples?
## Post #20
- Username: Javiliyors
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 08, 2019 5:39 am
- Post datetime: 2021-01-12T19:34:57+00:00
- Post Title: Re: Project Cars 2

it is possible to extract decript tracks from PC2 and AMS2 ???, they have the same engine
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-01-13T05:03:14+00:00
- Post Title: Re: Project Cars 2

> Reply from zimex25 ↑Tue Jan 12, 2021 2:33 am at Tue Jan 12, 2021 2:33 am
>
> 
Did you tring with Fast and Furious samples?
Unfortunately none of these samples I checked come with a valid top projection. Same circumstance might be applied to most of the meb files from PC3. So it seems pretty obvious that it's not meant to be handled in this way.
## Post #22
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2021-01-16T07:33:03+00:00
- Post Title: Re: Project Cars 2

Hi! Please upload unencrypted this cars from PC3:   

2019 McLaren 720S GT3 [https://igcd.net/vehicle.php?id=224912](https://igcd.net/vehicle.php?id=224912)

2020 Chevrolet Corvette C8.R [https://igcd.net/vehicle.php?id=219627](https://igcd.net/vehicle.php?id=219627)

1994 Jaguar XJ220S Racing [https://igcd.net/vehicle.php?id=226643](https://igcd.net/vehicle.php?id=226643)

2019 Aston Martin Vantage GTE [https://igcd.net/vehicle.php?id=226630](https://igcd.net/vehicle.php?id=226630)
## Post #23
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2021-01-17T00:10:17+00:00
- Post Title: Re: Project Cars 2

> Reply from Bigchillghost ↑Wed Jan 13, 2021 1:03 pm at Wed Jan 13, 2021 1:03 pm
>
> So it seems pretty obvious that it's not meant to be handled in this way.
Some years ago i send a model ripped using Ninja Ripper to Dave Noonan (author of 3DSimEd), he managed to restore mesh, using information from shader, but that method works only with one car model, others require another keys, which Noonan fails to locate and abandoned this game.
Sample rip [here](https://www.mediafire.com/file/4zmp8n22uhe1yr8/pCARS2AVX.zip/file).
Vertices decoding are in Shader_0000.gs, fragment (~1/7 of code):

```
if_z r0.x
  mov r1.z, l(0)
  ld_indexable(texture2d)(float,float,float,float) r0.xyzw, r1.xyzz, t1.xyzw
  mul r2.x, r0.w, cb1[13].x
  mad r0.w, r0.w, cb1[13].x, -cb1[13].w
  div r2.x, |r0.w|, r2.x
  mul r2.y, cb1[13].z, cb1[13].z
  add r2.z, -cb1[13].z, cb1[13].w
  mul r2.z, r2.z, cb1[14].x
  div r2.y, r2.y, r2.z
  mul r2.x, r2.x, r2.y
  mul r2.x, r2.x, cb1[10].x
  mul r2.x, r2.x, l(14.285714)
  lt r2.z, r0.w, l(0.000000)
  movc r2.w, r2.z, cb1[13].y, cb1[14].y
  min r2.x, r2.x, r2.w
  mul r3.xy, cb1[11].xyxx, l(0.500000, 0.500000, 0.000000, 0.000000)
  mul r4.xy, r2.xxxx, l(0.500000, 0.250000, 0.000000, 0.000000)
  ge r0.w, r0.w, l(0.000000)
  and r2.x, r0.w, l(1)
  dp2 r2.w, cb1[12].xyxx, icb[r2.x + 0].xyxx
  ge r2.w, r4.x, r2.w
  mul r4.z, cb1[14].w, l(0.250000)
  mov r4.w, l(2)
  mov r5.x, r4.x
  mov r5.y, cb1[14].w
  mov r5.z, l(0)
  movc r6.xyz, r2.wwww, r4.yzwy, r5.xyzx
  dp2 r2.x, cb1[12].zwzz, icb[r2.x + 0].xyxx
  ge r2.x, r6.x, r2.x
  mul r7.xy, r6.xyxx, l(0.500000, 0.250000, 0.000000, 0.000000)
  mov r7.z, l(4)
  movc r6.xyz, r2.xxxx, r7.xyzx, r6.xyzx
  lt r2.x, r6.x, l(1.000000)
  movc r2.x, r2.x, l(0), r6.x
  movc r2.x, r2.z, r2.x, r6.x
  add r2.x, r2.x, r2.x
  iadd r7.xyw, r1.xxxx, l(2, 1, 0, 3)
  mov r1.w, r7.y
  ld_indexable(texture2d)(float,float,float,float) r8.xyzw, r1.wyzz, t1.xyzw
  ...
```
## Post #24
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2021-04-18T21:46:48+00:00
- Post Title: Re: Project Cars 2

Hi,

Can anyone help figure it out.
These are the car files Acura NSX racing 1997 and Chevrolet Corvette C8r from "PS4" - PC3.
[https://sharemods.com/tl3vvn3atq0u/Test.zip.html](https://sharemods.com/tl3vvn3atq0u/Test.zip.html)

But they do not open in SMS import.  Try to open. Previously, models were usually opened. What could be the reason?
