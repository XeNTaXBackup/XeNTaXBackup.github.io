## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-20T21:52:49+00:00
- Post Title: Act To War DAT file..

Hello ....
Help extract DAT files ...
Example archive i am send EMail Watto and Mr.Mouse  
Thx
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-22T05:03:06+00:00
- Post Title: Act To War DAT file..

I didn't get the email 

I do have a demo of this game though, and here is the structure...

```
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

  4 - Relative offset to the first filename group entry (10)
  6 - null

  // for each group
    4 - Group/File Indicator (0=file, #=length of this group entry)
  
    if (group){
      4 - Length of this group and its entries (ie relative offset to next group)
      X - Group name (null)
      0-1 - null padding to a multiple of 2 bytes (ie only exists if groupnameLength+1 is odd)
      }
  
    else if (file){
      4 - Last File Indicator (0=last file in this group, #=length of this file entry
      4 - File Offset
      4 - File Length
      1 - Unknown (0) // something to do with the Filename position?
      X - Filename (null)
      0-1 - null padding to a multiple of 2 bytes (ie only exists if filenameLength+2 is odd)
      }
```


It is a little complicated so I have been trying to avoid making a plugin or script for it. It is on my todo list though, so hopefully something soon - I have a bunch of other games I need to write plugins for first though.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-22T08:29:43+00:00
- Post Title: Act To War DAT file..

As it is a pity that you have not received mail..  Watto to me it seems archives from Demo to the version do not differ from full.. If you will write a plug-in I shall be very glad.... Game weighs 5,23 GB  ... Archives->
datac.dat - 46MB
datag.dat - 1.6GB
datag2.dat - 690MB
dataglad.dat - 46MB
dataglad_DicoEtranger.dat - 4MB
datai.dat - 332MB
datal.dat - 2MB
datamaps.dat - 580MB
datar.dat - 65MB
datas_en.dat - 86MB
datav.dat - 1.4GB
datav_en.dat - 53MB
datavinterface.dat - 248MB
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-09T21:22:11+00:00
- Post Title: Act To War DAT file..

What program can eat to pull out all from archives?
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-09T23:44:52+00:00
- Post Title: Act To War DAT file..

Hi mate,

I did end up writing a Game Extractor plugin for this game - can't remember if I sent it to you or not (i did send it to someone). Anyway, if I didn't, you can get the plugin with the Full Version of Game Extractor. I still need to put some more work into the plugin though, because I know some of the filenames are not right 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-10T22:05:40+00:00
- Post Title: Act To War DAT file..

Hi Watto. where download full version Game Extractor or how to receive it? I even have passed all game... To play it be not become interesting
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-11T02:20:11+00:00
- Post Title: Act To War DAT file..

[http://www.watto.org/extract](http://www.watto.org/extract)

This is the Game Extractor website - you purchase Game Extractor (full version) through PayPal, and I will give you access to the download.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
