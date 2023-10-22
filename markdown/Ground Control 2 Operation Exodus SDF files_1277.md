## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-25T18:15:09+00:00
- Post Title: Ground Control 2: Operation Exodus SDF files

Help extract SDF files in game Ground Control 2: Operation Exodus

[gc2archive.rar](https://xentaxbackup.github.io/file/256_gc2archive.rar)
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-26T13:34:30+00:00
- Post Title: Ground Control 2: Operation Exodus SDF files

OK I have attached a Game Extractor (Full Version) plugin for these archives. Because there is some odd formatting in the archives, I cannot add support for this archive to Game Extractor (Basic Version).

If you have the full version, unzip into your plugins/ directory (make the directory if it doesn't already exist).

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_SDF_RYS.zip](https://xentaxbackup.github.io/file/259_Plugin_SDF_RYS.zip)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-26T14:14:33+00:00
- Post Title: Ground Control 2: Operation Exodus SDF files

Watto, I think it is impossible to get a correct format from the one file. 

Could we have more examples?

It seems that it start with RYS+version number(byte). 

Then the files. That's where to strange things happen. 

Each file is preceded by a uint32{4}, in case of the first file possibly representing an pointer (relative to the offset of this variable) to the start of the next file when the 8th bit of the 4th byte of the uint32 is NOT set (size would then be this pointer - 4). 

The second file starts with a (relative) pointer, but now that same 8th bit IS set. Consequently, the pointer now represents the exact size of the file (calculate only the first three bytes of the pointer). 

That would also mean the files each start at the 
```
 5D00 0080 
```


That's something different than what your plugin is doing, but may still prove the actual format.
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-27T02:30:08+00:00
- Post Title: Ground Control 2: Operation Exodus SDF files

OK I understand that Mr Mouse - sometimes when I do have more files to work with I need to change the specs alittle. So if we could get some more files for comparison, we will hopefully be able to come up with something more solid.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-28T08:25:08+00:00
- Post Title: Ground Control 2: Operation Exodus SDF files

> Reply from friendsofwatto
>
> OK I understand that Mr Mouse - sometimes when I do have more files to work with I need to change the specs alittle. So if we could get some more files for comparison, we will hopefully be able to come up with something more solid.

WATTO
watto@watto.org
http://www.watto.org

Well, technically, if you need to change the specs, you are not supporting the archive. So, that can be misleading. 

Anyway, I have been able to look at larger files and it appears to be a different story. A 250 MB file also had only two "files". One huge, and the second much smaller and at the back. This leads me to suspect that the second is actually a compressed/encrypted tail of some kind, with the first chunk the actual compressed/encrypted file data.
