## Post #1
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-23T10:45:39+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

I've had the insane idea to translate the PSP Game Valkyria Chronicles 3. You know this game is only in Japanese Language, so there are problems with Shift-Jis Encoding, translation itself from Japanese and, last but not least, encrypted DATA.BIN file.
What I've done, from the original UMD disk:
- dumped ISO with a PSP-1004, the old fat one,
- the hex editor (MadEdit, ShiftJis Encoding) says that DATA.BIN is a PGD (encrypted/compressed) file,
- extracted files with bms (CPK Script)
- I found 10147 files in various file formats.
This is a list of files extensions:
ABD
ABR
ATX
BF1
BHV
BIN
CNK
GRD
HCL
HCM
HSM
HSP
HTF
HTR
HTX
MLX
MMF
MMR
MSB
MTP
MVP
MXE
NAD
OMP
PAK
PSB
PVS

MLX files, in hex editor start with "IZCA" (like IZCA files in Valkyria Chronicles, 3D Models?), 
HTX files start with HTEX (textures?).
The file SCRIPT_LIST.BIN, addresses to these files:

```
ROOT List ev10000.msb ev10101.msb ev10102.msb
```
 and so on...
There's a chance to find dialogues, texts, etc, among all these files?
Some help would be really appreciated.
## Post #2
- Username: MrShyCity
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 17, 2012 6:48 am
- Post datetime: 2012-07-23T15:31:00+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

hmm have you tried [UTF-8] Unicode 8 bit sometime the script is unicode
## Post #3
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-24T09:37:41+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

Tried with [UTF-8] and [UTF-16LE]. No results..
But I know that this game has a chinese translation mod.
It would be interesting to find this patch and open it...
## Post #4
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-07-24T10:24:17+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

