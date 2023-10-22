## Post #1
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2020-08-08T08:52:13+00:00
- Post Title: MGS4 SSP / BGM / DBM / MTA2 audio format

Hi guys!
I'm trying to extract/convert audio data  from the MGS4 SSP format, which should contain SFX data and other currently non extractable audio data.
I asked Derrik (GHzGangster) about it and he told me this:

> It's the same mta2 codec so you could try to grab the audio and put it in a bgm or dbm
>
> Make sure you grab the start of the audio block and put it on 0x800 in a bgm
>
> Start of audio is usually like 00 or FF or F0, something like that. Look at the start of audio in a bgm and you'll see.

So what do we know about MTA2 format?
MTA2 (Container): [https://www.mgsdevwiki.com/wiki/index.p ... Container)](https://www.mgsdevwiki.com/wiki/index.php/MTA2_%28Container%29)
MTA2 Codec:         [https://github.com/GHzGangster/Drebin/wiki/MTA2-Codec](https://github.com/GHzGangster/Drebin/wiki/MTA2-Codec)
MTA2 File Format: [https://github.com/GHzGangster/Drebin/w ... ile-Format](https://github.com/GHzGangster/Drebin/wiki/MTA2-File-Format)
Drebin tool:           [https://github.com/GHzGangster/Drebin](https://github.com/GHzGangster/Drebin)

I've took a look at SSP file format (wpn035_pss.ssp) with SolidSnake11  and he found it contains some other infos like MIDI datas:



We also figured out the SSP "magic" is "SSW2" and the next bytes are the data size:

SolidSnake11 also said:

> after the file size
>
> the sample begins
>
> so the header is 8 byte in total
>
> if we can figure out the codec
>
> we could play them with audacity

Here is a sample of SPP/BGM/DBM files wich contains 3 files of each formats including the smallest ones:
[https://www.mediafire.com/file/lplfaf18 ... o.zip/file](https://www.mediafire.com/file/lplfaf18xpaue3j/MGS4_Audio.zip/file)

If anyone is able to convert it as an usable audio file, or can provide more info about the file format, it would be really appreciated, because I (and many other peoples) are interested in using those files for many different projects.
Thank you for your time and I hope we'll figure it out!
## Post #2
- Username: cionbird
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 20, 2017 12:35 pm
- Post datetime: 2022-02-01T16:28:42+00:00
- Post Title: MGS4 SSP / BGM / DBM / MTA2 audio format

Have you had any more success with figuring this out?
