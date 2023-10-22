## Post #1
- Username: ninearts
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 30, 2012 5:33 am
- Post datetime: 2012-11-29T22:53:38+00:00
- Post Title: Extracting Audio from Hitman Absolution

Having finished playing the game I decided to get my hands on those pretty sounds and songs in the game 
First of all, I must say I'm new here and I'm a noob when it comes to quickbms, I just started getting the hang of it. The script I created is working just fine and I was able to extract all of the FSB5 banks (the format of all sounds in game, I guess) from .PC_RESOURCELIB files stored in folder pc.layoutconfig.
Here's the code:
[spoiler]

```
# Archive Format: *.PC_RESOURCELIB
# Audio format: *.fsb (FMOD's sample bank)
# Tip1: use FMOD Designer to play/rebuild banks
# Tip2: use Aezay FSB Extractor 12.07.03 to convert to WAV (PCM uncompressed)
# Copyright 2012-11-29 by ninearts @ Xentax
set NEWNAME string "res_"
set EXTENSION string ".fsb"
set COUNTER 0
for
findloc FSB string "FSB5"
goto FSB 0
get IDFSB long
get UNK1 long
if UNK1 < 16
get ENTRIES long
math ENTRIES *= 4
get HEADERSIZE long
get NAMELENGTH long
get DATASIZE long
savepos IDHEADER
goto IDHEADER 0
goto 36 0 SEEK_CUR
goto HEADERSIZE 0 SEEK_CUR
goto ENTRIES 0 SEEK_CUR
getdstring FILENAME NAMELENGTH
set HEADERINFO 0
math HEADERINFO += 60
math HEADERINFO += HEADERSIZE
math HEADERINFO += NAMELENGTH
math DATASIZE += HEADERINFO
if NAMELENGTH == 0
set RANDOMNAME NEWNAME
math COUNTER += 1
string RANDOMNAME += COUNTER
string RANDOMNAME += EXTENSION
log RANDOMNAME FSB DATASIZE
else
string FILENAME += EXTENSION
log FILENAME FSB DATASIZE
endif
else
findloc FSB string "FSB5"
endif
next

```

[/spoiler]

Enjoy and happy extracting 
ninearts

EDIT 17.01.2020

I've created a small program in C# based on that code above. 
That should facilitate your endeavors 
See the attachement


 hitmanaudiotools.zip
Hitman Audio Tools v. 1.1 (100.95 KiB) Downloaded 125 times
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-11-30T18:18:25+00:00
- Post Title: Extracting Audio from Hitman Absolution

Thanks!
## Post #3
- Username: killer7
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 08, 2011 3:50 pm
- Post datetime: 2012-12-07T19:31:46+00:00
- Post Title: Extracting Audio from Hitman Absolution

Someone can convert on MP3 all the audio files in the game and upload it?

I don't know how do it!
## Post #4
- Username: saitek1911
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 09, 2012 5:26 am
- Post datetime: 2012-12-08T08:15:04+00:00
- Post Title: Extracting Audio from Hitman Absolution

> Reply from ninearts
>
> Having finished playing the game I decided to get my hands on those pretty sounds and songs in the game 
First of all, I must say I'm new here and I'm a noob when it comes to quickbms, I just started getting the hang of it. The script I created is working just fine and I was able to extract all of the FSB5 banks (the format of all sounds in game, I guess) from .PC_RESOURCELIB files stored in folder pc.layoutconfig.
Here's the code:
Code: Select all# Game: Hitman Absolution (PC - Steam Version)
# Archive Format: *.PC_RESOURCELIB
# Audio format: *.fsb (FMOD's sample bank)
# Tip1: use FMOD Designer to play/rebuild banks
# Tip2: use Aezay FSB Extractor 12.07.03 to convert to WAV (PCM uncompressed)
# Copyright 2012-11-29 by ninearts @ Xentax
idstring "BILR"
set NEWNAME string "res_"
set EXTENSION string ".fsb"
set COUNTER 0
for
findloc FSB string "FSB5"
goto FSB 0
get IDFSB long
get UNK1 long
if UNK1 < 16
get NUMSTRING long
math NUMSTRING *= 4
get HEADERSIZE long
get NAMELENGTH long
get DATASIZE long
goto FSB 0
goto 60 0 SEEK_CUR
savepos HEADSTART
goto HEADSTART 0
goto HEADERSIZE 0 SEEK_CUR
savepos ENDHEAD
goto ENDHEAD 0
goto NUMSTRING 0 SEEK_CUR
getdstring FILENAME NAMELENGTH
savepos DATASTART
goto DATASTART 0
set HEADERINFO 0
math HEADERINFO += 60
math HEADERINFO += HEADERSIZE
math HEADERINFO += NAMELENGTH
math DATASIZE += HEADERINFO
if NAMELENGTH == 0
set RANDOMNAME NEWNAME
math COUNTER += 1
string RANDOMNAME += COUNTER
string RANDOMNAME += EXTENSION
log RANDOMNAME FSB DATASIZE
else
string FILENAME += EXTENSION
log FILENAME FSB DATASIZE
endif
else
findloc FSB string "FSB5"
endif
next


