## Post #1
- Username: ChezLinux
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 01, 2011 6:52 am
- Post datetime: 2011-02-02T22:21:31+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

I realize it's bad etiquette to make a request as your first post, but I (as well as many others who are working on this) are stumped to the point of being frustrated, so maybe the brilliant minds at XeNTaX can help.

[EyaSoft/Enpang](http://lunaplus.enpang.com/) (and all the other official servers of Luna Online/Luna Plus, including [gPotato](http://luna.gpotato.com/)) have started protecting (encrypting/compressing) their bin files within the last six months.

The original bin files since it's release were quite easy to open.
An example of the original can be found [here](http://www.mediafire.com/?k5lv1a65odec7o1) (237 B)
The contents of this binary file are simply the following lines of text. (which gives a listing of the 13 model files to use for hair choices for human male characters in the game)

```
H_M_hair000.MOD
H_M_hair001.MOD
H_M_hair002.MOD
H_M_hair003.MOD
H_M_hair004.MOD
H_M_hair005.MOD
H_M_hair006.MOD
H_M_hair007.MOD
H_M_hair008.MOD
H_M_hair009.MOD
H_M_hair010.MOD
H_M_hair011.MOD
H_M_hair012.MOD
```


The same protected file (there may or may not have been information added to this file, but following the initial number the following 13 lines of text should still be the same) can be found [here](http://www.mediafire.com/?7ez5sk5ps0466ka) (478 B)

In our research, we have been able to assess that it is using some type of Huffman algorithm, but have not been able to work it out.

If you fine folks can have a look and see what you can come up with, I (we) would be very appreciative.  Even a simple DOS-based decryptor/decompressor (with source) would be very beneficial.

Thank you in advance for your time.
-ChezLinux
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-03T01:43:16+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

what was the original format structure?
is there an old extractor?
## Post #3
- Username: ChezLinux
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 01, 2011 6:52 am
- Post datetime: 2011-02-03T02:18:34+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

Thank you for your reply.

The existing usable extractor can be found [here](http://www.mediafire.com/?t6jsybcu0tgd1ks). (254.16 KB)

The included batch file (register.bat) registers the required Rich Text and Tab Control Active X components used by the program and must be run prior to running the executable.

I do not currently have the original source for the above program.


Thanks again.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-03T04:05:44+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

The old encryption was a xor based on the position in the file starting at position 0xC and incrementing by one each position after. i am assuming they changed the xor method slightly to break your extractor.
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-03T13:30:06+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

OLD BIN FORMAT

result of playing with that program. all done with a hex editor and good old trial and error.

however, my quickbms version completely breaks.. any help with that would be awesome (anyone really)

rough text description i came up with:

```
int rval ( > 1 and < size )
int size
byte checksum1
byte data[size]
byte checksum2

checksum:
checksum1 == checksum2

value is the sum of the encrypted bytes (of length 'size')
then add rval

decryption:
for i = 0 < size
  byte temp = byte[0xC + i]

  math temp -= i

  if i % rval == 0
    math temp -= rval

  byte[0xC + i] = temp
next i

```


it wasn't the purpose of this thread, but NOW IT'S DONE.



NEW BIN FORMAT

please upload another file, or something which reads it!

the size is 16 bytes smaller than it should be, and the checksum and base hash value needs something else to compare it with (ie. another file)


[obin_brokenBMS.txt.zip](https://xentaxbackup.github.io/file/3869_obin_brokenBMS.txt.zip)
## Post #6
- Username: ChezLinux
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 01, 2011 6:52 am
- Post datetime: 2011-02-04T08:39:35+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

> Reply from WRS
>
> 
NEW BIN FORMAT

please upload another file, or something which reads it!

the size is 16 bytes smaller than it should be, and the checksum and base hash value needs something else to compare it with (ie. another file)

Thank you for your response.  I uploaded another larger bin that uses the new bin format [here](http://www.mediafire.com/?dbf90rn8v2r9gso) 3.65 KB

Edit: Also uploaded the latest client executable, which is obviously coded to read the new bin format (no support files, full client with all files is well over a GB)   It can be found [here](http://www.mediafire.com/?8u3r890xirs62r5) (1.21 MB)



Thank you again. I definitely appreciate the effort.
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-04T18:46:00+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

written up what i noted:


so the base number has changed, but its checked the same, so nothing new here

```
base hash = 01328E8A
```


the "size" value i described is now the actual file size (usize), but the new data is padded to 16-byte blocks (remaining bytes are 00s)

the client reads the blocked data (as there is no size flag) from filesize - 0xE

not sure about the checksum. it pads the data as it did before though.

the data now has a rather long (690 line) function for decryption. there isn't any compression though. each block (16-bytes) is read and passed into the decryption function.

there is a 10-byte value which is read from a string i dont understand:

```
E7 6B 24 13 95 8B 00 E1 93 A1
```


following all this in a debugger is straightforward, as is dumping any bin file you want. so a client could be modded for that purpose, but i guess you want to be able to mod it, so that won't really be useful..

here is a dump of the new bin file to show the contents has changed (filesize is 0x1c1 - see the bin header):

> 21
>
> H_M_hair000.MOD
>
> H_M_hair001.MOD
>
> H_M_hair002.MOD
>
> H_M_hair003.MOD
>
> H_M_hair004.MOD
>
> H_M_hair005.MOD
>
> H_M_hair006.MOD
>
> H_M_hair007.MOD
>
> H_M_hair008.MOD
>
> H_M_hair009.MOD
>
> H_M_hair010.MOD
>
> H_M_hair011.MOD
>
> H_M_hair012.MOD
>
> H_M_Costume_Wig01_Hair.MOD
>
> H_M_Costume_Wig02_Hair.MOD
>
> H_M_Costume_Wig03_Hair.MOD
>
> H_M_Costume_Wig04_Hair.MOD
>
> H_M_Costume_Wig05_Hair.MOD
>
> H_M_Costume_Wig06_Hair.MOD
>
> H_M_Costume_Wig07_Hair.MOD
>
> H_M_Costume_Wig08_Hair.MOD

what next? well i dont have the ability to follow the decryption function, but maybe this can motivate someone who can
## Post #8
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:59:12+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

thanks
## Post #9
- Username: ChezLinux
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 01, 2011 6:52 am
- Post datetime: 2011-02-05T02:30:10+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

Thank you very much!

Hopefully someone else can follow-up who has the ability to work through the decryption function so we can work it into a stand-alone reader/editor similar to the old one above.
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-06T15:10:24+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: ChezLinux
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 01, 2011 6:52 am
- Post datetime: 2011-02-07T00:40:38+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

Thank you again.  Much appreciated.      

Hopefully someone can take it from here and follow the decryption to be able do a little more, but this is definitely a great start!
## Post #12
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-08T14:24:44+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

woo hoo
this is a great start
## Post #13
- Username: oodmaklub
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 11, 2011 10:46 am
- Post datetime: 2011-03-11T03:09:08+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

i thak you
## Post #14
- Username: hikari
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 18, 2011 2:21 am
- Post datetime: 2011-09-18T03:50:02+00:00
- Post Title: [REQ] Help Luna Online/Luna+ bin file encryption/compression

anyone have the backup of bin dumper by mr.WRS ?
please re-upload it, because the link seems to be unavailable or deleted by the hosting.

thanks.
