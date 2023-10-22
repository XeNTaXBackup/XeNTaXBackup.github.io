## Post #1
- Username: Mimo750
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 17, 2019 3:33 am
- Post datetime: 2019-11-16T19:37:18+00:00
- Post Title: Bank extract not working

Hello forum, i'm trying to extract this bank file but it only gives 1 very small fsb file and the actuall size of the bank file is 3.2mb so quickbms should extract same size fsb files at total right. But it only extract 23 kb fsb. Can you help me with this problem? I'm sharing the link cause forums says its large to upload.

[http://s000.tinyupload.com/index.php?fi ... 4821419920](http://s000.tinyupload.com/index.php?file_id=27423439904821419920)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-16T22:32:31+00:00
- Post Title: Bank extract not working

It seems like there's other data in the archive, so the FSB file is only a very small part of it.  The rest is made up of lots of other bits of data, some of which looks like audio.
## Post #3
- Username: Mimo750
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 17, 2019 3:33 am
- Post datetime: 2019-11-16T22:50:50+00:00
- Post Title: Bank extract not working

Yeah you could extract more fsb's out of this bank file? I'm looking for the rest of the  .wav files mostly since i only get sine and pass by audio files. Thanks for the reply by the way!
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-18T16:48:10+00:00
- Post Title: Bank extract not working

There are no more FSBs in that archive.  There are lots of other bits of audio in Apple Quicktime format.  I may be able to do an extractor if I can figure out the format!
## Post #5
- Username: Mimo750
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 17, 2019 3:33 am
- Post datetime: 2019-11-19T15:12:42+00:00
- Post Title: Bank extract not working

Thanks for your time checking on this bank file, i've asked here and there with no luck about how to extract this bank file.
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-19T17:59:54+00:00
- Post Title: Bank extract not working

I've figured it out.  You can use the attached QuickBMS script to extract the audio files, and the attached .vgmstream.txth file to play them in Foobar.

This probably won't work with other .bank files (if there are any in the game), but at least it's a start!
[motogp.zip](https://xentaxbackup.github.io/file/17086_motogp.zip)
## Post #7
- Username: Mimo750
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 17, 2019 3:33 am
- Post datetime: 2019-11-19T21:35:19+00:00
- Post Title: Bank extract not working

Thank you very much man, but where do i paste the vgstream.txth. Sorry but i'm completely dumb about this stuff!

edit: i've figured it out!

edit2: yes i've tried for other bikes sounds of the game and the result is not good. I'm getting noise sounds with distortion, completely different from the one in the first post.
## Post #8
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-19T22:18:09+00:00
- Post Title: Bank extract not working

Each archive is different, so I'd probably need a few examples so that I can rewrite the script to handle all of them.
## Post #9
- Username: Mimo750
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 17, 2019 3:33 am
- Post datetime: 2019-11-19T22:50:31+00:00
- Post Title: Bank extract not working

There is one more yamaha bank file but it LOD and it's way smaller, could you check on this just to see what's different from the one in the first post?

[http://s000.tinyupload.com/index.php?fi ... 5377219681](http://s000.tinyupload.com/index.php?file_id=03302545385377219681)
## Post #10
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-20T00:06:55+00:00
- Post Title: Bank extract not working

Yep, it's slightly different.  My script was just tailored towards the first .bank file, but I'll have a look at it tomorrow and put up a new script
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-20T20:14:41+00:00
- Post Title: Bank extract not working

This script will extract the non-FSB LOD bank file audio.
[MotoGP_LOD.zip](https://xentaxbackup.github.io/file/17098_MotoGP_LOD.zip)
## Post #12
- Username: Mimo750
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 17, 2019 3:33 am
- Post datetime: 2019-11-20T20:25:09+00:00
- Post Title: Bank extract not working

Thank you sir, you're a champ. Ok they are the same sounds as the first bank just without the other small bits of audio but the 3 big ones. So for different bikes i would need different script if i understood correct.
## Post #13
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-20T21:06:42+00:00
- Post Title: Bank extract not working

Yes, you would need another script - I would need to work on it to handle all bank files, but those 2 scripts were just for those 2 files.