I know there's someone who could make the code more efficient. Please let me know what you think 
Enjoy and happy extracting 

ps. Script is also in the attachement

ninearts

Thanks for the script, but i get out of memory problem all the time on MultiEx
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-12-08T21:08:58+00:00
- Post Title: Extracting Audio from Hitman Absolution

I can extract the segments but combining them is the problem because apparently there some overlaps at the start and end of each segment. Can anyone figure out how to combine the segments properly?
## Post #6
- Username: killer7
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 08, 2011 3:50 pm
- Post datetime: 2012-12-09T10:42:11+00:00
- Post Title: Extracting Audio from Hitman Absolution

> Reply from OrangeC
>
> I can extract the segments but combining them is the problem because apparently there some overlaps at the start and end of each segment. Can anyone figure out how to combine the segments properly?

Well, is better than nothing.    

But, so when you extract the segment what do you have? A small audio file or similar?
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-12-09T20:39:55+00:00
- Post Title: Extracting Audio from Hitman Absolution

Well each theme in the game is composed of 10 seconds segments. Combining them straight away ius not possible because there are gaps and overlaps that prevent a smooth transition.
## Post #8
- Username: killer7
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 08, 2011 3:50 pm
- Post datetime: 2012-12-09T21:15:15+00:00
- Post Title: Extracting Audio from Hitman Absolution

> Reply from OrangeC
>
> Well each theme in the game is composed of 10 seconds segments. Combining them straight away ius not possible because there are gaps and overlaps that prevent a smooth transition.

Uhm, understand.
## Post #9
- Username: killer7
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 08, 2011 3:50 pm
- Post datetime: 2012-12-16T20:37:50+00:00
- Post Title: Extracting Audio from Hitman Absolution

Some news?
## Post #10
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-21T23:32:23+00:00
- Post Title: Extracting Audio from Hitman Absolution

how use fmod no way to do batch for him ? fmod don't stop crashing on compile

i try this cmd line 
fmod_designercl.exe -pc 01.fdp -pcm

build crash on some fsb but no crash one by one 
log not identify source of problem someone got
## Post #11
- Username: ninearts
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 30, 2012 5:33 am
- Post datetime: 2012-12-25T16:26:40+00:00
- Post Title: Extracting Audio from Hitman Absolution

I've also found out that themes are split into segments, which are of random length. The only thing that remains constant for them is the overlap of 0.4 sec. I used Adobe Audition to put the pcm wav segments together and applied 0.2 sec wave in (except 1 segment) and 0.4 wave out (except last segment). The result caressed my ears LOL. No pops no cracks during play ) 
I did all manually, it was quite a mastodontic job. I created scripts for waving in and out, but couldn't come up with an idea of batch processing more of this splendid stuff.
## Post #12
- Username: killer7
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 08, 2011 3:50 pm
- Post datetime: 2012-12-25T20:19:29+00:00
- Post Title: Extracting Audio from Hitman Absolution

> Reply from ninearts
>
> I've also found out that themes are split into segments, which are of random length. The only thing that remains constant for them is the overlap of 0.4 sec. I used Adobe Audition to put the pcm wav segments together and applied 0.2 sec wave in (except 1 segment) and 0.4 wave out (except last segment). The result caressed my ears LOL. No pops no cracks during play ) 
I did all manually, it was quite a mastodontic job. I created scripts for waving in and out, but couldn't come up with an idea of batch processing more of this splendid stuff.

You are great!
## Post #13
- Username: killer7
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 08, 2011 3:50 pm
- Post datetime: 2012-12-29T10:26:11+00:00
- Post Title: Extracting Audio from Hitman Absolution

> Reply from ninearts
>
> I've also found out that themes are split into segments, which are of random length. The only thing that remains constant for them is the overlap of 0.4 sec. I used Adobe Audition to put the pcm wav segments together and applied 0.2 sec wave in (except 1 segment) and 0.4 wave out (except last segment). The result caressed my ears LOL. No pops no cracks during play ) 
I did all manually, it was quite a mastodontic job. I created scripts for waving in and out, but couldn't come up with an idea of batch processing more of this splendid stuff.

Some news?
## Post #14
- Username: kangmin
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 17, 2012 4:38 pm
- Post datetime: 2013-01-10T10:08:09+00:00
- Post Title: Extracting Audio from Hitman Absolution

any idea where to get the q toggle shooting sound fx ? @_@ like the after math of grenade explosion the *eeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiii* sound
## Post #15
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-10T16:10:21+00:00
- Post Title: Extracting Audio from Hitman Absolution

