## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T20:38:50+00:00
- Post Title: Favorite hex editor

So what kind of hex editors does everyone use? Maybe there are some we've never heard of that are quite useful.

I'm using 010 editor but sadly they don't support half-float conversion on the fly (whereas other hex editors do)
Only reason I use it is because I really like the UI, while most hex editors look like they're built for people that are very computer-oriented and don't mind ugly mechanical UI's.

It doesn't seem to load RAM either.
## Post #2
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2012-02-19T18:46:35+00:00
- Post Title: Favorite hex editor

I use Hex Workshop
## Post #3
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-02-19T22:00:18+00:00
- Post Title: Favorite hex editor

> Reply from ameneko
>
> I use Hex Workshop
Me too. The datavisualizer is great!

Would be nice if there were a relative search and a more complex colormapping feature.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-19T22:24:58+00:00
- Post Title: Favorite hex editor

xvi32
## Post #5
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2012-02-21T00:50:57+00:00
- Post Title: Favorite hex editor

i use 010 Editor.  The binary templates have been extremely helpful to my work.  Now if i could only get them to add some of the improvements i suggested, it would be even better.

```

string hfloatRead( const hfloat &v )
{
	uint32 dataValue;
	float  fValue;
	
	dataValue = 0;
	
	if (v & 0x7C00)
	{
		dataValue = ((v & 0x7C00) + 0x1C000) << 13;
	}
	
	dataValue |= ((v & 0x8000) << 16) | ((v & 0x03FF) << 13);
	
	string s;
	SPrintf( s, "%x", dataValue );
	SScanf( s, "%x", fValue );
	SPrintf( s, "%f", fValue );
	return s;
}

```


Not complete, but more than enough for the validation purposes i usually use it for.
## Post #6
- Username: JohnsJ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 17, 2012 7:58 pm
- Post datetime: 2012-05-17T12:09:05+00:00
- Post Title: Favorite hex editor

Ah yeah, I use 010 Editor as well.   
And I quite like it!
## Post #7
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-05-17T14:08:14+00:00
- Post Title: Favorite hex editor

Ultraedit
Notepad++

This is why I can't hack stuff ;-D
## Post #8
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-17T15:31:28+00:00
- Post Title: Favorite hex editor

Hex Editor Neo
## Post #9
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2012-05-18T06:02:09+00:00
- Post Title: Favorite hex editor

1. 010 editor
2. axe hex editor

* dataworkshop is an open source hex editor ! what is your idea about modifying its source code or updating ... and making some improvement in it ?
[http://www.dataworkshop.de/download.html](http://www.dataworkshop.de/download.html)

 


also Binary Browser looks amazing because of supporting file structures templates ...
## Post #10
- Username: harpseal
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:48 am
- Post datetime: 2012-06-01T08:34:56+00:00
- Post Title: Favorite hex editor

010 editor, among them is the best.
## Post #11
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-06-10T05:56:23+00:00
- Post Title: Favorite hex editor

Hex Workshop is the best.
## Post #12
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2012-06-17T02:44:34+00:00
- Post Title: Favorite hex editor

1.Hex Workshop. Support half float.
2.010 Editor. Binary Template is good.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-04-16T16:52:41+00:00
- Post Title: Favorite hex editor

010 editor v4 comes with the ability to modify the inspector using an inspector template (in Tools --> Options)
This allows you to define custom functions for interpreting data on-the-fly.

This is the default template

```
//--- 010 Editor v4.0 Binary Template
//
// File:     Inspector.bt
// Author:   SweetScape Software
// Revision: 1.0
// Purpose:  This template may be used 
//  to customize the auto tab of the 
//  Inspector with your own variables. 
//  See the Inspector section of the 
//  Options dialog for more information. 
//-----------------------------------
RequiresVersion( 4.0 );

// Calculate the position for each variable,
//  either at the beginning of the selection
//  or at the current cursor position.
local int64 pos;
if( GetSelSize() > 0 )
    pos = GetSelStart();
else
    pos = GetCursorPos();

// Define variables for the inspector
FSeek( pos ); byte     _si8  <name="Signed Byte">;
FSeek( pos ); ubyte    _ui8  <name="Unsigned Byte">;
FSeek( pos ); short    _si16 <name="Signed Short">;
FSeek( pos ); ushort   _ui16 <name="Unsigned Short">;
FSeek( pos ); int      _si32 <name="Signed Int">;
FSeek( pos ); uint     _ui32 <name="Unsigned Int">;
FSeek( pos ); int64    _si64 <name="Signed Int64">;
FSeek( pos ); uint64   _ui64 <name="Unsigned Int64">;
FSeek( pos ); float    _f    <name="Half Float">;
FSeek( pos ); float    _f    <name="Float">;
FSeek( pos ); double   _d    <name="Double">;
FSeek( pos ); char     _s [ReadStringLength(pos,256)]  <name="String">;  // limit to 256 characters
FSeek( pos ); wchar_t  _ws[ReadWStringLength(pos,256)] <name="Unicode">; // limit to 256 characters
FSeek( pos ); DOSDATE  _dd   <name="DOS Date">;
FSeek( pos ); DOSTIME  _dt   <name="DOS Time">;
FSeek( pos ); FILETIME _ft   <name="FILETIME">;
FSeek( pos ); OLETIME  _ot   <name="OLETIME">;
FSeek( pos ); time_t   _tt   <name="time_t">;

```


Anyone know how to add half-floats to it?
[inspector.jpg](https://xentaxbackup.github.io/file/6333_inspector.jpg)
