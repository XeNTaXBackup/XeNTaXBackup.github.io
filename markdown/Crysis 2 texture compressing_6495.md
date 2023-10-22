## Post #1
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-25T13:12:48+00:00
- Post Title: Crysis 2 texture compressing?

Hey everyone - im trying to make some nice mods for C2 but im having big texture issues - to be precise i'm having issues with the size of my textures!
For example - if i invert colour for a texture then save it as JPEG (with LOWEST photoshop quality possible!) and then proceed to converting them into .dds again the file is then over twice the size of the original!

Programs I'm using:
Photoshop CS3
DDS Converter 2.1
QuickBMS to extract .pak's
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-04-25T14:50:20+00:00
- Post Title: Crysis 2 texture compressing?

I downloaded Crysis 2 MP Demo and don't know if retail version uses the same DDS format. Demo has uncompressed DDS.

I opened Textures\FrontEnd\cw2_cxp_background.dds and changed it like this (shrinked only for forum purpose). 



Then I save it in Photoshop with these settings and modified texture is smaller about 8 bytes then original (good for reimport   )



So try these settings. Maybe they will help you.
## Post #3
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-25T15:07:04+00:00
- Post Title: Crysis 2 texture compressing?

where would i get that Nvidia SDK thing?

I also found that if i make the image in Paint instead of Photoshop i have almost identical size!
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-04-25T16:52:44+00:00
- Post Title: Crysis 2 texture compressing?

> Reply from badMan
>
> where would i get that Nvidia SDK thing?

It's a DDS plugin for Photoshop. Find it here [http://developer.nvidia.com/nvidia-text ... -photoshop](http://developer.nvidia.com/nvidia-texture-tools-adobe-photoshop)
