## Post #1
- Username: SolidSonicTH
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 11, 2016 6:34 am
- Post datetime: 2016-04-10T22:58:37+00:00
- Post Title: Modding the NFS Most Wanted 2012 PC soundtrack...

So I found this ealayer3 tool that was created here and it did a great job decoding the NFS MW 2012 .SPS files but now I want to replace those with my own music.

When I tried to encode the music, it encodes it as an ".EALAYER3" file and trying to change it into a .SPS format file to replace an existing song on the soundtrack just crashes the game.

I tried encoding with both options (--single-block and --header-b) but neither one produces a usable file. Decoding a file using the -v option shows that it looks like the game's music is encoded with the header B flag but that doesn't change anything when I try to encode it back as such.

Am I missing something here? I found a GameFAQs post from back in the day that led me here but I don't feel like they went deep enough with the issue, just leaving it at "that's how it is". Is the song I'm using encoded improperly to turn it into a compatible .SPS file?
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-11T06:14:39+00:00
- Post Title: Modding the NFS Most Wanted 2012 PC soundtrack...

Can you upload .SPS example? They are probably 6-channel, and I don't think ealayer3 is capable of encoding such files.
## Post #3
- Username: SolidSonicTH
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 11, 2016 6:34 am
- Post datetime: 2016-04-11T19:12:48+00:00
- Post Title: Modding the NFS Most Wanted 2012 PC soundtrack...

Sure. Thanks for replying.

I'll try to do it when I get home (at the office right now).
## Post #4
- Username: SolidSonicTH
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 11, 2016 6:34 am
- Post datetime: 2016-04-12T00:53:21+00:00
- Post Title: Modding the NFS Most Wanted 2012 PC soundtrack...

Here, [this is a sample .SPS song file from the game](https://drive.google.com/file/d/0BzH_zXs9SuBlamhCUWl1MF9RaW8/view?usp=sharing). Hope it can be useful.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-12T06:58:46+00:00
- Post Title: Modding the NFS Most Wanted 2012 PC soundtrack...

Well, thats normal stereo track in header-b format. Let me see what I can do here.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-12T10:11:27+00:00
- Post Title: Modding the NFS Most Wanted 2012 PC soundtrack...

Looks like the file encoded by ealayer3 tool is somehow different from what is expected by the game. I see at least one value that it doesn't put there. However, I've set it, and it still doesn't work. So it must be more complex problem. I don't have a solution for this now.
## Post #7
- Username: SolidSonicTH
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 11, 2016 6:34 am
- Post datetime: 2016-04-12T12:23:51+00:00
- Post Title: Modding the NFS Most Wanted 2012 PC soundtrack...

Fair enough. It's a more complete explanation for the failure than I had seen up to now.
