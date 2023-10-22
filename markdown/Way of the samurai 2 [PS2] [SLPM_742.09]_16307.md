## Post #1
- Username: Samdou
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 20, 2017 11:55 pm
- Post datetime: 2017-05-21T16:14:36+00:00
- Post Title: Way of the samurai 2 [PS2] [SLPM_742.09]

I'm trying to extract and rebuild the contents of the volume.dat in Way of the Samurai 2. Does anyone know of any tools/plugins/scripts that might be able to do that?

Here are the tools/scripts I've tried so far.

Xpert2 with the shinobidou plugin. It's able to extract the contents of the volume.dat, the total size of the extracted files being bigger than the volume.dat, suggesting compression.
Repacking the volume.dat, the new archive is bigger than the original, suggesting that Xpert and the shinobidou plugin are not recompressing the files.

akiba 2 bms script, but that only extracts some of the files before producing an error.
[https://forum.xentax.com/viewtopic.php?f=10&t=10941](https://forum.xentax.com/viewtopic.php?f=10&t=10941)
script.

```
get idstring long
get files long
get names long
get base long
get fsize long
savepos tmp
for i = 0 < files
goto tmp
get hash long
get offset long
get size long
get zip long
get nameoff long
get namesize long
savepos tmp
set zsize nameoff
math zsize - offset
math offset + base
math nameoff + base
goto nameoff
getdstring name namesize
if zip == 0
log name offset size
else
clog name offset zsize size
endif
next i
```

error received when extracting

```
--------------------------------------
  00e60800 38544      Common\chara\Body\musume_B_1_l.mdl
  00e6a000 63344      Common\chara\Body\musume_B_1_m.mdl
  05972000 74         Common\Debug\viewer.txt
  11673000 19704      JP\task\news_yujo1.bin

Error: the compressed zlib/deflate input is wrong or incomplete (-3)
Info:  algorithm   1
       offset      11673000
       input size  0x00000f8b 3979
       output size 0x00004cf8 19704
       result      0xffffffff -1

Error: the uncompressed data (-1) is bigger than the allocated buffer (19704)

Last script line before the error or that produced the error:
  26  clog name offset zsize size

Press ENTER or close the window to quit
Last script line before the error or that produced the error:
  26  clog name offset zsize size
```

volume.dat bms script from this thread, but it has similar results to the akiba 2 script.
[https://forum.xentax.com/viewtopic.php? ... 9&p=106511](https://forum.xentax.com/viewtopic.php?f=10&t=12889&p=106511)
script.

```
#by chrrox
#AKIBAS TRIP Undead Undressed
endian BIG
get MAGIC long
get FILES long
get FILES2 long
get BASE long
get UNK long
savepos TMP
for i = 0 < files
   goto TMP
   get HASH long #?
   get OFFSET long
   get SIZE long
   get COMTYPE long
   get NAMEOFF long
   get NSIZE long
   savepos TMP
   set ZSIZE NAMEOFF
   math ZSIZE -= OFFSET
   math OFFSET += BASE
   math NAMEOFF += BASE
   goto NAMEOFF
   getdstring NAME NSIZE
   if ZSIZE == SIZE
      log NAME OFFSET ZSIZE
   else
      clog NAME OFFSET ZSIZE SIZE
   endif
next i
```

error received when extracting

```
--------------------------------------
  00e60800 38544      Common\chara\Body\musume_B_1_l.mdl
  00e6a000 63344      Common\chara\Body\musume_B_1_m.mdl
  05972000 74         Common\Debug\viewer.txt
  11673000 19704      JP\task\news_yujo1.bin

Error: the compressed zlib/deflate input is wrong or incomplete (-3)
Info:  algorithm   1
       offset      11673000
       input size  0x00000f8b 3979
       output size 0x00004cf8 19704
       result      0xffffffff -1

Error: the uncompressed data (-1) is bigger than the allocated buffer (19704)

Last script line before the error or that produced the error:
  29  clog NAME OFFSET ZSIZE SIZE
```

volume.exe extraction tool for akiba, which is only able to extract, not repack the files, and the extracted files are bigger than the volume.dat, similar results to Xpert and shinobidou plugin. Opening the volume.exe in a hex editor shows that it uses deflate compression to extract the files.

error received when extracting 
```
JP\weapon\skillsheet\jo04.ssd
JP\weapon\skillsheet\jo05.ssd
JP\weapon\skillsheet\jo06.ssd
JP\weapon\skillsheet\jo07.ssd
JP\weapon\skillsheet\jo08.ssd
Common\collision\ryoteiyado.col
Common\motion\a02c1e_hanzaemon.mtp
Common\chara\Body\w_dona.mdl
Common\Accessory\?V?????t?H???_\AccessoryID.TBL

Unhandled Exception: System.ArgumentException: Illegal characters in path.
   at System.Security.Permissions.FileIOPermission.HasIllegalCharacters(String[]
 str)
   at System.Security.Permissions.FileIOPermission.AddPathList(FileIOPermissionA
ccess access, AccessControlActions control, String[] pathListOrig, Boolean check
ForDuplicates, Boolean needFullPath, Boolean copyPathList)
   at System.Security.Permissions.FileIOPermission..ctor(FileIOPermissionAccess
access, String[] pathList, Boolean checkForDuplicates, Boolean needFullPath)
   at System.IO.Directory.CreateDirectory(String path, DirectorySecurity directo
rySecurity)
   at volume.Program.CreatePath(String path, String s)
   at volume.Program.Main(String[] args)
```

hakuouki/way of the samurai 2 bms script, able to extract the files, with the total size bigger than the original, and the script unable to repack the files.
[http://aluigi.altervista.org/bms/hakuouki.bms](http://aluigi.altervista.org/bms/hakuouki.bms)
script.

```
#   maybe other games developed by Idea Factory
# script for QuickBMS http://quickbms.aluigi.org

endian big
idstring "\xfa\xde\xba\xbe"
get FILES long
get FILES long
get DATA_OFF long
get DATA_SIZE long
for i = 0 < FILES
    get NAME_HASH long
    get OFFSET long
    get SIZE long
    get ZERO long
    get NAME_OFF long
    get NAMESZ long

    math OFFSET + DATA_OFF
    math NAME_OFF + DATA_OFF

    savepos TMP
    goto NAME_OFF
    getdstring NAME NAMESZ
    goto TMP

    log NAME OFFSET SIZE
next i

```

error received when repacking 
```
--------------------------------------

Error: incomplete input file 0: C:\@VOLUME.DAT\!
       Can't read 4 bytes from offset 00000000.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.


Last script line before the error or that produced the error:
  6   idstring "\xfa\xde\xba\xbe"
```

Here's the volume.dat
[https://www.mediafire.com/?zaa8lmfm7tx74k8](https://www.mediafire.com/?zaa8lmfm7tx74k8)
