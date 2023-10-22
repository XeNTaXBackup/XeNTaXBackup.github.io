## Post #1
- Username: Ruzzz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 23, 2007 3:10 pm
- Post datetime: 2008-10-28T12:42:09+00:00
- Post Title: Hentai game - Critical Point

there is all resources in *.ARC files. Tamplate for 010 Editor:

```
local uint totalFiles;

uint numGroup;

typedef struct {
   char ext[4];
   uint numFiles;
   uint offset<format=hex>;    
} GROUP;

typedef struct {
   char filename[9]; // 0 terminated
   uint size;
   uint offset<format=hex>;
   local int64 curPos = FTell();
   FSeek(offset);
   uchar data[size];
   FSeek(curPos);
} FILE;

for(i = 0; i < numGroup; i++ ) {
   GROUP groups;
   totalFiles += groups.numFiles;
}

for(i = 0; i < totalFiles; i++ ) {
   FILE files;
}
```


Deplhi code:

```

{$APPTYPE CONSOLE}

uses
 SysUtils, Classes;

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

procedure ReadArchive(filename: String);
type
 TGroup = packed record
   Ext: array [0..3] of Char;
   numFiles,
   offset: Cardinal;
 end;

 TFile = packed record
   Filename: array [0..8] of Char;
   Size,
   Offset: Cardinal;
 end;

var
 Group: TGroup;
 currentFile: TFile;
 f: TFileStream;
 numGroup, i, k: Cardinal;
 dir, s: string;
 tmp_pos: Int64;
begin
 dir := ChangeFileExt(filename, '');
 if not (DirectoryExists(dir) or CreateDir(dir)) then exit;
 f := TFileStream.Create(filename, fmOpenRead);
 try
   f.Read(numGroup, SizeOf(numGroup));
   for i := 0 to numGroup - 1 do begin
     f.Read(Group, SizeOf(Group));
     tmp_pos := f.Position;
     f.Position := Group.offset;
     for k := 0 to Group.numFiles - 1 do begin
       f.Read(currentFile, SizeOf(currentFile));
       s := dir + '\' + currentFile.Filename + '.' + Group.Ext;
       writeln(s);
       SaveFileFromStream(s, f, currentFile.Offset, currentFile.Size);
     end;
     f.Position := tmp_pos;
   end;
 finally
   f.Free;
 end;
end;

begin
 ReadArchive(ParamStr(1));
end.
```


I cant extract *.WIP files (graphic ???). I try it do (template for 010 Editor):

```
ushort tflag; // ? for *.MSK = 01, for *.WIP = {01, 03, 04, 07, ...}
ushort Bit; // ? for *.MSK = 08, for *.WIP = 24
uint Width;
uint Height;
uint t[3]; // always = null
if (Bit == 8) {
   uint Size; // in bytes
   struct {
       byte R<format=hex>;
       byte G<format=hex>;
       byte B<format=hex>;
       byte E<format=hex>;
   } RGB[256];
   uchar RawData[Size];
   // EOF
};
//local uint calcSize = Bit / 8 * Width * Height;
//local uint calcBit = Size * 8 / (Width * Height);
//uchar Pallete[1024];
```


Help me!
## Post #2
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-11-17T00:36:01+00:00
- Post Title: Hentai game - Critical Point

Could you upload a sample of the images.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2008-12-14T17:55:23+00:00
- Post Title: Hentai game - Critical Point

Here is a description and pics
[http://forum.nihonomaru.com/trashimaru/ ... sored.html](http://forum.nihonomaru.com/trashimaru/32985-critical-point-hgame-english-uncensored.html)
