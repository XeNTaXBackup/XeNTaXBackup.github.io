## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-02T04:39:31+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Nice game and BAD game archives  you will look that it is possible to make in order to take out from there the resources  

Mr.Mouse , Watto what say guys ? 
[customdata.zip](https://xentaxbackup.github.io/file/539_customdata.zip)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T08:33:59+00:00
- Post Title: Snowy - Fish Frenzy - ARF

The archive itself contains raw pictures,
(only pictures from what ive seen)

here is an example after some hexxing
[Untitleddd1.gif](https://xentaxbackup.github.io/file/544_Untitleddd1.gif)
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T08:54:05+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Analyzed the archive a bit further.
unfortunately, im kind of bad in explaining things, so
i took a screenshot and tried my best to make an explanation
from what i THINK is a correct interpretation of the format.
[arf.gif](https://xentaxbackup.github.io/file/545_arf.gif)
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T12:15:50+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Nice work  - at least we know the type of files in there, as I could not find any filenames.

This is the specifications I have thus far - but I havn't coded or tested them yet.

```
| Snowy: Fish Frenzy *.arf |
+--------------------------+

// ARCHIVE HEADER
  2 - Header (AR)
  2 - null
  4 - Number Of Files
  4 - Hash?
  4 - Directory Offset

X - Unknown Junk

// DIRECTORY
  // for each file
    2 - File ID (incremental from 1)
    2 - Unknown
    4 - File Offset
    4 - File Length
    4 - Hash
    
// FILE DATA
  // for each file
    X - File Data
```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-03T14:51:56+00:00
- Post Title: Snowy - Fish Frenzy - ARF

It's easy. The filenames are right under your nose. 

The "unknown" chunk is actually the filenames. They are XOR-encrypted and the XOR key is saved right there in the archive, right after the Number of Files. 

After the pointer to the resource info offset, comes 

```
// For each resource

  [1]   Size of resourcename
  [n]   Encrypted resourcename


```


The XOR key is 4 bytes in length. To calculate the number of times you should apply the key to the filename in a row. 

```

```


The remainder of the resourcename is not encrypted (max 3 bytes). 

I've coded a MultiEx Commander plugin for these files, to extract the files with the correct filename. 

Get the plugin, and create an ARF archive in the data/plugins directory, then store there the Snowy.dll. Start MexCom and enjoy!
[mexarf.jpg](https://xentaxbackup.github.io/file/547_mexarf.jpg)

[Snowy.zip](https://xentaxbackup.github.io/file/546_Snowy.zip)
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-03T15:07:25+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Wow ......... Mr.Mouse , Watto , Strobe thanks guys
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T22:28:56+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Ah  I didn't even notice that junk section, I was supposed to come back to it after I worked out the rest of the format, but obviously I didn't  . Good work mate, glad someone was able to correct me.

I will look towards putting this in the next GE update.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-03T23:30:23+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Okey Watto  .... Am extracted files has been crypted..... all textures and sounds files.. Simple so not to open them
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-04T08:37:11+00:00
- Post Title: Snowy - Fish Frenzy - ARF

The textures I've seen are not encrypted, they are more like raw pixeldata. The filenames suggest they came from DDS files though, so it could be that the authors have stripped the DDS file headers from these. 

Something similar could then be the case with the sound files you mention.
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T09:55:32+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Actually, the headers of the file data are encrypted - you can see the entry I just placed on the wiki. There is a 1-byte value that, if used on the file data, will give back the normal headers. Well, at least it gave me the DDS headers for the files I tried, so I would assume it would work for the other files too.

I think Mr Mouse is correct though, in that the texture data is not encrypted, so there must be some way to distinquish where to start/stop the decryption of the file data.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #11
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T10:15:49+00:00
- Post Title: Snowy - Fish Frenzy - ARF

OK, it appears as though the first 20 bytes of the file data are XORed, and the remaining bytes are to be read as normal. I have tested it with all the DDS images in the sample archive and it worked fine.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-04T10:51:51+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Okay, good. I fixed the MexCom Snowy plugin to include such decryption. See screenshot.
[mexsnowy.jpg](https://xentaxbackup.github.io/file/554_mexsnowy.jpg)

[Snowy.zip](https://xentaxbackup.github.io/file/553_Snowy.zip)
## Post #13
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T11:05:28+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Wow - finally I got one right  - usually I post the specs for something and you correct me.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-04T11:10:48+00:00
- Post Title: Snowy - Fish Frenzy - ARF

> Reply from friendsofwatto
>
> Wow - finally I got one right  - usually I post the specs for something and you correct me.

lol
## Post #15
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-04T15:12:36+00:00
- Post Title: Snowy - Fish Frenzy - ARF

Mr.Mouse , Watto BIG thanks   I knew that you guys me you will help
## Post #16
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-04T18:48:00+00:00
- Post Title: 

Mr.Mouse create new topic here ....

[viewforum.php?f=14](http://forum.xentax.com/viewforum.php?f=14)


Since itself to create new topic there I not can (there are no rights of moderator) you create
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-04T19:01:28+00:00
- Post Title: 

[viewtopic.php?p=13088#13088](http://forum.xentax.com/viewtopic.php?p=13088#13088)
