## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-09-30T12:58:48+00:00
- Post Title: PSP MediEvil Resurrection .BIN

Hi, I need help unpack the PSP MediEvil Resurrection .BIN file and possibly other files that contains game data.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-10-03T09:37:46+00:00
- Post Title: PSP MediEvil Resurrection .BIN

Refreshing...

I also upload a small copy of my archive made by WATTOs File Cutter.
I hope maybe someone will be interested in this topic 
[gamedata.bin.zip](https://xentaxbackup.github.io/file/5874_gamedata.bin.zip)
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-06T09:44:14+00:00
- Post Title: PSP MediEvil Resurrection .BIN

I guess the following script does the job, let me know the result:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "TOCS"
get ARCHIVES long
for i = 0 < ARCHIVES
    get HEAD_SIZE long
    get OFFSET long
    getdstring NAME 0x20
    savepos TMP_OFF
    math OFFSET *= 0x800
    goto OFFSET
    savepos BASE_OFF
    idstring "TOC"
    get DUMMY byte
    get XFILES long
    get FILES long
    get DUMMY long
    for j = 0 < XFILES
        get OFFSET long
        get DUMMY short
        get DUMMY short
        putarray 0 j OFFSET
    next j
    for j = 0 < FILES
        get CRC long
        get SIZE long
        getdstring TYPE 4
        get DUMMY short
        get DUMMY short
        get DUMMY short
        get DUMMY short
        getarray OFFSET 0 j
        math OFFSET -= 1
        math OFFSET *= 0x800
        math OFFSET += BASE_OFF
        if SIZE != 0
            log "" OFFSET SIZE
        endif
    next j
    goto TMP_OFF
next i
```
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-10-06T10:40:39+00:00
- Post Title: PSP MediEvil Resurrection .BIN

Thank you aluigi! Your scripts are the best in the world! 

Using quickbms and your script i extracted many files with extensions .dat .psm .act .mod .ipm .fli .lng .wav .nfc .pkg .neo .ske .sta .txt .frg
and there is one file .dfont Can it be file with all fonts from game?

.lng - all texts from game
.txt - game scripts
.wav - sounds
I don't know other extensions ;p
After extraction there are 6283 files in my folder 

And I received following errors:



What do you think? Is everything good?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-06T12:35:17+00:00
- Post Title: PSP MediEvil Resurrection .BIN

for the first problem I thought to have fixed some versions ago, are you using quickbms 0.5.15a?
if yes, I will in the next version.

anyway don't worry, just type the name manually removing weird chars like * and it's ok

while for the second problem I guess you can ignore it because you are just at the end of the archive so there is nothing else to extract.
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-10-06T12:54:52+00:00
- Post Title: PSP MediEvil Resurrection .BIN

> are you using quickbms 0.5.15a?
Yes, i am.

Is it possible to get proper file names?
For example if i have 000008d1.lng file can it be english.lng or something like that?
You can get lost in these names 

Thanks again for your great work
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-06T13:15:31+00:00
- Post Title: PSP MediEvil Resurrection .BIN

filenames are not stored in the archive as far as I have seen so it's not possible to guess/retrieve them
## Post #8
- Username: InnocentSam2
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Apr 05, 2012 9:06 pm
- Post datetime: 2012-12-30T16:02:25+00:00
- Post Title: PSP MediEvil Resurrection .BIN

I unpacked gamedata.bin with your quickbms, and only the .txt files are usable. 

The output is only 223mb as well, and the file itself is 535mb.
## Post #9
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-01-01T05:51:22+00:00
- Post Title: PSP MediEvil Resurrection .BIN

> Reply from aluigi
>
> filenames are not stored in the archive as far as I have seen so it's not possible to guess/retrieve them
Just curious where else could the file names be then? There are other examples of PSP games that have the same type of .BIN file which contains pretty much the whole game's data.
## Post #10
- Username: Xeeynamo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jan 07, 2011 6:25 pm
- Post datetime: 2013-01-04T14:45:26+00:00
- Post Title: PSP MediEvil Resurrection .BIN

> Reply from MiLØ
>
> aluigi wrote:filenames are not stored in the archive as far as I have seen so it's not possible to guess/retrieve them
Just curious where else could the file names be then? There are other examples of PSP games that have the same type of .BIN file which contains pretty much the whole game's data.
The file names are hashed inside the TOC files, there are no chances to know the original strings. Inside the game there is a function that with a string in input (for example "medievil_00.mdl", it give as output an hash that looks like 0x12345678, this hash is found on TOC that has a file entry structure like HASH, Position, Size, Format and the file is loaded. The only way to retrieve the original file names is to find how this hashing function works (the only way is to find and disassemble it from the EBOOT.BIN of the game) and bruteforce the strings. Kingdom Hearts 1 and 2 uses the same system, I cracked all the hashing system but in two years I didn't cracked all the hashed filenames =\. F(x) produce y where x is the string and y the hash, but it will be never a G(y) that will produce the x. I hope that my explanations are clear.
## Post #11
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-01-05T17:01:53+00:00
- Post Title: PSP MediEvil Resurrection .BIN

Your explanation is good enough to understand that it's a ridiculously difficult process obtaining the file names. Thanks, Xeeynamo.
I guess it's a blessing that not all developers are using this hash madness, otherwise nothing would ever get done.
## Post #12
- Username: ViToTiV
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 11, 2009 12:38 am
- Post datetime: 2017-11-04T10:35:00+00:00
- Post Title: PSP MediEvil Resurrection .BIN

aluigi, your script is not complete. Archive is more complicated than it seems at first.
My utility for FULL unpack and FULL repack "gamedata.bin" - [https://mega.nz/#!Q9cGFJ7I!cO9RX4wzNsZr ... A_w7ulp1w8](https://mega.nz/#!Q9cGFJ7I!cO9RX4wzNsZriagc_ivw79lcKz61EEUtUA_w7ulp1w8)
Fonts in "01-global.group.toc_ex\00491.psm" - "01-global.group.toc_ex\00501.psm" files (metric in BIN files)
Text in *.LTR  files
maybe, this will help to someone
## Post #13
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-11-04T11:32:52+00:00
- Post Title: PSP MediEvil Resurrection .BIN

@ViToTiV, thank you :33

Could you please post full file format? I'm just curious. 
Did you manage to edit those fonts? :p
## Post #14
- Username: ViToTiV
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 11, 2009 12:38 am
- Post datetime: 2017-11-04T11:52:20+00:00
- Post Title: PSP MediEvil Resurrection .BIN

i wrote this util some time ago, it's hard to remember file format
i can upload Delphi sourcecode, it will be easy to me
## Post #15
- Username: ViToTiV
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 11, 2009 12:38 am
- Post datetime: 2017-11-04T12:28:39+00:00
- Post Title: PSP MediEvil Resurrection .BIN

> Reply from ikskoks
>
> Did you manage to edit those fonts? :p
use TileMolester
codec - 4bit
offset - 0x60
Block size - 4x1
Canvas size - 32x30

[](http://rgho.st/8ncqXyV9p.view)
## Post #16
- Username: Denis
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Oct 03, 2009 10:15 pm
- Post datetime: 2017-11-05T09:48:14+00:00
- Post Title: Re: PSP MediEvil Resurrection .BIN

> Reply from ViToTiV
>
> i wrote this util some time ago, it's hard to remember file format
i can upload Delphi sourcecode, it will be easy to me

Can you upload source code?
## Post #17
- Username: ViToTiV
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 11, 2009 12:38 am
- Post datetime: 2017-11-08T07:38:49+00:00
- Post Title: Re: PSP MediEvil Resurrection .BIN

Delphi Source [https://yadi.sk/d/IvT4lvtA3PW8tJ](https://yadi.sk/d/IvT4lvtA3PW8tJ) (JEDI VCL requared)
## Post #18
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-09-03T20:16:22+00:00
- Post Title: Re: PSP MediEvil Resurrection .BIN

Hey, guys. Check out this topic about modding and translating MediEvil Resurrection --> [https://forum.xentax.com/viewtopic.php?f=32&t=18772](https://forum.xentax.com/viewtopic.php?f=32&t=18772)
## Post #19
- Username: Izerantas
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 08, 2021 9:38 pm
- Post datetime: 2021-01-08T14:05:16+00:00
- Post Title: Re: PSP MediEvil Resurrection .BIN

> Reply from ViToTiV ↑Sat Nov 04, 2017 6:35 pm at Sat Nov 04, 2017 6:35 pm
>
> 
aluigi, your script is not complete. Archive is more complicated than it seems at first.
My utility for FULL unpack and FULL repack "gamedata.bin" - https://mega.nz/#!Q9cGFJ7I!cO9RX4wzNsZr ... A_w7ulp1w8
Fonts in "01-global.group.toc_ex\00491.psm" - "01-global.group.toc_ex\00501.psm" files (metric in BIN files)
Text in *.LTR  files
maybe, this will help to someone

I've been looking everywhere for a link to your tool lol. Thanks for the amazing work! Could you update the link? I'm trying to get all the sound files from the bin but I only managed to get to 37% unpacking with quickbms
