## Post #1
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2017-11-08T09:50:55+00:00
- Post Title: CHRONICLES OF SEALING GODS binary font

I am trying to edit a font so that this font can support my language. However, I do not have much knowledge about this file, can you help me? Thank you very much 
Link font file: [https://drive.google.com/file/d/0Bwg-L6 ... sp=sharing](https://drive.google.com/file/d/0Bwg-L6CMP5RpNGd6MEFsa0I1VGM/view?usp=sharing)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-11-18T19:55:23+00:00
- Post Title: CHRONICLES OF SEALING GODS binary font

dead simple format:

```
// WRS

uint count;

struct d
{
  ushort glyph_code;
  ubyte w, h;
  ubyte data[(int)w*(int)h];
};

d data[count] <optimize=false>;

// Ensure the whole file is parsed
Assert(FTell() == FileSize());

```


script for quickbms - these will need converting to a bitmap and reimporting or something   

```

for J = 1 to NUM
	get CHARCODE short
	get WIDTH byte
	get HEIGHT byte
	savepos FTELL
	math SIZE = WIDTH
	math SIZE *= HEIGHT
	string NAME p= "%u.font" CHARCODE
	log NAME FTELL SIZE
	math FTELL += SIZE
	goto FTELL
next J

```
## Post #3
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2017-11-19T15:00:21+00:00
- Post Title: CHRONICLES OF SEALING GODS binary font

> Reply from WRS
>
> dead simple format:
Code: Select all// 010 binary template
// WRS

uint count;

struct d
{
  ushort glyph_code;
  ubyte w, h;
  ubyte data[(int)w*(int)h];
};

d data[count] <optimize=false>;

// Ensure the whole file is parsed
Assert(FTell() == FileSize());


script for quickbms - these will need converting to a bitmap and reimporting or something   
Code: Select allget NUM long

for J = 1 to NUM
	get CHARCODE short
	get WIDTH byte
	get HEIGHT byte
	savepos FTELL
	math SIZE = WIDTH
	math SIZE *= HEIGHT
	string NAME p= "%u.font" CHARCODE
	log NAME FTELL SIZE
	math FTELL += SIZE
	goto FTELL
next J
Thanks so much WRS.
