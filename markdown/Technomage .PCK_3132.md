## Post #1
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2008-08-17T16:44:43+00:00
- Post Title: Technomage *.PCK

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-08-28T04:09:19+00:00
- Post Title: Technomage *.PCK

Ok this format is really easy. It contains all wav files, but the actuall data is compressed some how, not zlib though.

```
   Int32 - FileCount
   Then there is an array of Entrys defined below

    public struct Entry
    {
        string FileName; //Length = 32
        int Offset;?
        int Size;?
    }
```
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2008-08-28T14:58:28+00:00
- Post Title: Technomage *.PCK

well, thanks, but my problem is still there  any idea about the compression?
## Post #4
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-08-28T15:20:26+00:00
- Post Title: Technomage *.PCK

> Reply from Vash
>
> well, thanks, but my problem is still there  any idea about the compression?

Im not very good with identifiying compression methods.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-18T21:08:54+00:00
- Post Title: Technomage *.PCK

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

encryption xor "\xaa\xab\xac\xad\xae\xaf\xb0\xb1\xb2\xb3\xb4\xb5\xb6\xb7\xb8\xb9\xba\xbb\xbc\xbd\xbe\xbf\xc0\xc1\xc2\xc3\xc4\xc5\xc6\xc7\xc8\xc9\xca\xcb\xcc\xcd\xce\xcf\xd0\xd1\xd2\xd3\xd4\xd5\xd6\xd7\xd8\xd9\xda\xdb\xdc\xdd\xde\xdf\xe0\xe1\xe2\xe3\xe4\xe5\xe6\xe7\xe8\xe9\xea\xeb\xec\xed\xee\xef\xf0\xf1\xf2\xf3\xf4\xf5\xf6\xf7\xf8\xf9\xfa\xfb\xfc\xfd\xfe\xff\x00\x01\x02\x03\x04\x05\x06\x07\x08\x09\x0a\x0b\x0c\x0d\x0e\x0f\x10\x11\x12\x13\x14\x15\x16\x17\x18\x19\x1a\x1b\x1c\x1d\x1e\x1f\x20\x21\x22\x23\x24\x25\x26\x27\x28\x29\x2a\x2b\x2c\x2d\x2e\x2f\x30\x31\x32\x33\x34\x35\x36\x37\x38\x39\x3a\x3b\x3c\x3d\x3e\x3f\x40\x41\x42\x43\x44\x45\x46\x47\x48\x49\x4a\x4b\x4c\x4d\x4e\x4f\x50\x51\x52\x53\x54\x55\x56\x57\x58\x59\x5a\x5b\x5c\x5d\x5e\x5f\x60\x61\x62\x63\x64\x65\x66\x67\x68\x69\x6a\x6b\x6c\x6d\x6e\x6f\x70\x71\x72\x73\x74\x75\x76\x77\x78\x79\x7a\x7b\x7c\x7d\x7e\x7f\x80\x81\x82\x83\x84\x85\x86\x87\x88\x89\x8a\x8b\x8c\x8d\x8e\x8f\x90\x91\x92\x93\x94\x95\x96\x97\x98\x99\x9a\x9b\x9c\x9d\x9e\x9f\xa0\xa1\xa2\xa3\xa4\xa5\xa6\xa7\xa8\xa9"

get FILES long
math BASE_OFF = FILES
math BASE_OFF *= 40
math BASE_OFF += 4

for i = 0 < FILES
    savepos OFFSET
    get NAME string
    get EXT string
    math OFFSET += 32
    goto OFFSET
    get OFFSET long
    get SIZE long

    string NAME += "."
    string NAME += EXT
    math OFFSET += BASE_OFF

    log NAME OFFSET SIZE
next i
```

@mr.mouse: hope there are no problems resolving some old threads, otherwise let me know :)
## Post #6
- Username: IlDucci
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 20, 2014 10:01 pm
- Post datetime: 2018-05-25T22:35:21+00:00
- Post Title: Technomage *.PCK

Hi, I just tested the BMS script with the Spanish voice packs and some of these files are not decoded properly.

The first files are extracted properly but at some point they won't, causing them to just dump themselves compressed as is (The extracted files are WAV files). Could you still help, aluigi?

Sample: [https://nofile.io/f/CJ34eMvtt0B/forest.PCK](https://nofile.io/f/CJ34eMvtt0B/forest.PCK)