i try on another computer for fmod design compile but it's crash on build again
## Post #16
- Username: ninearts
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 30, 2012 5:33 am
- Post datetime: 2013-02-06T11:49:49+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

@ kilik I've recently found out, to my surprise, that we are in the same boat. I mean I started encountering the same problem as you. FMOD designer crashes on rebuild. I got pissed and decided to look for the root of this problem. What I have ascertained is that some of the extracted FSB5 banks are causing the designer to crash. It must be something with their structure that they cannot be rebuilt by "force software method" (drag and drop into events).

How did I get to it? Well after failed rebuilt I checked the folder .fsbcache inside program's main directory. Once you do the rebuild .fobj files are created in that folder. If you look at their sizes and notice a file with 0kb size it means that this is a file that cannot be rebuilt. 
So I went on with deleting those files from the events list and wavebank and try rebuilding. I had a list of nearly 200 sounds and found 20 that were bad eggs. 
I'm definitely going to try a workaround for these. 

I have also found out that most of the extracted banks have Vorbis compression. Rebuilding with MP3 compression type gave me best results (some of the files - mainly dialogs - sounded distorted and slomo when I used PCM compression)

@kangmin 

I've prepared a package of all nifty sounds, including the one you are talking about. I will upload them in the afternoon, right now I'm at work 

here's the package: [http://www29.zippyshare.com/v/66022606/file.html](http://www29.zippyshare.com/v/66022606/file.html)

You will find some of the songs here too. (I set the Waikiki Inn tune as my waking alarm haha)
## Post #17
- Username: 20Bucks
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 31, 2013 6:45 pm
- Post datetime: 2013-03-31T15:02:35+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

Hey, can someone upload a folder with all the audio files extracted? (.fsb, .wav or .mp3, either way its fine).

I have tried using the script with MultiEx, QuickBMS, QuickBMS not updated, the script in text form and in .bms form but I just can't do it. Either it doesn't work and it has a error or it only extracts 1/10th of the files, its really frustrating.
## Post #18
- Username: ninearts
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 30, 2012 5:33 am
- Post datetime: 2013-04-13T06:00:44+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

Here's my new brainchild:

I have recoded the script in C#. That should help you a lot:

[https://ninearts.tumblr.com/](https://ninearts.tumblr.com/)

Best wishes,

ninearts
## Post #19
- Username: ninearts
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 30, 2012 5:33 am
- Post datetime: 2013-04-20T09:19:22+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

> Reply from killer7
>
> ninearts wrote:I've also found out that themes are split into segments, which are of random length. The only thing that remains constant for them is the overlap of 0.4 sec. I used Adobe Audition to put the pcm wav segments together and applied 0.2 sec wave in (except 1 segment) and 0.4 wave out (except last segment). The result caressed my ears LOL. No pops no cracks during play ) 
I did all manually, it was quite a mastodontic job. I created scripts for waving in and out, but couldn't come up with an idea of batch processing more of this splendid stuff.

Some news?

I managed to create a small program "Hitman Concats" that merges all the segments. 
Well, here it is:
[http://www.hitmanforum.com/index.php/to ... try1603292](http://www.hitmanforum.com/index.php/topic/58859-hitman-absolution-audio-extractor/#entry1603292)

Hope you like it.
## Post #20
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-07-24T00:23:57+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

-
## Post #21
- Username: xuu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 05, 2019 11:28 pm
- Post datetime: 2019-05-05T15:44:51+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

0000
## Post #22
- Username: zeaofsuos
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Apr 19, 2019 10:07 pm
- Post datetime: 2019-05-09T20:23:35+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

ADMIN, PLEASE DELETE.
## Post #23
- Username: docbrownpants
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 05, 2019 8:01 pm
- Post datetime: 2020-02-25T20:34:12+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

> Reply from ninearts ↑Fri Nov 30, 2012 6:53 am at Fri Nov 30, 2012 6:53 am
>
> 
<snip>
EDIT 17.01.2020

I've created a small program in C# based on that code above. 
That should facilitate your endeavors 
See the attachement
--> hitmanaudiotools.zip <--

Uh dude, you attached a .gif file as a zip...
## Post #24
- Username: mark92
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 08, 2016 7:14 am
- Post datetime: 2020-04-30T17:22:27+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

Read [here](https://forum.xentax.com/viewtopic.php?f=17&t=21630#p160471).
I don't get why the author made it like this but the important thing is that it's working.
## Post #25
- Username: trainhobovegas
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 23, 2016 12:37 am
- Post datetime: 2022-05-05T22:57:33+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

I hate to break it to you but the zip file refuses to open
Cannot open the file as [zip] archive
Errors: Is not archive
## Post #26
- Username: Youba
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 07, 2023 7:43 am
- Post datetime: 2023-09-06T23:46:16+00:00
- Post Title: Re: Extracting Audio from Hitman Absolution

wass up bro i need a way to open hitman absolution localization
