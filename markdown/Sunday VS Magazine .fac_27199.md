## Post #1
- Username: OugiBoogie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 05, 2023 6:13 pm
- Post datetime: 2023-09-13T18:10:20+00:00
- Post Title: Sunday VS Magazine *.fac

Hey there. I was wondering if anyone could help me unpack this weird looking archive file? It's from a PSP game titled "Sunday VS Magazine Shuuketsu! Choujou Daikessen".

I thought it was an offshoot of the .farc files used in Miku Hatsune games, but the bms script for those can't handle it. I've also tried Game Extractor as well as Novasoft Extractor. No good. 

The aim is to get the models/textures and the voices of the characters if possible.

Any help is much appreciated. Cheers.

[https://www.mediafire.com/file/vwc2gafc ... m.fac/file](https://www.mediafire.com/file/vwc2gafcg8zigiy/sxm.fac/file)
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-09-13T22:32:50+00:00
- Post Title: Sunday VS Magazine *.fac

There should be a FAH or any companion file besides the FAC since it contains the TOC information of the archive.
WIthout it, it's just a continuous one big blob of a file without any context.

Can you find that companion file and upload it?
## Post #3
- Username: OugiBoogie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 05, 2023 6:13 pm
- Post datetime: 2023-09-17T15:45:45+00:00
- Post Title: Sunday VS Magazine *.fac

> Reply from BloodRaynare ↑Thu Sep 14, 2023 6:32 am at Thu Sep 14, 2023 6:32 am
>
> 
There should be a FAH or any companion file besides the FAC since it contains the TOC information of the archive.
WIthout it, it's just a continuous one big blob of a file without any context.

Can you find that companion file and upload it?

Apologies. I wasn't aware this was needed, but here it is. Thanks again for the help!

[https://www.mediafire.com/file/578bgc0e ... m.fah/file](https://www.mediafire.com/file/578bgc0exrugp90/sxm.fah/file)
## Post #4
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-09-17T22:27:19+00:00
- Post Title: Sunday VS Magazine *.fac

> Reply from OugiBoogie ↑Sun Sep 17, 2023 11:45 pm at Sun Sep 17, 2023 11:45 pm
>
> 

Apologies. I wasn't aware this was needed, but here it is. Thanks again for the help!

https://www.mediafire.com/file/578bgc0e ... m.fah/file

Turns out aluigi already created a BMS script for this game
[https://aluigi.altervista.org/bms/sunda ... ne_fah.bms](https://aluigi.altervista.org/bms/sunday_magazine_fah.bms)

But in order for the script to work, you have to edit and uncomment this line:

```

```


Because your files has those fields
Just remove the "# " to uncomment it

No real filenames though since the FAH file didn't provide any, so QuickBMS will assign the name with hex number counters

The WAV file is actually an AT3 file, just rename the extensions
Sound effects/voices are in the PPH/DAT pair
Models and it's texture are inside the FAR file (use the same script to extract them, again you have to rename the extensions to FAC though in order to extract them)
## Post #5
- Username: OugiBoogie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 05, 2023 6:13 pm
- Post datetime: 2023-09-18T07:13:30+00:00
- Post Title: Sunday VS Magazine *.fac

> Reply from BloodRaynare ↑Mon Sep 18, 2023 6:27 am at Mon Sep 18, 2023 6:27 am
>
> 

Thanks again for the reply. I hit an error with this script, though.

Can't read 64 bytes from offset 7e4f2d9d.
Last script line before the error or that produced the error:
19 log "" OFFSET SIZE 1

It only extracts a .lua from the .fah. It doesn't grab anything from the .fac file.
## Post #6
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-09-18T07:47:59+00:00
- Post Title: Sunday VS Magazine *.fac

> Reply from OugiBoogie ↑Mon Sep 18, 2023 3:13 pm at Mon Sep 18, 2023 3:13 pm
>
> 

I thought I already told you to edit and uncomment the line inside the script first, right?
Read my above post again carefully.
## Post #7
- Username: OugiBoogie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 05, 2023 6:13 pm
- Post datetime: 2023-10-05T16:47:07+00:00
- Post Title: Sunday VS Magazine *.fac

> Reply from BloodRaynare ↑Mon Sep 18, 2023 3:47 pm at Mon Sep 18, 2023 3:47 pm
>
> 
OugiBoogie wrote: ↑Mon Sep 18, 2023 3:13 pm


I thought I already told you to edit and uncomment the line inside the script first, right?
Read my above post again carefully.

Got this working. My mistake was removing both # symbols and not just the one you mentioned. Thanks again.
## Post #8
- Username: OugiBoogie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 05, 2023 6:13 pm
- Post datetime: 2023-10-05T17:33:32+00:00
- Post Title: Sunday VS Magazine *.fac

And now there are these .pak files, but gitmo can't grab the gmo. Any script for these? Thank you kindly.
## Post #9
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-10-06T10:07:33+00:00
- Post Title: Sunday VS Magazine *.fac

> Reply from OugiBoogie ↑Fri Oct 06, 2023 1:33 am at Fri Oct 06, 2023 1:33 am
>
> 
And now there are these .pak files, but gitmo can't grab the gmo. Any script for these? Thank you kindly.

Sorry but looks like the GMO file for this game are custom (Header was "GMOX" instead of "OMG.00.1PSP").
