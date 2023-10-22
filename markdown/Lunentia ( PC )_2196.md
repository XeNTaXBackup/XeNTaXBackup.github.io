## Post #1
- Username: Chris Christian
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 12, 2006 2:15 pm
- Post datetime: 2006-11-12T06:52:43+00:00
- Post Title: Lunentia ( PC )

Hi, can you add support for some of the Lunentia resource files?

The file types in this case are:

.MAK -> I think this is some type of animated image file, maybe TGA 32bit or BMP

.MCK - > This is some type of 32bit compressed TGA

.SKL -> Data compressed, maybe some type of CSV file or something, with the information

.MDL -> Same as SKL I think

There are some more file types, but for now this is good.

Examples are in the Attachment. Thank you very much.
[lunentia.rar](https://xentaxbackup.github.io/file/967_lunentia.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-11-12T18:17:20+00:00
- Post Title: Lunentia ( PC )

MDL tends to refer to model data. Or even a module music file.

[http://filext.com/detaillist.php?extdet ... rch=Search](http://filext.com/detaillist.php?extdetail=MDL&Search=Search)

I'll see if I can check it.

Well, MAP.MDL would assume it is well... a map.

Inside it proves it, it has several references to "TEX" (Texture) "GDS" "FOBJ" "MOBJ"  (OBJ refers to Object, F and M... Female and Male? XD) "MAP" (Map Data?) "CBX" "MCK" "BTD" and "LTS"

The MAK file IS an image. Even though it does not seem to be compressed, I cannot open it as of yet.

CharacterMake.MCK is an even clearer image. Also not sure as of yet here.

The SKL file seems to be well... Skill data.

Thats what I've determined.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-12T19:19:11+00:00
- Post Title: Lunentia ( PC )

CharacterMake.MCK is a TIFF file, without the header. The file starts with Width and Height and some unknown variable. 

```
// MCK format

uint32     Width
uint32     Heigth
uint32     Unknown

//

byte[n]    Image data, in CMYK format, size = Width * Heigth * 4 (CMYK) uncompressed


```


I copied the data into a TIFF template header and then viewed it. Seems to work, but I had to invert the colours to see it better. Probably because I'm missing some of the correct header variables. Nevertheless, it works. 
See attachment.
[character.jpg](https://xentaxbackup.github.io/file/972_character.jpg)
## Post #4
- Username: Chris Christian
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 12, 2006 2:15 pm
- Post datetime: 2006-11-12T20:10:28+00:00
- Post Title: Lunentia ( PC )

WoW, you guys are the best!

Well, can .MAK and .MCK be added? If possible, thanks very much!
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-12T20:37:38+00:00
- Post Title: Lunentia ( PC )

Well, what I did was very low level, and guesswork. There are still unknowns here. You should post this question also in the Graphics forum perhaps.
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-13T10:05:22+00:00
- Post Title: Lunentia ( PC )

hehehe. what i see is a 32Bit TGA file without header.

this is pretty easy stuff. if someone want i can write a converter for this
filetype in ......lets say.......3 minutes.
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-13T14:03:33+00:00
- Post Title: Lunentia ( PC )

MCK and SKL reader and converter now integrated into jaeder naub.

The SKL file was a bunch of 32x32 Raw images.

(and other data that was not graphics, possibly gamedata
for how the skills are configured).

im still analyzing the other files, i release this compile later today.
## Post #8
- Username: Chris Christian
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 12, 2006 2:15 pm
- Post datetime: 2006-11-13T19:52:28+00:00
- Post Title: Lunentia ( PC )

> Reply from Strobe
>
> MCK and SKL reader and converter now integrated into jaeder naub.

The SKL file was a bunch of 32x32 Raw images.

(and other data that was not graphics, possibly gamedata
for how the skills are configured).

im still analyzing the other files, i release this compile later today.

Oh, thank you very very much!
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-14T15:43:00+00:00
- Post Title: Lunentia ( PC )

[http://jaedernaub.ath.cx/jn2internal.zip](http://jaedernaub.ath.cx/jn2internal.zip)

So. preliminary SKL and MCK support added. just make sure to have those enabled on Option Screen, and press save.

then you should be able to load these files and scan them,
when identified they will be automatically converted to TGA.

but i only have tested this briefly as i have only 1 MCK and 1 SKL file ;D
