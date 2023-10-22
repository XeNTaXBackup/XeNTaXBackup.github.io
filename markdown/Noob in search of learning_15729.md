## Post #1
- Username: U2LN
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 11, 2015 1:53 pm
- Post datetime: 2017-01-14T04:47:21+00:00
- Post Title: Noob in search of learning

[NOOB ALERT]

I'm really sorry if this is the wrong place to post this.
I'm interested in learning how to crack model formats and stuff, but don't know where to learn the stuff. Especially interested in learning to write importer scripts for blender. Can someone who knows this stuff point me in the right direction?
## Post #2
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2017-01-19T16:17:44+00:00
- Post Title: Noob in search of learning

You need to be knowledgeable on:

Programming
Binary representation of values (int, float, etc)
Common data structures (arrays, lists, pointers)
How modern graphics APIs work (or if you're working with older consoles, their specific graphics API), what kind of inputs their functions require, as that is what will be stored in model formats
Experience. You simply need a decent amount of experience to be able to make educated guesses on where structures are in a file, and how the various structures are related to each other.

Google is your friend here. Be sure to also look for formats that already have a full format documentation, and look at them with a hex editor. Maybe write an importer for them.
As for blender in specific, the idea is to look at their api and find out which values it needs to build meshes, a skeleton, etc and then retrieve those values from the model format you're working with (either directly or after some pre-processing).
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-19T22:09:30+00:00
- Post Title: Noob in search of learning

[http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF)
[http://wiki.xentax.com/index.php/Blender_Import_Guide](http://wiki.xentax.com/index.php/Blender_Import_Guide)
## Post #4
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2017-01-20T22:39:20+00:00
- Post Title: Noob in search of learning

[https://www.youtube.com/playlist?list=P ... GrVNJ2kS2f](https://www.youtube.com/playlist?list=PLP26ZYnLb5EVqqBHDgltL6oGrVNJ2kS2f)
This is a list of realtime reversing tutorials by our awesome admin Mr. Mouse. I definetely recommend checking them out.
