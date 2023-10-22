## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-06-08T13:53:17+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

A tool for previewing/exporting animations from some games that use the ACL plugin for UE4. Apparently, UE Viewer doesn't support the animations atm. This was a request from a friend. So, I thought I might as well share it here too. Not that I think anyone will use it 

Some example animations




How to use

Set Skeleton
You don't need this step for Dislyte character models. Their skeleton is set by default. For any other game, you have to select the skeleton file (uasset) of the model you will be loading later.

Example: For loading a Mir 4 character skeleton, I will click Set Skeleton and select Pca_01_Skeleton.uasset.

Load Model/Animation

0) Everything  you need for extracting the models is here: [https://www.gildor.org/smf/index.php?topic=7760.0](https://www.gildor.org/smf/index.php?topic=7760.0)
1) Export the character model as GLTF using UE Viewer
2) Using Noesis, convert GLTF to NUX with the included NUX script
3) Load NUX in DislyteAnimViewer
4) Load the animation you want (uasset  or uexp)
5) Export the animation to NUX
6) You can load the exported file in Noesis and convert it to any format you want

Download :  [https://www.mediafire.com/file/53c2rzil ... r.rar/file](https://www.mediafire.com/file/53c2rzilmvtfz7a/ACLViewer.rar/file)

Supported Games
- Apex Legends Mobile
- Dislyte
- Life is Strange 2 (Don't know which episodes)
- Mir 4
- Ni no Kuni: Cross Worlds
- Valorant (partial)

Any other game might or might not work. Depends on the UE4 version used.
## Post #2
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-06-08T23:10:10+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

Oh yes finally someone decided to take care of this ! 
Very nice animations, thank you a lot
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-06-09T21:27:52+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

NEW GAMES: Mir 4, Ni no Kuni: Cross Worlds

The animation format is the same as Dislyte for these games. They can be loaded with the new tool update. However, the skeleton file for them must be loaded beforehand, using the Set Skeleton button. I have updated the tutorial in the first post explaining how to do that.

Ni no Kuni animation preview



Mir 4 animation preview



Edit: Made a small update for fixing some animations that aren't loading. Especially for Ni no Kuni.
## Post #4
- Username: zxhxy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 08, 2020 4:27 pm
- Post datetime: 2021-06-13T02:17:32+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

1
## Post #5
- Username: FDArtZz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 07, 2019 1:54 am
- Post datetime: 2021-06-20T20:32:59+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

Haay, first your work is amazing!  

Second Valorant started also to use ACL for some of there animations and i wanted to ask if you can may help to get a Umodel version that support ACL OR get your tool to support valorant?

Would be super happy if I here back from you even when you say no.
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-06-20T22:04:17+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

> Reply from FDArtZz ↑Mon Jun 21, 2021 4:32 am at Mon Jun 21, 2021 4:32 am
>
> 
Second Valorant started also to use ACL for some of there animations and i wanted to ask if you can may help to get a Umodel version that support ACL OR get your tool to support valorant?
I can get my tool to support it at some point if anyone PMs me samples with matching model/skeleton. I probably won't download the game just for this.
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-06-21T13:35:17+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

UPDATE: Valorant, Apex Legends Mobile, Life is Strange 2

The above games are supported based on the samples I have, but they aren't thoroughly tested. For Valorant only the "_Cosmetic" animations work. I don't know the problem with the other animations. As always the download link is updated in the first post.


Valorant



Life is Strange 2
## Post #8
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-21T14:36:53+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

> Reply from akderebur ↑Mon Jun 21, 2021 9:35 pm at Mon Jun 21, 2021 9:35 pm
>
> 
UPDATE: Valorant, Apex Legends Mobile, Life is Strange 2

The above games are supported based on the samples I have, but they aren't thoroughly tested. For Valorant only the "_Cosmetic" animations work. I don't know the problem with the other animations. As always the download link is updated in the first post.

Awesome job !
## Post #9
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-21T15:13:02+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

I live for the day that we'll be able to export shape keys successfully as well from UE games.
## Post #10
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-21T19:13:57+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

> Reply from akderebur ↑Mon Jun 21, 2021 9:35 pm at Mon Jun 21, 2021 9:35 pm
>
> 
UPDATE: Valorant, Apex Legends Mobile, Life is Strange 2

The above games are supported based on the samples I have, but they aren't thoroughly tested. For Valorant only the "_Cosmetic" animations work. I don't know the problem with the other animations. As always the download link is updated in the first post.

Wow this was fast, thank you so much akderebur!
## Post #11
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-06-21T20:42:53+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

> Reply from dimis9138 ↑Mon Jun 21, 2021 11:13 pm at Mon Jun 21, 2021 11:13 pm
>
> 
I live for the day that we'll be able to export shape keys successfully as well from UE games.
Morphs export is supported in third-party umodel build since middle of 2020, when oscateexor created it. I've recently ported those changes to more actual version of umodel by request.
## Post #12
- Username: cesm20
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jun 03, 2013 5:03 am
- Post datetime: 2021-06-24T13:37:15+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

Thank you so much for providing support for Life is Strange 2 acl compressed animations even before i sent you the samples for support, i was waiting a long since for someone to implement support for this, by the way Dontnod only started using the ACL plugin on episode 4 onwards, so for that game its only episode 4 and 5 try updating the info in there mentioning that since episodes 1-3 on Life is Strange 2 are supported by umodel.

UPDATE : i just found that Beyond a Steel Sky (older version that uses unreal engine 4.24, i am unsure if the newer version using 4.26 is compatible or not) now works perfectly after this last update! Hope that later gets added to the compatibilty list.
## Post #13
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-07-01T03:08:00+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

The recently released Marvel Future Revolution also uses ACLs.
It was pre-released in Canada, but I got it via VPN. 

If someone else hasn't provided the sample, I will.
(wrong) Note that the skeleton is probably included in the mesh.uasset file and may not need to set it. (wrong)
Animation also works in part. Perhaps the difference in compression level?

*EDIT
thanks akderebur, I'll check it!
## Post #14
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-01T09:02:50+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

> Reply from einherjar007 ↑Thu Jul 01, 2021 11:08 am at Thu Jul 01, 2021 11:08 am
>
> 
Note that the skeleton is probably included in the mesh.uasset file and may not need to set it.
Animation also works in part. Perhaps the difference in compression level?
I have received some samples for the Black Widow model/animations. The skeleton is a separate file. I have noticed a small bug with the tool. For the skeleton the extensions needs to be lower-case. Like NOT "BLACKWIDOW_SKELETON.UASSET", but "BLACKWIDOW_SKELETON.uasset". If you have a skeleton set error, try renaming the extensions.

Other than that the animations seem to work with the current tool.
## Post #15
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2021-09-05T01:43:47+00:00
- Post Title: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc]

> Reply from akderebur ↑Thu Jul 01, 2021 5:02 pm at Thu Jul 01, 2021 5:02 pm
>
> 
einherjar007 wrote: ↑Thu Jul 01, 2021 11:08 am
Note that the skeleton is probably included in the mesh.uasset file and may not need to set it.
Animation also works in part. Perhaps the difference in compression level?

I have received some samples for the Black Widow model/animations. The skeleton is a separate file. I have noticed a small bug with the tool. For the skeleton the extensions needs to be lower-case. Like NOT "BLACKWIDOW_SKELETON.UASSET", but "BLACKWIDOW_SKELETON.uasset". If you have a skeleton set error, try renaming the extensions.

Other than that the animations seem to work with the current tool.

I havent been getting the animations to work for this game. Not sure if im doing something wrong
## Post #16
- Username: Hammoda
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 13, 2021 10:41 pm
- Post datetime: 2021-09-13T14:50:59+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from akderebur ↑Tue Jun 08, 2021 9:53 pm at Tue Jun 08, 2021 9:53 pm
>
> 
A tool for previewing/exporting animations from some games that use the ACL plugin for UE4. Apparently, UE Viewer doesn't support the animations atm. This was a request from a friend. So, I thought I might as well share it here too. Not that I think anyone will use it 

Some example animations




How to use

Set Skeleton
You don't need this step for Dislyte character models. Their skeleton is set by default. For any other game, you have to select the skeleton file (uasset) of the model you will be loading later.

Example: For loading a Mir 4 character skeleton, I will click Set Skeleton and select Pca_01_Skeleton.uasset.

Load Model/Animation

0) Everything  you need for extracting the models is here: https://www.gildor.org/smf/index.php?topic=7760.0
1) Export the character model as GLTF using UE Viewer
2) Using Noesis, convert GLTF to NUX with the included NUX script
3) Load NUX in DislyteAnimViewer
4) Load the animation you want (uasset  or uexp)
5) Export the animation to NUX
6) You can load the exported file in Noesis and convert it to any format you want

