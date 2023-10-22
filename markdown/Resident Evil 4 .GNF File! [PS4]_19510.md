## Post #1
- Username: Scofield
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jul 13, 2014 5:27 am
- Post datetime: 2019-02-17T14:35:30+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

Hi all, and @Acewell I need Noesis python script  

Actually, it supports, but the picture goes wrong.

Sample File: [https://www87.zippyshare.com/v/LxgGq3lq/file.html](https://www87.zippyshare.com/v/LxgGq3lq/file.html)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-17T23:04:37+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

Noesis has native support for PS4 gnf textures and opens that gnf file no problem.  
1280x720 BC3(dxt5)
## Post #3
- Username: Scofield
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jul 13, 2014 5:27 am
- Post datetime: 2019-02-17T23:57:22+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

> Reply from Acewell ↑Mon Feb 18, 2019 7:04 am at Mon Feb 18, 2019 7:04 am
>
> 
Noesis has native support for PS4 gnf textures and opens that gnf file no problem.  
1280x720 BC3(dxt5)

Here problem. The part I marked repeated section
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-18T01:40:04+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

yeah it could be a problem with how Noesis handles non power of 2 gnf images or something.
any script i make to open this gnf will be overridden by Noesis native plugins, so no-go there.   
you can use daemon1's RawTex tool to get the image without data repeat.   

use these settings:
Offset = 0x100
width = 1280
height = 720
BC3 (DXT5)
PS4 swizzle
## Post #5
- Username: Scofield
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jul 13, 2014 5:27 am
- Post datetime: 2019-02-18T09:10:23+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

> Reply from Acewell ↑Mon Feb 18, 2019 9:40 am at Mon Feb 18, 2019 9:40 am
>
> 
yeah it could be a problem with how Noesis handles non power of 2 gnf images or something.
any script i make to open this gnf will be overridden by Noesis native plugins, so no-go there.   
you can use daemon1's RawTex tool to get the image without data repeat.   

use these settings:
Offset = 0x100
width = 1280
height = 720
BC3 (DXT5)
PS4 swizzle

Yes I know that.But this troublesome Noesis Batch process is very useful. 

How do I extract hundreds of files
## Post #6
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2019-03-20T15:29:14+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

> Reply from Acewell ↑Mon Feb 18, 2019 9:40 am at Mon Feb 18, 2019 9:40 am
>
> 
yeah it could be a problem with how Noesis handles non power of 2 gnf images or something.
any script i make to open this gnf will be overridden by Noesis native plugins, so no-go there.   
you can use daemon1's RawTex tool to get the image without data repeat.   

use these settings:
Offset = 0x100
width = 1280
height = 720
BC3 (DXT5)
PS4 swizzle
Hi

Do you think that it will be possible to make a noesis script for GNF files not power of 2 if we change GNF header and extention to something else?

ex GNFmagicid.gnf to XYZmagicid.xyz


 001.rar
(17.09 KiB) Downloaded 27 times



It will be usefull to have such noesis script to make command line automation
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-21T05:46:25+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

okay here is 3rd and hopefully final draft of Noesis python script to open your custom gnf with changed magic and extension.   
*script updated June 6, 2019*


 tex_ResidentEvil4_PS4_xyz.zip
(2.12 KiB) Downloaded 125 times


supports PS4 swizzled rgba32, dxt1, dxt3, dxt5, BC4, BC5, BC6 and BC7.
the results are the same as what daemon1's RawTex tool spits out.
i used TheUkrainianBard's "imageFromPeanoOrder" function so i could bypass using Noesis built in PS4 unswizzle.
i also had to refer to parts of his "Phyre Engine" python script to get that working properly, so thanks to him for this.  


and this bms script will automate the change to the header magic and extension
of your non power of 2 gnf images and prepare them for the Noesis script above.  

```

get SIZE asize
math SIZE - 3
get NAME basename
string NAME + .xyz
set memory_file string "XYZ"
append 
log NAME 0x0 0x3 -1
log NAME 0x3 SIZE
append

```
## Post #8
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2019-03-21T07:57:12+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

Thankyou so much
here you go with new formats


 samples.rar
(205.06 KiB) Downloaded 27 times
## Post #9
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2019-03-21T09:18:19+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

Can you add support for GNF files with zeroes padding in header?
thankyou
here you go with samples (those are the same as the previous ones but with zeroes padding in the header)


 samplesHeaderLong.rar
(205.46 KiB) Downloaded 19 times



Offset
[https://imgur.com/a/qSEHVBk](https://imgur.com/a/qSEHVBk)
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-21T23:21:04+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

okay i updated the Noesis script here to try and open your latest samples.   
[https://forum.xentax.com/viewtopic.php? ... 20#p149820](https://forum.xentax.com/viewtopic.php?f=18&t=19510&p=149820#p149820)

there seems to be issues with BC4, BC5 and BC6 unorm and snorm types,
i will look into these more later and try to come up with a better solution.
## Post #11
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2019-03-22T17:57:23+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

Here's my take on this.
Somehow I ended up with the same behaviour for BCns as Noesis.
SNorms - seems like a (channel_value+0x80) & 0xFF fix. - UPD: turns out no.
SRGBs... I don't think Noesis has gamma correction.

UPD: deleted, see [Acewell's post](https://forum.xentax.com/viewtopic.php?p=149820#p149820)
## Post #12
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2019-03-23T08:41:55+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

Great work
Thankyou both
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-24T02:11:30+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

okay i updated my script hopefully for the final time here:   
[https://forum.xentax.com/viewtopic.php? ... 20#p149820](https://forum.xentax.com/viewtopic.php?f=18&t=19510&p=149820#p149820)
i am happy with the results, they are the same as what daemon1's RawTex tool spits out.
as usual, it is never my intention to reproduce official specs, but to get satisfatory
results from the least amount of info while utilizing existing methods.
## Post #14
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2019-03-24T10:05:16+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

Other Samples for you if you are interested into add support for them.

[http://www.mediafire.com/file/s0611p3j4 ... w02xyz.rar](http://www.mediafire.com/file/s0611p3j4txrb0r/SamplesNew02xyz.rar)
## Post #15
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-06-04T06:45:49+00:00
- Post Title: Resident Evil 4 .GNF File! [PS4]

Hello I'm having an issue related to the GNF being repeated, but with a different game GinTama Rumble.
See this GNF sample file contains multiple textures, but once converted to XYZ it would only read the first one, since the default script already has the splitting function, I would guess it is a matter of combining the 2, yeah I know it's easier said than done, I honestly would try to do more, but I don't know where the default script is located. 

Using RE4 script


Using Noesis GNF default script
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-04T08:28:47+00:00
- Post Title: Re: Resident Evil 4 .GNF File! [PS4]

only the Noesis developer has access to the native gnf code, you will
have to upload some of those multi image samples for examination
if any modification to the xyz script is to be made.
## Post #17
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-06-04T10:01:41+00:00
- Post Title: Re: Resident Evil 4 .GNF File! [PS4]

Sorry I thought attachments could be larger, my bad. Here are some samples [https://www.mediafire.com/file/kqna3e7g ... es.7z/file](https://www.mediafire.com/file/kqna3e7g54clr96/gintama_rumble_samples.7z/file)
I already sent an email to the Noesis dev, but I don't know if this would be of his interest, hopefully it will.
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-06T11:31:11+00:00
- Post Title: Re: Resident Evil 4 .GNF File! [PS4]

okay i have updated the xyz script here to open your multi image samples too.   
[https://forum.xentax.com/viewtopic.php? ... 20#p149820](https://forum.xentax.com/viewtopic.php?f=18&t=19510&p=149820#p149820)
## Post #19
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-06-10T01:41:49+00:00
- Post Title: Re: Resident Evil 4 .GNF File! [PS4]

Thanks, you're a savior, I hope I didn't bother you that much. Honestly thanks.
