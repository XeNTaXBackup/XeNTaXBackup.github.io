## Post #1
- Username: thedarkknight
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 25, 2012 8:14 am
- Post datetime: 2012-07-13T11:40:52+00:00
- Post Title: ghost recon future soldier

hi 
i want to extract ghost recon future soldier game models but i couldn't find any extractor.
so any ideas are more than appreciated.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-13T12:34:08+00:00
- Post Title: ghost recon future soldier

Here modified script

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "[ GEAR BigFile ]"
get DUMMY long
get DUMMY long
get FILES long
get DUMMY long

savepos OFFSET_OFF
for i = 0 < FILES
    get DUMMY long
    get DUMMY long
next i

savepos SIZE_OFF
for i = 0 < FILES
    get DUMMY long
next i

savepos CRC_OFF         # crc of the filenames?
for i = 0 < FILES
    get DUMMY long
next i

savepos DUMMY_OFF
for i = 0 < FILES
    get DUMMY string    # or byte?
next i

for i = 0 < FILES
    goto OFFSET_OFF
    get OFFSET long
    get OFFSET64 long
    savepos OFFSET_OFF

    goto SIZE_OFF
    get SIZE long
    savepos SIZE_OFF

    goto CRC_OFF
    get CRC long
    savepos CRC_OFF
	
    string CRC p= "%08x" CRC

    log CRC OFFSET SIZE
next i

```


Filenames hashed (CRC32). Look .report file to get original file names.
## Post #3
- Username: thedarkknight
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 25, 2012 8:14 am
- Post datetime: 2012-07-13T20:43:19+00:00
- Post Title: ghost recon future soldier

woooow thank you Ekey you really made my day    .
thanks again Ekey you rock   .
## Post #4
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2012-07-14T09:25:12+00:00
- Post Title: ghost recon future soldier

> thedarkknight
Its working? For me not  I used latest version of Quick BMS from Aluigi (THX)
Sample:
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-14T14:54:40+00:00
- Post Title: ghost recon future soldier

Seems it's other BIG format.
## Post #6
- Username: thedarkknight
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 25, 2012 8:14 am
- Post datetime: 2012-07-14T20:51:33+00:00
- Post Title: ghost recon future soldier

> Reply from GRiNDERKILLER
>
> 
Sample:

it did the same thing for me .
i think they offset the archive packaging  .
we need someone good at scripting ho can write a script so we can extract it      .
## Post #7
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-07-15T06:49:20+00:00
- Post Title: ghost recon future soldier

@thedarkknight
@GRiNDERKILLER

Ekey's script works perfectly.
you're using it with wrong big file.
try it with files in Sound_Bin_PC folder.
## Post #8
- Username: thedarkknight
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 25, 2012 8:14 am
- Post datetime: 2012-07-16T01:08:00+00:00
- Post Title: ghost recon future soldier

@deepshit

thank you but i don't want to extract sounds 
i want 3D models
## Post #9
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2012-07-17T17:38:05+00:00
- Post Title: ghost recon future soldier

Any idea how to unpack/pack yeti.BIG files in main dir? Thanks to reply.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-17T18:11:39+00:00
- Post Title: ghost recon future soldier

Dunno but try to change

```
idstring "[ GEAR BigFile ]"
```


to

```
idstring "YBIG"
```
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-17T18:36:10+00:00
- Post Title: ghost recon future soldier

for YBIG try the following:
[http://aluigi.org/papers/bms/yeti2.bms](http://aluigi.org/papers/bms/yeti2.bms)

but note that I remember there was something wrong or incomplete so don't hope in a good result
## Post #12
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-07-18T09:07:21+00:00
- Post Title: ghost recon future soldier

> Reply from aluigi
>
> for YBIG try the following:
http://aluigi.org/papers/bms/yeti2.bms

but note that I remember there was something wrong or incomplete so don't hope in a good result

I tested it on all 4 YBIG archives and it didn't work.
It extracts 1kb files.
## Post #13
- Username: thedarkknight
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 25, 2012 8:14 am
- Post datetime: 2012-07-18T20:22:34+00:00
- Post Title: ghost recon future soldier

> Reply from deepshit
>
> aluigi wrote:for YBIG try the following:
http://aluigi.org/papers/bms/yeti2.bms

but note that I remember there was something wrong or incomplete so don't hope in a good result

I tested it on all 4 YBIG archives and it didn't work.
It extracts 1kb files.

same thing happens to me .
looks like theirs a problem with the script . 
please aluigi resolve this problem .
## Post #14
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2018-09-23T13:43:02+00:00
- Post Title: ghost recon future soldier

I finally found a way how to unpack Yeti.big, Yeti.big1, Yeti.big2, Yeti.big3 archives.



Open Yeti.big and goto offset (byte=1487572640) or (hex=58aa8ea0).
Open Yeti.big1 and remove first 65536 bytes then copy rest of bytes and paste it on offset of Yeti.big (byte=1487572640) or (hex=58aa8ea0).
Open Yeti.big2 and remove first 65536 bytes then copy rest of bytes and paste it on offset of Yeti.big.(byte=2975102352) or (hex=b1547590).
Open Yeti.big3 and remove first 65536 bytes then copy rest of bytes and paste it on offset of Yeti.big.(byte=4463445720) or (hex=10a0ac6d8).
Now you can save your file as Yeti_1.big and use bms script to unpack it.

Overall size of created archive Yeti_1.big must be 5896484568 bytes. If not then you did something bad or you have wrong version.
Tested on 1.8 version of the game. Not Steam one.
## Post #15
- Username: Runerd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 13, 2017 5:35 am
- Post datetime: 2018-10-25T08:08:52+00:00
- Post Title: ghost recon future soldier

> Reply from GRiNDERKILLER
>
> I finally found a way how to unpack Yeti.big, Yeti.big1, Yeti.big2, Yeti.big3 archives.



Open Yeti.big and goto offset (byte=1487572640) or (hex=58aa8ea0).
Open Yeti.big1 and remove first 65536 bytes then copy rest of bytes and paste it on offset of Yeti.big (byte=1487572640) or (hex=58aa8ea0).
Open Yeti.big2 and remove first 65536 bytes then copy rest of bytes and paste it on offset of Yeti.big.(byte=2975102352) or (hex=b1547590).
Open Yeti.big3 and remove first 65536 bytes then copy rest of bytes and paste it on offset of Yeti.big.(byte=4463445720) or (hex=10a0ac6d8).
Now you can save your file as Yeti_1.big and use bms script to unpack it.

Overall size of created archive Yeti_1.big must be 5896484568 bytes. If not then you did something bad or you have wrong version.
Tested on 1.8 version of the game. Not Steam one.

Thanks in advance! Which program do you use to open them?
