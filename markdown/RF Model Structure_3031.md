## Post #1
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-05-02T03:32:54+00:00
- Post Title: RF Model Structure

A few people have asked around for the RF Online mesh structure. To make this elegant I should probably write out the structure for each section, but I didn't prepare that offhand, so check my sourcecode.

A straight rip from a structorian file i made for the headers is here.
struct MESHFILE
{
  u16 LimbCount;
  child MESHLIMBDATA;
}

struct MESHLIMBDATA
{
  str[len=100] MeshName;
  str[len=100] LimbName;
  [hidden] u16 uk1;
  u32 ScaleX;
  skip 16;
  u32 ScaleY;
  skip 16;
  u32 ScaleZ;
  [hidden] u16 uk2;
  u32 PositionX;
  u32 PositionY;
  u32 PositionZ;
  [hidden] u16 uk3;
  u32 uk4;
  u32 uk5;
  skip 122;
  u16 PositionsCount;
  u16 FacesonLimb;
  u16 Sector3Count;
}

proceeding is a 28 byte struct which consist of the following
dword X - vector position
dword Y
dword Z
4 byte constant
dword X - normal position
dword Y
dword Z

Sadly I am to lazy to read off the rest to you, check over my source code in my msh->obj converter.

[http://honor-rf.blogspot.com/2008/04/rf ... h-obj.html](http://honor-rf.blogspot.com/2008/04/rf-model-converter-msh-obj.html)

Direct Download Links
[http://www.zshare.net/download/1134228887b5ec16/](http://www.zshare.net/download/1134228887b5ec16/)
Current Music : [http://www.youtube.com/watch?v=vYTJqGDgImU&NR=1](http://www.youtube.com/watch?v=vYTJqGDgImU&NR=1)
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2008-05-02T05:35:22+00:00
- Post Title: RF Model Structure

cool, but i can only seem to find msh files for the items and stuff. what about character models/nps? they seem to be packed in an rfs file
## Post #3
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-05-02T23:04:57+00:00
- Post Title: RF Model Structure

For character models check in [RF Folder]\Character\Player\Mesh, I can guarentee perfect unpacking for all files under DEFAULTBF.RFS, but there will be problems with msh's extracted from some acc and cora files, nothing too bad. NPC's & Monsters are there too lmao. I don;t think I mentioned anything about textures, so I will mention how to handle that. Extract the parralel textures from the tex directory, and use photoshop or something to convert the RFT->DDS->BMP. Open the MTL file with notepad and change the .dds to .BMP and you should have a perfectly skinned model.
## Post #4
- Username: OggerMC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 07, 2008 8:49 am
- Post datetime: 2008-05-07T13:30:46+00:00
- Post Title: RF Model Structure

i get severl erros when i use it :S
i tryed to convert this file
BELCOR_WEAPON_TSTAFF_196.msh
from
\RF Online\Item\Weapon\Mesh

WEM10.RFS (used RFSUnPack to unpack the .rfs)

pls, i need some help >_<
i want edit the glow of that staff
## Post #5
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-05-08T03:17:25+00:00
- Post Title: RF Model Structure

I will take a quick look for you, it may be one of the limited restrictions, but I can probably make an alternate program for you. Also, I think glow is an effect file of different format, if not then the dds texture attached, not the actual model.

Edit:

Er, that one was a working one with my XNA viewer(another program), I know because I accidently deleted it... if you can send it to me somehow I can look. As for effects, the Chef\Eff\ contains effects for various level staffs of that package, opening it with a hex editor you will see it references some .DDS files, try manipulating or rerouting those.

Edit2:
Got a copy of the file, there is a lot of extra data in the header for the weapon, so I am measuring that currently. The actually vertex data still starts at 0x2D8-5. The first count is there, the sector3 count is missing, I am going to try to patch that in.

Edit3: By assuming sector3 is always the same length as the position count I was able to load it, thank you alot that may be what I need to load any model! here are a few pics from the xna viewer, give me a few mins to update my exporter.
## Post #6
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-05-08T04:17:41+00:00
- Post Title: RF Model Structure

Program update for my little friend, thanks to you my program is now more functional.

[http://www.zshare.net/download/117026826741dd97/](http://www.zshare.net/download/117026826741dd97/)

Also check the blog. All I did was change a single line and a lot more work now. Also, remember if the texture doesn'
t load scroll up for info on how to. Enjoy, and let me know if you find more errors.
## Post #7
- Username: OggerMC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 07, 2008 8:49 am
- Post datetime: 2008-05-08T09:45:52+00:00
- Post Title: RF Model Structure

weee i gona try it, thanks alot
hehe, im glad that my erros helped ya ^_^
## Post #8
- Username: OggerMC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 07, 2008 8:49 am
- Post datetime: 2008-05-08T10:49:08+00:00
- Post Title: RF Model Structure

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-05-09T03:35:48+00:00
- Post Title: RF Model Structure

To achieve what you want, you need to go to RF\Chef\Tex folder. The eff files mention 55Shield_Pink.dds & Silver_Red.dds, but from your pictures those don't seem to be it. Try modding the colors on STAFF_135.dds, STAFF_Y.dds, STAFF_Y_01.dds, and elec_04.dds
## Post #10
- Username: OggerMC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 07, 2008 8:49 am
- Post datetime: 2008-05-09T09:03:21+00:00
- Post Title: RF Model Structure

thanks for the hints
## Post #11
- Username: OggerMC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 07, 2008 8:49 am
- Post datetime: 2008-05-09T14:03:43+00:00
- Post Title: RF Model Structure

ive checked the files u mentioned, but they are all already red/orange effects.

but i though i need to find the effect/texture what applys to the staffs current one, and change it.
so i though i have to find the blue,lightining one and change it color thema.
## Post #12
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-05-10T23:43:03+00:00
- Post Title: RF Model Structure

And for you, I present the effect ripper. No more lonely nights of manual extraction, now it will do it fast. Use in the Rf Effect folder with RPK files. There are tons of them... Goodluck. BTW, although the rip is easy, the replacement is manual, muahaha. Contact me on msn to do it. I am to lazy to make it easy for you.

[http://www.zshare.net/download/11835826bc3c3633/](http://www.zshare.net/download/11835826bc3c3633/)
## Post #13
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-05-11T01:30:54+00:00
- Post Title: RF Model Structure

Actually, I am thinking the effect may be in RF/Chef/ChefEntity1.rpk or RF/Chef/ChefEntity2.rpk ... To be honest, you got me stumped on this, but the control file is external of the mesh I am certain.
## Post #14
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2008-05-12T22:24:13+00:00
- Post Title: RF Model Structure

seems to crash alot on the player msh files, but the part that sucks is everything is in pieces. like legs arms, the torso and head are all mushed together in the center. I'm guessing the coordinate data for these objects are located in the animation files.. 

oh well from a modding perspective the OBJ to MSH function would have a greater value then just model viewing.
## Post #15
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-05-14T00:07:51+00:00
- Post Title: RF Model Structure

Actually the coordinating data is in the headers, I ignore it in my extraction. 

[hidden] u16 uk2;
u32 PositionX;
u32 PositionY;
u32 PositionZ;

That part controls location, but it basically transforms the points from an origin location.
## Post #16
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-05-18T23:13:40+00:00
- Post Title: Re: RF Model Structure

[http://honor-rf.blogspot.com/2008/05/v3-msh2obj.html](http://honor-rf.blogspot.com/2008/05/v3-msh2obj.html)

I pray this is the last correctional update I have to make. Some meshes were still giving errors, such as red maus, so I went in to check and found that the Sector3 data was missing and only a DWORD was in the place. In the header, if the sector3 daat has a 0x00 byte for it than it will more than likely not have a sector3, but rather than making it automatic I made it something you have to check just incase my assumption is incorrect. Let me know if there are still errors. Also, I think i fixed the having to close it every time you do a new model. Just a few pics... I am so lame. I can write the silly program to do the work, but I can't figure out how to assemble the mau T_T....
A final note, the final change I will make to the importer (hopefully) will be adding the positional coordinates. With that, assembling will become a painless matter.


Current Music: Hiro no Tsuki [http://www.youtube.com/watch?v=Bz1508RBx2w](http://www.youtube.com/watch?v=Bz1508RBx2w)





[http://www.zshare.net/download/12226941e9c5b118/](http://www.zshare.net/download/12226941e9c5b118/)
## Post #17
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2008-09-17T15:59:21+00:00
- Post Title: Re: RF Model Structure

Ok its a little old  old topic, but  question is, has anyone made any progress?

Or at least  in exporting to.msh without flaws.

Well also  those who have worked or has any idea, what kind of info (where, in what file) determines  what piece of model is in what location ingame . eg. hand position when holding item or weapon position (so its not  inside character etc).

Basic idea is to create custom model instead of  editing   already existing ones.
I know  rf engine supports only  3 vector faces (if im correct, might be wrong, correct me), But the problem would be  exporting from 3dsmax to .msh and getting it to work ingame.
Not sure if that tool  provided here works, anyone had any success?
## Post #18
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2008-10-06T19:06:50+00:00
- Post Title: Re: RF Model Structure

What client is this compatible with I can't extract any of the meshes.
## Post #19
- Username: Nava
- Rank: n00b
- Number of posts: 10
- Joined date: Thu May 01, 2008 12:02 pm
- Post datetime: 2008-11-02T04:09:18+00:00
- Post Title: Re: RF Model Structure

Wow, it has been so long since I abandoned the project that they might have changed things on me. I should have done this months ago, but here is the complete code work of my last version of the mesh extractor. I think ZShare deletes things after 3 months or so, so if the intact code is still useful please smear it around so everyone can use. My last version IS NOT USER FRIENDLY, so you will have to delve a bit into the code to understand what it is doing. [http://www.zshare.net/download/5077840012230b70/](http://www.zshare.net/download/5077840012230b70/)

Enjoy, hope it is still useful.
## Post #20
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2008-11-02T12:48:19+00:00
- Post Title: Re: RF Model Structure

Thanks for the source code I will use what little knowledge of programming I have to try to figure out how to get it to work with the newer model format.
## Post #21
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-16T19:43:07+00:00
- Post Title: Re: RF Model Structure

can you upload this to another host? doesnt work in zshare
## Post #22
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2009-05-10T19:22:05+00:00
- Post Title: Re: RF Model Structure

kinda old one, but i hope some still knows.

Anyone got any idea how to open  .rpk files in chef folder - as those seem to contain parts of  effect for 55 weapons.
i noticed some post here about those and a link to a file but its down.
## Post #23
- Username: renkinjutsushix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 13, 2009 10:16 pm
- Post datetime: 2009-11-15T03:35:28+00:00
- Post Title: Re: RF Model Structure

sorry im new and i dont understand how to use this~ can you help me?

the file name in RF is .RFS. . . how can i convert it so that Autodesk maya can view it?
## Post #24
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-11-16T00:37:47+00:00
- Post Title: Re: RF Model Structure

Sorry if this is thread necromancy-


Just a quick question:

Would this work on Star Wars Battlefront 1/ 2 and Titan Quest .msh files?



EDIT: Nevermind- just tried it. It does very odd things to them when it converts them...
## Post #25
- Username: dcurbow
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 18, 2010 10:57 am
- Post datetime: 2010-03-09T04:13:55+00:00
- Post Title: Re: RF Model Structure

Msh2Obj from the file share can no longer be downloaded, can it be reposted on a different site?
## Post #26
- Username: greedlt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 03, 2010 12:13 pm
- Post datetime: 2010-04-03T19:35:33+00:00
- Post Title: Re: RF Model Structure

anyone still have a working link  to the rpkextractor thingy?

or can upload it somewhere for me =/? would be greatly appreciated
## Post #27
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2010-04-09T11:30:24+00:00
- Post Title: Re: RF Model Structure

The contents of this post was deleted because of possible forum rules violation.
## Post #28
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-21T22:41:31+00:00
- Post Title: Re: RF Model Structure

The contents of this post was deleted because of possible forum rules violation.
## Post #29
- Username: jub123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 12, 2011 9:36 am
- Post datetime: 2011-03-12T18:56:30+00:00
- Post Title: Re: RF Model Structure

Someone can send me "msh viewer" for rf or post a link here, cuz I can't find it using the Google... [hino1071@hotmail.com](mailto:hino1071@hotmail.com) ... pls I need it so much
## Post #30
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-03-13T00:11:33+00:00
- Post Title: Re: RF Model Structure

I found a working link to the MshtoObj utility [HERE](http://www.rfpoa.com/forum/showpost.php?p=932066&postcount=1) and attached it to this post as a backup:


 MshtoObj.zip
(8.88 KiB) Downloaded 75 times
## Post #31
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-05-05T12:42:00+00:00
- Post Title: Re: RF Model Structure

well the program work fine sometimes, but anyway the model exported broken, you need fix UNWRAP with another program -.- anyway thanks