Download :  https://www.mediafire.com/file/53c2rzil ... r.rar/file

Supported Games
- Apex Legends Mobile
- Dislyte
- Life is Strange 2 (Don't know which episodes)
- Mir 4
- Ni no Kuni: Cross Worlds
- Valorant (partial)

Any other game might or might not work. Depends on the UE4 version used.

Will you support Lost ark? Ueviewer already updated to extract skeleton and etc, but not Anim since its ACL and its upk..
## Post #17
- Username: polaqwym
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 16, 2021 11:10 am
- Post datetime: 2021-09-22T01:05:54+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

Hey!   

I followed all the steps exactly, and upon setting the skeleton and importing the .uasset animation, my model becomes inflated. Any reason for this?
(Kena from Kena: Bridge of Spirits) https://ibb.co/sPDywkv

In this forum post on Gildor's forum, it says the software should be supportive of Kena; https://www.gildor.org/smf/index.php/to ... l#msg40562
## Post #18
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2021-09-24T16:12:23+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

Mine is somehow inflated like the guy said above when loading the anims of Kena : Bridge of Spirits  


Here's the sample of Kena, the original files extracted by umodel special build by spiritovod in this post.You may need to download this version's umodel to open the assets and the engine version of this game is 4.25:
[https://www.gildor.org/smf/index.php/to ... l#msg40562](https://www.gildor.org/smf/index.php/topic,7805.msg40562.html#msg40562)

Samples: [https://mega.nz/file/FCIVRQbI#zWat327BC ... GZ0_ecii88](https://mega.nz/file/FCIVRQbI#zWat327BC-A7CrtsmijA5PxTkpQbEGvmXGZ0_ecii88) (137.6MB)
## Post #19
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-09-24T23:47:31+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from Kanbara ↑Sat Sep 25, 2021 12:12 am at Sat Sep 25, 2021 12:12 am
>
> 
Mine is somehow inflated like the guy said above when loading the anims of Kena : Bridge of Spirits

Yea, the issue seems to be related to scale keys in the animation which indirectly affects the translations. I have a dirty fix in progress, but I will test it a bit more before releasing it. Once the scaling is sorted, the animation is actually fine:
## Post #20
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2021-09-25T00:15:38+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from akderebur ↑Sat Sep 25, 2021 7:47 am at Sat Sep 25, 2021 7:47 am
>
> 
Kanbara wrote: ↑Sat Sep 25, 2021 12:12 am
Mine is somehow inflated like the guy said above when loading the anims of Kena : Bridge of Spirits


Yea, the issue seems to be related to scale keys in the animation which indirectly affects the translations. I have a dirty fix in progress, but I will test it a bit more before releasing it. Once the scaling is sorted, the animation is actually fine:

Oh, thanks god! Looking forward to the upcoming release!!
## Post #21
- Username: Hammoda
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 13, 2021 10:41 pm
- Post datetime: 2021-09-26T10:28:18+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

Here is a sample file from lost ark upk with sk and anim, if possible to support the file best regards

[U81MP2PG1BZZE7UDU364SSP.rar](https://xentaxbackup.github.io/file/20891_U81MP2PG1BZZE7UDU364SSP.rar)
## Post #22
- Username: adam0000
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jul 23, 2015 6:34 am
- Post datetime: 2021-09-26T23:27:48+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from akderebur ↑Thu Jul 01, 2021 5:02 pm at Thu Jul 01, 2021 5:02 pm
>
> 
einherjar007 wrote: ↑Thu Jul 01, 2021 11:08 am
Note that the skeleton is probably included in the mesh.uasset file and may not need to set it.
Animation also works in part. Perhaps the difference in compression level?

I have received some samples for the Black Widow model/animations. The skeleton is a separate file. I have noticed a small bug with the tool. For the skeleton the extensions needs to be lower-case. Like NOT "BLACKWIDOW_SKELETON.UASSET", but "BLACKWIDOW_SKELETON.uasset". If you have a skeleton set error, try renaming the extensions.

Other than that the animations seem to work with the current tool.
How can i extract the game animation files?
I can't extract the animation files using umodel tool
## Post #23
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-09-27T13:30:14+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from Hammoda ↑Sun Sep 26, 2021 6:28 pm at Sun Sep 26, 2021 6:28 pm
>
> 
Here is a sample file from lost ark upk with sk and anim, if possible to support the file best regards

I will take a look when I have the time. I might think about adding support if it isn't too different from UE4 stuff.
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-09-27T22:44:05+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

Custom Version: Kena: Bridge of Spirits

This is probably not the best fix, but most of the Kena animations seem to be better. There are still some problematic ones, but I thought I should release this before losing interest forever 

Download: [https://www.mediafire.com/file/68z78ynd ... a.rar/file](https://www.mediafire.com/file/68z78yndo5ci9v4/ACLAnimViewer_Kena.rar/file)
## Post #25
- Username: crypt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 25, 2021 9:33 am
- Post datetime: 2021-09-28T20:03:50+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

Hello, I am testing the steps you mention, but since the skeleton is deformed when applying the animation to the model.nux does this monster, some solution to correct the skeleton.
Thank you
## Post #26
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-09-29T00:26:32+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from crypt ↑Wed Sep 29, 2021 4:03 am at Wed Sep 29, 2021 4:03 am
>
> 
since the skeleton is deformed

The skeleton was fine for me. Maybe it has something to do with your umodel version. It isn't something that I can/will fix.
## Post #27
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2021-09-29T06:26:34+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from crypt ↑Wed Sep 29, 2021 4:03 am at Wed Sep 29, 2021 4:03 am
>
> 
Hello, I am testing the steps you mention, but since the skeleton is deformed when applying the animation to the model.nux does this monster, some solution to correct the skeleton.
Thank you

Make sure that you didn't use the umodel named in something like "kena_morph" to export the model. Just use the other one to do it, otherwise the skeleton won't match up with the momdel then.
And I have successfully extracted the animations of kena and the tool works like a charm!
## Post #28
- Username: crypt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 25, 2021 9:33 am
- Post datetime: 2021-09-29T17:08:14+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

well, it still doesn't work, the original umodel when opening the mesh crashes, the only solution is to use a modified umodel_kena_morphs_export or umodel_kena, I renamed it only to umodel but it doesn't work, the skeleton remains the same.
## Post #29
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-09-29T17:43:05+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

@crypt: It was already answered in the original topic at gildor's forum, you just ignored it and didn't bother to read the whole topic in the first place. TLDR: Do not use armature when exporting morphs with morphs build, re-use default armature (skeleton) by exporting a model with base version of specific umodel build - or just don't use morphs at all.
## Post #30
- Username: crypt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 25, 2021 9:33 am
- Post datetime: 2021-09-29T21:58:52+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

Hi, first of all, if I look at the topic a lot in both forums, but these options and way of extracting are new for me, I'm sorry I'm not as clever as some of them jjaajaj, if I don't understand something I ask. In the end I was able to apply the animation correctly, I just need to polish it.
## Post #31
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2021-10-30T16:03:34+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

@ akderebur
Could you take a look at the files for "Blade & Soul: Revolution (Korean) version?" After the latest update they use ACL compression but loading in the animation crashes the ACLanim viewer.
Someone provided some sample files on Gildor's forum:
[https://www.gildor.org/smf/index.php/to ... l#msg41629](https://www.gildor.org/smf/index.php/topic,6432.msg41629.html#msg41629)

Regards,
## Post #32
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-11-01T07:17:57+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from WollieWoltaz ↑Sun Oct 31, 2021 12:03 am at Sun Oct 31, 2021 12:03 am
>
> 
loading in the animation crashes the ACLanim viewer.

They are using an older version of ACL which is not supported by the tool.
## Post #33
- Username: aza07
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 18, 2017 10:30 am
- Post datetime: 2021-11-15T19:25:07+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

Thanks you so much for this tool, since the time I was seraching somethings for the ACL animation ^^
unfortunatly i can't use it for the only game i was wanting to extract animation , and even if it's listed there, for me "Life Is Strange 2" doesnt work 

I can't set the skeleton , I always receive "skeleton error", for the same model you used as the preview of LIS2 here.

And without that the animation is only on the head, I followed all the Instruction, download even the umodel special version you mentioned,
but nope nothings is working 
Do you know why ?,  I can send you the uasset file of the model for the skeleton the NUX version and the uasset anim file too

Thanks again ,really appreciated
## Post #34
- Username: xdirec
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 29, 2021 11:56 pm
- Post datetime: 2021-12-22T14:55:15+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

halow guys please help if i export in ue viewer coming bin file and my noesis dont have gltf im noob new sir
someone have discord?
error #
FPakFile::Serialize: file=/Game/Characters/PC/Pc_Pet/Dog02/Pet_Dog02_InGame.uasset <- TArray::SerializeSimple <- SerializeBulkArray <- FMultisizeIndexContainer<< <- FStaticLODModel4::SerializeStreamedData <- FStaticLODModel4::SerializeRenderItem <- TArray::Serialize: 0/1 <- USkeletalMesh4::Serialize <- LoadObject: SkeletalMesh4'Pet_Dog02_InGame.Pet_Dog02_InGame', pos=14D3, ver=518/0 (unversioned), game=ue4.24 <- UObject::EndLoad <- LoadWholePackage: /Game/Characters/PC/Pc_Pet/Dog02/Pet_Dog02_InGame.uasset <- CUmodelApp::ShowPackageUI <- Main: umodel_build=1556 based
## Post #35
- Username: xdirec
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 29, 2021 11:56 pm
- Post datetime: 2022-02-08T08:59:26+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

halow sir can u share script for glft2 viewer in noesis please
## Post #36
- Username: xdirec
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 29, 2021 11:56 pm
- Post datetime: 2022-02-08T09:00:35+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from akderebur ↑Tue Jun 08, 2021 9:53 pm at Tue Jun 08, 2021 9:53 pm
>
> 
A tool for previewing/exporting animations from some games that use the ACL plugin for UE4. Apparently, UE Viewer doesn't support the animations atm. This was a request from a friend. So, I thought I might as well share it here too. Not that I think anyone will use it 

Some example animations




How to use

Set Skeleton
You don't need this step for Dislyte character models. Their skeleton is set by default. For any other game, you have to select the skeleton file (uasset) of the model you will be loading later.

Example: For loading a Mir 4 character skeleton, I will click Set Skeleton and select Pca_01_Skeleton.uasset.

Load Model/Animation

0) Everything  you need for extracting the models is here: https://www.gildor.org/smf/index.php?topic=7760.0
1) Export the character model as GLTF using UE Viewer
2) Using Noesis, convert GLTF to NUX with the included NUX script
3) Load NUX in DislyteAnimViewer
4) Load the animation you want (uasset  or uexp)
5) Export the animation to NUX
6) You can load the exported file in Noesis and convert it to any format you want

