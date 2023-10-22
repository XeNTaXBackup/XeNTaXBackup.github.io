## Post #1
- Username: dogukan1217
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 31, 2017 8:30 pm
- Post datetime: 2017-08-04T11:05:33+00:00
- Post Title: Northgard .hdll files ?

Hi, I want to localize this game to my own language, but I can not find the language file. But there are a few files I think it is. Is there a tool to open it in the form of files .hdll?

Example:

[https://drive.google.com/file/d/0B8Z5o3 ... g1bFk/view](https://drive.google.com/file/d/0B8Z5o3jnHOERemUyUHE4LTg1bFk/view)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-08-25T12:02:21+00:00
- Post Title: Northgard .hdll files ?

directx.hdll has MZ signature, so it's EXE/DLL file. It's DirectX library
fmt.hdll same
openall.hdll same, it's OpenAL library
prefs.sav look like your save file preferences
SDL is SDL library for C++
sqlite.hdll is also SQLite library to provide database support
ssl.hdll also library, probably for SSL crypting
steam.hdll also library
ui.hdll is library, but the file looks like it's .NET I didn't find any text inside however

Unfortunately, none of the files you provided contain anything related to language. Just libraries and code

I checked the file. ILSpy doesn't recognize it as managed assembly, so I bet it's Visual C++
## Post #3
- Username: dogukan1217
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 31, 2017 8:30 pm
- Post datetime: 2017-08-27T09:01:22+00:00
- Post Title: Northgard .hdll files ?

> Reply from MaKiPL
>
> directx.hdll has MZ signature, so it's EXE/DLL file. It's DirectX library
fmt.hdll same
openall.hdll same, it's OpenAL library
prefs.sav look like your save file preferences
SDL is SDL library for C++
sqlite.hdll is also SQLite library to provide database support
ssl.hdll also library, probably for SSL crypting
steam.hdll also library
ui.hdll is library, but the file looks like it's .NET I didn't find any text inside however

Unfortunately, none of the files you provided contain anything related to language. Just libraries and code

I checked the file. ILSpy doesn't recognize it as managed assembly, so I bet it's Visual C++

Could the language file be in these files?

[https://drive.google.com/file/d/0B8Z5o3 ... hTLWs/view](https://drive.google.com/file/d/0B8Z5o3jnHOEROUVKU1V5Z3hTLWs/view)
## Post #4
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-08-28T11:04:16+00:00
- Post Title: Northgard .hdll files ?

hlboot.dat is probably major file in this. It contains all function names (imports) and has exception codes. Like this:

```
FBX was not converted to HMD 
Invalid HMD header
Can't read HMD
```


It has also names for files:
map/MarshTree03.FBX
map/MarshTree04.FBX

Even CSS:

```
<bh:09>user-select : none;
<bh:09>-moz-user-select : none;
<bh:09>-webkit-user-select : none;
}
.jqpage panel, .dialog-floating panel {
<bh:09>display : block;
<bh:09>overflow : auto;
}
.jqpage pre, .dialog-floating pre {
<bh:09>user-select : text;
<bh:09>-moz-user-select : text;
<bh:09>-webkit-user-select : text;
}
.jqpage pre .kwd, .dialog-floating pre .kwd {
<bh:09>color : #1518FF;
}
.jqpage pre .meta, .dialog-floating pre .meta {
<bh:09>color : #156018;
}
.jqpage .panel, .dialog-floating .panel {
<bh:09>overflow : auto;
<bh:09>background-color : 
```


paths:
D:\\Projects\\haxe\\std/haxe/ds/BalancedTree.hx

A lot of unknown data afterward 

About extraData.dat:
Header is: XTRAGcTS (I don't know what is it)
after that encoded data appears and I completely don't know how to decode it (It has no indicator what was used to compress it)

I made some googling at found that:
Northgard is entirely written in Haxe, using the Heaps engine and the
HashLink runtime

I've never heard about Haxe, but it looks really easy, like a C# or Java, so it's fine


EDIT:
Found probably XTRA exporter:
[https://github.com/HeapsIO/heaps/blob/m ... xporter.ms](https://github.com/HeapsIO/heaps/blob/master/tools/xtra/xtraExporter.ms)

From game engine source I was able to find so far the "DynamicText" class, which is basically a XML loader. All the needed files should be in files with 'PACK' header (.pak)
## Post #5
- Username: dogukan1217
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 31, 2017 8:30 pm
- Post datetime: 2017-09-01T12:33:48+00:00
- Post Title: Northgard .hdll files ?

> Reply from MaKiPL
>
> hlboot.dat is probably major file in this. It contains all function names (imports) and has exception codes. Like this:
Code: Select allHMD
FBX was not converted to HMD 
Invalid HMD header
Can't read HMD

It has also names for files:
map/MarshTree03.FBX
map/MarshTree04.FBX

Even CSS:
Code: Select alldialog-floating th {
<bh:09>user-select : none;
<bh:09>-moz-user-select : none;
<bh:09>-webkit-user-select : none;
}
.jqpage panel, .dialog-floating panel {
<bh:09>display : block;
<bh:09>overflow : auto;
}
.jqpage pre, .dialog-floating pre {
<bh:09>user-select : text;
<bh:09>-moz-user-select : text;
<bh:09>-webkit-user-select : text;
}
.jqpage pre .kwd, .dialog-floating pre .kwd {
<bh:09>color : #1518FF;
}
.jqpage pre .meta, .dialog-floating pre .meta {
<bh:09>color : #156018;
}
.jqpage .panel, .dialog-floating .panel {
<bh:09>overflow : auto;
<bh:09>background-color : 

paths:
D:\\Projects\\haxe\\std/haxe/ds/BalancedTree.hx

A lot of unknown data afterward 

About extraData.dat:
Header is: XTRAGcTS (I don't know what is it)
after that encoded data appears and I completely don't know how to decode it (It has no indicator what was used to compress it)

I made some googling at found that:
Northgard is entirely written in Haxe, using the Heaps engine and the
HashLink runtime

I've never heard about Haxe, but it looks really easy, like a C# or Java, so it's fine


EDIT:
Found probably XTRA exporter:
https://github.com/HeapsIO/heaps/blob/m ... xporter.ms

From game engine source I was able to find so far the "DynamicText" class, which is basically a XML loader. All the needed files should be in files with 'PACK' header (.pak)

Can not a tool be made?
