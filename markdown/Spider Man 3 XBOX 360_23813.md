## Post #1
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-01T09:52:21+00:00
- Post Title: Spider Man 3 XBOX 360

Hi everyone!

There are different topics that solved two problems: how to extract PCPACK archives from Spider Man 3 and Spider Man: Web Of Shadows on PC. But there are no topics with description of how to extract XEPACK files. It's the same files but from XBOX360 game directory. Also these files got similar structure. 

I got some scripts from the internet and this one is working scipt for Noesis (made by Acewell):

```

def registerNoesisTypes():
    handle = noesis.register("Spiderman 3 (PC)", ".PCPACK")
    noesis.setHandlerExtractArc(handle, pacExtractArc)
    #noesis.logPopup()
    return 1
    
def pacExtractArc(fileName, fileLen, justChecking):
    with open(fileName, "rb") as file:
        bs = NoeBitStream(file.read(fileLen))
    if justChecking:
        return 1
    bs.seek(0x54, NOESEEK_ABS)
    fileCount = bs.readUInt()
    tableLen = fileCount * 16
    TMP = bs.tell()
    myString = bs.readBytes(4500) 
    myIndex = myString.find(b"\xA1\xA1\xA1\xA1")
    bs.seek((TMP + myIndex) - tableLen, NOESEEK_ABS)
    for i in range(fileCount):
        basename = bs.readUInt()
        extension = bs.readUInt()
        offset = bs.readUInt()
        size = bs.readUInt()
        TMP2 = bs.tell()
        fileName = hex(basename) + "." + hex(extension)
        fileName = fileName.replace("0x", "") 
        bs.seek(offset, NOESEEK_ABS)
        rapi.exportArchiveFile(fileName, bs.readBytes(size))
        bs.seek(TMP2, NOESEEK_ABS)
    return 1

```


This script extracts uncompressed PCPACK files. I understood that in bs.seek it needs to be started from 0x57 in XEPACK files. But Noesis always gives me an error:

```
  File "C:\Users\terno_000\Desktop\TOOLS\Noesis\plugins\python\extract_Spiderman3_XEPACK.py", line 30, in pacExtractArc
    bs.seek(offset, NOESEEK_ABS)
  File "C:\Users\terno_000\Desktop\TOOLS\Noesis\plugins\python\inc_noesis.py", line 152, in seek
    self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
  File "C:\Users\terno_000\Desktop\TOOLS\Noesis\plugins\python\inc_noesis.py", line 148, in fromUnpacker
    self.setOffset(self.byteOfs)
  File "C:\Users\terno_000\Desktop\TOOLS\Noesis\plugins\python\inc_noesis.py", line 77, in setOffset
    noesis.bsSetOfs(self.h, ofs)
OverflowError: Python int too large to convert to C long
Detected file type: Unknown
Nothing was exported!
Cleaned 22.82MB (in 2 pools).
```


I understand that the problem is in this line:

```
myString = bs.readBytes(4500)
```


I need to calculate how many bytes should be here. But I can't understand how.. Could anyone help me please?

