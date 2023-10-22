## Post #1
- Username: mikaelN7
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 25, 2012 11:16 pm
- Post datetime: 2013-10-14T21:13:30+00:00
- Post Title: Extracting audio from The Wolf Among Us

I used Aluigi's tool [Telltale TTARCH file extractor](http://aluigi.altervista.org/papers.htm#ttarchext) to extract wavs but they are unreadable. I've used this tool before for The Walking Dead but it seems Telltale uses a different filetype now (TTARCH2.) I'm not sure that's causing the issue.

On his site it says "The Wolf Among Us remember to use the -m option which allows to dump the FONT and D3DTX files as DDS and the AUD as OGG but do NOT use this option if you plan to rebuild the ttarch archive!."

This is what I am doing:

```
C:\ttarchext.exe -m 54 "C:\fables_pc_fables101_ms.ttarch2" C:\output
```


The wav files are of all different sizes so at first glance it seems like they extracted properly but they won't play in any programs. Any ideas?
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-10-15T13:09:37+00:00
- Post Title: Extracting audio from The Wolf Among Us

Upload one of the extracted files from the tool.

They should be Vorbis in an OGG container and not WAV according to how the tool works.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-15T13:28:07+00:00
- Post Title: Extracting audio from The Wolf Among Us

I guess you are referring to the FSB4 files, the wav files are just FSB archives that you can extract with fsbext.
Try it
## Post #4
- Username: mikaelN7
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 25, 2012 11:16 pm
- Post datetime: 2013-10-16T15:45:30+00:00
- Post Title: Extracting audio from The Wolf Among Us

> Reply from aluigi
>
> I guess you are referring to the FSB4 files, the wav files are just FSB archives that you can extract with fsbext.
Try it
This works!  Each wav contains one mp3 file, but fsbext is only letting me choose one file at a time. There are over 5k wavs, is there a way to extract from all of them?
## Post #5
- Username: mikaelN7
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 25, 2012 11:16 pm
- Post datetime: 2013-10-16T19:22:55+00:00
- Post Title: Extracting audio from The Wolf Among Us

> Reply from brendan19
>
> Upload one of the extracted files from the tool.

They should be Vorbis in an OGG container and not WAV according to how the tool works.
OGG is exactly what I was expecting. Here is an example of what the tool extracts: [http://speedy.sh/6Scvn/295744826.wav](http://speedy.sh/6Scvn/295744826.wav)

The tool Aluigi mentioned (fsbext) extracts an mp3 from the wav, which is perfect. But I just need to find a way to convert all the wavs. I tried a batch or other tools but they also only allow one .fsb to be unpacked.
## Post #6
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-10-17T19:47:34+00:00
- Post Title: Extracting audio from The Wolf Among Us

Try that command line in the batch file:

```
pause
```


The fsbext.exe has to be in the same folder as the .bat file and .fsb file. This command will dump any .fsb in that folder, so put all the .fsb files in it and you're ready to go.

Cordialy.
## Post #7
- Username: mikaelN7
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 25, 2012 11:16 pm
- Post datetime: 2013-10-17T21:00:46+00:00
- Post Title: Extracting audio from The Wolf Among Us

> Reply from Vosvoy
>
> Try that command line in the batch file:
Code: Select allfor %%i in (*.fsb) do "%CD%\fsbext.exe"  %%i
pause

The fsbext.exe has to be in the same folder as the .bat file and .fsb file. This command will dump any .fsb in that folder, so put all the .fsb files in it and you're ready to go.

Cordialy.
Thanks a ton, listening to the files now.
