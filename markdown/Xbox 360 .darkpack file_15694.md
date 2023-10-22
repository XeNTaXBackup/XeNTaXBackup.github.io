## Post #1
- Username: RicoKwothe
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 03, 2014 9:47 pm
- Post datetime: 2017-01-07T09:41:57+00:00
- Post Title: Xbox 360 .darkpack file

Hi!

Can somebody help me to write a QuickBMS script for the LocText_en.darkpack files of the Xbox 360 Dark? Example: [https://drive.google.com/file/d/0Bwt7wT ... hnNGM/view](https://drive.google.com/file/d/0Bwt7wT8aE6PIT3dpeFUySThnNGM/view)
The pc script not working.
Thanks for your help!
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-07T10:34:37+00:00
- Post Title: Xbox 360 .darkpack file

i guess it was just a matter of endianess   
added "endian big" before the "idstring" line in the script here and it seems to work
[viewtopic.php?f=13&p=87773#p87773](http://forum.xentax.com/viewtopic.php?f=13&p=87773#p87773)

```
# (c) 2013-09-02 by AlphaTwentyThree of XeNTaX
# script for QuickBMS http://quickbms.aluigi.org

endian big
idstring "DARKPACK"
goto 8
get TOC_SIZE long
get FILES long
for i = 1 <= FILES
   get OFFSET long
   get ZERO long
   get CRC long
   get ZERO long
   get SIZE long
   get NAMEL long
   getDstring NAME NAMEL
   log NAME OFFSET SIZE
next i
```
## Post #3
- Username: RicoKwothe
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 03, 2014 9:47 pm
- Post datetime: 2017-01-07T11:11:17+00:00
- Post Title: Xbox 360 .darkpack file

> Reply from AceWell
>
> i guess it was just a matter of endianess   
added "endian big" before the "idstring" line in the script here and it seems to work
viewtopic.php?f=13&p=87773#p87773
Code: Select all# extracts the *.darkpack archives from "DARK" (X360, 2013)
# (c) 2013-09-02 by AlphaTwentyThree of XeNTaX
# script for QuickBMS http://quickbms.aluigi.org

endian big
idstring "DARKPACK"
goto 8
get TOC_SIZE long
get FILES long
for i = 1 <= FILES
   get OFFSET long
   get ZERO long
   get CRC long
   get ZERO long
   get SIZE long
   get NAMEL long
   getDstring NAME NAMEL
   log NAME OFFSET SIZE
next i

Thx man, it's work!!
