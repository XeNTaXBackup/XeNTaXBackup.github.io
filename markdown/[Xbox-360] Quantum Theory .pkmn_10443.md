## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-21T21:19:00+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

Hi. Need help to extract files from quantum theory .pkmn archives. I would like to look at model format very much, models there are nice. If someone could help it will be great, thanks in advance.
## Post #2
- Username: zaramot
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-21T22:54:39+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

just run offzip on them.
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-22T17:00:22+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

Thanks a lot Chrrox!   Again you aided me, I'm really appreciate it. Good news textures are extractable and they working.



Also I figure out vertices, but still have problems with faces. Face indicies has FFFF everywhere, after every 6 or 12 bytes and so on. Never saw this before so need and advice how make them work. Here's I uploaded extracted model, maybe someone will fire out [http://www.mediafire.com/?ep9h333k41s7s1t](http://www.mediafire.com/?ep9h333k41s7s1t)
[qt_mdl.jpg](https://xentaxbackup.github.io/file/6421_qt_mdl.jpg)
## Post #4
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-22T21:25:16+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

FFFF just means reset the triangle strip.
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-22T21:49:47+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

Thanks again Chrrox, but how could I skip those FFFF or maybe parse them correctly. Some example of maxscript would be great
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-06-01T18:01:17+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

Still need help with this one, I managed to skip those FFFF, but imported mesh looks like a total mess. Thanks in advance for any help.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-01T18:11:58+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

[viewtopic.php?f=16&t=10348&hilit=Knights+Contract](http://forum.xentax.com/viewtopic.php?f=16&t=10348&hilit=Knights+Contract)
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-06-01T19:14:23+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

Thanks Chrrox, I tried this code, but it didn't help. All because of lack of experience I've did something wrong, or maybe it's some specific case. You don't mind if I send you my script and sample model file? Sorry, if this is too much 

EDIT: Problem solved, models working fine
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-04-27T10:37:04+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

hey zaramot, you wouldn't happen to still have the maxscript for this game would ya? thanks.
## Post #10
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-28T09:22:49+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

Hi Howfie!   I'm sure I have this script somewhere on my HDDs. I will take a look, when I'll find it I'll post it here
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-04-28T17:32:14+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

cool, thank you.
## Post #12
- Username: zdsmdbh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 13, 2013 10:03 am
- Post datetime: 2014-06-17T15:29:23+00:00
- Post Title: [Xbox-360] Quantum Theory .pkmn

Hi,any news about the script?
BTW,did you still remember the offzip command for unpack these .pkmn files?
I tried these two:
offzip.exe -a input_archive output_folder 0
offzip.exe -z -15 -a input_archive output_folder 0

But all I got are small files,obviously that's not correct.
Some files:[http://1drv.ms/1hsoiML](http://1drv.ms/1hsoiML)
Thanks!
