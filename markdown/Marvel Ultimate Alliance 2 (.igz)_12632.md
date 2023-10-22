## Post #1
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-02-22T07:30:21+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

Hello guys!
So, after i used quickbms and script that Developer of this wonderful program kindly provided to me, i stuck with a new problem - igz archieves that i cannot open. I opened them with nex editor and saw that they contain .tga textures and models.
So can someone help me in opening those files? I mainly need textures. Looking in files with hex editor i saw this:


Header:


Filesize about 191.kb
Is it possible to extract textures out of it somehow?
[Here](https://mega.nz/#!9dJXGQzS!Vxs4UyEB1G8zS-1vJtG9xdTBVNrGjfD1KX1KA4UoXKA) are sample files.

Thanks in advance.
## Post #2
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-03-14T09:06:23+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

anyone?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-14T12:36:52+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

Since TextureFinder doesn't reveal anything you could try to use a "comtype_scan" (Quickbms).
It will check the inputfile with 500 different decompression algos, iirc.
Then you'll need to check the outputted files (<= 500), a tedious task.

(But you can ignore all output files with a lower size than the inputfile.
 Press ctrl-c when an algo doesn't finish, then 'n' for "no".)

tga files normally have a "TRUEVISION-XFILE" string at files end.

So if you want to ease your task search for it in the decompressed files automatically
using some capable hex editor.
## Post #4
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-03-14T16:35:21+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

> Reply from shakotay2
>
> Since TextureFinder doesn't reveal anything you could try to use a "comtype_scan" (Quickbms).
It will check the inputfile with 500 different decompression algos, iirc.
Then you'll need to check the outputted files (<= 500), a tedious task.

(But you can ignore all output files with a lower size than the inputfile.
 Press ctrl-c when an algo doesn't finish, then 'n' for "no".)

tga files normally have a "TRUEVISION-XFILE" string at files end.

So if you want to ease your task search for it in the decompressed files automatically
using some capable hex editor.

Could you please describe how to use comtype_scan if it's not difficult for you? I don't get it
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-14T19:24:16+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

create a bat or cmd file with this line contained:
call comtype_scan2 D:\test\comtype_scan2.bms D:\test\test.bin D:\test [10000000]

where D:\test is the folder which contains quickbms.exe, comtype_scan.bat, comtype_scan2.bms
and test.bin, the file to be decompressed
## Post #6
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-03-14T21:14:30+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

> Reply from shakotay2
>
> create a bat or cmd file with this line contained:
call comtype_scan2 D:\test\comtype_scan2.bms D:\test\test.bin D:\test [10000000]

where D:\test is the folder which contains quickbms.exe, comtype_scan.bat, comtype_scan2.bms
and test.bin, the file to be decompressed

Made everything as said below and got bunch of .dmp files. 2 of them about 5megs in size, opened them in hex editor but don't find "truevision xfile" Gonna check other files tomorrow.
## Post #7
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-03-15T06:17:46+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

> Reply from pechenko121
>
> shakotay2 wrote:create a bat or cmd file with this line contained:
call comtype_scan2 D:\test\comtype_scan2.bms D:\test\test.bin D:\test [10000000]

where D:\test is the folder which contains quickbms.exe, comtype_scan.bat, comtype_scan2.bms
and test.bin, the file to be decompressed

Made everything as said below and got bunch of .dmp files. 2 of them about 5megs in size, opened them in hex editor but don't find "truevision xfile" Gonna check other files tomorrow.

don't give me any results  Maybe i made something wrong...
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-15T08:52:56+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

maybe - but keep in mind that an unknown compression or encryption method might be used.

Only method to reveal this for sure is to debug the game.

(For pc games ollydbg is a good debugger but seems this game was published for consoles only.)
## Post #9
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-03-15T09:04:52+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

> Reply from shakotay2
>
> maybe - but keep in mind that an unknown compression or encryption method might be used.

Only method to reveal this for sure is to debug the game.

(For pc games ollydbg is a good debugger but seems this game was published for consoles only.)

yeah, this game only for some consoles
## Post #10
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-04-02T05:03:00+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

No one can help me?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-02T07:13:42+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

accidentally I gave it another try -really don't know WHY I didn't use offzip:
offzip -a -z -15 deadpool_alt_1_n.igz D:\xxx 0
(which seems to split up the file a little bit too much but anyhow):



00151346_dat.JPG (83.12 KiB) Viewed 359 times
## Post #12
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-04-02T11:30:01+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

> Reply from shakotay2
>
> accidentally I gave it another try -really don't know WHY I didn't use offzip:
offzip -a -z -15 deadpool_alt_1_n.igz D:\xxx 0
(which seems to split up the file a little bit too much but anyhow):
00151346_dat.JPG

you got model from that file?
(sorry for my noob-ism i'm really interested in getting models from that game)

also i got bunch of errors while trying to use offzip.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-02T13:09:12+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

nope - just point clouds

offzip: ignore the errors, just use the decompressed files if any
## Post #14
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-04-02T13:28:52+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

even with offzip i didn't get anything 
hope someone more skilled can do this
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-15T17:27:21+00:00
- Post Title: Marvel Ultimate Alliance 2 (*.igz)

here are two of the dat files in question:
[http://www.uploadmb.com/dw.php?id=1427988377](http://www.uploadmb.com/dw.php?id=1427988377)
## Post #16
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2016-01-15T05:29:22+00:00
- Post Title: Re: Marvel Ultimate Alliance 2 (*.igz)

Bump
## Post #17
- Username: Raphael Splinterson
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 31, 2016 12:36 pm
- Post datetime: 2022-07-27T20:45:31+00:00
- Post Title: Re: Marvel Ultimate Alliance 2 (*.igz)

Hi all! Once upon a time, in one of these topics, an archive from MUA2 was published, unfortunately, I don’t remember what platform those files were from, but the IGZ format did not cause problems.
Now I wanted to extract the rest of the 3D models and publish them to the public, but I can’t open the IGZ files using the Noesis plugin. Regardless of whether they are on a PC or PS3, it is also impossible to open versions from XBox360 using QuickBMS and a script for MUA2. Unable to unpack PAK files. Maybe I'm doing something wrong, but please tell me how to extract 3d models and textures of characters from MUA2, no matter what version of the game, the main thing is to extract the main costumes and mobs. The game crashes when using Ninja Ripper. So I'm trying to think of an alternative way. Unfortunately, that topic on the forum, where everything was step by step and clear, has been deleted.
The latest versions of Noesis and QuickBMS are installed. Could it be the cause of Windows 10? Then there was Windows 7.
Please, help!
## Post #18
- Username: XFusion Shift
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 13, 2023 8:53 pm
- Post datetime: 2023-10-13T12:57:05+00:00
- Post Title: Re: Marvel Ultimate Alliance 2 (*.igz)

wait please tell me how you extracted models from the archived files, idk how to extract igz files or wtv the models are in, im trying to get the war machine model from MUA2 but i’m having difficulty
## Post #19
- Username: XFusion Shift
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 13, 2023 8:53 pm
- Post datetime: 2023-10-13T13:06:21+00:00
- Post Title: Re: Marvel Ultimate Alliance 2 (*.igz)

Or the PKGB files
