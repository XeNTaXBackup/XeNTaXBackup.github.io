## Post #1
- Username: SergioF
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 16, 2012 2:59 am
- Post datetime: 2014-11-14T20:09:34+00:00
- Post Title: Dreamcast Test Drive le mans ZIP contêiner

Sorry my english in advance.
[http://www.mediafire.com/download/ppdi5 ... 0/DATA.ZIP](http://www.mediafire.com/download/ppdi5q204wvzmf0/DATA.ZIP)

The file begins with a header size 0x43d8d (277 901) Bytes.
This seems to be heading Zip header information (PK \ x01 \ x02)
The header contains information of files in alphabetical order.
Here is a .CSV (Excel) file with the header information.

[https://www.dropbox.com/s/bjxfcg09jl8fl ... p.csv?dl=0](https://www.dropbox.com/s/bjxfcg09jl8flck/log_Zip.csv?dl=0)

Soon after this head comes the supposed compressed file with a type of zip do not know, are not in alphabetical order, but you can see it has some of the same information mentioned in the header (ZSIZE, SIZE, CRC, NAME, NAME SIZE .. .)

You can extract with ZipGenius but not reinsert.

Thank you for reading this far.
## Post #2
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2014-11-18T08:11:57+00:00
- Post Title: Dreamcast Test Drive le mans ZIP contêiner

After scratching my head for a bit, I realized what they did with this archive.

Basically, they put the "Central Directory Structure" first, which is NOT how the ZIP file format is defined. It must go at the end of the file, after everything else.

To "fix" this file, copy bytes 0x0 - 0x43DA2. Cut the data (CTRL + X) and paste it at the very end of the file, then save. The file will now open in any regular ZIP file viewer.

This document really helped me: [http://www.pkware.com/documents/APPNOTE ... -6.3.3.TXT](http://www.pkware.com/documents/APPNOTE/APPNOTE-6.3.3.TXT)

Hope this helps!

EDIT: I should've tested first, lol. It says "unsupported compression method" for every file. Sorry mate, I don't know what else to do.
