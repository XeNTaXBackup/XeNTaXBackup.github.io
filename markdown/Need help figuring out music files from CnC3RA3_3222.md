## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2008-11-16T08:55:34+00:00
- Post Title: Need help figuring out music files from CnC3/RA3

I have uploaded some samples of the music from CnC3:Kane's Wrath to [http://users.tpgi.com.au/jfwfreo/cc3.zip](http://users.tpgi.com.au/jfwfreo/cc3.zip)
The CNC3_LoadScreen_RAM.af and 166b084d.3107d99b.10792a13.c0f42330.cdata files are for a "non streaming" file and the TM_CNC3_BB_BLU_04_v1_12-12-06_5point1.af and 166b084d.3107d99b.1a9eb6c5.3c1fad9c.cdata files are for a "streaming" file.
The .af files are dumps from the relavent in-game data files containing header info with the .cdata files containing the actual music.
The data in the .af files, what has been figured out so far as follows:

```
unsigned int SubtitleStringSize;
unsigned int SubtitleStringOffset;
unsigned int NumberOfSamples;
unsigned int SampleRate;
unsigned int HeaderOffset;
unsigned int HeaderSize;
unsigned int ChannelCount;

```


After this header comes the subtitle string and header data (if they exist). Each item starts on a 4 byte boundary with the previous item padded out to the next 4 byte boundary.

The SubtitleString is a null terminated string pointing to a string in the games stringtable (it can be ignored for the purposes of the audio stuff).

The Header stuff is stored in the .af file in streamed tracks and stored at the start of the .cdata file in non-streamed tracks (in the non-streamed case, the HeaderSize and HeaderOffset fields are set to 0). The first byte seems to be 5 in EALayer3 files and 4 in EA XAS ADPCM files. There is also a value used on 360 for the XBOX360 MS ADPCM or something but I have no idea what that is. No idea what the second value, I think it is related to the # of channels. Then after that is 2 bytes for the sample rate and 4 bytes for the number of samples.

The Header (and also possibly the data itself) is in Big Endian format.

Thats all the info I have on this format.

It is known that the audio codec is a variant of the EALayer3 audio codec but I (and a lot of other CnC3/RA3 players) want some code or tools that can decode this, any help in figuring this out (especially the actual EALayer3 codec which seems totally undocumented) would be appreciated.

The other audio in the PC version of the games (sound effects) use EA XAS ADPCM which is already documented. If anyone wants any more examples, I can provide those.
## Post #2
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2009-08-09T08:19:16+00:00
- Post Title: Need help figuring out music files from CnC3/RA3

Ok the only way i know of (Not sure if this works on EAL3 Files) is to use a BIG Extractor and then use Binviewer.exe (in the modsdk) to open the .manifest files (which is a listing of files in the data subdir) and then you can extract sounds from that.

That's all i know about these files (You probably knew that anyway)

Sorry i can't help much more  

-Jenx
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2009-08-09T12:48:49+00:00
- Post Title: Need help figuring out music files from CnC3/RA3

I WROTE BigExtractor and BinView.
And NO, they cant do EALayer3 audio (which is why I am asking for help)
## Post #4
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2009-08-09T13:24:35+00:00
- Post Title: Need help figuring out music files from CnC3/RA3

> Reply from jfwfreo
>
> I WROTE BigExtractor and BinView.
And NO, they cant do EALayer3 audio (which is why I am asking for help)

Settle down man i was just trying to help...

i used FINALBIG btw so i don't think you wrote that,

> FinalBIG
>
> 
>
> Version 0.4 Beta released March 20th, 2006.
>
> 
>
> Copyright by Matthias Wagner 2006

Don't think that's you...

Also quoting myself

> Reply from jenx
>
> (You probably knew that anyway)

Sorry for replying
