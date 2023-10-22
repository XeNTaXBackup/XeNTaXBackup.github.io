## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-06T22:07:52+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Hi guys! Here's maxscript for Dead Rising 4 (PC 2017) 3ds max 2009-2014. Script is for rigged (skinned) meshes, haven't tried static ones because wasn't interested, but maybe will make/update script for them too. Script is quite slow, because of amount of bones and meshes, LODs. Prepare for some wating xD
## Post #2
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2017-11-11T16:12:48+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

WOW, I was beginning to think modders had abandoned this game, there's so much room for cool adjustments if somebody could figure out how to apply mods.

Script crashes when trying to extract Frank, it only works on the in-game npc models.  Any plans to continue working on this as a model export/import?

---fseek f (bigInfo[(findItem names "SharedZPassSecondCommandBuffer")][3]) #seek_set		

"--runtime error: array index must be positive number, got: 0"

This was on 3DSMax 2016. My guess is that Frank has a different skeleton since he's the 1st-person character (was same setup in DR3).
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-11T16:18:50+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Import yes, export no   What is the name of the file which is crashing? I have an update for this script already. But might check this problematic model with it first, before publishing it
## Post #4
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2017-11-11T16:24:03+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

I added a few more details above, the file I tried importing was Frank's default head:  head_frank_m0.mdl
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-11T16:26:45+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Strange, I dont' have this file. Could you send it too me? Via PM
## Post #6
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2017-11-11T16:45:36+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Check pm.  I've never been able to figure out DR3 or DR4 based on their principle of model rendering, but I pwned DR2:OTR inside and out and CC uses many of the same techniques in it, with some adjustments.  Would be great to be able to mod DR4 as it was a total half-assed rushed product and there's lots of room for 'fixes'.
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-11T16:56:56+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Thank you for the files, my updated script thankfully work with those files.
## Post #8
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2017-11-11T17:04:23+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Great!  let me know when you release the new script.

If I can help figure something out in any way just drop me a line.  As I said, ultimate goal would be to re-inject models back into this game and I know it's possible based on how the previous games worked (and RE6 uses the same engine and it had already been modded).  The only hurdles would be encryption and bucket variables.
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-11T17:28:15+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Of course export thing is possible, not sure who's gonna take this task. But definately it should be a DR fan of some sort
## Post #10
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2017-11-11T20:33:47+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Great- can you post your new script?
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-12T12:34:37+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Sure, here's the script.

EDIT: Try this one. Should be stable with your max

