## Post #1
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2020-12-04T22:35:32+00:00
- Post Title: streambank0.kas file (DDR Universe series for Xbox 360)

It is possible to extract the streambank0.kas files (from DanceDance Revolution Universe series, Xbox 360)
1) I have extracted the file in Dragon Unpacker with HiperRipper [https://i.imgur.com/OXn3pFe.png](https://i.imgur.com/OXn3pFe.png)
2)I open in audiacity (or foobar, etc), i got this error [https://i.imgur.com/CTqbOzm.png](https://i.imgur.com/CTqbOzm.png)
3) I open the wwise_ima_adpcm, also i get this error [https://i.imgur.com/QTNu5ww.png](https://i.imgur.com/QTNu5ww.png)

How do I solve?

link this file [https://mega.nz/file/KFgQBTBY#gANSxc0Pm ... SucE2AQTEo](https://mega.nz/file/KFgQBTBY#gANSxc0Pm7qWawt6_VY4loEkNRTD3d5s3SucE2AQTEo)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-05T01:19:45+00:00
- Post Title: streambank0.kas file (DDR Universe series for Xbox 360)

They are XMA1 audio, so with the files you extracted from Dragon Unpacker, just rename them to *.xma and they will play in Foobar with the vgmstream plugin.
## Post #3
- Username: topet2k12001
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 26, 2021 6:13 pm
- Post datetime: 2021-01-29T11:11:49+00:00
- Post Title: streambank0.kas file (DDR Universe series for Xbox 360)

> Reply from Wrland ↑Sat Dec 05, 2020 6:35 am at Sat Dec 05, 2020 6:35 am
>
> 
It is possible to extract the streambank0.kas files (from DanceDance Revolution Universe series, Xbox 360)
1) I have extracted the file in Dragon Unpacker with HiperRipper https://i.imgur.com/OXn3pFe.png
2)I open in audiacity (or foobar, etc), i got this error https://i.imgur.com/CTqbOzm.png
3) I open the wwise_ima_adpcm, also i get this error https://i.imgur.com/QTNu5ww.png

How do I solve?

link this file https://mega.nz/file/KFgQBTBY#gANSxc0Pm ... SucE2AQTEo

Hello,

The extracted audio files (.wav) are in "compressed" form. You have to convert them to "uncompressed" .wav. You may use vgmstream's command-line tool. Once done with the conversion, the converted ("uncompressed" .wav) file will then be playable like any other usual .wav file.

[https://www.vgmstream.org/downloads](https://www.vgmstream.org/downloads)
