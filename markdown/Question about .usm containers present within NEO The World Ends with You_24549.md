## Post #1
- Username: L33THAK0R
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 13, 2021 2:48 pm
- Post datetime: 2021-09-30T15:42:33+00:00
- Post Title: Question about "*.usm" containers present within "NEO The World Ends with You"

Hi all,

I'm currently trying to demux the audio & video for the USMs found within the aforementioned title. My first attempt involved VGMToolbox to see if they could just be demuxed this way, however upon extraction the audio was extracted in the form of a ".bin", which seemed to be just a bunch of corrupt data when examining the hex-code. The extracted video was a blank ~7 second ".m2v" file, appearing to use the standard MPEG1/2 codec all USMs are encoded to use. Next I attempted to figure out if the USMs were encrypted (see [here for more information](https://wiki.xentax.com/index.php/USM_Video)), but I was unable to determine whether an encryption key was even present, as the data appears to be unencrypted. For anyone curious I've [uploaded a variety of samples](https://mega.nz/folder/7VdAGJKC#Dg4QF2gR8TQbB9ES6w-Rbg), ranging all the different categories of USMs that I was able to discern. If anyone has any ideas please let me know, I'm very interested in figuring this one out!
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-30T18:21:24+00:00
- Post Title: Question about "*.usm" containers present within "NEO The World Ends with You"

Yeah, those USM files seems to be encrypted as I was not able to convert them with any tools I have.

Maybe you could try to use Il2CppDumper to find the key
as it was said in this topic [viewtopic.php?p=178423#p178423](https://forum.xentax.com/viewtopic.php?p=178423#p178423)
## Post #3
- Username: L33THAK0R
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 13, 2021 2:48 pm
- Post datetime: 2021-10-03T07:55:24+00:00
- Post Title: Question about "*.usm" containers present within "NEO The World Ends with You"

> Reply from ikskoks ↑Fri Oct 01, 2021 2:21 am at Fri Oct 01, 2021 2:21 am
>
> 
Yeah, those USM files seems to be encrypted as I was not able to convert them with any tools I have.

Maybe you could try to use Il2CppDumper to find the key
as it was said in this topic viewtopic.php?p=178423#p178423

Had a decent crack at trying to figure out the key used (thankfully stored in plaintext for .USMs), however I didn't have much luck. Turns out most titles with encrypted .USMs will only read a modified USM if its encrypted with the same key. [This project](https://github.com/donmai-me/WannaCRI) is the only application I can find that may support such functionality eventually, but for now I think I'll have to sit on this one.
