## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-06-18T06:18:24+00:00
- Post Title: Microprose: X-COM 1, 2 .CAT files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-18T09:29:13+00:00
- Post Title: Microprose: X-COM 1, 2 .CAT files

I'm too lazy to read those info so I used my way:

```

get FILES long
math FILES /= 8
goto 0
for i = 0 < FILES
    get OFFSET long
    get SIZE long

    savepos TMP_OFF
    goto OFFSET
    get NAMESZ byte
    set NAME string ""
    if NAMESZ > 0
        if NAMESZ < 40
            getdstring TMP NAMESZ
            savepos OFFSET
            math SIZE -= 1
            math SIZE -= NAMESZ
            if NAMESZ > 5
                get NAME basename
                string NAME += /
                string NAME += i
                string NAME += _
                string NAME += TMP
            endif
        endif
    endif
    goto TMP_OFF

    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-06-18T10:09:15+00:00
- Post Title: Microprose: X-COM 1, 2 .CAT files

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Borg Number One
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jun 06, 2004 10:33 pm
- Post datetime: 2010-07-02T11:21:37+00:00
- Post Title: Microprose: X-COM 1, 2 .CAT files

Hi,

referring to unpacking / extracting Microprose .cat files, here are some further tools and information:

1.)
cat_coder.tar.gz
Packing and unpacking programs for early Microprose .CAT archives as found in the first two X-COM games (UFO and TFTD), with format description.
[http://sqentropy.dyndns.org/Holding/](http://sqentropy.dyndns.org/Holding/)
[http://sqentropy.dyndns.org/Holding/Sou ... der.tar.gz](http://sqentropy.dyndns.org/Holding/Source/cat_coder.tar.gz)

2.)
[http://www.neologue.co.uk/mwuki?title=U ... .cat+files](http://www.neologue.co.uk/mwuki?title=Unpicking+XCom+.cat+files)
[http://www.neologue.co.uk/mwuki?title=X ... +extractor](http://www.neologue.co.uk/mwuki?title=XCom+catfile+extractor)

3.)
[http://www.simwarrior.com/gunship/gsdev.html](http://www.simwarrior.com/gunship/gsdev.html)
[http://www.simwarrior.com/gunship/utilities/xtrcat2.zip](http://www.simwarrior.com/gunship/utilities/xtrcat2.zip)

4.)
SFP1/WOE/WOV CAT File Extract Utility
A great utility that extracts game files from the .CAT files. A must for skinners and FM tweakers.
[http://combatace.com/index.php?automodu ... owfile=343](http://combatace.com/index.php?automodule=downloads&showfile=343)

4.)
[http://www.tt-forums.net/viewtopic.php?f=31&t=31293](http://www.tt-forums.net/viewtopic.php?f=31&t=31293)
[http://www.tt-forums.net/download/file.php?id=68636](http://www.tt-forums.net/download/file.php?id=68636)

```
 *  gmext.c                                                               *
 *                                                                        *
 *  gm.cat MIDI sequence extractor                                        *
 *                                                                        */

#include <stdint.h>
#include <stdio.h>
#include <stdlib.h>

#define RUNNING_MODE

inline long read_delta (const unsigned char* *p)
{
long delta = **p & 0x7F;
while ( *(*p)++ & 0x80 )
    {
    delta <<= 7;
    delta += **p & 0x7F;
    }
return delta;
}

void write_delta (FILE *f, long delta)
{
unsigned char c [4] = { 0, 0x80, 0x80, 0x80 };
int i = 0;
while ( delta > 0x7F )
    {
    c[i++] |= delta & 0x7F;
    delta >>= 7;
    }
c[i++] |= delta;
while ( i )
    fwrite (c + --i, 1, 1, f);
}

struct seq
    {
    uint32_t size;
    unsigned char *data;
    };

unsigned char volume [0x80] = {
  100,100,100,100,100, 90, 100,100,100,100,100, 90, 100,100,100,100,100,100,
  85, 100,100,100,100,100,100,100,100,100, 90,90, 110, 80, 100,100,100,
  90, 70, 100,100,100,100,100,100,100,100,100,100,100,100,100, 90,
  100,100,100,100,100,100, 120, 100,100,100, 120, 100, 127, 100,100, 90,
  100,100,100,100,100,100, 95,
  100,100,100,100,100,100,100,100,100,100,100,100,100, 115,
  100,100,100,100,100,100,100,100,100,100,
  100,100,100,100,100,100,100,100,100,100,
  100,100,100,100,100,100,100,100,100,100,
  100,100,100,100,100,100,100,100,100,100
  };

