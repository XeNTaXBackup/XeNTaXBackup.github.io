## Post #1
- Username: oneiros
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 15, 2008 10:14 pm
- Post datetime: 2008-05-16T21:04:51+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

Hello,

excuse for my bad engish but I need some help by the extraction of the *.packed files of the game Clive Barker´s Jericho.

I used this script:

[http://wiki.xentax.com/index.php?title=Scrapland_PACKED](http://wiki.xentax.com/index.php?title=Scrapland_PACKED)

I always get an error report. That is anyway the correct script? Or do I create the BMS-file wrongly?

Would be pleased with help.
Best some help lasts in German.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-06-12T21:06:03+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

You should forget about the tags, this is the script:

```
Goto 8 0 ;
Get FNum Long 0 ;
For n = 1 to FNum ;
Get FNLen Long 0 ;
GetDString FN FNLen 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FS FO FSO FOO ;
Next n ;

```
## Post #3
- Username: oneiros
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 15, 2008 10:14 pm
- Post datetime: 2008-07-26T09:37:51+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

I regret that I answer now again. I was for longer time in China.

Thank for the answer, MR. Mouse
I can open indeed the *.packed file, but I can not extract the files correctly.

The extracted audio-files are either empty or damaged. Neither I can not import it in an audio-player or audio-editor. What do I make wrong?

If you want, I will upload a *packed file.

Please need help
Thanks for your help.
## Post #4
- Username: oneiros
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 15, 2008 10:14 pm
- Post datetime: 2008-07-29T16:09:39+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

I need help, please!
The extraction of some wav-files still not work yet. What do I make wrong?

You can download one of the packed-file:
[http://www.serpenteye01.bplaced.net/Music.packed](http://www.serpenteye01.bplaced.net/Music.packed)
## Post #5
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-07-13T14:35:04+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

Friends script to extract the most is all corrupted, can anyone help?

Hug.
## Post #6
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2011-07-19T11:33:54+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

Look for Gobread here. It's somewhere in the applications. It supports Jericho without a hitch as far as I remember
## Post #7
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-07-19T11:43:44+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

I can draw with the hand he has no option to reimport.
## Post #8
- Username: nkindt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 12, 2014 3:42 am
- Post datetime: 2014-10-12T18:13:21+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

Reviving old topic in case someone is still interested. The problem with packed files is that all files inside are compressed and Gobread did not work for me (half of files could not be extracted, other failure messages). Just extracting packed files as is won't help much since the content is still compressed as a binary blob.

Investigating CBJ in detail turned out that all files are compressed with good old deflate. Below are two Python 3 scripts. The first one extract all files from specified *.packed file into a dedicated subdirectory. The second script will take all extracted files in compressed form in a directory and decompress them to original assets . After this all wav, xml, dds, tga, ... files can be observed without problems. If files are already extracted then only the second script is needed to decompress them.

Note that this process can obviously be reverted if someone would consider making a high-resolution texture pack for this great game.

Script 1:

```
# Usage: python3 -file E:\Games\CBJ\Data00.packed

import sys
import os
import struct

filename = ''
if "-file" in sys.argv:
    j = sys.argv.index("-file")
    try:
        filename = sys.argv[j+1]
    except Exception as reason:
        print(reason)
        sys.exit(-1)

with open(filename, 'rb') as f:
    header = f.read(8)
    numfiles = struct.unpack('i', f.read(4))[0]
    dirname = os.path.splitext(filename)[0]
    try:
        if not os.path.isdir(dirname):
            os.mkdir(dirname)
    except Exception as reason:
        print(reason)
        sys.exit(-2)
    
    for i in range(0, numfiles):
        strlen = struct.unpack('i', f.read(4))[0]
        name = f.read(strlen).decode()
        name = name.split('/')[-1]
        size = struct.unpack('i', f.read(4))[0]
        offset = struct.unpack('i', f.read(4))[0]
        pos = f.tell()
        f.seek(offset)
        bytes = f.read(size)
        f.seek(pos)
        with open(dirname + os.sep + name, 'wb') as w:
            w.write(bytes)
            print("%.4u/%.4u - %s (Bytes: %u)" % (i+1, numfiles, name, size))

```


Script 2:

```
# Usage: python3 -path E:\Games\CBJ\Data03

import sys
import os
import struct
import zlib

pathname = ''
if "-path" in sys.argv:
    j = sys.argv.index("-path")
    try:
        pathname = sys.argv[j+1]
        if pathname[-1] != os.sep:
            pathname += os.sep
    except Exception as reason:
        print(reason)
        sys.exit(-1)
    
# Decompress files in extra directory
newdir = pathname + "_decompressed" + os.sep
try:
    if not os.path.isdir(newdir):
        os.mkdir(newdir)
except Exception as reason:
    print(reason)
    sys.exit(-2)

# Collect files in given directory
filelist = []
for (dirpath, dirnames, filenames) in os.walk(pathname):
    filelist.extend(filenames)
    break

done, failed = 0, 0
for file in filelist:
    filename = pathname + file
    with open(filename, 'rb') as f:
        done += 1
        # For now handle only first block in file (some files have multiple 78 9C blocks)
        size = struct.unpack('I', f.read(4))[0]
        magic = struct.unpack('H', f.read(2))[0]
        if magic != 40056:
            print(r'<?> %.4u/%.4u  Invalid magic:  %s  (Bytes: %u)  (skipped)' % (done, len(filelist), file, size))
            continue
        try:
            print(r'%.4u/%.4u  Unpacking:  %s  (Bytes: %u)' % (done, len(filelist), file, size))
            bytes = f.read(size - 6)
            data = zlib.decompress(bytes, -15)
        except Exception as reason:
            failed += 1
            print(r'<!> %.4u/%.4u  Failed:  %s  (Bytes: %u)   (%s)' % (done, len(filelist), file, size, reason))
            continue
        
        if file.endswith(".dds1"):
            file = file[:-1]
        with open(newdir + file, 'wb') as w:
            w.write(data)
print("Done. Unpacked: %u;  Failed: %u" % (done, failed))

```
## Post #9
- Username: Heimataerde
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 14, 2014 10:47 am
- Post datetime: 2014-10-14T02:50:02+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

For someone who has no knowledge at all of python, how would I run these scripts to extract files out of the .packed files?
My installation folder is 
C:\Program Files (x86)\Steam\steamapps\common\Clive Barker's Jericho

Where exactly would I post that so it extracts properly, as well?
## Post #10
- Username: nkindt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 12, 2014 3:42 am
- Post datetime: 2014-10-14T11:51:42+00:00
- Post Title: Need help by *.packed (Clive Barkers Jericho)

Ok i see the point. Let me explain in simple steps:

1. Go to [https://www.python.org/download](https://www.python.org/download) and download the 3.x.x version. Currently this is 3.4.1.
2. Install Python 3
3. Go to the installed Python 3 directory (i.e. C:\Python34\)
4. There you have the Python interpreter called python.exe (this one understands the scripts)
5. Copy both scripts to this Python directory, name them i.e. cbj_extract.py (Script 1) and cbj_unpack.py (Script 2)
6. Open command line window in current directory (Shift + Right Click in Python34 folder -> in menu choose "Open command window here") (more info: [http://www.techgainer.com/open-cmd-dos- ... e-windows/](http://www.techgainer.com/open-cmd-dos-command-line-here-windows/))

7. Assuming you have all files already extracted and want to decompress them, just type in command window:

```
python.exe cbj_unpack.py -path "E:\Games\CBJ\Data03"
```

This will decompress all files in E:\Games\CBJ\Data03\ into E:\Games\CBJ\Data03\_decompressed

To extract files from *.packed:

```
python.exe cbj_extract.py -file "E:\Games\CBJ\Data03.packed
```

This will extract files to E:\Games\CBJ\Data03\.

Of course the sample directory in this example ("E:\Games\CBJ\Data03") should be replaced by your own. Note also that Windows is very paranoid about writing to C:\Program Files (x86)\ directories and the script might fail to read/write. I recommend to copy all *.packed files into an extra directory, extract all files from there (Script 1) then decompress (Script 2).

If you want only Music.packed then the first script is enough since it's the only archive not having any compression on the files it contains (data is already compressed inside the OGG container).
