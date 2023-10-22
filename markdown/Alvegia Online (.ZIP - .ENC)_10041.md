## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-14T20:09:26+00:00
- Post Title: Alvegia Online (*.ZIP -> *.ENC)

Site : [here](http://alvegia.ru)
Download (Setup) : [here](http://downloaders.alvegia.ru/Install_Alvegia_Online.exe)
Download (Torrent) : [here](http://downloaders.alvegia.ru/AlvegiaOnline_v9.torrent)

Well in game have default zip archives (use Winrar or Winzip or something similar). Inside every zip all files encrypted and have extension .ENC. Here tool for decrypt. How to:

```
        AlvegiaDecrypt <inPathName> <inFile> <outFile>

[Decrypt]

        AlvegiaDecrypt version.xml version.xml.enc version.xml
```


inPathName - Original file name and path in archive without extension .ENC
inFile - Input file for decrypt.
outFile - Output (decrypted) file.

Example: bwres.zip
Unpack file version.xml.enc in D:\Temp for example

version.xml.enc - not be in a folder within the archive, you should use the tool so

```
AlvegiaDecrypt version.xml D:\Temp\version.xml.enc D:\Temp\version.xml
```


Now take another file which is in the archives at the following path helpers\maps\disc_quarter.dds.enc and unpack again in D:\Temp . In inPathName you need set path with reversed slash's

```
AlvegiaDecrypt helpers/maps/disc_quarter.dds D:\Temp\disc_quarter.dds.enc D:\Temp\disc_quarter.dds
```


Result:



PS: I know shit explanation 
[AlvegiaDecrypt_0.1.rar](https://xentaxbackup.github.io/file/6130_AlvegiaDecrypt_0.1.rar)
## Post #2
- Username: jowsss
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2012 9:05 pm
- Post datetime: 2013-08-21T07:21:10+00:00
- Post Title: Alvegia Online (*.ZIP -> *.ENC)

yeah.. how about video tutorial?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-21T09:18:59+00:00
- Post Title: Alvegia Online (*.ZIP -> *.ENC)

Here are all described in detail how to use.
