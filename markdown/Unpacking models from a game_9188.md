## Post #1
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-01T19:38:15+00:00
- Post Title: Unpacking models from a game?

Ok, so I hope I put this in the right place. Hi! I'm new here, I just wanted to ask a question.
I want to unpack models from a certain game. The game? Tim Burton's The Nightmare Before Christmas: Oogie's Revenge.
However, I think I'll need a lot of help before I can write the program to dump them with.
My question? How do I write this program? How do I define where the models are? Where are the models in the first place?

I just want some of these questions answered.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-01T20:10:01+00:00
- Post Title: Unpacking models from a game?

That depends whether the data is packed into an archive or not.
If they're not packed, then it's a matter of going through the folders and looking for them.

Now if everything is stored in an exe that gets a little complicated.
## Post #3
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-01T20:35:50+00:00
- Post Title: Unpacking models from a game?

> Reply from finale00
>
> That depends whether the data is packed into an archive or not.
If they're not packed, then it's a matter of going through the folders and looking for them.

Now if everything is stored in an exe that gets a little complicated.
Ok, so I'm pretty sure they are in an .IMG file on the disk. (PS2)
May I ask what now?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-01T20:39:26+00:00
- Post Title: Unpacking models from a game?

Open it in a hex editor and hope that you can see something that makes sense. Like filenames. And then hope that the data is not compressed or encrypted.

If you can't make any sense of it then you'd have to do some real work.
## Post #5
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-01T20:52:56+00:00
- Post Title: Unpacking models from a game?

I think I found them. The weren't in the .IMG file, they were in a .STM file. They seem to be called NAMEHERE.lz
May I ask what to do now?
## Post #6
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-01T21:13:20+00:00
- Post Title: Unpacking models from a game?

> Reply from finale00
>
> Open it in a hex editor and hope that you can see something that makes sense. Like filenames. And then hope that the data is not compressed or encrypted.

If you can't make any sense of it then you'd have to do some real work.This is what you need to do next.
## Post #7
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-01T21:14:03+00:00
- Post Title: Unpacking models from a game?

> Reply from C00L12345
>
> finale00 wrote:Open it in a hex editor and hope that you can see something that makes sense. Like filenames. And then hope that the data is not compressed or encrypted.

If you can't make any sense of it then you'd have to do some real work.This is what you need to do next.
I don't get what you mean...
## Post #8
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-01T21:15:50+00:00
- Post Title: Unpacking models from a game?

> Reply from Cyndaquil
>
> C00L12345 wrote:finale00 wrote:Open it in a hex editor and hope that you can see something that makes sense. Like filenames. And then hope that the data is not compressed or encrypted.

If you can't make any sense of it then you'd have to do some real work.This is what you need to do next.
I don't get what you mean...
Upload the file and PM me the link i will have a quick look, do not post it on here as you may get in trouble for it.
## Post #9
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-01T21:22:23+00:00
- Post Title: Unpacking models from a game?

> Reply from C00L12345
>
> Cyndaquil wrote:C00L12345 wrote:

If you can't make any sense of it then you'd have to do some real work.This is what you need to do next.
I don't get what you mean...
Upload the file and PM me the link i will have a quick look, do not post it on here as you may get in trouble for it.[/quote]
All right... I already looked through the file with HxD, but here you go.
I can't really do it, Mediafire says it's too large, so any other sites?
## Post #10
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-01T21:27:34+00:00
- Post Title: Unpacking models from a game?

There is no point uploading the full file, just screenshot the header in hex editor and the end of the file it may help.
## Post #11
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-01T21:32:24+00:00
- Post Title: Unpacking models from a game?

Ok, this isn't all of it. But it's a good snippet.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-01T23:23:55+00:00
- Post Title: Unpacking models from a game?

That's the file table, so you need to figure out the archive structure, write a script to unpack it (like a bms script).

lz might mean the files are compressed using some lz compression  variation (or they might just be a random extension)

The data will probably start at the end of the file table, and then you can probably determined whether it's compressed/encrypted or not.
## Post #13
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-02T00:06:27+00:00
- Post Title: Unpacking models from a game?

Is this it?
## Post #14
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-02T00:16:42+00:00
- Post Title: Unpacking models from a game?

> Reply from Cyndaquil
>
> Is this it?

Can you cut the first 25MB and upload?
## Post #15
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-02T00:26:55+00:00
- Post Title: Unpacking models from a game?

> Reply from C00L12345
>
> Cyndaquil wrote:Is this it?


Can you cut the first 25MB and upload?
Most likely.
Edit: Okay, so most of that is text for talking and singing. (Yes, they sing in this game) It's going to take a while to cut out. I'll have it up by tomorrow.
## Post #16
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2012-11-27T00:34:25+00:00
- Post Title: Re: Unpacking models from a game?

Sorry to intrude here but, did this archive structure ever get figured out? I'm looking through the game's files myself, mainly for the backing tracks for the songs. I also seriously hope they are streams and not in the complicated psf2 format.
## Post #17
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-12-01T19:02:59+00:00
- Post Title: Re: Unpacking models from a game?

> Reply from hoodlum47
>
> Sorry to intrude here but, did this archive structure ever get figured out? I'm looking through the game's files myself, mainly for the backing tracks for the songs. I also seriously hope they are streams and not in the complicated psf2 format.
Sorry, I haven't had the time to look through it, and I haven't heard back from COOL12345, and I have no ideas about the compression.
## Post #18
- Username: Cyndaquil
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-12-12T18:23:15+00:00
- Post Title: Re: Unpacking models from a game?

I have made the unpacker now after getting access to the file today.

.STM Unpacker v0.1
Author: Mr.Nightmare™
Language: C#
Requires: .Net Framework 4.5

I tested it on DATA.STM and it unpacks fine:



File Info

.STM (Archive)
.LZ   (Compressed Data) (LZ?)
.PMT (???)
.txt (Standard text file)

Once you unpack the .STM there will be tons of lz, stm files i'm unsure about the compression on the lz files though. However, whilst extracting some .STM files did error due to a size issue.

Click thanks if i helped!

Regards
[STM UNPACK v0.2.rar](https://xentaxbackup.github.io/file/6086_STM UNPACK v0.2.rar)
## Post #19
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-12-12T20:03:33+00:00
- Post Title: Re: Unpacking models from a game?

Just fixed the issue when unpacking sub .STM archives it should work fine now.
## Post #20
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-12-12T23:51:28+00:00
- Post Title: Re: Unpacking models from a game?

COOL12345, the unpacker is done when it crashes, right?
And thank you.
## Post #21
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-12-13T18:06:36+00:00
- Post Title: Re: Unpacking models from a game?

> Reply from Cyndaquil
>
> COOL12345, the unpacker is done when it crashes, right?
And thank you.
Unpacker should not crash, However the extracted .STM seems to have folders embedded into the file, I have not yet found a flag which defines folders or which files are going in them, it's really inconsistent but i don't know for now.
## Post #22
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-12-14T06:50:56+00:00
- Post Title: Re: Unpacking models from a game?

> Reply from C00L12345
>
> Cyndaquil wrote:COOL12345, the unpacker is done when it crashes, right?
And thank you.
Unpacker should not crash, However the extracted .STM seems to have folders embedded into the file, I have not yet found a flag which defines folders or which files are going in them, it's really inconsistent but i don't know for now.
Well, it's still a job well done.
