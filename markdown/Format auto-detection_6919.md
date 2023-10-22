## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-05T13:16:08+00:00
- Post Title: Format auto-detection

Initially asked this in [noesis thread](http://forum.xentax.com/viewtopic.php?p=56159#p56159), but figured it should be separated into its own topic.

So I'm looking for ideas on some good ways to do format auto-detection.
It's mainly for 3D formats, but I suppose a generic discussion on auto-detection would also generate ideas.

Basically I've written a small 3D batch converter in python, sort of like karpati's 3D Object Converter in concept, except the only real purpose is so that I don't have to write export functions everytime I try to figure out another format. So ya, for convenience and not really for use.

It currently only supports 12 different formats (most of them are documented), and have found that trying to detect the format is getting pretty difficult.

Some formats use the same file extension as another format
Some formats use the same header as another format
Some formats don't even have a header, and may share the same extension as another header-less format!

There are probably more issues that can arise during the detection step which I have not encountered or thought of.

I've recently switched from a hardcoded design (just lots of cases) to a plugin design (where the plugin itself will tell the engine what it needs to know about the format), and even that can get a little messy with the above 3 conditions.

I'm currently checking two things:

1. headers, and then
2. extension

If neither are recognized, then I just say I couldn't recognize it and if it's supported then manually type in the input format lol

But the header itself can also be a headache.

-some formats have a 3-byte Id string
-some formats have 4-byte string
-some formats have 5-byte string
-some formats have ...

and of course some don't have any.

Well, most of the ones I've come across  (that have the magic word in the first place) tend to have between 3 and 7, more commonly 3 or 4, so I can just take the first 10 bytes or something and then start reading substrings and checking if the format is supported. Or at least try.

Anyone have ideas?

Dinoguy mentioned checking the folder that it is being loaded from, which is an interesting idea. I've been focused on individual files themselves so haven't really considered the big picture.

Some things I've thought of

-check header.
-If no header, check extension

-check both header AND extension and make sure both match the format

I would try brute forcing it, but it might successfully be parsed and still be wrong.
## Post #2
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-07-05T20:01:13+00:00
- Post Title: Format auto-detection

There is also the [TrID](http://mark0.net/soft-trid-e.html) method of simply looking for patterns that are likely to be unique to the format in question. TrID uses a very naive approach of only looking for static patterns, but my guess is that you could actually get quite sophisticated with this, if you have a deep enough understanding of a format.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-05T22:15:51+00:00
- Post Title: Format auto-detection

> if you have a deep enough understanding of a format.

I suppose one could consider trying to read specific bytes at particular offsets sequentially and check what the value is and use some additional definitions that will be specified by the format.

So for a header-less file with no extension, one might read an int and check whether it makes sense or not (ie: 35489122 probably won't for most formats), then skip that many values and then read a float and check whether it makes sense or not such that anything beyond a particular interval would probably be "unrealistic" (ie: 2.34e-23).

For very complex formats, it'd probably quickly realize that it's not that format and move on, whereas ironically for simple formats this might take a little longer!

Of course, this would be after filtering the list so you don't have to check too much.

Definitely makes use of the knowledge of the format itself.
