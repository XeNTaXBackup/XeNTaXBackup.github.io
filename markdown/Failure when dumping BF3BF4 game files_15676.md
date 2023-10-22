## Post #1
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-01-03T19:29:55+00:00
- Post Title: Failure when dumping BF3/BF4 game files

Whenever I try dumping the files of either of these games, I get this error:

Python 2.7 (r27:82525, Jul  4 2010, 09:01:59) [MSC v.1500 32 bit (Intel)] on win32
Type "copyright", "credits" or "license()" for more information.
>>> ================================ RESTART ================================
>>> 
Chunks0.toc
F:f3\dump\chunks\5484aa0d99720e7cbe7a9998d6128d71.chunk

Traceback (most recent call last):
  File "F:\Python_Scripts\dumper.py", line 366, in <module>
    main()
  File "F:\Python_Scripts\dumper.py", line 363, in main
    dump(fname,outputfolder)
  File "F:\Python_Scripts\dumper.py", line 194, in dump
    casHandlePayload(entry,chunkPathToc+hexlify(entry.elems["id"].content)+".chunk")
  File "F:\Python_Scripts\dumper.py", line 347, in casHandlePayload
    makedirs2(outPath)
  File "F:\Python_Scripts\dumper.py", line 68, in makedirs2
    if not os.path.isdir(manualPart): os.makedirs(manualPart)
  File "C:\Python27\lib\os.py", line 150, in makedirs
    makedirs(head, mode)
  File "C:\Python27\lib\os.py", line 157, in makedirs
    mkdir(name, mode)
WindowsError: [Error 123] The filename, directory name, or volume label syntax is incorrect: 'F:\x08f3'
>>> 

Anyone know how to fix this damn thing?
## Post #2
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-01-31T12:12:59+00:00
- Post Title: Failure when dumping BF3/BF4 game files

Anyone? I cannot get this to work no matter how hard I try.
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-02T04:08:07+00:00
- Post Title: Failure when dumping BF3/BF4 game files

[out]
## Post #4
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-02T21:43:24+00:00
- Post Title: Failure when dumping BF3/BF4 game files

That's the thing, the paths are correct in the dumper script:

##Adjust paths here. The script doesn't overwrite existing files so set tocRoot to the patched files first,
##then run the script again with the unpatched ones to get all files at their most recent version.

bf4Directory=r"F:\origin\Battlefield 3"
outputfolder="F:\bf3\dump"

This is what the paths are set as.
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-02T22:46:36+00:00
- Post Title: Failure when dumping BF3/BF4 game files

[out]
## Post #6
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-03T00:33:18+00:00
- Post Title: Failure when dumping BF3/BF4 game files

I did not remove it, it came like that.
In fact, I did not edit the script on any way, shape or form. I just changed the paths.
It's still not working.
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-03T01:08:40+00:00
- Post Title: Failure when dumping BF3/BF4 game files

[out]
## Post #8
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-03T19:29:16+00:00
- Post Title: Failure when dumping BF3/BF4 game files

Well editing the script did jack shit. I will try getting yet another different version and report back.
## Post #9
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-04T01:11:49+00:00
- Post Title: Failure when dumping BF3/BF4 game files

[out]
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-04T11:40:30+00:00
- Post Title: Failure when dumping BF3/BF4 game files

> Reply from Wobble
>
> Well, if it came like that, then the original script was buggy.

The script was not buggy. Python user can put a string without "r" if he knows there will be no symbols recognized as escape sequences. So if it was for example,

outputfolder="F:\games\dragonage",  it will work with no problems. Because "\g" will not be escape seq.
it will also work as outputfolder="F:/bf3/dump"
he could even use "F:\field3\dump" 

Until Portugalotaku will understand how to write strings in python, nobody can help him.
## Post #11
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-04T12:48:57+00:00
- Post Title: Failure when dumping BF3/BF4 game files

I will never understand how to write strings in python, nor do I want to understand, otherwise I would not be asking for help.

I just want the script to work. The BF1 extraction script worked fine, I do not understand why this one does not.

