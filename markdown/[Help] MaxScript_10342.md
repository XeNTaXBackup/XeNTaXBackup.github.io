## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-16T11:23:29+00:00
- Post Title: [Help] MaxScript

Hello everyone!
I need help with maxscript, how could I implement several loops in my script? I could successfully import files with one mesh, but how could I parse file with couple of meshes through maxscript?
## Post #2
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-04-18T04:29:51+00:00
- Post Title: [Help] MaxScript

You would use a "for" or "while" loop, but of course you'll need to understand the basic structure of your file.
With a while loop you'll need to keep it check with a loop condition that will return false at some point or else you'll get stuck in an infinite loop. There's a bunch of Maxscripts on this site you can look at as examples. One example is chrrox's Star Ocean 4 importer: [viewtopic.php?f=16&t=6860&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=6860&start=15)

Also, if you haven't seen them, these are some good videos:[http://vimeo.com/album/1514565](http://vimeo.com/album/1514565)
"Loops and Loop Control" is on the second page.

Actually, even better. Check out mariokart64n's videos. [viewtopic.php?f=16&t=5644](http://forum.xentax.com/viewtopic.php?f=16&t=5644)
That's how I got started.
