## Post #1
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-11T04:03:41+00:00
- Post Title: Defiance beta

result .wad file if someone can say more 
thank's
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-11T05:00:54+00:00
- Post Title: Defiance beta

why not post the client link.
## Post #3
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-11T13:56:46+00:00
- Post Title: Defiance beta

good question
[https://defiance.com/en/beta/](https://defiance.com/en/beta/)
## Post #4
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-11T19:39:52+00:00
- Post Title: Defiance beta

say me in pm i can share my account if someone need donwload the client
## Post #5
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2013-01-12T03:51:11+00:00
- Post Title: Defiance beta

i have registered an account.
but, they do not have download menu at that game site.
anyway, this game is very interesting for me.
## Post #6
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-01-12T13:57:22+00:00
- Post Title: Defiance beta

[http://update03.triongames.com/ch3-inst ... eSetup.exe](http://update03.triongames.com/ch3-installer/public/alpha/DefianceSetup.exe)
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-13T12:17:28+00:00
- Post Title: Defiance beta

Servers down ?

```

Recovery process failed. Please check your network connectivity and try again. Patch Error [115]. Download Error [0].
```
## Post #8
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-13T13:59:10+00:00
- Post Title: Defiance beta

yes is stress test at this time
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-13T14:44:46+00:00
- Post Title: Defiance beta

How much size full game? Maybe actually upload on sendspace for example if size < 2-3gb?
## Post #10
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-01-13T16:42:46+00:00
- Post Title: Defiance beta

its 14gb.
## Post #11
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2013-01-14T06:39:23+00:00
- Post Title: Defiance beta

Would you mind providing ftp of the installed game for sightseeing or download
## Post #12
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-01-14T09:33:47+00:00
- Post Title: Defiance beta

If someone has an FTP server I can use I can upload it, don't really want to use my own connection to host.
Also the .wad files use zlib but I've honestly no idea what the format of the files inside are, looks like total garbage.
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-14T12:59:15+00:00
- Post Title: Defiance beta

> Reply from twisted
>
> its 14gb.
Huh lol. Anyway upload 1-2 small wads for review and desirable main executable with all librarys.
## Post #14
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-01-15T10:22:00+00:00
- Post Title: Defiance beta

Drop me a PM for file links, I've uploaded 2 files to my dropbox neither of which are particularly small:

resources.wad (1.13gb)
sounds.wad (359mb) - this is the smallest wad file. 

The files were taken from the closed alpha but after the latest update they're probably the same as beta stress test.
## Post #15
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2013-01-16T12:06:51+00:00
- Post Title: Defiance beta

this is all i can do now
the game uses custom-formatted asset, and archived them to wad file.
some asset files are zip-compressed.

```
// 010 Editor v3.1 Binary Template
//
// File     : DefianceTemplateWAD.bt
// Author   : MrMoonKr
// Revision : 0.1
// Purpose  : Defiance wad file analyze
// Changes  :  
//
// ( 2013/01/16/Wed )
//          : Found some helpful links 
//          : ( http://forum.xentax.com/viewtopic.php?f=10&t=10028 )
//
//////////////////////////////////////////////////////////////////////////


//------------------------------------------------------------------------

#include "CommonTemplate.bt"


//------------------------------------------------------------------------

/**
    file offset, file size, etc... 
    - i cannot find yet
    - they scrambled data
*/
typedef struct
{
    uint32              mUnk1 ;
    uint32              mUnk2 ;
    uint32              mUnk3 ;
    uint32              mUnk4 ;
    time_t              mTime ;
    uint32              mZero1 ;
    uint32              mType ;
    uint32              mZero2 ;

    local uint32 bookMark     = FTell() ;
    //FSeek( mOffset ) ;
    //char                mFileData[ mSize ] ;
    //char                mFileName[ 260 ] ;
    FSeek( bookMark ) ;

} WADChunk < bgcolor = cLtPurple , read = ReadWADChunk > ;

string ReadWADChunk( WADChunk& data )
{
    string s = "(no data)" ;
    SPrintf( s , "( %12u , %12u , %12d , %12d )( %12d )" ,
        data.mUnk1 ,
        data.mUnk2 ,
        data.mUnk3 ,
        data.mUnk4 ,
        data.mType 
        ) ;
    return s ;
}

typedef struct
{
    uint32              mChunkCount ;
    uint32              mNextOffset ;
    uint32              mZero4[2] ;

    WADChunk            mChunks[mChunkCount] ;

    if ( mNextOffset > 0 )
    {
        FSeek( mNextOffset ) ;
    }

} WADChunkArray < bgcolor = cLtRed, read = ReadWADChunkArray > ;

string ReadWADChunkArray( WADChunkArray& data )
{
    string s = "(no data)" ;
    SPrintf( s , "( Chunk Count : %d )( Next Offset : %u )" ,
        data.mChunkCount ,
        data.mNextOffset
        ) ;
    return s ;
}

//------------------------------------------------------------------------

/**
    archive file header
*/
typedef struct
{
    char                mFourCC[4] ;
    uint32              mZero1 ;
    uint32              mChunkCount ;
    uint32              mZero2 ;
    uint32              mZero3[4] ;

    local uint32 i=0 ;
    local uint32 remainChunks = mChunkCount ;
    for ( i=0 ; i < remainChunks ; ++i )
    {
        WADChunkArray   mChunkArrays ;
        
        remainChunks    -= mChunkArrays[i].mChunkCount ;
    }
    

} WADHeader < bgcolor = cLtGray , read = ReadWADHeader > ;

string ReadWADHeader( WADHeader& data )
{
    string s = "(no data)" ;
    SPrintf( s , "( FourCC : %s )( ChunkCount : u )" ,
        data.mFourCC ,
        data.mChunkCount
        ) ;
    return s ;
}


//////////////////////////////////////////////////////////////////////////

LittleEndian() ;
//BigEndian() ;

WADHeader               gHeader ;




```
## Post #16
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-16T23:29:40+00:00
- Post Title: Re: Defiance beta

beta is up at 17h
## Post #17
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-19T01:35:28+00:00
- Post Title: Re: Defiance beta

Finally i downloaded game. Filenames hashed. Models and props in format NIF (Gamebryo Engine). Textures DDS. Audio (used Opus Decoder) Well situation is the same as in first release Rift PAK's. Files inside WADs dont have directories.
## Post #18
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-16T23:57:40+00:00
- Post Title: Re: Defiance beta

you think's can do somethink's about Audio ? it's can be fun
## Post #19
- Username: racquemis
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 04, 2012 5:27 am
- Post datetime: 2013-03-15T22:36:12+00:00
- Post Title: Re: Defiance beta

Has anyone made any progress getting the audio files to play?
Got some of the files extracted but the format is unknown to me. There is a reference to a bitrate of 48000 (80 BB), but i got no clue which format it could be.
Ekey has mentioned Opus. When i check the file i'm unable to identify the headers that would be used by this format.
Any ideas?
## Post #20
- Username: racquemis
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 04, 2012 5:27 am
- Post datetime: 2013-03-16T21:51:04+00:00
- Post Title: Re: Defiance beta

build a very crude BMS script to extract the files in Sounds.wad

```
get NULL1 long
get FILES long
get NULL2 long
get NULL3 long
get NULL4 long
get NULL5 long
get NULL6 long
get CHKFILES long
get NEXTCHK long
get NULL7 long
get NULL8 long
for i = 0 < FILES
if i == CHKFILES
if NEXTCHK != 0
GoTo NEXTCHK
get CHKFILES long
get NULL long
get NULL long
get NULL long
endif
endif
get UNK1 long
get OFFSET long
get LENGTH long
get NAMEOFFSET long
SavePos CURROFFSET
GoTo NAMEOFFSET
getdstring NAME 0x80
GoTo CURROFFSET
log NAME OFFSET LENGTH
get TIME long
get NULL9 long
get TYPE long
get NULL10 long
next i

```


Still no luck in identifying the file format
## Post #21
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-03-22T08:29:07+00:00
- Post Title: Re: Defiance beta

it's very good start somone can help more
## Post #22
- Username: racquemis
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 04, 2012 5:27 am
- Post datetime: 2013-03-22T09:39:33+00:00
- Post Title: Re: Defiance beta

Verified that the PS3 version used the same WAD files.

I have managed to identify most parts of the header. i can tell you the number of channels the file contains, the playback duration, number of samples, samplefrequency and bitrate.
Besides audio samples i think the file also contains information for loops.
But not sure how to continue.

Defiance beta will be running today, if anyone wants to look at the files themselfs.
## Post #23
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-24T04:32:02+00:00
- Post Title: Re: Defiance beta

Interested in the audio as well.
## Post #24
- Username: PseudoProxen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 05, 2013 10:01 am
- Post datetime: 2013-05-05T19:29:48+00:00
- Post Title: Re: Defiance beta

Well I have some insight into the sound being utilized.

[Defiance in W32Dasm](http://assets.enjin.com/wall_embed_images/1367719949_DefianceSoundAnswer.jpg)

[Opus](http://www.opus-codec.org/) is being utilized, but just for the voice communications inside the game.

[Miles Sound System](http://www.radgametools.com/miles.htm) by RAD Game Tools is the primary middleware thats being utilized for the ingame sounds and music. So far (before my Windows OS decided to say f it all and jack up its certs) is that the music is in a MIDI format and possibly MPEG-1. Not going to verify that conclusion until I can look into it further after I reinstall my OS.
## Post #25
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-05-07T14:29:40+00:00
- Post Title: Re: Defiance beta

I wrote a little utility to extract the RMID files from the WAD files. 

[https://github.com/zeiban/defiwad](https://github.com/zeiban/defiwad)

Nothing new that hasn't already been figured out but may be useful to some. Looks like you guys have a handle on the audio or at least getting real close to converting to a playable format. I did noticed 2 audio formats though, one for streaming and another for effects. The effects were all zlib compressed.

I've been working on extracting the textures and have been successful. I'll post the code after I get it cleaned up. 

Here is a Volge helmet texture. [http://imgur.com/eOxNxQM](http://imgur.com/eOxNxQM). I'm looking forward to seeing them in the game eventually.
## Post #26
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-05-10T07:35:58+00:00
- Post Title: Re: Defiance beta

It no doubt uses opus and the other audio type is BINK Audio (*.binka) with the header of 1FCB, unfortunately no decoding tool for binka I seen unless somebody can get the bink sdk's binka_encode.exe which may decode... Miles uses binkawin.asi for decode AFAIK.

Apparently bulk of the audio is all bink audio, there is 64 bytes RMID header in them that can be stripped out if get decoder.

RMID seems to be generic asset header as even textures have it.
## Post #27
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2013-05-17T12:44:16+00:00
- Post Title: Re: Defiance beta

> Reply from Apollo
>
> It no doubt uses opus and the other audio type is BINK Audio (*.binka) with the header of 1FCB, unfortunately no decoding tool for binka I seen unless somebody can get the bink sdk's binka_encode.exe which may decode... Miles uses binkawin.asi for decode AFAIK.

Apparently bulk of the audio is all bink audio, there is 64 bytes RMID header in them that can be stripped out if get decoder.

RMID seems to be generic asset header as even textures have it.

I stumbled upon this topic while researching Bink Audio for Scribblenauts Unlimited.

On disassembly, I found that mss32.dll has a utility function that can decode any supported format to a PCM .wav; it is exported as AIL_decompress_ASI (mangled using C-style mangling). I've posted code to sort-of abuse this [in the Scribblenauts thread](http://forum.xentax.com/viewtopic.php?p=85499#p85499) and convert the *.binka files to *.wav.

If this game has mss32.dll present (instead of having it statically linked), chances are that function will be present as well. That code should work.

All the best.
## Post #28
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-06-29T02:40:19+00:00
- Post Title: Re: Defiance beta

I can confirm that this method using the mss32.dll to decompress the 1FCB data works for the Defiance assets as well. I will post a bin and src once once I get it all wrapped up in a nice command-line tool. 

-Zeiban
## Post #29
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2013-06-29T07:02:55+00:00
- Post Title: Re: Defiance beta

> Reply from Garrland
>
> 

I've been working on extracting the textures and have been successful. I'll post the code after I get it cleaned up.

Please please share the texture extraction method.
## Post #30
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-07-01T14:10:58+00:00
- Post Title: Re: Defiance beta

Just leaves the handful of other type audio files in defiance left... someone commented opus (unsure myself) before but header is entirely custom seemingly and normal opus would demand ogg container for playback.
## Post #31
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-07-11T21:49:40+00:00
- Post Title: Re: Defiance beta

> Reply from Apollo
>
> Just leaves the handful of other type audio files in defiance left... someone commented opus (unsure myself) before but header is entirely custom seemingly and normal opus would demand ogg container for playback.

From what I can tell all the music and audio are in the 1FCB format. I've not encountered any assets of type 0x09 (snd)  that are not in that format.
## Post #32
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-07-11T21:56:48+00:00
- Post Title: Re: Defiance beta

> Reply from blackfoxeye
>
> 


Please please share the texture extraction method.

I've got a texture extractor that dumps them to png almost ready for release along with some other tools.  The texture assets are basically a 96 bytes header followed uncompressed RGBA or compressed DXT data.

I'm working on the mesh extraction as well. Here are some unreleased Volge helmets that I posted on reddit. 

[http://imgur.com/a/7pwq2](http://imgur.com/a/7pwq2)

There are a lot of assets that are in the WAD files but not in the game yet.
## Post #33
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-07-12T19:14:54+00:00
- Post Title: Re: Defiance beta

I've pushed all my extraction tools to [Github](https://github.com/zeiban/defiance-tools)

Mesh extractions is coming once I get it automated. The mes2obj doesn't work right now but the other tools do. 

-Zeiban
## Post #34
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-07-27T01:10:28+00:00
- Post Title: Re: Defiance beta

[Defiance Tools v0.2.0 Released](http://www.zeiban.com/2013/07/defiance-tools-v020-released.html)

Both static and skinned meshes are now supported.
## Post #35
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-27T02:34:15+00:00
- Post Title: Re: Defiance beta

nice. thx:). before i pick up the game are there any of the more smexxy models as there are in the tv series? id buy the game for smexy models, but not for what heard is a plain game.
## Post #36
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-07-27T02:55:45+00:00
- Post Title: Re: Defiance beta

> nice. thx:). before i pick up the game are there any of the more smexxy models as there are in the tv series? id buy the game for smexy models, but not for what heard is a plain game.
No the game is totally different. Almost no female characters except Ara, Rynn, and Irisa unless you count the female player characters.
## Post #37
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-27T03:07:39+00:00
- Post Title: Re: Defiance beta

cool, thx for the info. does it work with current retail version of the game?
## Post #38
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-07-27T12:04:25+00:00
- Post Title: Re: Defiance beta

> cool, thx for the info. does it work with current retail version of the game?
Yes, as of the current 1.024 patch.
## Post #39
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2013-07-27T16:48:25+00:00
- Post Title: Re: Defiance beta

[quote="Garrland"][Defiance Tools v0.2.0 Released](http://www.zeiban.com/2013/07/defiance-tools-v020-released.html)

Thank you very much for your Tools Release.

Can you please describe how to use the tool "waddump.exe" to extract texture from "textures01.wad".

I have drag the wad file over the waddump.exe, but nothing happened, one cmd window is appearing and disappearing suddenly.

I am using Windows8 64bit machine, is the problem due to this?
## Post #40
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-07-27T18:58:28+00:00
- Post Title: Re: Defiance beta

> Thank you very much for your Tools Release.
>
> 
>
> Can you please describe how to use the tool "waddump.exe" to extract texture from "textures01.wad".
>
> 
>
> I have drag the wad file over the waddump.exe, but nothing happened, one cmd window is appearing and disappearing suddenly.
>
> 
>
> I am using Windows8 64bit machine, is the problem due to this?

All the tools are run from the command-line. Run them from a command window with a -h switch to see the usage. Check out the [Readme](https://github.com/zeiban/defiance-tools/blob/master/README.md) for details. Also, waddump it probably not what you want to use as it just extracts the raw RMID files in WAD archives for research.  Use snd2wav for audio extraction and mes2obj/ski2obj for mesh extraction.
## Post #41
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2013-07-28T08:56:26+00:00
- Post Title: Re: Defiance beta

> Reply from Garrland
>
> 
All the tools are run from the command-line. Run them from a command window with a -h switch to see the usage. Check out the Readme for details. Also, waddump it probably not what you want to use as it just extracts the raw RMID files in WAD archives for research.  Use snd2wav for audio extraction and mes2obj/ski2obj for mesh extraction.

Thank you very much Garrland, now its working.
## Post #42
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-08-02T08:29:35+00:00
- Post Title: Re: Defiance beta

[Defiance Tools v0.5.0](https://github.com/zeiban/defiance-tools/releases/tag/v0.5.0) Released
## Post #43
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-08-03T01:53:03+00:00
- Post Title: Re: Defiance beta

stupid question but will all these tools work if I unpack my 360 Iso I made off my game disc? cause that's all I have to work with and as I have posted elsewhere I'd really like to research that challenger from the game. plus a few of the heavy weapons.

 also might there be a frontend for this program set. I really don't do well with command line (and before you go crying that I am a noobish child no I grew up with computers since some of the earliest itterations of dos. dos I can get these commandlines don't seem to work so well for me in win7)
## Post #44
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-08-04T01:24:51+00:00
- Post Title: Re: Defiance beta

> stupid question but will all these tools work if I unpack my 360 Iso I made off my game disc? cause that's all I have to work with and as I have posted elsewhere I'd really like to research that challenger from the game. plus a few of the heavy weapons.
>
> 
>
> also might there be a frontend for this program set. I really don't do well with command line (and before you go crying that I am a noobish child no I grew up with computers since some of the earliest itterations of dos. dos I can get these commandlines don't seem to work so well for me in win7)

I've not tried it but I remember reading the somewhere that the 360 & PS3 data files were the same as the PC. I have no way to test though. Also sorry no GUI but I've only tested them on Win7 so as long as you have the command-line params right it should work.  Check [here](https://github.com/zeiban/defiance-tools/releases) for the most recent release and you can see some basic examples in the [readme](https://github.com/zeiban/defiance-tools/blob/master/README.md)
## Post #45
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-08-04T13:38:02+00:00
- Post Title: Re: Defiance beta

[Defiance Tools v0.5.1](https://github.com/zeiban/defiance-tools/releases/tag/v0.5.1)
## Post #46
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2013-08-04T13:49:40+00:00
- Post Title: Re: Defiance beta

I've started a release thread for the tools in the Tools & Programs forum [here](http://forum.xentax.com/viewtopic.php?f=32&t=10660). Any new updates to the tools will be posted there.
## Post #47
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2020-04-05T15:38:58+00:00
- Post Title: Re: Defiance beta

i got this message 
0xED5DE286 snd_vo_hffarmer_002_enemy_down_02 Unable to decompress audio. No codec found for requested input type.
Failed to write WAV file
