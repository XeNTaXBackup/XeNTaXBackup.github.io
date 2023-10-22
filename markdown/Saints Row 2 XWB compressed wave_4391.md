## Post #1
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-26T11:26:47+00:00
- Post Title: Saints Row 2 XWB compressed wave

There's an application (towav.exe) that attempts to convert XWB files to WAV.  On one of the XWB files in SR2 (MUS MIX), it only manages to extract 8 files when there are 101.  I finally figured out why: the other 93 appear to be compressed but I can't figure out what kind of compression it is (no header info) or how to go about uncompressing them.

XWB is a Microsoft XNA Wavebank format so the logical conclusion would be something in System.IO.Compression.  I tried them both as well as ICSharpZipLib Zip.Compress.Inflate and all of them fail (most likely due to the lack of header.

I'm running out of ideas. 


Every file appears to start with a int16 value of 5-7.  I find this odd and it is probably important.  I attached a zip with 5 of the raw files (WAVE header removed).  If I play it with the WAVE header, it is just static.

Any incite would be greatly appriciated.  So close...but yet so far.
[sr2_comp_waves.zip](https://xentaxbackup.github.io/file/2972_sr2_comp_waves.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-26T13:37:09+00:00
- Post Title: Saints Row 2 XWB compressed wave

why don't you use [unxwb](http://aluigi.org.papers.htm#unxwb)?
it tells any information found about the file and automatically builds the needed headers to play/convert it in a second moment.
## Post #3
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-26T14:08:14+00:00
- Post Title: Saints Row 2 XWB compressed wave

I didn't know it existed because it got no hits on Google.  I put it on the [XBOX_XWB3#Compatible_Programs](http://wiki.xentax.com/index.php?title=XBOX_XWB3#Compatible_Programs) so more people will find it.

However, it didn't work.  All the files I'm having trouble with (the compressed lot) your tool dumps what I attached (a short, followed by compressed data) with a WMA extension.  Obviously, WMP can't play it because it doesn't have the appriorate header information.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-26T14:48:05+00:00
- Post Title: Saints Row 2 XWB compressed wave

uhmmm so they get identified as wma files.

indeed they don't look like xma1 or xma2 files because xmaencode can't decode them.
they could be msadpcm but I doubt because this adpcm needs a particular value located in the xwb archive and after a scanning I have found no value good to hear a clean sound so it's not msadpcm too.

is this a x360 game?
could it be xwma? mah
everything I know about this matter is already implemented in unxwb so I have out of ideas
## Post #5
- Username: GodOfWar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 05, 2010 11:35 am
- Post datetime: 2010-04-26T21:01:18+00:00
- Post Title: Saints Row 2 XWB compressed wave

> Reply from aluigi
>
> is this a x360 game?
yeah, is 360 game.the big archive called real_music.vpp_xbox2 (1.05gb) contains all music from game (files have .mus extension). [tool](http://blog.gib.me/category/games/saints-row-2/) for PC version didn't work with x360 version =(
## Post #6
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-26T21:35:34+00:00
- Post Title: Saints Row 2 XWB compressed wave

It was extracted from music1.vpp_pc to music4.vpp_pc from the PC (Steam) version of Saints Row 2.  The xwb format appears "normal" except for a few things:

Header:

```
        public int Unknown44;
        public int Unknown42;  // This is odd -- no idea what this 42 is for.  Maybe it is the original version number and they incremented it to 44 for their changes.
        public int WaveBankInfoOffset;
        public int WaveBankInfoLength;
        public int FileRecordsOffset;
        public int FileRecordsLength;
        public int CompressionInfoOffset;  // This is somewhat odd
        public int CompressionInfoLength;  // This is very odd.
        public int Unknown1Offset; // Always 0
        public int Unknown1Length; // Always 0
        public int FileDataOffset;
        public int FileDataLength;
```


CompressionInfo is an array of ints.  It counts up from zero except where it matches FileRecords for a compessed file (e.g. FileRecord[1] = compessed, CompressionInfo[1] = -1).  How quickly it counts up seems to be determined by the size of the file.  On MUS MIX.xwb, the Length of Compression Info is over 6000 but the counting up ends around 600.  There are only 101 file records.  No -1s appear after the 101 index.  It appears that, so long as the value isn't -1, it doesn't mean anything.

Wave Bank Info:

```
        public int FileCount;
        public string Name; // 64 bytes
        public int FileRecordLength;
        public int FileNameLength;
        public int FileDataOffset;
        public int Unknown1; // Always 0
        public int Unknown2;
        public int Unknown3;
```


Those Unknown2 don't seem to match up to what appears in the unxwb source (especially 2 and 3).  I haven't been able to sort what they are.  It might be that Unknown2 is a start time (or ticks from an epoch) and Unknown3 is a stop time.

I uploaded the smallest XWB with the CompressionInfo array here.  There are no files in this particular XWB that are not compressed:
[http://www.speedyshare.com/files/22145167/MUS_420.xwb](http://www.speedyshare.com/files/22145167/MUS_420.xwb)

When I say compressed, I mean these files are way too small to be waves.  MUS MIX.xwb has 8 uncompressed files and some are north of 20 MiB in size.  The compressed files rarely exceed 1 MiB.

I am not certain the format flag (WAV/WMA) is correct.  There's no way to be certain until the compression is dealt with.

I haven't tried DeflateStream or InflateStream without the first short but, on examining some other files, it appears that short isn't uniform across all XWB files.
## Post #7
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-28T03:43:32+00:00
- Post Title: Saints Row 2 XWB compressed wave

All WMA files start with 0500, 0600, or 0700.  The ones that are obviously music actually have the first 17 bytes match.  It would make sense if their uncompressed headers matched therefore causing a large chunk of the compressed data match.  So I guess my question is this:  What types of compression support headerless inflation?  I know zlib has compress() and uncompress() but I doubt it can handle the ~2 MiB some of these files are (I don't see any indication there are parts).


Edit: I tried zlib and zlib1 uncompress(dest, destlen, src, srclen) and both return Z_DATA_ERROR.


Anyone have any ideas I could try?


Maybe this thread should be moved to the compressed forum.
## Post #8
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-05-04T17:00:02+00:00
- Post Title: Saints Row 2 XWB compressed wave

This new section of the XWB (apparently unique to Saints Row 2) I call "CompressionInfo" has been described:

```

// at each offset
int count;
int[count] uncompressed_begin_offset;

```


For example, compress_array_offset_from_end_of_this_array could contain:

```
-1
12
```

Reading the offsets would turn that into an array:
File 0:

```
value = { 20, 40, 60 }
```


File 1: not compressed = null

File 2:

```
value = { 30, 60, 90, 120, 150 }
```


Basically, what I know:
-The file's total deflated size.
-How many inflated sections there are.
-The size of each inflated section.
-Zipping a compressed file results in virtually zero gain.
-Appears to be headerless.  If it has a header, it is short.
-Every deflated section appears to be exactly 929 or 1487 bytes in length (depends on file).

What I don't know:
-The compression method used.


Name that compression!
## Post #9
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-05-07T16:29:43+00:00
- Post Title: Saints Row 2 XWB compressed wave

I think it uses a combination of compression and encryption.  That is, it compresses x amount of data and then losslessly encrypts it to y block size (1487 and 929 for sure).  The compression itself could be as simple as zlib inflate (the SR2 exe has references to it) but I have no idea on the encryption.

I extracted the list of most of the strings from the SR2 executable and they are attached.  Maybe it has some clues as to what is happening in the XWB files.
[sr2 strings.zip](https://xentaxbackup.github.io/file/3017_sr2 strings.zip)
## Post #10
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-08-03T14:01:53+00:00
- Post Title: Saints Row 2 XWB compressed wave

Hello and sorry - I know, the last posting in this thread was 3 months ago, but it's the best thread on the subject XWB that I found so far - so I hope, the original posters are still reading. And sorry for my English!
I'm writing a tool (a perl script actually) in order to insert sounds into an existing german game, that uses .xsb/.xwb files. And additionally, the tool is supposed to extract waves (nearly all of them are WMA) from the wavebanks. I wrote it, because unxwb can't (afaik) write valid/playable .wma files... and other tools (XWB_Extractor, EkszBox,...) weren't able to handle the .xwb files of the game at all. This is no wonder, because backward compatibility is not really needed in XACT(=the tool that creates .xwb/.xsb files) and therefor, Microsoft can change the format with each version of the .xwb/.xsb file format. So "old" extraction tools won't work with "new" xsb/xwbs. 

First of all: Congratulations, FordGT90Concept   - you did a very good job in "demystifying" the .xwb structure , but (sorry, I have to say that) you can get detailed xwb-info very easy, because the .xwb format (unfortunately NOT the xsb format) is documented in Microsofts DirectX SDK. Just download+install the SDK and search for the header file "xact3wb.h" (in older SDKs it's "xact2wb.h"). As a summary: 

```
    DWORD           dwSignature;                        // File signature "WBND"
    DWORD           dwVersion;                          // Version of the tool that created the file
    DWORD           dwHeaderVersion;                    // Version of the file format
    WAVEBANKREGION  Segments[WAVEBANK_SEGIDX_COUNT];    // Segment lookup table
}
```
 so your "Unknown44" means, the .xwb file was created with tool(=XACT) version 44, and "Unknown42" is the xwb file format version. 

```
    DWORD       dwOffset;               // Region offset, in bytes.
    DWORD       dwLength;               // Region length, in bytes.
}
```
Actually, there COULD be up to 5 Regions, but all .xwbs I saw so far had only 3 or 4, namely (+appearing in this order in the file): 1. WAVEBANKDATA, 2. ENTRYMETADATA, (3. SEEKTABLES),(4.ENTRYNAMES), 5. ENTRYWAVEDATA
Thus, a Header of a .xwb with 5 Region-entries is 3*4(for Signature,..) + 5*8(Regions)=52 B long

1. WAVEBANKDATA

```
    DWORD                   dwFlags;                                // Bank flags
    DWORD                   dwEntryCount;                           // Number of entries in the bank
.....rest: see xact3wb.h }
```
dwFlags (= Bank flags) = info about: is it a in-memory or streaming wavebank; are EntryNames and/or SeekTables inlcuded?....
dwEntryCount = number of wave files in the wavebank
2. ENTRYMETADATA
In the ENTRYMETADATA region, there is for each wave file a WAVEBANKENTRY which contains the following infos for the wave file:
Flags (has Loops; Enable stream read-ahead)
Duration(e.g. a 10 second long wave with sampling rate 44100 Hz has Duration=441000) 
WAVEBANKMINIWAVEFORMAT (Typ (PCM,ADPCM,XMA,WMA); number of Channels; sampling rate (e.g.44100Hz); Align; 8or16bit PCM))
PlayRegion (Region within the wave data segment (=ENTRYWAVEDATA) that contains this entry)
LoopRegion
5. ENTRYWAVEDATA
the actual data as referenced by PlayRegion of the WAVEBANKENTRIES (/End-of-summary   )

> Reply from FordGT90Concept
>
> 
-Every deflated section appears to be exactly 929 or 1487 bytes in length (depends on file)

Name that compression!WMA  (quote from xact3wb.h: static const DWORD aWMABlockAlign[] = {  929, 1487,...}

So we seem to have the same problem, FordGT90Concept: we both try to extract .wma-files from .xwb wavebanks. But with different strategies: you try to decompress the wma file data in order to write them to .wav files, I try to simply write the compressed data and create appropriate WMA-Headers in order to have .wma files as a result.

This is what I did so far: I looked into the (very long and not very usefull) [ASF/WMA-Specification](http://www.microsoft.com/windows/windowsmedia/forpros/format/asfspec.aspx).
A .wma file contains at least 4 Objects: FileProperties Object,StreamProperties Object, Header Extension Object and DATA OBJECT (consisting of Data Packets, each Data Packet has some header/info bytes). With the infos from WAVEBANKENTRY of the file and xact3wb.h, I'm (almost) able to write the first 3 Objects. The biggest problem is the WMA Data Object. I hoped that the PlayRegion, i.e. the data region of a file in the ENTRYWAVEDATA Region simply contains the WMA DATA OBJECT for a wma file, but this is not the case. As you already noticed:

> Reply from FordGT90Concept
>
> 
All WMA files start with 0500, 0600, or 0700. The ones that are obviously music actually have the first 17 bytes matchUnfortunately, these bytes seem to have nothing to do with the header bytes of typical .wma-Data Packets 

So, can anyone give  hints on the Data Regions for wma data in the .xwb (especially the meaning of thos 0500, 0600, 0700 at the beginning) or/and the Data Packets in .wma files...? Please   !

PS: Sorry for the long post!
PS2: If anyone needs help on .XSB (Soundbank) files - I've 'decrypted' most of the file format. But a complete description would result in a posting at least twice as long as this one   
PS3:

> Reply from FordGT90Concept
>
> The compression itself could be as simple as zlib inflateUnfortunately not, I'm afraid. It's rather like the mp3 compression:
"The [WMA format](http://mp3.about.com/od/profiles/p/WMA_Profile.htm) uses a lossy compression algorithm. It is a transform codec that uses a psychoacoustics model and employs the modified discrete cosine transform (MDCT) to process the WMA bit stream."
## Post #11
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-09-02T12:14:01+00:00
- Post Title: Saints Row 2 XWB compressed wave

@FordGT90Concept: In case you ever look into this thread again: could you re-upload the .xwb file? It's no longer on speedyshare. I think, I succeeded in extracting the wma streams  . aluigi already mentioned the key to the solution: xWMA. First I tried to transform the wma streams from my .XWBs to  valid .wma files...rather impossible, because there are so many undocumented entries/codec specific data  in the WMA file format. xWMA is a lightweight wrapper for wma bitstreams and has (especially compared to .wma) a really easy [file format](http://msdn.microsoft.com/en-us/library/ee415832%28v=VS.85%29.aspx). The only difficulties were to calculate the correct values for AvgBytesPerSec, BlockAlign and the DPDS chunk from the infos given in the .xwb file.
The resulting xWMA file can be converted to playable .wav files using Microsofts xwmaEncode. This worked for my xwb files
## Post #12
- Username: GodOfWar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 05, 2010 11:35 am
- Post datetime: 2010-09-04T01:36:21+00:00
- Post Title: Saints Row 2 XWB compressed wave

> Reply from Liandril
>
> could you re-upload the .xwb file?

i can upload files  you need files from x360 or PC version?
## Post #13
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-09-04T13:53:51+00:00
- Post Title: Saints Row 2 XWB compressed wave

Thanks, GodOfWar.. so far, I only worked with PC versions... so the PC version would be better. So far, my tool supports only new versions of .xwb (Format Version 42-44), so it will probably not work with the Saints Row 2 .xwb files. But if I find the time, I'll try to adjust it.
## Post #14
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-09-22T22:12:26+00:00
- Post Title: Saints Row 2 XWB compressed wave

Hm, I'm still looking for a re-upload of the .xwb (PC version) mentioned above. So if anybody has it.. I'd like to test, if my tool is able to extract the xwma files to wav...
## Post #15
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-14T08:48:40+00:00
- Post Title: Saints Row 2 XWB compressed wave

> Reply from Liandril
>
> Hm, I'm still looking for a re-upload of the .xwb (PC version) mentioned above. So if anybody has it.. I'd like to test, if my tool is able to extract the xwma files to wav...

I've hosted the mus 420.xwb from Saints Row 2 on my site for you:
[http://finalack.com/Idol/mus_420.xwb.rar](http://finalack.com/Idol/mus_420.xwb.rar)

I release and maintain the Gentlemen of the Row mod for Saints Row 2 PC, and was recently able to get custom missions scripted and working. I would love to be able to add my own sound banks for them, in addition to extracting the current ones if possible.

Hope to hear some good news with your tool, and would be happy to host any other audio files you might need. Just say the word. 

More Saints Row 2 modding info here if anyone's interested:
[http://idolninja.com](http://idolninja.com)
[http://community.saintsrow.com/forums/topic/43953](http://community.saintsrow.com/forums/topic/43953)

EDIT:
I'm not sure if this helps, but the xml table files in the game reference the banks in the following format:

```
        <Name>1036fou_A</Name>
        <Tracks>
            <Music_Set>
                <Track>
                    <Filename>BarringtonLevy_HereICome.wav</Filename>
                    </Track>
                <Play_Time>3.44</Play_Time>
                </Music_Set>
            <Music_Set>
                <Track>
                    <Filename>BeanieMan_WhoAmI.wav</Filename>
                    </Track>
                <Play_Time>3.16</Play_Time>
                </Music_Set>
            <Music_Set>
                <Track>
                    <Filename>BornJamaicans_BoomShakATack.wav</Filename>
                    </Track>
                <Play_Time>4.04</Play_Time>
                </Music_Set>
            <Music_Set>
                <Track>
                    <Filename>BujuBanton_HeyBoy.wav</Filename>
                    </Track>
                <Play_Time>2.18</Play_Time>
                </Music_Set>
            </Tracks>
        <Play_Order>In Order</Play_Order>
        <Min_Dist>0.5</Min_Dist>
        <Max_Dist>30.0</Max_Dist>
        <Volume>0.55</Volume>
        <_Editor>
            <Category>Radio Stations:FOUR-20 103.6</Category>
            </_Editor>
        <AudioBanks>MUS 420</AudioBanks>
        </Music_Set>
```


The <AudioBanks> element entry of MUS 420 is a reference to audio_banks.xtbl's Name element as defined in the TableDescription at the end of the file. The Description reads: "Required field if the music comes from XACT... Leave unchecked if it comes from the volition music crunch tool."

The entry in audio_banks.xtbl:

```
        <Name>MUS 420</Name>
        <Streaming>
            <SectorRead>128</SectorRead>
            </Streaming>
        <_Editor>
            <Category>Music:Radio Stations</Category>
            </_Editor>
        </AudioBanks>
```


The TableDescription for the elements in the audio_bank.xtbl is:

```
    <Name>AudioBanks</Name>
    <Type>TableDescription</Type>
    <Display_Name>Audio Banks</Display_Name>
    <Element>
        <Name>Name</Name>
        <Type>String</Type>
        <Display_Name>Bank Names</Display_Name>
        </Element>
    <Element>
        <Name>Streaming</Name>
        <Type>Element</Type>
        <Description>Every cue from this bank is streamed when needed.</Description>
        <Required>false</Required>
        <Element>
            <Name>SectorRead</Name>
            <Type>Int</Type>
            <Display_Name>Sector Read</Display_Name>
            <Description>The size of a DVD sector is 2048 bytes. The optimal DVD size is a multiple of 16 (1 DVD block = 16 DVD sectors).</Description>
            <Default>16</Default>
            <MinValue>16</MinValue>
            <MaxValue>512</MaxValue>
            </Element>
        </Element>
    <Element>
        <Name>Managed</Name>
        <Type>Element</Type>
        <Description>The wavebank is streamed into memory when needed. Effectively causing it to be always in memory.</Description>
        <Required>false</Required>
        </Element>
    </TableDescription>
```


I have updated the hosted mus_420.xwb.rar with both table files for reference.
## Post #16
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-10-14T21:10:35+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Hi IdolNinja,

thanks for the files! So far, my tool just extracts .XWBs and provides info about .xsb/.xwb. Inserting a cue (see explanation below) into an .xsb is difficult, because .xsb uses (among other obstacles) a hash function...and I don't know, what this function looks like. But the good news is: extracting the Saint Row 2 .XWBs to .WAVs works (and therefor the subject/main question of this thread is solved   ).

1. Extracting .XWBs containing xWMA (for .xwbs containing ADPCM or XMA use aluigis unxwb !)
As mentioned some postings above, my tool extracts .xwb files to valid .xwma files. You need xWMAEncode (part of [Microsofts DirectX SDK](http://www.microsoft.com/downloads/details.aspx?FamilyID=24a541d6-0486-4453-8641-1eee9e21b282&displaylang=en)  or download it directly from [here](http://www.enbclan.com/?page=downloads)  (last link, on the bottom of the page)) in order to convert xWMAs (there's almost no player for .xwma) to "normal" .wav files. Just copy my xactxtract.exe and the downloaded xWMAEncode.exe into the directory with the .xwb files and type (command line):
xactxtract.exe -x2 *.xwb
This tells xactxtract to extract and convert all .xwb files in the directory. To be more precisely, xactxtract will:
1. create a directory for each .xwb file (e.g. for "MUS 420.xwb" a directory "MUS 420" will be created) 
2. extract all .xwma files from the .xwb to that directory
3. call xWMAEncode for each file, i.e. all .xwma files will be converted to .wavs
4. delete all .xwma files (because they are no longer needed)
So in the end you'll have a directory containing playable .wavs for each .xwb 
For the Saint Row 2 .xwbs, my tool will show a warning, because it wasn't written for this .xwb version, but you can just ignore this warning (unfortunately, the output messages of my tool are mostly in German, sorry).

[Download link for XACTxtract](http://ul.to/9w27vl1z)

2. Thoughts & infos about inserting own wave files into Saint Row 2...
(I'll try to keep the explanations as short as possible, first the basics:)

An .xwb Wavebank is a collection of wavs (pcm, adpcm, xma, xWma). In Saint Row 2 (at least in your "MUS 420.xwb") only xWma is used.

The .xsb (Soundbanks) contains infos/commands, when and how to play the wavs. There are 4 types of such commands: events, tracks, sounds and cues:
A track contains a "link" to ONE wave and events. The simplest case is: the event "play" followed by a link to the wavebank (e.g. "MUS 420.xwb") and the wave number in the wavebank.
A sound contains one or more tracks and properties (volume, category...)
A cue contains one or more Sounds and properties (e.g.playing possibility for each sound, crossfading,...)

Usually, each cue has a cuename - so to speak the "interface" between game and .xsb files: the game calls the XACT engine with the cuename, the XACT engine looks up the .xsb files and plays the cue. In Saint Row 2, the cuename infos obviously were left out... this is strange, because it's more work for the developers. So some info, that usually is in the .xsb files, is now in the .xtbl tables you included. REALLY strange is, that there seem to be no "links" to the cues in the tables:
the audio_banks.xtbl just describes the connection between Sound/Wavebanks and Categories, whereas the music.xtbl consists of elements (<Music_Set>) containing info that are usually in the cues.
It seems to me that 
EITHER the developers tried to avoid using the .xsb files and created their own way (.xtbl) to adress the .xwbs
OR the .xtbl tables are relicts of the production period, but then: how does the game address the .XSBs without cuenames?
In short: It's possible to create your own .xsb/.xwb, but I can't tell you, how the game adresses the soundbanks
## Post #17
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-16T02:26:32+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Liandril, 

I did some testing and your tool works perfectly on all the xwbs we were having problems with like the radio commercials and music.
## Post #18
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-16T19:00:57+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

There seems to be one xwb that has a problem and gives an "Out of Memory" error. I've confirmed the error with two of the other modders who are using your new tool. I've uploaded it here if you would like to take a look at it:
[http://finalack.com/Idol/wazza/SR2_CUTSCENES.xwb.rar](http://finalack.com/Idol/wazza/SR2_CUTSCENES.xwb.rar)

The rest of the xwb files have been confirmed extractable. 

Also, if you're curious, the xtbl files do at least partially control the playback and cues instead of the xsb. I can change them and see/hear the results in-game. There also seems to be more instructions in the exe itself which looks to be that missing link for how the engine works with the banks.

EDIT:
Would you also please consider releasing the source? Thanks!
## Post #19
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-10-16T23:57:11+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

So I was basically trying to decompress an xWMA file?

I always take the hard way because it the most fun. XD
## Post #20
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-10-17T21:43:25+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from IdolNinja
>
> The rest of the xwb files have been confirmed extractable.
Ah, very good   
And thanks for the "Out of Memory" bug report, too. I know, where the problem is..but I can't solve it. It's a bug with PAR::Packer (a perl module I'm using for building the executable). But I managed to extract SR2_CUTSCENES.xwb. Wow, this is the largest .xwb I've ever seen. And the extracted & converted .wav files need 4.5 GB!  

> Reply from IdolNinja
>
> Also, if you're curious, the xtbl files do at least partially control the playback and cues instead of the xsb. I can change them and see/hear the results in-game.
OK, that's interesting. I wonder, if the .xsb files are used at all. Maybe you could do a test (as I don't have the game):
I modified the "MUS 420.xsb" so that always - that means, whenever you turn to "Radio 420" (? I suppose, it represents a radio channel in the game) MUS 420_00009.wav is played. MUS 420_00009.wav is the first "non music" file in "MUS 420.xwb".. the one, where the Radio DJ says something like: 'Tis next artist's been spittin our tracks...' - so that's what you will (hopefully) hear when turning to Radio 420, IF the .xsb files are used (and IF I modified them correctly). If there is no difference in the game, then the .xsb files probably aren't used at all.

 MUS 420.rar
(356 Bytes) Downloaded 35 times



> Reply from FordGT90Concept
>
> I always take the hard way because it the most fun
Me too  ... for almost one month I tried the 'hard way': building .wma files (=very difficult and NOT funny) from the (x)wma data in the .xwb. Then I stumbled across aluigis mention of xWMA... one hour later I had written a routine to produce a valid xWMA header.
## Post #21
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-17T22:21:42+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Apparently the .xsb files are used. Your modified one for MUS 420 resulted in exactly what you thought it would. That same DJ track just repeats over and over on that station.
## Post #22
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-10-18T22:46:54+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

What vpp_pc file are those xtbl files in?
## Post #23
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-19T00:09:56+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from FordGT90Concept
>
> What vpp_pc file are those xtbl files in?

The xtbl files containing audio info are in common.vpp_pc.
## Post #24
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-10-19T00:15:04+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from IdolNinja
>
> Apparently the .xsb files are used. Your modified one for MUS 420 resulted in exactly what you thought it would. That same DJ track just repeats over and over on that station.
Over and over? OMG, I hope you didn't get an earache   

Hmm... then the playback is controlled by the xtbl files AND the cues in the xsbs ...and the "link" between those two is missing. Sounds difficult. I think the easiest way to insert (well, rather replace) sounds into the game would be the following:
I could try to expand the program so that it replaces wavs in the Wavebanks (.xwb) with an option like this:
xactxtract -r "MUS 420.xwb" 5 mywav.wav
meaning: Wave Nr. 5 in the "MUS 420.xwb" is replaced by mywav.wav
Would this help in modding the game? 
The problem is: this would take quite some time....and especially in the next 1-2 months I'll have VERY little time  

Edit:
If you don't want to wait that long, you could try to create your own modified .xwb file:
1) unpack the .xwb
2) replace the .wavs you want to change with your own .wavs
3) download from Microsoft: DirectX SDK from Mar2008, because this one creates .xwb files of the same version used in Saints Row 2 (Tool version 44, file format version 42)
4) try to follow the instructions [here](http://forum.xentax.com/viewtopic.php?f=17&t=4509) and (more detailed) [here](http://msdn.microsoft.com/en-us/library/ee416032%28v=VS.85%29.aspx)
Problem with this way is, of course, that you have to include the WHOLE .xwb in your mod. If I succeed in adding the functionality to my script, then you only have to include xactxtract and the .wavs to your mod.
## Post #25
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-19T00:32:15+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

It would help SR2 modding tremendously to be able to insert our own sound files. At the most basic beginning, we could begin importing our own custom music stations.

Would your planned tool also work on replacing adpcm and xma? I wasn't able to find the cell phone calls that happen in-game and I'm wondering if maybe they are in adpcm or wma format instead of wav and I just missed them when extracting/looking with unxwb a while back. The reason I'm wondering is that these phone calls usually give direction to the player during missions and would be my highest priority to get working for custom missions.

Ideally, I would like to be able to create and add my own sound banks, but that might not be doable with the missing links in the exe. So, the new missions could certainly just use existing banks with our own wav files inserted using your planned updated tool (if you have time )

Also, sorry to hear about your busy schedule. Real life often gets in the way of fun projects like this. Any effort you could make on this would certainly be appreciated. 

EDIT:
I'm looking through everything now to try and locate those cell phone calls.
## Post #26
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-10-19T01:07:14+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

I'd guess phone calls are somewhere in audio.vpp_pc.  The Gen X radio station, for some reason, is in audio.vpp_pc instead of the music#.vpp_pc file.
## Post #27
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-19T01:19:03+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Yeah, all the audio seems to be scattered. I'm wondering what bank they are in though. Here's what I've come up with so far:

AUDIO.VPP_PC contains:
* Ambients.xwb - background noise
* Animation.xwb and Animation Debug.xwb - sound fx
* All the vehicle xwb files for stuff like engine rev, horns, etc
* Movement.xwb and Movement Debug.xwb - Nothing extracted. I think they might be in adcpm format that you'll need unxwb for
* MUS GENX.xwb - The music and DJ spots from the GenX radio station
* Other inMemory.xwb and Other InMemory Debug.xwb - Misc sounds like end screen unlock sounds
* Other Streaming.xwb - Sound FX: Explosions, radio, static, fireworks, etc
* SR2_ACTIVITY_CUTSCENES - All activity cutscene audio
* Weapons.xwb and Weapons Debug.xwb - Weapon sounds

MUSIC1.VPP_PC contains:
* MUS K12.xwb - K12 electronica station dj spots and music
* MUS KLASSIC.xwb - Classical music station dj spots and music
* MUS KRHYME.xwb - Rap and hip hop station dj spots and music
* MUS KRUCH.xwb - Metal station dj spots and music

MUSIC2.VPP_PC contains:
* MUS 420.xwb - Reggae station dj spots and music
* MUS DISPATCH.xwb - police chatter
* MUS EZZZY.xwb - Easy listening station dj spots and music
* MUS FUNK .xwb - Funk station dj spots and music
* MUS MIX.xwb - 80s station dj spots and music
* MUS MUSIC.xwb - nothing (4kb file)
* MUS SHARED.xwb - All commercials and main menu pause music
* MUS UNDERGROUND - pirate radio dj spots and songs
* MUS WORLD - World music station dj spots and music

MUSIC3.VPP_PC contains:
* SR2_VOC_AF.xwb - Asian female npc random voices
* SR2_VOC_AM.xwb - Asian male npc random voices
* SR2_VOC_BF.xwb - Black female npc random voices
* SR2_VOC_BM.xwb - Black male npc random voices
* SR2_VOC_HF.xwb - Hispanic female npc random voices
* SR2_VOC_HM.xwb - Hispanic male npc random voices
* SR2_VOC_WF.xwb - White female npc random voices
* SR2_VOC_WM.xwb - White male npc random voices

MUSIC 4.VPP_PC contains:
* MUS_AMBIENT.xwb - store music, barbershop quartet, guitar player, etc
* SR2_CUTSCENES.xwb - "out of memory" error trying to extract
* SR2_VOC_SP.xwb - phone answering machine messages
## Post #28
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-10-19T01:32:31+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from IdolNinja
>
> Would your planned tool also work on replacing adpcm and xma? I wasn't able to find the cell phone calls that happen in-game and I'm wondering if maybe they are in adpcm or wma format instead of wav and I just missed them when extracting/looking with unxwb a while back.
Yes, replacing adpcm and xma should be possible. Unfortunately, my tool just extracts (x)WMA and PCM so far... I wanted to add extracting & converting for ADPCM, but didn't (and don't) have the time   .BTW: If you want to have a detailed list with infos about the .xwbs, just type:
xactxtract.exe *.xwb >xwb-info.txt
and you'll get a text file with informations  (type (wma,xma,adpcm,pcm), channels,...) for every wave in the wave banks. But when I look at your overview, then it will be a LONG text file   

> Other inMemory.xwb seems like a good guess for the phone calls to me (waves that are used often are usually kept in an in-memory wave bank)
## Post #29
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-10-19T09:15:48+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

There really aren't that many phone calls in SR2 (compared to, say, GTA4).  They could theoretically be in any XWB file.  Ones that are part of a mission are probably in cutscenes.  The rest are probably in VOC_SP.


I need to get xWMA support into my code so I can get that SR2_CUTSCENES extracted.  Then my focus will shift to giving everything proper titles (from xtbl and, if necessary, xsb).  I have no idea when I'll get around to it though.
## Post #30
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-19T17:18:28+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from FordGT90Concept
>
> There really aren't that many phone calls in SR2 (compared to, say, GTA4).  They could theoretically be in any XWB file.  Ones that are part of a mission are probably in cutscenes.  The rest are probably in VOC_SP.

I need to get xWMA support into my code so I can get that SR2_CUTSCENES extracted.  Then my focus will shift to giving everything proper titles (from xtbl and, if necessary, xsb).  I have no idea when I'll get around to it though.

SR2_VOC_SP seems to be only the phone answering messages when you call a business using the phone numbers on signs scattered throughout the game. I'm still looking, but I think you may be on the right track with the SR2_CUTSCENES bank.

Now that I think about it, it is both incoming phone calls and also triggered in-game dialogue between characters that drives some of the missions, and these are probably all located together in the same bank. The lua scripts use a couple of different functions to trigger audio conversations:

Example of a function call in a mission script triggering dialogue between two characters. 

```
audio_play_conversation_in_vehicle(Tss03_gat_player_drive_conversation)
```


^This is the conversation between you and Gat in mission 3 (tss03.lua) where you drive to Redlight District to clean out the bums from under the church:

Example of a function call to play a triggered cell phone conversation:

```
audio_play_conversation(VOICE_INTRO_PHONECALL, INCOMING_CALL)
```


^This is the phone call you receive from Shaundi at the start of the Brotherhood mission "The Enemy of my Enemy" (bh09.lua.) The VOICE_INTRO_PHONECALL global constant is assigned the following values:

```
{{"BR09_INTRO_L1", CELLPHONE_CHARACTER, 0},
{"PLAYER_BR09_INTRO_L2", LOCAL_PLAYER, 0},
{"BR09_INTRO_L3", CELLPHONE_CHARACTER, .25},
 {"PLAYER_BR09_INTRO_L4", LOCAL_PLAYER, .25},
{"BR09_INTRO_L5", CELLPHONE_CHARACTER, .25},
{"PLAYER_BR09_INTRO_L6", LOCAL_PLAYER, .25},
{"BR09_INTRO_L7", CELLPHONE_CHARACTER, .25},
{"BR09_INTRO_L8", CELLPHONE_CHARACTER, 0},
{"PLAYER_BR09_INTRO_L9", LOCAL_PLAYER, .25},
{"BR09_INTRO_L10", CELLPHONE_CHARACTER, 0},
{"PLAYER_BR09_INTRO_L11", LOCAL_PLAYER, .25}}
```


The conversation is broken up this way so that any of the six chosen voices for the main character can be inserted into the conversation.

And here is the actual code of these two audio functions from ug_lib.lua:

```
   if ( cellphone_call == nil ) then
      cellphone_call = NOT_CALL
   end

   -- Open with the cellphone, if this is a cellphone
   -- conversation
   if ( cellphone_call == INCOMING_CALL ) then
      cellphone_animate_start_do()
      delay(0.5)
   elseif ( cellphone_call == OUTGOING_CALL ) then
      cellphone_animate_start_do()
      audio_play( CELLPHONE_OUTGOING, "foley", true )
      delay(0.5)
   end

    -- Build a list of characters that will be tested for readyness before any line in the
    -- conversation is played. We only use this list for NOT_CALL conversations.
    local character_list = {}
    if (cellphone_call == NOT_CALL) then
        for segment_index, dialog_segment in pairs( dialog_stream ) do
            local speaking_character = dialog_segment[DIALOG_STREAM_CHAR_NAME_INDEX]
            character_list[speaking_character] = speaking_character
        end
    end

    local function dialog_characters_ready()
        for i,character in pairs(character_list) do
            if (not character_is_ready_to_speak(character)) then
                return false
            end
        end
        return true
    end

   for segment_index, dialog_segment in pairs( dialog_stream ) do
      local audio_name = dialog_segment[DIALOG_STREAM_AUDIO_NAME_INDEX]
      local speaking_character = dialog_segment[DIALOG_STREAM_CHAR_NAME_INDEX]
      local delay_seconds = dialog_segment[DIALOG_STREAM_DELAY_SECONDS_INDEX]
        local anim_action = dialog_segment[DIALOG_STREAM_ANIM_ACTION_INDEX]

      -- Play the dialog stream for each character
      if ( cellphone_call == NOT_CALL ) then
         repeat
            thread_yield()
         until ( dialog_characters_ready() )

            local playing_action = (    (anim_action ~= nil)
                                                and (not character_is_in_vehicle(speaking_character)) 
                                                and (not character_is_combat_ready(speaking_character))
                                                and (not mesh_mover_wielding(speaking_character))
                                                and (vehicle_exit_check_done(speaking_character))
                                                and (vehicle_enter_check_done(speaking_character))
                                            )

            if (playing_action ) then    
                inv_item_equip(nil,speaking_character)
                action_play(speaking_character, anim_action, anim_action, true, 0.0, true)
            end
         audio_play_for_character( audio_name, speaking_character, "voice", false, true)
         delay( delay_seconds )
      -- Cellphone calls are different - just play the audio, don't use the character function unless
      -- it's the player.
      else
         -- For players, use audio_play_for_character so that the tag can be correctly translated
         if (    speaking_character ~= nil and character_is_player( speaking_character ) ) then
            -- Don't play lines unless and until the player is alive and in a state to deliver them
            repeat
               thread_yield()
            until ( character_is_ready_to_speak( speaking_character ) )
            audio_play_for_character( audio_name, speaking_character, "voice", false, true)
         elseif ( speaking_character == CELLPHONE_CHARACTER or speaking_character == nil ) then
            -- for_cutscene = false, blocking = true, variant = nil, voice_distance = nil, cellphone_line = true
            audio_play_for_character( audio_name, LOCAL_PLAYER, "voice", false, true, nil, nil, true )
         else
            script_assert( false, "You must specify CELLPHONE_CHARACTER as the speaking character ( or leave it at nil ) for the other side of a cellphone conversation." )
             audio_play( audio_name, "voice", true )
         end
         delay( delay_seconds )
      end
   end

   -- Close the cellphone, if this was a cellphone
   -- conversation
   if ( cellphone_call ~= NOT_CALL ) then
      cellphone_animate_stop_do()
   end
end
```


```
--
-- dialog_stream: A table containing dialog stream segments. Each segment has a speaking character name,
--                the name of the audio to play, and a delay in seconds after the audio is played for the
--                next one to be played. Conversation will not exectute unless the speaker is in a vehicle.
--
function audio_play_conversation_in_vehicle(dialog_stream)
    -- Loop through the table conversation...
   for segment_index, dialog_segment in pairs( dialog_stream ) do
      local audio_name = dialog_segment[DIALOG_STREAM_AUDIO_NAME_INDEX]
      local speaking_character = dialog_segment[DIALOG_STREAM_CHAR_NAME_INDEX]
      local delay_seconds = dialog_segment[DIALOG_STREAM_DELAY_SECONDS_INDEX]

        -- Conversation requires them to be in a vehicle
        while (not character_is_in_vehicle(speaking_character)) do
            thread_yield()
        end

      -- Play the dialog stream for each character
        audio_play_for_character(audio_name, speaking_character, "voice", false, true)
        delay(delay_seconds)
   end
end
```


And finally the global constants that these functions are using in ug_lib.lua:

```
-- These indices are the indices of each segment of a dialog stream
-- in the dialog stream table.
DIALOG_STREAM_AUDIO_NAME_INDEX = 1
DIALOG_STREAM_CHAR_NAME_INDEX = 2
DIALOG_STREAM_DELAY_SECONDS_INDEX = 3
DIALOG_STREAM_ANIM_ACTION_INDEX = 4

-- Types of conversations
NOT_CALL = 1
OUTGOING_CALL = 2
INCOMING_CALL = 3

-- Used in a dialog stream to denote that this is a character speaking through the cellphone
CELLPHONE_CHARACTER  = "cellphone character"

-- Ring sounds
CELLPHONE_INCOMING = "SYS_CELL_RING_1"
CELLPHONE_OUTGOING = "SYS_CELL_RING_OTHER"
```
## Post #31
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-10-19T17:36:20+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

The LUA scripts aren't compiled?    Wow, they really did rush on the PC port. XD
## Post #32
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-19T18:46:11+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

There's a reason why it's considered one of the worst ports in PC gaming history.   

Good for us though since we can dig in and mod in changes easily. I've actually fixed a few of the mission scripts already that had crashing and other problems. Plus, it's easy to create new missions with a bit of lua knowledge.
## Post #33
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-10-19T19:13:05+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Hey!  It's an excellent game with shoddy code. Hopefully they'll put more effor into the PC version of Saints Row 3. XD

I'd say Dreamfall: The Longest Journey was the worst port.  The mouse X-axis is backwards with no way to change it.  So, so, SO annoying!!!! :'(


Yeah, very good for us.  Tropico 3 uses compiled LUAs of a custom variety and they are a real PITA to decompile.  You also get to see all the dev comments, w00t!
## Post #34
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-10-20T00:18:33+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from FordGT90Concept
>
> The LUA scripts aren't compiled?    Wow, they really did rush on the PC port. XDOr they wanted to do the modding community a favor   

> Reply from IdolNinja
>
> I'm still looking, but I think you may be on the right track with the SR2_CUTSCENES bank.OK, so the SR2_CUTSCENES waves are really needed, right? I tried to do a workaround. For .XWBs causing the "Out of memory" problem, you have call the tool with the new option "-safe"... this option is needed, because the script cannot tell, if a .xwb will cause problems, because (as I already wrote) the problem is not in the script, but in the program I use to translate the script into an executable. It seems to work, but I'm not too happy with this fix - plus, I almost didn't test it. So I wouldn't call it a "stable version"...

[xactxtract v0.97](http://www.file-upload.net/download-2904129/xactxtract-v0.97.rar.html)

Unpack 'normal' .XWBs as before:
xactxtract.exe -x2 *.xwb

For .XWBs that crash with "Out of memory" error(like SR2_CUTSCENES), use the -safe option:
xactxtract.exe -safe -x2 SR2_CUTSCENES.xwb

> Reply from FordGT90Concept
>
> Then my focus will shift to giving everything proper titles (from xtbl and, if necessary, xsb)The .xsb files won't be much help, I'm afraid, because (unlike in other games), they don't have cue names included
## Post #35
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-20T18:27:22+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

The new version of the tools was able to successfully extract the cutscene audio bank using the -safe param. 

Going through all of them now!
## Post #36
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-10-23T14:25:13+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Hi IdolNinja, 

just an idea in case you haven't found the cell phone calls yet: yesterday I followed your link, took a quick look at the SR2 Modding Site (very nice community and you're doing a great job over there  !) and found [this thread](http://community.saintsrow.com/forums/topic/43067) of yours. You mentioned a table called foley.xtbl there. From the sample entry you posted, it looks similar to the music.xtbl. Have you tried searching this foley.xtbl for something like "phone"? 
 In case there is such an entry, it might lead you directly to the wave bank with the cell phones.
## Post #37
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-10-24T05:34:29+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

@Liandril

Thank you for the kind words. It is a very open community that is built on the principles of sharing knowledge and welcoming newcomers. I couldn't ask for a better group of people to work with. 

Good idea about foley.xtbl, but I took a look and unfortunately it only contains sound fx rather than any kind of dialogue. I will find it eventually though. I'm determined!
## Post #38
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-12-04T20:45:06+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Hi All,

IMPORTANT: I only just found out this about the two versions of xactxtract I posted in this thread:

Virus scanners report they found the "Worm/Autorun bqef SIGNATURE" on newer versions of xactxtract (v0.96, v0.97). I think/hope/am quite sure it's a false alert, because I scanned my whole system and the only "infected" files were these two xactxtract executables. Therefor I think that compiling my Perl script (xactxtract is actually a Perl script) with PAR::Packer accidently produces the above signature in the resulting executables (i.e. in v0.96 & v0.97 of xactxtract.exe). But if you want to be sure, better don't use versions 0.96 & 0.97 and use [this old version (0.95)](http://www.file-upload.net/download-3023539/xactxtract-v0.95.zip.html)instead. I scanned this version (0.95) today (2010-dec-04) with several up-to-date scanners (including AntiVir, AVG, NOD32 and Kapersky) and they all found/reported nothing.
If you want to use v0.95 with Saints Row 2, then you first have to remove blanks from the .xwb file names, i.e. rename "MUS 420.xwb" to MUS420.xwb

BTW: I didn't forget about the "-replace" option in order to replace waves in a .xwb file ... but I really have absolutely no time at the moment.
## Post #39
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2010-12-18T09:18:48+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Liandril,

Thanks for the heads up. It's likely a false positive, but better safe than sorry.

I am still very much looking forward to your revised tool so I can start replacing dialogue for the custom missions I'm scripting, but completely understand how real life can you leave you with little free time. I just wanted to let you know that I still check in regularly to see if there's any progress and hope to see it eventually completed.
## Post #40
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2011-01-08T13:26:37+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Hi IdolNinja,

I'm glad to hear that you're still there. I was very sad to see what happened to you at Volition. Sorry that I still can't provide a new version of xactxtract. Today is the first(!) day within the last 2 months that I had a little time to look into the code again. I made some progress, but also encountered some unexpected problems...just wanted to let you know that I didn't forget about it.
## Post #41
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2011-01-09T12:30:20+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Thanks for continuing your work on the tool. 

It is a shame what happened on the Volition forums, but Saints Row 2 modding isn't dead just yet. I'm still working personally with some of the other modders like Minimaul and Innocent Sam and even went ahead and made all beta releases of the mod public on my site so fans can check out new features immediately without having to wait between releases:
[http://idolninja.com](http://idolninja.com)

I'm really exited about the original content that I'm working on with the new missions that should be released shortly. It will even better once I can get my own audio in there too!
## Post #42
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2011-01-13T21:39:10+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from Liandril
>
> IdolNinja wrote:Would your planned tool also work on replacing adpcm and xma? I wasn't able to find the cell phone calls that happen in-game and I'm wondering if maybe they are in adpcm or wma format instead of wav and I just missed them when extracting/looking with unxwb a while back. 
Yes, replacing adpcm and xma should be possible. Unfortunately, my tool just extracts (x)WMA and PCM so far... I wanted to add extracting & converting for ADPCM, but didn't (and don't) have the time   .BTW: If you want to have a detailed list with infos about the .xwbs, just type:
xactxtract.exe *.xwb >xwb-info.txt
and you'll get a text file with informations  (type (wma,xma,adpcm,pcm), channels,...) for every wave in the wave banks. But when I look at your overview, then it will be a LONG text file
I noticed a bug in your 0.97 xactxtract.exe app when dealing with raw WAV format in SR2.  Example: MUS MIX_00001.wav

Surprisingly, WAV is about the only format I could get to work with my code. XD

Anyway, there appears to be a problem in the header and at the end of the file.  In the header, there is a problem at offset 28 ([Byte Rate](https://ccrma.stanford.edu/courses/422/projects/WaveFormat/)) and offset 32 (Block Align).

Working Byte Rate: 88200 ( 22050 * 2 * 16 / 8 )
Nonworking Byte Rate: 132300

Working Block Align: 4  ( 2 * 16 / 8 )
Nonworking Block Align: 6

Basically, it looks like you got the math wrong in calculating those two values.  Working formulas:
Byte Rate: SampleRate * NumChannels * BitsPerSample/8
Block Align: NumChannels * BitsPerSample/8

That should be a quick fix for you. 

Edit: some songs have 1 channel and 32000 Byte rate so it is important that it is calculated correctly.


The other problem is that the file isn't long enough on your version.

Mine is: 20836396
Yours is: 20832300

I'm not sure why yours comes in short.  Maybe your app isn't reading far enough into the file.  Anyway, it would be great if you could get those WAVE bugs fixed.


Edit: Yeah, your app appears to work on all MUS files except the rare songs that are PCM (not a complete list but some that stood out):
MUS MIX 1
MUS MIX 5
MUS MIX 6
MUS MIX 100
MUS SHARED 52

Thanks for that app though.  I dunno if I'm going to finish work on mine now or not since you almost got them all.



...now to go through all the songs and get them proper names.  I'll post a list  of them when done.

172 files...


MUS SHARED_00076-MUS SHARED_00089 are the music files which play with a song where the main character sings to it.  MUS SHARED_00052 is the menu music.  All other "SHARED" files are ads.
## Post #43
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2011-01-14T04:32:26+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Here they are in filename|title|artist format:

```
MUS 420_00001|Who Am I?|Beanie Man
MUS 420_00002|Boom Shak A Tack|Born Jamericans
MUS 420_00003|Hey Boy|Buju Banton
MUS 420_00004|Ganja Smuggling|Eek A Mouse
MUS 420_00005|Krazy|Elephant Man
MUS 420_00006|Heads High|Mr. Vegas
MUS 420_00007|Guns Out|Ninja Man
MUS 420_00008|Picture This|Vybz Kartel
MUS 420_00093|Murder She Wrote|Chaka Demus And Pliers
MUS 420_00094|Stop The Fussing And Fighting|Dennis Brown
MUS AMBIENT_00327|Zombie Uprising Music 1|Saints Row 2
MUS AMBIENT_00328|Zombie Uprising Music 2|Saints Row 2
MUS AMBIENT_00329|Zombie Uprising Music 3|Saints Row 2
MUS AMBIENT_00330|Zombie Uprising Music 4|Saints Row 2
MUS EZZZY_00111|Bachelor Samba|Marc Durst
MUS EZZZY_00112|Berg Und Tal|Gerhard Narholtz
MUS EZZZY_00113|Bossa Cubana|Gerhard Narholtz
MUS EZZZY_00114|Chanson Pour Toi|Alfred Jack
MUS EZZZY_00115|A Cielito Lindo|Carlos Periguez
MUS EZZZY_00116|Coconuts|Gerhard Narholz
MUS EZZZY_00117|Colonie Celeste|Gerhard Narholtz
MUS EZZZY_00118|Dancing On The Avenue|John Cacavas
MUS EZZZY_00119|Dolce Vita|Bruno Bertoli
MUS EZZZY_00120|Face To Face|Sammy Burdson
MUS EZZZY_00121|A Girl Like You|Norman Candler
MUS EZZZY_00122|Jarabe Tapatio|Carlos Periguez
MUS EZZZY_00123|Just Strolling Along|Sammy Burdson
MUS EZZZY_00124|Kalamazoo Style|Oliver Andres
MUS EZZZY_00125|Love For Life|Sammy Burdson
MUS EZZZY_00126|Marvelous Singers Remix|Marc Durst
MUS EZZZY_00127|Naughty But Nice|Walt Rockman
MUS EZZZY_00128|Stereo Cha Cha|Umberto Pagnini
MUS EZZZY_00129|Sunny Day In Heidelberg|Helmuth Brandenburg
MUS EZZZY_00130|Swing Paname|Angel Debarre
MUS EZZZY_00131|Tchoupa Twist|Nicolas Folmer
MUS EZZZY_00132|Tooba Boogie|Otto Sieben
MUS EZZZY_00133|Walkie Talkie|Gerhard Narholz
MUS EZZZY_00134|Whistle Happy|Colin Baldry
MUS FUNK_00000|Don't Get Discouraged|UPC Allstars
MUS FUNK_00001|The Cissy's Thang|The Soul Seven
MUS FUNK_00002|Put A Smile On Time|The Rhythm Machine
MUS FUNK_00003|Funky In Here|Dayton Sidewinders
MUS FUNK_00004|Look What You've Done To Me|Sheila Skipworth
MUS FUNK_00005|You Can Be A Star|Luther Davis Group
MUS FUNK_00006|Street Scene|Leon Mitchison
MUS FUNK_00007|Drugs Ain't Cool|Ebony Rhythm Band
MUS FUNK_00008|Keep Running|Cliff Nyren
MUS FUNK_00009|Gotta Get Your Love|Chocolate Star
MUS FUNK_00010|Trespasser|Bad Medicine
MUS FUNK_00011|Love Fades|Amnesty
MUS FUNK_00107|Wake Up Pt. 1 and 2|Pure Essence
MUS GENX_00067|Hole In The Earth|Deftones
MUS GENX_00068|I Got It|Galactic featuring Lyrics Born
MUS GENX_00069|Let Me In|Hot Hot Heat
MUS GENX_00070|Put Your Money Where Your Mouth Is|Jet
MUS GENX_00071|Teenagers|My Chemical Romance
MUS GENX_00072|Misery Business|Paramore
MUS GENX_00073|Hate|Plain White T's
MUS GENX_00074|MakeDamnSure|Taking Back Sunday
MUS GENX_00075|Coat Of Arms|The Life And Times
MUS GENX_00076|Rock And Roll Queen|The Subways
MUS GENX_00077|All That I've Got|The Used
MUS GENX_00078|Lying Is The Most Fun|Panic! At The Disco
MUS GENX_00155|Knights|Minus The Bear
MUS GENX_00184|Face Down|Red Jumpsuit Apparatus
MUS K12_00000|Through The Hosiery|Crystal Castles
MUS K12_00001|Death Of A Moralist|Daniel Mansury
MUS K12_00002|Sexy Results|Death From Above 1979
MUS K12_00003|We Are Rockstars|Does It Offend You, Yeah?
MUS K12_00004|Crossover Appeal|Guns N Bombs
MUS K12_00005|North American Scum|LCD Soundsystem
MUS K12_00006|Don And Sherri|Matthew Dear
MUS K12_00007|Street Justice|MSTRKRFT
MUS K12_00008|Special Effect|TRS80
MUS K12_00091|Over And Over|Hot Chip
MUS K12_00092|Give Me Every Little Thing|The Juan MacLean
MUS KLASSIC_00111|Arrival of the Queen of Sheba|Georg Friedrich Handel
MUS KLASSIC_00112|Brandenburg Concerto No. 3 - Allegro|Johann Sebastian Bach
MUS KLASSIC_00113|Concerto No. 4 In A|Johann Sebastian Bach
MUS KLASSIC_00114|Coppelia Ballet Suite|Leo Delibes
MUS KLASSIC_00115|Eine Kleine Nachtmusik|Wolfgang Amadeus Mozart
MUS KLASSIC_00116|The Four Seasons No. 1 - The Spring|Antonio Vivaldi
MUS KLASSIC_00117|The Four Seasons No. 2 - The Summer|Antonio Vivaldi
MUS KLASSIC_00118|Haffner Serenade No. 7 In D Major|Wolfgang Amadeus Mozart
MUS KLASSIC_00119|Hungarian Dance No. 5|Johannes Brahms
MUS KLASSIC_00120|Moonlight Sonata|Ludwig Van Beethoven
MUS KLASSIC_00121|Music For The Royal Fireworks (Overture)|Georg Friedrich Handel
MUS KLASSIC_00122|Nutcracker Trepak|Peter Ilyich Tchaikovsky
MUS KLASSIC_00123|Marriage of Figaro (Overture)|Wolfgang Amadeus Mozart
MUS KLASSIC_00124|In The Hall Of The Mountain King|Edvard Grieg
MUS KLASSIC_00125|Anitra's Dance|Edvard Grieg
MUS KLASSIC_00126|Ride of the Valkyries|Richard Wagner
MUS KLASSIC_00127|Sleeping Beauty Waltz|Peter Ilyich Tchaikovsky
MUS KLASSIC_00128|String Quartet In G Major|Wolfgang Amadeus Mozart
MUS KLASSIC_00129|Symphony No. 5 In C Minor - Allegro Con Brio|Ludwig Van Beethoven
MUS KLASSIC_00130|Symphony No. 5 In C Minor - Allegro|Ludwig Van Beethoven
MUS KLASSIC_00131|Symphony No. 40 - 1st Movement|Wolfgang Amadeus Mozart
MUS KLASSIC_00132|Toccata and Fugue In D Minor|Johann Sebastian Bach
MUS KLASSIC_00133|Water Music Suite No. 1 - Overture|Georg Friedrich Handel
MUS KLASSIC_00134|Water Music Suite No. 1 - Presto|Georg Friedrich Handel
MUS KRHYME_00000|One Thing|Amerie
MUS KRHYME_00001|Gangsta Bitch|Apache
MUS KRHYME_00002|What A Thug About|Beanie Sigel
MUS KRHYME_00003|Twinz|Big Punisher Featuring Fat Joe
MUS KRHYME_00004|Good Girl|Chrisette Michelle
MUS KRHYME_00005|Fandango|DJ Quik Featuring B Real
MUS KRHYME_00006|Tell Me Bout It|Joss Stone
MUS KRHYME_00007|Trick Me|Kelis
MUS KRHYME_00008|Hands Up|Lloyd Banks
MUS KRHYME_00009|New York State Of Mind|Nas
MUS KRHYME_00010|So Sick|Ne Yo
MUS KRHYME_00011|Sucker MCs|Run DMC
MUS KRHYME_00012|Ridin In That Black Joint|Wale
MUS KRHYME_00013|I Luv It|Young Jeezy
MUS KRHYME_00121|Me And U|Cassie
MUS KRUNCH_00071|Deadly Sinners|Three Inches Of Blood
MUS KRUNCH_00072|Nothing Left|As I Lay Dying
MUS KRUNCH_00073|Bat Country|Avenged Sevenfold
MUS KRUNCH_00074|Resurrection|Chimaira
MUS KRUNCH_00075|Milk Lizard|The Dillinger Escape Plan
MUS KRUNCH_00076|Unsung|Helmet
MUS KRUNCH_00077|Stars|Hum
MUS KRUNCH_00078|Redneck|Lamb Of God
MUS KRUNCH_00079|Colony Of Birchmen|Mastodon
MUS KRUNCH_00080|Ghosts Of Perdition|Opeth
MUS KRUNCH_00081|Barn Burner|The Agony Scene
MUS KRUNCH_00082|What A Horrible Night To Have A Curse|The Black Dahlia Murder
MUS KRUNCH_00083|Anthem|Trivium
MUS KRUNCH_00084|Woman|Wolfmother
MUS MIX_00000|Take On Me|A-Ha
MUS MIX_00001|Karma Chameleon|Culture Club
MUS MIX_00002|The Reflex|Duran Duran
MUS MIX_00003|The Final Countdown|Europe
MUS MIX_00004|Working For The Weekend|Loverboy
MUS MIX_00005|Land Down Under|Men At Work
MUS MIX_00006|Sister Christian|Night Ranger
MUS MIX_00007|Don't You Forget About Me|Simple Minds
MUS MIX_00008|Everybody Wants To Rule The World|Tears For Fears
MUS MIX_00009|Pretty In Pink|The Psychedelic Furs
MUS MIX_00100|Out of Touch|Hall and Oates
MUS SHARED_00052|Menu Music|Saints Row 2
MUS UNDERGROUND_00000|Don't Call It A Ghetto|The Architects
MUS UNDERGROUND_00001|Western Biographic|Bound Stems
MUS UNDERGROUND_00002|Hazel Street|Deer Hunter
MUS UNDERGROUND_00003|Shoot The Runner|Kasabian
MUS UNDERGROUND_00004|Every Single Line Means Something|Marnie Stern
MUS UNDERGROUND_00005|For Real|Okkervil River
MUS UNDERGROUND_00006|Third Gear Scratch|Shiner
MUS UNDERGROUND_00007|House Of Cards|Shipwreck
MUS UNDERGROUND_00008|Call In The Debts|South Street
MUS UNDERGROUND_00009|Terror|The Rakes
MUS UNDERGROUND_00010|Dead Friends|The Saps
MUS UNDERGROUND_00011|Here's Your Future|The Thermals
MUS UNDERGROUND_00012|And She Would Darken The Memory|The Twilight Sad
MUS UNDERGROUND_00013|Cheer It On|Tokyo Police Club
MUS WORLD_00109|Baidoushka|Robin Jeffrey
MUS WORLD_00110|Bangara Dance|Ravi Shani
MUS WORLD_00111|Brasilian Fiesta|Claudia Figueroa
MUS WORLD_00112|Cigany|Niko Radic
MUS WORLD_00113|Connaught Chase|Greg Knowles
MUS WORLD_00114|Drumjig|Greg Knowles
MUS WORLD_00115|El Viento En La Isla|Liza Carbe
MUS WORLD_00116|Emerald Jig|Ian Clarke
MUS WORLD_00117|Friss A Rozsa|Niko Radic
MUS WORLD_00118|Good Morning Polka|Jan Schneeberg
MUS WORLD_00119|Gypsy Dance|Laszlo Borteri
MUS WORLD_00120|Hot Nights|John Leach
MUS WORLD_00121|Humors Of Glen Dart|Greg Knowles
MUS WORLD_00122|Hungarian Sundance|Friedrich Sehl
MUS WORLD_00123|Mambo De Fito|Liza Carbe
MUS WORLD_00124|Mandilatos|Robin Jeffrey
MUS WORLD_00125|Mountain Hut Landler|Martin Beeler
MUS WORLD_00126|Over The Moor To Maggie|Greg Knowles
MUS WORLD_00127|Schenkt's Ma Mal Was Boarisch|Karl Barthel
MUS WORLD_00128|The Drunkard's Song|Viktor Mastoridis
MUS WORLD_00129|Zahrat El Sahra|Roger Abaji
```
## Post #44
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2011-02-06T15:49:50+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from FordGT90Concept
>
> 
I noticed a bug in your 0.97 xactxtract.exe app when dealing with raw WAV format in SR2.  Example: MUS MIX_00001.wav
Thanks a lot for the bug report, the list and the PM, FordGT90Concept. As I already wrote in the PM: my problem is still that I've no time at all   
As regards the PCM bug: I'm not surprised that there are bugs left. The history of xactxtract is quite funny/sad: My goal was to insert new cues, sounds, tracks into .xsb files. About 60-70% of the time I worked on the project was spent on analyzing the xsb format. Unfortunately, I still don't know, how the .xsb hash function looks like. So I focussed on extracting the .xwbs to valid wmas...about 30% of the time, I spent on the WMA format...another fail. Finally I noticed that I only have to extract Xwma files.. the corresponding code for xwma was written in almost no time (1-2 hours), i.e. the code that is now used by most users was written in less than 1% of the time I worked on the project. And after all that happened to me in the last 3 months, I didn't even remember that I wrote a function for extracting PCM at all. But the problem is easy (and already fixed in the code): As you already wrote, I miscalculated the block align (didn't use INTEGER division). And the avg. byte rate was wrong, because I use the block align for calculating the byte rate...

I don't know why the file length is wrong... probably its better to extract PCM files with unxwb.
Apart from that I fixed one of the "unexpected" problems with the replace function mentioned in my last posting. So I'll try to include replace function(=still a big problem)  and renaming function(=should be quite easy; thanks for the list once again!!!) in the next version...but honestly: I don't know when it will be finished. The next weeks are stuffed with work for my job 

BTW: Thanks for the examples (MUS MIX_00001.wav, ...), too, but I can't test it with those, because I don't have Saints Row 2. I just have the two SR2-xwb files provided by IdolNinja.
## Post #45
- Username: IdolNinja
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Oct 14, 2010 4:33 pm
- Post datetime: 2011-02-14T21:15:20+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from Liandril
>
> 
BTW: Thanks for the examples (MUS MIX_00001.wav, ...), too, but I can't test it with those, because I don't have Saints Row 2. I just have the two SR2-xwb files provided by IdolNinja.

My offer is still good to buy you a copy of the game for testing if you're interested. It's dirt cheap right now on Amazon and I can just give you the registration key for Steam that comes with the manual. Let me know!
## Post #46
- Username: user452
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 05, 2011 11:00 pm
- Post datetime: 2011-03-05T21:10:56+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Thanks for doing this!  I've tried other tools and yours is the only one that works for me.

I've listened through all of the files I've extracted and noticed that there are definitely some things still missing (notably, audio from your character and your friends outside of missions)
In my extracted XWBs, there are a lot of numbers skipped.  At first i didn't think anything of it, but then I noticed that for the two example files you've been working with, SR2_CUTSCENES and MUS 420, there are no numbers skipped.
So I've uploaded some additional XWB files for you to test with, maybe you can work out what's going on with them, and hopefully all the missing files have the same cause so it's not too much work!

I've sent you a PM with links to the files.  If anyone else needs the files, PM me.

Some notes on the XWBs I've sent you:
I've included the XWBs FordGT90Concept mentioned.
When "MUS DISPATCH.xwb" is extracted, there are no files.
"Movement.xwb" has no files extracted and "Weapons.xwb" seems like it's missing some.
"SR2_VOC_SP.xwb" is 253mb, but only 61mb of files are extracted - just 32 files. (And they're in the 4000 range, if the numbers are relevant to show that some are missing) - As it's called VOC_SP, I believe this is probably where the missing single player audio is.

I hope this helps!


edit: Sorry, I didn't see that part where you had no time, I mainly saw this: 
> Reply from Liandril
>
> BTW: Thanks for the examples (MUS MIX_00001.wav, ...), too, but I can't test it with those, because I don't have Saints Row 2. I just have the two SR2-xwb files provided by IdolNinja.
Still, thanks for all your work!  If you ever do find time, now you have the files you need
## Post #47
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-06T02:37:00+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Thanks a lot dude
## Post #48
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2011-03-07T19:40:40+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

@user452: Thanks for your PM, but as I already wrote: I've currently no time to work on xactxtract (and if I have, the first thing will be the replace function). But your question was already answered a couple of times in this thread (and in the xactxtract readme): the missing files are ADPCM. xactxtract only extracts (x)WMA (and PCM, but as FordGT90Concept wrote, there are some small bugs in the PCM extraction function of the released versions of xactxtract). 
For extracting ADPCM (and PCM) files, I suggest using aluigis unxwb.  It supports (almost) all versions of .xwb and extracts everything except (x)WMA. Please note that there are difficulties with playing ADPCM files. VLC plays them correctly, but for other players (like WinAmp) you have to have the MS ADPCM codec (msadp32.acm) installed (on Windows XP).
xactxtracts info function will provide you with information (type (ADPCM,(x)WMA), sample rate...) about all files of a wavebank. With that information you'll know if you need unxwb, xactxtract or both for a specific .xwb file.
## Post #49
- Username: user452
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 05, 2011 11:00 pm
- Post datetime: 2011-04-06T09:00:23+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

The contents of this post was deleted because of possible forum rules violation.

edit:  There was no need to erase the entire post.  It would have been better to just remove the LINKS, so at least people could read the non-infringing text.

It's been a while, but I'm fairly sure that what this comment previously contained were a set of EXAMPLE archives with files which were not being extracted properly that people could use to improve the extraction tools.
## Post #50
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2011-04-10T15:14:39+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Hi user452,

first problem is that the .xwb is in Big Endian order (often used on consoles), xactxtract can only extract Little Endian order (used on PC). After a short look, I guess that the main problem with file 775 is the following:
all other files in the .xwb are marked as xma. 775 is the only file that is marked as PCM - this is probably wrong (i.e. an error in the .xwb). Someone could try to change the "PCM" entry into "XMA" (but not me as I really have no time, sorry).
## Post #51
- Username: user452
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 05, 2011 11:00 pm
- Post datetime: 2011-04-10T16:30:14+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Yes, this XWB is from the console version, and I've been using unxwb to extract the files as you suggested.

Thanks for the tip, 
I downloaded the source for unxwb, downloaded a compiler, downloaded zlib, got everything compiling correctly.
Now I've modified unxwb to treat pcm files as xma files, and recompiled it.  This should have exactly the same effect as editing the XWB.  Because it is simply treating that entry as if it said "XMA" in the file.

However, no luck.
After doing that, and using xmaencode on the file, it outputs a file that got to several hundred megabytes before I stopped it.

Thanks though, for now I'll just give up on that file, it probably wasn't anything important anyway.
## Post #52
- Username: ``~Scre@m~``
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 02, 2011 8:19 pm
- Post datetime: 2011-10-02T13:53:25+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Thanks anyone for this GREAT thread !

But i've got a question, whats the name of song "MUS AMBIENT_00191" ?
I meam, im asking is there any info about a track ? Like a name of file, or ID3 tag like in MP3s ? (i know its a WMA so it should have it, although it doesn't guarantee that something is filled empty strings there)

I will be very grateful if you help me out. Thanks again
## Post #53
- Username: InnocentSam2
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Apr 05, 2012 9:06 pm
- Post datetime: 2013-04-07T18:17:48+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Anyone have XACTXTRACT backed up somewhere? All download links are dead.
## Post #54
- Username: user452
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 05, 2011 11:00 pm
- Post datetime: 2013-04-07T18:39:15+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

I searched for [https://www.google.com/search?q=%22xactextract.rar%2](https://www.google.com/search?q=%22xactextract.rar%252) and found
[http://idolninja.saintsrowmods.com/sr2/tools/](http://idolninja.saintsrowmods.com/sr2/tools/) which seems to be v0.97

Just in case, I've uploaded the xactextract.rar I downloaded 2 years ago to mirrorcreator:
[http://mir.cr/UVABI0PW](http://mir.cr/UVABI0PW)
[http://mir.cr/1SJUWQIO](http://mir.cr/1SJUWQIO)

edit: I don't remember much about the troubles I had 2 years ago earlier in this thread, but I do know that I now have all the audio extracted from all 3 games, either using this tool or other tools.
## Post #55
- Username: InnocentSam2
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Apr 05, 2012 9:06 pm
- Post datetime: 2013-04-08T15:55:44+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Reply from user452
>
> I searched for https://www.google.com/search?q=%22xactextract.rar%2 and found
http://idolninja.saintsrowmods.com/sr2/tools/ which seems to be v0.97

Just in case, I've uploaded the xactextract.rar I downloaded 2 years ago to mirrorcreator:
http://mir.cr/UVABI0PW
http://mir.cr/1SJUWQIO

edit: I don't remember much about the troubles I had 2 years ago earlier in this thread, but I do know that I now have all the audio extracted from all 3 games, either using this tool or other tools.
Thanks! Thumbs up
## Post #56
- Username: caprum
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 21, 2018 4:33 pm
- Post datetime: 2018-05-21T08:38:03+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Hi, thanks a lot for the tools and explanations.
But has anyone ever tried to extract voices of the main characters of the game? I'd like to use them for modding another game.
The voices are packed (I think) in a file named 'voice_pc' without vpp_pc extension (in fact, without any extension) and the tools cannot open this package.
Does anyone have any idea how to open it? Any help will be appreciated.
## Post #57
- Username: zssllayers19460
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 18, 2022 1:04 pm
- Post datetime: 2022-07-22T16:36:22+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

You it's a shame this is the best game ever and Evey tool out there like unxwb either don't extract all the tracks or in xactxtract it says errors about the xwb being wrong version mine are V44, V42 all I wanna do is add my own songs and when I've got comfortable doing that move over to other stuff but no oneupdates these tools or release the source code so I can't fix it myself so idk I give up unless someone knows something I don't but I doubt anyone will even see this or even reply
## Post #58
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-23T09:23:53+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> but no oneupdates these tools or release the source code so I can't fix it myself so idk I give up unless someone knows something I don't but I doubt anyone will even see this or even reply

Well, actually this thread was dead since 2018, so no one really shared any new findings here.
But recently I've updated wiki article about this audio format. It's available here [http://wiki.xentax.com/index.php/XACT_XWB_XSB_XGS_Audio](http://wiki.xentax.com/index.php/XACT_XWB_XSB_XGS_Audio)
You can read it and try to update the tools yourself. There is a lot of useful information there and also some tools are open sourced like unxwb or XWBTool.


By the way, very detailed instruction on how to extract and 
import data to XWB 44/42 version is here [viewtopic.php?p=183974#p183974](https://forum.xentax.com/viewtopic.php?p=183974#p183974)
## Post #59
- Username: Kyoon
- Rank: n00b
- Number of posts: 16
- Joined date: Mon May 03, 2021 6:45 am
- Post datetime: 2022-07-24T16:19:13+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

Can anyone help me extract sound from Jumper Griffin's Story that also use xwb/xsb format?
[viewtopic.php?f=17&t=25576](https://forum.xentax.com/viewtopic.php?f=17&t=25576)

I tried multiple tools I've found, even the ones on the wiki, I sometimes got files extracted but I didn't obtain playable audio files
## Post #60
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-24T17:56:47+00:00
- Post Title: Re: Saints Row 2 XWB compressed wave

> Can anyone help me extract sound from Jumper Griffin's Story that also use xwb/xsb format?
Sorry, I don't know how to extract audio from Jumper Griffin's Story.

Also - you shouldn't ask about that in Saints Row topic. You've created your own topic and that's enough.
## Post #61
- Username: YourSoulIsMine
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 09, 2021 2:04 am
- Post datetime: 2022-08-06T22:03:24+00:00
- Post Title: Saints Row 2 Xbox 360 XWB/XSB modding

Greetings everyone. I'm attempting to add and/or replace XWB/XSB files for my Saints Row 2: Blood In Blood Out Edition Xbox 360 project. I've used over 10 versions of XACT to simply add and/or replace the files. But to no avail. Can anyone assist me in determining what version of XACT does the XWB/XSB files utilize?
