## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-08T13:11:15+00:00
- Post Title: Crash Tag Team Racing - *.rcf

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-08T13:56:50+00:00
- Post Title: Crash Tag Team Racing - *.rcf

I took a look at the format and wrote this script - NAMES MISSING. Any suggestions?

```
get NAMEPOS long
math NAMEPOS += 0x14
goto 0x38
get FILES long

for i = 1 <= FILES
	get NAME_HASH long
	get OFFSET long
	get SIZE long
	get NAME basename
        string NAME += "_"
        string NAME += i
	log NAME OFFSET SIZE
next i
```
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-08T18:49:11+00:00
- Post Title: Crash Tag Team Racing - *.rcf

Nevermind, found out that Xpert from Gnie has a plugin.
However, if anyone's interested in the audio material, this script extracts those nameless *.rsd files into a file structure. Can be helpful when sorting out sfx from the music.

```
get NAME string
get SIZE asize
math SIZE -= 0x800
log NAME 0x800 SIZE
```
## Post #4
- Username: spongehog5000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 17, 2012 2:11 pm
- Post datetime: 2012-06-27T03:01:30+00:00
- Post Title: Crash Tag Team Racing - *.rcf

> Reply from AlphaTwentyThree
>
> Nevermind, found out that Xpert from Gnie has a plugin.
However, if anyone's interested in the audio material, this script extracts those nameless *.rsd files into a file structure. Can be helpful when sorting out sfx from the music.
Code: Select allgoto 0x1a
get NAME string
get SIZE asize
math SIZE -= 0x800
log NAME 0x800 SIZE

What is this script for, and how do I use it?
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-27T06:46:51+00:00
- Post Title: Crash Tag Team Racing - *.rcf

> Reply from spongehog5000
>
> AlphaTwentyThree wrote:Nevermind, found out that Xpert from Gnie has a plugin.
However, if anyone's interested in the audio material, this script extracts those nameless *.rsd files into a file structure. Can be helpful when sorting out sfx from the music.
Code: Select allgoto 0x1a
get NAME string
get SIZE asize
math SIZE -= 0x800
log NAME 0x800 SIZE

What is this script for, and how do I use it?
It's for quickbms [Download](http://aluigi.altervista.org/papers/quickbms.zip)
## Post #6
- Username: spongehog5000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 17, 2012 2:11 pm
- Post datetime: 2012-06-27T07:52:44+00:00
- Post Title: Crash Tag Team Racing - *.rcf

> Reply from C00L12345
>
> spongehog5000 wrote:AlphaTwentyThree wrote:Nevermind, found out that Xpert from Gnie has a plugin.
However, if anyone's interested in the audio material, this script extracts those nameless *.rsd files into a file structure. Can be helpful when sorting out sfx from the music.
Code: Select allgoto 0x1a
get NAME string
get SIZE asize
math SIZE -= 0x800
log NAME 0x800 SIZE

What is this script for, and how do I use it?
It's for quickbms Download

OK, Thanks! I tested out one RSD file with the script and got a WAV. Only problem is getting it to play. Any suggestions?
## Post #7
- Username: BrodyBlue
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 11, 2017 5:57 am
- Post datetime: 2017-12-12T21:59:23+00:00
- Post Title: Crash Tag Team Racing - *.rcf

I can't get the extracted .wav file to play either. Anyone know how to get it to play? I've tried to convert it to .aa3 and still nothing 

EDIT: It seems I can open and play the .wav file in Audacity. But is there an easier way?
## Post #8
- Username: emanuelect
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 16, 2021 9:34 pm
- Post datetime: 2022-11-19T20:16:41+00:00
- Post Title: Crash Tag Team Racing - *.rcf

Hi, I am trying to translate the gamecube version of the game. There are tools on the internet that allow me to extract the files inside the .rcf archive, but I can't replace them. I tried the script atg_core_cement.bms but it is not compatible. Rcf explorer allows me to extract the contents, but I cannot edit or replace.


[https://mega.nz/file/alRm0LxQ#C5zcM9nZ9 ... AfPvaewSeI](https://mega.nz/file/alRm0LxQ#C5zcM9nZ9K_DDoOIJmOlOsx8AamxWfODyAfPvaewSeI)
## Post #9
- Username: onizuka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 19, 2023 4:12 am
- Post datetime: 2023-05-18T20:24:55+00:00
- Post Title: Crash Tag Team Racing - *.rcf

> Reply from emanuelect ↑Sun Nov 20, 2022 4:16 am at Sun Nov 20, 2022 4:16 am
>
> 
Hi, I am trying to translate the gamecube version of the game. There are tools on the internet that allow me to extract the files inside the .rcf archive, but I can't replace them. I tried the script atg_core_cement.bms but it is not compatible. Rcf explorer allows me to extract the contents, but I cannot edit or replace.


https://mega.nz/file/alRm0LxQ#C5zcM9nZ9 ... AfPvaewSeI
Hey man, any luck working with that RCF. file? I am trying to translate a game too, ps2 in my case, but it's a real pain in the ass to repack the contents back into a RCF. archive...
## Post #10
- Username: emanuelect
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 16, 2021 9:34 pm
- Post datetime: 2023-05-19T11:32:45+00:00
- Post Title: Crash Tag Team Racing - *.rcf

No, unfortunately, I had no luck.
## Post #11
- Username: onizuka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 19, 2023 4:12 am
- Post datetime: 2023-05-19T12:29:55+00:00
- Post Title: Crash Tag Team Racing - *.rcf

Damn man... Boy we really need a tool for that:(
