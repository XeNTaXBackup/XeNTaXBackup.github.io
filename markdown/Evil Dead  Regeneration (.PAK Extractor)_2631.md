## Post #1
- Username: Drak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 25, 2007 12:43 pm
- Post datetime: 2007-05-25T18:45:37+00:00
- Post Title: Evil Dead : Regeneration (.PAK Extractor)

Yes, i know that MultiEX supports evil dead regeneration, but the audio archives only. Standard pak "extractors" don't seem to work.
(WinRAR, WinZip, GCFScape, and most Quake tools)
[deerhead.rar](https://xentaxbackup.github.io/file/1185_deerhead.rar)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-26T12:15:51+00:00
- Post Title: Evil Dead : Regeneration (.PAK Extractor)

Did you cut the pak file or it's the original size?
Could you upload more samples sp I can give it a try!
## Post #3
- Username: Drak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 25, 2007 12:43 pm
- Post datetime: 2007-05-26T16:13:59+00:00
- Post Title: Evil Dead : Regeneration (.PAK Extractor)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-27T12:51:16+00:00
- Post Title: Evil Dead : Regeneration (.PAK Extractor)

LOL, the game make every single file type to .pak!?

```

DWORD		numFileType
DWORD		numFiles
DWORD		ukn1		//version??
DWORD		magicWord	//'XXXX'

{				//File Type description
 CHAR[4]	fileType
 DWORD		numThisType
 DWORD		ukn2
 DWORD		ukn3
} [numFileType]

{				//File description
 CHAR[4]	fileType
 DWORD		ukn4
 DWORD		ofsStart
 DWORD		fileLength
} [numFile]

The real file data start right after all the above data here.
```


I dont have MultiEx Commander ATM, so I can't write a mexscript.
If you need it, drop me a line.
## Post #5
- Username: Drak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 25, 2007 12:43 pm
- Post datetime: 2007-05-27T19:19:34+00:00
- Post Title: Evil Dead : Regeneration (.PAK Extractor)

> Reply from fatduck
>
> If you need it, drop me a line.

Uhh, sorry lulz. I'm not exactly sure what "drop me a line" means D:
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-27T22:59:34+00:00
- Post Title: Evil Dead : Regeneration (.PAK Extractor)

I had written a mexscript for it but seems having an error in MultiEx Commander!?

[You can take a look at this](http://forum.xentax.com/viewtopic.php?t=2637)
## Post #7
- Username: Drak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 25, 2007 12:43 pm
- Post datetime: 2007-05-27T23:26:44+00:00
- Post Title: Evil Dead : Regeneration (.PAK Extractor)

Awesome dude, thanks. But damn, I was hoping for a 'known' file type when extracted. Now i gotta figure out what the ".2pr" and ".ldmc" files are.
