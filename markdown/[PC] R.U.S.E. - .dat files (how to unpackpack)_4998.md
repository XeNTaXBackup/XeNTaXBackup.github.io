## Post #1
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-09-09T14:27:54+00:00
- Post Title: [PC] R.U.S.E. - .dat files (how to unpack/pack?)

Hello!
Does anyone know how to unpack and then pack the .dat files in the PC version of the game R.U.S.E. ?

Here are examples: 
[http://www.multiupload.com/3EQRZ1KL0T](http://www.multiupload.com/3EQRZ1KL0T)
[http://www.multiupload.com/0SCBYVYNSZ](http://www.multiupload.com/0SCBYVYNSZ)
## Post #2
- Username: thesnow
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2010 1:52 pm
- Post datetime: 2010-09-09T16:13:09+00:00
- Post Title: [PC] R.U.S.E. - .dat files (how to unpack/pack?)

may be like act of war:

+------------------+
| Act Of War *.dat |
+------------------+

// NOTES:
// The files are stored in a special way so as to reduce the amount of space
// needed to store the filenames. It does this by grouping the files together
// that share a common first-part of their name, and then building up the actual
// filename of each file by joinging a whole lot of group names together.
//
// For example, if we have 2 files called "sound11.wav" and "sound22.wav", you
// can see that they both share 5 common letters at the beginning of the filename
// (ie "sound"). This archive would have a group with the name "sound" and each
// of the 2 files would be saved with names "11.wav" and "22.wav" within that
// group, thus saving space. This space saving is only really benificial for
// storing directorie names though, as there is a lot of overhead.
//
// Groups can be nested inside each other, so there is no boundary as to the
// number of groups that can exist in a nested way.
//
// Also, filenames can be reused by using a negative number for the Group/File ID.
// In this case, take the offset just before the negative Group/File ID, subtract
// the negative number, and it will point to the filename that will be reused.

4 - Header (edat)
4 - Length of the header after the 10 nulls (18)
4 - Unknown
10 - null
2 - Unknown (1)
1 - null
4 - Directory Offset
4 - Directory Length
7 - null
X - File Data
X - Directory

// go to dirOffset

  // for each group
    4 - Group/File Indicator (0=file, #=length of this group entry, -#=offset to a previous file entry)

    if (group){
      4 - Length of this group, including the file entries (ie relative offset to next group) (or null)
      X - Group name (null)
      0-1 - null padding to a multiple of 2 bytes (ie only exists if groupnameLength+1 is odd)
      }

    else if (file){
      4 - Last File Indicator (0=last file in this group, #=length of this file entry)
      4 - File Offset
      4 - File Length
      1 - Unknown (0) // something to do with the Filename position?
      X - Filename (null)
      0-1 - null padding to a multiple of 2 bytes (ie only exists if filenameLength+2 is odd)
      }

    else if (previous offset (negative number)){
      4 - Last File Indicator (0=last file in this group, #=length of this file entry)
      4 - File Offset
      4 - File Length
      2 - null
      }
## Post #3
- Username: thesnow
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2010 1:52 pm
- Post datetime: 2010-09-09T16:17:58+00:00
- Post Title: [PC] R.U.S.E. - .dat files (how to unpack/pack?)

u can see: [http://www.eugensystems.com/](http://www.eugensystems.com/)
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-09-10T00:28:32+00:00
- Post Title: [PC] R.U.S.E. - .dat files (how to unpack/pack?)

Ubisoft Entertainment has updated the R.U.S.E. forums with word that there won't be any mod or map tools for the game.
Info from:
[http://www.fragland.net/news/RUSE-wont- ... ols/22104/](http://www.fragland.net/news/RUSE-wont-get-mod-or-map-tools/22104/)
I tried with offzip and the extraction works great, but all the data are massive and strange, look the graphics are DDS but headerless no idea what it's the audio maybe ogg or some dpcm? the movies are WMV formats

A extractor/bms will be nice to see what's inside..
## Post #5
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2010-10-20T16:02:06+00:00
- Post Title: [PC] R.U.S.E. - .dat files (how to unpack/pack?)

what about ruse dat packer/unpacker?
