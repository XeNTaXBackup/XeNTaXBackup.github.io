## Post #1
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-16T12:08:48+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

Hi, i have an audio file from from namco's motogp psp & motogp 04 ps2 that i'm interested in, it had the same name and format, at first i thought it was .bin but it's actually npsf, i heard that this format is also used in some other namco games on psp and ps2, i wonder if somebody could convert it to other format or maybe even convert other format to this one, here is a sample from motogp psp [https://www.mediafire.com/file/svznbt7i ... k.bin/file](https://www.mediafire.com/file/svznbt7i0r74alk/bgm_nps_pack.bin/file)
## Post #2
- Username: Ya begitulah
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-16T16:48:09+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

If you'll change file extension to *.npsf, you will be able to play it in Foobar with vgmstream plugin without any issues.
## Post #3
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-17T00:55:50+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

> Reply from ikskoks ↑Tue Aug 17, 2021 12:48 am at Tue Aug 17, 2021 12:48 am
>
> 
If you'll change file extension to *.npsf, you will be able to play it in Foobar with vgmstream plugin without any issues.

Thanks, i'll try it, is there any way to convert other format to this one?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-17T07:25:32+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

> is there any way to convert other format to this one?
You can convert NPSF to WAV using Foobar, but as far as I know it is not possible to convert any other format to NPSF.
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-08-17T12:27:27+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

Just an addition - if you change the extension, that will only play the first file in the archive.

To play them all, you will need to extract the individual NPSF sections, using something like VGMToolbox (Advanced Cutter option).  There should be 12 songs in that archive.
## Post #6
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-18T04:39:09+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

> Reply from DKDave ↑Tue Aug 17, 2021 8:27 pm at Tue Aug 17, 2021 8:27 pm
>
> 
Just an addition - if you change the extension, that will only play the first file in the archive.

To play them all, you will need to extract the individual NPSF sections, using something like VGMToolbox (Advanced Cutter option).  There should be 12 songs in that archive.
Thanks, at least i can extract all the songs 


 F1.rar
(229.23 KiB) Downloaded 15 times

by the way can you help me with this one? when i opened it in hex editor it says VAGp and then the name of the files inside it, it's engine sound file from f1 2009 PSP
## Post #7
- Username: Ya begitulah
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-18T07:29:31+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

> i opened it in hex editor it says VAGp and then the name of the files inside it
This file contain standard VAG Audio [http://wiki.xentax.com/index.php/VAG_Audio](http://wiki.xentax.com/index.php/VAG_Audio)
You can rip audio samples with PSound.
## Post #8
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-19T01:06:14+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

> Reply from ikskoks ↑Wed Aug 18, 2021 3:29 pm at Wed Aug 18, 2021 3:29 pm
>
> 
i opened it in hex editor it says VAGp and then the name of the files inside it
This file contain standard VAG Audio http://wiki.xentax.com/index.php/VAG_Audio
You can rip audio samples with PSound. yea, but when I try to repack with different audio file it doesn't work on the game, also there's multiple sound files inside the .vag, but when I try to make my own .vag with mfaudio why can I only put one file inside the .vag?
## Post #9
- Username: Ya begitulah
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-19T07:26:32+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

This ABC file is not one big VAG file with multiple audio samples, but it is a collection of VAG files with one audio sample.

So to replace data you would need create proper VAG files first (version 6 in this case) and then replace them in ABC file manually with hex editor or with some quickbms script.
## Post #10
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-19T08:48:08+00:00
- Post Title: Namco playstation sound format .Npsf sound/audio format (Namco psp and ps2 games)

> Reply from ikskoks ↑Thu Aug 19, 2021 3:26 pm at Thu Aug 19, 2021 3:26 pm
>
> 
This ABC file is not one big VAG file with multiple audio samples, but it is a collection of VAG files with one audio sample.

So to replace data you would need create proper VAG files first (version 6 in this case) and then replace them in ABC file manually with hex editor or with some quickbms script. Thank you, it works, I've replaced some of the sound files with hex editor
