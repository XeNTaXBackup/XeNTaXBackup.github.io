## Post #1
- Username: JeffT
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 16, 2009 4:15 pm
- Post datetime: 2009-09-29T16:01:44+00:00
- Post Title: Risen .PAK

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-09-29T23:17:40+00:00
- Post Title: Risen .PAK

This the 360 or PC version?
## Post #3
- Username: JeffT
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 16, 2009 4:15 pm
- Post datetime: 2009-09-30T18:44:51+00:00
- Post Title: Risen .PAK

PC
## Post #4
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-10-01T14:11:17+00:00
- Post Title: Risen .PAK

File:
Header[48];
RawData [variable size];
FileInfoHdr[4];
FileInfos[variable size];

Header:
int32 version; // = 1
char [4] string; // = "G3V0"
int64 unknown1; // = 0
int64 unknown2; // = 1
int64 address; // address (not offset!) where the data starts = 0x30
int64 offset; // offset from current position (0x20) to FileInfoHdr
int64 filesize; // size of the file
NOTE: all the above int64s may actually be int32s - but the more significant bytes are all zero, so it's hard to tell.

FileInfoHdr:
int32 unknown; // For the first glance it seemed like the number of FileInfos, but some files have a different number here

FileInfo:
TBD
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-01T14:42:29+00:00
- Post Title: Risen .PAK

the following is a quickbms script made on the fly:

*edit* watch the next posts

tell me if it works also with the other files
## Post #6
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-10-01T14:56:55+00:00
- Post Title: Risen .PAK

> Reply from Bugtest
>
> the following is a quickbms script made on the fly:
Code: Select allget DUMMY long
idstring G3V0
goto 0x20
get INFO_OFF long
get DUMMY long
get MAX_OFF long

goto INFO_OFF
getdstring DUMMY 36

for
    savepos INFO_OFF
    if INFO_OFF >= MAX_OFF
        cleanexit
    endif

    get DUMMY long
    get NAMESZ long
    math NAMESZ += 1
    getdstring NAME NAMESZ
    get OFFSET long
    getdstring DUMMY 40
    get ZSIZE long
    get SIZE long

    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
nexttell me if it works also with the other files

testet with german.pak, still not work 
[](http://pic-share.us/viewer.php?picture=bms_1712979480.jpg&action=full)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-01T15:02:49+00:00
- Post Title: Risen .PAK

nice image for a blind person...
how much is big this particular pak file?
## Post #8
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-10-01T15:17:34+00:00
- Post Title: Risen .PAK

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-01T18:34:27+00:00
- Post Title: Risen .PAK

ok done, practically the problem was in the name of the folders.
note that the folders will be not extracted so the files are extracted all in the output folder without subdirectories.

*edit* watch my next posts
## Post #10
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-10-02T18:37:19+00:00
- Post Title: Risen .PAK

Seems very similar to the Gothic 3 format.
Get g3pak from here:
[http://www.bendlins.de/nico/gothic3/](http://www.bendlins.de/nico/gothic3/)
and read the format description there.
The source (Delphi) is available for that tool at the same link - anyone willing to update it?
Thank you.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-09T22:42:34+00:00
- Post Title: Risen .PAK

I have given a look at that documentation but except for the header all the rest is completely different.
anyway the following bms script extracts everything included the subfolders:
[http://aluigi.org/papers/bms/risen.bms](http://aluigi.org/papers/bms/risen.bms)
## Post #12
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-10-10T09:57:07+00:00
- Post Title: Risen .PAK

[http://www.bendlins.de/nico/risen/](http://www.bendlins.de/nico/risen/)

Similar to the authors G3Pak utility, different tools to unpack files and then stuff inside them like the string table (text and stuff) file plus converting textures from ximg to dds (or tga) and sound files. 
(Game doesn't read unpacked data however but the hotfix patch works similar to Gothic 3 with .pak for the main archive followed by .p00 to p99 or something for addon data, of course it's a bit cumbersome and there's no re-packer yet but it gives a nice overview of the game engine and files although just like Gothic 3 it isn't easy to modify.)
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-11-14T07:19:58+00:00
- Post Title: Risen .PAK

> Reply from jbeckman
>
> http://www.bendlins.de/nico/risen/

Similar to the authors G3Pak utility, different tools to unpack files and then stuff inside them like the string table (text and stuff) file plus converting textures from ximg to dds (or tga) and sound files. 
(Game doesn't read unpacked data however but the hotfix patch works similar to Gothic 3 with .pak for the main archive followed by .p00 to p99 or something for addon data, of course it's a bit cumbersome and there's no re-packer yet but it gives a nice overview of the game engine and files although just like Gothic 3 it isn't easy to modify.)

Hi,

Do you know how can i contact author please ?
