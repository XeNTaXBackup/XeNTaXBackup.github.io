## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-06-16T17:57:23+00:00
- Post Title: Decompress ADPCM to PCM?

Is there a tool that can decompress adpcm files to pcm\wav?
I tried using MilesSoundTools, but it's too obsolete to recognize ADPCM.
## Post #2
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2014-06-19T11:48:52+00:00
- Post Title: Decompress ADPCM to PCM?

I don't know any 'specific' tools (although I'm sure there are some), but a while ago, I simply used VLC to convert an ADPCM to PCM/wav.
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-06-19T12:30:38+00:00
- Post Title: Decompress ADPCM to PCM?

Try FFMPEG

```
ffmpeg.exe -i ms_adpcm.wav pcm.wav
```
## Post #4
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-06-19T13:21:36+00:00
- Post Title: Decompress ADPCM to PCM?

> Reply from Liandril
>
> I don't know any 'specific' tools (although I'm sure there are some), but a while ago, I simply used VLC to convert an ADPCM to PCM/wav.

how?
## Post #5
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2014-06-19T18:40:55+00:00
- Post Title: Decompress ADPCM to PCM?

Hi,

take a look a this: [viewtopic.php?f=17&t=10685](http://forum.xentax.com/viewtopic.php?f=17&t=10685)

Payday 2 ( for example ) use WWISE IMA_ADPCM i presume. There's many types of ADPCM formats if I'm not mistaken.

The conversion via VLC consists on a batch command file. You can learn more about VLC commands on Google.

Cordialy
## Post #6
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2014-06-19T22:20:47+00:00
- Post Title: Decompress ADPCM to PCM?

> Reply from Vosvoy
>
> 
The conversion via VLC consists on a batch command file. You can learn more about VLC commands on Google.
You can do the conversion directly in VLC (v2.1.0), too. Open vlc, then

Media->Convert/Save
In the Open Media dialog, click on "add" to select the (ADPCM) file and choose "convert"
In the convert dialog, click the "edit profile" button and choose "wav" in the encapsulation tab and once again "wav" in the audio codec tab
choose destination file and press start
## Post #7
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-06-20T07:29:29+00:00
- Post Title: Decompress ADPCM to PCM?

ahh. it's a Save as option. I thought it was an actual decompression..
## Post #8
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-06-20T15:46:48+00:00
- Post Title: Decompress ADPCM to PCM?

> Reply from Devilot
>
> ahh. it's a Save as option. I thought it was an actual decompression..
Well.. ADPCM compression is lossy.
it's not like a zip file where you can get back the original full quality file by unzipping it, decoding an adpcm file is like decoding an mp3, you'll always have some loss.
## Post #9
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2014-06-20T15:51:14+00:00
- Post Title: Decompress ADPCM to PCM?

> Reply from Pepper
>
> Devilot wrote:ahh. it's a Save as option. I thought it was an actual decompression..
Well.. ADPCM compression is lossy.
it's not like a zip file where you can get back the original full quality file by unzipping it, decoding an adpcm file is like decoding an mp3, you'll always have some loss.

Yes it's true. When I decompressed sounds from Payday 2 I get a slight and hissy artefact in the sounds.
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-06-20T22:41:39+00:00
- Post Title: Decompress ADPCM to PCM?

> Reply from Vosvoy
>
> Pepper wrote:Devilot wrote:ahh. it's a Save as option. I thought it was an actual decompression..
Well.. ADPCM compression is lossy.
it's not like a zip file where you can get back the original full quality file by unzipping it, decoding an adpcm file is like decoding an mp3, you'll always have some loss.

Yes it's true. When I decompressed sounds from Payday 2 I get a slight and hissy artefact in the sounds.
did you use vlc for that without using imarejigger first? payday and the sequel use audiokenetic adpcm, which doesnt always decode right unless you fix it with hcs's tool.
## Post #11
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2014-06-21T01:36:24+00:00
- Post Title: Decompress ADPCM to PCM?

> Reply from Pepper
>
> did you use vlc for that without using imarejigger first? payday and the sequel use audiokenetic adpcm, which doesnt always decode right unless you fix it with hcs's tool.

Huh... Yeah, but now I use a tool that I found on a website about Payday 2 modding (called wwise_ima_adpcm.exe). It convert WWise files to wavs. The hissy artefact is not very annoying anyway (it's kind of audible on shell casing  and firing layers sounds, for example).
If I took this tool it's mainly because it was a pain in the ass to cut the .bnk files via HxD to have each sounds in this container (imagine: manualy cut about 2000 files, take you a goddamn time).
So, today I don't use ima_rejigger2+VLC anymore. The result is quite better and faster.

Cordialy
## Post #12
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-06-22T00:20:31+00:00
- Post Title: Decompress ADPCM to PCM?

> Reply from Devilot
>
> Is there a tool that can decompress adpcm files to pcm\wav?
I tried using MilesSoundTools, but it's too obsolete to recognize ADPCM.
try VGMToolbox + VGMstream and GENH format:
[http://sourceforge.net/projects/vgmtoolbox/](http://sourceforge.net/projects/vgmtoolbox/)
[http://sourceforge.net/projects/vgmstream/](http://sourceforge.net/projects/vgmstream/)
[http://hcs64.com/files/vgmstream_external_dlls.zip](http://hcs64.com/files/vgmstream_external_dlls.zip)
## Post #13
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-06-23T07:27:47+00:00
- Post Title: Decompress ADPCM to PCM?

> Reply from SILENTpavel
>
> Devilot wrote:Is there a tool that can decompress adpcm files to pcm\wav?
I tried using MilesSoundTools, but it's too obsolete to recognize ADPCM.
try VGMToolbox + VGMstream and GENH format:
http://sourceforge.net/projects/vgmtoolbox/
http://sourceforge.net/projects/vgmstream/
http://hcs64.com/files/vgmstream_external_dlls.zip

I already have VGMstream  but I don't know how to use the others.
