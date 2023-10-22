## Post #1
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-08-15T02:46:44+00:00
- Post Title: Rayman Legends .IPK

Using aluigi's "Rayman Origins" script gives me the following error:



Also maybe this can be of some use.



Message me if you want the example IPK file.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-15T06:46:54+00:00
- Post Title: Rayman Legends .IPK

type quickbms -v rayman_origins.bms fullLogic_X360.ipk test
then show the console output again.
## Post #3
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-08-15T07:36:39+00:00
- Post Title: Rayman Legends .IPK

> Reply from shakotay2
>
> type quickbms -v rayman_origins.bms fullLogic_X360.ipk test
then show the console output again.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-15T08:43:49+00:00
- Post Title: Rayman Legends .IPK

well, the start of the output is the important thingie.

okay, the bold numbers is what the script should get from the ipk:
goto 0xc
get BASE_OFF long  0x4A0AE
goto 0x2c
get FILES long   0x91F 2335 files?
goto 0x30
for i = 0 < FILES
    get DUMMY1 long     1
    get SIZE long      0x63 uncompressed size (just guessing)
    get ZSIZE long    0x43 compressed size
    get TSTAMP longlong 0x01CE...
    get DUMMY3 long   0
    get OFFSET long   0
    get NAMESZ long  0x3F
 erase this line   math NAMESZ *= 2
    getdstring NAME NAMESZ
and this one    set NAME unicode NAME

I'm wondering whether it's really 2335 files in this archive but the filenames are ASCII not unicode.
So you should erase the mentioned lines in the script and give it a second try.
If it doesn't work, well, then I can't help, I guess.
## Post #5
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-08-15T09:48:29+00:00
- Post Title: Rayman Legends .IPK

> Reply from shakotay2
>
> well, the start of the output is the important thingie.

okay, the bold numbers is what the script should get from the ipk:
goto 0xc
get BASE_OFF long  0x4A0AE
goto 0x2c
get FILES long   0x91F 2335 files?
goto 0x30
for i = 0 < FILES
    get DUMMY1 long     1
    get SIZE long      0x63 uncompressed size (just guessing)
    get ZSIZE long    0x43 compressed size
    get TSTAMP longlong 0x01CE...
    get DUMMY3 long   0
    get OFFSET long   0
    get NAMESZ long  0x3F
 erase this line   math NAMESZ *= 2
    getdstring NAME NAMESZ
and this one    set NAME unicode NAME

I'm wondering whether it's really 2335 files in this archive but the filenames are ASCII not unicode.
So you should erase the mentioned lines in the script and give it a second try.
If it doesn't work, well, then I can't help, I guess.

The filenames are ASCII this one particularly from the PC version but its the same on 360 so I guess that's a start.



Can I send the .ipk file your way shakotay2?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-15T10:41:11+00:00
- Post Title: Rayman Legends .IPK

My flat rate has expired atm, so only if the file is less than let's say 10 MB (0xA00000, 5 zeroes only!).
If not cut it using a hexeditor then zip and send the first part.
## Post #7
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-08-15T12:39:56+00:00
- Post Title: Rayman Legends .IPK

Hey !!!!!,

I'm Bar. Here's the adaptation of aluigi's Rayman Origins script I wrote yesterday so it works with Rayman Legends:

```
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0xc
get BASE_OFF long
goto 0x2c
get FILES long
for i = 0 < FILES
    get DUMMY1 long
    get SIZE long
    get ZSIZE long
    get TSTAMP longlong
    get OFFSET longlong
    if DUMMY1 == 2
        get DUMMY4 long
        get DUMMY5 long
    endif
    get FOLDERSZ long
	getdstring FOLDER FOLDERSZ
	get NAMESZ long
	getdstring NAME NAMESZ
	string FOLDER + NAME
	string NAME = FOLDER
    math OFFSET += BASE_OFF
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
	get DUMMY6 long
	get DUMMY7 long
next i
```

This works perfectly on Xbox 360 and PC. I haven't tested with the PS3 version yet.
The only things Rayman Legends added were DUMMY5 and DUMMY6, along with ASCII names instead of Unicode and separate folder and filenames. 

EDIT -> Fixed it so it works with >4GB archives now, like the PC bundle.
## Post #8
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2013-09-13T20:19:35+00:00
- Post Title: Rayman Legends .IPK

Hm...very cool! I managed to unpack the entirety of the PC Bundle file, but unfortunately as with Rayman Origins the blasted image files are corrupt, and the Origins converter doesn't seem to work with them.
## Post #9
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-10-03T16:45:13+00:00
- Post Title: Rayman Legends .IPK

> Reply from Doctor Loboto
>
> Hm...very cool! I managed to unpack the entirety of the PC Bundle file, but unfortunately as with Rayman Origins the blasted image files are corrupt, and the Origins converter doesn't seem to work with them.
Oh it's quite easy to extract the images from the PC version of Legends. The CKD header is 0x34 bytes, the DDS file inside each CKD file starts immediately after it. 

```
get SIZE asize
math SIZE -= 0x34
string NAME += ".dds"
log NAME 0x34 SIZE
```
## Post #10
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-10-04T15:18:08+00:00
- Post Title: Rayman Legends .IPK

> Reply from Droolie
>
> Doctor Loboto wrote:Hm...very cool! I managed to unpack the entirety of the PC Bundle file, but unfortunately as with Rayman Origins the blasted image files are corrupt, and the Origins converter doesn't seem to work with them.
Oh it's quite easy to extract the images from the PC version of Legends. The CKD header is 0x34 bytes, the DDS file inside each CKD file starts immediately after it. 
Code: Select allget NAME basename
get SIZE asize
math SIZE -= 0x34
string NAME += ".dds"
log NAME 0x34 SIZE

Would it be possible at all for you to expand on that at all, sorry if I sound stupid here, but I'm having trouble applying your findings to the old Rayman Origins BMS script.
## Post #11
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-10-05T10:05:49+00:00
- Post Title: Rayman Legends .IPK

> Reply from lionheartuk
>
> Would it be possible at all for you to expand on that at all, sorry if I sound stupid here, but I'm having trouble applying your findings to the old Rayman Origins BMS script.
The old Origins BMS script was for the PS3 version. The script I posted in my previous post is for the PC version of Rayman Legends.
There's no need to add/change the header in the PC version, the DDS files can just be extracted from the CKD files by removing the first 0x34 bytes. 
I haven't checked but it's possible that the old Origins script works for the PS3 version of Rayman Legends too.
## Post #12
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-10-05T14:48:24+00:00
- Post Title: Rayman Legends .IPK

> Reply from Droolie
>
> lionheartuk wrote:Would it be possible at all for you to expand on that at all, sorry if I sound stupid here, but I'm having trouble applying your findings to the old Rayman Origins BMS script.
The old Origins BMS script was for the PS3 version. The script I posted in my previous post is for the PC version of Rayman Legends.
There's no need to add/change the header in the PC version, the DDS files can just be extracted from the CKD files by removing the first 0x34 bytes. 
I haven't checked but it's possible that the old Origins script works for the PS3 version of Rayman Legends too.

Thankyou, I now feel like an idiot, I'd understood it to be a segment of code but not actually a working script... sorry.

Thankyou again.
