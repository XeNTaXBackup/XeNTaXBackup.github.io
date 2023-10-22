## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-24T22:52:52+00:00
- Post Title: AirStrike 1-2 - Archives

Watto in you at the site written which Game Extractor is supported APK archives from game AirStrike... while in me why there is no the this plugin ??   

[http://www.divogames.com/games/airstrik ... f_demo.exe](http://www.divogames.com/games/airstrike_2_gulf/airstrike2_gulf_demo.exe)
[http://www.divogames.ru/games/airstrike ... 2_demo.exe](http://www.divogames.ru/games/airstrike_2/airstrike2_demo.exe)
[http://www.divogames.ru/games/airstrike/as3d_demo.exe](http://www.divogames.ru/games/airstrike/as3d_demo.exe)
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T23:00:24+00:00
- Post Title: AirStrike 1-2 - Archives

Hi mate,

Air Strike 2 is a game that is supported using the Format Scanner (available in the full version). What this means is that I was not able to work out the archive format, but there were some common files in there that could be found using the format scanner - probably *.wav files.

You can see the relevant wiki thread at [http://wiki.xentax.com/index.php/Airstr ... lf_Thunder](http://wiki.xentax.com/index.php/Airstrike_2_Gulf_Thunder)

I have actually just downloaded the demo for Airstrike 2 yesterday, but havn't had the time to look at it yet - maybe I will be able to work it out now 

So why is there no plugin? Because it uses the format scanner. I have not included the format scanner in the source code, otherwise people would be able to compile the archive and get access to some of the full version features - but I can send you the source to 1 or 2 scanners if you really want them.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-24T23:10:31+00:00
- Post Title: AirStrike 1-2 - Archives

Oke oke .....  Watto look to this


I am using Extractor v2.4 ( This game scanner )
[AS_pak0.PNG](https://xentaxbackup.github.io/file/513_AS_pak0.PNG)
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-24T23:31:52+00:00
- Post Title: AirStrike 1-2 - Archives

After the starting of game is created astrike.log the file of this content


```

  pak0.apk - 840 files
  pak1.apk - 486 files
  pak2.apk - 25 files

F_Init: 
3 data files found.

---- Initializing sound system ----
  BASS_Init: Succeeded.

File 'gfx\logo\glow.tga' not found.
G_LoadObjects:  760 objects parsed succefully.

ERROR: Unknown object 'boss_1_rapidgun_proj'.
ERROR: Unknown object 'boss_1_rapidgun_flash'.
File 'gfx\logo\glow.tga' not found.
Shutting down sound system.
```

 I am using AirStrike3D II - Gulf Demo
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-28T10:37:46+00:00
- Post Title: AirStrike 1-2 - Archives

I do not yet have a TGA scanner in Game Extractor - I did originally but I removed it because it was slow (worked backwards through a file instead of forwards). I might look into re-supporting this format when I have some time to do it.

The error log file that happens when the game starts is just because the game developer removed some of the images from the archive, but did not remove the links from the startup script - this should not be a problem.

I hope this is the kind of thing you were asking.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: TkTech
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 02, 2017 7:22 am
- Post datetime: 2017-03-01T23:27:16+00:00
- Post Title: AirStrike 1-2 - Archives

12 years late but whatever...

I found this thread as pretty much the only search result for AirStrike so I had to work it out from scratch. Here's a writeup on the .apk file format including the "encryption" (skip to the bottom section) -> [http://www.tkte.ch/2017/02/27/air-strike-3d.html](http://www.tkte.ch/2017/02/27/air-strike-3d.html)

Just in case links aren't allowed on this forum, everything you need:

```
# -*- utf-8 -*-
import sys
import struct


class PakParser(object):
    #: File prefix.
    MAGIC_NUMBER = b'\x00\x00\x80\x3F\x99\x99\x00\x00'
    TABLE_ENTRY_SIZE = 76

    def __init__(self):
        self.file_count = 0
        self.cipher_table = None
        self.file_table = {}

    def load(self, file_obj):
        if not file_obj.read(len(self.MAGIC_NUMBER)) == self.MAGIC_NUMBER:
            raise IOError('invalid magic number')

        # The start of the file listing table (given from the start of the
        # file) and the number of file entries.
        file_table_offset, self.file_count = struct.unpack(
            '<II',
            file_obj.read(8)
        )

        # The cipher table comes after the header fields and is always exactly
        # 1kb.
        self.cipher_table = file_obj.read(1024)

        # Each entry in the file listing table is 76 bytes.
        file_obj.seek(file_table_offset, 0)

        self.file_table = dict(
            (filename.strip('\x00'), (offset, size))
            for filename, offset, size in (
                self.unpack_table_entry(
                    self.decipher(
                        file_obj.read(self.TABLE_ENTRY_SIZE),
                        i * self.TABLE_ENTRY_SIZE
                    )
                )
                for i in xrange(self.file_count)
            )
        )

    def decipher(self, chunk, offset):
        return ''.join(
            chr(
                ord(c)
                ^
                ord(self.cipher_table[(i + offset) % 1024])
            )
            for i, c in enumerate(chunk)
        )

    def unpack_table_entry(self, entry):
        # Filename (64 bytes)
        # Offset (4 bytes)
        # Size (4 bytes)
        # The unknown 4 bytes seem to always be 0.
        return struct.unpack_from('<64sIII', entry)[:3]

    def extract_file(self, file_obj, file_name):
        offset, size = self.file_table[file_name]
        file_obj.seek(offset, 0)
        return file_obj.read(size)

```
