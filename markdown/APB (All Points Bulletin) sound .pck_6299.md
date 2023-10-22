## Post #1
- Username: ShinobiMao
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Sep 07, 2010 11:41 pm
- Post datetime: 2011-03-26T07:21:25+00:00
- Post Title: APB (All Points Bulletin) sound .pck

It's similar to Assassin's Creed II's pck but none of the scripts for it work. In the attached file if you take out everything before the first RIFF you can use ww2ogg on it easily (and it stops at the proper end of the first file inside), but there's apparently 968 sounds in there, and doing them all manually would be really tedious. 

If a bigger file is needed, I can supply it.
[StreamedSFX_file.rar](https://xentaxbackup.github.io/file/4105_StreamedSFX_file.rar)
## Post #2
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2011-03-26T08:53:50+00:00
- Post Title: APB (All Points Bulletin) sound .pck

I don't see any problem,U need to use any WAV(RIFF) scanner(Nova Soft extractor for example),then rename *.WAV to *.RIFF and convert with ww2ogg...
## Post #3
- Username: ShinobiMao
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Sep 07, 2010 11:41 pm
- Post datetime: 2011-03-26T10:18:39+00:00
- Post Title: APB (All Points Bulletin) sound .pck

EDIT: Well, I thought I got it to work but every RIFF/WAVE scanner I tried gives me files ww2ogg can no longer convert. It gives me "Parse error: unknown chunk type".
## Post #4
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2011-03-26T19:01:56+00:00
- Post Title: APB (All Points Bulletin) sound .pck

Read [this topic](http://forum.xentax.com/viewtopic.php?f=17&t=5449)
## Post #5
- Username: ShinobiMao
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Sep 07, 2010 11:41 pm
- Post datetime: 2011-03-27T01:13:32+00:00
- Post Title: APB (All Points Bulletin) sound .pck

> Reply from mauzerX
>
> Read this topic

Using the parameter --full-setup I get a new parse error, "invalid codebook identifier".
## Post #6
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2011-03-27T06:45:13+00:00
- Post Title: APB (All Points Bulletin) sound .pck

> Reply from ShinobiMao
>
> mauzerX wrote:Read this topic

Using the parameter --full-setup I get a new parse error, "invalid codebook identifier".
It is important: ww2ogg.exe,*.RIFF,packed_codebooks.bin,RIFF.bat should be in the same folder...

If batch with full-setup doesn't work:
for %%a in (*.RIFX) do ww2ogg.exe "%%a" --full-setup
then U have to use batch without full-setup:
for %%a in (*.RIFF) do ww2ogg.exe "%%a"
## Post #7
- Username: ShinobiMao
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Sep 07, 2010 11:41 pm
- Post datetime: 2011-03-27T08:32:58+00:00
- Post Title: APB (All Points Bulletin) sound .pck

Amazing! I must've missed where you said I needed packed_codebooks.bin and that was my problem. My ww2ogg10.rar did NOT have the .bin inside, and only did when I re-downloaded it (well, along with a few other misc source files). So, when I put codebooks.bin in and used it, it worked properly!

So thank you for helping me find the source of my troubles. ありがとう。
