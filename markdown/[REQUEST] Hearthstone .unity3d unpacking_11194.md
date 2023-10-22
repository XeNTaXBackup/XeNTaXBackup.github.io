## Post #1
- Username: bekir007
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 02, 2012 8:52 pm
- Post datetime: 2014-02-06T19:20:59+00:00
- Post Title: [REQUEST] Hearthstone .unity3d unpacking

Can you help me? How can i extract .unity3d files?

<sample files removed due forum rules violation>
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-06T20:33:35+00:00
- Post Title: [REQUEST] Hearthstone .unity3d unpacking

You can use aluigi's script to unpack .unity3d files [http://aluigi.altervista.org/papers/bms ... player.bms](http://aluigi.altervista.org/papers/bms/unity3d_webplayer.bms)
and then my Unity Importer to load them in max [viewtopic.php?f=16&t=11095](http://forum.xentax.com/viewtopic.php?f=16&t=11095)
## Post #3
- Username: bekir007
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 02, 2012 8:52 pm
- Post datetime: 2014-02-06T20:40:13+00:00
- Post Title: [REQUEST] Hearthstone .unity3d unpacking

> Reply from Chipicao
>
> You can use aluigi's script to unpack .unity3d files http://aluigi.altervista.org/papers/bms ... player.bms
and then my Unity Importer to load them in max viewtopic.php?f=16&t=11095

I used but did not work
## Post #4
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-06T21:07:08+00:00
- Post Title: [REQUEST] Hearthstone .unity3d unpacking

Ah, sorry, you need this modified script by barracuda
[viewtopic.php?p=86592#p86592](http://forum.xentax.com/viewtopic.php?p=86592#p86592)
## Post #5
- Username: bekir007
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 02, 2012 8:52 pm
- Post datetime: 2014-02-06T21:18:27+00:00
- Post Title: [REQUEST] Hearthstone .unity3d unpacking

> Reply from Chipicao
>
> Ah, sorry, you need this modified script by barracuda
viewtopic.php?p=86592#p86592

I'm sorry, i also tried it :/
## Post #6
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-06T21:59:47+00:00
- Post Title: [REQUEST] Hearthstone .unity3d unpacking

Well it works for me...

[](http://www.imagebam.com/image/3bd778306342864)
## Post #7
- Username: bekir007
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 02, 2012 8:52 pm
- Post datetime: 2014-02-06T22:11:03+00:00
- Post Title: [REQUEST] Hearthstone .unity3d unpacking

> Reply from Chipicao
>
> Well it works for me...

Does not work properly. Doesn't extract. Converting all files to CAB-<filename>
## Post #8
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-06T22:18:17+00:00
- Post Title: [REQUEST] Hearthstone .unity3d unpacking

> Reply from bekir007
>
> Does not work properly. Doesn't extract. Converting all files to CAB-<filename>
No, it doesn't convert the file, it extracts the CAB file from the unity3d archive.

CAB files are Custom Asset Bundles, similar to .asset files, and they can be imported directly with my script. That's how you're supposed to do it.
## Post #9
- Username: jb55
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 20, 2010 11:23 pm
- Post datetime: 2014-07-14T17:59:47+00:00
- Post Title: [REQUEST] Hearthstone .unity3d unpacking

I was too lazy to build a full parser and all I wanted was the card xml data so I put together this little program.

I almost got away with just using sed and grep but I ended up giving up.

Here it is if anyone else is interested:

[https://github.com/jb55/hearthstone-cardxml](https://github.com/jb55/hearthstone-cardxml)
