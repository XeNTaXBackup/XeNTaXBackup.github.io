## Post #1
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2007-03-10T07:42:38+00:00
- Post Title: Star Wars: Jedi Starfighter

i have unpack archives files.. and found one texture folder, with .TEX files
i tried to convert TEX to BMP, i have test some possibility and soft, but i think this is a variant ...
someone could help me ??

thx
[dagger5.rar](https://xentaxbackup.github.io/file/1084_dagger5.rar)
## Post #2
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2007-03-24T07:03:36+00:00
- Post Title: Star Wars: Jedi Starfighter

up .. nobody havea solution ?????
## Post #3
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-03-24T08:09:05+00:00
- Post Title: Star Wars: Jedi Starfighter

Hmm, well, just looking at it briefly, it would seem to be a texture of 128x128 in size, it's not compressed it seems, as 128x128 = 0x4000h, and it has a palette of 256 colours probably (256xRGBAlpha = 0x400). Together this is 0x4400h, the exact size of the texture data (starts at offset 0x14h). 

But I haven't looked throroughly enough as to type of texture.
## Post #4
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2007-03-24T10:25:48+00:00
- Post Title: Star Wars: Jedi Starfighter

i have test many convert tools , for .tex format.. but no one work ..
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-24T11:05:44+00:00
- Post Title: Star Wars: Jedi Starfighter

Starting from Mr.Mouse's description (though the palette comes first, so the texture data actually starts at 0x0414 ) and for a moment ignoring the alpha channel, as I currently only have a BMP writing library at hand, this is what I have got. I am not sure whether the palette orientation is BGR (on the left) or RGB (on the right).

So, there is not much to it, as already suspected.

Any thoughts?
[dagger5.jpg](https://xentaxbackup.github.io/file/1099_dagger5.jpg)
## Post #6
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2007-03-24T15:38:09+00:00
- Post Title: Star Wars: Jedi Starfighter

my god ..
excellent ...
i'm a noob about file description .. could  give me a small progam for convert .tex ??  please
## Post #7
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-24T17:40:48+00:00
- Post Title: Star Wars: Jedi Starfighter

Sure, test the attached program. Usage via the command line:

```
TEX2TGA *.tex
```

or similar ...

Im not sure about the alpha channel, though. The results look a bit weird to me, but then again, I do not know what this texture is supposed to represent. You will have to check that for yourself.

[Edit: attached updated version]
[TEX2TGA.zip](https://xentaxbackup.github.io/file/1100_TEX2TGA.zip)
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-24T18:08:30+00:00
- Post Title: Star Wars: Jedi Starfighter

Looks to me like it is supposed to be a ship.
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-24T18:34:21+00:00
- Post Title: Star Wars: Jedi Starfighter

> Reply from Darkfox
>
> Looks to me like it is supposed to be a ship.
I thought that too, but the black parts of the image are marked as opaque, while everything else (also what I would interpret as metal) is attributed a value somewhere in the middle ranges. Thus, even turning the scale upside down does not make much sense.

Interesting fact: The palette seems to be sorted by what I have presumed to be the alpha value. I'm not sure whether this has some importance.
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-24T19:34:37+00:00
- Post Title: Star Wars: Jedi Starfighter

I also noted that in the example picture you displayed the right image seemed to have correct skin tone for the pilot's face. Hm. Games and their odd formats, no?
## Post #11
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-24T23:10:51+00:00
- Post Title: Star Wars: Jedi Starfighter

Maybe the right example uses the correct colour sequence. I am still not sure about that ...
But you are right, games tend to have have very odd formats. I am actually quite grateful for the current trend towards the use of standardized file formats.
## Post #12
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2007-03-25T09:26:34+00:00
- Post Title: Star Wars: Jedi Starfighter

> Reply from Deniz Oezmen
>
> Sure, test the attached program. Usage via the command line:
Code: Select allTEX2TGA *.tex
or similar ...

Im not sure about the alpha channel, though. The results look a bit weird to me, but then again, I do not know what this texture is supposed to represent. You will have to check that for yourself.

wooww
all working perfectly... except, le blue channel must be the red .. i think ...
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-25T10:05:53+00:00
- Post Title: Star Wars: Jedi Starfighter

> Reply from CZW
>
> all working perfectly... except, le blue channel must be the red .. i think ...
Okay, that probably settles our discussion. 
See the above post, I have updated the attachment accordingly.
## Post #14
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2007-03-25T16:38:36+00:00
- Post Title: Star Wars: Jedi Starfighter

perfect work, congratulations !!!!!!!!

now, the color is perfect..
cuz see a havoc blue isn't logical, now is red as usual ....
[havoc_256_blue.tex.jpg](https://xentaxbackup.github.io/file/1103_havoc_256_blue.tex.jpg)
## Post #15
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2007-03-25T16:44:35+00:00
- Post Title: Star Wars: Jedi Starfighter

now the right color .. red
[havoc_256.tex.jpg](https://xentaxbackup.github.io/file/1104_havoc_256.tex.jpg)
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-12-15T05:38:52+00:00
- Post Title: [PS2] Star Wars: Jedi Starfighter (.tex)

here is Noesis python script to open the PS2 Jedi Starfighter tex files.  


 tex_StarWarsJediStarFighter_PS2_tex.zip
(676 Bytes) Downloaded 27 times




and here is a bms script to extract files from the PS2 pak archives and pmdl files.  

```

get FOLDER basename
idstring "Europa Packfile"
goto 0x15
get TABLE_OFFSET long
get TABLE_SIZE long
get FILES long
goto TABLE_OFFSET
for i = 0 < FILES
    get STR_SIZE byte
    get FNAME string
    get OFFSET long
    get SIZE long
    get HASH long
    string NAME p "%s\%s" FOLDER FNAME
    log NAME OFFSET SIZE
    savepos OFFSET
    goto OFFSET
next i

```

sfdepak works too but i prefer to use the script.
