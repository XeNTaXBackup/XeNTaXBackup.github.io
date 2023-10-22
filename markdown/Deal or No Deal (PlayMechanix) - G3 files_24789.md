## Post #1
- Username: Squacktus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 18, 2013 12:11 pm
- Post datetime: 2021-11-27T15:24:49+00:00
- Post Title: Deal or No Deal (PlayMechanix) - G3 files

Anyone familiar with .g3 files? There are a bunch of them in this Deal or No Deal game I'm reverse-engineering. They are apparently video files, but I don't recognize the file header or structure. Some references in the file content for libTheora and some video dimensions as well.

I tried a PlayMechanix quickbms script that was for a slightly different format (GLCGZ/GLCGZ2) but didn't work of course.

Example file attached.
[shuffle.g3.zip](https://xentaxbackup.github.io/file/21299_shuffle.g3.zip)
## Post #2
- Username: Squacktus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 18, 2013 12:11 pm
- Post datetime: 2021-11-27T15:29:29+00:00
- Post Title: Deal or No Deal (PlayMechanix) - G3 files

Facepalm moment - I always thought Theora (OGG) was audio-only and therefore that the file was some obscure format that merely had reference to some extra embedded audio or something.

Renaming the files to .ogg works fine.

Learn something new every day I guess. I never knew OGG could contain video content as well.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-27T17:29:47+00:00
- Post Title: Deal or No Deal (PlayMechanix) - G3 files

Hi, it will be good for other users to clarify some things. According to Wikipedia:

> The Ogg container format can multiplex a number of independent streams for audio, video, text (such as subtitles), and metadata.
>
> 
>
> In the Ogg multimedia framework, Theora provides a lossy video layer. The audio layer is most commonly provided by the music-oriented Vorbis format or its successor Opus. Lossless audio compression formats include FLAC, and OggPCM.
>
> 
>
> Before 2007, the .ogg filename extension was used for all files whose content used the Ogg container format. Since 2007, the Xiph.Org Foundation recommends that .ogg only be used for Ogg Vorbis audio files. The Xiph.Org Foundation decided to create a new set of file extensions and media types to describe different types of content such as .oga for audio only files, .ogv for video with or without sound (including Theora), and .ogx for multiplexed Ogg.

So we can be sure that before 2007 OGG container was used for storing audio, video and other data, but now it is not recommended.
Currently game developers should use OGV container for storing Theora video files.

Another thing is that OGG container always starts with "OggS" signature. In your file you have 5016 bytes of some custom header and right after that you can see a start of the OGG container [https://i.imgur.com/eC1zz39.png](https://i.imgur.com/eC1zz39.png)
So I think that's the reason you are able to play this file with OGG extension. Media players are just skipping custom header and they are detecting start of the OGG container.


Btw, I have updated article on the wiki with the info from this topic
[http://wiki.xentax.com/index.php/OGG_Container](http://wiki.xentax.com/index.php/OGG_Container)
