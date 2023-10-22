## Post #1
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-09-24T08:58:19+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

please create script  
___________________
i have information about this but i dont know how to make plug-in

> 10. Data Files Structure
>
> ------------------------
>
> The structure of the data files are the same in all three of the Power of Chaos
>
> games. There two files in which all of the information is stored:
>
> 
>
> data.dat - everything except sound data (text files [*.txt], bitmaps [*.bmp],
>
>            opponent decks [*.ydc], etc.)
>
> Voice.dat - sound data (sound effects, music, and voice-overs [*.wav])
>
> 
>
> Both of them operate the same way:
>
> Offset:                 Purpose:
>
> 0-7 (8 bytes)           a tag acknowledging that the file is from Power of
>
>                         Chaos
>
> 8-11 (4 bytes)       (edited)   NUMBER OF FILES
>
> 12-279 (268 bytes each) individual file information
>
>  280-547
>
>  ...
>
>  etc.
>
> the rest                file contents
>
> 
>
> Individual file information segments consist of four parts: filename (bytes
>
> 0-255), file starting offset (256-259 bytes), uncompressed size(?) (bytes 260-
>
> 263), and compressed (in-file) size (264-267 bytes). The procedure for
>
> extracting this information goes as follows:
>
> 
>
> filename
>
> --------
>
> swap the hexadecimal values of each byte and chop off the trailing zeros
>
> 
>
> NUMBER OF FILES,file offset, uncompressed size(?), and compressed size
>
> ------------------------------------------------------
>
> byte0 + 256^1 * byte1 + 256^2 * byte2 + 256^3 * byte3
>
> 
>
> Using the file starting offset and compressed size, you can easily pull out the
>
> file information. How the files are compressed is unknown (toss me an e-mail if
>
> you figure it out), but most of the files are stored uncompressed, so this
>
> isn't too much of a problem.
>
> 
>
> By the way, I've slapped together a small program that does all of this:
>
> http://crispymarshmallow.home.comcast.net/unpacker.exe (needs Microsoft .NET
>
> Framework 2.0)
>
> 
>
> Some stuff you might want to look at:
>
> data.dat:
>
> \card\*.bmp - card images
>
> \?\file\*.ydc - the opponent's decks (? = y, k, or j)
>
> 
>
> voice.dat:
>
> everything - all game audio is at your disposal
i have unpacker.exe but it cant uncompress or add files

