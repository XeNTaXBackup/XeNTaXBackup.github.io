## Post #1
- Username: Gabor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 07, 2008 3:55 am
- Post datetime: 2008-04-07T17:18:05+00:00
- Post Title: Multiex failed to process. Subscript out of range?

Hi!
I wrote a script to support Rebel Raiders Operation Nighthawk .bag files, and it works fine until I want to extract something from the archive. Then it says "Multiex failed to process Subscript out of range", and does nothing. Any suggestions?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-07T18:44:06+00:00
- Post Title: Multiex failed to process. Subscript out of range?

Post the script?
## Post #3
- Username: Gabor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 07, 2008 3:55 am
- Post datetime: 2008-04-07T19:31:43+00:00
- Post Title: Multiex failed to process. Subscript out of range?

Here is the script:

```
Get JUNK Long 0;
Get NOF Long 0;
Get NEXTFILE Long 0;
Do;
GoTo NEXTFILE 0;
Get FILENAME String 0;
SavePos WOFFSET 0;
Get FILEOFF Long 0;
SavePos WSIZE 0;
Get FILELENGTH Long 0;
Log FILENAME FILEOFF FILELENGTH WOFFSET WSIZE;
Math NEXTFILE += 48;
Math COUNTER += 1;
While COUNTER <> NOF;

```
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-07T19:49:09+00:00
- Post Title: Multiex failed to process. Subscript out of range?

The contents of the bag files show correctly? (Screenshot?), oh and press CTRL+L for debug.log
## Post #5
- Username: Gabor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 07, 2008 3:55 am
- Post datetime: 2008-04-07T20:06:05+00:00
- Post Title: Multiex failed to process. Subscript out of range?

The content of the archieve seems to be ok, i just can't extract or prewiev anything.
I just discovered! It shows to separate errors depending on the file I try to open.
Debug log:

```
21:53:12[i]- MEX Open list file  C:\Program Files\MultiEx Commander\data\multiex.lst
21:53:12[i]- MEX Number of list entries  18282
21:54:28[!]- Extract: Corrupted file info! -33227260>-33686019 (?) 
21:54:29[!]- MEX Extraction of file failed 
21:54:30[!]- MultiEx failed to process Subscript out of range
21:54:31[!]- MEX Extraction of file failed 
21:54:32[!]- MultiEx failed to process Subscript out of range
21:54:33[!]- MEX Extraction of file failed 
21:54:34[!]- MultiEx failed to process Subscript out of range
21:54:35[!]- MEX Extraction of file failed 
21:54:36[!]- Extract: Corrupted file info! -33227256>-33686019 (?) 
21:54:36[!]- MEX Extraction of file failed 
21:54:38[!]- Extract: Corrupted file info! -33227256>-33686019 (?) 
21:54:40[!]- MEX Extraction of file failed 
21:54:43[!]- Extract: Corrupted file info! -33227256>-33686019 (?) 
21:54:44[!]- MEX Preview file failed 
21:54:45[!]- Extract: Corrupted file info! 14408666>-33686019 (?) 
21:54:46[!]- MEX Extraction of file failed 

```


