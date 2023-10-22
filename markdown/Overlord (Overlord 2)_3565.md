## Post #1
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-07-04T06:02:31+00:00
- Post Title: Overlord (Overlord 2)

Target files *.8ld

Somehow encrypted. How to decode?

[http://rapidshare.com/files/251713350/Minion_Names.rar](http://rapidshare.com/files/251713350/Minion_Names.rar)
[http://rapidshare.com/files/251713544/Prelude.rar](http://rapidshare.com/files/251713544/Prelude.rar)
[Minion_Names.rar](https://xentaxbackup.github.io/file/2174_Minion_Names.rar)
## Post #2
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-07-04T08:39:30+00:00
- Post Title: Overlord (Overlord 2)

Just one procedure from my Delphi program. It is easy format.

```
const
  HEADER_ID : array[0..3] of char = ('M', '8', 'L', 'D');
  XOR_ARR : array[0..6] of byte = ($4F, $4E, $E2, $99, $A5, $4D, $38);

...

procedure TfrmMain.Convert8ldToXml(aInFile: string);
var
  OutFileName : string;
  InStream, OutStream : TFileStream;
  MemStreamIn, MemStreamOut : TMemoryStream;
  I, Size, Counter : Integer;
  B : Byte;
begin
  OutFileName := ChangeFileExt(aInFile, '.xml');

  MemStreamIn := TMemoryStream.Create();
  MemStreamOut := TMemoryStream.Create();  

  InStream := TFileStream.Create(aInFile, fmOpenRead or fmShareDenyNone);
  // Skip header 'M8LD'
  InStream.Seek(4, soFromBeginning);
  // Hash table start index
  InStream.Read(B, 1);
  Counter := B mod 7;

  MemStreamIn.CopyFrom(InStream, InStream.Size - InStream.Position);
  MemStreamIn.Seek(0, soFromBeginning);
  InStream.Free;

  Size := MemStreamIn.Size;

  for I := 0 to Size - 1 do
  begin
    MemStreamIn.Read(B, 1);
    B := B xor XOR_ARR[Counter];
    MemStreamOut.WriteBuffer(B, 1);

    if Counter < 6 then
      Inc(Counter)
    else
      Counter := 0;
  end;

  OutStream := TFileStream.Create(OutFileName, fmCreate or fmShareDenyNone);
  MemStreamOut.Seek(0, soFromBeginning);
  OutStream.CopyFrom(MemStreamOut, 0);

  OutStream.Free;
  MemStreamIn.Free;
  MemStreamOut.Free;  
  
end;

```


Or download my tool for that.


 O2Tools.rar
(200.17 KiB) Downloaded 917 times
## Post #3
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-07-04T15:53:59+00:00
- Post Title: Overlord (Overlord 2)

Nice tool, thanks.
But, it only helps with the localization files.
What about the .prp files that hold creature data? Or, the System_Quests.spf?
Anyone digged into those? Any clues?
Thank you.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-05T05:18:23+00:00
- Post Title: Overlord (Overlord 2)

can you post some sample files so we can take a look at them.
## Post #5
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-07-05T05:55:12+00:00
- Post Title: Overlord (Overlord 2)

[http://rapidshare.com/files/251834204/Interface.rar](http://rapidshare.com/files/251834204/Interface.rar)

.prp file
## Post #6
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-07-05T11:00:52+00:00
- Post Title: Overlord (Overlord 2)

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-23T02:35:21+00:00
- Post Title: Overlord (Overlord 2)

I don't know how old this topic is, but rather than posting a new one I thought I would try to help with this. I've been searching for a .prp viewer/extractor as well.
## Post #8
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-05-24T19:01:33+00:00
- Post Title: Overlord (Overlord 2)

Oddly enough I found this topic by searching google for 'Overlord prp'. It's amazing no one's gotten to this yet, but I certainly hope it isn't dead, as I'd love to see a model viewer or converter for these games.
## Post #9
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-28T00:13:15+00:00
- Post Title: Overlord (Overlord 2)

I figured I'd try and contribute something.

In this archive are several PRP files. Specifically the main ones I want unraveled personally, so if anyone would find a way to unpack these, please let us know.
[http://www.sendspace.com/file/chbqhn](http://www.sendspace.com/file/chbqhn)
