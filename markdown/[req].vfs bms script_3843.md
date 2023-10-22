## Post #1
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-06T06:04:54+00:00
- Post Title: [req].vfs bms script?

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-08T12:57:01+00:00
- Post Title: [req].vfs bms script?

```
ComType ZLib1 ;
Get U1 Long 0 ;
Get BankSize Long 0 ;
Get U2 Long 0 ;
Get U3 Long 0 ;
Get U4 Long 0 ;
Get TOffset Long 0 ;
Set J Long 156 ;
GoTo J 0 ;
Do ;
SavePos ResStart 0 ;
Get ID Long 0 ;
If ID = 1751474532 ;
Get NumberOfBanks Long 0 ;
Get U6 Long 0 ;
Get CompressedSize Long 0 ;
SavePos FO 0 ;
Math NumberOfBanks *= BankSize ;
Math ResStart += NumberOfBanks ;
Set UCS Long 16 ;
Math UCS *= CompressedSize ;
CLog "" FO CompressedSize 0 0 UCS 0 ;
GoTo ResStart 0 ;
Else ;
Set ResStart Long TOffset ;
GoTo ResStart 0 ;
EndIf ;
While ResStart < TOffset ;
```


This is a BMS for MultiEx Commander. You can get the compiled *.bms here:


 vfs.zip
(388 Bytes) Downloaded 64 times



Note that there are no filenames with this script, as there are none in the archive. At least, I expect so. There are 9 files (zlib compressed) in the file, followed by a tail. The tail is odd, and has 21 entries. That could be small pieces of text, and hashed at that. I can write another script to extract all those entries. 
It would help if we had more *.vfs files to work with. 

The files that are extracted are some XML and some GamEmbryo game engine specific files, a long with meshes it seems.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-08T14:15:36+00:00
- Post Title: [req].vfs bms script?

the specified uncompressed size (UCS) is too small.
for example the first file which starts at offset 0xac has a compressed size of 46074 (0xb3fa) and an uncompressed one of 1070608 but your script uses a 16 multiplier which so sets a max size of 737184 and the extraction fails or is incomplete if you have received no warnings/errors (quickbms indeed reports the zlib error -5, Z_BUF_ERROR).
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-08T14:25:04+00:00
- Post Title: [req].vfs bms script?