Someone start the translation already, or this is an other game?
[http://vc3translationproject.wordpress.com/](http://vc3translationproject.wordpress.com/)
## Post #5
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-24T15:08:02+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

> Reply from swuforce
>
> Someone start the translation already, or this is an other game?
http://vc3translationproject.wordpress.com/

Yes, it's the same game, but that project is for the english version.
I want to translate in another language. I contacted the authors but they won't release the original japanese scripts or their WIP
until they'll release the english patch.
And so I have to start from zero..
## Post #6
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-24T18:46:49+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

If anyone knows how to get that chinese patch, it'd be a great help, I guess..
even just to understand what files contain texts..
## Post #7
- Username: MrShyCity
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 17, 2012 6:48 am
- Post datetime: 2012-07-25T21:57:30+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

have you go [http://www.romhacking.net/forum/index.php?topic=13668.0](here) there are talking about interesting stuff i just read half of it.
## Post #8
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-26T10:08:08+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

Yes, there's some kind of research about this game..
the group that started translation in english, based on the chinese script, is reticent to share the original japanese dump..
I don't see any good reason, but this is it..
I don't want to steal their job, just to share the knowledge how to dump original scripts from encrypted files in data.bin...
## Post #9
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-26T10:35:14+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

I found an interesting file.
Jis2UCS.cnk, a TOC... I think...
This is the initial hex code, in MadEdit with [UTF-16LE]:



The second block is the Katakana syllabary.

The Hiragana syllabary starts at 00004860.

Greek alphabet starts at 00004C62.

Cyrillic alphabet starts at 00004E62.

Other blocks have kanji:



Any advice?
## Post #10
- Username: MrShyCity
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 17, 2012 6:48 am
- Post datetime: 2012-07-27T02:21:51+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

it seems you found letters "not sure though"
have you try translating them on google see if it recognize it
is that the only script you have found?
## Post #11
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-27T09:49:19+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

I didn't found plain japanese text for now..
There's a file script_list.bin in the first part similar to the file above. This is the final part with addresses to evXXXXX.msb files.
EV = Event?
## Post #12
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-27T10:04:53+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

Final code of ev10000.msb:


Other parts look gibberish
## Post #13
- Username: MrShyCity
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 17, 2012 6:48 am
- Post datetime: 2012-07-27T22:54:46+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

those are files inside the script_list.bin "you probably already know that"
you need to dump/extract those files from script_list
## Post #14
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-28T09:34:24+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

> Reply from MrShyCity
>
> those are files inside the script_list.bin "you probably already know that"
you need to dump/extract those files from script_list

Actually, those files are already dumped..
## Post #15
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-07-31T08:31:49+00:00
- Post Title: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

No help? No advice? Nothing?
## Post #16
- Username: [Unknown]
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 04, 2012 3:12 pm
- Post datetime: 2012-08-25T18:53:55+00:00
- Post Title: Re: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

> Reply from rev3rsix
>
> No help? No advice? Nothing?

Here's some information:

```

## DATA.BIN datafile

This is a PGD-encrypted CPK file.  The file can be decrypted by using JPCSP's
CryptoEngine code, or by simply running the game with certain settings
enabled.

### CPK file

The actual CPK has a general format, and can be worked with using CRIWARE's
crifilesystem utilities.  The game appears to accept CPKs generated by older
versions of the CRIWARE's softare.

The general format seems to consist of:

 * 2048 byte general header.
 * TOC (file records, filenames.)
 * file data (in blocks of 2048 bytes.)

### CPK TOC

The actual structure of the TOC was not really deciphered, except that it has
24-byte records (starting 91 bytes in?) for each file within the CPK.  These
files are identified by filename, and the ID is not important (so they can be
in any order.)

The 24 bytes are 6 big-endian DWORDs, and include the filename pointer, ID,
length, and position of the file data.

## Files inside the CPK

There are several types of files in the CPK, but they all use a common
overall format.  High level, it looks something like this:

 * packet header
   * packet data
   * packet header
     * packet data
 * packet header
   * packet data

The NAD files don't exactly conform to this format, though, for some reason.

### Packet headers

Each packet has a 4 byte identifier, like MTPA.  The header format appears
to follow this format (in little endian):

 * char[4] magic;
 * uint32 packet_size; // not including header, round up to 16.
 * uint32 header_size;
 * uint32 flags;

If the header_size is 32 or greater (except for MSCR packets), the next
16 bytes are as follows:

 * ubyte[4] unknown;
 * uint32 data_size; // not including header, round up to 16.
 * ubyte[4] unknown;
 * ubyte[4] unknown;

### Packet data and sub-packets

For packets with headers of 32 bytes or more, there may be "sub-packets."
These generally look like:

	+------------------------------+
	| Containing Packet Header     |
	+------------------------------+
	| Containing Packet Data       |
	| ...                          |
	|                              |
	| +--------------------------+ |
	| | Sub Packet #1 Header     | |
	| +--------------------------+ |
	| | Sub Packet #1 Data       | |
	| |                          | |
	| +--------------------------+ |
	| | Sub Packet #2 Header     | |
	| +--------------------------+ |
	| | Sub Packet #2 Data       | |
	| |                          | |
	| +--------------------------+ |
	+------------------------------+

Everything is aligned to 16 bytes, which is very convenient for hex editors.
The data size or packet size can be 0, which means there's no data.

### Sub-structures

Even though the files already have a nesting capability for the headers,
sometimes there will be a data packet that is opaque, but itself is just
another file formatted in this same way (with headers and nesting all over
again.)

For example, MLX files (which contain graphics) have an IZCA packet that
works exactly this way.

### XOR encryption

Some files have their data segments encrypted using a rolling XOR.  How
it determines the first byte is not understood, but generally not needed
because the files follow a consistent format.

If the "flags" uint32 in the header has its 19th bit set (0x40000), then
this encryption is being used.

You can simply XOR each byte by the previous byte (pre-encrypted.) This is
easy to decrypt and re-encrypt.

### MTP files (MTPA packets)

MTPA packets are fairly simple and just have the Shift-JIS text with
each byte incremented by one for no apparent reason.

Note that pointers within the data are generally relative to the header.
That is, if the header is 32 bytes, than 0x20 would point to the
beginning of the data.

	struct info_header (16 bytes)
		DWORD unknown5		always 0x4000000f
		DWORD pointer_count	number of pointer records
		DWORD data_size		number of DWORDs each data record is
		DWORD data_count	number of data records

	struct unknown6[]		repeats data_size times
		DWORD unknown7		always <= 2

	<pointer segment>
	struct pointer_record[]	repeats pointer_count times
		DWORD data_pos		pointer into data record segment

	<data_segment>
	struct data_record[]	repeats data_count times
	if data_size = 2
		DWORD id			id of voice data within OD_VOICE.AFS
		DWORD text_pos		position of text within text segment
	if data size = 4
		DWORD flags1?		unknown meaning, varies wildly
		DWORD id			id of voice data within OD_VOICE.AFS
		DWORD text_pos		position of text within text segment
		DWORD flags3?		0x00 or 0x01 with 4 mysterious unique exceptions

	struct unknown8[]		always once?
		DWORD unknown9		unknown meaning
					EACH BYTE INCREMENTED

	<text_segment>
	struct text_record[]	undetermined length?
		UBYTE* shiftjis		text in shift jis, null terminated
					EACH BYTE INCREMENTED

	EACH BYTE INCREMENTED section always multiple of 4 bytes
					
	struct footer_padding
		DWORD padding		always 0x00 (padding to align ENRS)

### MXE files (MXEC packets)

MXEC packets are quite complicated, but consistent.

Note that pointers within the data are generally relative to the header.
That is, if the header is 32 bytes, then 0x20 would point to the
beginning of the data.

		DWORD unknown				varies, xor, doesn't seem important
		DWORD unknown				always 0x60
		DWORD something4_header_ptr	0x00 or pointer to something4 header.
		DWORD something2_header_ptr	0x00 or pointer to something2 header.
		DWORD unknown				meaning unknown, 0x00/0x01.
		DWORD unknown				always 0x00 (ends at 24)
		DWORD unknown				sometimes 0x00 or 0x01? MAYBE something6_count??
		DWORD something6_ptr		pointer to something6 data.
		DWORD[9] unknown			always 0x00 (ends at 68)
		DWORD something1_count		number of something1 records
		DWORD unknown				always 0xA0
		DWORD[13] unknown			always 0x00
	
	something1[]					always something1_count of them.
		DWORD id					seems like an id, counts up...
		DWORD type_ptr				points to ascii identifier in file.
		DWORD length				length of data.
		DWORD data_ptr				points to beginning of data.

	<something1 data>				variable in size, ends at last data_ptr + last length.
		DWORD[] varies				varies per record type.
	(padded to a multiple of 16 bytes.)

	<something4 header> (optional)
		DWORD unknown				always 0x00
		DWORD something4_count		number of something4 records.
		DWORD something4_ptr		pointer to something4 records.
		DWORD unknown				always 0x00
		DWORD[12] unknown			always 0x00

	something4[]					always something4_count of them.
		DWORD unknown				increasing, appears pointer like?  unknown meaning.
		DWORD unknown				optional text pointer, sometimes 0x00.
		DWORD something5_count		count of sub-something5's inside the something4.
		DWORD something5_ptr		pointer to the something5 records.
		DWORD[6] unknown			always 0x00
		DWORD unknown				usually 0x00, sometimes 0x01?
		DWORD weird_ptr				0x00 or pointer after text segment.
		DWORD[4] unknown			always 0x00

	something5[]					always something5_count of them PER something4.
		DWORD text_ptr				pointer to an ascii identifier.
		DWORD unknown				seems like a number?  maybe value for text_ptr.
		DWORD data_ptr				points to some extra data.
		DWORD unknown				always 0x00?

	<something5 data>				variable size?
		DWORD unknown				one per pointer?

	(padded to a multiple of 16 bytes after ALL the something5s.)

	<something2 header> (optional)
		DWORD unknown				always 0x00
		DWORD something2_count		count of something2 records.
		DWORD something2_ptr		pointer to something2 records.
		DWORD something3_count		count of something3 records.
		DWORD something3_ptr		pointer to something3 records.
		DWORD[3] unknown			always 0x00

	something2[]					always something2_count of them.
		DWORD[2] unknown			unknown meaning.
		DWORD path_ptr				pointer to path string.
		DWORD filename_ptr			pointer to filename string.
		DWORD[6] unknown			unknown meaning.

	something3[]					always something3_count of them.
		DWORD unknown				increases, seems like a pointer?  doesn't seem to match file?
	(padded to a multiple of 16 bytes.)

	<something6 data> (optional)
		DWORD unknown				unknown meaning.
	(padded to a multiple of 16 bytes.)

	<text starts here>
	(padded to a multiple of 16 bytes.)

	<weird data>
	(padded to a multiple of 16 bytes.)

Not everything is understood.  Some of the records have varying structure
defined by their identifier pointer, and may have string pointers embedded
within those structures.

The text itself is in Shift-JIS, null terminated.

## Comparison with Valkyria Chronicles 2

Valkyria Chroncles 2 seems to use the same data files and format, in general.
The primary difference is that rather than PGD-encrypting the DATA.BIN file,
instead they encrypt each file within the CPK.

Each file within the CPK has a 16-byte header which serves as a key.

The file is treated as a series of sets of 4 DWORDs, and uses the following
basic algorithm:

	uint32[4] key;
	uint32[] data;
	
	for (int i = 0; i < data.length; i++)
	{
		int key_i = i % 4;

		key[key_i] = key[key_i] * 3 + 1;
		data[i] ^= key[key_i];
	}

However, when it hits EOFC packets or other boundaries, it appears to do
something different, so this is not a complete description of the format.
```


Sorry if that's a bit rough, typed it up as documentation for myself (it's in markdown format, by the way.)

And also, some information on text within the files:

```

The text supports a few formatting codes which are sometimes used.  For the
most part, it's best to just use the same codes the Japanese text used in
roughly the same places.

Not all codes are supported everywhere.

The codes are:

 * **@lt0**: Left justifies the current and following lines.  Not actually
   used within the game.  This resets e.g. @lt1.
 * **@lt1**: Centers the current and following lines.  Interacts badly with
   pound (#) signs.
 * **@lt2**: Right aligns the current and following lines.  Not actually
   used within the game, and interacts badly with pound (#) signs.
 * **@db#**: # is a number like 1.  Defines the spread for a text shadow,
   the game only uses @db2.
 * **@dt#**: # is a number like 1.  Affects the number of shadows the text
   has drawn (combined with @dc and @db.)
 * **@fcFF000000**: Make text black (FF is alpha, 000000 is color.)
 * **@fci**: Resets the text color back to what it was before.
 * **@dcFF000000**: Show a text shadow (FF is alpha, 000000 is color.)
 * **\n**: The same as an enter.  Sometimes seems to show extra space, so
   as a rule of thumb use it when the Japanese does.
 * **#**: In some dialogs (like tutorials), pound signs wait for X to be
   pressed and start a new screenful of text.  Sometimes there are two in
   a row for this function, for unknown reasons.

Note: the @ codes (except @fci) may need to be terminated by a colon (:).
They keep going as long as there are matching characters (0-9, or in the
case of colors, A-F and a-f as well.)
```


Well, I'm not sure how that other group's Japanese -> Chinese -> English is gonna turn out, but they seem enthusiastic, and hey, they actually have translators.  Me and a friend and fun pulling these things apart, anyway.  They probably know all this anyway, not sure why they weren't willing to share.

There's also the font in a file like .BF1 or something.  You may need to change it to get your character set (we parsed it in to generate an accurate preview to work with text width issues... no translator, but hey, it's nice to file like we've torn apart the majority of the game.)  I would just replace Japanese characters and make your insertion script translate your text to those.

Note that there are generally no text-size limits, but there are a LOT of visual width limits (most are reasonable.)  Also, they did a good job of not reusing strings.  Unfortunately, there are a few strings in the ELF itself as well.  Most of it is in UTF-8, iirc.  I think the tank name is in UTF-16LE, though (annoyingly.)

I would ignore the script list, CNK files, MSB files, etc.  They're just red herrings.  No text there.

What language are you planning to translate to, anyhow?

-[Unknown]
## Post #17
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-09-04T23:05:25+00:00
- Post Title: Re: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

Thanks Unknown for your help.

I'd like to translate in italian language..
## Post #18
- Username: [Unknown]
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 04, 2012 3:12 pm
- Post datetime: 2012-09-05T05:49:31+00:00
- Post Title: Re: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

Cool.  I dunno a lick of Italian, but at least it's all Latin characters so it shouldn't be super hard.

Here's a version with some minor cleanup (and being formatted automatically as HTML):
[http://wrttn.in/04fb3f](http://wrttn.in/04fb3f)

Note that there are several images which contain text in them, some of it weird English, some of it Japanese.  You'll want pngquant and gimconv for those if you plan to do them.

And, at least for me, the game doesn't work properly in JPCSP - but even so, it's definitely the easiest way to test things.  Things just don't render properly after you go past the first action in a battle.  Would love to know if there was some workaround for that, aside from saving and loading.

-[Unknown]
## Post #19
- Username: rev3rsix
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:40 pm
- Post datetime: 2012-09-07T16:39:35+00:00
- Post Title: Re: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

Well, I don't have your knowledge in exadec, a little help how to extract text and image is welcome!!
## Post #20
- Username: ohnhai
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 08, 2013 8:16 pm
- Post datetime: 2013-01-09T10:58:34+00:00
- Post Title: Re: Valkyria Chronicles 3  - Senjou no Valkyria 3 [PSP]

> Reply from rev3rsix
>
> Thanks Unknown for your help.

I'd like to translate in italian language..
[http://vc3translationproject.wordpress.com/](http://vc3translationproject.wordpress.com/)

the guys here are translating it into english.. maybe you could help them and get an Italian version on the go too
