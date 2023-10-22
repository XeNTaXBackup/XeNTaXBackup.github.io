## Post #1
- Username: Hovnodabljumen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 02, 2006 11:15 pm
- Post datetime: 2006-12-19T21:45:59+00:00
- Post Title: Gorky 17 - game request

I have search for some days and found program that can open .dat files from game Gorky 17. Extracting those will create one level smaller files, also dat files are big folders for smaller (I think image files) .bkg 
Didnt know way next because no one from others extractors or programs  could not launch and view this format.
Thanks in advance for any help with this format.

HWman
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-12-20T21:54:40+00:00
- Post Title: Gorky 17 - game request

Providing an example would help.
## Post #3
- Username: Hovnodabljumen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 02, 2006 11:15 pm
- Post datetime: 2006-12-29T20:03:34+00:00
- Post Title: Gorky 17 - game request

Which type of example do you want?
## Post #4
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-12-29T23:37:09+00:00
- Post Title: Gorky 17 - game request

If you could attach or upload some sample files, that would work.
## Post #5
- Username: Hovnodabljumen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 02, 2006 11:15 pm
- Post datetime: 2007-01-04T20:12:08+00:00
- Post Title: Gorky 17 - game request

[http://www.chaosweaver.ic.cz/01_port.bkg](http://www.chaosweaver.ic.cz/01_port.bkg) (7mb cca)
[http://www.chaosweaver.ic.cz/01_port.zbf](http://www.chaosweaver.ic.cz/01_port.zbf) (2mb cca)
## Post #6
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2007-01-07T12:22:54+00:00
- Post Title: Gorky 17 - game request

OK - the bkg is basically a bunch of 8-bit images, in the example you gave it seems to be backgrounds, you can make out buildings and ships, etc.

The format is as so:

```
4 bytes: all zeroes in the example you provided
4 bytes: an unsigned 32-bit, the number of images in this file
8 bytes: *shrugs*

Then, after that, for each image you have:
8 bytes: a 'counter' of sorts
4 bytes: an unsigned 32, the width of the image, which needs to be multiplied by 2 to give the actual width
4 bytes: the height - does not need to be multiplied
4 bytes: an unsigned 32, the offset within the bkg to the image data itself.
```


As for the zbf: it looks, at first glance, to be RLE-compressed data - standard stuff, one byte gives the run, second gives the byte to draw out. Of course, you'd need to add 1 to the first byte as most of them are zeroes i.e. only one pixel of the following colour.  However, that's just a hunch and I could be wrong.
