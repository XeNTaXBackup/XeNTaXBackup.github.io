## Post #1
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-03T07:13:59+00:00
- Post Title: [Android/iOS] Need for Speed Most Wanted 2012 .sba

Would be much appreciated, as this format is used a lot in ex-Firemint's (now FireMonkey) games.

Example is srt_viper_2013 texture files. Thanks!


[srt_viper_2013.zip](http://www.solidfiles.com/d/50e21af218/)
## Post #2
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2012-11-28T15:48:07+00:00
- Post Title: [Android/iOS] Need for Speed Most Wanted 2012 .sba

No one interested in iOS ver of the game? Man seriously. I want the iOS car models too. But i guess we need to wait until the pc version's cracked :\
## Post #3
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-28T20:07:20+00:00
- Post Title: [Android/iOS] Need for Speed Most Wanted 2012 .sba

The iOS version has way more cars (mainly the Hummer H2 Alpha IS HERE!), I just hope someone takes a look on these formats rather than their chinese plastic made in china subpar fighting games
## Post #4
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2012-12-10T21:19:01+00:00
- Post Title: [Android/iOS] Need for Speed Most Wanted 2012 .sba

[texture_srt_viper_2013_diffuse_00.dds](http://www.mediafire.com/file/b5vj8d52k2dgns5/texture_srt_viper_2013_diffuse_00.dds)

How about some models?
## Post #5
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-12-13T07:11:04+00:00
- Post Title: [Android/iOS] Need for Speed Most Wanted 2012 .sba

Wow,  that's great! Excellent work, could you share the tool? As for models - they use m3g format, I will PM you samples once I get on the other HDD.
## Post #6
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2013-01-08T09:56:16+00:00
- Post Title: [Android/iOS] Need for Speed Most Wanted 2012 .sba

> Reply from RacingFreak
>
> Wow,  that's great! Excellent work, could you share the tool? As for models - they use m3g format, I will PM you samples once I get on the other HDD.

M3Gs with a different header as far as I observed.
## Post #7
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-09T16:02:41+00:00
- Post Title: [Android/iOS] Need for Speed Most Wanted 2012 .sba

Cool. Any progress thus far?
## Post #8
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-02T03:13:29+00:00
- Post Title: [Android/iOS] Need for Speed Most Wanted 2012 .sba

Ill take a look at the format again

-EDIT-
K working on it

```



struct sba_header {
	int32 header_define; // SBA Header identifier (SBIN)						(const)
	int16 unknown_vernum; // could be format version number						(const)
	int16 padding;	// ususally like 00 00 however could change				    (const)
	int32 identifier2; // another WORD (ENUM)									(const)
	int16 unknown_num; // unknown number again could be relating to the header	(const)
	int16 padding2; // ususally like 00 00 however could change					(const)
	int32 globvar1;    // i dont know what this is
	int32 padding3;    // padding ususally (01 00 00 00)
	int32 globvar2; 	// some sort of version number unknown still (eg. 14,12,11,14,39)
	int32 padding4;		// padding ususally (02 00 00 00)
	
	
	};
	
	
	-BULK		// size is 100bytes or 0x64
		-BARG // size is 12 bytes or 0xc
		-DATA // Datachunk
		-DATA // Datachunk	

	
	
	struct bulk_header {
	int32 header_define; // BULK Texturetype Header identifier (BULK)
	int32 DataStartOffset;
	int32 FileNameTableOffset;

	};
	
	struct barg_header {
	int32 header_define; // BARG Texturetype Header identifier (BARG)
	int32 ChunkSize;	// size of the image data chunk  (stored as litle endian)
	int32 bindat;		// unknown value

	};

```
## Post #9
- Username: SiriusR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 16, 2015 6:41 am
- Post datetime: 2015-08-07T22:50:24+00:00
- Post Title: [Android/iOS] Need for Speed Most Wanted 2012 .sba

I have to bump this thread after some observation:
- SBAs in published.*x folders cannot be opened with Chipicao's sbaBrute, regardless of platform; they also seem to have a slightly different structure
- There's a published.texture_pvrtc folder in iOS version of the game with SBAs that contain PVRs; Android version's equivalents of these textures seem to have a different kind of image file inside, thus it can't be recognized by sbaBrute

I'd like some help with those, as I would love to have the game's UI textures, and there's a Chinese freemium version of the game with Jaguar F-Type, which I'd like to get to worldwide version of the game both for iOS and Android, but port to the latter platform is now stuck due to car's usage of some iOS-only PVR textures.
