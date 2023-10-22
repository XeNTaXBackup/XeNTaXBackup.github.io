## Post #1
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-07-09T17:24:57+00:00
- Post Title: rise of flight mgm format

anyone have the game? if not, i can provide a sample mgm file.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-09T19:06:05+00:00
- Post Title: rise of flight mgm format

PM me some samples.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-10T02:45:47+00:00
- Post Title: rise of flight mgm format

The mesh is a really simple format. Vertex buffer and index buffer at the bottom, materials at the top.

It looks like it was serialized in some format but it shouldn't be hard to figure out.
## Post #4
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-07-10T05:09:51+00:00
- Post Title: rise of flight mgm format

do you know a way to open or extract it into editable format?
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-10T06:58:22+00:00
- Post Title: rise of flight mgm format

No, but it's not hard to write one.
## Post #6
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-07-10T15:50:18+00:00
- Post Title: rise of flight mgm format

could you write import export tool for blender?
## Post #7
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-07-17T07:57:09+00:00
- Post Title: rise of flight mgm format

what tools are needed?
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-19T04:19:30+00:00
- Post Title: rise of flight mgm format

Didn't look at the format too long but it's kind of annoying.

There are 4 integers somewhere in the mesh header that gives the vert count, face count, vert offset, and face offset, but first you have to figure out how they decided to serialize the format with their whole "class model" "struct model" etc whatever stuff.

Someone can write a blender importer if they want. I'd probably go for noesis cause it seems easier to use than having to figure out all of blender's different functions for manually creating all of the objects.

Anyways I've hardcoded some offsets for the infantry mgm you sent.
All that really needs to be done is to fill out the rest of the parse_file method properly...

[https://www.dropbox.com/sh/7stlpd4qvkq3 ... ght_mgm.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/mPrKYLtRAs/fmt_RiseOfFlight_mgm.py)
## Post #9
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-07-19T05:00:37+00:00
- Post Title: rise of flight mgm format

thanks for that. they use 3dsmax 8 originally, would it somehow be easier to write an importer for that?

i'm looking at the file, but don't really understand "codes" and such. thanks for the notations thought, they could help me piece something together i hop.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-19T05:10:41+00:00
- Post Title: rise of flight mgm format

Here, maybe you can help me with the format.
You don't need to write an importer or understand how to write code.
Just figure out the pattern for the files. You will need to be able to interpret hex data with the help of a hex editor (maybe), and some logical thinking and creative puzzle-solving.

There are a bunch of strings everywhere, but the important parts are some specific bytes that seem to indicate what kind of data follows.



Those are some suspicious bytes. 0x31, 0x32, 0x33.
There are some more, like 0x34 and 0x35. And that 0x30 at the very beginning.

Obviously, if it's part of a string or float, then it's nothing special, but if it just stands out...
I highlighted them because they don't make sense if you interpret them as numbers.

It's not important to know what they mean (though it would help, and if you investigate them long enough you might figure out what they mean).
I just need to know what to do when I see one.

Of course, they might not mean anything and you're supposed to look at what struct you're working with (model, node, chunk...)
## Post #11
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-07-19T05:41:33+00:00
- Post Title: rise of flight mgm format

i'm extremely confused by all of that. i noticed some patterns but they're probably basic things you know already. what do you mean by suspicious? what am i supposed to look for? i see associations of symbols with symbols. some numbers with alphabets, etc, some with numbers.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-19T05:54:01+00:00
- Post Title: rise of flight mgm format

You have to look at both the hex and what it represents. Which means you have to have some idea about different types in computing, and how they are stored (eg: 4-byte integers, 4-byte floats, etc)

The beginning of the file is a 4-byte integer representing the length of a string (0x12, or 18), followed by a string with that given length ("class model::Model", 18 characters).



Then you read an integer 0, followed by an integer 1, and then there's an odd 0x30 byte.
After that you read another integer which is the length of a string (0x12 again), followed by a string with that length ("struct model::Node").

It should be obvious why I isolate that 0x30, because looking ahead you can see that there's a string, so doing some simple process of elimination with some assumptions from earlier, you can conclude that "12 00 00 00" is the length of the string, and not supposed to be read as "30 12 00 00"

Most decent hex editors  automatically interpret the hex data for you so you just have to look at what it might be. Here's a screenshot from 010 editor:



The highlighted bytes don't mean much to me, but the inspector on the left tells me that it might be a float. and if you look ahead you'll see that there's a bunch of floats.

Having knowledge of what kind of data might be stored in the file gives you a better idea of what you might be looking at, but even if you don't know much about the file, if you compare many different files of the same format you will probably find enough similarities to determine that you've found a solid pattern.

Whenever you see an integer, you should be paying attention to things like how many times a particular pattern repeats itself. It could be the length of a string, which is easy enough to figure out by just counting how many characters you read and see if they match up.

It might be the number of strings, so if you see an integer, followed by 3 strings, then that integer is a count of how many instances of some data.

In the end, trying to reverse a file purely from looking at hex is trial and error, process of elimination, and pattern matching.

To test your findings, just grab another file and apply the pattern from beginning to end. If it works out then you probably found something.

I can guess that most of the files start with an integer 0x12, followed by the string "class model::Model". So at least you know one piece of the puzzle.
## Post #13
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-07-25T02:48:10+00:00
- Post Title: rise of flight mgm format

could a flawless exporter for this format be made? as in an original file that can be used by the game.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-25T03:45:14+00:00
- Post Title: rise of flight mgm format

That comes after the format's been figured out.
