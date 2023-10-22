## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-11-15T04:16:27+00:00
- Post Title: Hitman Absolution Strange FSB5 file

[http://www.sendspace.com/file/pkt7f3](http://www.sendspace.com/file/pkt7f3)

I not sure what to make of this, Current tools don't work, Fsbext spits out an ogg file but it looks clearly not ogg. Any help?
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-11-15T08:15:34+00:00
- Post Title: Hitman Absolution Strange FSB5 file

It's FSB Vorbis, I brought this issue up to hcs months ago for need to have FSB Vorbis tool.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-11-15T18:22:35+00:00
- Post Title: Hitman Absolution Strange FSB5 file

A Temporary workaround method for these is to load them in FMOD designer and rebuild the fsb into a pcm file or w/e codec you choose and extract the new bank with your prefered fsb extractor.
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-11-15T20:53:11+00:00
- Post Title: Hitman Absolution Strange FSB5 file

Eh, FMOD Designer only opens up project files instead of the actual sound banks (FSB) and often there is nothing but those FSBs present unless you fake a project file to read a bank or something?
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-11-15T23:30:26+00:00
- Post Title: Hitman Absolution Strange FSB5 file

Well this is what i did.

1. Open FMOD designer and dragged the fsb5 bank into the Untitled folder, You can even play them because the tool has Vorbis codec

2. Go to Banks and make sure the ompression is set to PCM.

3. Rebuild the Project into a new fsb file "project>Build"

4. Get the new fsb file from the fmod designer folder and extract the FSB file with [http://aezay.dk/aezay/fsbextractor/](http://aezay.dk/aezay/fsbextractor/) Which supports FSB5 files.

So you should have your wave pcm files.

Im stil not sure how to get the names of the files inside the fsb banks yet so you'd have to rename manually.
## Post #6
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-11-16T10:13:45+00:00
- Post Title: Hitman Absolution Strange FSB5 file

Thanks, it seems I had done that before but problem was in actual files of what I took from planetside2 beta, they do seem to me they use vorbis but fmod designer is unable to playback and says unsupported file/audio format...hmm having checked again, even adpcm fsb files from it do not play yet they do extract with other fmod tools fine... Perhaps game devs have access to newer fmod than public shared one(?)

my tests show it can play adpcm, celt, vorbis, mp2,mp3 and build as such, other types would need the sdk dlls...
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-11-18T17:24:07+00:00
- Post Title: Hitman Absolution Strange FSB5 file

The xbox30 uses MPEG fsb5 which handles well with fsb extractor. problem is i have got over 2,000 fsb files and fsb extractor can pen only one at a time. Anyone know of any automated batch script for GUI apps?
## Post #8
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2012-11-26T17:42:27+00:00
- Post Title: Hitman Absolution Strange FSB5 file

OrangeC, [latest fsbext](http://aluigi.org/papers.htm#fsbext) supports fsb5 files, but can't rebuild ogg stream and saves raw vorbis-encoded data (unplayable).
but i think it can be used for batch conversion of fsbs from x360.
ps: is there any tools for extracting .pc_resourcelib files or fsbs are extracted by "FSB5" signature search?
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-11-26T22:06:50+00:00
- Post Title: Hitman Absolution Strange FSB5 file

Tried fsbext but for mpeg files doesn't play with or without header option.

Sure try vgmtoolbox for fsb5 extraction.
## Post #10
- Username: armorfid
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 09, 2011 12:14 pm
- Post datetime: 2012-12-12T19:23:24+00:00
- Post Title: Hitman Absolution Strange FSB5 file

> Reply from Apollo
>
> Thanks, it seems I had done that before but problem was in actual files of what I took from planetside2 beta, they do seem to me they use vorbis but fmod designer is unable to playback and says unsupported file/audio format...
I emailed aluigi about PlanetSide 2 FSB files, and he replied the following:

> Reply from aluigi
>
> looks like these chunk-based sound files in FSB5 are diffusing rapidly.
Basicly they are a series of chunks of max 65535 bytes and in my opinion
they are just compressed.

---

I just performed a quick check with fmodex.dll on these strange files
and the result is... odd, in fact using the fsbankex only when you
choose the ogg output it creates that format.

They look like ogg chunks so fsbext recognizes the files correctly but
they are not like the normal ogg we know, that's why they can't be
played easily.

I don't know if I will spend more time on them moreover because in
these cases is better to have a stand-alone tool for doing the
ogg2wav job (fsbext is a pure extractor/dumper) anyway for the moment
this solves some doubts.

In the latest Fmod there are 10004dd0 and 10004960 of fmodex.dll which
seem good starting points for anyone interested in the decoding.
## Post #11
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-05T12:29:17+00:00
- Post Title: Hitman Absolution Strange FSB5 file

new FSB Extractor read fsb5 for ns2 only at this time
## Post #12
- Username: 20Bucks
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 31, 2013 6:45 pm
- Post datetime: 2013-04-04T05:13:51+00:00
- Post Title: Hitman Absolution Strange FSB5 file

Any news on this?
## Post #13
- Username: 20Bucks
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 31, 2013 6:45 pm
- Post datetime: 2013-04-04T05:14:59+00:00
- Post Title: Hitman Absolution Strange FSB5 file

> Reply from OrangeC
>
> The xbox30 uses MPEG fsb5 which handles well with fsb extractor. problem is i have got over 2,000 fsb files and fsb extractor can pen only one at a time. Anyone know of any automated batch script for GUI apps?
Can you upload a folder with all those files? I don't mind extracting one by one, I'll do it and upload them when I'm done.
