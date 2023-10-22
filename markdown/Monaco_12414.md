## Post #1
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2014-12-22T22:30:54+00:00
- Post Title: Monaco

How can I unpack and pack Monaco .lang files?

Thanks for your help!
[All.zip](https://xentaxbackup.github.io/file/8353_All.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-22T22:54:11+00:00
- Post Title: Monaco

binary template:

```
//--- 010 Editor v6.0 Binary Template
//
// File: monaco
// Author: wrs
// Revision: 1
// Purpose: locale
//--------------------------------------

#include "prelen.bt"

struct HEADER
{
    uint64 size;
    uint64 count;
} hdr;

struct ITEM_INFO
{
    uint64 offset;
    uint64 unknown_1;
};

struct ITEMS
{
    local uint i = 0;

    uint offsets[hdr.count];

    while( i < hdr.count )
    {
        FSeek(offsets[i]);
        ITEM_INFO info;
        ++i;
    }
} items;

struct STRINGS
{
    local uint i = 0;

    while( i < hdr.count )
    {
        FSeek(items.info[i].offset);
        wstr trans(pnt4);
        ++i;
    }
} strings;

```
## Post #3
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-01-06T11:58:11+00:00
- Post Title: Monaco

```
https://mega.co.nz/#!uxxxGRrR!0hyK6Pfu-y_NzDynfDP5yqPfUngIissL2tAtqq2_4aE
```

Text packer here,
and it contain extracted texts in .xlsx.
you can repack texts just drag & drop .xlsx file to .exe.
Enjoy
## Post #4
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2015-01-06T12:10:23+00:00
- Post Title: Monaco

Thank you guys!
