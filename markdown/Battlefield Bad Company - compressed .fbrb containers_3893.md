## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-25T12:35:40+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-26T18:00:10+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

don't use rapidshare, it never works:
[viewtopic.php?f=17&t=3792](http://forum.xentax.com/viewtopic.php?f=17&t=3792)
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-26T21:10:10+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

Sorry, didn't see that.  :  
Here's another link with different files: [http://www.sendspace.com/file/myvhv8](http://www.sendspace.com/file/myvhv8)
Thanks!
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-26T22:13:11+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

job done:
*edit* watch the link in the next posts
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-27T08:14:33+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

WOW! Thanks a lot! That was amazingly fast!    Hope to be able to write my own scripts some day!   
However when I try to extract the sound archive, quickbms gives me the error: 

```
Error: No such file or directory
```

I've uploaded the first 64KB, maybe you can figure out what's different with this file: [http://www.filefront.com/15006417/strea ... unds_start](http://www.filefront.com/15006417/streaming_sounds_start)
Thanks an awful lot for this!!!    

Edit: the whole file has a size of 1.396.312.523 Bytes - maybe this is a problem? Like a bounded-size variable I mean.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-27T11:38:39+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

how much ram you have?
it's possible that you don't have enough ram and/or virtual memory because it must decompress over 1gb of data in your memory.
so I'm highly sure that this is the problem (the files you provided were enough small, that's why I opted for the in-memory decompression).

in this case (big files only) you must use the following:
*edit* removed
it's just the same as before but with a phisical file.
let me know if it works otherwise please upload at least 1 megabyte of the sound file.
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-27T15:25:41+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

Thanks for the new code, I'll try it later when I'm home again! =)
I have 4GB of RAM which should be sufficient.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-27T18:23:58+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-27T23:43:15+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

I have verified the structure of the file table and it has nothing strange or fields too big (nothing that can't be handled by 4gb or ram + virtual memory eh eh eh).

I have noticed that you are using an old version of quickbms because at line 5111 there is no myalloc in the current one.
so can you make a test also using the latest version (the link is in the script)?
maybe nothing changes but at least is possible to exclude this hypothesis
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-28T01:29:08+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

Thanks for your efforts!
I've deleted the old quickbms and used the new one - now the error points to line 5779.    
No matter which of the above scripts I use...
Maybe I'll upload the whole file so you can check it directly there.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-28T01:51:34+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

uhmmm, the last thing I can try is watching the extractionlog.
so launch:

```
quickbms -v -x fbrb.bms streaming_sounds.fbrb c:\output_folder > log.txt
```
then send me log.txt or attach it to your post.
## Post #12
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-28T02:22:09+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

I've attached the error log. Thanks for looking.
[log.zip](https://xentaxbackup.github.io/file/2565_log.zip)
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-28T11:39:53+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

problem solved, it was simply that the data containing the files isn't compressed with gzip.
I have updated the script: [http://aluigi.org/papers/bms/fbrb.bms](http://aluigi.org/papers/bms/fbrb.bms)
## Post #14
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-29T15:23:58+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

Sorry, I still get the error at line 5779...
I should really upload the whole archive! This could take a while!
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-29T17:02:30+00:00
- Post Title: Battlefield: Bad Company - compressed *.fbrb containers

for reference: the problem has been solved and was related the size of the data which wasn't allocable (too big or something else).
so it's enough to use this modified script ONLY FOR THIS BIG ARCHIVE: [http://aluigi.org/papers/bms/fbrb_nogzip.bms](http://aluigi.org/papers/bms/fbrb_nogzip.bms)
## Post #16
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-29T19:41:33+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

THANKS A LOT LUIGI!!!     
So this topic can be closed now I guess
## Post #17
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-01T15:34:07+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

Hm, maybe could update the Xentax wiki? I guess a lot of people are interested in this!
## Post #18
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-06T19:38:24+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

Hi again. I just checked various fbrb archives when extracted and it seems as if there are plenty of files missing.    First thing I noticed was that in some command files there were links to music files that weren't extracted. Upon further research and some extractions I saw that only part of the containers are extracted.
For example, when extracting this file: [http://www.sendspace.com/file/s4n24j](http://www.sendspace.com/file/s4n24j) (5.09 MB), only 16.6 KB of data is extracted, whereas this file [http://www.sendspace.com/file/qn4ut5](http://www.sendspace.com/file/qn4ut5) and others aren't extractable at all...
Maybe you could take a look at these files again?
Sorry to bother you after quite a time...
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-07T12:14:16+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

it's obvious that it extract only 16 kb of files, there is a HUGE error showed by quickbms!
why don't you reported it?

anyway the explanation is simply that there are no compressed files in these archives, the ZSIZE field in reality is the SIZE one and the previous SIZE is... don't know.
I have updated the script to version 0.1.2, now everything should ok
## Post #20
- Username: ogomez
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 23, 2010 2:34 am
- Post datetime: 2010-06-21T12:56:33+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

Hey
I'm trying to extract the streaming_sounds-00.fbrb file... but I'm getting a memory dump error.
Can I extract the contents to a temp folder instead of memory? Because I only have 1.87gb ram...
## Post #21
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-26T22:34:22+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

[http://aluigi.freeforums.org/post10236.html#p10236](http://aluigi.freeforums.org/post10236.html#p10236)
## Post #22
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-30T20:06:39+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

The contents of this post was deleted because of possible forum rules violation.
## Post #23
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-02T09:18:03+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

EDIT: I took a look at the source code and the decompressed info and data files. I found out that your NAMESZ variable is actually a type offset. It also states if a file is deleted (the offset holds the string "*deleted*"), so you may want to update the main loop as follows:

```
    get NAMEOFF long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE
    get XSIZE long MEMORY_FILE
    get TYPEOFF long MEMORY_FILE

    savepos TMP MEMORY_FILE
    math NAMEOFF += NAME_BASE
    goto NAMEOFF MEMORY_FILE
    get NAME string MEMORY_FILE
		math TYPEOFF += NAME_BASE
		goto TYPEOFF MEMORY_FILE
		get TYPE string MEMORY_FILE
		if TYPE == "<non-resource>"
			set TYPE "non-resource"
		endif
		string NAME += "."
		string NAME += TYPE
	goto TMP MEMORY_FILE
	if SIZE != 0
		log NAME OFFSET SIZE MEMORY_FILE2
	endif
next i
```
It writes the file type behind the .res extension. You can also easily filter out all sounds for example by substituting
```
		if TYPE == "Wave"
			log NAME OFFSET SIZE MEMORY_FILE2
		endif
	endif
```
## Post #24
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-02T15:00:35+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

ah ok, so luckily it's not a bug in the script :)
good so there is nothing to change or would be better to not extract the 0 bytes files?
uhmmm I will think about the idea
## Post #25
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2010-07-26T18:15:41+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

Pls help me create or repack .fbrb archive.
Please
## Post #26
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-07-27T05:56:26+00:00
- Post Title: Re: Battlefield: Bad Company - compressed *.fbrb containers

i need to edit voices-speech, how shoud i do that? is there a way for this? can any-one make mercy to me?    
even though bms script extracts some in unknown way sound fbrb archives, i coudnt explore them
