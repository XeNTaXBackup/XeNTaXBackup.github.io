## Post #1
- Username: PaK
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue May 29, 2007 7:43 pm
- Post datetime: 2007-05-29T18:08:13+00:00
- Post Title: Sparking Neo ( PS2 ) .PAK files

Anyone knows how to decompress these pak files?
I have tryed with dragon unpacker, xpert2, multiEx, game extractor, pakscape, game graphic studio and other stuff,  and nothing.. seems no estandart way works..

At the end of each file are some signature tags like:
IECSsreV, IECSdaeH, IECSigaV, IECSbteS, etc..

[http://personales.ya.com/paks/tmp/pak_files.rar](http://personales.ya.com/paks/tmp/pak_files.rar)
## Post #2
- Username: PaK
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue May 29, 2007 7:43 pm
- Post datetime: 2007-06-08T11:26:57+00:00
- Post Title: Sparking Neo ( PS2 ) .PAK files

This is what I found hexaeditng about its format:

```
header(64 bytes)
{
  UINT32 Tag     = 0x03
  UINT32 Version = 0x40

  UINT32 IECS1_offset
  UINT32 IECS2_offset
  UINT32 TotalFileSize

  UCHAR8 dummy1[44] = 0x00
}

@encripted/compresed data
{
  ...
}

IECS1
{
  IECSsreV
	UCHAR8 Tag[8]  ="IECSsreV"
	UINT32 Version = 16
	UINT32 Id      = 131072

  IECSdaeH
	UCHAR8 Tag[8]  = "IECSdaeH"
	UINT32 Version = 64
	UINT32 unknow1?
	UINT32 EncriptedDataSize
	UCHAR8 dummy2[12] = 0xFF
	UINT32 dummy3 = 5
	UINT32 unknow2?
	UCHAR8 dummy4[24] = 0xFF

  IECSigaV
	UCHAR8 Tag[8]   = "IECSigaV"
	UINT32 igaV_size
	UINT32 Nlines ?num_files¿

	...data_info( size = igaV_size - 16 )

  IECSbteS
	UCHAR8 Tag[8]   = "IECSbteS"
	UINT64 bteS_SIZE

	...data_info
}

IECS2
{
  IECSsreV
	UCHAR8 Tag[8]  ="IECSsreV"
	UINT32 Version = 16
	UINT32 Id      = 512

  IECSuqeS
	UCHAR8 Tag[8]  ="IECSuqeS"
	UINT64 unknow4?
	UCHAR8 dummy4[8] = 0xFF
	UINT32 dummy5 = 3
	UCHAR8 dummy6[4] = 0xFF

  IECSqseS
	UCHAR8 Tag[8]  ="IECSqseS"
	UINT64 qseS_size

	...data_info( size = qseS_size )
}

```


Im trying to find the textures packet inside. More info about this texture format ->
[viewtopic.php?t=2640](http://forum.xentax.com/viewtopic.php?t=2640)

Anyone knows what kind of compresion/encription use this files?
