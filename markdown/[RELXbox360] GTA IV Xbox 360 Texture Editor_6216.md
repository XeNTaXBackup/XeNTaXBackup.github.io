## Post #1
- Username: Frosty
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 15, 2009 5:15 am
- Post datetime: 2011-03-14T00:31:17+00:00
- Post Title: [REL|Xbox360] GTA IV Xbox 360 Texture Editor

GTA IV Xbox 360 Texture Editor



What is this? -  An injection and extraction tool for the texture format .XTD of the Xbox 360 version of GTA IV, the first ever released  :happy: .

How to use? - Just extract any .XTD file from your ISO via OpenIV, open it up in the xtd section of the program. Extract one or all of the .dds files that are in your .XTD. Open the .dds files via Photoshop or any photo editing tool. After finished inject it back, you can swap PC .dds textures for the 360 ones. In the viewer, pay attention to the DXT format and levels as you will have to save it like that in photoshop for it to work. Thanks to Pimpin Tyler and Anthony for completing and finally releasing the build and source. 


GTA IV XTD Viewer Build:

```
http://www.megaupload.com/?d=E609D7T2
```


GTA IV XTD Viewer C# Source:

```
http://www.megaupload.com/?d=BM7C7X68
```



Hope you guys do some good with this, don't forget to give credit, have fun and enjoy.
## Post #2
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-03-14T11:35:41+00:00
- Post Title: [REL|Xbox360] GTA IV Xbox 360 Texture Editor

Wow!   That's awesome!
Can you make a text file editor as well? I'm interested in translating games.
## Post #3
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-03-14T16:58:21+00:00
- Post Title: [REL|Xbox360] GTA IV Xbox 360 Texture Editor

Work PS3 files?
## Post #4
- Username: JimmyTheFox
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jan 30, 2011 10:33 pm
- Post datetime: 2011-04-24T23:30:20+00:00
- Post Title: [REL|Xbox360] GTA IV Xbox 360 Texture Editor

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-25T10:34:40+00:00
- Post Title: [REL|Xbox360] GTA IV Xbox 360 Texture Editor

use offzip for these ctd/cft files (0x05 "CSR" header)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-25T13:37:07+00:00
- Post Title: [REL|Xbox360] GTA IV Xbox 360 Texture Editor

the alternative to offzip is the following script for quickbms:

```
comtype unzip_dynamic
set OFFSET long 0xc
get SIZE asize
math SIZE -= OFFSET
get NAME basename
get EXT extension
string NAME += "_unpacked."
string NAME += EXT
clog NAME OFFSET SIZE SIZE
```
## Post #7
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-25T21:11:50+00:00
- Post Title: [REL|Xbox360] GTA IV Xbox 360 Texture Editor

Managed to get with this script, more like I use them now to extract the dds?
## Post #8
- Username: blueplanet88
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 27, 2011 2:37 am
- Post datetime: 2011-06-26T18:43:15+00:00
- Post Title: [REL|Xbox360] GTA IV Xbox 360 Texture Editor

I have extracted the CTD file, it gave me a .DAT file. I opened the DAT in notepad 
these were some of the files:

pack:/vehicle_generic_carbon_normal.dds 
pack:/vehicle_generic_carbon_spec.dds
pack:/vehicle_generic_carbon.dds

How do I extract the DDS files?
I have been trying to do this for a long time now can someone please help me

Is there any way to use the xbox texture editor for these 
thankyou
## Post #9
- Username: SILENTpavel
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-07-27T23:00:59+00:00
- Post Title: [REL|Xbox360] GTA IV Xbox 360 Texture Editor

This tool was now posted here: [blog/](http://forum.xentax.com/blog/)
