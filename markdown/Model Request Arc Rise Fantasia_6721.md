## Post #1
- Username: TruePhil
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 02, 2011 2:32 pm
- Post datetime: 2011-06-04T00:16:41+00:00
- Post Title: Model Request: Arc Rise Fantasia

So I've been searching for the .mdl0 files for the cameo battle characters for a while (Vanessa, Lucia and Saki) and for the life of me I cannot find them in the iso.   Would anyone be kind enough to either provide me with the models or at least detailed instructions for how and where to get them in the iso?  Please any help would be very much appreciated as I have looked tirelessly to no avail. If the info helps, you fight them in the final fight of the Battle Arena.  I can provide pictures if need be or you could check out the cameo battle on Youtube to know what you're looking for.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-04T02:03:11+00:00
- Post Title: Model Request: Arc Rise Fantasia

The models would most likely be stored in one of the data files rather than being available out in the open for you to grab.

It'd probably be possible if you provided some data files.
I don't think pictures or videos would help though.

Speaking of arc rise fantasia..

[viewtopic.php?f=10&t=6711](http://forum.xentax.com/viewtopic.php?f=10&t=6711)
[viewtopic.php?t=4893&f=18](http://forum.xentax.com/viewtopic.php?t=4893&f=18)

Don't know if that's what you're talking about.

This may also be relevant
[viewtopic.php?f=16&t=3636](http://forum.xentax.com/viewtopic.php?f=16&t=3636)
## Post #3
- Username: daisuki
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 03, 2011 1:12 pm
- Post datetime: 2011-06-04T02:17:15+00:00
- Post Title: Model Request: Arc Rise Fantasia

[viewtopic.php?f=16&t=3636&start=45](http://forum.xentax.com/viewtopic.php?f=16&t=3636&start=45)

You can find the answer in this post.
## Post #4
- Username: TruePhil
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 02, 2011 2:32 pm
- Post datetime: 2011-06-04T03:11:55+00:00
- Post Title: Model Request: Arc Rise Fantasia

Here's the problem with that thread:  I've unpackaged the battle_enemy.vld and all that's in there is a crap ton of animation data. >_<
I was very excited that I finally cracked it only to find no character models whatsoever.  Does anyone know specifically where they are located?  I have the tools necessary to unpack them I just cannot find them at all. 

Edit:  I used tools I got from a user here to decompress the files btw.  Also after the file was decompressed I used a Python based brres separator to extract all mdl0 files in the decompressed file, however if there is further compression that could really screw things up I guess?  Anyone have any suggestions? Also as I've stated it'd be heaven if someone already has the models I'm looking for...   

Here is the file the topic you posted said they are:  [http://www.4shared.com/file/tIDNPBCX/btl_enemy.html](http://www.4shared.com/file/tIDNPBCX/btl_enemy.html)
## Post #5
- Username: daisuki
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 03, 2011 1:12 pm
- Post datetime: 2011-06-04T04:20:52+00:00
- Post Title: Model Request: Arc Rise Fantasia

[viewtopic.php?f=16&t=3636&start=45](http://forum.xentax.com/viewtopic.php?f=16&t=3636&start=45)

Darkfox already wrote the perfect answer.
## Post #6
- Username: TruePhil
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 02, 2011 2:32 pm
- Post datetime: 2011-06-04T04:53:21+00:00
- Post Title: Model Request: Arc Rise Fantasia

So you have the models?  Can you please send them to me?   
I'd be very much obliged.

Here's what I've done tho.  If I use LZ77ex on the Btl_enemy.vld file it only decompresses a small portion or the file (as in the very beginning).  Do I have to manually go in and hex something?  And if so what?  I'm sorry I'm such a noob at this, however you have to start somewhere right? Anyways someone here gave me decompression tools and it gave me a btl_enemy.vol from it.  I used the brres separator to get the files out, however I think something was lost in translation as I didn't find any character models whatsoever.  Just now I ran the .vol file it gave me through LZ77ex and all it gave me was a small portion yet again.  I can follow step by step instructions if someone would be willing to help me out.  Or the simplest thing would be to just send me the file either through email or post it on mediafire or something.
## Post #7
- Username: TruePhil
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 02, 2011 2:32 pm
- Post datetime: 2011-06-04T05:41:02+00:00
- Post Title: Model Request: Arc Rise Fantasia

Just to update I've gone into a hex editor and started at the BTEM listing before Vanessa's name in the text section of the hex and copied everything up until right before the next BTEM.  What should I do now?  Should I save the file as a certain file type?  What program should I run the file through to get her model?


Edit:  New Development: [http://www.4shared.com/file/BMWnvobC/opt_lum010.html](http://www.4shared.com/file/BMWnvobC/opt_lum010.html)

I'm positive this is the file her model is in.  I extracted another model via having their file that I edited in hex, just like this one, however this one is further encrypted and I don't know how to crack it.  The other was simple as I just ran QuickBMS with the Arc Rise script and it extracted everything, however this one, as I said is even further encrypted.  Can someone help me out here?  I'm sooooo close.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-04T21:55:48+00:00
- Post Title: Model Request: Arc Rise Fantasia

You will never receive models on this site, as that isn't the point.
Anyways if going through all the threads didn't help then I guess you're stuck
## Post #9
- Username: TruePhil
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 02, 2011 2:32 pm
- Post datetime: 2011-06-05T04:23:51+00:00
- Post Title: Model Request: Arc Rise Fantasia

Well not receiving the actual .mdl0 is fine, however if someone could check out the hex file I've provided and give me some instructions that would be enough.
