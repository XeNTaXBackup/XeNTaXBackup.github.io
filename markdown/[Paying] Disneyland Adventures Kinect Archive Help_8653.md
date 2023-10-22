## Post #1
- Username: gooms9
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 27, 2012 8:30 am
- Post datetime: 2012-03-28T02:21:35+00:00
- Post Title: [Paying] Disneyland Adventures Kinect Archive Help

Willing to pay $200 via paypal to whoever is able to help me extract the models and textures from this archive

Hey, I'm trying to rip some models from disneyland adventures kinect for xbox 360. I've managed to export the ISO, and I've started attempting to reverse engineer the archive format (OVL and OSL). I'm very new at this so it's pretty slow going and I'm beginning to feel a bit stuck. I was hoping that I could get some help here. Below is a link to a few samples of the file format. I can provide more upon request, though many of them are fairly large. And this is what I've surmised so far.

[http://cl.ly/1q3l1s3f2X0G0f371Y0v](http://cl.ly/1q3l1s3f2X0G0f371Y0v)

File is big endian

FILE HEADER (FRES)
4 bytes - Filetype identifier (string)
8 bytes - Filetype version information
4 bytes - unknown
8 bytes - size of the directory list must be evenly divisible by 4
4 bytes - unknown
2 bytes - unknown
2 bytes - references the number of file type descriptors in the directory list (the ones that have colons in them)
4 bytes - unknown
4 bytes - always a repeat of the previous 4 bytes
52 bytes - unknown
52 bytes - null

DIRECTORY LISTING START - Starts at byte 144
Looks similar to this. The first two i'm assuming are file descriptors of some sort, and the second two are file references of some sort I imagine
Casino:LanguagePackMap:lang
FGDK:Text:txt
default
sku_name

This game is made by the same company that made Roller Coaster Tycoon 3. That game also used OVL files, though the similarities between the two formats seem to end there. I'm assuming the OVL file is some sort of file map, and the OVS file contains the actual file data itself though I haven't been able to confirm that. I'm having trouble making heads or tales of the OVS file, I'm assuming it may be compressed.

Here is a link to the Roller Coaster Tycoon 3 OVL format spec, [http://wiki.xentax.com/index.php/RollerCoaster_Tycoon_3](http://wiki.xentax.com/index.php/RollerCoaster_Tycoon_3)
[Screen Shot 2012-03-27 at 7.15.18 PM.png](https://xentaxbackup.github.io/file/5239_Screen Shot 2012-03-27 at 7.15.18 PM.png)
## Post #2
- Username: gooms9
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 27, 2012 8:30 am
- Post datetime: 2012-04-02T21:12:27+00:00
- Post Title: [Paying] Disneyland Adventures Kinect Archive Help

Bump.

Offering $200 to whoever is able to help extract the models and textures from this archive
## Post #3
- Username: jasonpatrick72
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 16, 2015 9:58 am
- Post datetime: 2015-03-16T22:30:39+00:00
- Post Title: [Paying] Disneyland Adventures Kinect Archive Help

Any Luck? Its been a couple of years since your last reply. Ive also been looking to extract the models and textures from the Haunted Mansion levels
## Post #4
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2015-03-17T00:55:42+00:00
- Post Title: [Paying] Disneyland Adventures Kinect Archive Help

sorry to put this here but theres a rule for paying 

1. No paying for hacking. The new stand is: do not ask to pay someone, nor ask to get paid.