long tseq (FILE *f, unsigned nsubs, const struct seq *subs, char channel,
    const struct seq *seq, unsigned char *patch, long delta0)
{
long delta = delta0;
unsigned char output, command = 0x80;
unsigned char data1, data2;
const unsigned char *data = seq->data;
const unsigned char *dataend = seq->data + seq->size;
while ( data < dataend )
    {
    delta += read_delta (&data);
    if ( *data & 0x80 )  command = *data++;
    switch ( command )
        {
        case 0xFF:
        case 0xFD:  return delta;
        case 0xFE:  /* insert subsequence */
            if ( *data >= nsubs )
                {
                puts ("invalid subsequence");
                return 0;
                }
            delta = tseq (f, nsubs, subs, channel, &subs[*data++],
                patch, delta);
            continue;
        }
    command &= 0xF0;
    data1 = *data++;
    switch ( command )
        {
        case 0x80:  case 0x90:
            data2 = *data++;
            write_delta (f, delta);
            delta = 0;
#ifdef RUNNING_MODE
            if ( output != (command|channel) )
#endif
                {
                output = command | channel;
                fwrite (&output, 1, 1, f);
                }
            fwrite (&data1, 1, 1, f);
            if ( data2 )
                data2 = (unsigned) data2 *
                    (channel==9 ? 80 : volume[*patch]) >> 7;
            fwrite (&data2, 1, 1, f);
            break;
        case 0xC0:
            if ( data1 == 0x7E )  return delta;
            *patch = data1;
            write_delta (f, delta);
            delta = 0;
#ifdef RUNNING_MODE
            if ( output != (0xC0|channel) )
#endif
                {
                output = 0xC0 | channel;
                fwrite (&output, 1, 1, f);
                }
            if ( (data1==0x57) || (data1==0x3F) )  data1 = 0x3E;
            fwrite (&data1, 1, 1, f);
            break;
        case 0xB0:
            data2 = *data++;
            if ( (data1==0x7E) || (!data1 && !data2) )  continue;
            write_delta (f, delta);
            delta = 0;
            if ( !data1 )
                {
                uint32_t x;
                char xdata [3];
                output = 0xFF;
                fwrite (&output, 1, 1, f);
                data1 = 0x51;
                fwrite (&data1, 1, 1, f);
                data1 = 3;
                fwrite (&data1, 1, 1, f);
                x = (740*163840) * data2;
                xdata[0] = x>>16;
                xdata[1] = x>>8;
                xdata[2] = x;
                fwrite (&xdata, 1, 3, f);
                }
#ifdef RUNNING_MODE
            if ( output != (0xB0|channel) )
#endif
                {
                output = 0xB0 | channel;
                fwrite (&output, 1, 1, f);
                }
            fwrite (&data1, 1, 1, f);
            if ( data1 == 0x5B )  data2 = 0x1E;
            fwrite (&data2, 1, 1, f);
            break;
        case 0xE0:
            data2 = *data++;
            write_delta (f, delta);
            delta = 0;
#ifdef RUNNING_MODE
            if ( output != (0xE0|channel) )
#endif
                {
                output = 0xE0 | channel;
                fwrite (&output, 1, 1, f);
                }
            fwrite (&data1, 1, 1, f);
            fwrite (&data2, 1, 1, f);
            break;
        }
    }
return 0;
}

void midi_header (FILE *f, unsigned ntracks)
{
static const char header [10] = { 'M','T','h','d',0,0,0,6,0,1 };
static const char delta [2] = { 0,24 };
char ntr [2];
fwrite (header, 1, 10, f);
ntr[0] = ntracks>>8;
ntr[1] = ntracks;
fwrite (ntr, 1, 2, f);
fwrite (delta, 1, 2, f);
}

static const char midi_track_start [8] = { 'M','T','r','k',0,0,0,0 };
static const char midi_track_end [4] = { 0, 0xFF, 0x2F, 0 };

void midi_track0 (FILE *f, unsigned tempo, unsigned namelen,
    const char *name)
{
static const char set_tempo [4] = { 0, 0xFF, 0x51, 3 };
static const char text_event [3] = { 0, 0xFF, 1 };
char data [4];
unsigned tsize;
fwrite (midi_track_start, 1, 4, f);
tsize = namelen + 15;
data[0] = tsize>>24;
data[1] = tsize>>16;
data[2] = tsize>>8;
data[3] = tsize;
fwrite (data, 1, 4, f);
fwrite (set_tempo, 1, 4, f);
tempo = (370*163840) / tempo;
data[0] = tempo>>16;
data[1] = tempo>>8;
data[2] = tempo;
fwrite (data, 1, 3, f);
fwrite (text_event, 1, 3, f);
fwrite (&namelen, 1, 1, f);
fwrite (name, 1, namelen, f);
fwrite (midi_track_end, 1, 4, f);
}

