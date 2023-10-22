## Post #1
- Username: genjix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 03, 2010 10:46 pm
- Post datetime: 2010-10-03T14:53:06+00:00
- Post Title: Breath of Fire 4 & .EMI file format

Hey,

Having been looking at the bewildering amount of .DAT files through my hex editor I cannot make sense of any of it. Through google I came to your forum here and found these posts,

[viewtopic.php?f=15&t=1984&start=30](http://forum.xentax.com/viewtopic.php?f=15&t=1984&start=30)
[viewtopic.php?f=18&t=3190&hilit=breath+of+fire](http://forum.xentax.com/viewtopic.php?f=18&t=3190&hilit=breath+of+fire)

What is this .EMI format I keep seeing? And what success has there been in extracting content from BOF4?

I notice it has a bunch of .DAT files. Are these archives or files? If so, to extract the sprites I need to find out the chunk structure? I saw some sprites of BOF4 around... If you know any extracted data from this game then please do link me 

Thanks!
## Post #2
- Username: genjix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 03, 2010 10:46 pm
- Post datetime: 2010-10-03T15:09:57+00:00
- Post Title: Breath of Fire 4 & .EMI file format

So I've found apparently the BOF4 format *has* been cracked:

[http://www.xentax.com/?p=122](http://www.xentax.com/?p=122)

But the link to the wiki and the source code is broken.
## Post #3
- Username: Quetzalcoatil
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 02, 2010 10:12 am
- Post datetime: 2010-10-08T12:29:40+00:00
- Post Title: Breath of Fire 4 & .EMI file format

Actually, that first link you posted has the MultiEx Commander script to extract the files from Capcom's .EMI archive format.  They use it apparently on at least BoF:3,4, & 5.  Get a hold of a copy of MultiEx Commander and register ($10), then you can copy the script from down the page on your first link, save it as a text file and run it on one of the .EMI files.  I'm currently working towards ripping out the main models from BOF:5/DQ, but I'm not sure if the model files are compressed, encrypted, or both ... <sigh>

-Q13
## Post #4
- Username: genjix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 03, 2010 10:46 pm
- Post datetime: 2010-10-09T04:35:20+00:00
- Post Title: Breath of Fire 4 & .EMI file format

I see, so it's a script for that program.

What does this line mean?
ImpType SFileSize ;

Is this mean write from Off until FSO? What do the other arguments mean?
Log "" Off FS 0 FSO ;

I assume this means read LONG bytes and store in variable FN? What is the 4th argument?
Get FN Long 0 ;

I assume that LONG = 4 bytes and INT = 2 bytes?