other extractor:[download](http://yugiohextractor.sourceforge.net/Yu%20Gi%20Oh!%20File%20Extractor%201.0.zip)-------[source](http://yugiohextractor.sourceforge.net/Yu%20Gi%20Oh!%20File%20Extractor%201.0%20SourceCode.zip)------- [documentation](http://yugiohextractor.sourceforge.net/documentation.htm)
[unpacker.rar](https://xentaxbackup.github.io/file/867_unpacker.rar)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-24T12:57:41+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

i that case i recommend the "injection" techique, you can do with naeder or filestripper
## Post #3
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-09-24T16:40:33+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

how to uncompress theese
[files.rar](https://xentaxbackup.github.io/file/868_files.rar)
## Post #4
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-09-24T16:47:26+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

image
[unpacker.jpg](https://xentaxbackup.github.io/file/870_unpacker.jpg)
## Post #5
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-09-25T07:30:43+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

Looks like rle, maybe LZ77 or something. Only looked briefly
## Post #6
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-09-25T12:13:39+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

i found this rle decompression script but i don't know what to do with this

> while InputPos < InputSize do
>
> begin
>
> RunLength := Input[InputPos++]
>
> if RunLength = 0 then
>
> begin
>
> Count := Input[InputPos++]
>
> for i := 1 to Count do
>
> Output[OutPos++] := Input[InPos++]
>
> end
>
> else
>
> begin
>
> Symbol := Input[InputPos++]
>
> for i := 1 to RunLength do
>
> Output[OutPos++] := Symbol
>
> end
>
> end

----------------------------------------------

lob065-.bmp:      compressed size 139144
                        uncompressed size 174056
                         i took it from data.dat with unpacker.exe

lob065.bmp:       it's lob065-.bmp uncompressed
                        i took it from older game version
[card.rar](https://xentaxbackup.github.io/file/872_card.rar)
## Post #7
- Username: TightIsRight
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 23, 2006 12:54 pm
- Post datetime: 2006-09-26T02:51:40+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

Found this on sourceforge.net

```
http://sourceforge.net/projects/yugiohextractor
```


An application that can extract, replace and view the files as cards, sound effects and music from the Yu Gi Oh! Power of Chaos PC games. It is written in C# .NET. Aplicaciï¿½n que puede extraer y manipular los archivos de YuGiOh Power of Chaos, cartas,etc.

Translations : English, Spanish
## Post #8
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-09-26T12:24:31+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

> Reply from TightIsRight
>
> Found this on sourceforge.net
Code: Select allhttp://sourceforge.net/projects/yugiohextractor

An application that can extract, replace and view the files as cards, sound effects and music from the Yu Gi Oh! Power of Chaos PC games. It is written in C# .NET. Aplicaciï¿½n que puede extraer y manipular los archivos de YuGiOh Power of Chaos, cartas,etc.

Translations : English, Spanish
it can't uncompress either  
---------------
Tell me if you need more information
## Post #9
- Username: TightIsRight
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 23, 2006 12:54 pm
- Post datetime: 2006-09-26T21:09:33+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

Oh... I forgot that this forum is all about uncompressing things, not editing them.
## Post #10
- Username: smernesto
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 05, 2006 6:47 am
- Post datetime: 2006-12-04T22:50:51+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

Hi.

I am the creator of yu gi oh extractor, I was reading the forum.

If you have more information about how works the files in the game please write me at [udprogramacion@yahoo.com](mailto:udprogramacion@yahoo.com).

I never knew how read the text files in the game. 

Bye

Ernesto Gutierrez Arrazola
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2007-01-11T22:17:48+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

The compression algorithm is the same used by the games Chaser, KOTT2 and Conan for their files.
I don't know its name for the moment anyway the following is the C code of the unpacking function I have reversed from Chaser:

int unpack(u_char *out, int outsz, u_char *in, int insz) {
    u_short i,
            c,
            zg,
            num,
            e14 = 0,
            zp  = 0xfee;
    u_char  *p,
            *inx,
            *outx;
    static u_char   zmem[0x1000];

    p    = out;
    inx  = in  + insz;
    outx = out + outsz; 
    memset(zmem, 0x20, sizeof(zmem));

#define CGET    if(in == inx) break;    \
                c = *in++;
#define CPUT    if(p == outx) break;    \
                *p++ = c;
#define ZGET    c = zmem[(zg + i) & 0xfff];
#define ZPUT    zmem[zp] = c;           \
                zp = (zp + 1) & 0xfff;

    for(;;) {
        for(;;) {
            e14 >>= 1;
            if(!((e14 >> 8) & 1)) {
                CGET
                e14 = c | 0xff00;
            }
            if(!(e14 & 1)) break;
            CGET
            CPUT
            ZPUT
        }
        CGET
        zg  = c;
        CGET
        zg |= (c & 0xf0) << 4;
        num = (c & 0x0f) + 2;
        for(i = 0; i <= num; i++) {
            ZGET
            CPUT
            ZPUT
        }
    }

#undef CGET
#undef CPUT
#undef ZGET
#undef ZPUT

    return(p - out);
}
## Post #12
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2007-04-05T16:21:19+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

BMS

ImpType Standard;
IDString 0 KCEJYUGI;
Get RN Long 0;
For T = 1 To RN;
SavePos N 0;
Math N += 256;
GoTo N 0;
SavePos FOO 0;
Get FO Long 0;
SavePos FSO 0;
Get FS Long 0;
SavePos UFSO 0;
Get UFS Long 0;
Log T FO UFS FOO UFSO;
Next T;

But still it cant show filenames

> The file name is illegible since they invert the first 4 bits with the last 4 bits of each character, or it can be described as a rotation of 4 bits toward the left or the same thing a rotation of 1 bit, 4 times toward the left. To make it llegible the inverse process should be made and rotate the bits 4 times toward the right. For example if we have the byte 0x4A (01001010) when rotating it 4 times to the right it would be 0xA4(10100100). 
>
> 
>
> Step for step would be this way: (0x4A)01001010 -> 00100101 -> 10010010 -> 01001001 -> 10100100(0xA4) 
>
> 
>
> Immediately after having finished all the file descriptions, they follow the data of each one of the files.

> filename 
>
> -------- 
>
> swap the hexadecimal values of each byte and chop off the trailing zeros
## Post #13
- Username: Xtrmntr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 01, 2009 12:36 am
- Post datetime: 2009-01-31T17:06:49+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

Hello, I am new here! I wanted to add god cards to Joey the passion, but I find out I must have "Yu-gi-oh! power of chaos file extractor", so I downloaded it! I have some problems with it  , so if someone can help me, here goes: I turn on My Yu-gi-oh! File Extractor.exe and I get following:Yu-gi-oh! File Extractor.exe - Aplication error 
The application failed to initialize properly (0x0000135). Click on OK to terminate the application. 
If anyone knows what is the problem, PLEASE HELP!!
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-01T10:42:40+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

> Reply from smernesto
>
> Hi.

I am the creator of yu gi oh extractor, I was reading the forum.

If you have more information about how works the files in the game please write me at udprogramacion@yahoo.com.

I never knew how read the text files in the game. 

Bye

Ernesto Gutierrez Arrazola

Better is that the information is posted here for all to read and work with.
## Post #15
- Username: Rancher
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 22, 2015 11:00 am
- Post datetime: 2015-06-22T03:08:10+00:00
- Post Title: Yu-Gi-Oh power of chaos all 3 versions *.dat files

I need help with decompiling the files inside .dat file of this game. I attached two .bin files with card descriptions: a binary and a decompiled one I found on Google (I don't know if the content is the same; this game has a lot of mods floating around the net), binary .txt files (I found a decompiled version of "list_card.txt" [here](http://www.scribd.com/doc/19964513/list-card)) and .yga one. Please help me decompile and recompile them back. Thank you in advance!
[YGO.zip](https://xentaxbackup.github.io/file/9327_YGO.zip)
## Post #16
- Username: Rancher
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 22, 2015 11:00 am
- Post datetime: 2015-06-22T03:08:10+00:00
- Post Title: Re: Yu-Gi-Oh power of chaos all 3 versions *.dat files

I need help with decompiling the files inside .dat file of this game. I attached two .bin files with card descriptions: a binary and a decompiled one I found on Google (I don't know if the content is the same; this game has a lot of mods floating around the net), binary .txt files (I found a decompiled version of "list_card.txt" [here](http://www.scribd.com/doc/19964513/list-card)) and .yga one. Please help me decompile and recompile them back. Thank you in advance!
[YGO.zip](https://xentaxbackup.github.io/file/9327_YGO.zip)
## Post #17
- Username: admirzuza
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 03, 2010 12:38 am
- Post datetime: 2015-08-12T20:33:26+00:00
- Post Title: Re: Yu-Gi-Oh power of chaos all 3 versions *.dat files

how to compress files back after decompressing?

decompression works fine, but compression doesnt work (several bytes are missing)

in attached zip file u will find original compressed file (card_desceng_compressed), file after being decompressed (card_desceng_decompressed), and file being compressed back again but with different size thn original (card_desceng_compress2)..

NOTE: nothing has been changed inside files during compression/decompression

thanks  
[card_desceng.zip](https://xentaxbackup.github.io/file/9523_card_desceng.zip)
## Post #18
- Username: chuckthetekkie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 13, 2017 12:14 am
- Post datetime: 2017-08-12T19:15:48+00:00
- Post Title: Re: Yu-Gi-Oh power of chaos all 3 versions *.dat files

I know this is an old thread but does anyone know how to extract/decompress/decrypt the *.yga files? *.ygc?
## Post #19
- Username: kiemkhach
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 18, 2023 3:07 am
- Post datetime: 2023-05-20T16:53:58+00:00
- Post Title: Re: Yu-Gi-Oh power of chaos all 3 versions *.dat files

Hi!, I know this is an old thread but recently I found the perfect compress and uncompress functions. I found it on a guy's github called "pku-translation" for another game, luckily his algorithm works fine for YGO-POC (seems like these 2 games have the same development team), it is written in C#. link: [https://github.com/pku-translation/root ... se/LZSS.cs](https://github.com/pku-translation/rootdouble-CN/blob/master/CSYetiTools.Base/LZSS.cs)
I tried it on both list_card.txt and card_desceng.bin files. after uncompress and re-compress, the resulting file and the original fille are exactly the same.
## Post #20
- Username: kiemkhach
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 18, 2023 3:07 am
- Post datetime: 2023-05-20T17:04:46+00:00
- Post Title: Re: Yu-Gi-Oh power of chaos all 3 versions *.dat files

> Reply from smernesto ↑Tue Dec 05, 2006 6:50 am at Tue Dec 05, 2006 6:50 am
>
> 
Hi.

I am the creator of yu gi oh extractor, I was reading the forum.

If you have more information about how works the files in the game please write me at udprogramacion@yahoo.com.

I never knew how read the text files in the game. 

Bye

Ernesto Gutierrez Arrazola

Hi Ernesto Gutierrez Arrazola! I already read your code for yu gi oh extractor, It nice to understand.
I am trying to add new features for your app as "add new file to .data file", "replace file dont care file size", "un-compress and re-compress file"
