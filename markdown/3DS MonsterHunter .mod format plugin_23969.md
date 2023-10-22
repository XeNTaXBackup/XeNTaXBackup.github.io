## Post #1
- Username: meecube
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 04, 2020 9:04 pm
- Post datetime: 2021-05-28T15:23:40+00:00
- Post Title: 3DS MonsterHunter .mod format plugin

Hello!
I'm inquiring about a tool, or plugin for Noesis/Blender to be able to convert/import this file into Blender 2.7 or higher, 

.mod is a fileformat commonly used by Capcom and appears to have changed over time, in this instance I'm looking to open/convert an older version from the 3DS Era,

There exists a plugin to import this file into 3DS Max(someone helped by testing) located here -
[https://lukascone.wordpress.com/2017/06 ... ork-tools/](https://lukascone.wordpress.com/2017/06/18/mt-framework-tools/)
I would normally just grab the required software, however in this case- it wants to put a lot of data into my C: Drive, which is small and intended purely for booting, so that isn't possible without buying a new drive...

I have tried this Noesis plugin - however it isn't able to read this version of the .mod format, 
[https://residentevilmodding.boards.net/ ... mc5-noesis](https://residentevilmodding.boards.net/thread/13501/exporting-custom-models-dmc5-noesis)

I think this is enough information! but please do ask for more if needed, Thank you!
[fi027.7z](https://xentaxbackup.github.io/file/20222_fi027.7z)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-28T20:10:23+00:00
- Post Title: 3DS MonsterHunter .mod format plugin

I'm not sure yet of the full file layout, but this is the object from an initial test of the data.  I'll have a proper look at it if I get some time.
## Post #3
- Username: meecube
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 04, 2020 9:04 pm
- Post datetime: 2021-05-28T20:18:12+00:00
- Post Title: 3DS MonsterHunter .mod format plugin

That looks good to me! What did you do out of curiosity?
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-28T20:29:32+00:00
- Post Title: 3DS MonsterHunter .mod format plugin

I used 3D Model Researcher - vertices start at 0x2354 (padding is 24 for Model Researcher) - 6141 entries

Face indices start at 0x382e8 - 13923 entries, triangle strips

That's the whole data for the model, but it's split up into smaller sub-meshes in the file.
## Post #5
- Username: meecube
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 04, 2020 9:04 pm
- Post datetime: 2021-05-28T20:55:00+00:00
- Post Title: 3DS MonsterHunter .mod format plugin

That's awesome! 
I've never used Model Researcher before,
I'm not getting anything in the viewport, did i do something incorrectly?
[https://imgur.com/Lnuqv7p](https://imgur.com/Lnuqv7p)
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-28T21:06:55+00:00
- Post Title: 3DS MonsterHunter .mod format plugin

Yes, there's no padding on the faces, so that should be zero, and the faces type should be Short, then it'll work.
## Post #7
- Username: meecube
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 04, 2020 9:04 pm
- Post datetime: 2021-05-28T22:51:23+00:00
- Post Title: 3DS MonsterHunter .mod format plugin

You're awesome dood!
Thanks to your help I've managed to rebuild a different file! 
[https://imgur.com/J30IJT3](https://imgur.com/J30IJT3)
