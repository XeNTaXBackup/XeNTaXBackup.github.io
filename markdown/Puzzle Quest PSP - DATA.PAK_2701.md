## Post #1
- Username: Charcoal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 12, 2007 7:16 am
- Post datetime: 2007-07-12T10:30:16+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

So, I'm trying to extract the data from the DATA.PAK, from Puzzle Quest PSP.

But as you could possibly tell, I've had no luck 

It's not a Quake .PAK file, it;s not a RAR, ZIP, or any other "normal" compression I know of.
And there doesn't seem to be any human-readable hearer or footer information regarding what compression scheme it is.

Also, inside the archive there should be:
LUA scripts
PNG images (but this could obviously be different formats)
XML data
There might be a few other files, but they will be making up the majority of them.

So, now I turn to you guys.

I've used the WATTO Archive Cutter and I can't attach the result.
So, here's a link: [http://www.rocketreplay.com.au/charcoal/DATA.PAK.zip](http://www.rocketreplay.com.au/charcoal/DATA.PAK.zip)

If needed, I'm sure I could also find the space to put the whole ~80Mb file somewhere.

Thanks for the help!

-Charcoal
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-20T21:25:11+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

Yeah, there's definitely such files in there, see attachment. I'm trying to figure out the stream structure.
[e.png](https://xentaxbackup.github.io/file/1277_e.png)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-20T21:35:50+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

Right, and I think these XML files are compressed, DenizOezmen might say : 'Huffman!" ?  Looks like it has a dictionary??
[font.zip](https://xentaxbackup.github.io/file/1278_font.zip)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-20T22:37:59+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

Allright, I've cornered the structure of the file, will create a plugin for MexCom.
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-21T01:21:40+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

> Reply from Mr.Mouse
>
> Right, and I think these XML files are compressed, DenizOezmen might say : 'Huffman!" ?
I wouldn't dare suggest such a ghastly thing. 

Actually, the given file is not compressed, but rather seems to be a binary representation of an XML file intended for easier parsing. This particular file is even larger than its textual representation, which the programmers could have partly avoided by not duplicating entries in the dictionary (which you have correctly identified):

```
  <Fonts numfonts="39">
    <Font id="0" tag="font_system" file="Assets\Fonts\System" pointsize="18" baseline="14" lineheight="0" r="255" g="245" b="235" a="255" scale="1">
    </Font>
    <Font id="1" tag="font_button" file="Assets\Fonts\WC_Button" pointsize="24" baseline="18" lineheight="0" r="255" g="245" b="235" a="255" scale="1">
    </Font>

[... 37 other font defintions ...]

  </Fonts>

```

[Here's a tool](http://www.xentax.com/uploads/author/denizoezmen/_XMLConv.zip) that outputs the XML structure to the console. Usage:

```
XMLConv font.xml
```

Due to the output method, it's not really useful yet and might fail with other files, since the above example does not have enough structure to identify all values within the file.
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-21T05:15:05+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

> Reply from Deniz Oezmen
>
> Actually, the given file is not compressed, but rather seems to be a binary representation of an XML file intended for easier parsing.
A similar approach is used in Age of Empires 3 and Ghost Recon 2 (*.xmb)
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-21T08:28:19+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

> Reply from Deniz Oezmen
>
> 
Actually, the given file is not compressed, but rather seems to be a binary representation of an XML file intended for easier parsing. This particular file is even larger than its textual representation, which the programmers could have partly avoided by not duplicating entries in the dictionary (which you have correctly identified):

Nice going!
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-23T22:11:37+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

```
<?xml version="1.0"?>
  <TextLibrary>
    <Text tag="[MONSTER_MARB_NAME]">
    </Text>
    <Arboleth  Warning: node count 1 (50) does not match node count 2 (2), mightfail
 TextLibrary="TextLibrary" extLibrary="" tLibrary="" tag="[MONSTER_MBAT_NAME]" Giant Bat="Text">
      <xtLibrary  Warning: node count 1 (2) does not match node count 2 (0), mightfail
>
      </xtLibrary>
      <[MONSTER_MBAT_DESC]  Warning: node count 1 (1286) does not match node count 2 (1355), mightfail
 ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="" ="">
        <  Warning: node count 1 (1129144146) does not match node count 2 (1130320969), mightfail
Exception ERangeError in Modul XMLconv.exe bei 00004927.
Fehler bei Bereichspr

```
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-23T22:28:51+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

Okay, here's the plugin for MultiEx Commander as promised. Will open those files and extract the contents for you.

I also attach a table of contents of the PAK file. 

Will post the details when I have the time.
[MexCom_Plugin_PuzzleQuestPSP.zip](https://xentaxbackup.github.io/file/1280_MexCom_Plugin_PuzzleQuestPSP.zip)

[data_pak_pq_psp.zip](https://xentaxbackup.github.io/file/1279_data_pak_pq_psp.zip)
## Post #10
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-23T23:55:46+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

> Reply from Mr.Mouse
>
> Guess you were on the right track at least!
And fortunately, it's [not too hard to fix](http://www.xentax.com/uploads/author/denizoezmen/_XMLConv.zip):

```
  <TextLibrary>
    <Text tag="[MONSTER_MARB_NAME]">
      Arboleth
    </Text>
    <Text tag="[MONSTER_MARB_DESC]">
      Arboleths are violent and mindless creatures of chaos. They absorb energy from enemy spells to heal themselves.  They can also use the Consume Mana spell to power the Chaos Bolt spell.
    </Text>
    <Text tag="[MONSTER_MARB_CAPT]">
      You have captured an Arboleth. Once you have built a Mage Tower in your capital city, you will be able to learn the Consume Mana and Chaos Bolt spells from this creature.
    </Text>

[... tons of descriptions ...]

  </TextLibrary>
```

(Actually, I still don't know more about the missing values. We simply discovered a new node type within the document. )

Ah, and the tool now creates a separate text output file for each input ...
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-24T08:18:30+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

And the format of the Puzzle Quest (PSP) .PAK files:

```

Byte(16)		Header
Byte(n)			Resource Info Table
byte(n)			String Table
Byte(n)			Resource raw data

// Detailed structure:

// Header

uint32		Size of resource information data
uint32		Relative Offset of String Table (Size of Resource Info Table)
uint32	 	Absolute offset of Resource Info Table (Size of Header) 
uint32		Version number (1) ?

// Resource Info Table
//
// The number of variables per entry vary depends on type of entry (Folder or File)
// Folders take up 5 uint32 (or 1 uint32 and 2 uint64), Files take up three uint32. 
// As files can only have a value up to uint32, and the number of files/folders is hardly going to 
// exceed an uint32 value, it's probably save to assume that the authors only use uint32 
// values. 

uint32		Relative Offset of Resource Name in String table (starting from 0)
uint32 		IF Folder --> Number of Resources in Folder
		IF File --> Absolute Offset of Resource  
uint32		IF Folder --> Unknown (but could mean that the previous is actually an uint64). 
		IF File --> Size of Resource
uint32		IF FOLDER --> Number of SubFolders in Folder
uint32		IF FOLDER --> Unknown (but could mean that the previous is actually an uint64).

// String Table
//
// To save space, the authors have not listed full paths of each resource in the archive. 
// Instead, they saved a tree, and thus only need to save each folder and file once, 
// as a single null-terminated string. 
//
// The order is simple and also applies to the Resource Info Table obviously.
// The first node is the root ("\"). The Resource Info table tells us this node has 0 files and 2 subfolders
// If there are files or subfolders at a node, the archive lists first the files in sequence and then the folders. 
// (Again, this applies to both the Resource Info Table as the String Table)
// Once this is listed, the next resource will be the first subfolder of the current node. 
// If this too has subfolders, then the subsequent node listed will be the first subfolder of this one. 
// Once all subfolders have been listed of a given node (including any deeper files and subfolders), 
// the next-in-line subfolder of the parent node will be listed. 
// And so on....until we get back a the root node and no more folders are left. 

```


Understandable ?
## Post #12
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-24T08:49:58+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

> Reply from Mr.Mouse
>
> Understandable ?
Completely. Good work!
## Post #13
- Username: Charcoal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 12, 2007 7:16 am
- Post datetime: 2007-07-25T09:40:42+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

Thanks for all the work, but it isn't working 

The Lua scripts also seem to have been "compressed", much like the xml files were.

But even if someone were to figure that out I doubt that my original plan would work, there are alot more lua scripts in the PSP version, compared to the PC demo.
AND there is a PC full version coming out.
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-25T09:46:00+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

> Reply from Charcoal
>
> Thanks for all the work, but it isn't working 

The Lua scripts also seem to have been "compressed", much like the xml files were.

But even if someone were to figure that out I doubt that my original plan would work, there are alot more lua scripts in the PSP version, compared to the PC demo.
AND there is a PC full version coming out.

Exactly what isn't working?
## Post #15
- Username: SHOCKeR
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 14, 2008 6:02 pm
- Post datetime: 2008-02-14T10:24:12+00:00
- Post Title: Puzzle Quest PSP - DATA.PAK

Thanks Mr. Mouse for a plugin for extraction gamefiles from DATA.PAK!
If I understand, your plugin only for extraction, but not for creation or saving after changes..

Could you modify this plugin, that I could save DATA.PAK after some changes? 

Thanks for the help!

SHOCKeR
## Post #16
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-14T10:30:31+00:00
- Post Title: Re:

> Reply from Charcoal
>
> The Lua scripts also seem to have been "compressed", much like the xml files were.
Does this problem still persist?
May you upload some example files?
