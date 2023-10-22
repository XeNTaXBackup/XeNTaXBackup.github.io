## Post #1
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-10-13T13:53:07+00:00
- Post Title: RAGE .bimage files.

Here is a sample unzipped(I extracted it with offzet using -z -15 value) .bimage file of RAGE. How can I edit it?
I have no idea about OpenGL textures.
[http://up.ht/nFK2WM](http://up.ht/nFK2WM)
## Post #2
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-10-19T16:13:27+00:00
- Post Title: RAGE .bimage files.

Bump.
## Post #3
- Username: 49131
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 28, 2011 11:23 pm
- Post datetime: 2011-10-28T15:35:44+00:00
- Post Title: RAGE .bimage files.

The Bimages are a pretty simple format in general it is similar to something like DDS or whatever.

All ints are big endian
There are two structures in the file Headers and SubHeaders:

```
#pragma pack(1)

struct BimageHeader
{
	unsigned int magic1;
	unsigned int magic2;
	unsigned int zeros0;
	unsigned int width;
	unsigned int height;
	unsigned int zeros1;
	unsigned int numMips;
	unsigned int zeros2;
	unsigned char garbage[10];


};

struct BimageSubHeader
{
	unsigned int mipLevel;
	unsigned int zeros;
	unsigned int width;
	unsigned int height;
	unsigned int dataSize;


};

#pragma pack(pop)
```


The file starts with the header followed by a number of sub headers. The exact number of sub header depends on the header (numMips field) and whether it is a regular 2D texture or a cubemap. The subheaders are followed by pixel data. Pixel data is usually coded as DXT1 or DXT5. Altough the coding is probably somewhere in those headers just use the following code to figure it out:

```

	// Try to guess the decoding flags from the data size
	if ( decodedSize == subHeader.dataSize )
	{
		// probably uncompressed :)
	}
	else if ( subHeader.dataSize == squish::GetStorageRequirements(subHeader.width, subHeader.height, squish::kDxt1 ) )
	{
		//DXT1
	}
	else if ( subHeader.dataSize == squish::GetStorageRequirements(subHeader.width, subHeader.height, squish::kDxt5 ) )
	{
		//DXT5
	}	

```


Then just decode subheaders till the end of the file and dump it all out...
Thus the whole file is something like

Header
SubHeader
RAW data
SubHeader
RAW data
SubHeader
RAW data
SubHeader
RAW data
...


Finally some of the textures (level loading screens etc.) are coded in the YCoCg color space with the luma in  DXT5 alpha to give a bit better quality results. Petty of online sources on how do reverse that.
## Post #4
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-10-29T15:42:18+00:00
- Post Title: RAGE .bimage files.

@49131 thanks for your help. But the information you gave so advanced for me.  Can you give a script to use with QuickBMS or something like that if it's possible? Unfortunately, I'm not an expert. 

An example: [http://localhostr.com/file/l3ovQTd/subway_town.bimage](http://localhostr.com/file/l3ovQTd/subway_town.bimage)
## Post #5
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-11-06T09:14:19+00:00
- Post Title: RAGE .bimage files.

yes, If you give your c# or c program it will be very nice. For decompressor and compressor
## Post #6
- Username: doomed
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 09, 2010 7:55 am
- Post datetime: 2012-10-17T17:18:59+00:00
- Post Title: RAGE .bimage files.

Bumping because Doom 3 BFG uses the same format!

If anyone is going to work on it, chances are this will help him: [http://www.nvidia.com/object/real-time- ... ssion.html](http://www.nvidia.com/object/real-time-ycocg-dxt-compression.html)
## Post #7
- Username: y2keeth
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Sep 19, 2021 5:36 pm
- Post datetime: 2023-02-23T07:36:45+00:00
- Post Title: RAGE .bimage files.

wattos game extractor
can convert them [http://www.watto.org/game_extractor.html](http://www.watto.org/game_extractor.html)
