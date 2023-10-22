## Post #1
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-04-23T02:23:47+00:00
- Post Title: BMS script for DEPONIA dosent work good

Hi,

I need help with the script.
I have the program quickbms and i have the script that is working with the Deponia Demo. The working script is at this location:

[http://aluigi.org/papers/bms/visionaire.bms](http://aluigi.org/papers/bms/visionaire.bms)


But when i try it on the original big file of the game it dosent work its throwing error that it didnt finish to extract the file.
In the demo the file i try to to extract is 21mb and in the game it self not the demo the file is 43mb

Can someone show me create a new script that will work ? Im new to this and tried to make it work but so far nothing.

I just tried to reimport the files i extracted with deponia demo and it dosent work 0 files imported on each of them he give error say the key or address dosent match.

Can someone write a script that will also extract the original data.vis file from the original game file wich is 43mb and also a script for the import to put back all the files togeather after changed them ? The program the quickbms i downloaded from : [http://quickbms.aluigi.org](http://quickbms.aluigi.org) and i tried the script that come with the program and the script in the link above they dosent work on the original game only extracting does work on the demo. 

Thank you very much.
## Post #2
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-04-23T11:06:17+00:00
- Post Title: BMS script for DEPONIA dosent work good

This is a screen shot of the error im getting while trying to extract the original file wich is 43mb.

 a link for the image:

[http://imageshack.us/photo/my-images/17 ... error.jpg/](http://imageshack.us/photo/my-images/17/deponiaerror.jpg/)


The error is: SCRIPTS MESSAGE USE KEY : 98d1a1f120d8ce55
Then i see 6 files all of them .dat
Then Error: incomplete file number 0 cant read 64 bytes. Anyway dont worry...etc...

Then i hit enter and the output directory of the extraction is empty.


------------------------------------------------------------------

The script im usig is: 

# Visionaire Player/Studio (script 0.2)
# script for QuickBMS [http://quickbms.aluigi.org](http://quickbms.aluigi.org)

set KEY binary "76093af7c458e3c5"   # md5 hash of unicode "VSADV3PL"
putarray 8 0 KEY
set KEY binary "98d1a1f120d8ce55"   # md5 hash of unknown string
putarray 8 1 KEY
set KEY binary ""
putarray 8 2 KEY

getdstring SIGN 4
if SIGN == "VIS3"
    get FILES long  # max 0x1869f?
    if FILES u> 0x00ffffff # 0x1869f
        endian big
        reverselong FILES
    endif
    savepos BASE_OFF
    math TMP = FILES
    math TMP *= 16
    math TMP += 6

    # key scanner
    math i = 0
    do
        getarray KEY 8 i
        if KEY == ""
            print "unknown Visionaire key, contact me"
            cleanexit
        endif
        encryption xor KEY
        log MEMORY_FILE BASE_OFF 3
        encryption "" ""
        getdstring SIGN 3 MEMORY_FILE
        math i += 1
    while SIGN != "HDR"
    print "use key %KEY%"

    encryption xor KEY
    log MEMORY_FILE BASE_OFF TMP
    encryption "" ""
    math BASE_OFF += TMP

    getdstring SIGN 3 MEMORY_FILE
    for i = 0 < FILES
        encryption "" ""
        get OFFSET long MEMORY_FILE
        get ZSIZE long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get TYPE long MEMORY_FILE
        math OFFSET += BASE_OFF
        set NAME long i
        string NAME += "."
        string NAME += TYPE
        #if TYPE == 0
        #    string NAME += ".ogv"
        #elif TYPE == 3
        #    string NAME += ".xml"
        #elif TYPE == 8
        #    string NAME += ".png"
        #else
        #    string NAME += ".dat"
        #endif
        set NAME string ""
        if TYPE & 2
            encryption xor KEY
        endif
        if SIZE == ZSIZE
            log NAME OFFSET SIZE
        else
            clog NAME OFFSET ZSIZE SIZE
        endif
    next i
else
    # if you have only one big executable you must first dump
    # everything from the first occurrence of the bytes d1 b5 d1
    set PASSWD string "PASSWD"
    strlen TMP PASSWD
    for i = 0 < TMP
        getvarchr BYTE PASSWD i
        math BYTE += 0x2b
        math BYTE n= BYTE   # needed for Encryption
        putvarchr PASSWD i BYTE
    next i
    encryption rot PASSWD "" "" TMP
    get SIZE asize  # yeah, lame way but it's the only one here
    math SIZE /= 4  # because it's necessary a one-byte function
    log MEMORY_FILE 0 SIZE
    encryption "" ""
    idstring MEMORY_FILE "VIS"
    get FILES long MEMORY_FILE
    for EXTRACT = 0 < 2
        goto 7 MEMORY_FILE
        for i = 0 < FILES
            get NAMESZ byte MEMORY_FILE
            getdstring NAME NAMESZ MEMORY_FILE
            get OFFSET long MEMORY_FILE
            get SIZE long MEMORY_FILE
            if EXTRACT != 0
                math OFFSET += BASE_OFF
                log NAME OFFSET SIZE
            endif
        next i
        savepos BASE_OFF MEMORY_FILE
    next EXTRACT
endif


This script is working for the deponia demo data.vis file but dosent work on the data.vis file of the original game.
Both files have the same name and both start with VIS3 only the size is not the same.

I dont understand why it dosent work on the original game file.


-------------------------------------------------------------


Then when i try to reimport back the extracted files i have a shortcut wich is:

Z:\quickbms.exe -r -w

Start in .\

Its working all over the files of the demo in the end im getting error it dosent match 0x0000000 or something like that and there is no output file.

Link for the image of the not working reimport shortcut: [http://imageshack.us/photo/my-images/82 ... rror1.jpg/](http://imageshack.us/photo/my-images/827/deponiaerror1.jpg/)
## Post #3
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-04-23T15:56:02+00:00
- Post Title: BMS script for DEPONIA dosent work good

I just uploaded the data.vis file to mediafire about 40mb maybe it will help here someone to create/build/change the script to make it work.

[http://www.mediafire.com/?kj28u2yz4na14lq](http://www.mediafire.com/?kj28u2yz4na14lq)


Thanks you.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-23T17:53:06+00:00
- Post Title: BMS script for DEPONIA dosent work good

there is no problem with the script, it's the file which is "damaged" (not by you, maybe it's an anti-script solution of the developers for invalidating the format).
look:

```
32 1b 3f 38 63 4e 6e 35 39 38 6c 31 61 1a 3d 31   2.?8cNn598l1a.=1
32 5c cc 38 63 09 9d 35 40 38 64 31 61 a9 65 31   2\.8c..5@8d1a.e1
32 77 45 38 63 22 14 35 39 40 64 31 61 ee 42 31   2wE8c".59@d1a.B1
32 f3 1f 38 63 a6 4e 35 39 38 40 31 60 93 f9 31   2..8c.N598@1`..1
32 76 86 38 63 23 d7 35 39 38 64 40 60 d8 e7 31   2v.8c#.598d@`..1
32 81 c5 38 63 d4 94 35 39 38 64 31 40 aa 44 31   2..8c..598d1@.D1
32 43 59 38 63 16 08 35 39 38 64 31 62 40 39 31   2CY8c..598d1b@91
32 97 30 38 63 c2 61 35 39 38 64 31 62 84 40 31   2.08c.a598d1b.@1
32 a8 46 38 63 fd 17 35 39 38 64 31 65 7c b3 40   2.F8c..598d1e|.@
32 0b 88 38 63 5e d9 35 39 38 64 31 65 b8 a7 31   2..8c^.598d1e..1
32 0a 8c 38 63 5f dd 35 39 38 6c 31 65 f5 cf 31   2..8c_.598l1e..1
32 09 af 38 63 5c fe 35 39 38 6c 31 65 cf 12 31   2..8c\.598l1e..1
```

from offset 0x8 starts a xored file table.
as you can see there are 8 '@' chars starting from offset 0x28 and at an interval of 0x11 bytes one from the other.

being a fixed byte but different decrypted content (almost all are 0x00s except 3 or 4 bytes) it means that there is nothing to decrypt so it's not possible to make an universal guesser and fixer.

anyway (I like to make big introductions and explanation and then putting the magic link at the end ih ih ih) I have updated the script to support the Deponia crazyness:
[http://aluigi.org/papers/bms/visionaire.bms](http://aluigi.org/papers/bms/visionaire.bms)
## Post #5
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-04-23T18:50:08+00:00
- Post Title: BMS script for DEPONIA dosent work good

Aluigi the updated scripy in the link give me the same error as before.
Are you sure its updated ? I just checked compared it to the deponia script i already have and it seems excatly the same.


Thanks.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-23T18:54:24+00:00
- Post Title: BMS script for DEPONIA dosent work good

you are loading the cache of your browser, the new version is 0.2.1
## Post #7
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-04-23T18:58:58+00:00
- Post Title: BMS script for DEPONIA dosent work good

Aluigi can maybe you could also update or make a script for the reimport shortcut i tried to use it with the script of the deponia demo but it gave me errors.
I will need to reimport to make in the end the data.vis big file again after changes in the original game.


Thanks.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-23T19:04:45+00:00
- Post Title: BMS script for DEPONIA dosent work good

if I'm not in error the reimporting should work.
only for the first 10 files you can't use the reimport due to that crazy thing in Deponia but I don't see problems for the others.
in any case I can do nothing else
## Post #9
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-04-23T19:10:16+00:00
- Post Title: BMS script for DEPONIA dosent work good

Great thanks the extraction is working.
The reimpoert dosent i will try to make it work without the first 10 files but then i guess the game will not run good.

In my reimport shortcut properties i see: D:\quickbms\quickbms.exe -r -w
And under it in start in  .\
And i used the last script 0.2.1 but it didnt work on all the files its giving me the error as above dosent match....


I will try it to see what to do.


Thanks a lot for the help.
## Post #10
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-04-23T19:15:59+00:00
- Post Title: BMS script for DEPONIA dosent work good

No the reimport dosent work. After extracted the files i have 1195 files all togeather are 85.6mb
The original data.vis file was only 43mb

So i used the reimporter with hte last scrip 0.2.1 and selected all the files except the first 10 files but it didnt work gave me error on all over the files.

Why there are 1195 files and they are all togeather 85.6mb if the original file is 43mb ?
And any ideas what else can i do to reimport the files back ?


Thanks and sorry for bothering.
## Post #11
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-04-23T19:20:25+00:00
- Post Title: BMS script for DEPONIA dosent work good

Luigi 

I tried to reimport only the big xml file wich is one file of 47,662mb used the last deponia script you gave me the 0.2.1
And it gave me this error: [http://imageshack.us/photo/my-images/13 ... rror2.jpg/](http://imageshack.us/photo/my-images/13/deponiaerror2.jpg/)

And i didnt change yet anything in the big xml file. I selected only him to be reimport and it dosent work.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-23T19:37:00+00:00
- Post Title: BMS script for DEPONIA dosent work good

> Reply from Chocolade1972
>
> 
Why there are 1195 files and they are all togeather 85.6mb if the original file is 43mb ?

Compression maybe.

> And i didnt change yet anything in the big xml file. I selected only him to be reimport and it dosent work.

Select the archive that you unpacked.
