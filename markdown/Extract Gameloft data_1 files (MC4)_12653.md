## Post #1
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-02-27T20:35:01+00:00
- Post Title: Extract Gameloft data_1 files (MC4)

hello,

I try to rip assets from MC4 (Modern Combat 4) Android.

I have already extracted the OBB data, now I have some data_# files:

data_1 - 506 MB
data_2 - 491 MB
data_3 - 763 MB
data_4 - 60 MB
data_5 - 2.2 MB
data_6 - 126 MB

They have no file extension. Are they .gla files? How do I extract them?
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-02-28T03:36:40+00:00
- Post Title: Extract Gameloft data_1 files (MC4)

> Reply from Slandey
>
> hello,

I try to rip assets from MC4 (Modern Combat 4) Android.

I have already extracted the OBB data, now I have some data_# files:

data_1 - 506 MB
data_2 - 491 MB
data_3 - 763 MB
data_4 - 60 MB
data_5 - 2.2 MB
data_6 - 126 MB

They have no file extension. Are they .gla files? How do I extract them?

Most likely its in the gla format open it in a hex editor and have a look
## Post #3
- Username: jakkrit
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 14, 2014 8:08 pm
- Post datetime: 2015-04-08T07:44:09+00:00
- Post Title: Extract Gameloft data_1 files (MC4)

I got all files in .sobfs format. I tried to open them in hex and found them in random format like vox, bres, etc,.
So, I want to know how can I read and extract bres file?
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-04-11T15:30:09+00:00
- Post Title: Extract Gameloft data_1 files (MC4)

> Reply from jakkrit
>
> I got all files in .sobfs format. I tried to open them in hex and found them in random format like vox, bres, etc,.
So, I want to know how can I read and extract bres file?
bres are the models

some very very very old research

```

struct bdae_header {
	int32 header_define; // BRES Header identifier 
	int16 byteorder; // BYTE ORDER (little endian/big)
	int16 padding;	// ususally like 00 however could change
	int32 unknown_val; // could be version num
	int32 filesize; // filesize
	
	int32 unknown_val2; 		// ??
	int32 unknown_val3;			// always 32
	int32 pointer1;				// points to the start of the texture info each entry is sperated by 00 00 and not 00 alone
	int32 pointer2;				// end of texture shit start of data
	
	int32 const_unknown1;			// const 20 but could change
	int32 const_unknown2;			// const 24 but could change
	int32 const_unknown3;			// const 28 but could change
	int32 pointer3;					// same as pointer 2 points to the end of texture shit
	
	
	int32 pointer4;					// points to an unknown value after texture data
	int32 pointer5;					// points to some data after pointer4
	int32 pointer6;					// points to some data after pointer4
	int32 pointer7;					// points to some data after pointer5
	
	
	int32 pointer8;					// points to data unknown
	int32 pointer9;					// points to data unknown
	int32 pointer10;				// points to data unknown
	int32 pointer11;				// points 4 bytes after pointer 10 :/
	
	int32 pointer12;				// points to data unknown
	int32 pointer13;
	int32 pointer14;
	int32 pointer15;
	
	int32 pointer16;				
	int32 pointer17;
	int32 pointer18;
	int32 pointer19;	
	
	int32 pointer20;				
	int32 pointer21;
	int32 pointer22;
	int32 pointer23;		
	
	int32 pointer24;				
	int32 pointer25;
	int32 pointer26;
	int32 pointer27;	
	
	int32 pointer28;				
	int32 pointer29;
	int32 pointer30;
	int32 pointer31;

	int32 pointer32; // facelist offset		
	int32 pointer33; // use this to find vertcount just offset 8 bytes from this
	int32 pointer34;
	int32 pointer35;	
	
	
	
	};

```
