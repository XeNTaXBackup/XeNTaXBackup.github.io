## Post #1
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2017-05-23T03:14:10+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

I'm not sure if this applies to "The House Of The Dead" and "The House Of The Dead 3" (<- I believe it's another format but the first, I'm not quite sure)

But here it goes,

everything except its game sounds are in .bin (Binary) format. They're from PC.

I have seen several threads stating other games in .bin format so I hope this works as well.

No-one has ever make a topic about this game so it's kind of weird. I wonder if it's possible to do it.

Here's the file:

[https://drive.google.com/file/d/0B65RgA ... 51elE/view](https://drive.google.com/file/d/0B65RgAuEXgTBRlZHZGlsdk51elE/view)
## Post #2
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2017-05-24T08:43:11+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

Well, I will just wait for a week...

CAM - Camera position (On-Rail)
COLI - Collider (Maps)
EVT - Event
MOT - Animations / Motions
POL - Models and stuff
SOUND - Sounds
TEX - Textures
## Post #3
- Username: Mortisanti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue May 31, 2016 2:35 pm
- Post datetime: 2018-09-04T22:16:09+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

I'm interested in this project as well, but I don't have the knowledge to identify the file structures in a Hex Editor nor write a BMS script to extract from the game archives.

Oddly enough, it's possible to open "coli.bin" located in the "coli" folder with WinRAR. Within it are files all with the same names as the ones in the "coli" folder and a .TBL file that can be opened in notepad:

```
F COLI0.BIN;1                       	coli0.bin
F COLI1.BIN;1                       	coli1.bin
F COLI2.BIN;1                       	coli2.bin
F COLI3.BIN;1                       	coli3.bin
F COLI4.BIN;1                       	coli4.bin
F COLI5.BIN;1                       	coli5.bin
F COLI6.BIN;1                       	coli6.bin
F COLIT.BIN;1                       	coliT.bin

```


Some other random info: I recently learned that you can go into the "tex" folder and rename "scr_blood_red.bin" to "scr_blood_green.bin" to replace the monsters' green blood with red blood.
## Post #4
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2018-12-04T19:49:53+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

The .bin files in this game are definitely different that Hotd 1, III and 4; I can tell you that from experience since I've successfully extracted models from those games.  I'm planning to look into these .bin files early next year, hopefully I can make some progress on it.
## Post #5
- Username: Mortisanti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue May 31, 2016 2:35 pm
- Post datetime: 2018-12-04T22:02:19+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

> Reply from egregiousguy
>
> The .bin files in this game are definitely different that Hotd 1, III and 4; I can tell you that from experience since I've successfully extracted models from those games.  I'm planning to look into these .bin files early next year, hopefully I can make some progress on it. Nice. Not to mention, I think the .bin files between the version published by SEGA and the one published by Empire Interactive may be different (or I wasn't able to rip subchannel data from my CD properly). More info, [here](https://zenhax.com/viewtopic.php?f=9&t=4225).

Also, here's a BMS script by chrrox that can be used to decompress the texture .bin files:

```
#quickbms script by chrrox
comtype PRS
get NAME basename
get EXT extension
string NAME + "_dec."
string NAME + EXT
get SIZE long
get ZSIZE asize
math ZSIZE -= 4
clog NAME 4 ZSIZE SIZE
```
## Post #6
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2018-12-22T05:23:46+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

> Reply from Mortisanti
>
> egregiousguy wrote:The .bin files in this game are definitely different that Hotd 1, III and 4; I can tell you that from experience since I've successfully extracted models from those games.  I'm planning to look into these .bin files early next year, hopefully I can make some progress on it. Nice. Not to mention, I think the .bin files between the version published by SEGA and the one published by Empire Interactive may be different (or I wasn't able to rip subchannel data from my CD properly). More info, here.

Also, here's a BMS script by chrrox that can be used to decompress the texture .bin files:
Code: Select all#House of the dead
#quickbms script by chrrox
comtype PRS
get NAME basename
get EXT extension
string NAME + "_dec."
string NAME + EXT
get SIZE long
get ZSIZE asize
math ZSIZE -= 4
clog NAME 4 ZSIZE SIZE

I tested out the bms script and it worked great on texture files. There seem to be a few .bin files that don't work with the script because the file is already decrypted  such as ST1_1.BIN.  I also realized that the bms script works with the POL folder for the models because the output data looks very similar to the data I've been seeing for other model formats so expect to see some maps and models very soon next year.
## Post #7
- Username: Mortisanti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue May 31, 2016 2:35 pm
- Post datetime: 2018-12-22T05:56:18+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

> Reply from egregiousguy
>
> I tested out the bms script and it worked great on texture files. There seem to be a few .bin files that don't work with the script because the file is already decrypted  such as ST1_1.BIN.  I also realized that the bms script works with the POL folder for the models because the output data looks very similar to the data I've been seeing for other model formats so expect to see some maps and models very soon next year.
That's good to hear. Which copy of HOD2 are you using?

Also, I wonder how much progress this guy has made despite the video being 10 years old: [https://www.youtube.com/watch?v=v7uXaBYf6Zk](https://www.youtube.com/watch?v=v7uXaBYf6Zk)
His last video was uploaded 3 months ago, so he's still somewhat active.
## Post #8
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2018-12-22T09:14:11+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

> Reply from Mortisanti
>
> 
That's good to hear. Which copy of HOD2 are you using?
I tried using a Dreamcast dump but the textures came out all garbled.  I ended up finding an old copy of the game on a backup drive back from who knows when and it had better results.

> Reply from Mortisanti
>
> 
Also, I wonder how much progress this guy has made despite the video being 10 years old: https://www.youtube.com/watch?v=v7uXaBYf6Zk
His last video was uploaded 3 months ago, so he's still somewhat active.
Yeah, I've seen that video many times.  That's how I was first inspired to extract the maps from HotD1 which then led to HotD III and 4.  I commented on that video a few months ago and I think he said no longer had the files or it was tucked away in a backup drive somewhere.
## Post #9
- Username: Mortisanti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue May 31, 2016 2:35 pm
- Post datetime: 2018-12-22T09:38:46+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

> Reply from egregiousguy
>
> I tried using a Dreamcast dump but the textures came out all garbled.  I ended up finding an old copy of the game on a backup drive back from who knows when and it had better results.
Ah, so it's a PC version?

> Reply from egregiousguy
>
> 
Yeah, I've seen that video many times.  That's how I was first inspired to extract the maps from HotD1 which then led to HotD III and 4.  I commented on that video a few months ago and I think he said no longer had the files or it was tucked away in a backup drive somewhere.
Well, that would be a shame if he abandoned his project.
## Post #10
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2020-04-29T02:53:12+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

A little progress update: 

[https://youtu.be/3UzYZCV6H4o](https://youtu.be/3UzYZCV6H4o)

I'll post a more detailed explanation of the format when I get around to it.
## Post #11
- Username: hazmeister
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 14, 2020 4:40 am
- Post datetime: 2020-05-13T20:56:43+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

This is so awesome!  Any chance of uploading the blender project somewhere?
## Post #12
- Username: hatsunemiekuah
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 10, 2022 3:03 am
- Post datetime: 2022-05-09T19:12:47+00:00
- Post Title: The House Of The Dead 2 (PC) .bin files

> Reply from egregiousguy ↑Sat Dec 22, 2018 5:14 pm at Sat Dec 22, 2018 5:14 pm
>
> 
Mortisanti wrote:
That's good to hear. Which copy of HOD2 are you using?
I tried using a Dreamcast dump but the textures came out all garbled.  I ended up finding an old copy of the game on a backup drive back from who knows when and it had better results.
Mortisanti wrote:
Also, I wonder how much progress this guy has made despite the video being 10 years old: https://www.youtube.com/watch?v=v7uXaBYf6Zk
His last video was uploaded 3 months ago, so he's still somewhat active.
Yeah, I've seen that video many times.  That's how I was first inspired to extract the maps from HotD1 which then led to HotD III and 4.  I commented on that video a few months ago and I think he said no longer had the files or it was tucked away in a backup drive somewhere.

Greeting sir. i have downloaded the tools but the guides here [ have lost](https://steamcommunity.com/sharedfiles/filedetails/?id=303487646) which i found from [here](https://zenhax.com/viewtopic.php?f=9&t=4225#p38129)

Can somebody please tells us how to mod House of the Dead 2 textures please? thanks in advance...
