## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-04-12T23:49:07+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

So, I'm following this tutorial by MirrorMan to get the Kingdom Hearts 2 animations to FBX.

Some links are broken, I can eventually resupply to the best of my ability.

When viewing them, however, I believe there are some issues with them, since sometimes they appear "frozen".

> You need Revelation's version of khkh_xldMii, mediafire.com/download/xym4yaa75qjvdpt/Release.7z
>
> Then for best results, download the latest version of khkh_xldMii, http://kkdf2.sakura.ne.jp/pcsx2lair/Release_13.7z (password is 2).
>
> Replace the ef1Declib.dll from Release 13 with the dll from Revelation's version.
>
> Then, download Noesis from richwhitehouse.com/index.php?content=inc_projects.php.
>
> Then, download Revelation's special version of his KH2 plugins for Noesis at code.google.com/p/noesis-plugins-official/source/browse/trunk/revelation/kingdom_hearts_2_v2.zip and put them in Noesis's plugins folder.
>
> You can view animations with khkh_xldMii by dragging a MDLX into the program (as long as it has an MSET of the same name in that folder to animate it) and export them with the ASET exporter.
>
> You'll have to dig through all the MSETs until you find some that correspond to the model.
>
> You can also use ANB animations by converting them to MSETs with http://kkdf2.sakura.ne.jp/pcsx2lair/expack1anbz2.7z (password is ][).
>
> 
>
> Once the animations are in ASET format, load Noesis and view the model you just exported the ASET for.
>
> Noesis will automatically load the ASET of the same name as the MDLX you just opened if they're in the same folder.
>
> With Noesis's export function, you can then export the ASET animations to a variety of other animation formats.
>
> In order to extract the most ANBs and MSETs, I'd suggest using the most sophisticated KH2FM file extractor, Govanify's KH2FM Toolkit at https://github.com/GovanifY/KH2FM_Toolkit/

Can anyone help?
## Post #2
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2019-04-16T11:45:36+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

Gosh, I'm sorry you're having problems with my tutorial. I wish I knew how to solve it, but I haven't done this in a while. I think the only links that're broken are revelation's plugins, which can now be found at [https://github.com/mrpostiga/noesis-plu ... revelation](https://github.com/mrpostiga/noesis-plugins-official/tree/master/revelation) .
## Post #3
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-04-16T12:11:15+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

No no, not a problem with your tutorial, but with the viewer - the one where you're supposed to drop the models in, thanks!

Animations are weird there, they freeze after a bit, and saving them doesn't appear to work.
## Post #4
- Username: Alo3
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 09, 2019 7:25 am
- Post datetime: 2019-05-08T23:30:19+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

i was following you along the tutorial but i cant load the animations of the ASET im using Noesis 44 so i dont know if thats the reason it doesnt work also i used Release instead of Release 13 because 13 doesnt have ASET export 
im using P_EX100
u know what i did wrong or missing?
## Post #5
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2019-05-10T17:20:38+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

> Reply from Alo3 ↑Thu May 09, 2019 7:30 am at Thu May 09, 2019 7:30 am
>
> 
I was following you along the tutorial but I can't load the animations of the ASET. I'm using Noesis 44 so I don't know if that's the reason it doesn't work also I used Release instead of Release 13 because 13 doesn't have ASET export.
I'm using P_EX100.
You know what I did wrong or missing?
I'm pretty sure the Noesis version wouldn't affect ASET support, especially 4.4, since it's the latest version. The only Noesis-side problem would be if you're using the older version of the KH2 plugin, which doesn't have ASET support, instead of the latest version, which does.
## Post #6
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-05-14T17:51:24+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

I'm sorry, can you elaborate?
## Post #7
- Username: TheFutureTimeline
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 28, 2021 4:17 pm
- Post datetime: 2021-03-28T08:35:17+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

> Reply from Devilot ↑Tue Apr 16, 2019 8:11 pm at Tue Apr 16, 2019 8:11 pm
>
> 
No no, not a problem with your tutorial, but with the viewer - the one where you're supposed to drop the models in, thanks!

Animations are weird there, they freeze after a bit, and saving them doesn't appear to work.

Having the same issue. Has anyone found a fix?
## Post #8
- Username: TheFutureTimeline
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 28, 2021 4:17 pm
- Post datetime: 2021-03-28T10:59:52+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

> Reply from TheFutureTimeline ↑Sun Mar 28, 2021 4:35 pm at Sun Mar 28, 2021 4:35 pm
>
> 
Devilot wrote: ↑Tue Apr 16, 2019 8:11 pm
No no, not a problem with your tutorial, but with the viewer - the one where you're supposed to drop the models in, thanks!

Animations are weird there, they freeze after a bit, and saving them doesn't appear to work.


Having the same issue. Has anyone found a fix?

It turns out the viewer itself is actually broken. I found a fixed version you can use here:
[https://mega.nz/#!WNN0iaCK!SdCE5F_8qKKI ... u3DO0Pehb8](https://mega.nz/#!WNN0iaCK!SdCE5F_8qKKI8s1p0paUKhRQUq44Xq0eAu3DO0Pehb8)

The problem I'm having now is getting noesis to export the anims alongside the model
## Post #9
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2021-03-28T22:20:06+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

Maybe the PC release will be helpful?
## Post #10
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2021-09-24T22:41:42+00:00
- Post Title: Correct way to export Kingdom Hearts 2 Final Mix animations to FBX?

Hi. I’m trying to find a Noesis plugins  in for Kh2 ps3 Version 

thanks