Daemon1, I did not make the script, in case that was not obvious enough already. I do not understand coding at all, that's why I came to this forum, to ask about this with people that do understand.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-04T14:55:42+00:00
- Post Title: Failure when dumping BF3/BF4 game files

> Reply from Portugalotaku
>
> I do not understand coding at all

You don't have to. This "r" is not a part of the script, its a part of path that you want to change.

So now, what happens if you do it like wobble said?

```
outputfolder=r"F:\bf3\dump"
```
## Post #13
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-04T15:01:32+00:00
- Post Title: Failure when dumping BF3/BF4 game files

I already tried that before, it does not work.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-04T15:32:34+00:00
- Post Title: Failure when dumping BF3/BF4 game files

> Reply from Portugalotaku
>
> I already tried that before, it does not work.

what EXACTLY happens?
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-04T16:07:03+00:00
- Post Title: Failure when dumping BF3/BF4 game files

> Reply from Portugalotaku
>
> F:f3\dump\chunks\5484aa0d99720e7cbe7a9998d6128d71.chunk
....
WindowsError: [Error 123] The filename, directory name, or volume label syntax is incorrect: 'F:\x08f3'
you can see the first slash + b is being interpreted as a backspace escape character, it is omitted
from that printed path, placing an r before the string like Wobble said earlier should correct it.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-04T16:20:29+00:00
- Post Title: Re: Failure when dumping BF3/BF4 game files

> Reply from AceWell
>
> placing an r before the string like Wobble said earlier
should correct it.

He said "it does not work". 

But he didn't say what happened.
## Post #17
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-04T17:14:05+00:00
- Post Title: Re: Failure when dumping BF3/BF4 game files

I posted the error in the first post. It's the same error all the time.
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-04T17:17:43+00:00
- Post Title: Re: Failure when dumping BF3/BF4 game files

here is similar discussion on Stack Overflow
[http://stackoverflow.com/questions/2296 ... to-x08-and](http://stackoverflow.com/questions/22961145/the-reason-python-string-assignments-accidentally-change-b-into-x08-and)

3 ways to fix it

> Use raw strings or double your backslashes or use forward slashes

r"\b"  = raw string
"'\\b'" = double backslash
"/b"   = forward slash
## Post #19
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-04T18:05:41+00:00
- Post Title: Re: Failure when dumping BF3/BF4 game files

Chunks0.toc
F:\bf3\dump\chunks\d9ad7b0ce3b63eb0ff68581d2bc6a3cf.chunk

Traceback (most recent call last):
  File "F:\Python_Scripts\dumper.py", line 366, in <module>
    main()
  File "F:\Python_Scripts\dumper.py", line 363, in main
    dump(fname,outputfolder)
  File "F:\Python_Scripts\dumper.py", line 194, in dump
    casHandlePayload(entry,chunkPathToc+hexlify(entry.elems["id"].content)+".chunk")
  File "F:\Python_Scripts\dumper.py", line 353, in casHandlePayload
    LZ77.decompressAndWriteUnknownFile(catEntry.filename,catEntry.offset,catEntry.size,outPath)
WindowsError: [Error -529697949] Windows Error 0xE06D7363
>>> 

It's not working.
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-04T18:53:23+00:00
- Post Title: Re: Failure when dumping BF3/BF4 game files

And you're calling it "the same error" ???

Finally, after 3 different people told you, now you're posting the actual error. This means the data is not compressed with LZ4, but different compressor. You need a script for BF3, not BF4. They are different, and since you never posted the script you used, nobody could help you.
## Post #21
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-04T19:19:58+00:00
- Post Title: Re: Failure when dumping BF3/BF4 game files

The errors seemed identical to me, I saw them so many times they blurred together. I told you I suck at anything coding-related.

I was looking for a BF3 script, and they said this worked on BF3, that's why I used it. I will see if I can find a BF3 script.
## Post #22
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-04T19:31:38+00:00
- Post Title: Re: Failure when dumping BF3/BF4 game files

Okay it seems to be working now, thanks.
 I won't bother you guys with this crap anymore now, peace.
