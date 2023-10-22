## Post #1
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2014-09-05T23:13:07+00:00
- Post Title: Can someone please look at this file?

Hi,

I have a mod for Dirt 3 that is called ACAT Online (All Cars All Tracks Online). It modifies the computer's memory after the game is running to allow the game host to select any car type to run on any track type (Cat n Mouse can use trucks as the Cats, etc., or you can use Gymkhana cars in Rally Cross, etc.)

It's not a "cheat" as everyone on the host's server can use the same car class as the host. It makes the game the way it should have been made by Codemasters (as they originally programmed Dirt 2 to actually allow this).

I am a bit paranoid about running the program since it changes memory while the game is online and I don't know if it's doing anything malicious to the computer.

I was wondering if anyone out there with the knowledge to look at this file can tell me if it's doing anything other than modding the actual game?

The file is too big to attach. It can be downloaded here: [http://www.mediafire.com/download/a1h55 ... ck+2.1.EXE](http://www.mediafire.com/download/a1h55m1s2c56but/BandiHack+2.1.EXE)

I would really appreciate any help in this matter.
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-06T20:53:17+00:00
- Post Title: Can someone please look at this file?

The outer EXE extracts a decompressor for the compressed trainer. The trainer is compressed with possibly custom Zlib. That's all I've got right now.
## Post #3
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2014-09-08T12:27:37+00:00
- Post Title: Can someone please look at this file?

> Reply from GMMan
>
> The outer EXE extracts a decompressor for the compressed trainer. The trainer is compressed with possibly custom Zlib. That's all I've got right now.

OK, thank you.

Is there any way to see what this trainer is actually doing in memory?
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-14T16:22:56+00:00
- Post Title: Can someone please look at this file?

Step through the decompression code with a debugger.
