## Post #1
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2017-02-08T22:44:13+00:00
- Post Title: Insert same bytes to multiple addresses

Hi

I need to insert same bytes automatically to 240 different addresses from a file but I have not found any hex editor able to do that.

Tried with Hex Editor Neo and Save/Load Selection and Copy/Paste commands but that didn't work properly (bytes get shifted).

How can I do that?

Thanks for your help!
## Post #2
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2017-02-09T09:32:54+00:00
- Post Title: Insert same bytes to multiple addresses

Removed.
## Post #3
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2017-02-09T12:40:54+00:00
- Post Title: Insert same bytes to multiple addresses

Thanks but I don't want to replace bytes I just want to insert (not overwrite) the same bytes to many different addresses from the file. How can I do that?
## Post #4
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2017-02-11T03:27:01+00:00
- Post Title: Insert same bytes to multiple addresses

Removed.
## Post #5
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2017-02-11T08:02:59+00:00
- Post Title: Insert same bytes to multiple addresses

Sorry for my horrible English. You are right, inserting bytes shifts other data (there is no problem with that) but I want the bytes to insert remain in their right addresses (relative addresses instead of absolute addresses?)

If I paste all of them at once with Hex Editor Neo only first one remains in the right address but the other bytes to insert end up in wrong addresses because one shifts the other.

I guess I need something to insert them automatically but one by one (not at once).
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-04-25T23:18:48+00:00
- Post Title: Insert same bytes to multiple addresses

the only way to do this woud be to override the bytes when you copy your replacements.

have you tried the INSERT key before pasting?
## Post #7
- Username: RamiroCruzo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 07, 2015 11:38 pm
- Post datetime: 2017-04-29T09:53:26+00:00
- Post Title: Insert same bytes to multiple addresses

In my view, you can do it in two ways:
1. Split the file according to your offset list, and while merging them add those bytes.
2. Maintain track of how many times you've added those bytes and add it into your offset while you go to next offset.
