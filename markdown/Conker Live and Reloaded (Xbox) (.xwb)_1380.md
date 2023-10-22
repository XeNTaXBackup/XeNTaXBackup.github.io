## Post #1
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-07-07T04:24:09+00:00
- Post Title: Conker Live and Reloaded (Xbox) (.xwb)

Conkers bad fur day was recently realesed on xbox only thing is...They bleeped out the cuss words! As you can imagine this ruins what would have been a perfect remake. So I had the idea maybe we could crack the sound files and insert the orginal n64 version audio (captured from the rom) into the xbox remake!  This would be historic if possible hundreds of people on forums are going crazy about this. I was hoping you guys @ XeNTaX could be the heroes
[Conker_Audio_Files.rar](https://xentaxbackup.github.io/file/331_Conker_Audio_Files.rar)
## Post #2
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-07-07T07:43:28+00:00
- Post Title: Conker Live and Reloaded (Xbox) (.xwb)

I can't help, but I fully support this effort and hope Mr.Mouse or others can crack it. Conkers bad fur day is a classic. How lame that they bleeped out cuss words.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-07T08:55:49+00:00
- Post Title: Conker Live and Reloaded (Xbox) (.xwb)

> Reply from sound.xsb
>
> 
// Header

char{4}		'SDBK'
uint16{2}	Unknown (0xB)
uint16{2}	Unknown (0xF7D1)
uint32{4}	Offset 'Wave' table (lists of strings (names for buttonclicks etc))
uint32{4}	Offset of tail part
uint32{4}	Offset of end of 'Wave'table? Start of other table?
uint32{4}	Archive/File size 
uint16{32}	Unknown (0x0) First entry in a subheader?
uint16{32}	Unknown (0x10) Offset of 'Sound' table starting from subheader?
uint16{32}	Unknown (0x09) Number of entries in unknown table (see below)?
uint16{32}	Number of entries in file? 
char{8}		Unknown


// 'Sound'table 

char{16}	'Sound'
char{20*n} 	STEntries (12 entries)
char{20*n2)	Unknown table entries (9 entries)

// STEntry

uint32{4}	Unknown
uint32{4}	Offset of name for entry in the archive (falls in the 'Wave' name list)
uint32{4}	Unknown (0xFFFFFFFF)
uint16{2}	Unknown (0x0)
uint16{2}	Unknown ( 1, 2, 4, 5, 9, 0xB, 0xC)

// 'Wave' table

char{16} 	'Wave'
char{n}		List of null-terminated strings, 12 entries.

Still have to look at the others.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-07T09:16:25+00:00
- Post Title: Conker Live and Reloaded (Xbox) (.xwb)

> Reply from *.xwb
>
> 
// Header

char{4}		'WBND'
uint32{4}	Unknown (0x3)
uint32{4}	Unknown (0x28)
uint32{4}	Unknown (0x28)
uint32{4}	Unknown (0x50)
uint32{4}	Unknown (0xa8)
uint32{4}	Unknown (0x0)
uint32{4}	Unknown (0x0)
uint32{4}	Offset of Wave data
uint64{8}	Size of Wave data (to end of .xwb file)
uint32{4}	Number of (wave) entries
char{16} 	Archivename 
uint32{4}	Size of entries in resource info table
uint32{4}	Unknown (0x40)
uint32{4}	Unknown (0x4)
uint32{4}	Unknown (0x0)

// Resource info table - For each entry :

uint32{4}	Unknown (0x0)
uint32{4}	Unknown (Type??)
uint32{4}	Offset of wave (relative to start of Wave data)
uint32{4}	Size of Wave 
uint32{4}	Unknown (0x0)
uint32{4}	unknown (0x0)

// WAVE DATA

char{n} 	The actual sound data

These contain wave data.
## Post #5
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-07-07T09:53:21+00:00
- Post Title: Conker Live and Reloaded (Xbox) (.xwb)

Have you checked xbins on this. There may be a xwb extractor already for it.

edit:

[http://www.xbins.org/index.php?action=s ... rchtxt=xwb](http://www.xbins.org/index.php?action=search&searchtxt=xwb)

03-14-2005 PC XWB Extractor 1.1 0.04MB    
02-13-2005 PC EATrax XWB Extractor 0.04MB

connect to #xbins on irc.efnet for ftp information.

The problem as I see it is getting both the audio from the N64 cart/rom and making sure it syncs up. This is all if the bleeping isn't a hardcoded option like the multiplayer is (Which is an unlockable).
## Post #6
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-07-07T21:17:20+00:00
- Post Title: Conker Live and Reloaded (Xbox) (.xwb)

> Reply from keshire
>
> Have you checked xbins on this. There may be a xwb extractor already for it.

edit:

http://www.xbins.org/index.php?action=s ... rchtxt=xwb

03-14-2005 PC XWB Extractor 1.1 0.04MB    
02-13-2005 PC EATrax XWB Extractor 0.04MB

connect to #xbins on irc.efnet for ftp information.

The problem as I see it is getting both the audio from the N64 cart/rom and making sure it syncs up. This is all if the bleeping isn't a hardcoded option like the multiplayer is (Which is an unlockable).

The audio should snyc up fine since they are identical. Also I dont plan on editing the entire game just the main parts of the game that are ruined with the bleeps (great might poo Song!!)

EDIT: ok I downloaded the program and extracted the .xwb and it gave me a .pcm now what do I do?
[000.rar](https://xentaxbackup.github.io/file/333_000.rar)
## Post #7
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-07-08T04:52:07+00:00
- Post Title: Conker Live and Reloaded (Xbox) (.xwb)

> Reply from Online_Dude
>
> keshire wrote:Have you checked xbins on this. There may be a xwb extractor already for it.

edit:

http://www.xbins.org/index.php?action=s ... rchtxt=xwb

03-14-2005 PC XWB Extractor 1.1 0.04MB    
02-13-2005 PC EATrax XWB Extractor 0.04MB

connect to #xbins on irc.efnet for ftp information.

The problem as I see it is getting both the audio from the N64 cart/rom and making sure it syncs up. This is all if the bleeping isn't a hardcoded option like the multiplayer is (Which is an unlockable).

The audio should snyc up fine since they are identical. Also I dont plan on editing the entire game just the main parts of the game that are ruined with the bleeps (great might poo Song!!)

EDIT: ok I downloaded the program and extracted the .xwb and it gave me a .pcm now what do I do?

Always hit up google for information next. ALWAYS.

[http://www.google.com/search?hl=en&q=PC ... gle+Search](http://www.google.com/search?hl=en&q=PCM+audio+converter&btnG=Google+Search)

Then if it isn't already covered ask for help.
