## Post #1
- Username: thunderysteak
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 20, 2016 3:54 pm
- Post datetime: 2018-02-10T23:59:56+00:00
- Post Title: Wowhead's model viewer - Need help with MO3 format

I'm trying to get World of Warcraft: Battle for Azeroth models like the Sethrak creatures, but because it's currently in alpha for Blizzard employees and friends, only way how to get the hands onto said models is only with Wowhead's 3D model viewer on their own site (Not even obtaining the alpha client will work because I'd need an updated list file). Also will come pretty handy when the WoW Model Viewer breaks again with a major WoW patch

Things I know so far:
You can get the model file and the texture from a XHR node via inspect element
Textures are sent separately as PNG
File compressed by zlib due of 78 byte at the start of compressed data, viewer code contains zlib libraries was even confirmed with offzip for it reporting 0x99 hex offset in all tested files
File contains animations, skeleton, UV map and several meshes (for example, different types of ears or pieces of armor in file, also called "geosets") 
Kind of looks like to be following the M2 format spec at first with the geosets but upon further inspection it's custom


Wowhead's JS viewer code, JSON code that requests on model load and an MO3 model samples in attachment 
Data pulled from Wowhead's dressing room

If someone actually figured out how to get the models from the viewer I'd greatly appreciate it
[wowheadviewer_with_malehuman_sample.zip](https://xentaxbackup.github.io/file/13897_wowheadviewer_with_malehuman_sample.zip)
## Post #2
- Username: Sylbriana
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 08, 2018 10:49 am
- Post datetime: 2018-03-08T06:26:17+00:00
- Post Title: Wowhead's model viewer - Need help with MO3 format

I'm currently beating my head against the wall trying to figure out the same thing. If I have any success I'll let you know.
## Post #3
- Username: xayzer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 27, 2020 6:56 am
- Post datetime: 2020-11-26T23:08:16+00:00
- Post Title: Wowhead's model viewer - Need help with MO3 format

Does anyone have any new info on this?
