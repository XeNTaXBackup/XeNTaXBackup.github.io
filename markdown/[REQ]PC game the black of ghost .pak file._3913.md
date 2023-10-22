## Post #1
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2009-12-01T02:25:01+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

This is my company new product for pc game.
Some body knows how to unpack those files?
I uploaded some pak files, hope some body can try it.

[http://www.yourfilelink.com/get.php?fid=518714](http://www.yourfilelink.com/get.php?fid=518714)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-01T08:41:31+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

What do you mean, your company's new product for PC?
## Post #3
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-01T18:13:26+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

> Reply from dongdong
>
> This is my company new product for pc game.

I'm not the expert in english over here but I think that you were meaning: "This is my company's new product for pc gamers"

Aside from that, what is the purpose of the topic? Just by curiosity. Maybe knowing if it's going to be "hacked" soon?   

I wouldn't expend too much time on those kind of protections but in a better exclusive product. For example, requesting a serial to play online. Or special extra content for original game clients. At some time any protection has to "unprotect" the resources so they make sense for the game engine (can load images, sounds etc).

Anyway I'll take a fast look over that, again just by curiosity.
## Post #4
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-01T18:30:15+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

Didn't recognise anything neither at beginning or end of the file (such as file size, file number, etc fields)

However there are some uncoded strings at the beggining which may reveal some info for someone. As I said, it's a matter of time, you can make this almost imposible to figure out but then it would be easier to find that code on the .exe and reverse it.

Maybe if you combine this + the latest themida release which is pretty good at encoding any not NET .exe...

That should make things harsh
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-01T18:34:08+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

Yeah, people take a look at the executable and when they want to figure out the format. It's no use to protect them. I agree that games should be made so gamers can mod it themselves, that will ensure good sales and a long duration of success.

About the file, at the back is clearly a repeating pattern, right after the "1A0a.vertices" string. The pattern is 12 bytes long that are encrypted maybe,. Note the repeating 5B AB and further on the 86. This could indicate a XOR method of encryption with some algorithm.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-01T18:41:35+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

Also, the files seem in there without compression. I've been able to find a lot of different file types, including DDS files:



m copy.jpg (25.09 KiB) Viewed 245 times
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-01T18:58:58+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

yeah an ugly file format (today it's a bad day, all the requests were about absurd formats), the data is uncompressed but seems that the filenames are compressed.
anyway this game doesn't exist (yet?) so be happy :)
## Post #8
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-01T19:10:49+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

Great job! Yeah I've just noticed the 5BAB pattern in there. Althought, hyperripper wasn't able to find any uncompressed file, maybe because it doesn't search dds etc

Now, what's that image supposed to be, dongdong?  

> Reply from aluigi
>
> (today it's a bad day, all the requests were about absurd formats)
I guessed that from "latest topics" view even without looking at the formats haha Just didn't hear in my live about those games, it's a luck that someones takes the time to answer those posts man!
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-01T20:01:00+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

Well, when I see a post with 0 replies I always take a look, to help out.
## Post #10
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2009-12-02T02:31:51+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

I'm sorry.My english is poor.
I mean, can you parse out all the file ?
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-02T06:51:07+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

Ok, dongdong, which game is this PAK file from?
## Post #12
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2009-12-04T10:44:45+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

> Reply from Mr.Mouse
>
> Ok, dongdong, which game is this PAK file from?
The game's name is black of ghost, but it is in the testing phase.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-04T11:08:06+00:00
- Post Title: [REQ]PC game the black of ghost .pak file.

Is this your companies' game? And you wish to test if it can be reverse engineered?