if more files are needed here is the installer once I download it Ill upload some more files.
[http://down.qq.com/xxz/full/QQXXZ_Full_ ... 4.1735.exe](http://down.qq.com/xxz/full/QQXXZ_Full_Install_Ver1.14.1735.exe)
the installer is 570Mb
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-08T14:49:10+00:00
- Post Title: [req].vfs bms script?

OK, aluigi, thanks. It's a bit annoying when there's not a UCS variable somewhere. I just figured an estimated compression 1/16th of original size would suffice. Obviously not. Well, then 32 or even 64 might be enough.
## Post #6
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-08T15:08:40+00:00
- Post Title: [req].vfs bms script?

Thanks!

after installation of game, we can launch the client and enter game account(acc:869222041,pwd: xentaxforum).then it will give error information,we can dump the xxzshell with hxd. and now we can find the filenames of all file and other information.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-08T20:15:16+00:00
- Post Title: [req].vfs bms script?

Ok, the big xxz.vfs file contains some 17800 files, that I can extract with the adapted script. At the end, there is the tail that has some 18000 entries. I'm pretty sure the tail holds the key to the filenames. Did you see the game has a vfs.dll file? In there, there's text reference to a FDT part in the .vfs. I think that might be File Dxxx Table or something, the tail part . Perhaps it's even possible to use the dll to do everything. 

Here's a few extracted graphics files, there's TGA, GIF, BMP etc in there.



file10.png (321.12 KiB) Viewed 540 times





file17379s.jpg (171.75 KiB) Viewed 540 times





file17588.png (81.64 KiB) Viewed 540 times
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-08T20:26:39+00:00
- Post Title: [req].vfs bms script?

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-08T23:02:42+00:00
- Post Title: [req].vfs bms script?

Great work! 

OPEN vfs.dll with ida pro, and we find:

```
call    sub_100033B8
pop     ecx
mov     ecx, [ebp+var_2C]
mov     eax, [ecx]
push    esi
push    offset a_?fdt   ; ".?fdt"
call    dword ptr [eax+8Ch]
cmp     eax, edi
mov     [ebp+var_34], eax
mov     ecx, esi
jz      loc_1000F715


```


call dword ptr[eax+8ch]:

```
lea     ecx, [ebp+NumberOfBytesRead]
push    ecx             ; lpNumberOfBytesRead
push    4               ; nNumberOfBytesToRead
lea     eax, [esi+14h]
push    eax             ; lpBuffer
push    [ebp+hFile]     ; hFile
call    ebx ; ReadFile
test    eax, eax
jz      loc_1000F864


```


now call ebx;readfile: jump again we can find more functions which handle .vfs file.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-08T23:15:58+00:00
- Post Title: [req].vfs bms script?

Wait, upon examining the vfs.dll file in IDAPro, I noticed a reference to a CodeFilter.cpp, along with a 16-byte array :

```

```


This code is used in a function that is called by another function. The first function calculates a value by ANDing a gotten value with 0F and then presumably that value is used to pick the right letter from the above array (e.g. 0e would pick 'X', while 0 would pick 'Q'). A value of 16 or higher would return 32 (a space character).  

Now notice the following in the tailsection of a vfs file, it is one complete tailentry:



Untitled-2.jpg (120.14 KiB) Viewed 495 times



Take a look at the distribution of all 256 characters, of course only 16 show up:



Untitled-4.jpg (123.4 KiB) Viewed 492 times



Recognize them? Yes, only those that are in the filter array in the vfs.dll: QIKJHMNAETOGDCXS

As you can see, Q is represented much more than all the others. I guess you figured out by now why that is so. Yes, because a 0 is more abundant in this type of file allocation table. And the function in the dll picks a 'Q' whenever the value input is 0. 

This however leaves us with a problem to solve. These 16 characters can thus presumably only represent a byte value from 00-0F each. That is not much to go by,if we want filenames in our language. Unless, it is like "0F 08 0D 0A" etc that later is combined into F8DA or something alike. Or in UTF-16 to get Oriental characters. Just a thought.
## Post #11
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-08T23:51:06+00:00
- Post Title: [req].vfs bms script?

You did almost beat me   

```
#include <stdlib.h>
#include <string.h>
#include <stdint.h>
#include <assert.h>

/**
 * Converts an encoded character to a nibble.
 *
 * [in] c: The encoded character.
 * [out] retVal: The nibble, or -1 on error.
 */
int decodeNibble(char c)
{
    static const char key[] = "QIKJHMNAETOGDCXS";

    for (int i = 0; i < strlen(key); i++)
        if (key[i] == c) return i;

    return -1;
}

/**
 * Decode an encoded string to an array of bytes.
 *
 * [in] text: Encoded string.
 * [in] textLen: Encoded string length.
 * [out] bytes: Decoded bytes (will need to free() them).
 * [out] bytesLen: Size of the "bytes" array.
 * [out] retVal: Zero on success, nonzero on error.
 */
int decodeString(const char *text, size_t textLen, uint8_t **bytes, size_t *bytesLen)
{
    if ((textLen % 2) != 0) // 2 characters are a byte, so it has be a multiple of 2
        return !0;

    // Allocate the output array
    *bytesLen = textLen / 2;
    *bytes = (uint8_t *)malloc(*bytesLen);
    if (*bytes == NULL)
        return !0;

    // Decode
    int n1, n2;

    for (size_t i = 0; i < textLen; i += 2)
    {
        // Decode 2 character to 2 nibbles
        n1 = decodeNibble(text[i + 1]);
        n2 = decodeNibble(text[i]);

        if (n1 == -1 || n2 == -1)
            return !0;

        // Combine
        (*bytes)[i / 2] = n1 | (n2 << 4);
    }

    return 0;
}

```


Basically it's what you said, each character on the "string" is a nibble (that can be converted using that 16 byte string), and to make bytes, the first character of each pair is the high part, and the second one is the low part.

By the way, it seems to contain the names 

EDIT: Fixed a little bug
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-09T07:14:18+00:00
- Post Title: [req].vfs bms script?

Ah, I love it when I'm right.   

Also great work, GameZelda! I'm sure that decode routine will come in handy. Got a few examples of decoded filenames ? Because there's still a lot of Q's in there. We still need to figure out the format of the tail entries after they've been decoded.
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-09T11:01:36+00:00
- Post Title: [req].vfs bms script?

I have written a basic script for the extraction, if someone wants to have fun there is still the directory tree to implement so this simple script extracts the files without the folders:

```
goto 0x18
get INFO_OFF long
goto INFO_OFF
get FILES long
for i = 0 < FILES
    get DATASZ long
    get DUMMY long
    savepos INFO_OFF

    #encryption charset2 "\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0QIKJHMNAET\0\0\0\0\0\0\0OGDCXS" #wait quickbms 0.3.8
    encryption charset "\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\x37\0\x64\x63\x38\0\x62\x34\x31\x33\x32\0\x35\x36\x61\0\x30\0\x66\x39\0\0\0\x65\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0"
    comtype hex
    clog MEMORY_FILE INFO_OFF DATASZ DATASZ
    encryption "" ""

    idstring MEMORY_FILE "daeh"
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get SIZE long MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get TYPE long MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get NEXT_DATA long MEMORY_FILE  # for folders

    math OFFSET += 16
    if TYPE == 0
        log NAME OFFSET SIZE
    elif TYPE == 1
        comtype zlib
        clog NAME OFFSET ZSIZE SIZE
    elif TYPE == 2
        # folder
    else
        print "unknown type %TYPE%"
        cleanexit
    endif

    math INFO_OFF += DATASZ
    goto INFO_OFF
next i
```
## Post #14
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-09T11:52:24+00:00
- Post Title: [req].vfs bms script?

ok.it works.
but quickbms sends error information after extracting 13128 files from zzx.vfs.

```

```
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-09T12:00:42+00:00
- Post Title: [req].vfs bms script?

While I applaud you thanking aluigi, the important forework was done by others.
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-09T12:40:53+00:00
- Post Title: Re: [req].vfs bms script?

@Chessman
can you try with the following updated script?

```
goto 0x18
get INFO_OFF long
goto INFO_OFF
get FILES long
for i = 0 < FILES
    get DATASZ long
    get DUMMY long
    savepos INFO_OFF

    #encryption charset2 "\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0QIKJHMNAET\0\0\0\0\0\0\0OGDCXS" #wait quickbms 0.3.8
    encryption charset "\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\x37\0\x64\x63\x38\0\x62\x34\x31\x33\x32\0\x35\x36\x61\0\x30\0\x66\x39\0\0\0\x65\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0"
    comtype hex
    clog MEMORY_FILE INFO_OFF DATASZ DATASZ
    encryption "" ""

    idstring MEMORY_FILE "daeh"
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get SIZE long MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get TYPE long MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get NEXT_DATA long MEMORY_FILE  # for folders

    math OFFSET += 16
    if TYPE == 0    # I don't know if it's used
        log NAME OFFSET SIZE
    elif TYPE == 1
        comtype zlib
        if SIZE == ZSIZE
            log NAME OFFSET SIZE
        else
            clog NAME OFFSET ZSIZE SIZE
        endif
    elif TYPE == 2
        # folder
    else
        print "unknown type %TYPE%"
        cleanexit
    endif

    math INFO_OFF += DATASZ
    goto INFO_OFF
next i
```
I will delete the one in the previous post if this one solves the problem with the 13138th file, so let me know if it's ok
## Post #17
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-09T13:53:12+00:00
- Post Title: Re: [req].vfs bms script?

there're 13128 files in out-folder. but while extracting, many files  were overwritten by  files with same filename.so > 13128. maybe there are many files which have same filename in diff directorys.
## Post #18
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-09T14:03:39+00:00
- Post Title: Re: [req].vfs bms script?

form xxshell dump files, we can find some xml file(book.xml, item.xml ,etc.) . but there're not in out-folder.maybe their size are so large that quickbms can't extract them from vfs file.
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-09T14:08:59+00:00
- Post Title: Re: [req].vfs bms script?

Like I said. We still have to figure out the folder sytem.
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-11T11:43:57+00:00
- Post Title: Re: [req].vfs bms script?

I'll have a tool for you ready soon.
## Post #21
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-11T15:06:46+00:00
- Post Title: Re: [req].vfs bms script?

> Reply from Mr.Mouse
>
> I'll have a tool for you ready soon.

Thanks!
## Post #22
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-14T10:17:26+00:00
- Post Title: Re: [req].vfs bms script?

I figured out the folder format. Just to update you, I'm working on that tool.
## Post #23
- Username: shekofte
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-22T12:14:01+00:00
- Post Title: Re: [req].vfs bms script?

Okay, I've got a rough tool for you. 

Just start the loader and select vfsExtractor. 

Now open that xxz.vfs archive. Wait for the analysis and then select the arrow to extract all files into a folder of your choice. Mind, the tool is NOT idiot proof, like most tools in that loader of mine 

[EDIT]updated the zip file.
[xentaxtools_1.zip](https://xentaxbackup.github.io/file/2546_xentaxtools_1.zip)
## Post #24
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-22T21:52:56+00:00
- Post Title: Re: [req].vfs bms script?

[http://www.xentax.com/?p=223](http://www.xentax.com/?p=223) There's an update.
## Post #25
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-23T16:17:55+00:00
- Post Title: Re: [req].vfs bms script?

> Reply from Mr.Mouse
>
> http://www.xentax.com/?p=223 There's an update.

Great Done!Thks Mr.Mouse.

when analyzing xxz.vfs archive (618,389,304 bytes after updating the game client), it occurs:
[vfserror.png](https://xentaxbackup.github.io/file/2548_vfserror.png)
## Post #26
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-23T19:34:02+00:00
- Post Title: Re: [req].vfs bms script?

Hmm, that is odd. It works on my xxz.vfs file. Try this dll, overwrite the other in tools/vfsextractor. It will create a debug.txt file there. please attach that here after it crashed.


 vfsextractor.zip
(30.92 KiB) Downloaded 47 times
## Post #27
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-23T23:02:50+00:00
- Post Title: Re: [req].vfs bms script?

Crash again.
I can extract all files from xxz.vfs before updating client, and I can extract files from res_patch.vfs in the patch file.
here 's debug.txt.
Thks.
[debug.rar](https://xentaxbackup.github.io/file/2550_debug.rar)
## Post #28
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-24T11:50:44+00:00
- Post Title: Re: [req].vfs bms script?

Ok, well the updated extractor does not change anything in the extraction process. Just a debug.txt. 

Anyway, I'm glad it works on the original xxz.vfs file. This means that the updating process alters the file table. I suspect there will now be empty spaces in the table (files of 0 length), which will lead to an overflow in the calculation process of the Extractor. I can ignore such errors and you can see what happens. Alternatively, you can use the FileCutter to cut out the 1 MB (1024 Kb) and upload the resulting zip file of the UPDATED xxz.vfs, so I can take a look at it.
## Post #29
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-24T12:19:00+00:00
- Post Title: Re: [req].vfs bms script?

well.plz ignor errors and I will try again. I don't know how to use filecutter.
thanks.
## Post #30
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-24T12:32:32+00:00
- Post Title: Re: [req].vfs bms script?

That is easy. 

1. Select the FileCutter:



24-11-2009 13-27-36.png (17.65 KiB) Viewed 165 times



2. Select 1024K:



24-11-2009 13-28-22.png (27.33 KiB) Viewed 165 times



3. Select the xxz.vfs file and then give a name for the new file (that you must upload)



24-11-2009 13-29-47.png (27.09 KiB) Viewed 165 times



4. Click Go! to start.
## Post #31
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-24T12:47:26+00:00
- Post Title: Re: [req].vfs bms script?

The contents of this post was deleted because of possible forum rules violation.
## Post #32
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-24T22:28:44+00:00
- Post Title: Re: [req].vfs bms script?

Well, I could not see it. The pieces of 1024K are too small. Try this and attach the debug.txt.
[vfsextractor.zip](https://xentaxbackup.github.io/file/2556_vfsextractor.zip)
## Post #33
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-24T23:13:08+00:00
- Post Title: Re: [req].vfs bms script?

it works on .vfs in patch file, not xxz.vfs.
[debug.rar](https://xentaxbackup.github.io/file/2557_debug.rar)
## Post #34
- Username: shekofte
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-25T07:28:34+00:00
- Post Title: Re: [req].vfs bms script?

LOL.Found the bug, and it was a very STUPID one. 

THis should fix the issue.


 vfsextractor.zip
fixed bug (29.61 KiB) Downloaded 92 times
## Post #35
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-25T12:14:24+00:00
- Post Title: Re: [req].vfs bms script?

OK.it works on the updated vfs files.
Thank you,Mr.Mouse.
## Post #36
- Username: Chessman
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-25T12:50:28+00:00
- Post Title: Re: [req].vfs bms script?

Good, now thank me by clicking the <thank post> button dammit! Do you realise the amount of work that has gone into deciphering this format and programming that tool?
## Post #37
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2009-11-25T14:05:06+00:00
- Post Title: Re: [req].vfs bms script?

> Reply from Mr.Mouse
>
> Good, now thank me by clicking the <thank post> button dammit! Do you realise the amount of work that has gone into deciphering this format and programming that tool?
  I do. This tool is great.
## Post #38
- Username: xtx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 05, 2009 10:05 am
- Post datetime: 2009-12-05T10:03:36+00:00
- Post Title: Re: [req].vfs bms script?

The contents of this post was deleted because of possible forum rules violation.
## Post #39
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-05T11:57:54+00:00
- Post Title: Re: [req].vfs bms script?

uhmmm only for my personal curiosity:
wasn't more simple and easy to add the missing part for handling the folders tree in the bms script I posted?

it was already done at 95% :)
if the complete tree is not important I could add at least the handling of the last folder to avoid the problem of the files with the same name.

anyway was only a curiosity.
## Post #40
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2011-12-03T19:30:16+00:00
- Post Title: Re: [req].vfs bms script?

The contents of this post was deleted because of possible forum rules violation.
