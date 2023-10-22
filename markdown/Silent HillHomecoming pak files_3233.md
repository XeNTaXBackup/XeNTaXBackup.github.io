## Post #1
- Username: gamemaster
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 21, 2008 8:07 am
- Post datetime: 2008-11-27T22:52:11+00:00
- Post Title: Silent Hill:Homecoming pak files?

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: MrDeviance
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 27, 2008 12:05 pm
- Post datetime: 2008-11-28T05:23:44+00:00
- Post Title: Silent Hill:Homecoming pak files?

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-28T14:08:54+00:00
- Post Title: Silent Hill:Homecoming pak files?

```
uint version; // ?, =1
uint numFiles;
uint uk;

struct Entry
{
    char name[64];
    uint uk1; // 1 or 33
    time_t timestamp;
    uint offset;
    uint size1;
    uint flags<format=hex>; // ?
    uint size2; // guess the 2 sizes are compressed size and uncompressed size, but I haven't seen any compressed file yet
} directory[numFiles];
```

Strangely this doesn't work for all entries. For example entry 1910 has offset 0, size1 0xFFFF, size2 0
## Post #4
- Username: MrDeviance
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 27, 2008 12:05 pm
- Post datetime: 2008-11-29T02:55:01+00:00
- Post Title: Silent Hill:Homecoming pak files?

So, by that you are saying you can't figure it out?
Should I be waiting on a fix here anymore or should I aknoledge that the format is impossible to crack by this community?
The reason I am asking this, is because I don't like to come to a forum and wait for new posts if nobody will ever post back.
If possible, I would like a final conclusion on this file.
A yes, no or please wait some more will do.
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-29T12:06:13+00:00
- Post Title: Silent Hill:Homecoming pak files?

You can at least extract the entries with valid offsets and sizes.
Somebody just needs to write a BMS. I don't have time for that.
## Post #6
- Username: MrDeviance
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 27, 2008 12:05 pm
- Post datetime: 2008-11-30T07:57:38+00:00
- Post Title: Silent Hill:Homecoming pak files?

Oh well, I didn't expect much from here anyway so thanks for caring to check those files.
When it will support this game I will buy the app till then good luck.
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-30T12:00:30+00:00
- Post Title: Silent Hill:Homecoming pak files?

To finish this:
(code is not tested)

```
If magic <> "PAK_";
CleanExit;
EndIf;
Get Dummy Long 0;
Get numFiles Long 0;
Get Dummy Long 0;

For i = 1 to numFiles;
GetDString filename 64 0;
Get Dummy Long 0;
Get timestamp Long 0;
Get offset Long 0;
Get size Long 0;
Get Dummy Long 0;
Get Dummy Long 0;
If offset <> 0;
Log filename offset size;
EndIf;
Next i;
```
## Post #8
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2008-12-19T07:58:34+00:00
- Post Title: Silent Hill:Homecoming pak files?

Rheini
What does it means your CODEs?

Here are peaople who do not know any programming lang.
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-12-19T11:03:42+00:00
- Post Title: Silent Hill:Homecoming pak files?

This is a MultiEx Commander script to support this file type.
Think you can also use it with GameExtractor.
## Post #10
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2008-12-19T12:03:08+00:00
- Post Title: Silent Hill:Homecoming pak files?

Rheini
either it doesn't works or I'm doin' somthin' wrong!

How to use it by GExtractor i've no clue!

Please tell me what to do
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-12-19T12:46:36+00:00
- Post Title: Silent Hill:Homecoming pak files?

In the scripts folder there is a scripts.zip.
You may add files in there:

```
GetDString magic 4 0;
If magic <> "PAK_";
CleanExit;
EndIf;
Get Dummy Long 0;
Get numFiles Long 0;
Get Dummy Long 0;

For i = 1 to numFiles;
GetDString filename 64 0;
Get Dummy Long 0;
Get timestamp Long 0;
Get offset Long 0;
Get size Long 0;
Get Dummy Long 0;
Get Dummy Long 0;
If offset <> 0;
Log filename offset size;
EndIf;
Next i;
</bms>
```
## Post #12
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2008-12-19T19:26:21+00:00
- Post Title: Silent Hill:Homecoming pak files?

it coudn't open the archive!
It says: "The selected script wasn't able to open the archive."
## Post #13
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2009-03-23T10:57:00+00:00
- Post Title: Silent Hill:Homecoming pak files?

I hope resurrecting a 3-month-old thread isn't too taboo here, but there is a good reason for it.  I was looking into this format myself, and have hammered out all of the specifics. Then I went on to figure out all of the custom container formats and the models. A complete viewer and extractor for all of the resources can be obtained here:

