## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-15T22:16:38+00:00
- Post Title: The saboteur rifx vorbis

I tried the latest version of ww2ogg (0.5) and always i get a error

> ww2ogg test.wav -o 2.ogg --inline-codebooks
>
> Audiokinetic Wwise RIFF/RIFX Vorbis to Ogg Vorbis converter 0.5 by hcs
>
> 
>
> Input: test.wav
>
> RIFF WAVE 2 channels 32000 Hz 134112 bps
>
> 270367 samples
>
> Output: 2.ogg
>
> Parse error: unspecified.
I have the file: packed_codebooks.bin in the same folder
It's the PC version
Any idea?
[test.rar](https://xentaxbackup.github.io/file/2724_test.rar)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-15T23:02:49+00:00
- Post Title: The saboteur rifx vorbis

Did you try the command -inline-codebooks?

not tested it though.
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-15T23:08:35+00:00
- Post Title: The saboteur rifx vorbis

I tried with the -inline-codebooks, have look the 1rst post, this is the command i used:

> ww2ogg test.wav -o 2.ogg --inline-codebooks
and i get:

> Input: test.wav
>
> RIFF WAVE 2 channels 32000 Hz 134112 bps
>
> 270367 samples
>
> Output: test.ogg
>
> Parse error: unspecified.
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-15T23:09:25+00:00
- Post Title: The saboteur rifx vorbis

Okay yeah i get the same thing, ask hcs, he might need to update the program.
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-16T01:15:13+00:00
- Post Title: The saboteur rifx vorbis

It definitely does need --inline-codebooks, but this must be an even earlier version than the ones I dealt with in Army of Two 2.  I haven't been able to work out from just the file how it is stored differently.  Could you post some more files, maybe the main executable and any suspicious dlls?
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-16T02:47:44+00:00
- Post Title: The saboteur rifx vorbis

I attach the file WWiseIDTable, maybe helps
The dll's only i have:
1,1M  GDFBinary.dll
170K binkw32.dll
1,1M dbghelp.dll

If you need more waved ogg i can upload
[WWiseIDTable.7z](https://xentaxbackup.github.io/file/2725_WWiseIDTable.7z)
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-16T12:14:39+00:00
- Post Title: The saboteur rifx vorbis

I picked up the game myself and dug into the executable, it turns out that this version of Wwise uses an almost completely normal vorbis setup packet.  This is probably the same format that is seen in the EVE and Divinity 2, but with the triad of vorbis packets stripped down, discarding the identification and comment headers.  It does still have the time domain setup stripped out of the setup packet, as was seen before and after.  Interesting to see another intermediate form.
I've added support for this to ww2ogg 0.6, with the --full-setup command line switch.  If you try to convert one of these files without that switch it will fail and suggest it (though not if --inline-codebooks is used, that will just fail).

Note that I didn't get around to extracting the .pck so I haven't actually tested it with all the files, let me know if anything fails.
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-16T17:11:42+00:00
- Post Title: The saboteur rifx vorbis

The final audio works perfect!!!   
You know if the audios have some data, like parameters or similar?
I tried kinetik tools and looks the audio can't be reconverted, when i transcode the audio i lose "something", anyway actually audios works perfect.

Thanks!!
## Post #9
- Username: shearerc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 05, 2010 10:09 pm
- Post datetime: 2010-02-06T13:58:08+00:00
- Post Title: The saboteur rifx vorbis

hcs,
Thanks for your superb tool.
I used ww2ogg 0.8 --full-setup on The Saboteur WWise RIFF files, works perfectly.
