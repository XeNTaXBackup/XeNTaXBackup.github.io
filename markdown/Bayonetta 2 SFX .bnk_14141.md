## Post #1
- Username: fabe1212
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 12, 2011 9:24 am
- Post datetime: 2016-03-25T09:45:33+00:00
- Post Title: Bayonetta 2 SFX .bnk

I recently got my hands on some Bayo 2 files and I can't seem to convert the .bnk files to anything. I could use some assistance as I think the voices used in the recent game are amazing and would love to create mods with them. I tried using bnkextr and still no luck 

[https://i.gyazo.com/0b78f960d6d154690fe ... dac755.png](https://i.gyazo.com/0b78f960d6d154690fe4b61d0fdac755.png)
## Post #2
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2016-03-30T09:47:26+00:00
- Post Title: Bayonetta 2 SFX .bnk

> Reply from fabe1212
>
> I recently got my hands on some Bayo 2 files and I can't seem to convert the .bnk files to anything. I could use some assistance as I think the voices used in the recent game are amazing and would love to create mods with them. I tried using bnkextr and still no luck 

https://i.gyazo.com/0b78f960d6d154690fe ... dac755.png
I am also trying to extract the sound from the game, I can't seem to get it as every post on xentax has been taken down or not as helpful as I would have hoped
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-30T15:35:21+00:00
- Post Title: Bayonetta 2 SFX .bnk

it would be helpful if you can provide samples. in PM if you like
## Post #4
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2016-04-01T09:40:00+00:00
- Post Title: Bayonetta 2 SFX .bnk

> Reply from daemon1
>
> it would be helpful if you can provide samples. in PM if you like
Sorry for late reply, but I just sent one over your way
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-01T15:29:09+00:00
- Post Title: Bayonetta 2 SFX .bnk

well, thats easy. Its standard wwise bank. adpcm codec

1. use [viewtopic.php?p=74664#p74664](http://forum.xentax.com/viewtopic.php?p=74664#p74664) to extract wav files

2. convert them with new hcs ima decoder [https://hcs64.com/files/ima_rejigger5.zip](https://hcs64.com/files/ima_rejigger5.zip)
## Post #6
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2016-04-03T10:54:12+00:00
- Post Title: Bayonetta 2 SFX .bnk

> Reply from daemon1
>
> well, thats easy. Its standard wwise bank. adpcm codec

1. use viewtopic.php?p=74664#p74664 to extract wav files

2. convert them with new hcs ima decoder https://hcs64.com/files/ima_rejigger5.zip
After step 1 I get the .WAV files and can't play them (which is to be expected) but when I use the decoder it just opens and closes instantly and nothing happens. I try dragging the wav file to the exe but nothing and I tried opening the exe as administer but that didn't work either... What am I supposed to do with it?
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-03T10:59:03+00:00
- Post Title: Bayonetta 2 SFX .bnk

this is command line tool, needs 2 parameters

or you can run batch file like this:

for %%a in (*.wav) do ima_rejigger5 "%%a" "wav\%%a"

and create WAV folder first
## Post #8
- Username: fabe1212
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 12, 2011 9:24 am
- Post datetime: 2016-04-06T20:08:54+00:00
- Post Title: Bayonetta 2 SFX .bnk

Im sorry for the extremely late reply, I am new to sound ripping and this makes 100% no sense to me. Is there a simpler way for people like me?
## Post #9
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2016-04-12T04:54:21+00:00
- Post Title: Bayonetta 2 SFX .bnk

> Reply from fabe1212
>
> Im sorry for the extremely late reply, I am new to sound ripping and this makes 100% no sense to me. Is there a simpler way for people like me?
I'm going to assume you already have the .dat files extracted into .bnk and extracted that into .wav (all this is done by quick bms, yes you need a dat and bnk extractor) and all you need to do is download the file listed above and created a notepad file with this line " ima_rejigger5 "%%a" "wav\%%a" " and save it at a *.bat then put it in the folder you just downloaded and mae new folder called WAV/wav

finally just place the wav files into the directory and run the bat.
