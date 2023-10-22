## Post #1
- Username: stipo360
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 06, 2014 9:00 am
- Post datetime: 2016-10-02T00:42:37+00:00
- Post Title: Header Renamer? (quickbms)

.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-10-02T13:46:06+00:00
- Post Title: Header Renamer? (quickbms)

What game? what platform?

Also, Quickbms can do this, but it might take a few lines. Probably better to do it in C/C++ (would take very few lines of code).

Cheers.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-02T17:13:03+00:00
- Post Title: Header Renamer? (quickbms)

> Reply from stipo360
>
> So i'm trying to cook up a quickbms / or (some other type of script) that could take my textures header ".XETU" and spit out the file 100% unmodified except i need the header replaced with ".XETV"
i'm working on a simple bms script but i need to see a sample to know exactly what the header is in binary  
i got the XETU to XETV working, i just need to know what that dot is

the double zero is a place holder until i can see a sample

```
get NAME filename
set MEMORY_FILE binary "\x00\x58\x45\x54\x56" #".XETV"
log NAME 0 0x5 MEMORY_FILE
append
get SIZE asize
math OFFSET = 0x5
math SIZE - OFFSET
log NAME OFFSET SIZE
```
## Post #4
- Username: stipo360
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 06, 2014 9:00 am
- Post datetime: 2016-10-02T18:41:24+00:00
- Post Title: Header Renamer? (quickbms)

.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-02T20:48:28+00:00
- Post Title: Header Renamer? (quickbms)

> Reply from stipo360
>
> ...the reason it needs to be set to "V" is because noesis and other texture viewers are only setup to read ".XETV"
if you have a Noesis script to open these textures i could just modify the type checking in it to accept them, so no need for bms script here   


> I replaced idstring "\x00XETU" with get NAME basename because i have multiple texture headers i need spat out in .XETV,
i don't understand, idstring is just a type check so you don't mistakenly modify the wrong files and basename doesn't grab the extension
## Post #6
- Username: stipo360
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 06, 2014 9:00 am
- Post datetime: 2016-10-03T04:02:19+00:00
- Post Title: Header Renamer? (quickbms)

.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-03T16:22:16+00:00
- Post Title: Header Renamer? (quickbms)

try this, didn't have any of your samples to test it on  

```
get VERSION byte
if VERSION == 0x55                               #".XETU"
	get NAME filename
	set MEMORY_FILE binary "\x00\x58\x45\x54\x56" #".XETV"
	log NAME 0 0x5 MEMORY_FILE
	append
	get SIZE asize
	math OFFSET = 0x5
	math SIZE - OFFSET
	log NAME OFFSET SIZE
elif VERSION == 0x48                             #".XETH"
	get NAME filename
	set MEMORY_FILE binary "\x00\x58\x45\x54\x56" #".XETV"
	log NAME 0 0x5 MEMORY_FILE
	append
	get SIZE asize
	math OFFSET = 0x5
	math SIZE - OFFSET
	log NAME OFFSET SIZE
elif VERSION == 0x40                             #".XET@"
	get NAME filename
	set MEMORY_FILE binary "\x00\x58\x45\x54\x56" #".XETV"
	log NAME 0 0x5 MEMORY_FILE
	append
	get SIZE asize
	math OFFSET = 0x5
	math SIZE - OFFSET
	log NAME OFFSET SIZE
else
	get NAME filename
	print "%NAME% is version:%VERSION% which is not supported yet!"
endif
```


it'd be alot easier if you could just link to the Noesis script you mentioned earlier,
then i could just modify the type checking to support however many versions you have. 

edit
never mind, it looks like that plugin is compiled into noesis.dll and there is no source  
if you upload some unaltered texture samples i will make a python script that can be extended.