p.s. there are samples of the same files in different formats (*PCPACK and *XEPACK)
[https://mega.nz/folder/pUF01JjZ#yJKvR3S45Qk1yB3X4Hkg5A](https://mega.nz/folder/pUF01JjZ#yJKvR3S45Qk1yB3X4Hkg5A)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-01T10:49:00+00:00
- Post Title: Spider Man 3 XBOX 360

The reason it doesn't work is because the XBox 360 files use Big Endian format for storing numbers, so the script as it is will only work on PC.

Assuming the file structure is identical, you should be able to change the following line and see if it works:

bs = NoeBitStream(file.read(fileLen))

Change to: bs = NoeBitStream(file.read(fileLen), NOE_BIGENDIAN)
## Post #3
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-01T11:28:50+00:00
- Post Title: Spider Man 3 XBOX 360

> Reply from DKDave ↑Sat May 01, 2021 6:49 pm at Sat May 01, 2021 6:49 pm
>
> 
The reason it doesn't work is because the XBox 360 files use Big Endian format for storing numbers, so the script as it is will only work on PC.

Assuming the file structure is identical, you should be able to change the following line and see if it works:

bs = NoeBitStream(file.read(fileLen))

Change to: bs = NoeBitStream(file.read(fileLen), NOE_BIGENDIAN)

Thanks for the answer!

A tried to change this line and now I got another error:

```
  File "C:\Users\terno_000\Desktop\TOOLS\Noesis\plugins\python\extract_Spiderman3_XEPACK.py", line 21, in pacExtractArc
    bs.seek((TMP + myIndex) - tableLen, NOESEEK_ABS)
  File "C:\Users\terno_000\Desktop\TOOLS\Noesis\plugins\python\inc_noesis.py", line 152, in seek
    self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
  File "C:\Users\terno_000\Desktop\TOOLS\Noesis\plugins\python\inc_noesis.py", line 148, in fromUnpacker
    self.setOffset(self.byteOfs)
  File "C:\Users\terno_000\Desktop\TOOLS\Noesis\plugins\python\inc_noesis.py", line 77, in setOffset
    noesis.bsSetOfs(self.h, ofs)
OverflowError: Python int too large to convert to C long
Detected file type: Unknown
Nothing was exported!
Cleaned 22.82MB (in 2 pools).
```


Got any ideas what the problem is?
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-01T17:22:34+00:00
- Post Title: Spider Man 3 XBOX 360

I'm not sure from looking at the script.  I've rewrote a QuickBMS script using the same logic that should work for both file versions, if you want to give this a try:


 s3.zip
(453 Bytes) Downloaded 28 times
## Post #5
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-01T18:38:04+00:00
- Post Title: Spider Man 3 XBOX 360

> Reply from DKDave ↑Sun May 02, 2021 1:22 am at Sun May 02, 2021 1:22 am
>
> 
I'm not sure from looking at the script.  I've rewrote a QuickBMS script using the same logic that should work for both file versions, if you want to give this a try:

s3.zip

OMG MAN YOU'RE AMAZING! It's really works!   

Now we got important file with extension *54 that contains textures, meshes and other. When we extracting *PCPACK we got *36 important file. So these files (*36 from PC and *54 from XBOX) also similar. There is also script that works with *36 and doesn't works with *54. 

Could you please try to upgrade this script too?

Here is samples of *36 file, *54 file and script for exracting *36 files:
[https://mega.nz/folder/AQEiibwQ#HJmJwXHVOScsmdm9BncX5w](https://mega.nz/folder/AQEiibwQ#HJmJwXHVOScsmdm9BncX5w)

I'll be glad if you could help again
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-01T19:17:00+00:00
- Post Title: Spider Man 3 XBOX 360

Yeah, it looks like the original Python script had the extension in hex, so just a quick modification to my script:



 s3.zip
(478 Bytes) Downloaded 24 times
## Post #7
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-01T19:30:22+00:00
- Post Title: Spider Man 3 XBOX 360

> Reply from DKDave ↑Sun May 02, 2021 3:17 am at Sun May 02, 2021 3:17 am
>
> 
Yeah, it looks like the original Python script had the extension in hex, so just a quick modification to my script:


s3.zip

Hmm. I really got now *36 file instead *54, thanks! But classic 36-extractor script still doesn't extract this file. It's so odd
## Post #8
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-01T20:00:21+00:00
- Post Title: Spider Man 3 XBOX 360

> Reply from DKDave ↑Sun May 02, 2021 3:17 am at Sun May 02, 2021 3:17 am
>
> 
Yeah, it looks like the original Python script had the extension in hex, so just a quick modification to my script:


s3.zip

So interesting.. *36 files from PC and XBOX seem to be similar, but all words and strings in XBOX file looks like.. Mirrored?
Do you know how to fix it?
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-01T20:18:15+00:00
- Post Title: Spider Man 3 XBOX 360

Yes, everything is mirrored because the XBox format is Big Endian, so numbers and strings are the other way around compared to the PC version.  Any scripts that reads those files need to take into account the difference and read them accordingly.

If the format is identical, then it should be a case of just setting the endianness in Noesis (or whatever else is used).
## Post #10
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-01T21:35:16+00:00
- Post Title: Spider Man 3 XBOX 360

> Reply from DKDave ↑Sun May 02, 2021 4:18 am at Sun May 02, 2021 4:18 am
>
> 
Yes, everything is mirrored because the XBox format is Big Endian, so numbers and strings are the other way around compared to the PC version.  Any scripts that reads those files need to take into account the difference and read them accordingly.

If the format is identical, then it should be a case of just setting the endianness in Noesis (or whatever else is used).

Hmm.. How I understand I need to find script that transform big-endian to little-endian, isn't it?
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-01T22:27:00+00:00
- Post Title: Spider Man 3 XBOX 360

Yes...  If the format is identical, then it might be enough just to set any scripts to read Big Endian instead of Little Endian on the PC version.
## Post #12
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-03T19:26:08+00:00
- Post Title: Spider Man 3 XBOX 360

> Reply from DKDave ↑Sun May 02, 2021 6:27 am at Sun May 02, 2021 6:27 am
>
> 
Yes...  If the format is identical, then it might be enough just to set any scripts to read Big Endian instead of Little Endian on the PC version.

Hello again!
So I found the way to swap endianness from big- to small-. But now *36 script-extractor says that offset if wrong:

```
Wrong offset, so we try again!
```


Could you please check what the problem is?
Here are samples of swapped *36 file, unswapped *36 file and script for extraction:

[https://mega.nz/folder/VElECQrC#qQMCsOjmP-iB1GYZ9bI5sQ](https://mega.nz/folder/VElECQrC#qQMCsOjmP-iB1GYZ9bI5sQ)
## Post #13
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-03T21:35:11+00:00
- Post Title: Spider Man 3 XBOX 360

You shouldn't need to change the file data at all - it looks like you've swapped every 4 bytes in the whole file, as all of the texts etc. are the wrong way round.  This definitely won't work as Big Endian only applies when reading numbers; any strings should remain the same, although there are expections, such as some 4-byte strings may be read as numbers.  And not all numbers are on 4-byte boundaries or consist of 4 bytes - e.g some are single bytes, some are 2 bytes, so any swapping will completely change the file.

It's only the script to extract them that should be changed.  I think the script probably needs to be amended as it seems to be searching for only data in Little Endian format.  And it looks like that script is only designed to extract textures too.  So it probably needs a complete rewrite to get everything, unfortunately.
## Post #14
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-04T16:48:46+00:00
- Post Title: Spider Man 3 XBOX 360

> Reply from DKDave ↑Tue May 04, 2021 5:35 am at Tue May 04, 2021 5:35 am
>
> 
You shouldn't need to change the file data at all - it looks like you've swapped every 4 bytes in the whole file, as all of the texts etc. are the wrong way round.  This definitely won't work as Big Endian only applies when reading numbers; any strings should remain the same, although there are expections, such as some 4-byte strings may be read as numbers.  And not all numbers are on 4-byte boundaries or consist of 4 bytes - e.g some are single bytes, some are 2 bytes, so any swapping will completely change the file.

It's only the script to extract them that should be changed.  I think the script probably needs to be amended as it seems to be searching for only data in Little Endian format.  And it looks like that script is only designed to extract textures too.  So it probably needs a complete rewrite to get everything, unfortunately.

Oh, yeah, I see.. I swapped words also. Sorry, I'm little bit a nub in this, ahah   
Okay, thanks for your tips in this theme and your patience!! Will try to change script for reading Big Endian instead of Little Endian. 

Got one more problem. Tried again your script for extracting another *XEPACK file and it doesn't work... I will be so glad if you could check it   

More different samples here:
[https://mega.nz/folder/BEFUDDRQ#V_htxyUrzcBctpG2inCbWg](https://mega.nz/folder/BEFUDDRQ#V_htxyUrzcBctpG2inCbWg)
## Post #15
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-04T22:26:29+00:00
- Post Title: Spider Man 3 XBOX 360

Having looked at the other samples, some of them don't fit the logic of my script.  Some of them have the file table starting in a slightly different place.  There's no obvious offset to the start of this table because the logic used doesn't always work, so I'm stumped on how to calculate it accurately for every file.
## Post #16
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-06T11:08:52+00:00
- Post Title: Re: Spider Man 3 XBOX 360

> Reply from DKDave ↑Wed May 05, 2021 6:26 am at Wed May 05, 2021 6:26 am
>
> 
Having looked at the other samples, some of them don't fit the logic of my script.  Some of them have the file table starting in a slightly different place.  There's no obvious offset to the start of this table because the logic used doesn't always work, so I'm stumped on how to calculate it accurately for every file.

So I think that the solution is edit script every time before extraction new file - it's not a problem. How do you know where the table has starting? Could you give please a tip?
## Post #17
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-06T18:41:36+00:00
- Post Title: Re: Spider Man 3 XBOX 360

The way it was calculated was to look for the hex sequence 0xa1a1a1a1 and subtract the size of the file table to get the start, but this didn't always work.  The file table usually starts at 0x394 in GAME.XEPACK, 0x368 in GAME.PCPACK, somewhere after the string of 0x01 bytes.  In LOCATION_BLACK_CAT_1.XEPACK, the file table starts at 0x3c0.
## Post #18
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-06T21:47:48+00:00
- Post Title: Re: Spider Man 3 XBOX 360

> Reply from DKDave ↑Fri May 07, 2021 2:41 am at Fri May 07, 2021 2:41 am
>
> 
The way it was calculated was to look for the hex sequence 0xa1a1a1a1 and subtract the size of the file table to get the start, but this didn't always work.  The file table usually starts at 0x394 in GAME.XEPACK, 0x368 in GAME.PCPACK, somewhere after the string of 0x01 bytes.  In LOCATION_BLACK_CAT_1.XEPACK, the file table starts at 0x3c0.

Hmm, okay, I understand how to calculate where table is starting, thanks. But how to decide where ENTRIES must start? 

```
Get ENTRIES Long
Get TEMPNAME basename
```


If offset is different so that place where we appoint ENTRIES must be also different - not 0x54 every time, isn't it? How to choose this number?
## Post #19
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-06T22:10:45+00:00
- Post Title: Re: Spider Man 3 XBOX 360

The location of entries is always at 0x54, or at least it is in all of your samples.
## Post #20
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-06T22:28:14+00:00
- Post Title: Re: Spider Man 3 XBOX 360

> Reply from DKDave ↑Fri May 07, 2021 6:10 am at Fri May 07, 2021 6:10 am
>
> 
The location of entries is always at 0x54, or at least it is in all of your samples.

So what string in script I need to change for taking account the starting of the table? (0x349 for one file and 0x3c0 for other)
## Post #21
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-07T11:30:43+00:00
- Post Title: Re: Spider Man 3 XBOX 360

If you delete the following line:

XMath ENTRY "OFFSET - (ENTRIES * 0x10)"

And replace it with:

Math ENTRY = 0x3c0 (or whatever it is)
## Post #22
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-07T17:54:50+00:00
- Post Title: Re: Spider Man 3 XBOX 360

> Reply from DKDave ↑Fri May 07, 2021 7:30 pm at Fri May 07, 2021 7:30 pm
>
> 
If you delete the following line:

XMath ENTRY "OFFSET - (ENTRIES * 0x10)"

And replace it with:

Math ENTRY = 0x3c0 (or whatever it is)

OMG, YES!! It really works! This string is working for most of all other files! 
```
Math ENTRY = 0x3c0
```
 Great thanks for you!!!

Now I got the last problem, It looks like you solved at the first time. There is script that decrypts NCH PCPACK to clean PCPACK:

```
get PCPACK_SIZE asize
log MEMORY_FILE 0 0
append 1
for i = 0
    savepos TMP_OFF
    if TMP_OFF == PCPACK_SIZE
        break
    endif
    idstring "NCH\0"
    get ZSIZE long
    get DUMMY_CRC long
    get SIZE long
    get XOFFSET long
    get DUMMY_CRC long
    get XSIZE long
    get ZIP long
    savepos OFFSET
    goto XOFFSET MEMORY_FILE
    if ZIP == 0
        log MEMORY_FILE OFFSET ZSIZE
    else
        clog MEMORY_FILE OFFSET ZSIZE SIZE
    endif
    math TMP_OFF + XSIZE
    goto TMP_OFF
    padding 0x1000
next i
append
get NAME basename
get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE
```


I need to decrypt the same NCH *XEPACK files and maybe this is the same problem with big-endian reading, maybe no.

Sample of PCPACK with NCH encryption: [https://mega.nz/file/IN8lUKza#cRwyOzfK5 ... AOvTA_D3RU](https://mega.nz/file/IN8lUKza#cRwyOzfK5Di-Dp4ZczMhyYuQNr_j5iOlWAOvTA_D3RU)
Sample of XEPACK with NCH encryption: [https://mega.nz/file/IclnEAgB#0bmDGxpBB ... JfP8QNaXiQ](https://mega.nz/file/IclnEAgB#0bmDGxpBBHA9h5JVUzLyrZkFs68ns_f70JfP8QNaXiQ)

Could you pleace check it? I will be soooo appreciative of it
## Post #23
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-07T18:25:21+00:00
- Post Title: Re: Spider Man 3 XBOX 360

Yes, if you add the following line at the very start of the script, it will decompress the NCH.XEPACK files:

Endian Big

It looks like that's the only change needed, at least for the XEPACK sample, so it should work fine with the others.
## Post #24
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-09T00:18:44+00:00
- Post Title: Re: Spider Man 3 XBOX 360

> Reply from DKDave ↑Sat May 08, 2021 2:25 am at Sat May 08, 2021 2:25 am
>
> 
Yes, if you add the following line at the very start of the script, it will decompress the NCH.XEPACK files:

Endian Big

It looks like that's the only change needed, at least for the XEPACK sample, so it should work fine with the others.

Oh yeah, It really works, big thanks for all!!!
## Post #25
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-09T00:58:38+00:00
- Post Title: Re: Spider Man 3 XBOX 360

> Reply from DKDave ↑Sat May 08, 2021 2:25 am at Sat May 08, 2021 2:25 am
>
> 
Yes, if you add the following line at the very start of the script, it will decompress the NCH.XEPACK files:

Endian Big

It looks like that's the only change needed, at least for the XEPACK sample, so it should work fine with the others.

And also it has appeared new problem. I asked Aluigi if he could upgrade his script (also for working with *36 files). He made it, and script extract all files, but they were empty. Right names, but without extension and empty. After my question he thought and said that it's impossible and better try to use hex2obj.

Maybe you ever encountered with this?

There is original script to extract textures for PC:

```

//idstring "APKF"
findloc PHYS string "PHYS"
goto PHYS
savepos TMP
goto 0x14 0 SEEK_CUR
get infoOffset long
xmath OFFSET "infoOffset + TMP + 0x14"
goto 0x1c
findloc TEX binary "\x54\x45\x58\x00"
goto TEX
goto 0xc 0 SEEK_CUR
savepos TMP1
get tableLoc long
get FILES long
math tableLoc + TMP1
goto tableLoc
for i = 0 < FILES
	savepos TMP2
	get nameOffset long
    math nameOffset + TMP2
    get hash long
	get type long
	get SIZE long
    savepos TMP3
    goto nameOffset
    get NAME string
	findloc hashID long hash
	goto hashID
	goto 0xc 0 SEEK_CUR
	get WIDTH long
	get HEIGHT long
	goto 8 0 SEEK_CUR
	get FORMAT long //14, 15, 32, 33 ,DXT1, DXT3, DXT5
	if FORMAT == 0x31545844 //DXT1
		set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\xDD\xDD\xDD\xDD\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
		putVarChr MEMORY_FILE 0XC HEIGHT long
		putVarChr MEMORY_FILE 0x10 WIDTH long
		putVarChr MEMORY_FILE 0x14 SIZE long
		putVarChr MEMORY_FILE 0x54 FORMAT long
		string NAME + ".dds"
		log NAME 0 0x80 MEMORY_FILE
	elif FORMAT == 0x33545844 //DXT3
		set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\xDD\xDD\xDD\xDD\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
		putVarChr MEMORY_FILE 0XC HEIGHT long
		putVarChr MEMORY_FILE 0x10 WIDTH long
		putVarChr MEMORY_FILE 0x14 SIZE long
		putVarChr MEMORY_FILE 0x54 FORMAT long
		string NAME + ".dds"
		log NAME 0 0x80 MEMORY_FILE
	elif FORMAT == 0x35545844 //DXT5
		set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\xDD\xDD\xDD\xDD\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
		putVarChr MEMORY_FILE 0XC HEIGHT long
		putVarChr MEMORY_FILE 0x10 WIDTH long
		putVarChr MEMORY_FILE 0x14 SIZE long
		putVarChr MEMORY_FILE 0x54 FORMAT long
		string NAME + ".dds"
		log NAME 0 0x80 MEMORY_FILE	
	elif FORMAT == 0x14 //RGB
		set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x40\x00\x00\x00\x00\x00\x00\x00\x18\x00\x00\x00\x00\x00\xFF\x00\x00\xFF\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
		putVarChr MEMORY_FILE 0XC HEIGHT long
		putVarChr MEMORY_FILE 0x10 WIDTH long
		putVarChr MEMORY_FILE 0x14 SIZE long
		string NAME + ".dds"
		log NAME 0 0x80 MEMORY_FILE	
	elif FORMAT == 0x15 //ARGB
		set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x41\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\xFF\x00\x00\xFF\x00\x00\xFF\x00\x00\x00\x00\x00\x00\xFF\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
		putVarChr MEMORY_FILE 0XC HEIGHT long
		putVarChr MEMORY_FILE 0x10 WIDTH long
		putVarChr MEMORY_FILE 0x14 SIZE long
		string NAME + ".dds"
		log NAME 0 0x80 MEMORY_FILE	
	elif FORMAT == 0x32 //L8 (R8)
		set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x08\x00\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
		putVarChr MEMORY_FILE 0XC HEIGHT long
		putVarChr MEMORY_FILE 0x10 WIDTH long
		putVarChr MEMORY_FILE 0x14 SIZE long
		string NAME + ".dds"
		log NAME 0 0x80 MEMORY_FILE	
	elif FORMAT == 0x33 //A8L8 (A8 R8)
		set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x01\x00\x02\x00\x00\x00\x00\x00\x10\x00\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\xFF\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
		putVarChr MEMORY_FILE 0XC HEIGHT long
		putVarChr MEMORY_FILE 0x10 WIDTH long
		putVarChr MEMORY_FILE 0x14 SIZE long
		string NAME + ".dds"
		log NAME 0 0x80 MEMORY_FILE	
	else
		print "Wrong offset, so we try again!"
		findloc hashID long hash
		goto hashID
		print "%hashID|h% :hashid"
		goto 0xc 0 SEEK_CUR
		get WIDTH long
		print "%width|hex% :width"
		get HEIGHT long
		print "%height|hex% :height"
		goto 8 0 SEEK_CUR
		get FORMAT long //15, 32, 33 ,DXT1, DXT3, DXT5
		print "%FORMAT|hex% :format"
		if FORMAT == 0x31545844
			set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\xDD\xDD\xDD\xDD\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
			putVarChr MEMORY_FILE 0XC HEIGHT long
			putVarChr MEMORY_FILE 0x10 WIDTH long
			putVarChr MEMORY_FILE 0x14 SIZE long
			putVarChr MEMORY_FILE 0x54 FORMAT long
			string NAME + ".dds"
			log NAME 0 0x80 MEMORY_FILE
		elif FORMAT == 0x33545844
			set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\xDD\xDD\xDD\xDD\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
			putVarChr MEMORY_FILE 0XC HEIGHT long
			putVarChr MEMORY_FILE 0x10 WIDTH long
			putVarChr MEMORY_FILE 0x14 SIZE long
			putVarChr MEMORY_FILE 0x54 FORMAT long
			string NAME + ".dds"
			log NAME 0 0x80 MEMORY_FILE
		elif FORMAT == 0x35545844
			set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\xDD\xDD\xDD\xDD\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
			putVarChr MEMORY_FILE 0XC HEIGHT long
			putVarChr MEMORY_FILE 0x10 WIDTH long
			putVarChr MEMORY_FILE 0x14 SIZE long
			putVarChr MEMORY_FILE 0x54 FORMAT long
			string NAME + ".dds"
			log NAME 0 0x80 MEMORY_FILE	
		elif FORMAT == 0x14 //RGB8 (24)
			set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x40\x00\x00\x00\x00\x00\x00\x00\x18\x00\x00\x00\x00\x00\xFF\x00\x00\xFF\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
			putVarChr MEMORY_FILE 0XC HEIGHT long
			putVarChr MEMORY_FILE 0x10 WIDTH long
			putVarChr MEMORY_FILE 0x14 SIZE long
			string NAME + ".dds"
			log NAME 0 0x80 MEMORY_FILE	
		elif FORMAT == 0x15 //ARGB8 (32)
			set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x41\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\xFF\x00\x00\xFF\x00\x00\xFF\x00\x00\x00\x00\x00\x00\xFF\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
			putVarChr MEMORY_FILE 0XC HEIGHT long
			putVarChr MEMORY_FILE 0x10 WIDTH long
			putVarChr MEMORY_FILE 0x14 SIZE long
			string NAME + ".dds"
			log NAME 0 0x80 MEMORY_FILE	
		elif FORMAT == 0x32 //L8 (R8)
			set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x08\x00\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
			putVarChr MEMORY_FILE 0XC HEIGHT long
			putVarChr MEMORY_FILE 0x10 WIDTH long
			putVarChr MEMORY_FILE 0x14 SIZE long
			string NAME + ".dds"
			log NAME 0 0x80 MEMORY_FILE	
		elif FORMAT == 0x33 //A8L8 (A8 R8)
			set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x01\x00\x02\x00\x00\x00\x00\x00\x10\x00\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\xFF\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
			putVarChr MEMORY_FILE 0XC HEIGHT long
			putVarChr MEMORY_FILE 0x10 WIDTH long
			putVarChr MEMORY_FILE 0x14 SIZE long
			string NAME + ".dds"
			log NAME 0 0x80 MEMORY_FILE	
		endif
	endif
	append
	log NAME OFFSET SIZE
	append
    math OFFSET + SIZE
	goto TMP3	
next i
```


And there is upgraded version made for extracting textures from xbox files:

```

idstring "APKF"
get DUMMY long
get ZERO long   # 0 or 4 (xbox?)
get DUMMY long  # -1
get DUMMY long  # 2
endian guess DUMMY
savepos TMP
get OFFSET long
math OFFSET + TMP
get ZERO long
math MAX_TYPES = 4
for TYPE = 0 < MAX_TYPES
    getdstring PATH 4
    get DUMMY long
    get STRUCT_TYPE long
    savepos TMP
    get INFO_OFF long
    math INFO_OFF + TMP
    get FILES long
    get DUMMY5 long
    get FLAGS long

    savepos BACKUP_OFF
    goto INFO_OFF
    for i = 0 < FILES
        savepos TMP
        get NAME_OFF long
        math NAME_OFF + TMP
        get CRC long
        get SIZE long
        if STRUCT_TYPE == 1
        elif STRUCT_TYPE == 2
            get DUMMY long
        else
            print "Error: unknown structure %STRUCT_TYPE%, contact me"
            cleanexit
        endif
        savepos TMP
        goto NAME_OFF
        get NAME string
        goto TMP
        string NAME p "%s/%s" PATH NAME
        log NAME OFFSET SIZE
        math OFFSET + SIZE
    next i
    goto BACKUP_OFF
next TYPE

```


I would be so appreciate of it if you could check this
## Post #26
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-09T17:35:13+00:00
- Post Title: Re: Spider Man 3 XBOX 360

I've had a look, but I'm not sure either.  It's a bit of a weird format, but as Luigi says, sometimes if the format can't be worked out properly then you might need to extract the files manually with a hex editor.
## Post #27
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-10T12:03:48+00:00
- Post Title: Re: Spider Man 3 XBOX 360

> Reply from DKDave ↑Mon May 10, 2021 1:35 am at Mon May 10, 2021 1:35 am
>
> 
I've had a look, but I'm not sure either.  It's a bit of a weird format, but as Luigi says, sometimes if the format can't be worked out properly then you might need to extract the files manually with a hex editor.

Yeah, I tried to find the way to extract textures from hex. The only way I found is TextureFinder, but it doesn't work right with this files. I know about hex2obj, but it's extracting only meshes, isn't it?

If you could give an advise how to understand where texture starts, ends and how to calculate size so I can try to find needed strings and separate them to textures. 

Or maybe you know another way to extract it using hex?
## Post #28
- Username: ben10x
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 10, 2022 3:10 pm
- Post datetime: 2022-04-10T07:48:23+00:00
- Post Title: Re: Spider Man 3 XBOX 360

> Reply from DKDave ↑Sun May 02, 2021 1:22 am at Sun May 02, 2021 1:22 am
>
> 
I'm not sure from looking at the script.  I've rewrote a QuickBMS script using the same logic that should work for both file versions, if you want to give this a try:

s3.zip

It's working great!!!
