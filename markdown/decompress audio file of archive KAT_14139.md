## Post #1
- Username: domingo
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 25, 2016 6:43 am
- Post datetime: 2016-03-24T23:04:41+00:00
- Post Title: decompress audio file of archive KAT

He I need help to extract audio tracks from this file KAT
HEX


Link archive Kat

```
 https://mega.nz/#!2EtyQAgQ!_pExM5uoRAoK-U9H0vDwGVO6JpiiI5gsX2MOJO2iqf0 
```


I think what are adpcm samples, but can not find the way to extract all audio files
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-03-25T03:22:56+00:00
- Post Title: decompress audio file of archive KAT

Post a sample of .KAT archive
## Post #3
- Username: domingo
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 25, 2016 6:43 am
- Post datetime: 2016-03-25T12:53:33+00:00
- Post Title: decompress audio file of archive KAT

I added the link to the file KAT, are 60 mg compressed in rar file and 80mg decompressed
## Post #4
- Username: RedEyeX32
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 22, 2014 4:38 am
- Post datetime: 2016-04-02T15:13:02+00:00
- Post Title: decompress audio file of archive KAT

> Reply from domingo
>
> I added the link to the file KAT, are 60 mg compressed in rar file and 80mg decompressed

The structure is fairly simple, it goes as the following:

```
{
   int unk1;
   int file_offset;
   int file_length;
   int unk2;
   __int64 unk3;
   char file_name[28];
}

```


Each entry is 0x40 (64) bytes. This isn't a complete structure, but it is sufficient to do the things you want to do.
## Post #5
- Username: domingo
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 25, 2016 6:43 am
- Post datetime: 2016-04-03T10:21:50+00:00
- Post Title: decompress audio file of archive KAT

Ok thanks, I'll go testing, have if I get results
## Post #6
- Username: domingo
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 25, 2016 6:43 am
- Post datetime: 2016-04-06T14:01:35+00:00
- Post Title: decompress audio file of archive KAT

Just I try for 2 hours and not get extract the contents
## Post #7
- Username: RedEyeX32
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 22, 2014 4:38 am
- Post datetime: 2016-04-07T00:17:01+00:00
- Post Title: decompress audio file of archive KAT

> Reply from domingo
>
> Just I try for 2 hours and not get extract the contents

It's not that hard, just go to the file_offset and extract the data that equals to the file_length in the struct. Then rename that data to .wav and you will be able to play that audio. Also this is a Little Endian format.

The extracted raw data is a headerless wav file, so it won't play in Windows Media Player. I used Audacity to play it, import it as raw data.

I have extracted the first audio entry which is Escapeloop.wav, I'll attach it below.
[https://mega.nz/#!IglGyLTD!yUyNbRMkJCsn ... _mRBDQGfg8](https://mega.nz/#!IglGyLTD!yUyNbRMkJCsnwtFt_eK71IZNaQmkf6M0l_mRBDQGfg8)
## Post #8
- Username: domingo
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-04-07T12:59:50+00:00
- Post Title: decompress audio file of archive KAT

This looks like a game archive, I'll move this thread to Audio file formats, hopefully someone can put together a quickbms script. I'd do it but I've forgotten most of the syntax as it has been years since I've written one.

Could you also let us know what game this has come from?

Cheers.

---
Edit:
Just quickly updated this struct.

```
{
   int m_fileID;     //This seems to decrease, I assume it's the file ID, while loop till this is 1.
   int m_fileOffset;
   int m_fileLength;
   int m_sampleRate;
   __int64 m_unk1;
   char m_fileName[28];
}

```


Data does not look compressed so someone will need to write an unpacker that also creates a valid RIFF header.
## Post #9
- Username: domingo
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 25, 2016 6:43 am
- Post datetime: 2016-04-07T22:12:30+00:00
- Post Title: decompress audio file of archive KAT

ok, will try
Yes.the audio is raw,I have the Sound Forge Pro for to play
You can give an example of the structure of excapeloop.wav? to guide me? please

The game is Star war Episode 1 Racer, Dreamcast versión and I would like to replace the audio for the Spanish version of pc