Here's a screenshot.
[multiex.JPG](https://xentaxbackup.github.io/file/1488_multiex.JPG)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-07T20:21:50+00:00
- Post Title: Multiex failed to process. Subscript out of range?

You seem to be having trouble with some of your file sizes and offsets... they shouldn't ever be negative. Has the Rebel Raiders *.bag format been documented elsewhere here on the forum? It would be useful to be able to look at it side-by-side with the script.
## Post #7
- Username: Gabor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 07, 2008 3:55 am
- Post datetime: 2008-04-08T12:46:33+00:00
- Post Title: Multiex failed to process. Subscript out of range?

Yes, it doesn't seem to be allright. Perhaps it uses some encryption. I'm not sure about that. If i open it in hex and it shows the filenames correctly, but where the numbers are, I only see junk, then it meens encryption, doesn't it? Unfortunately, there is only one .bag file, and its 500 MB so i have no idea on where to upload it.

Do you have any idea?

EDIT:[http://wiki.xentax.com/index.php?title= ... aiders_BAG](http://wiki.xentax.com/index.php?title=Rebel_Raiders_BAG)
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-08T17:02:00+00:00
- Post Title: Multiex failed to process. Subscript out of range?

All right, looking at your script versus the posted format (and referencing some MexScript command documentation), it seems that your problem lies with the filename field - the field is always 40 bytes long, but the actual filename is null-terminated. This means that when you Get FILENAME String 0;, you're reading up to the null, and then the next commands read into the junk left at the end of the field. Try using this script instead (this is sort of my first one, so please forgive me if it doesn't work):

```
Get JUNK Long 0;
Get NOF Long 0;
Get NEXTFILE Long 0;
Do;
GoTo NEXTFILE 0;
Get FILENAME String 0;
Math NEXTFILE += 40;
GoTo NEXTFILE 0;
SavePos WOFFSET 0;
Get FILEOFF Long 0;
SavePos WSIZE 0;
Get FILELENGTH Long 0;
Log FILENAME FILEOFF FILELENGTH WOFFSET WSIZE;
Math NEXTFILE += 8;
Math COUNTER += 1;
While COUNTER <> NOF;
```


It's a bit of a hack, if anyone knows a shorter way to do

```
GoTo NEXTFILE 0;
```

I'm all ears...
## Post #9
- Username: Gabor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 07, 2008 3:55 am
- Post datetime: 2008-04-08T17:13:51+00:00
- Post Title: Multiex failed to process. Subscript out of range?

It works!!! Thank you very much!
## Post #10
- Username: Gabor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 07, 2008 3:55 am
- Post datetime: 2008-04-09T16:05:37+00:00
- Post Title: Multiex failed to process. Subscript out of range?

Hi! I have problems again. 

First, perhaps you saw on the screenshot I sent, that there are some files without extension (and with -1 size) I think these are some kind of separators between different kinds of files (e.g. Textures, Fonts). When I try to open these it says "MultiEx failed to process. Bad record number", but I think it's not a problem, these files doesn't contain any data. BUT, when I open a file next to these separators (only before these, not after) it says "Extract: Corrupted file info! <offset> > -1 (?)". The offset is always equal to the <offset of file I tried to open> + <size of file I tried to open>.

Okay, it was only my first problem 

The other one is, that if I manage to edit anything, and it's not exactly as long as before, then the game crashes. Isn't it possible, that four unknown bytes in the GRAF is a checksum, or something like that? Or do you think, the game checks the SIZE of tha bag before starts?

Huhh, thanks for reading (and answering)!
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-09T16:14:25+00:00
- Post Title: Multiex failed to process. Subscript out of range?

Looking at the screenshot, I'd say these extensionless "files" are actually folders... Unfortunately, I really don't know how to handle folders like this in a MexScript, so someone else is going to have to help you... Although, it may help to post a new log.
## Post #12
- Username: Gabor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 07, 2008 3:55 am
- Post datetime: 2008-04-09T16:25:41+00:00
- Post Title: Multiex failed to process. Subscript out of range?

```
18:24:12[i]- MEX Open list file  C:\Program Files\MultiEx Commander\data\multiex.lst
18:24:12[i]- MEX Number of list entries  18282
18:24:29[!]- Extract: Corrupted file info! 56124>-1 (?) 
18:24:30[!]- MEX Extraction of file failed 
18:24:31[!]- Extract: Corrupted file info! 19744>-1 (?) 
18:24:32[!]- MEX Extraction of file failed 
18:24:40[!]- Extract: Corrupted file info! 16536698>138 (?) 
18:24:42[!]- MEX Extraction of file failed

```


You meant debug.log?
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-13T15:12:20+00:00
- Post Title: Multiex failed to process. Subscript out of range?

Is it possible to use the filecutter to cut out the first and last pieces of the archive file of 500mb? Perhaps the format is just a little different. 

@Dinoguy: Good show, old chap! Now you've mastered some of the totally illogical yet somehow vaguely logical MexScript!
## Post #14
- Username: Gabor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 07, 2008 3:55 am
- Post datetime: 2008-04-13T15:46:58+00:00
- Post Title: Multiex failed to process. Subscript out of range?

Hello!

Unfortunately I don't think it is possible, you need the beginning, a part from the end and a part from the middle. Is that possible with filecutter?
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-13T22:03:21+00:00
- Post Title: Multiex failed to process. Subscript out of range?

> Reply from Mr.Mouse
>
> @Dinoguy: Good show, old chap! Now you've mastered some of the totally illogical yet somehow vaguely logical MexScript!
Eh heh heh, it's something I've been meaning to do for some time. ^_^;; It's actually fairly straightforward if you have the script, file format, and MexScript reference open at the same time so you can flip between them as needed.
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-14T04:53:13+00:00
- Post Title: Re: Multiex failed to process. Subscript out of range?

> Reply from Gabor
>
> Hello!

Unfortunately I don't think it is possible, you need the beginning, a part from the end and a part from the middle. Is that possible with filecutter?

No, it is not. But it may not make too much a difference, could at least take a look at the begin and end parts of the script this way. If you could use the cutter, then that would be swell.
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-14T18:12:59+00:00
- Post Title: Re: Multiex failed to process. Subscript out of range?

Alternatively, if you're that worried about it, you could try uploading the whole archive to a filesharing website and post a link to it here... I'd suggest only using that as a last resort, though.
