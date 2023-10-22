## Post #1
- Username: Ridertron
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 24, 2023 3:57 am
- Post datetime: 2023-09-23T20:21:20+00:00
- Post Title: (PS3) Resident Evil 4 HD (DAT.CRC) Audio files

Hello, I recently registered in this forum   because I have been wanting to do this for days, it turns out that I am dealing with changing audios to the resident evil 4 hd of ps3, (I only managed to change .sfd videos and .vag sounds that are together in some files. bnk) but there is a rather strange file which is bio4evt.dat.crc. I used some programs and they managed to extract some supposed "AT3 Plus 48000 Hz and 129 kbps sound" files but when I tried to convert them with vgmstream it didn't make sense, it threw error messages and there was no way to know what type of audio those were. Searching further inside the game folder I found a header file of the audios of the game events (the audios that are in bio4evt) So I would appreciate if you could give me a hand as I have been wanting to know how to do this correctly for a long time.
Thank you.   


Here I leave the links to the audio file:
[https://www.mediafire.com/file/q5r65cq4 ... t.crc/file](https://www.mediafire.com/file/q5r65cq42rp2yjo/bio4evt.dat.crc/file)

and this is its supposed header:
[https://www.mediafire.com/file/hksi6k2u ... t.crc/file](https://www.mediafire.com/file/hksi6k2uj9t5qjv/EveHeader.dat.crc/file)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2023-09-23T21:55:12+00:00
- Post Title: (PS3) Resident Evil 4 HD (DAT.CRC) Audio files

The CRC file looks like a bunch of offsets, but they don't match with the files in the audio archive.

Extracting the audio files directly also seems wrong - they play partially but then seem corrupt.

Is the .dat file exactly as it is in the game or has it been decompressed or anything?
## Post #3
- Username: Ridertron
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 24, 2023 3:57 am
- Post datetime: 2023-09-23T23:16:47+00:00
- Post Title: (PS3) Resident Evil 4 HD (DAT.CRC) Audio files

> Reply from DKDave ↑Sun Sep 24, 2023 5:55 am at Sun Sep 24, 2023 5:55 am
>
> 

Yes, it is exactly the same as I found it in the game files. but I don't know if it will be a compressed file, maybe it is like that since it is very rare that 245 audios of 48000hz give a weight of 80 mb. Maybe in reality they are 32000 hz or less if that file does not have a type of compression
