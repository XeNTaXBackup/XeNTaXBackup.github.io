## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-02-14T12:57:55+00:00
- Post Title: GMO from Otomedius Excellent xbox360

I really hope someone can make a converter for this.
[viewtopic.php?f=29&t=7760](http://forum.xentax.com/viewtopic.php?f=29&t=7760)
At a glance, GXXM0124 and GXXM0301 seem to have similar.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-14T19:28:10+00:00
- Post Title: GMO from Otomedius Excellent xbox360

last time i looked at this, a few months ago, i thought it was impossible; i forget why.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T07:21:26+00:00
- Post Title: GMO from Otomedius Excellent xbox360

Lol ya it looks easy doesn't it. Header, stuff, (mesh header + vert buff + index buff)
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-15T14:20:23+00:00
- Post Title: GMO from Otomedius Excellent xbox360

It is? Maybe my rip was bad.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T17:56:20+00:00
- Post Title: GMO from Otomedius Excellent xbox360

Ok I have the general structure out (96 byte vertex buffer followed by index buffer).
The only problem I'm having right now from parsing it completely is that there are a couple extra bytes after the index buffer, sometimes, and I'm not sure which flags control it.



Hopefully this generates some interest.

[http://db.tt/x30ehe73](http://db.tt/x30ehe73)

Take a look at the end of the parse_mesh method and you'll see me doing some silly hacking around.
This is flawed and the condition for skipping does not actually work in general (there are cases where some of those unknown integers meet the requirements).

The mesh number also does not appear in sequence so I couldn't check for that either.
If you cut out each mesh struct and compare them, you'll see that right before the 2 sets of matrices after the materials, there are some integers that change. I don't know what these integers represent but they might have something to do with it.
