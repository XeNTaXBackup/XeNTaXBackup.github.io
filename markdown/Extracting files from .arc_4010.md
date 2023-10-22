## Post #1
- Username: bwesty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 05, 2010 3:10 pm
- Post datetime: 2010-01-05T09:00:03+00:00
- Post Title: Extracting files from .arc

Hello All, 

I was wondering if somebody had a spare minute or two, to assist me in extracting the files from either of the two .arc files presented in sample at this link [http://www.sendspace.com/file/hutu2u](http://www.sendspace.com/file/hutu2u). I tried using the method described in this link [viewtopic.php?f=15&t=2845](http://forum.xentax.com/viewtopic.php?f=15&t=2845) which seemed to work because it listed the amount of files present, but not the filenames, and then I didn't know how to manually extract the files.

Thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-05T13:36:49+00:00
- Post Title: Extracting files from .arc

the archive doesn't seem to contain the names of the files and seems the some of these arc files (for example igc.arc) contain other arc files inside them, anyway the following script for quickbms does the job:

```
if XFA10 != 0xfa10
    cleanexit
endif
get FILES long
get BASE_OFF long
get DUMMY long

get FULLNAME basename
string FULLNAME += "_"

for i = 0 < FILES
    get CRC long
    get OFFSET long
    get ZSIZE long
    get SIZE long

    set NAME string FULLNAME
    string NAME += i
    if SIZE == 0
        log NAME OFFSET ZSIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: bwesty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 05, 2010 3:10 pm
- Post datetime: 2010-01-06T00:09:55+00:00
- Post Title: Extracting files from .arc

Thankyou very much for your script. I think I managed to extract all the files from both .arc files but I stopped there because there were thousands of files with no names or extensions. Later I will try to ascertain what some of them are.

EDIT: You are 100% correct, inside igc.arc are other .arc files which then either have files or U8 archives
## Post #4
- Username: bwesty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 05, 2010 3:10 pm
- Post datetime: 2010-01-06T07:18:12+00:00
- Post Title: Extracting files from .arc

Unfortunately the script only worked for the first few archives inside igc.arc

EDIT: The script only worked for the first 10 files of igc.arc, there are close to 300 arc files in igc.arc. I tried editing the script but I havent got it to work yet.
## Post #5
- Username: bwesty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 05, 2010 3:10 pm
- Post datetime: 2010-01-07T04:37:11+00:00
- Post Title: Extracting files from .arc

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: bwesty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 05, 2010 3:10 pm
- Post datetime: 2010-01-08T10:21:41+00:00
- Post Title: Extracting files from .arc

I need some help creating a script to unpack some files I believe to be archived. I have been trying very hard by myself to learn how to do it but I need a few pointers. A typical file that I am trying to extract are located [http://www.sendspace.com/file/j78d8z](http://www.sendspace.com/file/j78d8z) I estimate there are about 10-15 of 290 which are composed in this manner. I was fortunate enough to unpack the first 10 using the above script.

This is all I know so far. All of the aforementioned 10-15 files begin with 01 0F. Then there are another four bytes which I thought might be a file count figure, however the hex numbers are way too high for this. Then we have another 12 bytes which are insignificant then the first file name commences. I have uploaded a screenshot of a typical file loaded in a hex editor just in case someone recognises something which might be of assistance to me.

P.S sorry the screenshot is so large

EDIT: Now I am thinking that a file such as this is actually an fsb file, therefore I will be directing my attention towards decrypting an fsb file.
[igc.JPG](https://xentaxbackup.github.io/file/2699_igc.JPG)
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-22T19:33:31+00:00
- Post Title: Extracting files from .arc

I'm also working on the format right now. I think it's helpful to mention that the files are from Silent Hill: Shattered Memories. My script is basically the same as Luigi's (seems as if I'm slowly getting the hang of QuickBMS  ) but it only works for the PS2 and Wii version, but not for the DATA.ARC from the PSP version.

Look at this thread I accidentially opened: [viewtopic.php?f=10&t=4245&start=0&st=0&sk=t&sd=a](http://forum.xentax.com/viewtopic.php?f=10&t=4245&start=0&st=0&sk=t&sd=a)
As soon as I understand the hash reverse, we'll have file names. 
BTW, those FSB archives you mentioned are contained in these *.fev files (at least I guess that's the extension) you took a screenshot from. Just cut the data before "FSB4" and save it as *.fsb. Then you can extract it with fsbext. However this doesn't work for all of the FSB files I've encountered.

Edit: The file names can't be reversed from the CRC values but I've researched a bit more on those formats. I'm now writing an extensive script that also includes an extension allocator. I'll post here if the status is advanced enough.
