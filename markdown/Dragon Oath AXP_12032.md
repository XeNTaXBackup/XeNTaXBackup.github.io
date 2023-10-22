## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-01T02:05:49+00:00
- Post Title: Dragon Oath AXP

Hello guys, well after check a lot topics I got BMS Script for unpack files but really no work anymore, sure the files change or something because bms script no work anymore, so somebody can take a look into files? ok I hope somebody can take a look into files and give a small help, here I leave samples + old bms script, thanks a lot guys.

Web: [http://tl.changyou.com/](http://tl.changyou.com/)
Download: [http://tl.changyou.com/download/index.shtml](http://tl.changyou.com/download/index.shtml)

Format: AXP

too leave source code of AXP Unpacker I found, is chinese tool, but the problem is only can unpack one file per time, is not possible select all of them, so maybe somebody can build it for unpack all files from one time?

APXUnpacker Source:

[http://puu.sh/bULiM/546044ba4f.7z](http://puu.sh/bULiM/546044ba4f.7z)

Samples:

[http://puu.sh/bULqs/81a5a374a7.7z](http://puu.sh/bULqs/81a5a374a7.7z)

BMS Script:

> #Dragon Oath AXP extractor 
>
> #quickbms script 
>
> #by Tsukihime 
>
> 
>
> get idstring long 
>
> get unk1 long 
>
> get null long 
>
> get unk2 long 
>
> get offsetBlock long #this block gives the offsets and data sizes 
>
> get files long #includes the (list) block which holds all filenames and their data size 
>
> get unk3 long 
>
> get startOffset long #not important, but the data for first file starts here. 
>
> get unk4 long 
>
> goto offsetBlock 
>
> savepos offsetPtr 
>
> 
>
> get folder basename 
>
> 
>
> #get the (list) offset 
>
> math temp = files 
>
> math temp -= 1 
>
> math temp *= 12 
>
> math temp += offsetBlock 
>
> 
>
> goto temp 
>
> get listOfs long 
>
> 
>
> #go to the first filename 
>
> goto listOfs 
>
> goto 9 0 SEEK_CUR 
>
> savepos listPtr 
>
> findloc newline string "\n" 
>
> math newline += 1 
>
> goto newline 
>
> savepos listPtr 
>
> #list pointer is now set 
>
> 
>
> for i = 0 < files 
>
> 
>
>    #======Get offset and size====== 
>
> 
>
>    goto offsetBlock 
>
>    get offset long 
>
>    get size long 
>
>    get unk long #always 0x0000008 
>
>    savepos offsetBlock #remember where we are 
>
> 
>
>    #======Get Filename============= 
>
>    #find the pipe character 0x7C 
>
>    goto listPtr 
>
>    findloc pipeOfs string "|" 
>
> 
>
>    #calculate string length 
>
>    math stringlen = pipeOfs 
>
>    math stringlen -= listPtr 
>
> 
>
>    #get the string name 
>
>    getdstring name stringlen 
>
> 
>
>    #update position of list pointer 
>
>    math listPtr = pipeOfs 
>
>    math listPtr += 19 
>
>    goto listPtr 
>
> 
>
>    #========save file=============== 
>
>    set outName = folder 
>
>    string outName += "/" 
>
>    string outName += name 
>
>   log outName offset size 
>
> next i
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-01T09:40:55+00:00
- Post Title: Dragon Oath AXP

[http://www.progamercity.net/game-files/ ... acker.html](http://www.progamercity.net/game-files/1672-dragon-oath-axp-unpacker.html)
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-01T16:08:38+00:00
- Post Title: Dragon Oath AXP

yeah I forget try with packer, but the packer allow to unpack too, is all in one tool, many thanks Ekey.
