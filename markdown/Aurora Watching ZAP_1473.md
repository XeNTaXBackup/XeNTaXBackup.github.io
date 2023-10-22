## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-30T16:54:58+00:00
- Post Title: Aurora Watching ZAP

Help extract  
Cutted file file there 
thx
[textures.zap.zip](https://xentaxbackup.github.io/file/417_textures.zap.zip)
## Post #2
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-08-30T18:05:36+00:00
- Post Title: Aurora Watching ZAP

I've writted yet the script for this format but I can't decompress file because i don't know what compression was used.
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-30T18:50:16+00:00
- Post Title: Aurora Watching ZAP

Yes I need to take only packing is in Game Extractor
## Post #4
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-08-30T19:11:48+00:00
- Post Title: Aurora Watching ZAP

The problem is that Watto's specification is a little wrong and incomplete
## Post #5
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-08-30T20:04:18+00:00
- Post Title: Aurora Watching ZAP

This's my Zap Specification

```

4 - FileZapTag (x31x10x03x20)
4 - 4					// probably ZapFileVersion
4 - DirectoryTableOffset	// of first root subdirectory
4 - DirectoryTableOffset	// of root directory
4 - IdRootDirectory

// EOF



// DirectoryTable{
  2 - NumberOfSubDirectory
  2 - NumberOfFiles
  4 - FileTableOffset		// if file was 0 place offset of next directory

  // for each Directory{
    4 - HowManyBytesToDirectoryEntry
  }

  // for each DirectoryEntry{    
    1 - DirectoryNameLength
    x - DirectoryName
    4 - DirectoryTableOffset
  }
}


// FileTable{

  // for each File{
    4 - HowManyBytesToFileEntry
  }

  // for each FileEntry{
    1 - FileNameLength
    x - FileName
    4 - FileDataOffset
    4 - FileSize
    4 - FileSizeCompressed
    4 - (x17x7CxD0x32)		// probably CompressionMethod
    4 - NULL
    4 - IdDirectory
  }
}

```


This only for english versione because other version, for example italian version, have changed position of offset entry and variables.
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-30T20:07:02+00:00
- Post Title: Aurora Watching ZAP

Yes.. But Game Extractor the some people archives does not open...
## Post #7
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-08-30T20:40:43+00:00
- Post Title: Aurora Watching ZAP

> Reply from KorNet
>
> Yes.. But Game Extractor the some people archives does not open...

Yes I know probably Watto has studing only one file for his scripts.

The script above can open all zap file and directory structure, but all file are compressed, I don't know which compression is used
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-08-31T04:42:55+00:00
- Post Title: Aurora Watching ZAP

Hi mate,

Thanks for the script changes. Sometimes I write the specs for a format, but when I go to implement it I realise some mistakes which I don't always update in the specs. Sorry about that - hopefully there shouldn't be too many dodgy specs.

Anyway, I will look into my Game Extractor plugin and check that it actually does what you have in your specs. Thanks mate!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
