## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-23T22:24:18+00:00
- Post Title: Notes on PathMusic data in RA3

This thread is a place for me to dump all my notes on the PathMusic data and formats as seen in Red Alert 3 and for anyone else who wants to help reverse engineer this stuff to contribute their own findings.

The following link contains the data files relavent to the PathMusic data (at least the ones I know are relavent) extracted from the game data files (these files aren't stored loose in the game archive files but are instead "compiled" into the game data files along with all the other game data via the BinaryAssetBuilder tool which is included in the RA3 Mod SDK. I extracted these files from the "compiled" data)
[https://mega.nz/#!igsVUQbY!tEZuxaoR1OIW ... 0DXvksnB-w](https://mega.nz/#!igsVUQbY!tEZuxaoR1OIWYP2sA5JarYl0OkfjZNsT50DXvksnB-w)

track.mus and track-mem.mus come from PathMusicTrack data and contain the actual audio.
pc.mpf comes from the PathMusicMap data and contains data to (somehow) map PathMusicEvents to actual audio pieces.
ra3music.h contains some data extracted from the PathMusicEvents in the game that maps the event names to special values used later in the PathMusicMap data.

The next post I make will contain details of all that is known so far about the format of the PathMusicMap data (the .mpf file) and the PathMusicTrack data (the .mus file)
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-24T11:45:08+00:00
- Post Title: Notes on PathMusic data in RA3

These notes apply to RA3, the formats may have changed in RA3: Uprising and C&C4.
The PathMusicTrack data (the .mus files) contains a header as follows:

struct PathMusicTrackHeader {
    unsigned int magic; //magic number/hash referenced inside the PathMusicMap file
    unsigned int count; //how many audio pieces are in this file
    unsigned int unk1;
    unsigned int unk2;
    unsigned int unk3;
    unsigned int unk4;
    unsigned int unk5;
    unsigned int unk6;
    unsigned int unk7;
    unsigned int unk8;
};

Each music segment has a header as follows:
struct PathMusicTrackSegmentHeader {
    unsigned int magic; //some sort of magic number/hash for the music segment
    unsigned int index;
    unsigned int HeaderOffset; //this gets multiplied by 0x10 to find the offset within the .mus data for the header of this music segment
    unsigned int DataOffset; //this gets multiplied by 0x80 to find the offset within the .mus data for the compressed audio data of this music segment
    unsigned int HeaderSize;
    unsigned int DataSize;
    unsigned int unk;
}

Coming up next is some notes on PathMusicMap data (the .mpf file)
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-25T10:52:48+00:00
- Post Title: Notes on PathMusic data in RA3

For reference, a "track" refers to a specific PathMusicTrack data piece (i.e. a .mus file) and a "track segment" refers to a piece of audio inside that track file.

Here is what is known so far about the MPF files.
They start with this header: (all the fields named "offset" are offsets within the file to other data tables)
struct mpfheader
{
  unsigned int magic; //always 0x50464478
  unsigned char version1; //always 5
  unsigned char version2; //always 3
  short field_6;
  int field_8;
  char field_C;
  unsigned char trackcount; //count of how many .mus files this .mpf file references
  char field_E;
  unsigned char pathmusiceventcount; //count of how many events there are in the "events table"
  short field_10;
  short field_12;
  unsigned int offsets1offset; 
  unsigned int unk1offset;
  unsigned int eventdataoffsetsoffset;
  unsigned int eventdataoffset;
  unsigned int unk2offset;
  unsigned int unk3offset;
  unsigned int trackdataoffsetsoffset;
  unsigned int trackdataoffset;
  unsigned int tracksegmentsdataoffset;
  unsigned int mpfsize; //matches the size of the .mpf file
  int field_3C;
  int field_40;
  int field_44;
};

The data table pointed to by trackdataoffsetsoffset is an array of unsigned ints. These ints get multiplied by 4 and used as an offset into the file to locate the data structure for the track entry (i.e. the .mus file/PathMusicTrack data). This offset will be somewhere inside the table pointed to by the trackdataoffset pointer.

The data table pointed to by trackdataoffset is an array of this structure:
struct trackdatastr
{
  unsigned int firstindex; //this is used to map where in the track segments table the first track segment from this .mus file is to be found.
  int unk1;
  unsigned int magic; //this matches with the magic number in the PathMusicTrackHeader structure in the .mus file.
  unsigned int endoffset; //this is the offset within the .mus file of the byte immediately after all the audio headers (the ones that define the compression type, channel count, sample rate and sample count).
  int unk2;
};

What is pointed to by the tracksegmentsdataoffset value is unknown but it appears to be entries 8 bytes in size with one for each track segment (although I may be wrong about that)

The eventdataoffsetsoffset value points to a table of unsigned shorts. Its size is the same as the pathmusiceventcount value in the header. These offsets are multiplied by 4 and used as an offset into the file to locate the data matching this event. This data will be somewhere inside the table pointed to by the eventdataoffset pointer.

The structure pointed to by the offsets in the eventdataoffsets table are unknown so far although it looks like they contain a flags value at offset 0x10 and at offset 0xC is a "magic" value that matches the #defines in ra3music.h except that the upper byte is masked off (so if the data being loaded is for the MenuTrack event, the hash value is 0x01B9D554 and the "magic" field in this structure will be ??B8D554 with the ?? being some other value that we dont know the purpose of yet)

The data pointed to by offsets1offset is clearly offsets further into the file but what they point to (and what the values are multiplied by) is not yet know.
The data pointed to by unk1offset, unk2offset and unk3offset is totally unknown.

That is everything that is known so far about the .mpf (PathMusicMap) data in Red Alert 3.

Any help to figure out more of the file format would be most appreciated.
## Post #4
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2020-06-03T10:02:08+00:00
- Post Title: Notes on PathMusic data in RA3

I have recently discovered some more information about this format.
The .mpf file starts with a header
struct PATHFINDHEADER
{
  int id;
  unsigned char majorRev; //5 in the files/code I am working with
  unsigned char minorRev; //3 in the files/code I am working with
  unsigned char release;
  unsigned char prerelease;
  unsigned short saveIncrement;
  unsigned short generateID;
  unsigned char projectID;
  unsigned char numtracks;
  unsigned char numsections;
  unsigned char numevents;
  unsigned char numrouters;
  unsigned char numnamedvars;
  unsigned short numnodes;
  unsigned int nodeoffsets; //offset within the file of an array of short
  unsigned int nodedata; //offset within the file of an array of PATHFINDNODE structures
  unsigned int eventoffsets; //offset within the file of an array of short
  unsigned int eventdata; //offset within the file of an array of PATHEVENT structures
  unsigned int namedvars; //offset within the file of an array of PATHNAMEDVAR structures
  unsigned int noderouters; //offset within the file of an array of int
  unsigned int trackoffsets; //offset within the file of an array of int
  unsigned int trackinfos; //offset within the file of an array of PATHTRACKINFO structures
  unsigned int sampleoffsets; //offset within the file of an array of PATHFINDSAMPLE structures
  unsigned int mapfilelen;
  unsigned int v40reserve;
};

More data structures:
struct PATHNODEBEATS
{
  unsigned int unk : 30;
  unsigned int playbeats : 1;
  unsigned int forcesynch : 1;
};
struct PATHNODEEVENT
{
  unsigned int unk : 8;
  unsigned int eventID : 24;
};
struct PATHNODECHANNEL
{
  unsigned int : 4;
  unsigned int channelset : 4;
  unsigned int eventID : 24;
};
union PATHNODEEXTRA
{
  PATHNODEBEATS beat;
  PATHNODEEVENT sendevent;
  PATHNODECHANNEL channelbranch;
};
struct PATHFINDNODE
{
  int repeat : 5;
  unsigned __int32 sectionID : 6;
  unsigned __int32 trackID : 5;
  int index : 16;
  unsigned int bars : 8;
  unsigned int beats : 4;
  unsigned int controller : 3;
  unsigned int numbranches : 5;
  unsigned int routerID : 12;
  unsigned int unused : 1;
  unsigned int channelbranching : 1;
  unsigned int synch : 2;
  unsigned int notes : 4;
  unsigned int synchoffset : 4;
  unsigned int synchevery : 4;
  unsigned int partID : 16;
  PATHNODEEXTRA extra;
};
struct PATHEVENT
{
  unsigned int queued;
  unsigned int expiry;
  unsigned int lastact;
  unsigned int numactions : 8;
  unsigned int eventID : 24;
  int unused : 11;
  int project : 3;
  unsigned int beingFiltered : 1;
  unsigned int bumplower : 1;
  int priority : 4;
  unsigned int voices : 4;
  unsigned int currentaction : 8;
};
struct PATHNAMEDVAR
{
  char name[16];
  int value;
};
struct PATHTRACKINFO
{
  unsigned int startingsample;
  unsigned short numsubbanks;
  unsigned short purgemode;
  unsigned int muschecksum;
  unsigned int maxaram;
  unsigned int maxmram;
};
struct PATHFINDSAMPLE
{
  unsigned int offset;
  unsigned int duration;
};

The MUS files start with this header
struct PATHMUSHEADER
{
  int checksum;
  int numsamples;
  char reserved[32];
};

and the individual music segments start with this header
struct __cppobj PATHNODEOFFSETS
{
  unsigned int nodechecksum;
  unsigned __int16 index;
  unsigned __int16 subindex;
  unsigned int snroffset;
  unsigned int snsoffset;
  unsigned int snrbytes;
  unsigned int snsbytes;
  void *gstream;
};

More to come later most likely.
## Post #5
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-04-13T08:05:29+00:00
- Post Title: Notes on PathMusic data in RA3

I have done a deeper dive into PathMusic in RA3 and this forum post:
[https://ppmforums.com/post-602390/all-t ... a3/#602390](https://ppmforums.com/post-602390/all-the-known-information-about-pathmusic-in-ra3/#602390)
contains all the known information.

Its likely the PathMusic data in other games (Need For Speed Underground for example) is going to have the same format.
