## Post #1
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-01T22:55:33+00:00
- Post Title: Shadow Of Mordor .arch05

I could not help my self from taking a quick look on the files after my first minutes on this MAGNIFICENT game.

I  don't know the engine that the game was built on, so i have no idea if there is a similar storage theme on the archives.

What i've found so far:

Some bundlexmls are defined at the start of any archive which contain data about the rest of the files in the archive, so i guess these have to be parsed first and i'll try to do that tomorrow. These xml files are zlib compressed.

I'm attaching 2 sample xmls i managed to decompress.

[https://www.dropbox.com/s/sygk3ov82wm1d ... xml05?dl=0](https://www.dropbox.com/s/sygk3ov82wm1dy1/troll.bndlxml05?dl=0)
[https://www.dropbox.com/s/uew0m4r8twavk ... xml05?dl=0](https://www.dropbox.com/s/uew0m4r8twavk3m/globaldatabase.bndlxml05?dl=0)

There are also some .embb files which contain some names in there, have not checked it yet how they are used.

I'm excited to be honest, because i can clearly see some .mat some .mesh some .skel files which i'll investigate tomorrow.


-----------------------------------
.arch05 Explorer v0.2




Latest Version Download Link
[https://bitbucket.org/gregkwaste/.arch0 ... r_v0.2a.7z](https://bitbucket.org/gregkwaste/.arch05_explorer/downloads/arch05Explorer_v0.2a.7z)

Repository
[https://bitbucket.org/gregkwaste/.arch05_explorer/](https://bitbucket.org/gregkwaste/.arch05_explorer/)

ChangeLog v0.2:
-64 bit application, handles tha largest archives
-Fixed Naming Issues in embb
-Added embb file export support
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-10-02T00:37:25+00:00
- Post Title: Shadow Of Mordor .arch05

those are not complete files.
use the - 1 command with offzip so it does not separate them into zlib chunks
then look for <?xml and the closing xml tags to dump the file.
then post that
## Post #3
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-02T07:54:29+00:00
- Post Title: Shadow Of Mordor .arch05

> Reply from chrrox
>
> those are not complete files.
use the - 1 command with offzip so it does not separate them into zlib chunks
then look for <?xml and the closing xml tags to dump the file.
then post that

You are right, i did not notice that yet, the files are indeed incomplete but there are no issues with the unzlibing. The output sizes are exactly as written in the file. There are probably more chunks for the file somewhere later in the archive. I'll make my search
## Post #4
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-02T08:59:50+00:00
- Post Title: Shadow Of Mordor .arch05

I think i got them 

Those are some bundle xmls from the monsters.arch05

[https://www.dropbox.com/s/bxxuux59byz5t ... xml05?dl=0](https://www.dropbox.com/s/bxxuux59byz5t9x/goblin.bndlxml05?dl=0)
[https://www.dropbox.com/s/sygk3ov82wm1d ... xml05?dl=0](https://www.dropbox.com/s/sygk3ov82wm1dy1/troll.bndlxml05?dl=0)
[https://www.dropbox.com/s/z1nych3wz759i ... xml05?dl=0](https://www.dropbox.com/s/z1nych3wz759irv/warg.bndlxml05?dl=0)
## Post #5
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-02T16:50:18+00:00
- Post Title: Shadow Of Mordor .arch05

Ok after fixing the decompression issues, i managed to get the contents of the archives.

It seems like the archives contain other typeof containers. embb files.

Maybe someone has seen them before, i haven't.

Anyway embb files contain the actual raw files of the game.
I wrote a simple embb explorer in GTK python just to get a graphical view of the structure and i was able to get some files that i was most intersted in.

I've shared some orc files here  

[https://www.dropbox.com/sh/7d9mhhbu8crq ... hWPFa?dl=0](https://www.dropbox.com/sh/7d9mhhbu8crqz7e/AACFB-Ms74hslCUvCbddhWPFa?dl=0)
[embb explorer.png](https://xentaxbackup.github.io/file/7874_embb explorer.png)
## Post #6
- Username: ChaosCom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 04, 2014 12:13 am
- Post datetime: 2014-10-03T16:23:29+00:00
- Post Title: Shadow Of Mordor .arch05

Hi,

can anyone tell something about the "MMSH" mesh format they use?
## Post #7
- Username: Mireneye
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 29, 2013 3:46 am
- Post datetime: 2014-10-03T20:25:00+00:00
- Post Title: Shadow Of Mordor .arch05

Any hope for packing and repacking textures? Would love to at least swap out some of the UI textures as I'm using a ps3 controller. 
It's really awesome you've already been able to retrieve some raw files ^-^
## Post #8
- Username: RicoKwothe
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 03, 2014 9:47 pm
- Post datetime: 2014-10-03T22:56:11+00:00
- Post Title: Shadow Of Mordor .arch05

Hy.
Please upload your embb explorer.
Sorry my bad english.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-04T05:28:05+00:00
- Post Title: Shadow Of Mordor .arch05

nice armor - point cloud ok, but some corrections required for the obj (grouping/erasing of faces):



Troll_PtCloud.jpg (183.88 KiB) Viewed 1567 times


You'll need this update 0.22c of hex2obj to enter a face indices count >65535:
[http://www.uploadmb.com/dw.php?id=1410093768](http://www.uploadmb.com/dw.php?id=1410093768) (exe only, for full 0.22 archive view link in my sig)

or simply use 65535 here.
## Post #10
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-04T09:30:14+00:00
- Post Title: Shadow Of Mordor .arch05

Excellent job shotokay  I'm planning to take a closer look to MMSH format because i am REALLY interested in the game characters (which i have not yet found xD). If anyone has played the game, you can really understand what i am talking about.

As for the embb explorer i'll definitely upload it as long as i finish it , i'll try to add the arch05 file explorer in it as well, because right now it only works from command line and an embb explorer is useless without an arch05 explorer. Unless there is another way to get the embb's which i don't know yet
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-04T11:36:49+00:00
- Post Title: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
> Excellent job shotokay  I'm planning to take a closer look to MMSH formatyes, it's me, the chocotail.  
The uvs are to be found at offset 8 of the 60 bytes vertex stride. They're using Word (uint16):



troll_uvs.jpg (96.94 KiB) Viewed 1550 times
## Post #12
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-04T16:33:18+00:00
- Post Title: Shadow Of Mordor .arch05

> Reply from shakotay2
>
> gregkwaste wrote:Excellent job shotokay  I'm planning to take a closer look to MMSH format yes, it's me, the chocotail.  
The uvs are to be found at offset 8 of the 60 bytes vertex stride. They're using Word (uint16):
troll_uvs.jpg

hahahahahh
sorry mate i always read shotokay, i don't know why xD

Anyway since you've found your way in the geometry offsets and stuff, i'll try to find and share a full character model
## Post #13
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-10-04T17:45:45+00:00
- Post Title: Shadow Of Mordor .arch05

Sorry for the intrusion, but are you guys unpacking the "bndxml05"s with offzip? 
I was trying to use aluigi's "bndl_4.bms" script with quickbms to extract those, without any success whatsoever of course.

I'm eager to find me some textures, but I can't get past the "bndxml05"s. Because I'm a n00b and such.
## Post #14
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-04T20:06:17+00:00
- Post Title: Shadow Of Mordor .arch05

> Reply from passburger
>
> Sorry for the intrusion, but are you guys unpacking the "bndxml05"s with offzip? 
I was trying to use aluigi's "bndl_4.bms" script with quickbms to extract those, without any success whatsoever of course.

I'm eager to find me some textures, but I can't get past the "bndxml05"s. Because I'm a n00b and such.

I did not use offzip, i don't even know what it is xD. I wrote my explorer in python using the zlib package available which does the trick 

I'll try to share some .tex files as well. I think these are the texture files so you can work on them
## Post #15
- Username: Isilfor
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 20, 2010 12:01 am
- Post datetime: 2014-10-05T10:02:12+00:00
- Post Title: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
> passburger wrote:Sorry for the intrusion, but are you guys unpacking the "bndxml05"s with offzip? 
I was trying to use aluigi's "bndl_4.bms" script with quickbms to extract those, without any success whatsoever of course.

I'm eager to find me some textures, but I can't get past the "bndxml05"s. Because I'm a n00b and such.

I did not use offzip, i don't even know what it is xD. I wrote my explorer in python using the zlib package available which does the trick 

I'll try to share some .tex files as well. I think these are the texture files so you can work on them
Can you upload your explorer?
Have you found the configuration or database files of the game? For example quests, parameters of characters, etc to mod the game ?
## Post #16
- Username: ChaosCom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 04, 2014 12:13 am
- Post datetime: 2014-10-05T16:20:48+00:00
- Post Title: Re: Shadow Of Mordor .arch05

On another note, did anyone take a look at the pck files for the sounds? They're even more confusing, as they don't seem to be packed (i.e. you can see the typical RIFF WAVE fmt structures) but nothing i tried plays them...
## Post #17
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-05T17:33:07+00:00
- Post Title: Re: Shadow Of Mordor .arch05

I'm working on the explorer and i will upload it here.

I took a quick look on the textures and they are very easy to get



They are located into tex files and they are in dds format. Fortunately dds headers are included so its super easy to extract them.

I've added some more .mat and .tex files in the share folder.
## Post #18
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-10-05T20:06:09+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
> I'm working on the explorer and i will upload it here.

I took a quick look on the textures and they are very easy to get

They are located into tex files and they are in dds format. Fortunately dds headers are included so its super easy to extract them.

I've added some more .mat and .tex files in the share folder.

Good stuff!

Well I'd love to unpack the stuff on my own either with your tools (if you're willing to share it), or with the help of someone who knows how to make scripts for quickBMS for extracting  bndxml files.
I tried reading chroxx quickBMS guide ([viewtopic.php?f=29&t=3525](http://forum.xentax.com/viewtopic.php?f=29&t=3525)) but I still haven't learned the ropes enough to make a script of my own.

That way I wouldn't have to come back here and bother you with textures or whatever else files I wanna get from the game.

Cheers!
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-10-05T21:42:53+00:00
- Post Title: Re: Shadow Of Mordor .arch05

The QuickBMS script already exists, it covers the compressed embb archives, the non-compressed ones, textures, LTMI and there are even a couple of separated scripts to allow reimporting:
[http://zenhax.com/viewtopic.php?f=9&t=185](http://zenhax.com/viewtopic.php?f=9&t=185)
[http://zenhax.com/viewtopic.php?f=9&t=208](http://zenhax.com/viewtopic.php?f=9&t=208)
## Post #20
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-10-05T21:47:51+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from aluigi
>
> things

Thanks a whole bunch Luigi!

I'm still gonna try to learn how to script on your program  

Awesome job nonetheless!
## Post #21
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-10-05T22:22:42+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Really nice work so far guys.
## Post #22
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-05T22:53:30+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from aluigi
>
> The QuickBMS script already exists, it covers the compressed embb archives, the non-compressed ones, textures, LTMI and there are even a couple of separated scripts to allow reimporting:
http://zenhax.com/viewtopic.php?f=9&t=185
http://zenhax.com/viewtopic.php?f=9&t=208

I wish i knew that before   


Anyway i finished coding an hour ago, and i uploaded my work on my repo.

Some notes:

The software is actually a python script using pyGTK for its interface. The way i run the script and i recommend for anyone to do so, is to get Python (2.7), install PyGTK and run the script from cmd using "python arch05explorer_gtk.py".

I've compiled the script for the nonPython users, but the results (as often happens with py2exe) are not so stable. The program is working, but there may be some gtk (minor) issues.

This is the repo: [https://bitbucket.org/gregkwaste/.arch05_explorer](https://bitbucket.org/gregkwaste/.arch05_explorer)
I'd attach the binary package here but its quite big (6mbs) for an attachment.

The binary files are available in the Downloads section.


Now some features:

1) Opens .arch05 archives
2) .embb and .bndlxml05 explorer
3) multiple .embb contents extractor (via treeview selection)

[](http://imgur.com/kj6BVwN)
[](http://imgur.com/nA4B95n)
[](http://imgur.com/ArJ5hnm)


To be honest i don't know if this app has more things to offer, but the main reason i made it (besides my Shadow Of Mordor interest) was to improve my skills on PyGtk programming  

Cheers
## Post #23
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-10-05T23:11:02+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
>  ...
Greg, great job!

How are you extracting the TEX files? 
I've found the textures I want, but I don't know how to open them in order to edit them.
Can you help me out?
Here's one of them : [http://www.4shared.com/file/diHCWJmWba/babutton.html](http://www.4shared.com/file/diHCWJmWba/babutton.html)
Thanks!
## Post #24
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-05T23:20:16+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from passburger
>
> gregkwaste wrote: ...
Greg, great job!

How are you extracting the TEX files? 
I've found the textures I want, but I don't know how to open them in order to edit them.
Can you help me out?
Here's one of them : http://www.4shared.com/file/diHCWJmWba/babutton.html
Thanks!

Open it with hex, and delete everything before the DDS header 




PS: I've just noted that i have no scroll support on the embb explorer, i'll update the files xD
## Post #25
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-10-05T23:41:31+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Can you also add a pck file extractor as well. when i select the embb file for the music, nothing extracts.
## Post #26
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-10-06T01:47:23+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Open it with hex, and delete everything before the DDS header

EDIT: Well I'll be damned, I managed to open the header-less archive with Dxtbmp(a program)
## Post #27
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-06T09:18:11+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from OrangeC
>
> Can you also add a pck file extractor as well. when i select the embb file for the music, nothing extracts.

please tell me the .arch05 archive so i can test it ^^
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-10-06T12:23:11+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Its global.arch05
## Post #29
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-06T20:54:52+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from OrangeC
>
> Its global.arch05

I've fixed the file loading, but there seems to be a wrong file name indexing in this particular .arch05 file.

What happens is that the language related sound file names are declared only once for the englishus folder.

There are 7 more language packs in the file:
French,German,Italian,Localized(???),PortugueseBrazil,SpanishMexico and SpanishSpain

For all those sound packs there are no file names, they are exactly the same with the englishus version.
I am searching where the hell is this defined but i haven't found it yet. For now i need to exceptionally handle this one but i'll search a little bit more before i do this.

The most possible case is that the default language is english, so the game already knows its names and probably gets the other language files automatically.


Edit: I just found the way the naming in the archives works  I'm updating the code right now
## Post #30
- Username: ELCID777
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 07, 2014 5:44 am
- Post datetime: 2014-10-06T21:54:21+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
> I'm working on the explorer and i will upload it here.

I took a quick look on the textures and they are very easy to get



They are located into tex files and they are in dds format. Fortunately dds headers are included so its super easy to extract them.

I've added some more .mat and .tex files in the share folder.

hi, all. i'm new here.

i'm interested in creating a quality ultra HD texture pack that replaces the default pack and uses less VRAM as well. i'm a pretty seasoned texture modder (skyrim texture packs). 

i see a lot of progress being made, but is it possible yet to extract the textures, mod them and repack them?

what tools (if any) do i need to unpack them? 

thanks in advance.
## Post #31
- Username: ELCID777
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 07, 2014 5:44 am
- Post datetime: 2014-10-06T21:55:46+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from aluigi
>
> The QuickBMS script already exists, it covers the compressed embb archives, the non-compressed ones, textures, LTMI and there are even a couple of separated scripts to allow reimporting:
http://zenhax.com/viewtopic.php?f=9&<a href="http://cityadspix.com/tsclick-BQBE4NTK- ... kw=t%3D185" target="_blank" alt="Planet T-301 185/60 R15 84H" title="Planet T-301 185/60 R15 84H" style="">t=185</a>
http://zenhax.com/viewtopic.php?f=9&t=208

oh wow, thanks for this. 

so is this all that's need to extract and repack textures?
## Post #32
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-06T22:37:38+00:00
- Post Title: Re: Shadow Of Mordor .arch05

I updated the Explorer 

[https://bitbucket.org/gregkwaste/.arch0 ... _v0.15a.7z](https://bitbucket.org/gregkwaste/.arch05_explorer/downloads/arch05Explorer_v0.15a.7z)

I am pretty sure that it can open ALL the .arch05 files and get the correct file names.
Unfortunately the only file it can't handle (past the 4gb limit) is the udun.arch05 because of 32 bit issues which i just realised. I'll try building it in 64bit mode.

I am also planning to add a texture previewer just to get a quick preview of the textures.

Repacking seems hard though because pretty much all files are compressed. Ultra HD textures maybe need a whole archive rebuild. Maybe i am missing something, but i guess i'd need help from more experienced guys, in order to find if this is possible
## Post #33
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-10-06T22:53:54+00:00
- Post Title: Re: Shadow Of Mordor .arch05

The new build is still not extracting the pck files.

Noting happens when i highlight the file inside the EMBB explorer and click export.
## Post #34
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-06T23:01:25+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from OrangeC
>
> The new build is still not extracting the pck files.

Noting happens when i highlight the file inside the EMBB explorer and click export.

I think i have never mentioned that the exported files go to C:\ and follow the struct in the embb file 

I just checked and i exported some pck and some bnk files as well 
pck files are a bit small though i am not sure if this is correct :S
## Post #35
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-10-06T23:31:56+00:00
- Post Title: Re: Shadow Of Mordor .arch05

haha oops. didn't even bother to check there. 

Thanks.!
## Post #36
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-10-07T01:13:42+00:00
- Post Title: Re: Shadow Of Mordor .arch05

As far as I know, there no way to repack just yet not even with quickBMS.
But I was thinking here, that maybe if we leave the folders unpacked int he right structure, and misplace the packed files, the game might read it from the unpacked directory?
I know that other games do.
Probably not the most viable solution (if this works), but at least it's a start.
## Post #37
- Username: Isilfor
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 20, 2010 12:01 am
- Post datetime: 2014-10-07T15:40:04+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Anyone familiar with this database format?
[https://drive.google.com/file/d/0Bz30dU ... sp=sharing](https://drive.google.com/file/d/0Bz30dUEtJzLnbGVGaFBlTTZYZTg/view?usp=sharing)
## Post #38
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-10-08T16:56:26+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hi, is there a way to extract Vo.pck? I tried with this program you made but it doesnt even open it. Regards.
## Post #39
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-09T19:07:23+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Starnova
>
> Hi, is there a way to extract Vo.pck? I tried with this program you made but it doesnt even open it. Regards.

tell me the arch05 file, i've found some erros myself and i am trying to fix them.
## Post #40
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-10-09T20:45:22+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
> Starnova wrote:Hi, is there a way to extract Vo.pck? I tried with this program you made but it doesnt even open it. Regards.

tell me the arch05 file, i've found some erros myself and i am trying to fix them.

That's the problem, is not an arch05 file. The location is "...Shadow of Mordor/Game/Sound". Aluigi said is the same header than Borderlands 2, but I want to extract the subtitles in it. The script only extracts WAV files.
[
http://aluigi.altervista.org/papers/bm ... s2_pck.bms](http://aluigi.altervista.org/papers/bms/others/borderlands2_pck.bms)

I saw that OrangeC opened it, so I though it was the same file.
## Post #41
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-09T22:21:32+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Starnova
>
> gregkwaste wrote:Starnova wrote:Hi, is there a way to extract Vo.pck? I tried with this program you made but it doesnt even open it. Regards.

tell me the arch05 file, i've found some erros myself and i am trying to fix them.

That's the problem, is not an arch05 file. The location is "...Shadow of Mordor/Game/Sound". Aluigi said is the same header than Borderlands 2, but I want to extract the subtitles in it. The script only extracts WAV files.

http://aluigi.altervista.org/papers/bm ... s2_pck.bms

I saw that OrangeC opened it, so I though it was the same file.

Ah so its not an .arch05 file. I can't do much now, i'll fix the arch05 issues for now, and if i find some time i'll look on the pck as well
## Post #42
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-10-10T11:21:00+00:00
- Post Title: Re: Shadow Of Mordor .arch05

What are the news on the repacking? Has anyone tried what I suggested?

Tudelou.
## Post #43
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-10T12:59:24+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from passburger
>
> What are the news on the repacking? Has anyone tried what I suggested?

Tudelou.

I personally haven't tried anything yet, i made some pretty serious and big fixes in the explorer.

Now it works ok with the biggest archives as well (udun.arch05). 64 Bit memory offsets 

Anyway the script requires python 64 bit for obvious reasons. Because its the same script running in 32 and 64 bit mode, it will work in any python version. You'll just get memory errors when trying to access files over the limit 


Because of this huge archive searching, i realised that previewing these TONS of files in a treeview just sucks. Thats why i converted this treeview to a simple sortable list. 
The other major issue that i solved was the naming inside the embb file as well. I was reading the names wrong and that lead most of the time to files with wrong names. Thats fixed once and for all.
I also added embb file export support, in case anyone needs to investigate something himself. The export button is the same, you just have to select (ONLY ONE) an embb file first.

I'll update the repository in a couple of minutes for the ppl who are comfortable with python, and i'll try to make a 64 build of the app with py2exe. I hope it works.

I've also include all the information in the first post
## Post #44
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-10T14:40:46+00:00
- Post Title: Re: Shadow Of Mordor .arch05

I've been experimenting with Watch Dogs, and used a batchfile there to extract the DDS files "automatically". Based on the example posted earlier, I could easily adapt this for SoM.
I assume that - for the Fullname extraction - the folder structure always starts at position 18.
Unfortunately, sofar I'm not able to extract any of the arch05 files with quickbms. I keep getting error: "Not enough storage is available to process this command.". No matter what script/EXE I am using (EXE=standard or 4GB vs)...
And I tried this on several arch05 files.
p

ps: you'll need to download Swiss File Knife yourself (which is what I use to extract)
ps2: I've 4 GB Ram memory
ps3: you can easily adapt the batchfile to analogue file types (w/ header)
[SoM_DDS+Header.rar](https://xentaxbackup.github.io/file/7914_SoM_DDS+Header.rar)
## Post #45
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-10-10T15:56:27+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Paul44
>
> I've been experimenting with...

I had the same "memory errors", that's because you're not using the right script. 
Try this one instead ==> [http://aluigi.altervista.org/papers/bms ... mordor.bms](http://aluigi.altervista.org/papers/bms/others/shadow_of_mordor.bms)
## Post #46
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-10-10T16:00:51+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hi Paul, thanks for this, works well   

I got the same error at first. You need to use quickbms_4gb_files.exe with [new_fear.bms](http://zenhax.com/viewtopic.php?f=9&t=196#p727) to extract the embb files from the .arch05, then use shadow_of_mordor.bms to extract the files from the embb archives.

I then used your batch file on the files from the HD texture pack monsters_0.arch05, and everything seems to have converted correctly.

> Reply from Paul44
>
> Unfortunately, sofar I'm not able to extract any of the arch05 files with quickbms. I keep getting error: "Not enough storage is available to process this command.". No matter what script/EXE I am using (EXE=standard or 4GB vs)...
And I tried this on several arch05 files.
p

ps: you'll need to download Swiss File Knife yourself (which is what I use to extract)
ps2: I've 4 GB Ram memory
ps3: you can easily adapt the batchfile to analogue file types (w/ header)
## Post #47
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-11T09:35:00+00:00
- Post Title: Re: Shadow Of Mordor .arch05

@zardalu
Thx, that did the trick. I've also updated the batchfile since it did not take "spaces" into account. My folders contain spaces, and I'm sure some of the 'internal' files will as well; this version should handle that...
I've also added another batchfile which will "identify" the DDS type. Important to know for conversion/saving purposes.
p

ps: you need to download [Swiss File Knife] and [Crunch] (for DDS type).
ps2: you'll need to keep the header-files if you plan to reimport a file. Use [copy /b header_file+DDS_file original_file] for this purpose.

EDIT:
Forgot to mention this: I extracted 3 arch05 files (intro.arch05, sun.arch05, udun.arch05) - only using 1st script - then renamed the corresponding arch05 files temporarily, and renamed the resp. folders accordingly. The game keeps running fine, but loading times are loooooooooong now: about 7-8 minutes to load the map...
Not tried (yet) to see if it continues to run upon extracting the emb-files?!

UPDATE: You'll find an update version in later a post (pag5)
## Post #48
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-11T12:20:26+00:00
- Post Title: Re: Shadow Of Mordor .arch05

I noticed that they use Bink 2 (.vib) files for the video scenes. Anyone happens to know where I can download the Radtools for this version. Apparently, I can't download them from the 'Bink' site (still v1.x)?!

thx in advance,
p
## Post #49
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-12T12:25:26+00:00
- Post Title: Re: Shadow Of Mordor .arch05

So do you confirm that the game reads of folders with extracted content?
I can fix my explorer to extract in the arch05 directory for this reason
## Post #50
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-12T14:09:43+00:00
- Post Title: Re: Shadow Of Mordor .arch05

@gregkwaste
Yes. Try it out with either 'sun' or 'udun' (2 major maps) extracted, and then use the "bottom" FastTravel.
As a final test, I renamed one of the extracted folders - still with the original arch05-files renamed - and when I then try to load the map (ie continue game), I get an error stating it can not find a particular file (forgot which one). Iow: it did not use the (renamed) arch05-file, but the appropriate folder.
For what it is worth: I only ran around a bit, but DID switch between maps (bottom FastTravel) without problems.
p

ps1:I've deleted the extracted folder_archives for now: too slow to load, and I needed the diskspace.
ps2: extract [son.arch05] to folder [son.arch05_EXT]; ren [son.arch05] to [son.arch05.temp] and then ren [son.arch05_EXT] to [son.arch05] (as an example)

EDIT:
You can simply extract ANY arch05-file into the \game folder, and that will work as well.
I also tried to extract the embb files, and use the same logic but that does not seem to work. The easiest way to test this, is with [monsters.arch05] and the Warg-files (= caragor). You'll see their icons on the hud-map, but you won't see them in the world (nor will they react to their environment). Location: there is always one in the cage in Udun Crossing (SE).
Maybe it could work if one could extract the .bndlxml05 file as well...
(and yes, I also tried copying them in the "main" \game folder; did not work either)
## Post #51
- Username: Sordid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 13, 2014 4:22 pm
- Post datetime: 2014-10-13T09:25:22+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Oh this is very interesting. Am I wrong in thinking this could be used to solve the "nobody likes the reforged dagger" problem? Extract the archive, replace the reforged model with the default model, and pack up the archive again? Can that be done?
## Post #52
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-13T09:46:48+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
> So do you confirm that the game reads of folders with extracted content?
I can fix my explorer to extract in the arch05 directory for this reason

I think a dedicated explorer/extractor like yours is much more user friendly than using a Quickbms script, and a dedicated tool. I would work on it more, if I were you.  

Where's the latest version of the tool?
## Post #53
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-13T21:24:18+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Sordid
>
> Oh this is very interesting. Am I wrong in thinking this could be used to solve the "nobody likes the reforged dagger" problem? Extract the archive, replace the reforged model with the default model, and pack up the archive again? Can that be done?
If you mean, can one export, then import changes into the embb-file. Yes, it can.  #aluigi already posted this in another topic (see pag2), but for completeness I'll add the scripts here as well.
Use [SoM_ImpExportEmbb-bndl.bms] (which I renamed to clarify its purpose) to export specific embb-files. If you get errors with particular embb-files, then you can use [ShadowOfMordor.bms] (which you'll find in this topic).
p

ps1: when you import, filesize of any changed file must be <= (LEQ) then the original size!
ps2: not sure about the [unpack.bms]; I had no need for it sofar.

UPDATE: You'll find an update version in later a post (pag5)
## Post #54
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-13T21:48:58+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from aluigi
>
> The QuickBMS script already exists, it covers the compressed embb archives, the non-compressed ones, textures...
http://zenhax.com/viewtopic.php?f=9&t=208
@aluigi
Is there a way to automate export (and possibly import) of the files, using [quickbms_4gb_files.exe]? Via a batchfile, one can pipe 1 inputrequest, but not 3 as in the case of the arch05 export (security message, folder creation, overwrite prompt).
A possible solution would be to give possible requests a unique number/id, which can then be used/added to the command line...
p

ps: I've used quickbms extensively on Sniper elite 3 (which in some cases expects one to run the export twice through the "re-use" of the Temporary-file)...
Another feature I missed was an overview of files effectively imported/exported; and better still which one didn't.
Pipe usage: [echo y | quickbms_4gb_files SoM_ImpExportEmbb-bndl.bms warg.embb warg.embb_EXT > BMS_Export.txt]
(but that is just 1 possible response)
## Post #55
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-13T22:47:06+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Mr.Mouse
>
> gregkwaste wrote:So do you confirm that the game reads of folders with extracted content?
I can fix my explorer to extract in the arch05 directory for this reason 

I think a dedicated explorer/extractor like yours is much more user friendly than using a Quickbms script, and a dedicated tool. I would work on it more, if I were you.  

Where's the latest version of the tool?

First post 

Its 99.9% complete, it can open and extract everything. Its only drawback is that it exports in C:\\ while i could make it extract files in the game directory.

I can also add some texture previewing but i am making my research on how to embedd opengl in gtk applications, because its always better using the gpu  for rendering that the gpu for image convertions, i'll definitely do that in the future.

Please try using it, and make your suggestions
## Post #56
- Username: Sordid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 13, 2014 4:22 pm
- Post datetime: 2014-10-14T10:45:03+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Paul44
>
> Sordid wrote:Oh this is very interesting. Am I wrong in thinking this could be used to solve the "nobody likes the reforged dagger" problem? Extract the archive, replace the reforged model with the default model, and pack up the archive again? Can that be done?
If you mean, can one export, then import changes into the embb-file. Yes, it can.  #aluigi already posted this in another topic (see pag2), but for completeness I'll add the scripts here as well.
Use [SoM_ImpExportEmbb-bndl.bms] (which I renamed to clarify its purpose) to export specific embb-files. If you get errors with particular embb-files, then you can use [ShadowOfMordor.bms] (which you'll find in this topic).
p

ps1: when you import, filesize of any changed file must be <= (LEQ) then the original size!
ps2: not sure about the [unpack.bms]; I had no need for it sofar.

Ah, thank you very much! I'm a total noob with very little idea of what I'm doing, but I'll try to fiddle around with it, see if I can make it work.

> Reply from gregkwaste
>
> 
First post 

Its 99.9% complete, it can open and extract everything. Its only drawback is that it exports in C:\\ while i could make it extract files in the game directory.

I can also add some texture previewing but i am making my research on how to embedd opengl in gtk applications, because its always better using the gpu  for rendering that the gpu for image convertions, i'll definitely do that in the future.

Please try using it, and make your suggestions

That's a very cool tool! I didn't realize it could actually extract things, I thought it was just a viewer. I do have a suggestion, though. I'm thinking it would be nice to be able to remove individual files from the archive.

I'm trying to replace the reforged weapons with their default variants and I really don't want to have to unpack and repack this giant archive file just to replace a couple of weapon models. Someone said in the thread that the game can load loose files, so I thought I could do it simply by extracting the files for the default variants (for which your tool was wonderful, thank you so much!), renaming them to the reforged variants, and dumping them into the game's folder. Sadly that doesn't work, the game seems to prioritize loading files in the archives over loose files. So now I'm thinking if the files in question aren't in the archives, it might force the game to load the loose ones.

Would that be possible, do you think?
## Post #57
- Username: ELCID777
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 07, 2014 5:44 am
- Post datetime: 2014-10-14T22:17:11+00:00
- Post Title: Re: Shadow Of Mordor .arch05

So, is it now possible to extract, edit and repack textures in this game? Someone give me a simple answer, please.
## Post #58
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-15T16:52:42+00:00
- Post Title: Re: Shadow Of Mordor .arch05

prenote: if you only want to extract a few particular files, then use #gregkwaste's tool. As he noted himself, files will be extracted in the C: root drive (which - in principal - is a no_go for me). It's a great tool though.

That said: I've created 2 batchfiles
1. SoM_Extract_Arch05.bat: extracts any Arch05 file. To my standards, it's done quick&dirty to get the job done. But you can 'change certain parameters' within the batchfile easily. It will create 2 logfiles as well: general info from Quickbms and the extracted filelist.
2. SoM_Arch05_UniqueFilelist.bat: this one uses the [SoM_Arch05_LogFiles.txt] (created by the 1st batchfile) to generate a unique filelist. It is also delimited  (+~+) so that it can easily be used for other stuff.
While I can generate the filesize per file, I'm unfortunately not able to create the offset size per file (ie: what is it uncomrpressed size within the Arch05 file).
However: this is - to my opinion - do-able. Luckily, somebody mentioned earlier that [offzip] can be used to decompress the files. So I did some experimenting to find the actual location of a few files with it Arch05 file.

I did my test with [corecharacter.arch05] and the 1st 2 files that will be extracted (see attached: [SoM_ExtractImport.txt])

I take [charactercommon.bndlxml05] as example. quickbms gives you following list:
  0000000000000000 0          bundles/charactercommon.bndlxml05
  000000000000026c 65536      bundles\charactercommon.bndlxml05
  00000000000014dc 1516       bundles\charactercommon.bndlxml05
  0000000000000000 0          bundles/charactercommon.embb
  00000000000015f8 65536      bundles\charactercommon.embb

One would assume that it resides between  0x26c and 0x15f8 (or even 0x14dc). Unfortunately, that is not the case. The start offset is correct, the end_offset not.
So, using SFK (swiss file knife), I extracted this chunk and quickly noticed I had more then I bargained for. Next step: use [offzip) on this 'chunk' file and see what happens:
+------------+-------------+-------------------------+
| hex_offset | blocks_dots | zip_size --> unzip_size |
+------------+-------------+-------------------------+
  0x00000000 ... 4710 --> 65536
  0x00001270 . 276 --> 1516
  0x0000138c . 336 --> 400

Notice the "1516"... So Offzip found that this file ended at offset 0x138c. I now use SFK again to extract this part of the file; ét voilà...
Why is this important: well, if you want to re-import (inject) an 'updated' embb-file again into the Arch05-file, then you'll need its exact location within that file (can't overwrite anything else). And btw: this should be possible with packzip (and also with SFK) as long as you know the correct compression parameters.

Request: I do not know if Quickbms delivers the filelist, or if it can be controlled via the BMS-script. But I'd rather like to see its end_offset for each file on its "last" series-line.
So, instead of '14dc' I would like to get the '138c' ?!
p

ps1: if anyone knows how to forward this to #aluigi, let me know.
ps2: I did some experimenting with packzip, in that I can get a value below its actual compressed size, but not exactly the same. Will it work after injection, I can't tell at the moment?
ps3: offzip and packzip can be found on #aluigi's website
ps4: all input_requests from quickbms can be automated through its options. If such an option is not available, you can 'force' this through piping "type Response.txt | quickbms ..." (each line in [Response.txt] contains a specific input_response)
ps5: I will be writing another batch that will extract the embb-files

ps6: oh yeah, before I forget, I've extracted all files and copy/pasted them in the [game] folder. Seems to work fine, but loading of a region is a 'pain'. Within a region and once loaded, response is quick(er)...

EDIT: I have "cleaned up' the batchfile w/ all "features" enabled.

UPDATE: You'll find an update version in later a post (pag5)
## Post #59
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-15T17:08:24+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from ELCID777
>
> So, is it now possible to extract, edit and repack textures in this game? Someone give me a simple answer, please.
see top of this page, and ask #zardalu how he is doing.
Simple answer: yes, if 
a) you use the extracted/updated embb-file instead of the Arch05 file (which just gives me another idea 
b) the updated texture file can not be greater in size then its original
c) extract/recreate TEX-file can be done through a batchfile I've posted earlier. Once you've updated the DDS-file, use [copy /b Header_file+DDS-file TEX-file]. Its new size must me <= original size

You can use Quickbms for this purpose (use the Bndl.bms script). as an example:
extract: quickbms_4gb_files SoM_ImpExportEmbb-bndl.bms charactercommon.embb charactercommon.embb_EXT
import: quickbms_4gb_files -r -w SoM_ImpExportEmbb-bndl.bms charactercommon.embb charactercommon.embb_EXT

Did not do any testing though, except a quick extract/import...
p

ps: there is a [hotchunk_Patch.arch05] residing in the root. Could probably used for modders?!
## Post #60
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-10-15T22:45:37+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Paul44
>
> 
ps1: if anyone knows how to forward this to #aluigi, let me know.
Try him at his own e-mail: "[me@aluigi.org](mailto:me@aluigi.org)" (taken form his hompage: [http://aluigi.altervista.org/](http://aluigi.altervista.org/))
Or just PM him here I guess.
## Post #61
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-16T19:28:50+00:00
- Post Title: Managing EMBB files

Performs following on EMBB files:
- Extract [EMBB files]: enter {1}
- Create [DDS files]  : enter {3}
 - Identify [DDS files]: enter {4}
- Create [TEX files]  : enter {5}
- Import [EMBB files] : enter {7}
Tested this batchfile extensively, but if something goes wrong - or you have particular questions - then let me know.
p

UPDATE: 
the identify DDS routine no longer deletes the DDS file if Crunch can't load it, but gets renamed (more elegant solution; avoids confusion)
[SoM_Export_Embb.rar](https://xentaxbackup.github.io/file/7963_SoM_Export_Embb.rar)
## Post #62
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-10-16T19:33:39+00:00
- Post Title: Managing EMBB files

Just a quick question: is translating the texts possible at the moment?
## Post #63
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-17T07:22:52+00:00
- Post Title: Managing EMBB files

> Reply from lostprophet
>
> Just a quick question: is translating the texts possible at the moment?
I noticed that [global.arch05] and [hotchunk_Patch.arch05] contain 'language' files (ending with a ISO language code). When you extract those, you'll find [string.strdb] files per language.
How to edit/update: no idea; nor do I know if these files contain all the subtitle strings. But if you can edit/update those, then let us know.
p

ps: the header shows it is a "SKDB" file?!
## Post #64
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-17T13:57:13+00:00
- Post Title: Managing EMBB files

I've tried the BL2 script as suggest by #aluigi to extract the pck-files. One gets the "wav"-files, but they did not play, nor could I identify them with MedioInfo (Codex=FFFF) or Sox.
After some digging, I came across Ravioli Game Tools (yep ), downloaded its latest v2.8 (incl patch); and run [RExplorer.exe] on [Streaming.pck]. It showed me a list of '.wwise'-files, some of which played fine while others did not?!
This tool allows you to extract and even convert them on the fly.
When I access [vo.pck], none (?) of them are recognized. Which makes me conclude that: a) a recent Audiokinetic format has been used or b) the 'PCK' format is (slightly) different?!
p

ps: anyone knows of a (recent) wwise-player?
## Post #65
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-17T17:35:15+00:00
- Post Title: Managing EMBB files

Based on my experience with the latest Update 2, I had to change a few minor things in the batchfile.
p

ps: I 've have removed the 'older' versions from previous posts.
[SoM_Extract Arch05.rar](https://xentaxbackup.github.io/file/7964_SoM_Extract Arch05.rar)
## Post #66
- Username: chasemm18
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 19, 2014 3:51 pm
- Post datetime: 2014-10-19T07:53:57+00:00
- Post Title: Managing EMBB files

this might be off topic, but by locating all of the files and extracting them, does this mean we are getting closer to being able to mod this game? I would love to find a way to replace the talion skin with say celebrimbor ( not as the wraith) using texmod or something
## Post #67
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-10-22T16:25:30+00:00
- Post Title: Managing EMBB files

Hi guys! Does anyone working on Shadow Of Mordor model format? Any plans for importing models?

P.S. Does someone could tell me, is there Sauron model somewhere inside files? Or Celebrimbor clean, not ghost model? Thank in advance
## Post #68
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-24T12:00:30+00:00
- Post Title: Managing EMBB files

> Reply from zaramot
>
> Hi guys! Does anyone working on Shadow Of Mordor model format? Any plans for importing models?

P.S. Does someone could tell me, is there Sauron model somewhere inside files? Or Celebrimbor clean, not ghost model? Thank in advance

Shakotay ( i hope i got it this t ime xD) managed to exctract some geometry as you may have seen, on the first pages of the topic, but i guess he has not fully parsed the model.

I was also interested in the sauron model, while coding the extractor, but i don't remember finding something. To be honest if you have played the game, there is no sauron character appearing in the game as a model. (At least as far as i witnessed). There is surely the human form of sauron, but not the armored one. All those should be in the arch05 files. I'll search a bit for you and share the character models if i find any 


Update:
Some models i managed to find:

[https://www.dropbox.com/s/e1wsiedeww48y ... on.7z?dl=0](https://www.dropbox.com/s/e1wsiedeww48y58/sauron.7z?dl=0)
[https://www.dropbox.com/s/m7ogo7lwskym0 ... or.7z?dl=0](https://www.dropbox.com/s/m7ogo7lwskym0o2/celebrimbor.7z?dl=0)
[https://www.dropbox.com/s/zw060yudx2y20 ... on.7z?dl=0](https://www.dropbox.com/s/zw060yudx2y20ev/player_talion.7z?dl=0)
## Post #69
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-10-24T13:32:56+00:00
- Post Title: Managing EMBB files

Ah, thank you so much Gregkwaste!   So it's a human form of Sauron, right (could you please send me textures or at least tell me where you found him  )?  If no one is working on the model format I'll gladly do it by myself. I'm a fan of LOTR, also format is pretty understandable

EDIT: Just checked your Sauron model, it's armored version  I hope there's his human form somewhere too
[Sauron.jpg](https://xentaxbackup.github.io/file/7981_Sauron.jpg)
## Post #70
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-24T20:38:20+00:00
- Post Title: Managing EMBB files

> Reply from zaramot
>
> Ah, thank you so much Gregkwaste!   So it's a human form of Sauron, right (could you please send me textures or at least tell me where you found him  )?  If no one is working on the model format I'll gladly do it by myself. I'm a fan of LOTR, also format is pretty understandable

EDIT: Just checked your Sauron model, it's armored version  I hope there's his human form somewhere too

Holy shit, thats so fucking cool :D

Well i used my tool for that first of all xD

Now where i found those with other tons of mat,fxo,tex and anix files:

Celembrimbor and Talion in corecharacter.arch05/player_talion.embb

Sauron (and i think i just found the human form as well) in outro.arch05/zainzadan.embb and outro.embb

Also the most important one, the main reason why i worked on this tool was when i saw the gollum in game which looked AMAZING and it is located in udun.arch05/gollum.embb


I'm sharing them as well via dropbox in case you are lazy to search yourself 

[https://www.dropbox.com/s/8sqlbhort5wf9 ... an.7z?dl=0](https://www.dropbox.com/s/8sqlbhort5wf98w/zainzadan.7z?dl=0)
[https://www.dropbox.com/s/m6xd916t08tl7 ... um.7z?dl=0](https://www.dropbox.com/s/m6xd916t08tl715/gollum.7z?dl=0)


Update: I've also uploaded talion's family members
[https://www.dropbox.com/s/p8lgwjiy185c7 ... rs.7z?dl=0](https://www.dropbox.com/s/p8lgwjiy185c7ev/rangers.7z?dl=0)
## Post #71
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-10-25T08:11:20+00:00
- Post Title: Managing EMBB files

Yeah, Gollum looks pretty cool! This Zain Zadan too, pitty there's no Sauron as he appears in visions - as an elf
[zainzadan.jpg](https://xentaxbackup.github.io/file/7986_zainzadan.jpg)
## Post #72
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-25T11:11:38+00:00
- Post Title: Managing EMBB files

Zain Zadan is how they named the human sauron and he does appear in this form in the game . He did not appear in the game as an elf, only in cutscenes, so there should be no model of him in that form. I hope i am wrong (as i was with sauron) and locate the model file somewhere 

Btw if i remember correctly you are working on max don't you? I would be very interested in porting our script into a blender one
## Post #73
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-25T12:17:10+00:00
- Post Title: Managing EMBB files

> Reply from gregkwaste
>
> Shakotay ( i hope i got it this t ime xD) managed to exctract some geometry as you may have seen, on the first pages of the topic, but i guess he has not fully parsed the model.yep, this time you got it, thx.  

I never parse the models fully.  
But I got the submeshes which seem to overlap partially (means left leg for ex. is in two different SMs):



troll_body_submeshes.jpg (124.98 KiB) Viewed 417 times



> I would be very interested in porting our script into a blender one
should not be too hard.
There's a data table after the face index list containing vertexcounts and faces counts of 13 submeshes:
For the first 4 submeshes I calculated the params required for hex2obj,
so 1st submesh starts at 0x3FE, vertex count is 3789,
face indices to be found at 0xEA09E, count is 3x 6287 = 18861

```
0D 00 00 00   0 0 3789 0 0 0 0 0          6287 0 0 0 32 0 0 0 0 0   ea09e 18861   3FE   3789
0C 78 03 00   0 0 2586 0 18861 0 3789 0   4166 0 0 0 32 0 32 0 0 0  F33F8 12498 37C0A   2586
24 D6 05 00   0 0 845 0 31359 0 6375 0    1337 0 0 0 11 0 64 0 0 0  F959C  4011 5DA22    845
30 9C 06 00   0 0 2780 0 35370 0 7220 0   4087 0 1 0 32 0 76 0 0 0  FB4F2 12261 6A02E   2780
C0 27 09 00   0 0 1649 0 47631 0 10000 0  2564 0 1 0 32 0 108 0 0 0 
3C AA 0A 00   0 0 196 0 55323 0 11649 0    278 0 1 0 6 0 140 0 0 0 
2C D8 0A 00   0 0 1612 0 56157 0 11845 0  2212 0 1 0 32 0 148 0 0 0 
FC 51 0C 00   0 0 683 0 62793 0 13457 0    865 0 1 0 32 0 180 0 0 0 
10 F2 0C 00   0 0 300 0 65388 0 14140 0    347 0 1 0 32 0 212 0 0 0 
60 38 0D 00   0 0 30 0 893 1 14440 0        20 0 1 0 13 0 244 0 0 0 
68 3F 0D 00   0 0 868 0 953 1 14470 0     1166 0 2 0 32 0 260 0 0 0 
D8 0A 0E 00   0 0 386 0 4451 1 15338 0     444 0 2 0 32 0 292 0 0 0 
50 65 0E 00   0 0 236 0 5783 1 15724 0     249 0 2 0 30 0 324 0 0 0 
                15960 verts              24022 faces
```


(As can be seen there's an offset of 0x3FE between the table entries first DWORD (0x3780C for ex.) and the vertex start address.
So the first entries first DWORD should be zero?. Seems they used it as submesh count: 0x0D.)
## Post #74
- Username: Tpiom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 08, 2011 7:37 pm
- Post datetime: 2014-10-25T23:24:44+00:00
- Post Title: Managing EMBB files

> Reply from Paul44
>
> I've tried the BL2 script as suggest by #aluigi to extract the pck-files. One gets the "wav"-files, but they did not play, nor could I identify them with MedioInfo (Codex=FFFF) or Sox.
After some digging, I came across Ravioli Game Tools (yep ), downloaded its latest v2.8 (incl patch); and run [RExplorer.exe] on [Streaming.pck]. It showed me a list of '.wwise'-files, some of which played fine while others did not?!
This tool allows you to extract and even convert them on the fly.
When I access [vo.pck], none (?) of them are recognized. Which makes me conclude that: a) a recent Audiokinetic format has been used or b) the 'PCK' format is (slightly) different?!
p

ps: anyone knows of a (recent) wwise-player?

I downloaded an updated version of ww2ogg ([http://www.hcs64.com/vgm_ripping.html](http://www.hcs64.com/vgm_ripping.html)) and added those files in Ravioli's plugin folder (...\RavioliGameTools_v2.8\Plugins\ww2ogg)
Everything worked out just fine from there.
## Post #75
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-26T13:34:21+00:00
- Post Title: Managing EMBB files

> Reply from Tpiom
>
> Paul44 wrote:...When I access [vo.pck], none (?) of them are recognized...
I downloaded an updated version of ww2ogg (http://www.hcs64.com/vgm_ripping.html) and added those files in Ravioli's plugin folder (...\RavioliGameTools_v2.8\Plugins\ww2ogg)
Everything worked out just fine from there.
Thx, it got me in the right direction. As a matter of fact, I did try the latest ww2ogg, but it still did not work. Upon your suggestion, I checked the plugin-folder, and also noticed the Revorb.exe. Treating ogg-files with this tool make them work.
If anyone wants to process this through a batchfile:
1. extract .bnk files
2. remove header (all bytes from start till 'RIFF') and footer (from 'HIRC' till end) (you can use Swiss File Knife for that)
   (this actually gives you the ".wwise" file)
3. run [ww2ogg]
4. run [revorb]
p

ps: anyone knows if these processes can be reversed: i.e. go from ogg => wwise => bnk
(if those header/footers remain the same, then one can simply keep them for this 'reverse' process)
(they do differ per file though...)

ps2: in the meantime, I found out that all spoken language files seem to be in [presentations.arch05]; containing following languages:
englishus
frenchfrance
german
italian
portuguesebrazil
spanishmexico
spanishspain
## Post #76
- Username: chasemm18
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 19, 2014 3:51 pm
- Post datetime: 2014-10-26T16:24:18+00:00
- Post Title: Re: Shadow Of Mordor .arch05

you guys are my heroes !!!! please keep this up, I would love to have the ability to play the game as Celebrimbor before he became a wraith!

 thank you!
## Post #77
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-26T17:35:07+00:00
- Post Title: Re: Shadow Of Mordor .arch05

anyone knows of a tool that can compress/restore these type of files?
(similar to e.g. Crunch for DDS)
p
## Post #78
- Username: WorldSoup
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 29, 2014 2:28 am
- Post datetime: 2014-10-28T18:31:02+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hi guys. has or can anyone found/find the models and textures for Lithariel yet. If you have can i get a link ? Thanks
## Post #79
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-10-31T04:58:10+00:00
- Post Title: Re: Shadow Of Mordor .arch05

amazing works
Thanks all of guys!
## Post #80
- Username: Marsbar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 01, 2014 7:04 am
- Post datetime: 2014-10-31T23:24:04+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Anyone found files for the minimap? The minimap is permanent during gameplay except when the new screenshot mode is selected, called Photo Mode. So in Photo Mode you can take screenshots without the minimap in the lower left and it also gets rid of any text in the upper right and anything else in the hud. But back to the gameplay, it would be more immersive to have an option to play without the minimap or the text messages. The game doesn't have a hud fade to 0 like Skyrim and some other games and no toggle for it either.
## Post #81
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-03T09:39:01+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from zaramot
>
> Ah, thank you so much Gregkwaste!   So it's a human form of Sauron, right (could you please send me textures or at least tell me where you found him  )?  If no one is working on the model format I'll gladly do it by myself. I'm a fan of LOTR, also format is pretty understandable

EDIT: Just checked your Sauron model, it's armored version  I hope there's his human form somewhere too
Hello, my friend, may I ask what tool is used to import a model file, can you teach us
## Post #82
- Username: Blinkstar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 11, 2014 6:37 am
- Post datetime: 2014-11-10T22:45:00+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Marsbar
>
> But back to the gameplay, it would be more immersive to have an option to play without the minimap or the text messages. The game doesn't have a hud fade to 0 like Skyrim and some other games and no toggle for it either.

It would be awesome if we could make some of the HUD items transparent and thus invisible. I particularly hate the giant red bars that float above some of the monsters ... just really takes me out of the world the game is trying to create. (Why does there have to be so much hand holding in games these days? Are people more stupid now than they used to be?)

Anyway ... if someone could upload some of the HUD elements in transparent form, or give me some idea of how to do it myself, I'd be eternally grateful.
## Post #83
- Username: boumkwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 28, 2014 10:09 am
- Post datetime: 2014-12-06T14:47:45+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hi, I was wondering if anyone knew where the cut-scenes dialogues are located. They're not located in the Vo.pck like i thought they would be. I even used gregkwaste's .arch05 explorer to look for them in every archive but with not success.  
Any help would be appreciated.
## Post #84
- Username: vpzneox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 09, 2014 12:48 pm
- Post datetime: 2014-12-09T07:11:57+00:00
- Post Title: Re: Shadow Of Mordor .arch05

so....  how Exactly  do u make texture mods with this?
## Post #85
- Username: chasemm18
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 19, 2014 3:51 pm
- Post datetime: 2014-12-18T17:08:46+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hey everyone,

sorry to keep lurking on this thread to keep asking the same thing, but is progress being made towards being able to use custom skins/models for the game?? I would LOVE to be able to replace talion with Another elf, I know eventually they are releasing a Celebrimbor skin but I think it would be awesome to play as legolas or elrond or something. 

Thank you to those who are working towards making this game moddable!
## Post #86
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2014-12-21T15:09:47+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from zaramot
>
> Ah, thank you so much Gregkwaste!   So it's a human form of Sauron, right (could you please send me textures or at least tell me where you found him  )?  If no one is working on the model format I'll gladly do it by myself. I'm a fan of LOTR, also format is pretty understandable

EDIT: Just checked your Sauron model, it's armored version  I hope there's his human form somewhere too

Wich program did you use to open the .mesh file? Can you save it to .OBJ format?
## Post #87
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-12-21T15:28:08+00:00
- Post Title: Re: Shadow Of Mordor .arch05

[viewtopic.php?f=16&t=12317](http://forum.xentax.com/viewtopic.php?f=16&t=12317)
## Post #88
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-01-20T23:31:34+00:00
- Post Title: Re: Shadow Of Mordor .arch05

I managed to get the models, but how do I convert the textures? are in a unreadable format! I would like in version dds. What do I do?
## Post #89
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-21T16:27:30+00:00
- Post Title: Re: Shadow Of Mordor .arch05

I uploading converter on weekend
## Post #90
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-24T19:59:30+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Release of texture converter.
Start this script.
Enter path to the directory with textures. Script recursive find *.tex or *.tex0 (hd addon) files and rewrite correct DDS header.
P.S. Very simple format  

UPD fixed small bug with "unASCII" symbols
[ShadowOfMordor_tex_converter_v1.1.py.7z](https://xentaxbackup.github.io/file/8556_ShadowOfMordor_tex_converter_v1.1.py.7z)
## Post #91
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-01-25T08:15:33+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from erik945
>
> Release of texture converter.
Start this script.
Enter path to the directory with textures. Script recursive find *.tex or *.tex0 (hd addon) files and rewrite correct DDS header.
P.S. Very simple format  

UPD fixed small bug with "unASCII" symbols

yeah, ok, but for which program? I used quickbms to export everything!
## Post #92
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-25T09:02:10+00:00
- Post Title: Re: Shadow Of Mordor .arch05

This is a script.
Install python interpreter (I use version 2.7) [https://www.python.org/downloads/](https://www.python.org/downloads/).
Then start command line and write (as example).
[py.jpg](https://xentaxbackup.github.io/file/8560_py.jpg)
## Post #93
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-01-25T09:50:44+00:00
- Post Title: Re: Shadow Of Mordor .arch05

I followed the instructions but nothing shows! there is only written on the cmd "end of dds creating", but there are only the old texture!
## Post #94
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-25T10:17:05+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Input the path to the directory with tex files. All subdirectories will be checked too.
As example:
D:\Program Files\Middle-earth. Shadow of Mordor\Arch05\!!Unpack\models\player\
## Post #95
- Username: Ditta
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 13, 2015 11:07 pm
- Post datetime: 2015-06-21T20:52:42+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hello! I have a couple of silly questions about extracting models too. At first, which tools namely I must use to extract game archives step by step to get to the mesh files? That discussion is long enough and I cannot figure out which tools I need. If they are really working, couldn't you post straight links to them here and how to use them exactly? I need to extract just meshes and dds files (textures), not music or videos.
At second, is it possible to get to architectural models of Mordor etc so easily as with characters? Where are they located in game folders and can I use the Max script for mesh files to import them in 3D Max?
## Post #96
- Username: osman66
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 17, 2015 5:57 am
- Post datetime: 2015-08-07T13:49:10+00:00
- Post Title: Re: Shadow Of Mordor .arch05

How open string.strdb, can you help me ?
## Post #97
- Username: Zefron
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 15, 2015 9:33 am
- Post datetime: 2015-08-17T12:31:30+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Has anyone had any luck with the .anix file type or converting it to a more usable file type?
## Post #98
- Username: Pavikjan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 11, 2015 2:45 am
- Post datetime: 2015-10-10T18:48:47+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hi guys!
I am new here,so please don't be harsh on me.
I wanted to knew if anyone has Celebrimbor model.I need The Bright Lord Celebrimbor.Please if you have them upload them somewhere or send me a message with the link.

NOTE:(I have Wraith Model of Celebrimbor,but i need textures for it and a 3d model OF The Bright Lord and textures)
Regards!
## Post #99
- Username: SonofKalas
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Aug 27, 2015 5:42 am
- Post datetime: 2015-12-09T04:12:37+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Can anyone tell me which files contain music?
## Post #100
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2016-01-18T02:49:20+00:00
- Post Title: Re: Shadow Of Mordor .arch05

would anyone happen to have the textures for Sauron?
I have the model but can't seem to get the textures :/
## Post #101
- Username: lordnihrain
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 10, 2016 12:34 pm
- Post datetime: 2016-04-10T04:37:33+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Anyone here know how to combine the various files from a character embb?
## Post #102
- Username: Inviktys
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 11, 2016 8:28 am
- Post datetime: 2016-04-11T02:45:40+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hi!

I'm trying to mod the armor worn by the Uruk's in the Bright Lord dlc into the main game, I like Talion's skills much better than just Celebrimbor's crap. I was able to use the quickbms to extract the stuff however the reimporter will not reimport the updated embb's back into the arch05. Does anyone know a way around this or how to repackage it as a arch05?
## Post #103
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2016-05-24T00:14:40+00:00
- Post Title: Re: Shadow Of Mordor .arch05

hello, and I would like to ask how one exports an .embb file and it's contents in the arch05 Explorer, because I want to be able to get my hands on the Sauron model somehow, if anyone can explain the process I would be most greatful for the help (BTW I'm trying to get Sauron in SFM as well)
## Post #104
- Username: Morell
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 30, 2016 6:22 pm
- Post datetime: 2016-06-02T18:03:18+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Anyone able to find elf form of Sauron in those arch05 files? I found Morwen so I believe that he can be found as well.
## Post #105
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2016-06-09T16:00:03+00:00
- Post Title: Re: Shadow Of Mordor .arch05

guys it is happening after finalizing his rig off to SFM the Dark Lord goes
## Post #106
- Username: Ditta
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 13, 2015 11:07 pm
- Post datetime: 2016-07-29T01:01:22+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Morell
>
> Anyone able to find elf form of Sauron in those arch05 files? I found Morwen so I believe that he can be found as well.

I dare to join to the question - did anyone here find Lithariel, Black Hand, and caragors (the beasts)? When I played this game, I tried to find them, but with no luck. Such a lamer I am. Please upload them if you have, even raw OBJ without rigging will go, especially caragors.
## Post #107
- Username: Ditta
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 13, 2015 11:07 pm
- Post datetime: 2016-07-31T02:15:01+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
> I'm working on the explorer and i will upload it here.

I took a quick look on the textures and they are very easy to get



They are located into tex files and they are in dds format. Fortunately dds headers are included so its super easy to extract them.

I've added some more .mat and .tex files in the share folder.

Please, couldn't you share character textures for your extracted characters which you posted at xentax shares (Sauron, Talion, Celebrimbor, Zainzadan and Gollum), in tex format. I want to test the texture extractor tool on them and retexture meshes for 3ds Max. When I played this game, I couldn't find these tex files for their body and armor textures. Then I deleted the game and don't want to reinstall all these gigs of content just to find several missing files. I hope other more successful players have found the most valuable pieces of that content and would be very grateful for sharing.
## Post #108
- Username: vpzneox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 09, 2014 12:48 pm
- Post datetime: 2016-09-20T20:05:05+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Okay,  is there by any  chance some way to convert DDS  Into  the  tex0? 
Btw,  Huge thanks  to Everyone who's done research on this subject, Including erik945,  who made   the texture  converter-  now,  just  looking if there is a way  to  make Headers  converted back?
## Post #109
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-09-22T11:20:53+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Well, if you need just to conver .dds into .tex (without packing them back into .arch05) I'm sure you can do this super easy xD  Open .tex file in hexeditor and just copy first bytes of original .tex (before laters DDS) into your edited .dds file and change extention of your edited .dds to .tex and done lol Though, it will work if Shadow of Mordor works with extracted files, like Skyrim, Fallout does - if nope, then just converting .dds to .tex will not help you much
## Post #110
- Username: vpzneox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 09, 2014 12:48 pm
- Post datetime: 2016-09-27T01:44:49+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from zaramot
>
> Well, if you need just to conver .dds into .tex (without packing them back into .arch05) I'm sure you can do this super easy xD  Open .tex file in hexeditor and just copy first bytes of original .tex (before laters DDS) into your edited .dds file and change extention of your edited .dds to .tex and done lol Though, it will work if Shadow of Mordor works with extracted files, like Skyrim, Fallout does - if nope, then just converting .dds to .tex will not help you much
Hi,  thank  you for reply.   
Any chance  of a tutorial?   Just  in case      it's possible -  I am  not good at understanding which parts  to replace/ insert  ( I got HexEd though)
## Post #111
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-09-29T08:39:43+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Well, I can try to make some screenshots in a sort of tutorial, though it's quite easy. Now I'm installing Shadow of Mordor to check if it will work xD But, from what I see for now it should work and texture editing is possible
## Post #112
- Username: vpzneox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 09, 2014 12:48 pm
- Post datetime: 2016-10-01T02:13:31+00:00
- Post Title: Re: Shadow Of Mordor .arch05

That will be Greatly appreciated. Thank You =) 
Not as Much interested  in   making   folder    readable by Game- just converting the texture.
## Post #113
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-10-01T15:23:03+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hmm, why you want to convert textures then? I mean, convert them back into in-game "format"
## Post #114
- Username: vpzneox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 09, 2014 12:48 pm
- Post datetime: 2016-10-02T18:44:07+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Well,  I got  my Reasons)) Let's just say, I need it for Testing-  and,   as far as I know,  Tex and Tex0  are not Only used  in Shadow  of Mordor =P   
(Dam, I  DO hope  they  make second game soon- but that's offtopic)
## Post #115
- Username: vpzneox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 09, 2014 12:48 pm
- Post datetime: 2016-11-05T14:14:02+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Well, no1?
## Post #116
- Username: vpzneox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 09, 2014 12:48 pm
- Post datetime: 2016-11-09T08:49:10+00:00
- Post Title: Re: Shadow Of Mordor .arch05

All I  am interested in is just converting  the DDS to TEX0  and reimporting atm
## Post #117
- Username: Ditta
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 13, 2015 11:07 pm
- Post datetime: 2017-02-03T00:53:45+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Thanks to erik945 for his cool texture transformer script. I mastered this texture extraction at last and it was super-easy to run. For users of Windows 7 and similar Windows versions - if you want to run this script, you don't need to write complicated paths in the command line, just install Python 27, associate the .py extensuin with Python27.exe and then double-click the script. When you see the black console window of Python, write just the path to your directory with unpacked tex0 files, nothing more is required! The script converts all textures in a minute, even HD textures. I write this at the case if noobs like me have encountered some problems with running this script on Windows. 
Just one question about textures once more - where to go for Marwen and Eryn models in the game archives? As far as I learned, there is seemingly no hd textures for these characters, but there must be their models with standard textures. Which arch05 should I explore for them? 
For all who needs hi-res textures for your extracted characters, I extracted them and posted here - [https://facepunch.com/showthread.php?t= ... st51790047](https://facepunch.com/showthread.php?t=1530068&p=51790047#post51790047). Although they lack 3d models themselves, but they can be useful if you have the meshes of these models. I hope someday there will be a backward script to convert dds into tex automatically, it would be great.
## Post #118
- Username: walamo15
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 26, 2017 1:10 am
- Post datetime: 2017-02-25T22:25:40+00:00
- Post Title: Re: Shadow Of Mordor .arch05

So how do i reimport the edited embb file into that arch05 file?
## Post #119
- Username: Horst Schimanski
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 19, 2017 3:15 pm
- Post datetime: 2017-04-19T07:48:07+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
> Ok after fixing the decompression issues, i managed to get the contents of the archives.

It seems like the archives contain other typeof containers. embb files.

Maybe someone has seen them before, i haven't.

Anyway embb files contain the actual raw files of the game.
I wrote a simple embb explorer in GTK python just to get a graphical view of the structure and i was able to get some files that i was most intersted in.

I've shared some orc files here  

https://www.dropbox.com/sh/7d9mhhbu8crq ... hWPFa?dl=0

Is fixation of decomp_data(...) published also in arch05explorer_gtk.py at [https://bitbucket.org/gregkwaste/.arch05_explorer/src](https://bitbucket.org/gregkwaste/.arch05_explorer/src)?
## Post #120
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-10-21T09:35:31+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from gregkwaste
>
> I could not help my self from taking a quick look on the files after my first minutes on this MAGNIFICENT game.

I  don't know the engine that the game was built on, so i have no idea if there is a similar storage theme on the archives.

What i've found so far:

Some bundlexmls are defined at the start of any archive which contain data about the rest of the files in the archive, so i guess these have to be parsed first and i'll try to do that tomorrow. These xml files are zlib compressed.

I'm attaching 2 sample xmls i managed to decompress.

https://www.dropbox.com/s/sygk3ov82wm1d ... xml05?dl=0
https://www.dropbox.com/s/uew0m4r8twavk ... xml05?dl=0

There are also some .embb files which contain some names in there, have not checked it yet how they are used.

I'm excited to be honest, because i can clearly see some .mat some .mesh some .skel files which i'll investigate tomorrow.


-----------------------------------
.arch05 Explorer v0.2




Latest Version Download Link
https://bitbucket.org/gregkwaste/.arch0 ... r_v0.2a.7z

Repository
https://bitbucket.org/gregkwaste/.arch05_explorer/

ChangeLog v0.2:
-64 bit application, handles tha largest archives
-Fixed Naming Issues in embb
-Added embb file export support

I can not choose to export models. models do not export. 
Although I do not command, I still do not export the models.   It's not the only one. 
can you help me. please
[Nalısl.PNG](https://xentaxbackup.github.io/file/13474_Nalısl.PNG)
## Post #121
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2017-10-29T16:46:35+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Okay, so...

I'm sort of new to this, but I assume that I'm supposed to get some sort of dialog or something when I press Export. Alas, I get nothing. Nothing at all...
Anyone know anything?

I'm running windows 10, if that helps...

EDIT: I have looked through the pages, and attempted to run the various suggested QuuickBMS Scripts, but to no avail.
Can anyone help?
## Post #122
- Username: vpzneox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 09, 2014 12:48 pm
- Post datetime: 2017-11-03T23:31:36+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Still  not  sure how to Convert   Tex0 files     Tried converters   for both  Erik945's  and  Zaramot's    .PY  files seem  to either convert tex0  into  1kb dds, that's not openable   by graphical editors,  or (Zaramot's converter- also  .py)  seems to flicker and disappear as soon  as I launch it. 
Am I doing something  wrong?
## Post #123
- Username: Rkpaarsa
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 20, 2018 11:58 pm
- Post datetime: 2018-11-07T15:40:30+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from Paul44
>
> I've been experimenting with Watch Dogs, and used a batchfile there to extract the DDS files "automatically". Based on the example posted earlier, I could easily adapt this for SoM.
I assume that - for the Fullname extraction - the folder structure always starts at position 18.
Unfortunately, sofar I'm not able to extract any of the arch05 files with quickbms. I keep getting error: "Not enough storage is available to process this command.". No matter what script/EXE I am using (EXE=standard or 4GB vs)...
And I tried this on several arch05 files.
p

ps: you'll need to download Swiss File Knife yourself (which is what I use to extract)
ps2: I've 4 GB Ram memory
ps3: you can easily adapt the batchfile to analogue file types (w/ header)

I can't download it when i try to download it says you dont have permission to download.
Help me
## Post #124
- Username: Rkpaarsa
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 20, 2018 11:58 pm
- Post datetime: 2018-11-07T16:02:43+00:00
- Post Title: Re: Shadow Of Mordor .arch05

> Reply from erik945
>
> Release of texture converter.
Start this script.
Enter path to the directory with textures. Script recursive find *.tex or *.tex0 (hd addon) files and rewrite correct DDS header.
P.S. Very simple format  

UPD fixed small bug with "unASCII" symbols

Hi erik945 
 I downloaded your converter and it works fine with .tex files up to 5 MB but some of the .tex  file in are 44 MB and your converter can't convert them to DDS can you please update it .
Thanks in advance
## Post #125
- Username: DavidisGamingHD
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 12, 2021 8:35 pm
- Post datetime: 2021-06-12T12:36:38+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Did anyone happen to extract many of the Orcs as .FBX? I have a ton of textures for them, just need a large selection of the models. If anyone was kind enough to upload them, please link me or PM me!
## Post #126
- Username: Infernum31
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 01, 2023 4:37 pm
- Post datetime: 2023-09-29T17:04:58+00:00
- Post Title: Re: Shadow Of Mordor .arch05

Hello, how to fix the export button in arch05explorer, because it doesn’t work, if anyone knows, please help.
