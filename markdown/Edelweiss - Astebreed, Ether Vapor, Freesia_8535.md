## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-12T22:01:09+00:00
- Post Title: Edelweiss - Astebreed, Ether Vapor, Freesia

[http://edelweiss.skr.jp/works/astebreed/index.html](http://edelweiss.skr.jp/works/astebreed/index.html)

Looks cool.
I've played their games before but I never actually paid attention to their game resources lol

Maybe I'll load up ether vapor again and see what it has.
Here's ether vapor: [http://edelweiss.skr.jp/works/ethervapor/re/index.html](http://edelweiss.skr.jp/works/ethervapor/re/index.html)

EDIT: wow the remastered version looks so much better than the original lol

Freesia also looks good, though maybe the only 3D parts are actually just videos lol

[http://www.youtube.com/watch?v=jbdzJGrO3OE](http://www.youtube.com/watch?v=jbdzJGrO3OE)

Ethervapor is just using direct3d txt .x files.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-13T03:41:16+00:00
- Post Title: Edelweiss - Astebreed, Ether Vapor, Freesia

Well this unpacks the ethervapor archives

```
#Supports the following games

#Ether Vapor (remastered)
#Fairy Bloom Freesia
#Astebreed

idstring "TGP0"
get unk1 long
get null long
get FILES long

for i = 0 < FILES do
	getdstring NAME 96
	get OFFSET long
	get flag long
	get SIZE long
	get unk2 long
	
	log NAME OFFSET SIZE
next i
```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-13T06:58:54+00:00
- Post Title: Edelweiss - Astebreed, Ether Vapor, Freesia

Freesia uses the same archives.
They used a different model format this time, but it's still a text file...

In fact it almost looks like they just took the .x format, changed things around, used "polygon" structs to define each triangle and wasting a whole bunch of space while they're at it, and then somehow ended up with a 3.5 MB file for a model with 3811 verts and 6783 faces. I mean, what's the difference between just all of the face indices line by line like the MQO format does? At least they don't waste space with braces and spaces and new-lines.

They even marked every 10 entries with like, a comment.

I went and compressed that file and it ended up being 200 KB.

Like wow...

```

#====================
# テクスチャリスト
#====================
TextureList 16
{
	Texture "Sky_Morning_Tex"
	{
		type Standard
		file "Sky_Morning.dds"
	}

	Texture "Far_Forest_Tex"
	{
...

```


```
	# メッシュ
	#========================================
	Mesh "MiniTree_F"
	{
		PolygonList 360
		{
			# No.0
			Polygon 3
			{
				Material 1
				{
					11
				}
				Face 3 (2 1 3)
				Color 3 (4288455609 4288587196 4288718782)
				UV 3 (3 1 2)
			}
			# No.1
			Polygon 3
			{
				Material 1
				{
					11
				}
				Face 3 (0 1 2)
				Color 3 (4288324023 4288587196 4288455609)
				UV 3 (0 1 3)
			}
			# No.2
			Polygon 3
			{
				Material 1
				{
					11
				}
				Face 3 (6 5 7)
				Color 3 (4286348684 4283783014 4283848807)
				UV 3 (4 5 6)
			}
			# No.3
			Polygon 3
			{
				Material 1
				{
					11
				}
				Face 3 (4 5 6)
				Color 3 (4283849064 4283783014 4286348684)
				UV 3 (7 5 4)
			}
			# No.4
			Polygon 3
			{
				Material 1
				{
					11
				}
				Face 3 (10 9 11)
				Color 3 (4285301127 4284840318 4285103491)
				UV 3 (8 9 10)
			}
...

```
## Post #4
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2012-03-16T07:50:00+00:00
- Post Title: Edelweiss - Astebreed, Ether Vapor, Freesia

There's already a Freesia thread here.
[viewtopic.php?f=16&t=7523](http://forum.xentax.com/viewtopic.php?f=16&t=7523)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T13:48:13+00:00
- Post Title: Edelweiss - Astebreed, Ether Vapor, Freesia

Cool. This was mainly for astebreed, but then it probably made sense to just clump all their games together.

Astebreed uses the same format as Freesia, except now it seems like it doesn't define a material struct with every single face.

Now I'm wondering if I should parse all of the structs first before going back and retrieving the data.
## Post #6
- Username: How Horrifying
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 18, 2014 6:39 pm
- Post datetime: 2014-01-19T09:12:57+00:00
- Post Title: Edelweiss - Astebreed, Ether Vapor, Freesia

I'm trying to see if translation of Astebreed is possible now that the full version has released from C85, but your script gives me a "MultiEx failed to process 17" error.
I am somewhat at a loss as to what to do at this point, since MexScript is a somewhat unintuitive beast.

Edit: Using this code gives me "No Errors" when checking it with MultiEx, but gives me "MultiEx 3 could not process, error 18" when I use it on the game archive.

```
Get UNK Long 0 ;
Get null Long 0 ;
Get FILES Long 0 ;

For T = 0 To FILES ;
   GetDString NAME 96 0 ;
   SavePos OFFSETOFFSET 0 ;
   Get OFFSET Long 0 ;
   SavePos SIZEOFFSET 0 ;
   Get SIZE Long 0 ;
   Get flag Long 0 ;
   Get UNKN Long 0 ;
   
   log NAME OFFSET SIZE OFFSETOFFSET SIZEOFFSET ;
Next T ;
```

I wrote it based on what I could understand from the archive



Screenshot (7).jpg (204.3 KiB) Viewed 191 times
## Post #7
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-07-09T09:17:09+00:00
- Post Title: Edelweiss - Astebreed, Ether Vapor, Freesia

```
DWORD Flags; // 0x00020000 is compressed;
DWORD NumFiles;
DWORD DecompessedDataSize;

struct File
{
    char Name[96];
    DWORD Offset;
    DWORD Size;
    DWORD Reserved[2];
};

File files[NumFiles];
BYTE Data[FileSize()-FTell()];
```


If Flags has 0x00020000 value, then data is compressed. 0x00088b1f value at the start of Data block indicates a compression using gzip.
## Post #8
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2015-06-18T05:26:43+00:00
- Post Title: Edelweiss - Astebreed, Ether Vapor, Freesia

Sorry for the necro, though I've been poking at Astebreed, which I just bought. The format above isn't quite correct. Here's a better one.

```
WORD Version; // Only 2 is accepted
WORD Flags; // 0x0001 is encrypted, 0x0002 is compressed
DWORD NumFiles;
DWORD DecompessedDataSize;

struct File
{
    char Name[96];
    DWORD Offset;
    DWORD Size;
    DWORD Reserved[2];
};

File files[NumFiles];
BYTE Data[FileSize()-FTell()];
```


For archives with encryption flag set, only files with the extensions dds, png, bmp, tga, jpg, and jpeg (i.e. all textures) are encrypted. Encryption is simply XORing each byte with 0x46.
## Post #9
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2016-02-16T12:41:01+00:00
- Post Title: Edelweiss - Astebreed, Ether Vapor, Freesia

Any hopes in this??? This is a dead thread??? So sad!!! Still want those model though
