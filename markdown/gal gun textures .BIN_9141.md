## Post #1
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-06-23T18:48:39+00:00
- Post Title: gal gun textures .BIN

I have successfully ripped models from Gal Gun but I want to extract or convert the texture files, which are .BIN. I have looked everywhere, and have asked all around, but no one, NO ONE will help me... I do not know if I am over thinking the simplicity of this process but it doesnt seem to be appearing anywhere. here is a .bin file for one of the characters Akira...
[AKira_body_dif.rar](https://xentaxbackup.github.io/file/5511_AKira_body_dif.rar)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-23T20:05:45+00:00
- Post Title: gal gun textures .BIN

This needs Xbdecompress.exe from the Xbox SDK. It works fine now at decompressing they look like standard .dds files?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-23T20:09:25+00:00
- Post Title: gal gun textures .BIN

the sdk works fine for me then just paste a dds header on the file and your all set.
## Post #4
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-23T20:30:45+00:00
- Post Title: gal gun textures .BIN

I edited some .dds header adder script here for quickbms. It seems that they come out a funny colour though, someone else should fix it but here it is anyway:

```
get UNK1 long
get UNK2 long
reverselong UNK2
get UNK3 long
reverselong UNK3
get UNK4 long
get UNK5 long
set MEMORY_FILE2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE2 0xC UNK3 long
putVarChr MEMORY_FILE2 0x10 UNK2 long
append
get SIZE asize MEMORY_FILE2
log MEMORY_FILE 0 SIZE MEMORY_FILE2
get SIZE asize     
math SIZE -= 0x24             
log MEMORY_FILE 0x24 SIZE             
append
get SIZE asize MEMORY_FILE
string NAME += ".dds"
log NAME 0 SIZE MEMORY_FILE

```
## Post #5
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-06-24T03:29:43+00:00
- Post Title: gal gun textures .BIN

alright im testing it out now
## Post #6
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-06-24T03:42:35+00:00
- Post Title: gal gun textures .BIN

okay so i extracted the .dds file from the bms script but texture didnt event show up. forgive the noob question, what did I miss?
## Post #7
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-24T16:18:16+00:00
- Post Title: gal gun textures .BIN

> Reply from askB
>
> okay so i extracted the .dds file from the bms script but texture didnt event show up. forgive the noob question, what did I miss?

That only converts the texture. You have to decompress it using Xbdecomrpess.exe from the Xbox 360 SDK. You can find it in the usual places since it's illegal to distribute SDK tools.
## Post #8
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-06-24T22:58:38+00:00
- Post Title: gal gun textures .BIN

really thats it? Let us see....
## Post #9
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-06-25T09:46:27+00:00
- Post Title: gal gun textures .BIN

okay all the dds files were extracted successfully....Although, like COOL12345 stated, the colors are funny. They look really bad lol. Ill look into solving the problem myself but, could someone please explain this?



TEXTURE!!!


[DDS Files!.rar](https://xentaxbackup.github.io/file/5515_DDS Files!.rar)
## Post #10
- Username: askB
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-25T10:29:30+00:00
- Post Title: gal gun textures .BIN

they are just big endian dds files.
you must swap every 2 bytes of the entire file starting at 0x80
so if the original bytes were
12 34 56 78
it would become
34 12 78 56
most hex editors can do this for you no problem.
## Post #11
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-06-25T11:34:00+00:00
- Post Title: gal gun textures .BIN

Great! Thanks for the tip. Im still pretty new at hex editing, I have HxD and im guessing that the swapping of the 0x80 bytes are found under the search/replace tab???




EDIT!!!!: Okay, so I use HxD (as explained above) and i went to search then clicked on replace. 

I searched for the first 8 bytes in 0x80 (because im not sure howto replace just two.) which were 84 F4 7C 54 i had them replaced to look like this:

"F4 84 54 7C"

When I tried to view the image nothing came up at all. Im sure its a small issue that im not seeing but I cant seem to figure it out...

Here are some pics of the hex:


1 Before Swapped





2 After
## Post #12
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-25T13:22:17+00:00
- Post Title: gal gun textures .BIN

hxd does not have a byte swap function try 010 editor.
then use the swap unsigned short.
## Post #13
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-06-25T14:39:01+00:00
- Post Title: gal gun textures .BIN

See? what i tell ya somethin small lol. ill let u know my results


EDIT: Sigh... Sorry this isnt working how the hell do I swap bytes with 010 editor? :/
## Post #14
- Username: askB
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-25T19:56:41+00:00
- Post Title: gal gun textures .BIN

Be patient, at least you are getting help unlike me in my threads, i'm ignored all the time. I made a quickbms script to reverse the endianness, Well i know this script will have problems if the number of bytes aren't even (odd). But it should work on some of the files, here you go, thanks to Chrrox for telling us how to do this.

Here it is anyway:

```
# May not have full support
# MrNightmareTM
# Special thanks, Chrrox for the method!
# v0.1a

get SIZE asize
log MEMORY_FILE 0 SIZE

get SIZE2 asize
math SIZE2 -= 0x80
math SIZE2 /= 2
goto 0x80

for i = 0 < SIZE2
savepos CURRENTOFFSET
get UNK1 short
reverseshort UNK1
putVarChr MEMORY_FILE CURRENTOFFSET UNK1 short
next i 

get NAME basename
string NAME += "_reversed.dds"

log NAME 0 SIZE MEMORY_FILE

```
## Post #15
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-06-26T03:31:32+00:00
- Post Title: gal gun textures .BIN

Hey how come you guys banned COOL12345? He gave me a really useful .bms script!
## Post #16
- Username: askB
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-26T07:40:00+00:00
- Post Title: Re: gal gun textures .BIN

> Reply from askB
>
> Hey how come you guys banned COOL12345? He gave me a really useful .bms script!
I'm not banned, but i apparently am according to my profile. I'm not sure why it says i'm banned it's pretty funny since i'm actually not banned   

Enjoy.
## Post #17
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-06-26T11:20:20+00:00
- Post Title: Re: gal gun textures .BIN

Oh wow durr my bad lol, thanks man I will.


> I'm not banned, but i apparently am according to my profile. I'm not sure why it says i'm banned it's pretty funny since i'm actually not banned   
>
> 
>
> Enjoy.
## Post #18
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-01-14T20:25:02+00:00
- Post Title: Re: gal gun textures .BIN

I got the textures converted and fixed except the eyes. I keep trying to fix them in hex editor but I'm not having very much luck with it. Can someone help me with how to fix them in hex editor? Or either make a QuickBMS script that will fix the eye textures?
