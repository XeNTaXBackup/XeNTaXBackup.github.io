## Post #1
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2012-10-22T16:15:22+00:00
- Post Title: Carmageddon 1 IOS (.WAD Extracton Help)

Hi, would someone with expertise look to see if its possible to extract the contents & if possible Reimport the files of this DATA_IOS.WAD please.

Here is the DATA_IOS.WAD
[https://dl.dropbox.com/u/17063965/Carma ... ta_IOS.zip](https://dl.dropbox.com/u/17063965/Carmageddon%201%20IOS/Data_IOS.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-24T04:27:03+00:00
- Post Title: Carmageddon 1 IOS (.WAD Extracton Help)

this is a strange format - i cannot find the offset table

```
byte   data[ unknown_zsize ]

note: data is aligned to 4 byte blocks

```


if the data is compressed it uses zlib
## Post #3
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2012-10-24T09:54:47+00:00
- Post Title: Carmageddon 1 IOS (.WAD Extracton Help)

Not sure if this page will help, but it seems there are 3 variations of the WAD for at 1, 2 & 3.

I think DATA_IOS.WAD is type 1 as it includes the txt files & models of the game & type 2 & 3 only do textures.

Though I'm probably wrong 

Link to said page.
WAD2
[http://www.gamers.org/dEngine/quake/spe ... spec_7.htm](http://www.gamers.org/dEngine/quake/spec/quake-spec34/qkspec_7.htm)
&
Doom WAD (WAD1)
[http://tkboom.sourceforge.net/wadfile_spec.shtml](http://tkboom.sourceforge.net/wadfile_spec.shtml)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-24T12:55:40+00:00
- Post Title: Carmageddon 1 IOS (.WAD Extracton Help)

Absolute different archives
## Post #5
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2012-10-25T08:25:43+00:00
- Post Title: Carmageddon 1 IOS (.WAD Extracton Help)

The program WADEdit from this site rr2000.toshiba-3.com/pc-files can unpack (and repack) the file DATA_IOS.WAD

Btw, there's an offset table at 0x11860-0x15CD3.
## Post #6
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2012-10-25T11:47:28+00:00
- Post Title: Carmageddon 1 IOS (.WAD Extracton Help)

> Reply from herbert3000
>
> The program WADEdit from this site rr2000.toshiba-3.com/pc-files can unpack (and repack) the file DATA_IOS.WAD

Btw, there's an offset table at 0x11860-0x15CD3.

I already have this app WadEdit, but it was not working on my computer (Win7, kept coming up that it wasn't responing) but redownloaded it & it now works :-/ thank you.

Not much I can edit bar in game properties  car models & file structure is different from the original 

Was trying to workout if I could have the wad point to an external folder, would have saved me rebuilding a wad every time I want to test something. (was a no go )
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-25T17:22:34+00:00
- Post Title: Carmageddon 1 IOS (.WAD Extracton Help)

i wanted to write a quickbms script for this, but cannot spend anymore time on the format.

i also couldn't find the file spec used by 'wadedit', so here is my current info:

```
int32 unknown
int32 unknown (0)
int32 str_table_size (including alignment)

str_table:
  null-terminated string table
  aligned to 4 bytes

int32 struct_1_num

struct_1:
  int32 index : 24 (incremental index 0 to struct_1_num)
  int32 val : 8 (always 1)
  int32 tag (not a hash)

int32 unknown (same value as struct_1_num)
int32 unknown

int32 offset_num

int32 offsets[ offset_num ] (in reverse order)

/* unknown data here */

file data:
  int32 size
  byte data[] (zsize looked up from unknown data )

  if size != -1 
    data is compressed with zlib


```
## Post #8
- Username: WRS
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-11-25T23:26:42+00:00
- Post Title: Carmageddon 1 IOS (.WAD Extracton Help)

Archive, texture, and model support will be in the next Noesis. I should have that build up sometime tonight.


WRS: The section you don't have figured out is laid out as:

```
{
	int				nameOfs;
	int				dataSize;
	int				entryIdx:24;
	int				entryType:8;
	int				resv;
} wadFileEntry_t;
typedef struct wadDirEntry_s
{
	int				nameOfs;
	int				numFiles;
	int				numSubDirs:24;
	int				entryType:8;
	int				resv;
} wadDirEntry_t;
```
If entryType is 0, it's a wadDirEntry_t, otherwise it's a wadFileEntry_t. You then run through recursively appending to your path with each nested directory entry.
