## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-07T19:25:28+00:00
- Post Title: Green Lantern: Rise of the Manhunters .tfo textures

Could someone take a look at .tfo textures from Green Lantern Xbox-360, and help me convert them. I will be grateful for any help, tip or advice. Here's some sample textures [http://www.mediafire.com/?f00pjvk2qbxv6v9](http://www.mediafire.com/?f00pjvk2qbxv6v9)
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-08T15:46:29+00:00
- Post Title: Green Lantern: Rise of the Manhunters .tfo textures

Inside .lvl_760 container I found reference about textures, with proper names and texture size, for example these textures should be 2048x2048. Also I noticed letters 5TXD it's DXT5 only backwards, could it be what they are .dds textures? I've tried to add dxt headers and nothing.
## Post #3
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-05-08T17:20:57+00:00
- Post Title: Green Lantern: Rise of the Manhunters .tfo textures

They could very well be DDS. Often times compilers leave the original extension in the archive. In other words, TGA was probably what the tools used, then when compiled the textures would be changed on a per-platform basis.
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-09T11:11:09+00:00
- Post Title: Green Lantern: Rise of the Manhunters .tfo textures

Thank you for the tip   If they are .dds I have no idea why when I add .dds header, they didn't work. Maybe as letters DXT5 are like 5DXT all data flipped  too? We definitely need more tutorials about image formats   I'm always get stuck at loading/converting textures, if they aren't already supported by any other plugin or script.
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-10T10:03:39+00:00
- Post Title: Green Lantern: Rise of the Manhunters .tfo textures

Good news, problem with textures totally solved. Thanks deronar for some tips.
[Green_Lantern.jpg](https://xentaxbackup.github.io/file/6393_Green_Lantern.jpg)
## Post #6
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-05-10T21:25:46+00:00
- Post Title: Green Lantern: Rise of the Manhunters .tfo textures

Would you be so kind to share your information about the texture format with us? Maybe someone else will mess with the same image format in the future. So it would be handy to have some information about it.
## Post #7
- Username: wandererBC
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 06, 2013 8:39 am
- Post datetime: 2013-06-10T16:20:21+00:00
- Post Title: Green Lantern: Rise of the Manhunters .tfo textures

Hi there. 

 I'm a new member here (long time lurker), and was wondering about any progress you've made on the extracting of the .lv_760 container files (A QuickBMS script perhaps?) and the import script you wanted to write for this game's models (for Noesis I assume.) you mentioned in your previous thread and if you might consider posting them if they're ready, as I have been wanting to extract these models my self for a loooong, while now.

Anyways, just thought I'd ask.
