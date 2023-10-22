## Post #1
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2016-09-23T15:54:00+00:00
- Post Title: Call of Duty: Advanced Warfare .pak FLAC

Hello. Author the tool "[AWFlac](http://dev.cra0kalo.com/?p=195)" does not provide support for old tools.
Can anyone help with extracting audio from the game? Program extracts audio from no all the archives and somewhere not completely (soundfile1.pak = 1.05 GB, but audio = 509 MB).
## Post #2
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2016-09-26T07:49:06+00:00
- Post Title: Call of Duty: Advanced Warfare .pak FLAC

> Reply from VladlenCry
>
> Hello. Author the tool "AWFlac" does not provide support for old tools.
Can anyone help with extracting audio from the game? Program extracts audio from no all the archives and somewhere not completely (soundfile1.pak = 1.05 GB, but audio = 509 MB).
Try to extract with [VGMtoolbox](https://sourceforge.net/projects/vgmtoolbox/)
----------------------------
Note:Go to Misc.Tools->Extraction Tools->Generic->Advanced Cutter/Offset Finder
Criteria: 664C614300000022
Treat as Hex:+
Extract Files:+
Output File Extension: .flac
Use Terminator String: 664C614300000022
Treat as Hex:+
Cut to EOF when Terminator Not Found:+
Source Files: soundfile*.pak - soundpacks
## Post #3
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2016-09-26T14:35:21+00:00
- Post Title: Call of Duty: Advanced Warfare .pak FLAC

> Reply from mauzerX
>
> Note:Go to Misc.Tools->Extraction Tools->Generic->Advanced Cutter/Offset Finder
Criteria: 664C614300000022
Treat as Hex:+
Extract Files:+
Output File Extension: .flac
Use Terminator String: 664C614300000022
Treat as Hex:+
Cut to EOF when Terminator Not Found:+
Source Files: soundfile*.pak - soundpacks
Thank you very much))
## Post #4
- Username: Laitig
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 05, 2019 2:07 pm
- Post datetime: 2019-02-05T06:10:23+00:00
- Post Title: Call of Duty: Advanced Warfare .pak FLAC

> Reply from mauzerX
>
> VladlenCry wrote:Hello. Author the tool "AWFlac" does not provide support for old tools.
Can anyone help with extracting audio from the game? Program extracts audio from no all the archives and somewhere not completely (soundfile1.pak = 1.05 GB, but audio = 509 MB).
Try to extract with VGMtoolbox
----------------------------
Note:Go to Misc.Tools->Extraction Tools->Generic->Advanced Cutter/Offset Finder
Criteria: 664C614300000022
Treat as Hex:+
Extract Files:+
Output File Extension: .flac
Use Terminator String: 664C614300000022
Treat as Hex:+
Cut to EOF when Terminator Not Found:+
Source Files: soundfile*.pak - soundpacks

Hi, but how did you get criteria numbers? 
What is in other soundfile*.pak files?
Which criteria numbers go to other files?
## Post #5
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2019-02-06T12:43:56+00:00
- Post Title: Call of Duty: Advanced Warfare .pak FLAC

> Reply from Laitig
>
> Hi, but how did you get criteria numbers? 
What is in other soundfile*.pak files?
Which criteria numbers go to other files?The criteria number is just hexadecimal code.

```
66 4C 61 43 00 00 00 22
```
 is just

```
fLaC..."
```
 in ASCII


Games generally don't use multiple compression formats, they usually stick to just one.

But it always helps to post a sample archive
## Post #6
- Username: Proteus37
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 02, 2020 5:50 pm
- Post datetime: 2020-02-04T09:11:13+00:00
- Post Title: Call of Duty: Advanced Warfare .pak FLAC

If anyone knows which of the 90-some soundfile.pak archives contain music, please do let us all know. Dumping these one by one is just a pain in the ass right now.
## Post #7
- Username: ppyrew
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 21, 2020 6:40 pm
- Post datetime: 2020-02-24T09:01:45+00:00
- Post Title: Call of Duty: Advanced Warfare .pak FLAC

Same as ghosts the sound pak files are just mushed flac audio.

[CODAW_FlacDumper_x64_3.0.zip](http://j.gs/1261794/codaw-flacdumperx64-3)
[DQFanSurvey](https://www.dqfansurvey.us/)
## Post #8
- Username: Kulfon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 11, 2017 2:22 am
- Post datetime: 2021-03-29T11:34:04+00:00
- Post Title: Call of Duty: Advanced Warfare .pak FLAC

> Reply from ppyrew ↑Mon Feb 24, 2020 5:01 pm at Mon Feb 24, 2020 5:01 pm
>
> 

CODAW_FlacDumper_x64_3.0.zip

Damn, looks like the file is not available at that page. Any other place to get it?
## Post #9
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-01-23T15:53:11+00:00
- Post Title: Call of Duty: Advanced Warfare .pak FLAC

[https://web.archive.org/web/20160613181 ... 64_2.0.zip](https://web.archive.org/web/20160613181113/http://rel.cra0kalo.com/depot/CODAW_FlacDumper_x64_2.0.zip)
