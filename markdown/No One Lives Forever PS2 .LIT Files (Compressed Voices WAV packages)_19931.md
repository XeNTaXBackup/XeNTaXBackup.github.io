## Post #1
- Username: Tgames
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 01, 2019 5:51 pm
- Post datetime: 2019-04-02T10:42:03+00:00
- Post Title: No One Lives Forever PS2 .LIT Files (Compressed Voices WAV packages)

Hi everyone !

Thanks again to aLuigi for the script to extract the PS2 REZ File !

But there is small issue on this script, it only extract the 1st block (english language) and not the others blocks (others languages)

I found that the voices WAV files are stored in all .LIT extracted files from the LITH_PS2.REZ

Here is some LIT examples files (extracted from LITH_PS2.REZ) : 

[https://we.tl/t-vXmwvd9qfa](https://we.tl/t-vXmwvd9qfa)

The PS2 NOLF REZ File (LITH_PS2.REZ) : 

[https://mega.nz/#!unQkVKDT!ygoH01WVA7r2 ... DLJdfOQqs4](https://mega.nz/#!unQkVKDT!ygoH01WVA7r2pRHq0VTQu7qnyRSsX3snHDLJdfOQqs4)

For faster download : LITH_PS2.REZ (7zip compressed 1,40gb only !)

[https://we.tl/t-4DTT772vdF](https://we.tl/t-4DTT772vdF)

The Script made by aLuigi : 

[http://aluigi.org/bms/nolf_ps2.bms](http://aluigi.org/bms/nolf_ps2.bms)

```
get FOLDER basename


get EXT extension
if EXT == "rez"

    math ALIGN = 0x800
    get DUMMY long  # 3
    get FILES long
    get DUMMY long  # 10
    get DATA_OFF long
    math DATA_OFF * ALIGN
    get DUMMY long  # 0x1fa
    padding ALIGN
    for i = 0 < FILES
        get NAME_CRC long
        get OFFSET long
        get SIZE long
        get XSIZE long
        math OFFSET * ALIGN
        math XSIZE  * ALIGN
		set NAME ""
		string NAME1 p "%s\%s" FOLDER NAME
        log NAME1 OFFSET SIZE
    next i

else

    get DUMMY short # 0xa3d
    for
        getdstring NAME 0x10
        if NAME == ""
		    string NAME1 p "%s\%s" FOLDER NAME
            break
        endif
        get SIZE long
        get OFFSET long
        get ZERO byte
		string NAME1 p "%s\%s" FOLDER NAME
        log NAME1 OFFSET SIZE
    next

endif

```


This script code need a small fix to also extract others languages.

I can see that all WAV voices files are named exactly the same as the PC Port.
As the PS2 version contains french voices (and not the PC port) i will use theses files to inject them in the PC port.
And we can see the ID « LithTech PSX Sound Data 1.20 »



They seems to be compressed i guess ?

About the PC Port (just to compare) :



The PC REZ File (just to compare, nothing has to be done on it, we already have everything !)
[https://mega.nz/#!uvIkiYqK!_cyAbfaH6O9F ... bh1MOckJX4](https://mega.nz/#!uvIkiYqK!_cyAbfaH6O9FaG9KDaZZ6S_uwJeN-YfWLbh1MOckJX4)

Can someone on the "Audio and Video file formats" section check if the WAV are in the .LIT files and what compression is used (if there is a compression) ?

Thanks a lot !

I managed to read every voices in theses .LIT files.

1) Download PSounds
here :[http://snailrush.online.fr/PSound/PSound201.zip](http://snailrush.online.fr/PSound/PSound201.zip)

2) Open PSounds and go to "OPTIONS" -> "CONFIGURE"
Set "Sample Rate" to Force 16000Hz

3) Open Any .LIT files, and click "scan anyway" (it will first don't recognize the file then... magic every voices are viewable and readable !!! :O)

Can someone make a script to extract them ?

Now we are sure there are in theses files and we are able to read all of them !

Edit:  Warning some WAV are not render in 16000Hz, you have to select "8000Hz" for some !

Edit 2:  It seems lot of .LIT files are missing in the first extract of the LITH_PS2.REZ.
I only got the english voices in this export (it's seems !)

Edit 3: After first analyse :

- LITH_PS2.REZ is separated in 5 blocks :

1st block is english language only
2nd block is another language
3nd block is another language
4nd block is another language
5nd block is another language

The Script of aluigi only extract the 1st block (english only) for now.

The languages are (English/French/Deutsch/Espagnol/Italiano).

LITH_PS2.REZ : 

[https://mega.nz/#!unQkVKDT!ygoH01WVA7r2 ... DLJdfOQqs4](https://mega.nz/#!unQkVKDT!ygoH01WVA7r2pRHq0VTQu7qnyRSsX3snHDLJdfOQqs4)

All .LIT files contains Sounds Effects and Voices.
In 1 .LIT file is always the same language (if the lit is french, we will have always french voices in this LIT).

LIT file contains multiple WAV file at different Sample Rate <!>. In a same LIT file you can have 16000Hz,  10000hz, 8000hz... It's never the same Sample Rate.

Edit 4: 

To aLuigi,

Indeed only 30% of the REZ file is extracted, lot of files are not extracted for now.

I have extracted myself some WAV Voices file from LIT files on the LITH_PS2.REZ.

Theses LIT files were not extracted with your script
It's some french voices.

[https://we.tl/t-5CfPCVCnPN](https://we.tl/t-5CfPCVCnPN)

If it can help.
## Post #2
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-04-03T00:25:01+00:00
- Post Title: No One Lives Forever PS2 .LIT Files (Compressed Voices WAV packages)

If you are looking for a place to put these up, I suggest The Sounds Resource.
