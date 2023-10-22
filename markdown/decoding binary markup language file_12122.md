## Post #1
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-10-17T06:44:20+00:00
- Post Title: decoding binary markup language file

hi, i have this file:

[https://www.sendspace.com/file/32c700](https://www.sendspace.com/file/32c700)

can someone help to make a converter into xml and vice versa?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-18T08:03:52+00:00
- Post Title: decoding binary markup language file

you really shouldn't open different threads for the same request.
(Since your uploaded file is not compressed I answer here.)

For your request, here's like I would do it:
search for the offsets of the entries in the string table at files end.
(there's approx. 3141 entries +74 (used for formatting))

174EE: search for EE 74 01 (00) -> 128 findings

174F0 (2x), F4 (2x), F8 (2x), FC (2x)
the difference between the two offsets to be found is
26BC (+ 24 dec. or + 48 dec. for example)

17500 (2x)
17919 (2x)

1792E  1x at 0x48C
17940  1x at 0xB08
17950  1x at 0x10
17955  1x at 0x16424

and so on

Then try to find out the structure of the file.
## Post #3
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-10-18T17:37:42+00:00
- Post Title: decoding binary markup language file

thanks do i use cheat engine to find these entries of is there some dedicated hex editor?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-18T19:02:22+00:00
- Post Title: decoding binary markup language file

> Reply from odrin
>
> thanks do i use cheat engine to find these entries of is there some dedicated hex editor?afaik cheat engine is not a suiting tool to find start addresses of strings.

Use any simple hexeditor. Maybe you can track down the structure after having processed 50 to 100 strings, maybe not. 

For GBL_item.BML the first strings start at 0x174EE then  after the string terminating 00 there's the next start address and so on.

After you managed to gather the BML structure some coding is required.
## Post #5
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-10-19T03:54:31+00:00
- Post Title: decoding binary markup language file

I was looking at this a couple of days ago, and I think the first few ints after the "xml\0" were pointers to the string tables. You've got char data, element names, and attribute values (and possibly names somewhere), and an "extra bits" table (made of tabs and spaces and newlines, I suppose that are from the original XML). After that, I don't know. I'd probably make a program to read each of the ints and try to dump the string it points to, if it exists. That way you can look for patterns in the way things are organized and figure out the document structure. FWIW, XML is simple to figure out, and binary XML formats always contain the same parts, even if they're roundabout with it.
## Post #6
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-11-02T04:54:15+00:00
- Post Title: decoding binary markup language file

this is harder than that one time i tried to crack la noire's file naming system
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-12T15:38:31+00:00
- Post Title: decoding binary markup language file

just noticed this is from alien isolation (put the name of the game in the title!!!!)

see the bnl->xml converter on this thread:
[viewtopic.php?p=101005#p101005](http://forum.xentax.com/viewtopic.php?p=101005#p101005)

download it:
[download/file.php?id=8215](http://forum.xentax.com/download/file.php?id=8215)
