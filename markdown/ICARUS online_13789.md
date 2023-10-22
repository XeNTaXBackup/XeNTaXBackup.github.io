## Post #1
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2016-01-11T11:33:18+00:00
- Post Title: ICARUS online

[http://www.mediafire.com/download/ez7pq ... p003_3.zip](http://www.mediafire.com/download/ez7pqzll8j3uczo/hw_ar0_p003_3.zip)

How can we resolve this type of model?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-11T15:30:13+00:00
- Post Title: ICARUS online

Why don't you try it out using hex2obj?
There's all you need: floats, face indices.

I'd suggest to start your examination at 0x27790 or 0x29F2C to skip assumed bone data.
There's 7 assumed startaddresses for face indices blocks (search for 000001000200).
## Post #3
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2016-01-11T16:22:10+00:00
- Post Title: ICARUS online

> Reply from shakotay2
>
> Why don't you try it out using hex2obj?
There's all you need: floats, face indices.

I'd suggest to start your examination at 0x27790 or 0x29F2C to skip assumed bone data.
There's 7 assumed startaddresses for face indices blocks (search for 000001000200).
I have been using hex2obj
But the first contact of this type
I do not know how to search and setup
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-11T17:38:39+00:00
- Post Title: ICARUS online

> Reply from wordhg
>
> I do not know how to search and setupread the tutorial, please ('tut' button in hex2obj).

The binary search for 00 00 01 00 02 00 has to be done in a hexeditor where you open the .skin file.
## Post #5
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2016-01-11T19:16:58+00:00
- Post Title: ICARUS online

Yes, I was so search
But setp.2 i will not set
So can you give me an example?
[](http://piccy.info/view3/9260783/b3f1a75b2c7c7b0b2dc4347afdc95d50/1200/)[](http://i.piccy.info/a3c/2016-01-11-19-32/i9-9260783/800x338-r)
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-01-11T21:45:11+00:00
- Post Title: ICARUS online

This is so funny lol Icarus using CryEngine, just rename .skin to .cgf/chr and you will be able to open it in Noesis. Geometry with bones and weights. Maybe even some of my script's will do, though better use Noesis!
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-11T21:59:34+00:00
- Post Title: ICARUS online

well, you are pretty close. But why did you choose an FVF size of 48?
It doesn't make sense as you can see from the pic where the characteristic patterns have an offset of 64.

I'm unsure of the uvs, maybe we'll find them later (more likely to be floats than half floats (HF_)).

Well done so far, wordhg.  
Btw: better use 0x29F38 as a start address for the vertices (while your address will do, too, strangely, but the mesh looks different then)

Seems, zaramot answered meanwhile I was writing...



hw_ar0_p003_2-skin.JPG (82.84 KiB) Viewed 283 times
