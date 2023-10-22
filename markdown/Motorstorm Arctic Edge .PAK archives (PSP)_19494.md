## Post #1
- Username: RossRapper
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Sep 18, 2014 9:22 am
- Post datetime: 2019-02-14T11:34:39+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

Trying to get movies from MSAE. JPCSP failed, just as some other things I've thrown at the two .PAKs from the game. And I couldn't find any game-specific tool around the web. There also was some kind of universal extractor around here: [viewtopic.php?f=13&t=6572](http://forum.xentax.com/viewtopic.php?f=13&t=6572)

The download link is long dead though. Besides, I'm not sure how heavily the archive is encrypted/compressed - after all these years of small-time hex-editing here and there I'm still not skilled enough even to use pointers effectively, so file headers and all this stuff... is way above my level, unfortunately.

So if anyone would be able to give me a hand - I would be very grateful. Link to the .PAKs: [https://www.mediafire.com/file/5z737j12 ... S.rar/file](https://www.mediafire.com/file/5z737j121oj5mix/MSAE_PAKS.rar/file)

Thanks.
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2019-02-19T15:35:08+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

I guess someone needs to write a new unpacker.
Here's some info about the file format:

MAIN.PAK:

50 41 4B 20	magic word "PAK "
01 00 00 00	?
93 78 DA A3	number of files (XORed with 0xA3DA79B6) = 0x1E4
34 41 00 00	size of string table
1F 00 00 00	lenght of directory name
A1 FF 99...	directory name (XORed with 0xC5) = "d:\workdir\MotorStormPSP\game\"

for (number of files) {
00 00 00 00 	offset in string table
00 60 00 00 	offset in current file
9C C2 08 00 	file size
9C C2 08 00	file size again?
}

now comes the string table (XORed with 0xB5)
F1 D4 C1 D4 EA E5 E6 E5 E9 E7 D0 D2 85 9B E5 E6 E5 EA FC FB FC EA F8 F4 FC FB B5
becomes
"Data_PSP\Reg0.PSP_INI_MAIN"


I noticed that files that start with "BBZL" are zlib compressed.
Haven't done any further investigation on the actual files.


If you are only interested in the movie files, you could also obtain them manually.
First open FE.PAK with a hex editor
Search for the string "PSMF"

The last number of the first 16 bytes is the file size.
For example: 50 53 4D 46 30 30 31 34 00 00 08 00 00 AF 90 00

Add 800 to AF9000 -> AF9800

Select the block (starting from 50 53 4D 46), copy it to a new file and save it as .pmf file.
Finally google how to convert pmf to avi
## Post #3
- Username: RossRapper
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Sep 18, 2014 9:22 am
- Post datetime: 2019-02-19T17:22:33+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

> Reply from herbert3000 ↑Tue Feb 19, 2019 11:35 pm at Tue Feb 19, 2019 11:35 pm
>
> 
If you are only interested in the movie files, you could also obtain them manually.
First open FE.PAK with a hex editor
Search for the string "PSMF"

The last number of the first 16 bytes is the file size.
For example: 50 53 4D 46 30 30 31 34 00 00 08 00 00 AF 90 00

Add 800 to AF9000 -> AF9800

Select the block (starting from 50 53 4D 46), copy it to a new file and save it as .pmf file.
Finally google how to convert pmf to avi

A-ha. Thanks A LOT for this. I'll try it a bit later today or tomorrow and will write back about how it went through.
## Post #4
- Username: RossRapper
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Sep 18, 2014 9:22 am
- Post datetime: 2019-02-20T18:39:32+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

> Reply from herbert3000 ↑Tue Feb 19, 2019 11:35 pm at Tue Feb 19, 2019 11:35 pm
>
> 
The last number of the first 16 bytes is the file size.
For example: 50 53 4D 46 30 30 31 34 00 00 08 00 00 AF 90 00

Add 800 to AF9000 -> AF9800

Select the block (starting from 50 53 4D 46), copy it to a new file and save it as .pmf file.
Finally google how to convert pmf to avi

Alright... some questions that didn't strike me until I was actually on it...

Why are we adding 800 to AF9000? Because of the  00 00 08 00 right?
And how do we calculate the end of the block? It should be the address of 50 plus AF9800, correct? - That's correct, I've just ran it myself and... well, it is how it is, nothing to add here.

Thanks.

Edit: I gave it a try meanwhile. Managed to get the video, so... I'm cool and this will do. Thank you very much for your answer.
The questions above still stay though, just for the sake of knowledge.
## Post #5
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2019-02-20T22:40:25+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

Glad I could help 
I guess 800 is the size of the  file header.

By the way, those are the filenames of the movies:
FE_Movie_Alaska.pmf
FE_Movie_Attract.pmf
FE_Movie_Bigbiglogo.pmf
FE_Movie_Characters.pmf
FE_Movie_Credits_Bigbig.pmf
FE_Movie_Credits_Loop.pmf
FE_Movie_FrontendA.pmf
FE_Movie_HighAltitude.pmf
FE_Movie_Intro_A.pmf
FE_Movie_Intro_B.pmf
FE_Movie_LowAltitude.pmf
FE_Movie_MidAltitude.pmf
FE_Movie_MSworld.pmf
FE_Movie_Outro.pmf
FE_Movie_Vehicles.pmf
XMovie.pmf
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-21T11:57:47+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

here is bms script to unpack the pak file samples using herbert3000's findings.  


 MotorstormArcticEdge_PSP_pak.zip
(670 Bytes) Downloaded 80 times


it will also decompress those zlibbed files during extraction.
when you get the file exists prompt just press "a" to overwrite all, or "r" to
rename them, looks like they stored duplicates of a few files in the pak.
## Post #7
- Username: RossRapper
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Sep 18, 2014 9:22 am
- Post datetime: 2019-02-23T17:47:16+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

Thanks! This will be very handy if I'll ever need anything else from this game.
## Post #8
- Username: QrTa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 17, 2022 11:34 pm
- Post datetime: 2022-08-17T15:48:26+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

Hi guys!

Maybe I write too late.. 

Is it possible to unpack the .PAK files then pack it back after modifying some files?

I wanted to make a "texture pack" for ppsspp but find out every cutom livery every custom logo or moving the livery generates a new textuer when I dumped them.

So I wanted to unpack the PAK files, upscale the required textures then pack back and make the iso with umdgen. 

What do you think? Is it possible? Is it worth the time? 
Is there any unpacker which can pack it back to PAK? 

Thank you for the help!
## Post #9
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-17T18:15:58+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

> Is there any unpacker which can pack it back to PAK?

quickbms script provided by Acewell should do the work [download/file.php?id=15764](https://forum.xentax.com/download/file.php?id=15764)

Here is the tool's page [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
and documentation [http://aluigi.altervista.org/papers/quickbms.txt](http://aluigi.altervista.org/papers/quickbms.txt)

Try to read more about reimport mode in quickbms.txt.
## Post #10
- Username: QrTa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 17, 2022 11:34 pm
- Post datetime: 2022-08-18T05:47:50+00:00
- Post Title: Motorstorm Arctic Edge .PAK archives (PSP)

Thank you! I will give a try tomorrow maybe at the weekend! I hope it can work after some file modification because texture dumping is not an option to make texture pack for this game.