[http://www.richwhitehouse.com/index.php?postid=32](http://www.richwhitehouse.com/index.php?postid=32)

Specs on the actual PAK files are as follows:

```
{
	char			id[4]; //PAK_
	uint			unknownA;
	uint			numFiles;
	uint			unknownB;
} shPakHdr_t;

//skip ahead sizeof(header), and for each entry up to numFiles:

typedef struct shPakEntry_s
{
	char			name[64];
	uint			indexFlag;
	uint			timestamp;
	int			ofs;
	int			size;
	short			fileIndex;
	ushort		unknownB;
	uint			unknownC;
} shPakEntry_t;

```


If fileIndex is -1, the ofs is the location of bytes of the file from the beginning of the main PAK file. Otherwise, fileIndex directly corresponds to the numbered file extension (e.g. fileIndex 9 is for pakname_09.pak), while the offset is relative to the beginning of that file. There is one exception, though. When fileIndex >= 0, and unknownB is 3, the offset is still for the main PAK file. Not sure what the significance is, but with these rules, every file in the game can be extracted reliably. Also be aware that multiple entries can have the same "name", while having different offsets to different data (for example, a model and a material file with the same base file name).

Additionally, SHADERS.PAK and SHADERSL.PAK have special half-sized pak entries, with no header bytes to indicate such, for some reason. Their entry structure is as follows.

```
{
	char		name[64];
	int			ofs;
	int			size;
	int			unknownA;
} shMiniPakEntry_t;

```

Some files in the PAKs are LZO-compressed. They begin with a 12 byte header, "LZO ", followed by 2 big-endian 32-bit integers. The first int is the size once decompressed, and the second int is the size of the compressed data. Run the data that follows the 12 bytes through a standard LZO decompression algorithm up to the value of the second int, and you will have your original file data. This compression is often used on DDS textures in the PAK files.

Some main data types include Ogg files, "SYT" files (which are DDS files with a custom header), and "EIFF" files (a media container header used on models and particle systems - the container includes resource dependencies for materials or other files that the model/particle system references). I will eventually document my findings on these media formats as well if anyone is interested, but in the mean time, feel free to contact me if you're working on deciphering the formats yourself and want some pointers.
## Post #14
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-03-29T10:58:04+00:00
- Post Title: Silent Hill:Homecoming pak files?

I hope you become success ,masters ! that is really a beautiful game !
## Post #15
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-11-17T14:45:59+00:00
- Post Title: Silent Hill:Homecoming pak files?

can anyone find the siam model from the pak files? cuz all i c is alex and his weapons?
## Post #16
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2009-11-19T10:12:14+00:00
- Post Title: Re: Silent Hill:Homecoming pak files?

if you want the textures and models and sound you can use this tool   
Scarlet: [http://www.richwhitehouse.com/index.php ... hp#prjmp87](http://www.richwhitehouse.com/index.php?content=inc_projects.php#prjmp87)
## Post #17
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-08T18:59:54+00:00
- Post Title: Re: Silent Hill:Homecoming pak files?

does anyone no how to apply those single colored normal maps extracted from SH5 in 3dsmax or a way to convert them to normal tangent spaced normal map?

help plz?
## Post #18
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2009-12-26T00:52:02+00:00
- Post Title: Re: Silent Hill:Homecoming pak files?

Hey. Those normal maps are already in tangent space. They use a common technique that involves swapping the alpha and red channels, and deriving the z in a pixel shader. Here's an example of how to decode it from the fragment program I wrote for Scarlet:

PARAM	mulf = {2.0, 2.0, 2.0};
PARAM	subf = {-1.0, -1.0, -1.0};
#(for standard scale+bias normal expansion)
MAD		nrml, nrml.wyzx, mulf, subf; #<--notice r-a swizzle
DP4_SAT	nrml.z, nrml, nrml; #<--and of course, it's simple to derive z from here
## Post #19
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-26T19:12:34+00:00
- Post Title: Re: Silent Hill:Homecoming pak files?

> Reply from MrAdults
>
> Hey. Those normal maps are already in tangent space. They use a common technique that involves swapping the alpha and red channels, and deriving the z in a pixel shader. Here's an example of how to decode it from the fragment program I wrote for Scarlet:

PARAM	mulf = {2.0, 2.0, 2.0};
PARAM	subf = {-1.0, -1.0, -1.0};
#(for standard scale+bias normal expansion)
MAD		nrml, nrml.wyzx, mulf, subf; #<--notice r-a swizzle
DP4_SAT	nrml.z, nrml, nrml; #<--and of course, it's simple to derive z from here

thanks for the info but i no nothing about scripting. so am i suppose to plug this script in somewhere in max.
## Post #20
- Username: onionhead
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2009-12-27T14:05:56+00:00
- Post Title: Re: Silent Hill:Homecoming pak files?

This is a Photoshop plugin that will perform the swizzling, z derivation, and re-normalization operations.

[http://www.richwhitehouse.com/index.php ... izzler.zip](http://www.richwhitehouse.com/index.php?content=inc_projects.php&filemirror=PS_NormalSwizzler.zip)

I don't know if it will work in anything earlier than CS3. I don't have anything for Max either.
## Post #21
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-28T15:28:05+00:00
- Post Title: Re: Silent Hill:Homecoming pak files?

cool this works. thanks
## Post #22
- Username: srcs34k
- Rank: n00b
- Number of posts: 14
- Joined date: Wed May 23, 2012 11:45 pm
- Post datetime: 2014-01-11T21:03:59+00:00
- Post Title: Re: Silent Hill:Homecoming pak files?

Scarlet (RichWhitehouse) is good, but problem is a thousands files, that hell extract by one file...
i dont find option in Scarlet "Extract All Files To..."

how Batch extract PAK? that possible?
