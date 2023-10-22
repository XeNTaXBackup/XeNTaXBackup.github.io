## Post #1
- Username: Axem
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 04, 2012 11:32 pm
- Post datetime: 2015-10-30T23:39:33+00:00
- Post Title: Need help with a weird dds

I've got these files that claim they're DDS files, but they look like they've be run through some sort of compression. The file starts with a 0xFD and then has the the "DDS" magic word and the DXT type ("DXT3") later on, but the rest is some sort of mess. I'm hoping that some wise eyes can help point me in the right direction with these.

Link to sample files below (with a TGA that appears to have been run through the same process)
[https://drive.google.com/file/d/0B_q0tk ... sp=sharing](https://drive.google.com/file/d/0B_q0tkX7VcSaZWNBTmxhbkNRaTA/view?usp=sharing)

When I was decoding the original archive file format in a hex editor, these values came up related to something about these files.

00 15 50 80 (e_asgrimm_bump.dds)
00 15 50 80 (e_asgrimm_h.dds)
00 00 15 D0 (e_asgrimm_l.dds)
00 05 54 80 (e_asgrimm_m.dds)
00 10 00 2C (allships.tga)

But what they are exactly escapes me. No idea if that helps or not...

Thanks in advance!
## Post #2
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-11-01T13:33:00+00:00
- Post Title: Need help with a weird dds

Is it the new .dds format files, where instead of having the mip maps as part of the file they are spread out into .dds1, .dds2, etc?  Along with an index file.

Try this tool to see if it can convert them to the old .dds files:

[http://www.cryengine.com/community/down ... 528a1bf7e6](http://www.cryengine.com/community/download/file.php?id=115943&sid=abc7b44862f3b444522e75528a1bf7e6)
## Post #3
- Username: Axem
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 04, 2012 11:32 pm
- Post datetime: 2015-11-01T23:07:20+00:00
- Post Title: Need help with a weird dds

No dice on that I'm afraid.