void midi_track (FILE *f, unsigned nsubs, const struct seq *subs,
    char channel, const struct seq *seq)
{
static char midi_track_begin [10] =
    { 0, 0xB0, 0x78, 0, 0, 0x79, 0, 0, 0x7B, 0 };
long foffset, length;
char data [4];
unsigned char patch = 0;
fwrite (midi_track_start, 1, 8, f);
foffset = ftell (f);
midi_track_begin[1] = 0xB0 | channel;
fwrite (midi_track_begin, 1, 10, f);
write_delta (f, tseq (f, nsubs, subs, channel, seq, &patch, 0));
fwrite (midi_track_end+1, 1, 3, f);
length = ftell(f) - foffset;
fseek (f, foffset-4, SEEK_SET);
data[0] = length>>24;
data[1] = length>>16;
data[2] = length>>8;
data[3] = length;
fwrite (data, 1, 4, f);
fseek (f, 0, SEEK_END);
}

int gmext_song (FILE *f, uint32_t n)
{
uint32_t offset, length;
unsigned char namelength, tempo, nsubs, ntracks;
char name [256];
struct seq subs [256];
char channels [256];
struct seq tracks [256];
unsigned namelen, i;
char out [256];
FILE *fout;
/* read in offset and length of song */
if ( fseek (f, 8*n, SEEK_SET) == -1 )     return -1;
if ( fread (&offset, 4, 1, f) != 1 )      return -1;
if ( fread (&length, 4, 1, f) != 1 )      return -1;
if ( fseek (f, offset, SEEK_SET) == -1 )  return -1;
/* read in song name */
if ( fread (&namelength, 1, 1, f) != 1 )  return -1;
if ( fread (name, 1, namelength, f) != namelength )  return -1;
if ( namelength && !name[namelength-1] )
    namelen = namelength-1;
else name[namelen=namelength] = 0;
printf ("Extracting song #%u %s\n", n, name);
/* read in tempo */
if ( fread (&tempo, 1, 1, f) != 1 )  return -1;
/* read in subs */
if ( fread (&nsubs, 1, 1, f) != 1 )  return -1;
for (i=0; i<nsubs; i++)
    {
    /* do not bother free()ing memory on failure, */
    /* since we are going to abort                */
    if ( fread (&subs[i].size, 4, 1, f) != 1 )  return -1;
    if ( subs[i].size < 4 )
        {
        puts ("invalid data length");
        return -2;
        }
    subs[i].size -= 4;
    subs[i].data = malloc (subs[i].size);
    if ( !subs[i].data )
        {
        perror (0);
        return -2;
        }
    if ( fread (subs[i].data, 1, subs[i].size, f) != subs[i].size )
        return -1;
    }
/* read in tracks */
if ( fread (&ntracks, 1, 1, f) != 1 )  return -1;
for (i=0; i<ntracks; i++)
    {
    if ( fread (&channels[i], 1, 1, f) != 1 )     return -1;
    if ( fread (&tracks[i].size, 4, 1, f) != 1 )  return -1;
    if ( tracks[i].size < 4 )
        {
        puts ("invalid data length");
        return -2;
        }
    tracks[i].size -= 4;
    tracks[i].data = malloc (tracks[i].size);
    if ( !tracks[i].data )
        {
        perror (0);
        return -2;
        }
    if ( fread (tracks[i].data, 1, tracks[i].size, f) != tracks[i].size )
        return -1;
    }
/* check current offset */
if ( ftell(f) != (offset+length+namelength+1) )
    {
    puts ("offset mismatch");
    return -2;
    }
/* write output file */
snprintf (out, sizeof(out), "%02u.mid", n);
printf ("Output file: %s\n", out);
fout = fopen (out, "wb");
if ( !fout )
    {
    perror (out);
    return -2;
    }
midi_header (fout, ntracks+1);
midi_track0 (fout, tempo, namelen, name);
for (i=0; i<ntracks; i++)
    midi_track (fout, nsubs, subs, channels[i], &tracks[i]);
/* clean up */
fclose (fout);
for (i=0; i<nsubs; i++)    free (subs[i].data);
for (i=0; i<ntracks; i++)  free (tracks[i].data);
return 0;
}

