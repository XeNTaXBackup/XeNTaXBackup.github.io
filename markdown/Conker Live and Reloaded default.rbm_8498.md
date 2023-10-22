## Post #1
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-07T17:57:40+00:00
- Post Title: Conker Live and Reloaded "default.rbm"

hello im trying to extract modles from conker live and reloaded. So far, i was able to decrompress the iso file and found the particular model i am looking for, but its in a very weird format, "RBM". I tried reading it on HxD and cant seem to find the files im looking for because its all a bunch of random variables. Can someone please help me? 

[http://www.mediafire.com/?d1htggzc5pf2m9k](http://www.mediafire.com/?d1htggzc5pf2m9k)
## Post #2
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-09T05:54:49+00:00
- Post Title: Conker Live and Reloaded "default.rbm"

Did I even post this in the right place?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-12T11:59:27+00:00
- Post Title: Conker Live and Reloaded "default.rbm"

its using an unkown compression not much anyone can do for this.
## Post #4
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-16T05:39:46+00:00
- Post Title: Conker Live and Reloaded "default.rbm"

Could that be possibly due to the fact that no one is taking the time to invest on finding a way to extract it? Ill do it myself but i need SOME kind of direction im still a noob at all of this shit.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-16T09:27:24+00:00
- Post Title: Conker Live and Reloaded "default.rbm"

the only way your going to get anything from these games is to buy a debug original xbox unit and send it to someone who knows how to use one and also is willing to put in the time to reverse the format compression. I already looked at the files and without that nothing is going to happen.
## Post #6
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-18T08:10:32+00:00
- Post Title: Conker Live and Reloaded "default.rbm"

Okay im now one step further, thanks a mil. , and sorry for the temper
## Post #7
- Username: smurfted
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 23, 2014 11:32 pm
- Post datetime: 2014-11-23T18:35:34+00:00
- Post Title: Conker Live and Reloaded "default.rbm"

Sorry for dragging this up but, as 2014 comes to an end does anyone have any ideas on how to unpack this file type?
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-29T21:29:20+00:00
- Post Title: Conker Live and Reloaded "default.rbm"

> Reply from smurfted
>
> Sorry for dragging this up but, as 2014 comes to an end does anyone have any ideas on how to unpack this file type?

bumping to say that ida can open the xbox xbe format ([https://www.hex-rays.com/products/ida/f ... mats.shtml](https://www.hex-rays.com/products/ida/file_formats.shtml))

also, the global "CAFF" containers only contain a single file and the 'gpu' segments aren't always compressed (textures, and font are not)

finally, the "text" segments are very similar to rare's other xbox game (grabbed by the ghoulies)

edit

tiny progress on the caff files - [https://gist.github.com/x1nixmzeng/c55c248c384bf1c9df2a](https://gist.github.com/x1nixmzeng/c55c248c384bf1c9df2a)

the compressed data is chunked, but running aluigi's comscanner returns nothing useful in this case
## Post #9
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-01-15T03:01:35+00:00
- Post Title: Conker Live and Reloaded "default.rbm"

Has there been any further updates regarding this?
