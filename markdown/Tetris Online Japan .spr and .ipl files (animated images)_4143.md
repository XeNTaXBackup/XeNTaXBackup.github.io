## Post #1
- Username: dodd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 15, 2010 9:09 am
- Post datetime: 2010-02-15T09:32:55+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

I successfully figured out resource archive format. Most things inside are common format files, like wav, png. But i don't know how can i edit those animated files. SPR files start with 1RPS, IPL files start with 1LPI. Is this some common format or custom one? Format dosn't look very complicated so I think i can figure it out, but first i want to be sure this is not some common file format.

edit:
i mostly figured out this format (only .ipl part for now). Only problem was special encoding for empty spaces. anyway i still want to know if this is common format or not.

edit2:
i'm sorry, i was sure i'm posting this in graphics format section, please move.
[start_button.zip](https://xentaxbackup.github.io/file/2784_start_button.zip)
## Post #2
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-02-18T11:28:12+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

Send more files .spr and .ipl for comparing procedure. Thank's.
## Post #3
- Username: dodd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 15, 2010 9:09 am
- Post datetime: 2010-02-18T19:53:24+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

here are all files i unpacked from this game:
[http://bziumm.mooo.com/~wojtek/toj_res.zip](http://bziumm.mooo.com/~wojtek/toj_res.zip)

here is my source code for unpacking and rebuilding .ipl:
[http://bziumm.mooo.com/~wojtek/SprIpl_src.zip](http://bziumm.mooo.com/~wojtek/SprIpl_src.zip)
when rebuilding i don't use their empty space encoding, because i was too lazy.

i'm still interested in .spr files.

you can download this game from:
[http://www.tetrisonline.jp/toj/gmain/teco_top.aspx](http://www.tetrisonline.jp/toj/gmain/teco_top.aspx) .
this guide can be helpful if you don't know japanese:
[http://harddrop.com/forums/index.php?showtopic=1144](http://harddrop.com/forums/index.php?showtopic=1144)

here is game archive format if you are interested:
[http://harddrop.com/wiki/index.php?title=Sje.jhh](http://harddrop.com/wiki/index.php?title=Sje.jhh)
## Post #4
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-02-20T15:03:51+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

Here is my work "in progress" for SPR:

```
* HEADER OF SPR FILE *
**********************

4B	Char	M1	Magic string - "1RPS"
4B	Int32	C1	Count of action
4B	Int32	C2	Count of section
4B	Int32	L1	Length of one section
4B	Int32	L2	Length of one action
1B	Byte	U1	Unknown
1B	Byte	U2	Unknown
1B	Byte	U3	Unknown

4x4B	Int32	U4-U7	Unknown free

32B	String	S1	Name of animation	(Trim 00h)
128B	String	S2	Name of file of IPL contain image of animation (Trim 00h)

* Section
For I1 = 1 to C2
	L1	Section
Next I1

* Action
For I2 = 1 to C1
	L2	Action
Next I1

***********
* SECTION *
***********
32B	String	S3	Name of section	(Trim 00h)
2B	Int16		U8	?
2B	Int16		V1	Action number - start
2B	Int16		V2	Action number - finish
2B	Int16		V3	?
2B	Int16		V4	Count of action for this section
..	Empty

**********
* ACTION *
**********
2B	Int16		V5	Number of action
2B	Int16		U10	Image number
2B	Int16		U11	?
2B	Int16		U12	?
2B	Int16		U13	?
2B	Int16		U14	?
2B	Int16		U15	?
2B	Int16		U16	?
2B	Int16		U17	?
2B	Int16		U18	?
2B	Int16		U19	?
2B	Int16		U20	?
2B	Int16		U21	?
2B	Int16		U22	?
2B	Int16		U23	?
2B	Int16		U24	?

```

I searching actions marks (animations, moviment of picture, atd.)

The code for IPL is nearly complete.

```
* HEADER OF IPL FILE *
**********************

4B	Char	M1	Magic string - "1LPI"
4B	Int32	C1	Count of images

For I1 = 1 to C1
..	Images Chunks
Next I1

*****************
* IMAGES CHUNKS *
*****************

4B	Byte	M2	Magic byte - 32414E00h
4B	Int32	C2	Count of variable

For I2 = 1 to C2+1
	4B	Int32	W1	Width of image
	4B	Int32	H1	Height of image
	4B	Int32	U2	Unknown
	4B	Int32	U3	Alpha channel
	4B	Int32	L1	Image data length
	For I3 = 1 to L1
		4B	Int32	D1	Data
	Next I3
Next I2

***********************
* ALGORITMUS OF IMAGE *
***********************

For Y = 1 to H1
	4B	Int32	V1	Semafor for action
	
	V1 = 1
		4B	Byte	CC	ARGB
		for all row
	V1 > 0
		V1 set count of repeation next ARGB
		4B	Byte	CC	ARGB
Next Y

```
## Post #5
- Username: dodd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 15, 2010 9:09 am
- Post datetime: 2010-02-20T18:09:14+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

Great work, that helped me a lot. However I think you are bit wrong about .ipl, because my code is different in few places:

```
BinaryReader ipl = new BinaryReader(fs);

StreamWriter log = new StreamWriter(String.Format("{0}_log.txt", filename));

byte[] hd1 = ipl.ReadBytes(4); // "1LPI"

int count = ipl.ReadInt32();
log.WriteLine(count);

for (int i = 0; i < count; i++)
{
	byte[] hd2 = ipl.ReadBytes(4); // "2AN\0"
	int unk1 = ipl.ReadInt32(); // 4

	int w = ipl.ReadInt32();
	int h = ipl.ReadInt32();

	int unk2 = ipl.ReadInt32(); // 0
	int unk3 = ipl.ReadInt32(); // 1
	int img_len = ipl.ReadInt32(); // number of 4-bytes blocks

	Bitmap bm = new Bitmap(w, h);

	for (int y = 0; y < h; y++)
	{
		int x = 0;
		int j = 0;

		int t = ipl.ReadInt32();

		if (t == 1)
		{
			j = w;

			while (j > 0)
			{
				Color c = Color.FromArgb(ipl.ReadInt32());
				bm.SetPixel(x, y, c);
				x++;
				j--;
			}
		}
		else if (t == 0)
		{
		}
		else if (t > 1 && t-1 <= w)
		{
			for (int q = 1; q < t; q++)
			{
				x += ipl.ReadInt32();
				j = ipl.ReadInt32();

				while (j > 0)
				{
					Color c = Color.FromArgb(ipl.ReadInt32());
					bm.SetPixel(x, y, c);
					x++;
					j--;
				}
			}
		}
		else
			throw new Exception();

	}
	
	string img_file = String.Format("{0}_{1}.png", filename, i);

	bm.Save(img_file, ImageFormat.Png);
	log.WriteLine(img_file);
}

log.Close();

ipl.Close();
fs.Close();
```


I don't have this loop:

```
For I2 = 1 to C2+1
```

and image data encoding is bit diffrent.
Good example is emot_hi.ipl .
## Post #6
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-02-20T18:53:24+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

Yes, you're right.

Corect code:

```
* IMAGES CHUNKS *
*****************

4B	Byte	M2	Magic byte - 32414E00h
4B	Int32	C2	Count of variable (4)

Variable cycles:

1.	4B	Int32	W1	Width of image
2.	4B	Int32	H1	Height of image
3.	4B	Int32	U2	Unknown
4.	4B	Int32	U3	Alpha channel (Yes/No)
5.	4B	Int32	L1	Image data length

For I3 = 1 to L1
	4B	Int32	D1	Data
Next I3


```
## Post #7
- Username: dodd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 15, 2010 9:09 am
- Post datetime: 2010-02-21T00:04:33+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

oh, actually c2 is 4 for most files expect for tetrislogo.ipl which has c2=8 for some reason. Other example is deep_bar.ipl, some images has 4 and some 8. How do you know u3 is Alpha channel (Yes/No)? For all files i seen it's allways 1. And seems c2 = 8 for images without alpha channel and c2=4 for images with alpha channel. What do you think?

edit:
maybe this will help you with actions:
tetrislogo has fadeout
tt_t has movement
emot_hi has movement in section sub1

edit2:
u12 -> next action
u13 -> prev action

seems frames actions are not necessary in order. for example start_button clicked section start at 12, ends at 13, but has lenght 4, this is because it goes 12->14->15->13

u19 is probably alpha

also some files' sections have string at offset (from beginning of section) 16 (dec) and 45 (dec).
## Post #8
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-02-21T20:25:15+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

> Reply from dodd
>
> oh, actually c2 is 4 for most files expect for tetrislogo.ipl which has c2=8 for some reason. Other example is deep_bar.ipl, some images has 4 and some 8. How do you know u3 is Alpha channel (Yes/No)? For all files i seen it's allways 1. And seems c2 = 8 for images without alpha channel and c2=4 for images with alpha channel. What do you think?

hum ... really 

I analysed "deep_bar.ipl" and I have to say "You are right" in that c2 = 8 for images without alpha channel and c2=4 for images with alpha channel.  

Then C2 isn't "Count of variable", and is now V2 - Alpha channel (Yes/No).
U3 (Alpha channel (Yes/No)) was only shot. U3 is now uknown   

```
* HEADER OF IPL FILE *
**********************

4B	Char	M1	Magic string - "1LPI"
4B	Int32	C1	Count of images

For I1 = 1 to C1
..	Images Chunks
Next I1

*****************
* IMAGES CHUNKS *
*****************

4B	Byte	M2	Magic byte - 32414E00h
4B	Int32	V2	Alpha channel (Yes/No) - (4/8)
4B	Int32	W1	Width of image
4B	Int32	H1	Height of image
4B	Int32	U2	Unknown
4B	Int32	U3	Unknown
4B	Int32	L1	Image data length

For I3 = 1 to L1
	4B	Int32	D1	Data
Next I3


***********************
* ALGORITMUS OF IMAGE *
***********************

For Y = 1 to H1
	4B	Int32	V1	Semafor for action
	
	V1 = 1
		4B	Byte	CC	ARGB
		for all row
	V1 > 0
		V1 set count of repeation next ARGB
		4B	Byte	CC	ARGB
Next Y

```
## Post #9
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-02-21T20:27:37+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

If you use WinHEX, then here is template for SPR file.

```
description "SPR file"
fixed_start 0

begin
	section	"Header SPR"
		string 4	"Magic"
		uint32	"CountAction"
		uint32	"CountSection"
		uint32	"LengthSection"
		uint32	"LengthAction"
	
		uint8	"U1"
		uint8	"U2"
		uint8	"U3"
	
		uint32	"U4"
		uint32	"U5"
		uint32	"U6"
		uint32	"U7"

		char[32]	"NameAnimation"
		char[128]	"FileAnimationIPL"
	endsection
	
	section	"Sections"
		numbering 1 {
			char[32]	"NameSection ~"
			uint16	"U8 ~"
			uint16	"NumberActionStart ~"
			uint16	"NumberActionFinish ~"
			uint16	"V3 ~"
			uint16	"CountActionForSection ~"
			char[86]	"Empty ~"
		} ["CountSection"]
	endsection
	
	section	"Actions"
		numbering 1 {
			uint16	"NumberAction ~"
			uint16	"ImageNumber ~"
			uint16	"U11 ~"
			uint16	"NumberNextAction ~"
			uint16	"NumberPrevAction ~"
			uint16	"U14 ~"
			uint16	"U15 ~"
			uint16	"DurationOfAction ~"
			uint16	"U17 ~"
			uint16	"U18 ~"
			uint16	"Opacity ~"
			uint16	"U20 ~"
			uint16	"U21 ~"
			uint16	"U22 ~"
			uint16	"OffsetX ~"
			uint16	"OffsetY ~"
		} ["CountAction"]
	endsection
end

```


Edit1: Edit code according to new information.
## Post #10
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-02-21T20:37:44+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

> Reply from dodd
>
> also some files' sections have string at offset (from beginning of section) 16 (dec) and 45 (dec).
Yes. For example "attack.spr" have in first section text "1". Next byte is 00h and next byte is char "5". I think "5" is residual from previous setup.
## Post #11
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-02-21T20:44:21+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

> Reply from dodd
>
> 
u12 -> next action
u13 -> prev action

seems frames actions are not necessary in order. for example start_button clicked section start at 12, ends at 13, but has lenght 4, this is because it goes 12->14->15->13

u19 is probably alpha
Yes, this is true. Good job.

Only U19 isn't alpha, but opacity (255 - 100%, 0 - 0%)  

```
* ACTION *
**********
2B	Int16		V5	Number of action
2B	Int16		U10	Image number
2B	Int16		U11	?
2B	Int16		U12	Number of next action
2B	Int16		U13	Number of previous action
2B	Int16		U14	?
2B	Int16		U15	?
2B	Int16		U16	?
2B	Int16		U17	?
2B	Int16		U18	?
2B	Int16		U19	Opacity (255 - 100%, 0 - 0%)
2B	Int16		U20	?
2B	Int16		U21	?
2B	Int16		U22	?
2B	Int16		U23	?
2B	Int16		U24	?

```
## Post #12
- Username: dodd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 15, 2010 9:09 am
- Post datetime: 2010-02-21T21:21:46+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

> Reply from Kryspin
>
> dodd wrote:also some files' sections have string at offset (from beginning of section) 16 (dec) and 45 (dec).
Yes. For example "attack.spr" have in first section text "1". Next byte is 00h and next byte is char "5". I think "5" is residual from previous setup.
yeah, i was suspecting this could be some trash.
## Post #13
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-02-21T21:24:58+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

Maybe:

U16	Time of duration in ms?
U23	Offset of image in x-direction?
U24	Offset of image in y-direction?

Attention - U23 and U24 are signed Int16  

```
* ACTION *
**********
2B	Int16		V5	Number of action
2B	Int16		U10	Image number
2B	Int16		U11	?
2B	Int16		U12	Number of next action
2B	Int16		U13	Number of previous action
2B	Int16		U14	?
2B	Int16		U15	?
2B	Int16		U16	Time of duration in ms?
2B	Int16		U17	?
2B	Int16		U18	?
2B	Int16		U19	Opacity (255 - 100%, 0 - 0%)
2B	Int16		U20	?
2B	Int16		U21	?
2B	Int16		U22	?
2B	Int16s		U23	Offset of image in x-direction?
2B	Int16s		U24	Offset of image in y-direction?

```

Is in game same animation with rotation, skew?

U11 is a number between 0-255. I found 0,1,2,3,4,6,10,19,255. Maybe some graphical effect.
## Post #14
- Username: dodd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 15, 2010 9:09 am
- Post datetime: 2010-02-21T23:41:49+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

> U23 Offset of image in x-direction?
>
> U24 Offset of image in y-direction?
correct, just got same idea.

also got:

U11 - duration time
U16 - flags: 8h = has prev frame, 4h = has next frame, 2h = visible, 1h = horizontal flip

this is all i need, thank you very much for your help.
## Post #15
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-02-22T09:06:46+00:00
- Post Title: Tetris Online Japan: .spr and .ipl files (animated images)

You are welcome.

I am going finish editor for Avatar in VB.NET
