## Post #1
- Username: RaineFeanaro
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 28, 2011 1:45 am
- Post datetime: 2011-08-27T18:06:18+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

Hi there,

I'm cuurently working on an translation patch for Inazuma Eleven strikers from japanese to english/german. The language isn't the problem, since japanese ist my second mother language, but I'm working the first time on a translation so I have a few questions:

1: I think I have to change the japanese letters in arabic letters first but how to start with it? For example Fire Emblem Radiant Dawn hast .font files which contain the letters, but Inazuma Eleven Strikers hasn't any at all.

2: Since I'm a member of a subgroup I'd like to sub the Opening Video but the file format is unkown to me since it's .mo. The header tells me its MOC5 converted.

I don't if it helps but here is the game tree:
partition.bin
|- boot.bin
|- bi2.bin
|- apploader.img
|- main.dol
|- fst.bin
|- dat.bin
|- grp.bin
+ Home Button (should be clear)
|- InazumaWii.brsar (It contains the sounds)
|- InazumaWii.dlf
|- InazumaWii.elf
|- mcb0.bln
|- mcb1.bln
+ movie (contains the opening video)
|- opening.bnr
|- scn.bin
+ stream (contains audio)
## Post #2
- Username: Rastsan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 28, 2011 2:06 am
- Post datetime: 2011-09-01T01:11:22+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

that is a mobiclip video file.  
if you can, record an avi of the clip as it plays.  either by capturing it through an input onto your computer by tv capture tools/ software.  Then edit the avi frame by frame.  then re-encode the avi back into the .mo file.  

as to the letters... time to research system specific stuff.  My experience is nds specific so i cannot really help you with that.
## Post #3
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-01T11:39:23+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

Since there are only a few files in the filetree you posted one of the files must be an archive. Are these really all files and directories?

For the font: As you already said the game maybe uses a graphicsfile which contains the font and you have to change it. Another possibility is that the game already uses a system that supports ASCII chars so that you "just" have to find out where and how the text is stored.
## Post #4
- Username: RaineFeanaro
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 28, 2011 1:45 am
- Post datetime: 2011-09-02T11:08:31+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

thanks for the answers^^

I looked into the game via GeckoUSB and it seems like it uses a graphic file wich contains the font. And yes thats all the files it has.
Also thanks for tip for the video encode. I'm looking now for a mobiclip converter.
## Post #5
- Username: Roxas75
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 03, 2010 9:20 pm
- Post datetime: 2011-09-10T22:17:12+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

I'd love to hel you in this project.
I can say that the encoding is shift-jis, and that the file mcb1.bln is the game archive.
However the files are compressed but i don't know what kind of compression is it.
Me too i have experience with DS, if you need help, i'm here.^^
## Post #6
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-11T08:39:44+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

Since you now know the archive you could post some bytes of it.
## Post #7
- Username: Roxas75
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 03, 2010 9:20 pm
- Post datetime: 2011-09-11T12:05:46+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

