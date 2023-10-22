## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-14T14:51:23+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

i tried to wrote a script for a simple 3d game:
[http://www.gametop.com/download-free-games/magic-pets/](http://www.gametop.com/download-free-games/magic-pets/)
when i open the data.000 archive in hex editor i saw 
```

```


```
  16: 000 000 000 000 000 000 000 000 000 000 005 000 000 000 070 111  ..............Fo 
  32: 110 116 047 080 075 003 004 010 000 000 000 000 000 202 129 076  nt/PK........ÊL 
  48: 049 182 223 173 206 101 017 000 000 101 017 000 000 013 000 000  1¶ß­Îe...e...... 
  64: 000 070 111 110 116 047 098 105 103 046 102 111 110 116 115 099  .Font/big.fontsc 
  80: 097 108 101 032 048 046 055 013 010 097 099 116 105 118 101 108  ale 0.7..activel 
  96: 101 116 116 101 114 115 013 010 123 032 013 010 045 049 032 045  etters..{ ..-1 - 
 112: 049 032 045 049 032 045 049 032 045 049 032 045 049 032 045 049  1 -1 -1 -1 -1 -1 
 128: 032 045 049 032 013 010 045 049 032 045 049 032 045 049 032 045   -1 ..-1 -1 -1 - 
 144: 049 032 045 049 032 045 049 032 045 049 032 045 049 032 013 010  1 -1 -1 -1 -1 .. 
 160: 045 049 032 045 049 032 045 049 032 045 049 032 048 032 049 032  -1 -1 -1 -1 0 1  
 176: 050 032 051 032 013 010 052 032 053 032 054 032 055 032 056 032  2 3 ..4 5 6 7 8  
 192: 057 032 049 048 032 049 049 032 013 010 049 050 032 049 051 032  9 10 11 ..12 13  
 208: 049 052 032 049 053 032 049 054 032 049 055 032 049 056 032 049  14 15 16 17 18 1 

```

indeed it is a zip compressed method !
and immediatly i excute an zip binary tempelate on it , you see the conclude on screenshot !
they are imperfect zips ! because when i trimed one of them and save it as zip , it was damaged !
so that , i confused for writing .bms , i hope teachers guide me at this condition ?
sincerely 
[pet.jpg](https://xentaxbackup.github.io/file/2103_pet.jpg)
## Post #2
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-14T15:01:21+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

excuse me all !
i am so foolish !  
the archive opened by winrar !
i sorry  that i released a useless topic
## Post #3
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-14T15:15:51+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

i will choose another game for this topic 
the reason of this mistake is that i swamped on applying a comtype command for this pak and  i forgot to did a simple rename test !!!!!!!
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-14T15:33:48+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

usually it's not needed to rename the files, just open them directly with 7-zip and if they are a known compressed format the job is done (like in this case)
## Post #5
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-18T13:11:13+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

hi all , again
when i survey net to find an archive for BMS exercise , i encounterd an attractive screen saver !
and tried to discover some codes !
this screen saver contains archives with .3dr extension !
each Actor of screen saver has a 3dr pack !
in fact each pack contains : 360 degree camera scaned images of the actress ! that compressed in some ways that i can't understand   
after instaling of screen saver you will find this packs at <system32>
[http://www.anything3d.com/product/softw ... index.php3](http://www.anything3d.com/product/software/screen/index.php3)
i showd my progress in this binary template :

```
char key[10];
unsigned int offset;
unsigned int frames;
unsigned int block;
unsigned int ukn1;
unsigned int ukn2;
unsigned int ukn3;
unsigned int ukn4;
unsigned int w;
unsigned int h;
unsigned int ukn5;
unsigned int ukn6;           
} header;
struct fra {
struct pat {
char rgb[3];
}pattern[header.block];
}frame[header.frames];
```

you can download a sample 3dr from :
[http://filekeeper.org/download/shared/Vika.zip](http://filekeeper.org/download/shared/Vika.zip)
----------------------------------------------
I hope masters show me how should judge at this condition ?
----------------------------------------------
sincerely
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-18T17:01:22+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

the following is the BMS script for extracting the 3dr files with quickbms:

```
idstring "3DR\0"
goto -12
savepos MAX_OFFSET

get INFO_OFFSET long
math INFO_OFFSET *= -1
goto INFO_OFFSET
savepos INFO_OFFSET

set FILES long MAX_OFFSET
math FILES -= INFO_OFFSET
math FILES /= 4

get OFFSET long
for i = 1 <= FILES
    if i == FILES
        set NEXT_OFFSET long MAX_OFFSET
    else
        get NEXT_OFFSET long
    endif

    set SIZE long NEXT_OFFSET
    math SIZE -= OFFSET

    log "" OFFSET SIZE

    set OFFSET long NEXT_OFFSET
next i
```
## Post #7
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-20T05:53:53+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

bugtest you are very wonderful   
how you could recognize the structure , rapidly ?
 
sincerely , brilliant bugtest
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-20T07:30:12+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

the archive begins directly with a bitmap file so the only other location where was possible to find the index table was at the end.
so here we find the size of the index (which includes also this 12 bytes header), a number which I have not verified and the "3DR\0" signature.
figuring the index was easy because they contain only the offsets of the files, indeed I found them simply searching the offset of the second bitmap inside the whole archive and it confirmed the offset-only table theory.
## Post #9
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-20T08:07:38+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

they are jfif image sequence
this is the first time , i encounter with this file format ! 
APPLAUD
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-21T20:41:38+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

Hey shekofte, where are the other pictures?
## Post #11
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-22T09:37:24+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

excuse me boss , whether i had vandalism here ?
are you angry from me ?
i assumed they are common !
## Post #12
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-22T11:34:58+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

@bugtest ,forgive me too ,computer is not my main job , it is only a gamble for me, web is a great delight  and  i am a little playful 
i see you ,like a friend on the other half of world , i never forget your donations and the time spended for me
i dont know how you see me ,but like it i annoied you in a reverse way !
anyway , i should be careful on this community
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-22T13:58:29+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

personally I like to figure the formats of the games so everything is positive when there are new formats to reverse and (most important) I figure them and moreover correctly :)
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-22T15:36:05+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

> Reply from shekofte
>
> excuse me boss , whether i had vandalism here ?
are you angry from me ?
i assumed they are common !

Huh? No, I am not angry. Not at all! I was just wondering why you stopped posting those pictures. You were just getting to the good part . I was joking.
## Post #15
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-07-20T09:29:06+00:00
- Post Title: writing a .bms for a frreware 3d game: magic pets

the structure that applied in these two game are the same :
[http://www.gametop.com/download-free-games/city-racing/](http://www.gametop.com/download-free-games/city-racing/)
[http://www.gametop.com/download-free-ga ... ro-racing/](http://www.gametop.com/download-free-games/quadro-racing/)
[](http://xs.to)

the offset and size of each file in the .pak archive keeped in its corresponding .hdr header file !
how is the routine when we must write a  BMS for pair files (like this case) ?

[](http://xs.to)
BLUE : fixed characters
GOLD : unknown
GREEN : size
RED : offset
-----------------
i attached one of headers !
thanks dear for your guides  
[Textures.rar](https://xentaxbackup.github.io/file/2212_Textures.rar)
## Post #16
- Username: shekofte
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-20T11:42:26+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

The null-terminated filenames have extremely easy encryption. Remember that filenames usually have the structure: name.ext
So clearly, 

```
C4 E1 F4 E1 AF C5 E6 E5 E3 F4 F3 AF C2 EC EF EF E4 F3 AF C2 EC EF EF E4 AE E4 E4 F3 00
```
 is one filename. The last 4 characters: AE E4 E4 F3 are then the dot + extension. A dot (.) = 2E hex. Here it is AE. The difference is 80 hex (128 dec). Could it be that simple? Yes it is:

```

```


Simply subtract 128 from each byte and you get the correct ASCII code for the filename. LOL!
## Post #17
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-07-21T07:57:09+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

thanks DR Mike
it was like honey
## Post #18
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-27T09:11:21+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

i will to decompress the archives of this online game , gratitude for your help !
[http://hp.wildgames.com/games/puppy-luv](http://hp.wildgames.com/games/puppy-luv)
i uploaded one of its archive !
[3DProps.rar](http://uploadmb.com/dw.php?id=1256634085)
## Post #19
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-15T14:01:05+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

the archives  of these two games are similar : ( .grp format )
[http://www.gametop.com/download-free-games/star-sword/](http://www.gametop.com/download-free-games/star-sword/)
[http://www.gametop.com/download-free-ga ... dly-stars/](http://www.gametop.com/download-free-games/deadly-stars/)

first i assumed the structure is simple , but when i tried  to figure how the file directories are formed , i can't discover any rule for it !
and this is my last effort :

game : DeadlyStars

```
for i = 0 < 1286
get pad long

if pad < 3
get pad long
GetDString folder pad
get pad long
if pad == 0
get pad long
if pad == 1
set pad 14
Elif pad == 2
set pad 14
Elif pad == 4
set pad 26
Elif pad == 18
set pad 15
Elif pad == 5
set pad 14
else
set pad 18
endif
GetDString folder pad
endif
get pad long
endif

GetDString NAME pad
get off long
get size long
log NAME off size
next i
```


output :

```
  0256b320 16512      powerbull lazer.dds
  0256f3a0 622        powerbull lazer.x
  0256f60e 16512      rocets.dds
  0257368e 4224       rocetsnuke.dds
  0257470e 3102       rocket1.x
  0257532c 4876       rocket2.x
  02576638 9032       rocket3.x
  02578980 1110       rocket_small.x
  02578dd6 16512      scorpion lazer.dds
  0257ce56 612        scorpion lazer.x
  0257d0ba 2600       swarm.x
  0257dae2 4224       termit lazer.dds
  0257eb62 637        termit lazer.x
  0257eddf 75         bomb.lbm
  0257ee2a 89         boss1 lazer.lbm
  0257ee83 83         boss3 lazer.lbm
  0257eed6 83         boss4 lazer.lbm
  0257ef29 89         bullet rose.lbm
  0257ef82 86         crab lazer.lbm
  0257efd8 85         discharge.lbm
  0257f02d 87         laser blue.lbm
  0257f084 89         laser green.lbm
  0257f0dd 85         laser red.lbm
  0257f132 88         lazer1_mod1.lbm
  0257f18a 88         lazer1_mod2.lbm
  0257f1e2 88         lazer1_mod3.lbm
  0257f23a 88         lazer1_mod4.lbm
  0257f292 88         lazer1_mod5.lbm
  0257f2ea 88         lazer2_mod1.lbm
  0257f342 88         lazer2_mod2.lbm
  0257f39a 88         lazer2_mod3.lbm
  0257f3f2 88         lazer2_mod4.lbm
  0257f44a 88         lazer2_mod5.lbm
  0257f4a2 88         lazer3_mod1.lbm
  0257f4fa 88         lazer3_mod2.lbm
  0257f552 88         lazer3_mod3.lbm
  0257f5aa 88         lazer3_mod4.lbm
  0257f602 88         lazer3_mod5.lbm
  0257f65a 88         lazer4_mod1.lbm
  0257f6b2 88         lazer4_mod2.lbm
  0257f70a 88         lazer4_mod3.lbm
  0257f762 88         lazer4_mod4.lbm
  0257f7ba 88         lazer4_mod5.lbm
  0257f812 88         lazer5_mod1.lbm
  0257f86a 88         lazer5_mod2.lbm
  0257f8c2 88         lazer5_mod3.lbm
  0257f91a 88         lazer5_mod4.lbm
  0257f972 88         lazer5_mod5.lbm
  0257f9ca 82         nuke.lbm
  0257fa1c 88         panter lazer.lbm
  0257fa74 91         powerbull lazer.lbm
  0257facf 58         rocket1.lbm
  0257fb09 58         rocket2.lbm
  0257fb43 81         rocket3.lbm
  0257fb94 68         rocket_small.lbm
  0257fbd8 90         scorpion lazer.lbm
  0257fc32 61         swarm.lbm
  0257fc6f 88         termit lazer.lbm
  0257fcc7 686        long laser.x
  0257ff75 4224       long_lazer.dds
  02580ff5 106        long laser.lbm
  0258105f 225        comet.lbm

- 1286 files found in 2 seconds

D:\quickbms>
```


I get a really bad headache on this enigma   
I am very eager to know , how do you will write a script for this satanic format ?
i attached the "DeadlyStars" table index !
thanks for dedication of your valuable time !
[table.rar](https://xentaxbackup.github.io/file/2614_table.rar)
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-15T14:10:16+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

Hey , shekofte, you wrote that BMS yourself? Nice!
## Post #21
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-15T14:58:47+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

yes sure , so far , you thought i am dullard ?
## Post #22
- Username: shekofte
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-15T15:03:45+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

Haha, no, but not many people can do that, so good job!
## Post #23
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-28T08:04:19+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

I wrote a 010 editor binary template that highlight variables in different colors , so that you can explore the structure easily !
as you see my script will checkmate after reading 1287 records !
where is my mistake ?
(this 40 mb archive is causes of obsession ! )

```
local unsigned int y=18;
struct folder {
uchar name[x];
};
struct pad {
uchar row[y];
};
FSeek(49);
for (i=0;i<1287
;++i){
SetColor(0x000000 , 0xb0ff00 );
unsigned int x;

if(x<3){
SetColor(0x000000 , 0xa000ff );
unsigned int x;
SetColor(0x000000 , 0xffe000 );
folder root;
SetColor(0x000000 , 0xffffff );
unsigned int x;

if(x==0){
SetColor(0x000000 , 0xff00ff );
unsigned int x;

if(x==1)y=14;
else if(x==5)y=14;
else if(x==2)y=14;
else if(x==18)y=15;
else if(x==4)y=26;
else
y =18;

SetColor(0x000000 , 0xffff00 );

pad sub;
}
SetColor(0x000000 , 0xa000ff );
unsigned int x;
}

SetColor(0x000000 , 0xdfa000 );
folder path;
SetColor(0x000000 , 0x00d0ff );
unsigned int offset;
SetColor(0x000000 , 0x00ffd0 );
unsigned int size;
}
```

[colourful.jpg](https://xentaxbackup.github.io/file/2665_colourful.jpg)
## Post #24
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-28T08:43:34+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

other games that developed by programmer of this game : Star Defender
[http://www.mobygames.com/developer/shee ... Id,308059/](http://www.mobygames.com/developer/sheet/view/developerId,308059/)
Star Defender has a more entice style !   
[http://www.awem.com/star-defender-4.html](http://www.awem.com/star-defender-4.html)
## Post #25
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-28T17:47:12+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

the following is the quickbms script for Star Defender:

```

get VER short
get FILES long
for i = 0 < FILES
    get NAMESZ short
    filexor 0xcd
    getdstring NAME NAMESZ
    get OFFSET long
    get SIZE long
    filexor ""
    log NAME OFFSET SIZE
next i
```
## Post #26
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-28T18:06:09+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

VIVA Luigi
## Post #27
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-28T19:22:23+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

and the following is the quickbms script for the other 2 games you linked: DeadlyStars and StarSword

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

set PATH string ""
get VER long
callfunction extract

startfunction extract
    get NAMESZ long
    getdstring NAME NAMESZ
    string PATH += NAME
    string PATH += /

    get FILES long
    for i = 0 < FILES
        get NAMESZ long
        getdstring NAME NAMESZ
        get OFFSET long
        get SIZE long

        set FULLNAME string PATH
        string FULLNAME += NAME
        log FULLNAME OFFSET SIZE
    next i

    get FOLDERS long
    for i = 0 < FOLDERS
        callfunction extract
    next i
endfunction
```
## Post #28
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-28T20:48:52+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

thanks Luigi you are a real nobleman , this script is very informative for me ...
## Post #29
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-23T23:17:34+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

I would just like to applaud Aluigi for the efforts he puts into his work. Keep it up! Once I could produce many scripts, sadly those days are gone now.
## Post #30
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-24T15:43:43+00:00
- Post Title: Re: writing a .bms for a frreware 3d game: magic pets

> sadly those days are gone now
unfortunately that's normal for anyone.
that's why is necessary to "knuckle down" in the moments when this is possible (with the help of time and interest) because the future is ever uncertain...
