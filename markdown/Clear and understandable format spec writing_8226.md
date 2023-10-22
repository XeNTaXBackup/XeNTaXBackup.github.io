## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T18:24:19+00:00
- Post Title: Clear and understandable format spec writing

Graphics, audio, images, 3D, etc.
There doesn't seem to be a set standard for spec-writing. 

Some of it can be very technical, or very verbose.
Some people are really comfortable with technical specs, while others probably not so much.

Any ideas on making easy-to-understand yet precise format specs?

There's only a finite set of types to work with. Signed values?

Structs would make sense. Defined in-line? Separately?

Array syntax? C-like syntax? Even with an array of structs?

```

Vertex[20] vertices...

```


What about strings? Null-terminated strings? Strings with specific encodings? I would like an easy way to say "this is a null-terminated string".
I've been used char_/0 lol

What are some good or bad specs you've seen?
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2012-02-08T20:07:04+00:00
- Post Title: Clear and understandable format spec writing

I just use 010 editor binary templates.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-08T20:16:38+00:00
- Post Title: Clear and understandable format spec writing

I love reading specifications. Html5, c, c+ +, ecmascript, opengl, sql, certain rfcs... Fun shit. By far the most ugly and most difficult I've read is the sql spec. It is flat out nasty. Every paragraph is filled with two and three letter abbreviations. By far the easiest one to read is html and css specs. Most rfcs are pretty bland too and are difficult to follow because they say stuff like refer to some other rfc for this, another rfc for that... For example the zlib one is pretty bad but the nntp protocol one is very easy.
## Post #4
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-02-10T06:44:06+00:00
- Post Title: Clear and understandable format spec writing

The wiki uses a reasonably straightforward method of laying out specs, though said method was originally designed with archive formats in mind and therefore may not be quite developed enough for all image, audio, model, etc. formats.
