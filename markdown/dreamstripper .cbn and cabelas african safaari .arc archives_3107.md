## Post #1
- Username: gamemaster
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 21, 2008 8:07 am
- Post datetime: 2008-07-30T19:20:02+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

The first game id like a script for is for Cabela's African Safari's .arc files.
For those who dont have the game ive uploaded one of the arc files so you can try and crack it.
[http://rs348.rapidshare.com/files/133640664/data2.rar](http://rs348.rapidshare.com/files/133640664/data2.rar)
just extract the rar file and the .zip file and thats were you'll find the arc files. I put it in a rar file to compress the size and to make it a faster download.

The other game game I want to view the files of is DreamStripper which uses .cbn archive files. 
Again ive uploaded a archive file from the game for those who dont have it in order to try and open it.Just a warning it is an adult game so that the .cbn archive might have some naughty content in it. Like textures for some of the models.
[http://rapidshare.com/files/133618414/Models.zip](http://rapidshare.com/files/133618414/Models.zip)
## Post #2
- Username: gamemaster
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 21, 2008 8:07 am
- Post datetime: 2008-08-02T17:59:22+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

Just wondering. Has anyone been able to open them yet?
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-08-04T05:55:34+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

I don't think people would like to download 170M unknown file to see what's there!? Actually I had downloaded it and that arc file is zlib packed. But there is not index table inside the arc, it means there should be another index file to tell what files, offset, length etc inside the arc.

The CBN archive is easy. And this game use granny engine as well!

```
dword          numFiles
struct IndexTable {
   dword       ofsFile
   dword       ofsLength
   dword       Len
   char[Len]  FileName
}
<data>

```


I don't have MultiEX atm, so I don't know if the script works or not

```
# by Fatduck edited 04Sep08
#
Set START Long 4;
GoTo START 0;
Get FCOUNT Long 0;

For T = 1 To FCOUNT;
Get OFSDATA Long 0;
Get OFSSIZE Long 0;
Get DSTGLEN Long 0;
GetDString FNAME DSTGLEN 0;
Log FNAME OFSDATA OFSSIZE 0 0;
Next T;
```
## Post #4
- Username: gamemaster
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 21, 2008 8:07 am
- Post datetime: 2008-08-04T13:31:32+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

Damn it said multiex could not process it. But thank you for trying. Could someone try and and edit it to make it work? Also what is the top code used for? I know the bottom is the bms script but what am I supposed to do with the top one?
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-09-04T18:11:36+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

I had another look of Cabela's African Safari's ARC today. And I think I figure out the format now!

The archive is divided in 0x800 a chunk. And the header is located at the last chunk 0x0A77E800

```
0A77E800   41 52 43 00 00 01 00 00  F6 4E 01 00 D4 C2 01 00   ARC.....譸..堎..
0A77E810   9A 34 00 00 B0 05 00 00  00 00 00 00 00 00 00 00   ?..?..........
```


And the format of the header is:

```
dword          Ver??
dword          ofsChunkIndex       //this is the indices table, real offset need * 0x800
dword          UnCompressedSize
dword          CompressedSize
dword          numRes
```


The indices table is zlib compressed, after uncompressed it, the format will be:

```
  char[4]       Magic               //"ARCH"
  dword         ofsChunkStart
  dword         ofsChunkSize
  dword         UnCompressedSize
  dword         CompressedSize
  dword         CompressionFlag     //-1 = compressed, 0 = raw data
  dword         nLen
  char[nLen]    ResName
}
```
## Post #6
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-09-07T19:38:23+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

Here is a small unpacker for Dreamstripper CBN-files:
[download/file.php?id=1633](http://forum.xentax.com/download/file.php?id=1633)
## Post #7
- Username: gamemaster
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 21, 2008 8:07 am
- Post datetime: 2008-09-16T23:07:12+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

Darn it fatduck! I just discovered you figured it out today but I already uninstalled the African safari game this week so I could have room in my hard drive to install spore and age of conan!
## Post #8
- Username: Ruzzz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 23, 2007 3:10 pm
- Post datetime: 2008-10-25T13:11:16+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

```

{$APPTYPE CONSOLE}

uses
  SysUtils, Zlib, Classes;

procedure SaveFileFromStream(SaveFileName: String; FileStream: TFileStream; FileOffset, FileSize: Cardinal);
var
  SaveFile: TFileStream;
  SaveCurrentPosition: Int64;
begin
  SaveCurrentPosition := FileStream.Position;
  SaveFile := TFileStream.Create(SaveFileName, fmCreate);
  try
    FileStream.Position := FileOffset;
    SaveFile.CopyFrom(FileStream, FileSize);
  finally
    FileStream.Position := SaveCurrentPosition;
    SaveFile.Free;
  end;
end;

function ExtractZLibFromStream(Stream: TStream; Buffer: TMemoryStream; Offset: Int64; CompressedSize, UnCompressedSize: Cardinal): Boolean;
var
  temp_buffer: TMemoryStream;
begin
  Stream.Position := Offset;
  temp_buffer := TMemoryStream.Create;
  try
    temp_buffer.CopyFrom(Stream, CompressedSize);
    temp_buffer.Position := 0;
    Buffer.Size := UnCompressedSize;
    Buffer.Position := 0;
    DecompressToUserBuf(temp_buffer.Memory, CompressedSize, Buffer.Memory, UnCompressedSize);
  finally
    temp_buffer.Free;
  end;
  Result := True;
end;

procedure ReadArchive(filename: String);
type
  THeader = packed record
    Magic: array [0..3] of Char;
    Version,
    ofsChunkIndex,
    UnCompressedSize,
    CompressedSize,
    numRes: Cardinal;
  end;

  TFilesTableChunk = packed record
    Magic: array [0..3] of Char;
    ofsChunkStart,
    ofsChunkSize,
    UnCompressedSize,
    CompressedSize,
    CompressionFlag, // Integer
    nLen: Cardinal;
    // ResName: array [0..nLen - 1] of Char;
  end;

var
  f: TFileStream;
  s, extract_path: String;
  buffer_files, buffer_file: TMemoryStream;
  Header: THeader;
  CurrentFile: TFilesTableChunk;
begin
  f := TFileStream.Create(filename, fmOpenRead);
  try
    f.Position := f.Size - $800; //$0A77E800
    f.Read(Header, SizeOf(Header));
    f.Position := Header.ofsChunkIndex * $800;
    buffer_files := TMemoryStream.Create;
    try
      if ExtractZLibFromStream(f, buffer_files, Header.ofsChunkIndex * $800, Header.CompressedSize, Header.UnCompressedSize) then begin
        buffer_file := TMemoryStream.Create;
        try
          buffer_files.Position := 0;
          extract_path := ExtractFilePath(filename) + 'Extract\';
          while buffer_files.Position + SizeOf(CurrentFile) <= buffer_files.Size do begin
            try
              buffer_files.ReadBuffer(CurrentFile, SizeOf(CurrentFile));
            finally
            end;
            SetLength(s, CurrentFile.nLen);
            buffer_files.ReadBuffer(s[1], CurrentFile.nLen);
            ForceDirectories(extract_path + ExtractFilePath(s));
            if Integer(CurrentFile.CompressionFlag) = -1 then begin
              if ExtractZLibFromStream(f, buffer_file, CurrentFile.ofsChunkStart * $800, CurrentFile.CompressedSize, CurrentFile.UnCompressedSize) then
                 buffer_file.SaveToFile(extract_path + s);
            end else begin
              SaveFileFromStream(extract_path + s, f, CurrentFile.ofsChunkStart * $800, CurrentFile.UnCompressedSize);
            end;
            writeln(s);
          end;
        finally
          buffer_file.Free;
        end;
      end;
    finally
        buffer_files.Free;
    end;
  finally
    f.Free;
  end;
end;

begin
  ReadArchive(ParamStr(1));
end.

```

[cabelas african safaari.rar](https://xentaxbackup.github.io/file/1701_cabelas african safaari.rar)
## Post #9
- Username: Ruzzz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 23, 2007 3:10 pm
- Post datetime: 2008-10-25T13:15:36+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

For 010 Editor

```
char Magic[4]; //"ARC\0"
uint version;
uint ofsChunkIndex<format=hex>; //this is the indices table, real offset need * 0x800
uint UnCompressedSize;
uint CompressedSize;
uint numRes;

FSeek(ofsChunkIndex * 0x800);
uchar indicesTable[CompressedSize];
```


after uncompressed the indices table

```
  char Magic[4]; //"ARCH"
  uint ofsChunkStart<format=hex>; // real offset need * 0x800
  uint ofsChunkSize; // real size need * 0x800
  uint UnCompressedSize;
  uint CompressedSize;
  int CompressionFlag; //-1 = compressed, 0 = raw data
  uint nLen;
  char ResName[nLen];
} FILES;

while( !FEof() )
{
    FILES file;    
}
```
## Post #10
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2019-03-04T14:19:54+00:00
- Post Title: dreamstripper .cbn and cabelas african safaari .arc archives

> Reply from asmxtx ↑Mon Sep 08, 2008 3:38 am at Mon Sep 08, 2008 3:38 am
>
> 
Here is a small unpacker for Dreamstripper CBN-files:
download/file.php?id=1633

For Win7 x64 please.Thx
