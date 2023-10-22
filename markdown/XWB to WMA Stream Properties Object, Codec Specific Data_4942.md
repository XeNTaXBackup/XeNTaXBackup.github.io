## Post #1
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-08-28T20:15:57+00:00
- Post Title: XWB to WMA: Stream Properties Object, Codec Specific Data

Hi,
some weeks ago I posted a similar request in [this](http://forum.xentax.com/viewtopic.php?f=17&t=4391) thread, but received no answer, so hopefully I've more luck this time. I'm currently writing a tool (a Perl script, actually) to extract WMA data from .xwb files (XACT Wavebanks) to valid .wma files (unfortunately, tools like unxwb DON'T extract playable/valid .wma files)

Extracting the wma DATA is quite easy and I'm able to transform them to a ASF DATA OBJECT (probably you know: wma is actually ASF (roughly spoken). And a valid .wma file consists of at least 5 objects:Header Object, File Properties Object, Stream Properties Object, Header Extension Object and Data Object).
My problem is the Stream Properties Object which contains a [WAVEFORMATEX](http://msdn.microsoft.com/en-us/library/ms720517%28VS.85%29.aspx) structure. Appended to the WAVEFORMATEX structure is a "Code Specific Data Section" for WMA (which is not described in the [ASF Specification](http://www.microsoft.com/windows/windowsmedia/forpros/format/asfspec.aspx)):

```
{
//......
    WORD    cbSize;   //Size of the appended codec specific data (10 in case of WMA)
} WAVEFORMATEX;
//the codec specific data:
    DWORD dwSamplesPerBlock; 
    WORD   wEncodeOptions;
    DWORD dwSuperBlockAlign;
```

Unfortunately I've not really an idea how to determine the values for these fields (especially the wEncodeOptions). 
So I'd really, really appreciate, if someone could give me a hint about this WMA-Code specific data section...
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-30T23:02:32+00:00
- Post Title: XWB to WMA: Stream Properties Object, Codec Specific Data

hard to find anything other than the code-specific data structure you already have. a few of my searches point to vlc or ffmpeg though, so i'd trawl through some of their sourcecode

if you haven't already, try the msdn forums?
## Post #3
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-08-31T12:56:16+00:00
- Post Title: XWB to WMA: Stream Properties Object, Codec Specific Data

Thanks a lot for your answer, WRS    ! Yes, I tried ffmpeg, but obviously not thoroughly enough. The wmadec.h/.c seems to have some answers for me... unfortunately, the source code is extremly undocumented and only for decoding and my C++ knowledge is not very good. I also looked into [libasf](http://libasf.googlecode.com/svn/trunk/), but that wasn't very helpful. So thanks again for pointing me to vlc... I just downloaded the source code.
Hm, yes, I might try the msdn forums if everythings fails... but probably they'll tell me, that I may look into the ASF specification, but I'm not allowd to look into the codec details or write a program, that creates .wma files...