What do you mean? where i found the text?
Well i done a screen...
[screen.png](https://xentaxbackup.github.io/file/4705_screen.png)
## Post #8
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-11T13:14:19+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

To examine the archive it would be good to have it  I guess its quite big so you could upload just a part of it to the internet. (That's what I meant by speaking about a segment of the file). People cant do much with just a filename. It would be best to show us the beginning of the file, the so called header (not with a screenshot!) by uploading the first 50 mb (or more) of the archive or so. The more the better.
## Post #9
- Username: Roxas75
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 03, 2010 9:20 pm
- Post datetime: 2011-09-11T20:05:36+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

I can't upload it, my connection is slow... You can extract it with Wiiscrubber from your dump.
## Post #10
- Username: RaineFeanaro
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 28, 2011 1:45 am
- Post datetime: 2011-09-12T15:43:53+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: Roxas75
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 03, 2010 9:20 pm
- Post datetime: 2011-09-12T19:55:11+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

Actually i'm using MadEdit, i think it's the best, it supports a lot of encodings, Shift_Jis too!^^
## Post #12
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-15T16:02:03+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

I had a look at the file you uploaded. Here is what I found out:
The archive itself is not compressed.
It looks like every file in the archive has an extra header which is 25 bytes long (first 5 bytes are always zeros or the header is just 20 bytes long). The extra header contains the filesize(+16) in little endian byteorder (4 bytes long, offset 0x14). I could not make sense of the other values in the extra header... I guess there is a filetable in another file that tells the offsets and the filenames of the files in the archive -or at least the offsets.
Beside that it looks like the game is using the standard texture format of the wii (TPL, "0020AF30") for graphics.
## Post #13
- Username: RaineFeanaro
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 28, 2011 1:45 am
- Post datetime: 2011-09-15T16:15:45+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

About filetable. Can be something like this?


It's from the fst.bin file.
## Post #14
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-16T18:25:59+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

> Reply from RaineFeanaro
>
> About filetable. Can be something like this?


It's from the fst.bin file.
Something like this but in this case this a standard filetable that can be found on any? wii game.

EDIT: I could imagine the mcb0.bln holds the offsets to the files. Just a guess.
## Post #15
- Username: RaineFeanaro
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 28, 2011 1:45 am
- Post datetime: 2011-09-18T17:54:11+00:00
- Post Title: Inazuma Eleven Strikers: A few question about files

I found another one:


It's from the InazumaWii.elf file.
## Post #16
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-19T13:35:18+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

> Reply from RaineFeanaro
>
> I found another one:
It's from the InazumaWii.elf file.
As far as I know the elf-file is the standard Wii executable therefore I doubt it contains such a big filetable.

I was able to take a look at the mcb0.bln and from the looks it could be a filetable (little endian again!):

```
4bytes = fileid
4bytes = offset
4bytes = size
```
## Post #17
- Username: pache
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 20, 2011 3:39 pm
- Post datetime: 2011-09-20T08:23:26+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

Hello, i found another game using the same files. Is it usefull?
I didn't found any tool that could extract the .bin or the .bln files. 

Mahou Sensei Negima!? Neo-Pactio Fight!! NTSC-J

Partition 1
|__ 1.056          __update.inf
|__ 4.096          mcb0.bln
|__ 214.492       apploader.img
|__ 316.360       opening.bnr
|__ 583.680       dat.bin
|__ 600.064       evt.bin
|__ 1.952.288     NegimaWii.dol
|__ 4.341.760     vce.bin
|__ 14.301.408    NegimaSound.brsar
|__ 52.393.984    grp.bin
|__ 585.713.664  mcb1.bln
|__  _sys
|_________ 151.104    BOOT2-64-v2.wad
|_________ 1.614.528 IOS21-64-v514.wad
|__ THP
|_________ 28.087.488 MV05.thp
|_________ 33.675.616 MV02.thp
|_________ 34.261.824 MV03.thp
|_________ 34.412.512 MV01.thp
|_________ 35.207.040 MV04.thp
|__ stream (only lots of brstm files inside)
|__ HomeButton
|_________ 35        config.txt
|_________ 2.540    home_nosave.csv
|_________ 3.610    home.csv
|_________ 6.336    homeBtnIcon.tpl
|_________ 59.424  SpeakerSe.arc
|_________ 357.088 HomeButtonSe.brsar
|_________ 432.160 homeBtn_ITA.arc
|_________ 432.160 homeBtn_NED.arc
|_________ 432.160 homeBtn_SPA.arc
|_________ 432.160 homeBtn_GER.arc
|_________ 432.160 homeBtn.arc
|_________ 432.160 homeBtn_FRA.arc
|_________ 432.160 homeBtn_ENG.arc
## Post #18
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-25T16:28:01+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

I created a little tool that extracts the mcb1 with the information gathered from the mcb0.
It looks like the size specified in the mcb0 is not the real filesize of the file to extract and there is also the 25 bytes (sometimes 26? or just a compressionflag?) extra header for every extracted file. A value that represents the real filesize could be in this extra header at offset 0x14 (4 bytes long, little endian) but I'm not totally sure. Most files are bres files (wasnt able to open them in a bress-viewer) and some files don't make any sense at all. Maybe there are some trashfiles since the footer of the mcb0 holds a value that could be the number of files in the archive and its smaller than what you get by reading in every row -like I did.

The program will not respond while extracting! Just wait for it to finish!
[mcb-extract.zip](https://xentaxbackup.github.io/file/4739_mcb-extract.zip)
## Post #19
- Username: pache
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 20, 2011 3:39 pm
- Post datetime: 2011-10-12T21:54:00+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

The contents of this post was deleted because of possible forum rules violation.
[mcb.PNG](https://xentaxbackup.github.io/file/4771_mcb.PNG)
## Post #20
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-10-13T08:17:04+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

The format looks the same. By getting the offsets from the mcb0 you can make out the files in the mcb1. The tool is doing exactly this. But indeed it looks like it outputs some garbage. Anyway, most of the files it extracts are files of the mcb0-archive with a special header before the real file. In case of the negima game there are 0xD or 0XE bytes before the real file starts (SHTX... for example). I dont know what these files are, I just wrote the extractor.
## Post #21
- Username: RaineFeanaro
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 28, 2011 1:45 am
- Post datetime: 2011-11-23T16:24:51+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

Just a small feedback: I'm still working on this.
I finished up the translation for most of the text the only thing that remains is the insertion. But I think I need some help there... I still don't get where the text is actually stored.
## Post #22
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2012-03-15T20:03:20+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

Another game named "Aa Megami-sama"(Ah, My Goddess) has exactly the same fileformat.
## Post #23
- Username: RedChaos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 22, 2012 3:15 am
- Post datetime: 2012-06-21T19:20:45+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

is the patch done ?
## Post #24
- Username: RaineFeanaro
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 28, 2011 1:45 am
- Post datetime: 2012-10-01T12:55:03+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

So far I've dropped the patched for Strikers and working now on a Translation Patch for Strikers Xtreme which make much more sense cause I don't thing it will ever be released outside Japan.
The Translation ist almost done the only thing left ist the character description (the hole game dosen't have much Text at all), so I would say the patch ist at 55%. Since I still don't know how to insert it could take some more time. Even after the insertion it need some quality checking.
## Post #25
- Username: Dmitry
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 04, 2011 9:40 pm
- Post datetime: 2013-04-07T13:31:24+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

Suzumiya Haruhi no Heiretsu have exactly files like in Mahou Sensei Negima!? Neo-Pactio Fight!! NTSC-J
[07_04.png](https://xentaxbackup.github.io/file/6318_07_04.png)
## Post #26
- Username: Milozaki
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 25, 2020 4:11 am
- Post datetime: 2020-01-25T19:04:29+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

Hello, I would like to revive a Inazuma Eleven Go Strikers 2013 Translation, but I don´t know to edit the mbc1extract files with MadEdit.
Anyone can help me?
## Post #27
- Username: EmmeCipolla
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 09, 2020 3:32 pm
- Post datetime: 2020-07-09T09:30:42+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

> Reply from Milozaki ↑Sun Jan 26, 2020 3:04 am at Sun Jan 26, 2020 3:04 am
>
> 
Hello, I would like to revive a Inazuma Eleven Go Strikers 2013 Translation, but I don´t know to edit the mbc1extract files with MadEdit.
Anyone can help me?
I'm trying to do the same thing, but I'm stuck here... Anyone can help please?
## Post #28
- Username: Obluda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 03, 2021 8:10 pm
- Post datetime: 2021-03-03T12:20:04+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

Hey, to anyone that may come across this post. I'm currently translating the game "Inazuma Eleven GO Strikers 2013", most of the file formats (SHTXs, BLN, the compression algorithm too) are supported in a tool called "Kuriimu 2". 
If there's any question you'd like to ask, I'd gladly answer them, whether it's for Inazuma, or any other game developped by Shade.
## Post #29
- Username: Syura1999
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 31, 2022 8:57 pm
- Post datetime: 2022-05-31T13:05:09+00:00
- Post Title: Re: Inazuma Eleven Strikers: A few question about files

> Reply from Obluda ↑Wed Mar 03, 2021 8:20 pm at Wed Mar 03, 2021 8:20 pm
>
> 
Hey, to anyone that may come across this post. I'm currently translating the game "Inazuma Eleven GO Strikers 2013", most of the file formats (SHTXs, BLN, the compression algorithm too) are supported in a tool called "Kuriimu 2". 
If there's any question you'd like to ask, I'd gladly answer them, whether it's for Inazuma, or any other game developped by Shade.

Can you add me on discord, i need help with the .bin files outputed by Kuriimu 2 from the .bln files from the Negima game
Sato1999#0365