EDIT: Update
[Dead_Rising_4_UPD_A.7z](https://xentaxbackup.github.io/file/13568_Dead_Rising_4_UPD_A.7z)
## Post #12
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2017-11-13T04:50:33+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Thanks zaramot!

Hmm, I'm still getting errors when importing.  I'm using 3dsMax 2016 and trying to open head_frank_m0.mdl.

The error is --Unknown property: "count" in undefined

If I try to run the script again I see this error:

-- Unable to convert: [0.843196,-0.0152287,0] to type: String

Essentially it locks Max up and I re-open it.  But anything else I try importing gives me the "count" undefined error again.
## Post #13
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-11-14T16:05:50+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Script work perfect
Phanx
How convert .Tex to any format
## Post #14
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-15T10:23:26+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Yeah, here's tool for textures
[DR4_TEX.7z](https://xentaxbackup.github.io/file/13550_DR4_TEX.7z)
## Post #15
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-11-15T15:02:55+00:00
- Post Title: Dead Rising 4 model import maxscript (.mdl .tex)

Zaramot phanx
your script .tex work perfect

Dead_Rising 4 UPD sometimes when importing produces an error then you choose Scripting-Run Script
i choose Scripting-Open Script in window script choose Tools-Evaulate All
head_frank_m0.mdl imported without problems

Sorry for bad English i am Russian use Google Translate

Zaramot thanks again.
## Post #16
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-15T15:24:11+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

I'm russian too, don't worry I understand what you said, you're doing right.
## Post #17
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-11-20T06:23:39+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Hi! Awesome job with your script, but there are problems with Hair/lashes/beard uvs.. any suggestion?
Thank you again
## Post #18
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-20T08:30:37+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Thank you! Sure, just provide the file with bad uv's and I'll try my best to fix it:)
## Post #19
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-11-20T11:32:23+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Привет у меня проблемы модель cast07a.mdl (Dead Rising 4\data\models\npcs) скрипт загружает не полностью модель, так же и модель cast13.mdl
А у модели cast10b.mdl у волос и ресниц поврежденны

[https://1drv.ms/u/s!Amg1SaLumVp4tVGiuJymSKQ_NQ0n](https://1drv.ms/u/s!Amg1SaLumVp4tVGiuJymSKQ_NQ0n)
## Post #20
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-20T13:35:49+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Okay, I have an update. Script should import uv's now. The problem was because of two uv's lareys. Though, I might fixed it for all of models, but still there's a chance, that I didn't. I fixed 2 of 7 types, since I don't know for sure if others 5 using same method too. I think it's not the happy end xD

If any part of rigged meshes would have "broken" uv's. Do this simple procedure:
Select the model and add the "Unwrap UVW" modifier above it and then press "Edit" button
Change the channel from 1 to 2 and press the button "Reset UVWs", when prompted, press Yes. 
This will display the second texture coordinates set. Second Uv's channel

P.S. As about missing parts, not sure that script is skipping something, maybe these characters using parts from other models? Maybe there are some default ones. I checked, and there no extra data for import.
[Dead_Rising_4_UPD_B.7z](https://xentaxbackup.github.io/file/13572_Dead_Rising_4_UPD_B.7z)
## Post #21
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-11-20T15:35:38+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

> Reply from zaramot
>
> Okay, I have an update. Script should import uv's now. The problem was because of two uv's lareys. Though, I might fixed it for all of models, but still there's a chance, that I didn't. I fixed 2 of 7 types, since I don't know for sure if others 5 using same method too. I think it's not the happy end xD

If any part of rigged meshes would have "broken" uv's. Do this simple procedure:
Select the model and add the "Unwrap UVW" modifier above it and then press "Edit" button
Change the channel from 1 to 2 and press the button "Reset UVWs", when prompted, press Yes. 
This will display the second texture coordinates set. Second Uv's channel

P.S. As about missing parts, not sure that script is skipping something, maybe these characters using parts from other models? Maybe there are some default ones. I checked, and there no extra data for import.

 sorry why i have to deal with channels? A script is supposed to do all the job
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-11-20T16:51:32+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

> Reply from fil1969
>
> zaramot wrote:Okay, I have an update. Script should import uv's now. The problem was because of two uv's lareys. Though, I might fixed it for all of models, but still there's a chance, that I didn't. I fixed 2 of 7 types, since I don't know for sure if others 5 using same method too. I think it's not the happy end xD

If any part of rigged meshes would have "broken" uv's. Do this simple procedure:
Select the model and add the "Unwrap UVW" modifier above it and then press "Edit" button
Change the channel from 1 to 2 and press the button "Reset UVWs", when prompted, press Yes. 
This will display the second texture coordinates set. Second Uv's channel

P.S. As about missing parts, not sure that script is skipping something, maybe these characters using parts from other models? Maybe there are some default ones. I checked, and there no extra data for import. sorry why i have to deal with channels? A script is supposed to do all the jobscript is open sourced — you are welcome to add any feature you want.
## Post #23
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-11-20T17:32:18+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

> Reply from Tosyk
>
> fil1969 wrote:zaramot wrote:Okay, I have an update. Script should import uv's now. The problem was because of two uv's lareys. Though, I might fixed it for all of models, but still there's a chance, that I didn't. I fixed 2 of 7 types, since I don't know for sure if others 5 using same method too. I think it's not the happy end xD

If any part of rigged meshes would have "broken" uv's. Do this simple procedure:
Select the model and add the "Unwrap UVW" modifier above it and then press "Edit" button
Change the channel from 1 to 2 and press the button "Reset UVWs", when prompted, press Yes. 
This will display the second texture coordinates set. Second Uv's channel

P.S. As about missing parts, not sure that script is skipping something, maybe these characters using parts from other models? Maybe there are some default ones. I checked, and there no extra data for import. sorry why i have to deal with channels? A script is supposed to do all the jobscript is open sourced — you are welcome to add any feature you want.
 if i have the skills i will make a my tool! what shitty answer is thi!s!|!!  If someone released a tool is supposed he emprove it.. otherwhise every one can do it..
## Post #24
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-11-20T17:46:31+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

> Reply from zaramot
>
> Okay, I have an update. Script should import uv's now. The problem was because of two uv's lareys. Though, I might fixed it for all of models, but still there's a chance, that I didn't. I fixed 2 of 7 types, since I don't know for sure if others 5 using same method too. I think it's not the happy end xD

If any part of rigged meshes would have "broken" uv's. Do this simple procedure:
Select the model and add the "Unwrap UVW" modifier above it and then press "Edit" button
Change the channel from 1 to 2 and press the button "Reset UVWs", when prompted, press Yes. 
This will display the second texture coordinates set. Second Uv's channel

P.S. As about missing parts, not sure that script is skipping something, maybe these characters using parts from other models? Maybe there are some default ones. I checked, and there no extra data for import.
  Is awesome now! Thank you very much for the update!!!!!
## Post #25
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-11-20T18:34:40+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

> Reply from fil1969
>
> If someone released a tool is supposed he emprove it..no one supposed to do anything by you wish, show some respect to person who contributed — he spent his time using his skills for your fun. be wise in your words and patient.
## Post #26
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-11-20T18:43:19+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

> Reply from Tosyk
>
> fil1969 wrote:If someone released a tool is supposed he emprove it.. no one supposed to do anything by you wish, show some respect to person who contributed — he spent his time using his skills for your fun. be wise in your words and patient.
 i respect him a lot ( read my comments) i don't respect people like you who wants to be a professor!
## Post #27
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-11-20T18:47:56+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Привет у меня проблемы с моделью classic_frank_npc.mdl при импорте в 3d max кости ног не работают 
Ссылка на модель если нужно - [https://1drv.ms/u/s!Amg1SaLumVp4tVLg-rHXnG4B3D-7](https://1drv.ms/u/s!Amg1SaLumVp4tVLg-rHXnG4B3D-7)
## Post #28
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-11-20T19:09:58+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

> Reply from fil1969
>
> Tosyk wrote:fil1969 wrote:If someone released a tool is supposed he emprove it.. no one supposed to do anything by you wish, show some respect to person who contributed — he spent his time using his skills for your fun. be wise in your words and patient.
 i respect him a lot ( read my comments) i don't respect people like you who wants to be a professor!okay, just don't cry — no one need your tears.
## Post #29
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-20T19:30:51+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Here's updated version for your Frank model, should work fine. Also, here's a video, smal tutorial how to restore uv's when they arern't correct or missing.

[https://www.youtube.com/watch?v=YzKvKea ... e=youtu.be](https://www.youtube.com/watch?v=YzKvKea1CXU&feature=youtu.be)
[Dead_Rising_4_UPD_B.7z](https://xentaxbackup.github.io/file/13571_Dead_Rising_4_UPD_B.7z)
## Post #30
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2017-11-20T21:01:48+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Thank you so much for this zaramot, the script is awesome! I really appreciate your time  

By the way, about the classic Frank model not working (above), I have found there are inherent problems with some of the models themselves.  Some are not skinned properly (in-game), some models use multiple instances of the same mesh (my guess would be because one may have default textures, another may have special glossiness/tinting/specular etc, it's a pretty hack way by CV to get some effects to look good, but it's a huge memory hog), and some are incomplete.

The legs not working may be Capcom's fault, especially if it's not officially in game yet
## Post #31
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-11-20T22:09:20+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Thank you so much for script
## Post #32
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2021-08-25T08:28:12+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Sorry for post it too late, but it's possible to get prop/vehicle support? it only imports the skeleton. I can even pay?
## Post #33
- Username: edwardnorton
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 02, 2023 1:23 am
- Post datetime: 2023-01-01T17:25:40+00:00
- Post Title: Re: Dead Rising 4 model import maxscript (.mdl .tex)

Hi there, any updates on static mesh export?
