## Post #1
- Username: Kojinzx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 15, 2015 8:47 pm
- Post datetime: 2017-01-15T10:45:12+00:00
- Post Title: Can anyone Help me extract/insert Caladrius Blaze .mma files

Can anyone help me open,edit,unpack those files extensions 
I want redraw some of game art but cant edit this file

file for check
[https://drive.google.com/file/d/0B9xTXq ... sp=sharing](https://drive.google.com/file/d/0B9xTXqZuFzTILWo0SmwwN2xFM0k/view?usp=sharing)

thnx
## Post #2
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2017-01-15T12:28:09+00:00
- Post Title: Can anyone Help me extract/insert Caladrius Blaze .mma files

I believe your link is dead or wrong...
## Post #3
- Username: Kojinzx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 15, 2015 8:47 pm
- Post datetime: 2017-01-15T13:43:36+00:00
- Post Title: Can anyone Help me extract/insert Caladrius Blaze .mma files

> Reply from happydance
>
> I believe your link is dead or wrong...

sry, butfor now its may work
## Post #4
- Username: Kojinzx
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-01-15T15:08:11+00:00
- Post Title: Can anyone Help me extract/insert Caladrius Blaze .mma files

Zlib compressed

```
{
    unsigned char m_fileName[256];
    unsigned int m_uncompressedSize;//unconfirmed
    unsigned int m_compressedSize;
    unsigned int m_flags;//Might be flags 1 = compressed?
    unsigned int m_offset;//Relative, base is end of MMAFileEntry list or (0x20+m_numFiles*0x110
};

struct MMA
{
    unsigned char m_magic[16];//"MMArchiver2.000
    unsigned int m_numFiles;
    unsigned int m_padding00;
    unsigned int m_padding01;
    unsigned int m_padding02;
    MMAFileEntry[m_numFiles];
}

```
