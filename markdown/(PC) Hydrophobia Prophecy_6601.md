## Post #1
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-05-11T20:06:49+00:00
- Post Title: (PC) Hydrophobia Prophecy

Please, help me with unpacking .dat file.

Cut file:

[http://www.multiupload.com/74A1AED379](http://www.multiupload.com/74A1AED379)

[http://www.multiupload.com/GFV98PXMKH](http://www.multiupload.com/GFV98PXMKH)
## Post #2
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2011-05-13T11:09:42+00:00
- Post Title: (PC) Hydrophobia Prophecy

The last patch.dat from the last steam update.
[http://www.mediafire.com/?odxw3o1oa5odkyl](http://www.mediafire.com/?odxw3o1oa5odkyl)
And the game executable with dlls.
[http://www.mediafire.com/?zrgs28euz2qhsso](http://www.mediafire.com/?zrgs28euz2qhsso)

Thanks
## Post #3
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2011-05-18T07:41:34+00:00
- Post Title: (PC) Hydrophobia Prophecy

up
## Post #4
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2011-06-02T23:10:54+00:00
- Post Title: (PC) Hydrophobia Prophecy

Up!
## Post #5
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-06-13T04:55:45+00:00
- Post Title: (PC) Hydrophobia Prophecy

Anyone?
## Post #6
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2011-07-10T19:06:39+00:00
- Post Title: (PC) Hydrophobia Prophecy

Up!
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-17T13:11:49+00:00
- Post Title: (PC) Hydrophobia Prophecy

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

get FILES long

for i = 0 < FILES
    get HASH long
    get OFFSET long
    get SIZE long
    string NAME p= "%08X" HASH
    log NAME OFFSET SIZE
next i
```


Attached DLL sources with function for generate hashes (C++) and filelist (unfinished) with some filenames

Example use for Delphi.

```
function GetHash(StrType: Integer; Text: PChar): Cardinal; cdecl; external 'HashLib.dll' name '?GetHash@@YGIHPBD@Z';
```


```
begin
Len:=edtFileName.GetTextLen;
Hash:= GetHash(6,PChar(edtFileName.Text));
if Len <> 0 then
edtFileNameHash.Text:=Format('%0.8x',[Hash])
else
edtFileNameHash.Text:='';
```


Types :

6 - FileName
3 - String (for translate)

other types unknown 
[HashLib-FileList.rar](https://xentaxbackup.github.io/file/5904_HashLib-FileList.rar)
