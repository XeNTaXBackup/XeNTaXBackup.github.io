## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-07-08T19:26:36+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

I know this is possibly the most UNLIKELY request because it is PSX, but I was wondering on this format for some time. It is from Breath of Fire 4 and I am pretty sure it contains an image format that appears to not be a TIM. Not sure what, this format wasn't extensively researched, probably my look into it was the most extensive O_o in any case I'm attaching one.

Edit: Eh... [http://www.geocities.com/shindarkfox/PL013.zip](http://www.geocities.com/shindarkfox/PL013.zip)

Edit2: Ah, it seems Capcom does indeed use this for BOF3 as well, and perhaps if I remember correctly, the Megaman games as well.

Edit3: These are from the PLAYER folder of the main CD, they should be the character graphics or portraits.. or both.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-17T21:50:39+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

Actually, this is stuff you should post in the Graphics forum.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-07-18T21:22:51+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

I feel however that EMI is a form of archive. As it is also used for Background Music and map data. As seen in these below. Though I will post this in the graphics forum regardless.
[BGM.zip](https://xentaxbackup.github.io/file/775_BGM.zip)
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-19T06:57:22+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

Okido!
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-07-26T20:46:52+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

Any news on the EMI format anyone?
I have looked at it myself, well the CHARACTERS at least, I can find NOTHING whatsoever that can help, not even the name of the character, the game MUST store the character NAMES as numbers and only SHOW the strings during play.
Unlike games such as Final Fantasy which RECORED ALL THE INFO files with the Default character names ie: Cloud, ect...
THo i think SOME of these were done as Digets aswell
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-26T13:20:52+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

The BGM files seems to contain VAG Audio data.
(the header looks totally different, but the data itself is structured just
like a Sony Vag Audio file.)

im gonna make a test and recreate a VAG header for a file
and see if a VAG player will accept it. *bbl* :X
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-26T13:25:53+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

IT WORKED! =D=DDD

I r teh roxx lol.
[vagemi2raw.zip](https://xentaxbackup.github.io/file/826_vagemi2raw.zip)
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-26T14:08:33+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

> Reply from Strobe
>
> IT WORKED! =D=DDD

I r teh roxx lol.
OMG wow thankyou.
The character files and everytihng is saved in the SAME way.
Think maybe you can take a look at thm at all?
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-26T14:09:57+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

If i get some kind of link or something where i can download them
i can do it. The VAG stuff was easy, but i cannot guarantee the rest of 
their datafiles is just as easy :X , but ofcourse i can try!
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-26T14:11:52+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

Original VAG:

```

```


The  .EMI

```
 ..Ã Â¿           ...........................
```
 and a lot's of ....

```
..pBAV        ÃŒ  Ã®Ã® 	  s@
```


You see the differenceÂ¿?

Original:
VAGp

EMI:
pBAV
## Post #11
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-26T14:15:19+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

thats also what i first thought....but the pBAV sign is located on a
totally different place than the VAGp in real VAG headers, so
im not sure that is SO easy to just modify that =o .....

but creating a VAG header isnt much of a task. it just contains a signature
, a frequency header, and length header. ....
## Post #12
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-26T14:25:46+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

Well i modified the code, replacing the "VAGp" for "pBAV", now the coder creates a file with the Fourcc "pBAV", anywayh examining  the files .emi (downloaded from the example) only i found two "pBAV" one at the first and other after the "...", if you encode the .emi only can get 1 sample, and example have more than one...
## Post #13
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-26T14:39:23+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

> Reply from Strobe
>
> If i get some kind of link or something where i can download them
i can do it. The VAG stuff was easy, but i cannot guarantee the rest of 
their datafiles is just as easy :X , but ofcourse i can try!
Here you are a Player file.
I own the game so i should be easiy enough for me to GIVE you ANY and EVERY file that you may need ot get this running.
The same format is used for PS2 Breath Of Fire Dragon Quater aswell, im wondering if that means "If a tool works on numer 4 maybe itl wokr on number 5" tho thats just a dream lol.

Any chance of you MSN strobe?
That way it will be EASIER not to mention FASTER for me to send you the files you need, that way I can work on these files with you so that whe you become swamped with other things I will have LEARNED enough to do it myself (I HOPE)
[PL013.zip](https://xentaxbackup.github.io/file/828_PL013.zip)
## Post #14
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-26T15:04:46+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

I downloaded the .wav created and tried to encode with the encoder of vag, but...
"no data chunk"

I compressed the .wav with lame and unpacked again and uoops encoded succedeed, i know it's a silly solution but works
[vagemi2raw.zip](https://xentaxbackup.github.io/file/829_vagemi2raw.zip)
## Post #15
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-26T15:08:48+00:00
- Post Title: Capcom .EMI file format (from Breath Of Fire 4)

> Reply from pulposo
>
> I downloaded the .wav created and tried to encode with the encoder of vag, but...
"no data chunk"

I compressed the .wav with lame and unpacked again and uoops encoded succedeed, i know it's a silly solution but works
Does it sound the same as before.
As I unerstand the reason behind converting at to a USEABLE format, but the only reason for Converting it back would be if we wanted to INJECT IT BACK inot the ARCHIEVE, which unfortunatly isnt actually possible as the game is for PSX and unless we own an EMU (yes they are LEGAL) an repack an ISO ot play it from there is no need to repack it again.
But i may just be reading this all the wrong way, Il take the file and see what it is.
Thankyou for your work so far tho.

The OST tot his game is easily accessible so its only really the 3D/2D data that I would like to extract.
## Post #16
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-26T15:53:12+00:00
- Post Title: ......

im writing an Universal VAG detector. that should be able to detect any possible VAG files , even without headers, and it will recreate a VAG header if
data is found. however this is a very early test stage of this.
ill get back when its more finished. seems to work currently on the EMI files
atleast. *hmmms*
## Post #17
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-26T16:08:43+00:00
- Post Title: ......

> Reply from Strobe
>
> im writing an Universal VAG detector. that should be able to detect any possible VAG files , even without headers, and it will recreate a VAG header if
data is found. however this is a very early test stage of this.
ill get back when its more finished. seems to work currently on the EMI files
atleast. *hmmms*
Cool thanks man.
Tho I personally have little interest in the games SOUND, some people may do.
It seems asthough 2 tools will be needed, 1 for 3D/Image data and another For Sound/Music Data.
I wonder......
Strobe are you more of a Music perosn or a Graphics person?
I have seen a good few Music/Sound related posts of yours.
## Post #18
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-26T16:18:50+00:00
- Post Title: ......

Im very much more of a sound person 
 maybe because im a composer. This VAG stuff is something i thought
of doing since a long time ago, basically because there are so many different VAG formats out there, so now im tired of adding different rippers for them,
now it should instead dont give a damn if there is a header, and instead
detect the data and recreate the header on its own =D

I havent even looked at the graphics yet! HHhaHAhAhaha  (or models)

EDIT: My detector is working so far!   (tested on only 4 files yet though)
the only fault in the header so far im creating is the correct length of the VAG
data. but the vag player dont seem to care, it still plays the ripped vag data.
## Post #19
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-26T17:40:41+00:00
- Post Title: ......

> Reply from Strobe
>
> 
I havent even looked at the graphics yet! HHhaHAhAhaha  (or models)
Well there not really MODELS as such, its a 2D type game, so It looks to me asthough the BATTLE models might just be 2D models.
see this example (just in case you havent played the game

Not ot mention THIS 
which for ONCE i havent put as my avatar, its my avatar in like 9999999 other forums (exageration btw), i think il make it mine here too.
## Post #20
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-26T18:02:45+00:00
- Post Title: ......

beta VAG detector and converter done!

[http://jaedernaub.ath.cx/](http://jaedernaub.ath.cx/)

download v1.9.0n to try it out. should work on EMI files aswell,
(have yet only tested it on 3 emi files, the ones ive found on this forum :X)

there is an "UVAG v1.0" button on the main screen, just next to "Hex View" button. simply select the file with Load window, and press "UVAG v1.0",
and it should work.....hopefully....

Maybe time to move on to the graphics :X

im using Awave Audio to replay VAG files, what are you guys using?
is there a plugin for WinAmp or something?
## Post #21
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-26T18:26:03+00:00
- Post Title: ......

> Reply from Strobe
>
> beta VAG detector and converter done!

http://jaedernaub.ath.cx/

download v1.9.0n to try it out. should work on EMI files aswell,
(have yet only tested it on 3 emi files, the ones ive found on this forum :X)

there is an "UVAG v1.0" button on the main screen, just next to "Hex View" button. simply select the file with Load window, and press "UVAG v1.0",
and it should work.....hopefully....

Maybe time to move on to the graphics :X

im using Awave Audio to replay VAG files, what are you guys using?
is there a plugin for WinAmp or something?
Us guys?
Eh?
Erm....
O no longer have WINAMP as i dont really like it, I jsut use Media Player or CLASSIC or even VLC to play most things.
Yeah move on to Graphics if you can.
Id liek that.
Tell me your MSN or something like that and il send you as many files as i can.
Damn all this work tryingt o figure out the EMI fiels and im fogetting all about the MGS3 .DAT files.
Damn am i ever even gonna get ANYTHING from them...
Oh well keep trying i say.
## Post #22
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-08-27T00:05:52+00:00
- Post Title: ......

Patience is a virtue lionheartuk . Much thanks on what you've done so far Strobe! Looking forward to what else you find. I don't think I ever said welcome back...  well welcome back Strobe!

Also if you need anything more for this just say so.
## Post #23
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-22T17:15:54+00:00
- Post Title: ......

Any progress on this request?
## Post #24
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-22T18:52:33+00:00
- Post Title: ......

> Reply from LustD
>
> Any progress on this request?
I looked into it as did Strobe but the GFX are compressed with some unknown format.
We currently are nto sure how to Unzip then/Uncompress
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-22T20:27:44+00:00
- Post Title: ......

These EMI files  contain sections padded to multiples of 0x800 bytes.

For instance, the BGM053 file has three section in the beginning of 0x800, 0x1000 and 0x800 in size. They are padded either with 0x2E or 0x5F. The other sections in there are also padded. It would be reasonable to assume that one can read the contents (all of it) of those files by loading chunks of data of 0x800 in size, check if the last bytes of the chunks are either repetitions of 0x2E or 0x5F, and if so, save them as separate files. 

I'm also looking at the first sections, as they may actually be tables referring to contents of EMI files.
## Post #26
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-22T21:02:01+00:00
- Post Title: ......

Update:

The first section, padded to 0x800 is indeed the file contents table. (MATH_TBL). It consists of entries of 16 bytes in length, terminated by 0x2E2E. 

A preliminary format of the table is: 

```
// Header

uint32   Number of files/Data section
uint32   Unknown, in my files always 0x1
char(8) String, Identifier of the table: "MATH_TBL"

// For each entry in the table

uint32   Size of the file/section
uint32   Unknown number (often 0x4)
uint32   Could also be a 4 byte string, identifying the type of file (pBAV, or pQES etc )
uint16   Unknown number
uint16   End-of-entry marker (0x2E2E)

Take into account that each section is padded to multiples of 0x800, so if make sure you start reading the next section from a position that marks the next 0x800 block from the actual data end of the section.

```
## Post #27
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-22T22:44:10+00:00
- Post Title: ......

> Reply from Mr.Mouse
>
> Update:

The first section, padded to 0x800 is indeed the file contents table. (MATH_TBL). It consists of entries of 16 bytes in length, terminated by 0x2E2E. 

A preliminary format of the table is: 
Code: Select all
// Header

uint32   Number of files/Data section
uint32   Unknown, in my files always 0x1
char(8) String, Identifier of the table: "MATH_TBL"

// For each entry in the table

uint32   Size of the file/section
uint32   Unknown number (often 0x4)
uint32   Could also be a 4 byte string, identifying the type of file (pBAV, or pQES etc )
uint16   Unknown number
uint16   End-of-entry marker (0x2E2E)

Take into account that each section is padded to multiples of 0x800, so if make sure you start reading the next section from a position that marks the next 0x800 block from the actual data end of the section.
Hmm interesting dude.
Maybe Il speak to strobe abotu adding this to his Ripper.
Then again What can we even find there?
Curently were looking for a way to get the IMAGE data out
## Post #28
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-22T23:13:22+00:00
- Post Title: ......

What can you find here??? You can extract ALL CONTENT of those files ! Thus including IMAGE data, AND, possibly import them back, altered!
## Post #29
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-22T23:36:55+00:00
- Post Title: ......

> Reply from Mr.Mouse
>
> What can you find here??? You can extract ALL CONTENT of those files ! Thus including IMAGE data, AND, possibly import them back, altered!
That sounds pretty cool actually dude.
Sorry i was a bit busy at the time and never got round to reading ur post propperly, just a SKIM was all.
But yes as i was saying, When me and Strobe looked at the files, He did find IMAGE data, But it appeared to be Compressed by soem Unknow compressor he said.
Btw what does "uint" mean cos u ahve many uint32 ect...
## Post #30
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-23T00:19:53+00:00
- Post Title: ......

Seem this request have nice progress
## Post #31
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-23T05:15:40+00:00
- Post Title: 

It does sound promising  thanks again guys
## Post #32
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-23T08:18:42+00:00
- Post Title: 

> Reply from lionheartuk
>
> 
Btw what does "uint" mean cos u ahve many uint32 ect...

uint32 = unsigned 32-bit integer (4 bytes)
uint16 = unsigend 16-bit integer (2 bytes).
## Post #33
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-23T08:27:57+00:00
- Post Title: 

> Reply from LustD
>
> Seem this request have nice progress
lol.
Actually it was dead for  awhile Until you posted an revived it, but since then some Progress has been made on this game.
Nicely too.
Still Im not sure if we will be able tp uncompress them compressed textures or not,
## Post #34
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-23T08:39:16+00:00
- Post Title: 

Lol, you make me like necromancer.

So the main problem is how to uncompresed it?
Well Capcom have good job with this
## Post #35
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-23T08:58:01+00:00
- Post Title: 

> Reply from LustD
>
> Lol, you make me like necromancer.

So the main problem is how to uncompresed it?
Well Capcom have good job with this
Yes thats IF there compresse as strobe ses.
Im not actually sure.
The info that MrMouse Posted wasnt in Visual Basic.
Seing as im relativly new to this whole ripping thing so far I can only do more common formats.
Funnyly enough though, Mr Mouses info can be posted to VB, But seign as im actually rather new to this I dont know Quite how atm.
Tho Uint function can be made rather simply.
## Post #36
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-23T09:10:40+00:00
- Post Title: 

No no, what I posted it just the format of the header able of LIB files. An unsigned 32-int is just that. A format of a number. It's not difficult to write an extractor based on what I posted. I might even write a Multiex script for it.
## Post #37
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-23T09:37:06+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> No no, what I posted it just the format of the header able of LIB files. An unsigned 32-int is just that. A format of a number. It's not difficult to write an extractor based on what I posted. I might even write a Multiex script for it.
lol.
Cool.
THo i dont own Multi Ex so thats no use to me personally.
But doesnt mean many others wont use it eh.
LIB files? But arnt the games file .EMI.
## Post #38
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-23T09:57:51+00:00
- Post Title: 

Well if Mr.Mouse can make the extractor, maybe he can post the script i here. so someone can messing around with it.
## Post #39
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-23T10:37:32+00:00
- Post Title: 

> Reply from lionheartuk
>
> 
LIB files? But arnt the games file .EMI.

Er.. yeah, EMI files.
## Post #40
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-23T12:44:39+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> lionheartuk wrote:
LIB files? But arnt the games file .EMI.

Er.. yeah, EMI files.
lol.
Im still a bit confused as to what i would write into my ripper atm.
But  have sent oyu that PM which should explain what i mean.
## Post #41
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-26T20:27:28+00:00
- Post Title: 

Version 4.3 of MultiEx Commander will be released come sunday. 

That can open EMI files and extract all content using this script:

```
# By Mr.Mouse
# ----------------------------
# First get the Number of files (FN)
ImpType SFileSize ;
Get FN Long 0 ;
Get U1 Long 0 ;
GetDString ID 8 0 ;
# The ID string is "MATH_LAB"
# Very well, now prepare some padding calculations
# Each data stream (data section) is padded up to 
# 0x800 blocks. 
Set B Long 2048 ;
Set A Long FN ;
Math A *= 16 ;
Math A += 16 ;
Set C Long A ;
Math C /= B ;
Math C *= 2048 ;
Math C += 2048 ;
Set Off Long C ;
# Good, now we have calculated the Offset of the 
# first file. Let's start reading the file info for each file 
# in the archive!
For T = 1 To FN ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get U2 Long 0 ;
Get ID2 Long 0 ;
Get U3 Int 0 ;
Get END Int 0 ;
Log "" Off FS 0 FSO ;
# Need to perform padding calculations to get to the 
# offset of the next file (if any)
Math FS /= 2048 ;
Math FS *= 2048 ;
Math FS += 2048 ;
Math Off += FS ;
Next T ;
# There! That did the trick! 

```


So, hold your breath
## Post #42
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-27T03:32:16+00:00
- Post Title: 

Thanks alot Mr.Mouse, I'll wait till then!
## Post #43
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-27T11:41:01+00:00
- Post Title: 

Wow that great news, i cant wait for this.
## Post #44
- Username: Ray Phoenix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 19, 2007 3:09 am
- Post datetime: 2007-11-20T00:35:22+00:00
- Post Title: 

Sorry if i asking, but has it worked?
## Post #45
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-11-20T10:52:00+00:00
- Post Title: 

Has what worked?
## Post #46
- Username: Ray Phoenix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 19, 2007 3:09 am
- Post datetime: 2007-11-20T12:24:27+00:00
- Post Title: 

Well, Darkfox has asked for help for the .EMI file on the Breath Of Fire IV disk. But i want to know if he has extrated the sprite sheets on the cd.
Stupid Question, i know...
## Post #47
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-11-20T12:33:40+00:00
- Post Title: 

> Reply from Ray Phoenix
>
> Well, Darkfox has asked for help for the .EMI file on the Breath Of Fire IV disk. But i want to know if he has extrated the sprite sheets on the cd.
Stupid Question, i know...

Okay, well I hope the MultiEx Commander script works for you.
## Post #48
- Username: Ray Phoenix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 19, 2007 3:09 am
- Post datetime: 2007-11-20T12:38:53+00:00
- Post Title: 

okay, Now i got a registrated Version. but i'm really a noob in making rips and making scripts. Well i dont know how to install those. Sry...

EDIT: Okay, it works now, but the prob is, all i get there are files. How can i now change them to picture files?
## Post #49
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-11-20T14:02:55+00:00
- Post Title: 

I don't know really. I've just created the script.  Perhaps you could attach a few of these files that you suspect are pictures in the Graphic Formats forum, so people can look at it.
## Post #50
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-07-27T05:52:36+00:00
- Post Title: 

Anyone can rewrite MrMouse MultiEx script to quickbms-support bms script, which will support .EMI format from all files in Bof3 and 4? 

I try use MrMouse MultiEx script with MultiEx 4.3.0, but this version bad working on Win7 - Installer doesn't run(temporaly directory couldn't set), cannot find zlib.dll(he try find in system32?), one of .OCX files from distributive cannot be find, if it dont registered in the system.
