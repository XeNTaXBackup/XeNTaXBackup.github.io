## Post #1
- Username: vivanco5555
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Mar 20, 2017 11:54 pm
- Post datetime: 2017-03-20T16:03:32+00:00
- Post Title: Double text-height on opening credits of TWD episode 1

Hi:

I'm doing a personal translation of The Walking Dead episode 1 (cos I'm bored xd) and I've found an error when I encrypt the opening credits text with TTG Tools and ttarchext: it adds more text height than usual. That mean:

ORIGINAL TEXT

lead animator
ONE GUY

ENCRYPTED TEXT

lead animator

ONE GUY

How can I fix this?
## Post #2
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-03-22T10:40:05+00:00
- Post Title: Double text-height on opening credits of TWD episode 1

> Reply from vivanco5555
>
> Hi:

I'm doing a personal translation of The Walking Dead episode 1 (cos I'm bored xd) and I've found an error when I encrypt the opening credits text with TTG Tools and ttarchext: it adds more text height than usual. That mean:

ORIGINAL TEXT

lead animator
ONE GUY

ENCRYPTED TEXT

lead animator

ONE GUY

How can I fix this?
try with telltale explorer and extract this text file
all game in telltale can use a external file in pack folders or archive folder and dont change format files... becuse ttg tool and ttarch extractor cant do that
try last version of telltele explorer... last version can support on all texture , landb , and all ttarch files
## Post #3
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-03-22T10:41:05+00:00
- Post Title: Double text-height on opening credits of TWD episode 1

> Reply from vivanco5555
>
> Hi:

I'm doing a personal translation of The Walking Dead episode 1 (cos I'm bored xd) and I've found an error when I encrypt the opening credits text with TTG Tools and ttarchext: it adds more text height than usual. That mean:

ORIGINAL TEXT

lead animator
ONE GUY

ENCRYPTED TEXT

lead animator

ONE GUY

How can I fix this?
try with telltale explorer and extract this text file
all game in telltale can use a external file in pack folders or archive folder and dont change format files... becuse ttg tool and ttarch extractor cant do that
try last version of telltele explorer... last version can support on all texture , landb , and all ttarch files
## Post #4
- Username: vivanco5555
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Mar 20, 2017 11:54 pm
- Post datetime: 2017-03-22T14:00:21+00:00
- Post Title: Double text-height on opening credits of TWD episode 1

I've tried it but it didn't work. I've downloaded version 1.2.1. 
The problem is you can extract the .text file from .landb with Telltale Explorer, 
but you have to use TTG to encrypt the modified text into a landb again. 
And I can't directly change the text from Telltale Explorer neither.
## Post #5
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-03-22T14:13:59+00:00
- Post Title: Double text-height on opening credits of TWD episode 1

> Reply from vivanco5555
>
> I've tried it but it didn't work. I've downloaded version 1.2.1. 
The problem is you can extract the .text file from .landb with Telltale Explorer, 
but you have to use TTG to encrypt the modified text into a landb again. 
And I can't directly change the text from Telltale Explorer neither.
Dont extract as text.... Click on save all files and select save all(raw dump) and extract to a empty folder on desktop... And now you can see files in original method
## Post #6
- Username: vivanco5555
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Mar 20, 2017 11:54 pm
- Post datetime: 2017-03-22T14:57:09+00:00
- Post Title: Double text-height on opening credits of TWD episode 1

Done. I have some .landb files. But now, how can I modify them without using TTG? Because in order to modify them, I need them to be text files.
## Post #7
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-03-23T11:25:49+00:00
- Post Title: Double text-height on opening credits of TWD episode 1

> Reply from vivanco5555
>
> Done. I have some .landb files. But now, how can I modify them without using TTG? Because in order to modify them, I need them to be text files.
first, extract all files in a empty folder. then... copy your select files to input folder.
open ttg tools and go to auto(de)packer and click on export.
go to output folder and now... you see your text files. edit files and copy edited files to input folder and out put folder... and again, go to auto(de)packer in ttg tool and click on import.
ttg tool making new landb files in out put folder(your text files)
## Post #8
- Username: vivanco5555
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Mar 20, 2017 11:54 pm
- Post datetime: 2017-03-23T12:57:18+00:00
- Post Title: Double text-height on opening credits of TWD episode 1

That didn't work. TTG modify the file in some way causing the double text-height.
## Post #9
- Username: vivanco5555
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Mar 20, 2017 11:54 pm
- Post datetime: 2017-03-23T13:10:35+00:00
- Post Title: Double text-height on opening credits of TWD episode 1

SOLVED!!!!!

For those who had or will have this problem. To avoid the annoying double text-height, you have to follow this steps:

1. Extract your .landb with Telltale Extractor. TTG and ttarchext desencrypt the files in some way, causing the goddamned problem.

2. Open your .landb with an hex software (Hex Editor Neo or Hex Workshop Editor).

3. Modify your text. IMPORTANT: you must conserve the number of characters of the original file AND do not press "supr" while you are hexing. If you don't do that, it won't work. As Tormunds illustrate in the OTWDF forum: 

Hey! Don't eat the cookies! <----- ORIGINAL DIALOGUE
We have to go! Run!           <----- MODIFIED DIALOGUE. Note that we can put spaces if we want to make the dialogue shorter.

And it should work, pals!!

PD.: Thanks to Ghost Dead who named the Telltale Extractor software, which I didn't know it was so much improved.
