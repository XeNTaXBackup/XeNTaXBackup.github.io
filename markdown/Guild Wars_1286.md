## Post #1
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-05-29T18:15:48+00:00
- Post Title: Guild Wars

any chance you could look into the GW .dat format? I'd post a link to one of the archives, but you only have one archive which is the entire install and mine is currently 200+ megs. but if youd like to dl the client (93 kb) ill lend one of the admins my acct to get a small archive
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-29T18:22:03+00:00
- Post Title: Guild Wars

Use the Filecutter instead (click link in my signature)
## Post #3
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-05-30T04:47:38+00:00
- Post Title: Guild Wars

i couldnt get that to work for some reason, but I found out you don't need an acct to download the client, it can be done at the GW home page. 

[http://www.guildwars.com/downloads/GwSetup.zip](http://www.guildwars.com/downloads/GwSetup.zip)
## Post #4
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-06-02T01:25:27+00:00
- Post Title: Guild Wars

any progress on this? me and a few friends have been attempting some work on it, heres the thread with our info

[http://undev.org/forum_viewtopic.php?4.58](http://undev.org/forum_viewtopic.php?4.58)

hope we can work together to crack it!
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-02T09:02:19+00:00
- Post Title: Guild Wars

Ok, check out my preliminary specs at the Work In Progress page of Guild Wars at the XeNTaX WIKI. 

[http://wiki.xentax.com/index.php/WIP_Guild_Wars](http://wiki.xentax.com/index.php/WIP_Guild_Wars)

Please let your gang join up and help figure it out there!
## Post #6
- Username: AnonAMouse
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 15, 2007 8:30 pm
- Post datetime: 2007-01-15T12:37:29+00:00
- Post Title: Guild Wars

decompression easy, extraction harder.
gw.exe -image to download the decompressed gw.dat

I also refer you to my post on this thread: [viewtopic.php?t=1645&postdays=0&postord ... s&start=15](http://forum.xentax.com/viewtopic.php?t=1645&postdays=0&postorder=asc&highlight=guild+wars&start=15)
Which has a similar discussion.
## Post #7
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2007-03-27T09:11:04+00:00
- Post Title: Guild Wars

Try extracting only riff, then open in a wave editor like cooleditpro. I found  this way with FACTIONS preorder client, using extractor 2.4. I found a good 22050 wave file between noise when opening a riff, then just edited out, saved as pcm wave. 

LMK
## Post #8
- Username: AnonAMouse
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 15, 2007 8:30 pm
- Post datetime: 2007-09-07T22:34:10+00:00
- Post Title: Guild Wars

Found a very interesting zip file here: [ftp://ftp.plaync.com/Source/XDeltaWithNCsoftMods1.zip](ftp://ftp.plaync.com/Source/XDeltaWithNCsoftMods1.zip)
This seems to contain information on all of NCSoft compression techniques, hope this is useful to some people.

Edit:-
Some of the sub info points here: [http://www.ietf.org/rfc/rfc1951.txt](http://www.ietf.org/rfc/rfc1951.txt)
And that in turn points here: [ftp://ftp.uu.net/graphics/png/documents ... index.html](ftp://ftp.uu.net/graphics/png/documents/zlib/zdoc-index.html)

I did notice this however:

> RFC 1951: DEFLATE 1.3 specification
>
> Abstract: This specification defines a lossless compressed data format that compresses data using a combination of the LZ77 algorithm and Huffman coding, with efficiency comparable to the best currently available general-purpose compression methods. The data can be produced or consumed, even for an arbitrarily long sequentially presented input data stream, using only an a priori bounded amount of intermediate storage. The format can be implemented readily in a manner not covered by patents.
So it may possibly be Deflate AKA a combination of the LZ77 algorithm and Huffman coding.

Just trying my best to help.
## Post #9
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2007-09-10T13:15:52+00:00
- Post Title: Guild Wars

I did take a (quick) look at it, but it seems the changes NCsoft made to the source code are rather trivial and have nothing to do with GW.DAT compression (it still is only an XDelta implementation, after all).
