## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-06-23T10:16:59+00:00
- Post Title: Chameleon / H&D2SS / Wings of War ISD1

Format

```

typedef struct t_dtaheader {
    DWORD   FileCount;
    DWORD   TableOffset;
    DWORD   TableSize;
    DWORD   Unknown;
} DTA_HEADER;

typedef struct t_dtacontentheader {
    DWORD   Unknown1;
    DWORD   FileOffset;
    DWORD   Unknown2;
    char    FileName[16];
} DTA_CONTENT_HEADER;

typedef struct t_dtafileheader {
    DWORD           Unknown1;
    DWORD           Unknown2;
    DWORD           Unknown3;
    DWORD           Unknown4;
    DWORD           FileSize;
    DWORD           Unknown5;
    DWORD           Unknown7;
    unsigned char   FileNameLength;
} DTA_FILE_HEADER;
```


Edited: [Finished!](http://forum.xentax.com/viewtopic.php?f=32&t=9135)
