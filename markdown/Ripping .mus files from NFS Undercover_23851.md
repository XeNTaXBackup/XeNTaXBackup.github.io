## Post #1
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-05-09T12:13:20+00:00
- Post Title: Ripping .mus files from NFS Undercover

Hello!

Lately, I've been trying to convert the mus files from the /SOUND/PFDATA/ folder of Need for Speed Undercover. I have tried EAlayer3 and EAConv, none worked - both hang and do nothing. I also tried Sound Exchange, but I cannot seem to figure out how to properly use it: it keeps saying "Cannot convert nfs09cd.mus onto itself". The GUI version just hangs when I import nfs09cd.mus.

I do know NFS Multimedia Converter converts the soundtrack, but I know for a fact there are more tracks in the game than that tool extracts.

Any help?
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-09T17:38:02+00:00
- Post Title: Ripping .mus files from NFS Undercover

Have you tried Foobar with the vgmstream plugin?
## Post #3
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-05-10T05:48:50+00:00
- Post Title: Ripping .mus files from NFS Undercover

Not until now, but it doesn't seem to work either.

Not sure how this FooBar2000 plugin works, but I guess it's supposed to make game music files playable or at least convertable to some other format.
Well, it doesn't work on NFS Undercover.

Here is the error message:
1 out of 1 tracks converted with major problems.

Source: "D:\Program Files (x86)\Electronic Arts\Need For Speed Undercover\SOUND\PFDATA\nfs09cd.mus"
  Unable to open source file: Unsupported format or corrupted file
  Conversion failed: Unsupported format or corrupted file
## Post #4
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-05-10T08:52:53+00:00
- Post Title: Ripping .mus files from NFS Undercover

The .mus files sound like part of the PathMusic system (the PFDATA folder probably means Pathfind Data)
Not sure where you can find a program that can unpack those though.
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-10T11:22:07+00:00
- Post Title: Ripping .mus files from NFS Undercover

As usual, the best way is to upload the file in question for people to look at.
## Post #6
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-05-10T19:49:38+00:00
- Post Title: Ripping .mus files from NFS Undercover

> Reply from jfwfreo ↑Mon May 10, 2021 4:52 pm at Mon May 10, 2021 4:52 pm
>
> 
Not sure where you can find a program that can unpack those though.

I can very easily unpack those files found in NFS Most Wanted and Carbon. Only Undercover gives me a headache.
Also, the size of the file is fairly big, suggesting it contains some data.

> Reply from DKDave ↑Mon May 10, 2021 7:22 pm at Mon May 10, 2021 7:22 pm
>
> 
As usual, the best way is to upload the file in question for people to look at.

Sure, didn't think it was an acceptable option. Here is the file in question: [https://drive.google.com/file/d/1jJi_0g ... sp=sharing](https://drive.google.com/file/d/1jJi_0gHLXx-VpJLS9lWoj3BE_b2qO9YT/view?usp=sharing)

As an update, I finally figured Sound eXchange out, but it just hangs for a while and then says "Unable to identify format of "nfs09cd.mus", skipping ...". I also tried [Toolkit Big Import/Export](https://nfsmods.xyz/mod/2190), but this one only unpacks archives that contain asf files, which seems not to be the case here.
## Post #7
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-05-24T13:16:21+00:00
- Post Title: Ripping .mus files from NFS Undercover

Bump

The file was uploaded to Google Drive, since the forum doesn't seem to accept the "mus" file extension.
## Post #8
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2021-08-10T09:57:23+00:00
- Post Title: Ripping .mus files from NFS Undercover

Last time I checked, this game worked fine in vgmstream. You should open .mpf not .mus.
## Post #9
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-08-10T18:54:40+00:00
- Post Title: Ripping .mus files from NFS Undercover

Hm, i am surprised i never saw this topic.

Every NFS game is supported by the foobar2000/vgmstream combo, and as one of the devs of vgmstream above (Nicknine) mentioned, associating the .MPF with foobar2000, you will be able to play/convert everything.

You just have to be patient until all segments are loaded in to foobar2000 then you'll be able to do what ever you want.
Also the rest of other formats work too, not just associating .MPF only.
## Post #10
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-09-02T22:13:51+00:00
- Post Title: Ripping .mus files from NFS Undercover

> Reply from mono24 ↑Wed Aug 11, 2021 2:54 am at Wed Aug 11, 2021 2:54 am
>
> 
Hm, i am surprised i never saw this topic.

Every NFS game is supported by the foobar2000/vgmstream combo, and as one of the devs of vgmstream above (Nicknine) mentioned, associating the .MPF with foobar2000, you will be bale to play/convert everything.

You just have to be patient until all segments are loaded in to foobar2000 then you'll be bale to do what ever you want.
Also the rest of other formats work too, not just associating .MPF only.

Yes, this actually works. Thank you!
## Post #11
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-29T03:06:29+00:00
- Post Title: Ripping .mus files from NFS Undercover

sorry to bump into this topic, I found an alternative to extract MUS/MPF file using Xan's MPFmaster tool for NFS MW-World games and Red Alert 3

EDIT: an alternative way to extract those files

[https://github.com/xan1242/MPFmaster](https://github.com/xan1242/MPFmaster)
