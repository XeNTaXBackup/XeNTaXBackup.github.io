## Post #1
- Username: Danceatron
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 10, 2012 8:55 am
- Post datetime: 2012-07-10T01:23:31+00:00
- Post Title: PS2 Audio File: Re-interleaving?

Hey guys.

I've been digging through the Hex of this file to try to find the interleave.... I found a definite obvious pattern, but it hasn't helped me much.

File starts out with a bunch of "junk"

```
00000010        d0 ac 48 00 46 02 00 00     d0 0c 00 00 00 00 00 00
00000020        d0 ac 48 00 b8 02 00 00     d0 0c 00 00 00 00 00 00

```
Ok, then I get a bunch of lines of 00's
then fourty lines of:
```

```

actual data for about 20 lines 
a single line of 00's
then fourty more lines of:
```

```
 Then actual data again.
Also, every 8,192 bytes I get a line of 00's
So, I figured that was my interleave, but no dice.

Side note: I've been using MF Audio to test, I know there's something better out there, what SHOULD I be using?

This is from the Japanese game "Dance Summit 2001" btw.
If anyone has any insight, I'd appreciate it greatly. This has been driving me crazy.

EDIT:
Here's the first 50k of the file as a reference.
[http://www.sendspace.com/file/c5kceq](http://www.sendspace.com/file/c5kceq)
## Post #2
- Username: Danceatron
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 10, 2012 8:55 am
- Post datetime: 2012-07-11T00:20:17+00:00
- Post Title: PS2 Audio File: Re-interleaving?

I got this figured out all thanks to Snakemeat.
Basically there are two streams interleaved together for each song in the game, which are both independently interleaved.

So I was looking at two interleaved streams that were interleaved together.
(The game has 2 versions of each song; it changes the song if you're doing really well.)

Solution:
I used this to split the song into the two separate interleaved streams:
[http://www.mediafire.com/?68n330681c1q98t](http://www.mediafire.com/?68n330681c1q98t)

And viola!
But, this was just the first half of my quest. 
My goal here is actually to replace the music in the game.

So I was wondering....
Is there a way I could put these two separate streams back together the way they were?
In other words, how can I interleave 2 separate streams together?

If I can figure that one out I could put my on music into the game!
