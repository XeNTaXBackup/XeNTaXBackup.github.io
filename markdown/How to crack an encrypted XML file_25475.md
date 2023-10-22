## Post #1
- Username: IGBT001
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Mar 24, 2022 5:27 pm
- Post datetime: 2022-06-01T09:11:14+00:00
- Post Title: How to crack an encrypted XML file

As mentioned in the title, I found in localizing a game called "Ship Simulator Extreme Edition",
All the strings of the game are stored in XML files, try to open and modify, but it is garbled.
But when I entered the game, I found that he could load and display normally. I tried to use OllyDbg to analyze it, but I still couldn't analyze how he decrypted the XML file normally.
I used Google Translator to translate all the above words.
## Post #2
- Username: IGBT001
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Mar 24, 2022 5:27 pm
- Post datetime: 2022-06-01T09:18:46+00:00
- Post Title: How to crack an encrypted XML file

I uploaded the extracted string as an attachment, please help me analyze it, thank you!
[（求大佬分析）模拟航船极限版语言文件备份.zip](https://xentaxbackup.github.io/file/22291_（求大佬分析）模拟航船极限版语言文件备份.zip)
## Post #3
- Username: IGBT001
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-01T19:56:48+00:00
- Post Title: How to crack an encrypted XML file

Those XML files are not encrypted, they are compressed with ZLIB.
Here is the file format [http://wiki.xentax.com/index.php/Ship_S ... tremes_XML](http://wiki.xentax.com/index.php/Ship_Simulator_Extremes_XML)


You can decompress those files with offzip [http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)

```
offzip.exe -a Language_EN.xml
```


Then you can open/edit output files with Notepad++ and repack with offzip if you need.
## Post #4
- Username: IGBT001
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Mar 24, 2022 5:27 pm
- Post datetime: 2022-06-10T11:16:28+00:00
- Post Title: How to crack an encrypted XML file

Thank you for your reply, I successfully unpacked the XML file and generated it according to the .wdproj suffix. He edited it normally, but I can't compress the file at present, I don't know how to regenerate the XML file, can you tell me how to compress it Are they? Thanks!
I tried to use the -o command to generate the xml file, but the program reported an error.

```

Offzip 0.4.1
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file:    C:\Users\pengzhen\Desktop\5555\offzip\001\Language_EN.xml
- enter in directory: C:\Users\pengzhen\Desktop\5555\offzip\002
- zip data to check:  32 bytes
- zip windowBits:     15
- seek offset:        0x00000000  (0)

+------------+-----+----------------------------+----------------------+
| hex_offset | ... | zip -> unzip size / offset | spaces before | info |
+------------+-----+----------------------------+----------------------+
  0x00000008 ........... 20888 -> 135126 / 0x000051a0 _ 8 8:7:28:0:1:17cfe096


- 1 valid compressed streams found
- 0x00005198 -> 0x00020fd6 bytes covering the 99% of the file

C:\Users\pengzhen\Desktop\5555\offzip>offzip.exe -o C:\Users\pengzhen\Desktop\5555\offzip\002\00000008.wdproj C:\Users\pengzhen\Desktop\5555\offzip\002\00000008.xml

Offzip 0.4.1
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file:    C:\Users\pengzhen\Desktop\5555\offzip\002\00000008.wdproj
- zip data to check:  32 bytes
- zip windowBits:     15
- seek offset:        0x00000000  (0)
- open output file:   C:\Users\pengzhen\Desktop\5555\offzip\002\00000008.xml
.
- zlib Z_DATA_ERROR, the data in the file is not in zip format
  or uses a different windowBits value (-z). Try to use -z -15

- 2 bytes read (zipped)
- 0 bytes unzipped
```
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-10T16:48:37+00:00
- Post Title: How to crack an encrypted XML file

You can use "-r" option in offzip for reimport.

```
offzip.exe -r ......
```


Here's some more info [https://www.google.com/search?client=fi ... p+reimport](https://www.google.com/search?client=firefox-b-d&q=offzip+reimport)
## Post #6
- Username: IGBT001
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Mar 24, 2022 5:27 pm
- Post datetime: 2022-06-10T17:43:14+00:00
- Post Title: How to crack an encrypted XML file

I don't know which step I did wrong, I still can't generate the .xml file using the -r command.

```

Offzip 0.4.1
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file:    002\00000008.wdproj
- zip data to check:  32 bytes
- zip windowBits:     15
- seek offset:        0x00000000  (0)
- open output file:   001.xml
.
- zlib Z_DATA_ERROR, the data in the file is not in zip format
  or uses a different windowBits value (-z). Try to use -z -15

- 2 bytes read (zipped)
- 0 bytes unzipped

```

I tried to pack it with the packzip program, but the .XML file generated in this way cannot be read properly by the game.
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-10T20:48:15+00:00
- Post Title: How to crack an encrypted XML file

Do it this way:

Export:

```
offzip.exe -a Language_EN.xml
```


Import:

```
offzip.exe -a -r Language_EN.xml
```
## Post #8
- Username: IGBT001
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Mar 24, 2022 5:27 pm
- Post datetime: 2022-06-11T01:52:42+00:00
- Post Title: How to crack an encrypted XML file

Ok, after I did what you did, I found a new problem, and the following error was prompted:

```

Offzip 0.4.1
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file:    Language_EN.xml
- zip data to check:  32 bytes
- zip windowBits:     15
- seek offset:        0x00000000  (0)

+------------+-----+----------------------------+----------------------+
| hex_offset | ... | zip -> unzip size / offset | spaces before | info |
+------------+-----+----------------------------+----------------------+
  0x00000008 . < reimporting 00000008.wdproj
.........
Error: the compressed data is bigger than the original one by 0x17 bytes
```

If you don't modify the .wdproj file this appears to import fine.

```

Offzip 0.4.1
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file:    Language_EN.xml
- zip data to check:  32 bytes
- zip windowBits:     15
- seek offset:        0x00000000  (0)

+------------+-----+----------------------------+----------------------+
| hex_offset | ... | zip -> unzip size / offset | spaces before | info |
+------------+-----+----------------------------+----------------------+
  0x00000008 . < reimporting 00000008.wdproj
.......... 20888 -> 135126 / 0x000051a0 _ 8 8:7:26:0:1:17cfe096


- 1 valid compressed streams found
- 0x00005198 -> 0x00020fd6 bytes covering the 99% of the file
- 1 files reimported
```
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-11T09:36:07+00:00
- Post Title: How to crack an encrypted XML file

Try to read more carefully error messages and the documentation.

The error says

> the compressed data is bigger than the original one
so it means your new data can't be bigger than original. That's just how the quickbms and offzip work.

So just edit the file and keep the final result as smaller or equal original.
## Post #10
- Username: IGBT001
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Mar 24, 2022 5:27 pm
- Post datetime: 2022-06-11T13:39:18+00:00
- Post Title: How to crack an encrypted XML file

Well, I understand what you mean, I really can't understand what this byte is. Even if Play is changed to Klay, the program will report that the new data is 0x2 bytes larger than the original data. I still think of other ways to deal with it.
