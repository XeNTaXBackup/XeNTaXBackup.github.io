## Post #1
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2016-07-28T23:54:13+00:00
- Post Title: Tak 2: The Staff of Dreams "sound.hog"

Hello, members of Xentax! I've been conducting an audio rip on this game from the XBOX, and I was wondering if I could seek help on a BMS script for this archive. I'm still shaky and new to writing them and I'm only  mediocre at identifying structures in an archive, thus I wouldn't know how to use which commands to extract the files. So far, this is what I've identified:

little endian.
4 byte long- na
4 byte long fcount
4 byte long DUMMY
4 byte long- logs value of fname pointer
0x800 4 byte long- pointer to fname
0xAA0- fname table x15 per name

If anyone is willing to aid me in extracting the files, that would be great! The file can be found here:
[sound.zip](https://mega.nz/#!5l90SASZ!5zNU52i0D8YriSIYHGgrVFawZ2MRHtEKAUPXxd834fc)

I would greatly appreciate any response. Thanks, and enjoy your day!
~Eric
## Post #2
- Username: Acewell
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-29T02:25:19+00:00
- Post Title: Tak 2: The Staff of Dreams "sound.hog"

Quite a simple format, I hope this helps.

struct Header
{
    unsigned short m_unk00;
    unsigned short m_unk01;
    unsigned int m_numFiles;
    unsigned int m_offsetDataStart;
    unsigned int m_offsetFileTable;
};

struct fileEntry//0x800
{
    unsigned int m_nameOffset;
    unsigned int m_fileOffset;
    unsigned int m_fileSize;
};
## Post #3
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2016-07-29T03:02:27+00:00
- Post Title: Tak 2: The Staff of Dreams "sound.hog"

> Reply from Gh0stBlade
>
> Quite a simple format, I hope this helps.

struct Header
{
    unsigned short m_unk00;
    unsigned short m_unk01;
    unsigned int m_numFiles;
    unsigned int m_offsetDataStart;
    unsigned int m_offsetFileTable;
};

struct fileEntry//0x800
{
    unsigned int m_nameOffset;
    unsigned int m_fileOffset;
    unsigned int m_fileSize;
};

That's great, thanks!!!

UPDATE I WROTE MY FIRST SCRIPT :

```
# for QuickBMS
get UNK long
get fcount long
get offset long
get otable long
goto otable

for i = 0 < fcount
get fname long
savepos POS
goto fname
getdstring NAME 0x15
goto POS
get offset long
get size long
log NAME offset size
next i

```
## Post #4
- Username: rl080897
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 10, 2023 9:23 pm
- Post datetime: 2023-05-10T13:26:02+00:00
- Post Title: Tak 2: The Staff of Dreams "sound.hog"

Do you know how to reimport modded audio in the .HOG archive ? Or repack them?