Download :  https://www.mediafire.com/file/53c2rzil ... r.rar/file

Supported Games
- Apex Legends Mobile
- Dislyte
- Life is Strange 2 (Don't know which episodes)
- Mir 4
- Ni no Kuni: Cross Worlds
- Valorant (partial)

Any other game might or might not work. Depends on the UE4 version used.

halow sir can u share glft2 script in noesis please
## Post #37
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2022-02-09T11:20:18+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

AFAIK You don't need a script for importing gltf into noesis. It's supported by default.
## Post #38
- Username: xdirec
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 29, 2021 11:56 pm
- Post datetime: 2022-02-09T15:23:00+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from WollieWoltaz ↑Wed Feb 09, 2022 7:20 pm at Wed Feb 09, 2022 7:20 pm
>
> 
AFAIK You don't need a script for importing gltf into noesis. It's supported by default.

After i extract the glft 2 coming 2 file 1 bin 1 3d then when iwant to view in noesis im give error cannot view
## Post #39
- Username: xdirec
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 29, 2021 11:56 pm
- Post datetime: 2022-02-11T08:04:30+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from WollieWoltaz ↑Wed Feb 09, 2022 7:20 pm at Wed Feb 09, 2022 7:20 pm
>
> 
AFAIK You don't need a script for importing gltf into noesis. It's supported by default.

can you help me please realy need only the pet in mir4 iwant to pull out with animation. you have discord
i extract then idont know how to load the anim in nux viewer
## Post #40
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2022-02-12T13:23:42+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

Hmm everything works fine for me. Strange that you can't load the .gltf file into Noesis.. maybe it got corrupted dunno.
I have discord yes... send me a PM with your discord tag and i'll send you a request!
## Post #41
- Username: xdirec
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 29, 2021 11:56 pm
- Post datetime: 2022-02-14T03:09:37+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from WollieWoltaz ↑Sat Feb 12, 2022 9:23 pm at Sat Feb 12, 2022 9:23 pm
>
> 
Hmm everything works fine for me. Strange that you can't load the .gltf file into Noesis.. maybe it got corrupted dunno.
I have discord yes... send me a PM with your discord tag and i'll send you a request!
Done
Error when exporting the glft2 no animation
Isend dm
## Post #42
- Username: zxhxy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 08, 2020 4:27 pm
- Post datetime: 2022-02-17T17:04:59+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

I noticed that some of Dislyte's character directories had skeleton files, while others only had Physics files

After opening the NUX model file with the tool, must load the skeleton file to play the animation correctly

So which step am I missing?
## Post #43
- Username: SCArkadia
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 7:50 am
- Post datetime: 2022-05-03T10:34:40+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

> Reply from zxhxy ↑Fri Feb 18, 2022 1:04 am at Fri Feb 18, 2022 1:04 am
>
> 
I noticed that some of Dislyte's character directories had skeleton files, while others only had Physics files

After opening the NUX model file with the tool, must load the skeleton file to play the animation correctly

So which step am I missing?

I agree with this. Some characters like Wu kong in Dislyte has no skeleton. How do we solve this?
## Post #44
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-08-20T23:24:39+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

In case if someone missed latest developments, ACL animations are now mostly supported in umodel directly with different builds, including older versions like used in Final Fantasy VII Remake, Borderlands 3, Tiny Tina’s Wonderlands, etc. For more info read [this topic](https://www.gildor.org/smf/index.php/topic,8304.0.html) and respective game topics at gildor's forum.
## Post #45
- Username: pepapoha
- Rank: n00b
- Number of posts: 16
- Joined date: Wed May 20, 2020 9:49 pm
- Post datetime: 2022-08-28T15:10:45+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

hey I how to open Mir4 .uasset fiels animation ? I import nux ACLAnimViewer but I dont have animations mir4 I need .uasset extract animations file
## Post #46
- Username: yamadinggong
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 18, 2022 2:31 pm
- Post datetime: 2022-09-18T07:04:06+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

I'm importing NUX file from Apex legends mobile, everything fine when i import the skeleton and it work properly, until the ACLViewer crashed when i import the .uasset file of the animation, am i missing something?
## Post #47
- Username: nhatvpo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jul 12, 2015 5:41 pm
- Post datetime: 2023-05-29T05:32:20+00:00
- Post Title: Re: UE4 ACL Animation Tool [Valorant, Life is Strange, Apex etc.]

Will it work with Back 4 Blood?

Could you share the source project  thanks
