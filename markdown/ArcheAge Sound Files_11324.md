## Post #1
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-03-16T11:17:32+00:00
- Post Title: ArcheAge Sound Files

Hey guys!

I extracted the FSB Files from ArcheAge last night and tried to revorb it (with revorb.exe)

But revorb tell me it is not a OGG File, but it is.

FSB say:

The extracted Celt/Ogg sample will not have a header, and cannot be played

OGG File:
[http://www.multiupload.nl/8KC8PZS33J](http://www.multiupload.nl/8KC8PZS33J)

FSB File:
[http://www.multiupload.nl/4CADRA56TU](http://www.multiupload.nl/4CADRA56TU)

Hope someone can look into it
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-03-17T01:25:48+00:00
- Post Title: ArcheAge Sound Files

If it's ogg files from a FSB, what you get is a headerless chunk of ogg data.
there's no easy header to add to ogg vorbis, due to it's encoding and packet scheme.
the app should have warned you that oggs from fsb's aren't playable, no one has solved this issue aside from one tool for planetside 2, but it only decoded the first file of an fsb, not all streams inside. it also didn't always work right on newer games that weren't planetside 2. basically, the coder hooked into the fmod dlls to decode it.

The other way is to rebuild to pcm (instead of ogg) using fmod designer, this can be mind numbing work when you have thousands of fsbs.
[http://www.hitmanforum.com/index.php/to ... try1603292](http://www.hitmanforum.com/index.php/topic/58859-hitman-absolution-audio-extractor/#entry1603292) (click spoiler for tutorial on this)
## Post #3
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-03-17T21:20:58+00:00
- Post Title: ArcheAge Sound Files

This is working at least ,)

Thx!

PS: There are FEV Files which pretty replace all, just double click nice
## Post #4
- Username: SysVR
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 20, 2014 6:30 am
- Post datetime: 2015-06-22T23:16:09+00:00
- Post Title: ArcheAge Sound Files

not work