int gmext (const char *filename)
{
FILE *f;
uint32_t nsongs, i;
printf ("Reading file %s\n", filename);
f = fopen (filename, "rb");
if ( !f )
    {
    perror (filename);
    return 1;
    }
/* compute the number of songs, knowing that the */
/* first song starts right after the index table */
if ( fread (&nsongs, 4, 1, f) != 1 )    /* file format is little-endian */
    {
    perror (filename);
    return 1;
    }
nsongs /= 8;
printf ("There are %u songs in %s\n", nsongs, filename);
/* read songs one by one */
for (i=0; i<nsongs; i++)
    switch ( gmext_song (f, i) )
        {
        case -1:
            perror (filename);
        case -2:
            fclose (f);
            return 1;
        }
fclose (f);
return 0;
}

int main (int nargs, char* *args)
{
return gmext (nargs>1 ? args[1] : "gm.cat");
}

```


5.)
[http://www.simwarrior.com/gunship/modwork.html](http://www.simwarrior.com/gunship/modwork.html)
--> look for: ".cat"

6.)
[http://users.lia.net/chris/ttdlx/](http://users.lia.net/chris/ttdlx/) (outdated/offline) (maybe try: web.archive.org)
[http://www.ttdpatch.net/chris_becke_ttdlx.html](http://www.ttdpatch.net/chris_becke_ttdlx.html) (current)
tttools.zip (5Kb) is a small archive containing some interesting things.
* savetool.exe Is a small tool that lets you export and inport savegames from an easy to edit "big" format back to proper save games. It works with both V1 and V2 savegames.
* decat.exe will extract all the files contained within any .CAT file. Usefull for extracting the .wav's in sample.cat, and the MIDI .PAT files from adlib.cat, roland.cat and gm.cat.
* ttycoon.h A C++ header file containing definitions of most the structs I have found in the savegame file, and in Transport Tycoon itself.

7.)
[http://combatace.com/files/file/10458-c ... g-utility/](http://combatace.com/files/file/10458-catpack-archiving-utility/)
CatPack Archiving Utility by usafmtl
CatPack - Archiving utility for Third-Wire CAT format, GB 27-12-2009.

V1.12, Freeware, Use at your own risk, files limit is set at 8000.
Packs all files in current folder to CatPack.cat except CatPack.exe/CatPack.cat.
Unpacks any cat file you drop on the icon to a folder with the archive's name.

You can press Ctrl+Break to interrupt and close the program, but it will leave
files unfinished when doing so.

UPDATE:
CatPack V1.1 will extract contents of the new Strike Fighters 2 Cat archives.
The Display will tell the Cat version to be 2, instead of 1.
Subfolder information contained in version 2 archives will be restored properly.
The unicode filenames in the version 2 archives are converted back to ASCII,
therefor actual unicode-only characters in filenames will not be restored.
Catpack does not yet support creating a version 2 Cat archive. Maybe later.

CatPack V1.11 works properly when Cat files are in folders that have their
'archive' flag set. This seems to be the case with the SF2 objects folder.

CatPack V1.12 has some additional features when extracting a Cat archive:
First it automatically creates an index file of the Cat file.
Second and it allows one to optionally pass a wildcard string, only files matching
this wildcard string will be extracted from the archive. For example "mig" will
only extract files that have "mig" in their name or extension.

Credits:
Gerwin - Author
Kreelin and Paolo - Beta testing of V1.1.
Allegro game programming library - File and Unicode routines. 


Some years ago I was in contact with John Broomhall (the musician of Transport Tycoon) and I asked him about the technical details in adlib.cat, gm.cat, roland.cat.
He could not tell me much, because he was only responsible for the music and not for the conversion to .cat container files.
He just has got the original Transport Tycoon and music cubasis files.
## Post #5
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2011-09-04T16:55:00+00:00
- Post Title: Microprose: X-COM 1, 2 .CAT files

I tried use several utils for unpacking .cat files: quickbms script by aluigi, decat.exe, xtrcat, cat unpacker, created from sources and gmext from source. Other utils dont work with .cat files from X-com games.

All utils, except xtrcat and gmext, has unpack data from .cat files(xtrcat need filenames or list, and gmext cannot be built in MVS(used 2010 version)).

The general problem of all unpackers - unpacked data cannot be using for decoding/rebuilding into MIDI/tracker format.

[Here](http://narod.ru/disk/24011170001/Xcom_Cat_Unpackers.rar.html) - all utils(except quickbms script and gmext.c) what I tried use for unpacking .cat files. I think, here need auto-converter/rebuilder(or decoder?) to a MIDI(better - in particular formats for saving original Roland and ADLIB OPL commands, if its possible).
## Post #6
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-06-06T16:03:50+00:00
- Post Title: Microprose: X-COM 1, 2 .CAT files

If anyone can help, PM for getting files for tests and research.
