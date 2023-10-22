## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-10-25T17:51:00+00:00
- Post Title: Looney Tunes Racing .SKN

[http://puu.sh/kX5KU.SKN](http://puu.sh/kX5KU.SKN)

I'm trying to use hex2obj on these, and I know to look for 0000 0100 0200 in hex, but I don't know where to to start since it comes up multiple times.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-25T19:44:12+00:00
- Post Title: Looney Tunes Racing .SKN

this skn seems to be a skeleton file, isn't it?
I can't seem to find a decent point cloud here.

Anyway you may try out these H2O parameter files:
0x2E36 112
Vb1
16 99
0x22AA 96
020400
0x0 255

and
0xEF2 1077
Vb1
16 99
0x22AA 185
020400
0x0 255

For the last one it's important to enter a 2 into the editbox below hex2obj's "toggle pointCloud" button
since we've 4 bytes faces here with the fourth value (0) to be skipped.

(Guess these files won't help you either.)
## Post #3
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-10-25T20:51:55+00:00
- Post Title: Looney Tunes Racing .SKN

with the models, there's .bin, .skn and .anm. I'm gonna guess .bin is the model, but the hex is looking like this. Here's a .bin file:

[http://puu.sh/kXqzs.BIN](http://puu.sh/kXqzs.BIN)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-25T22:38:48+00:00
- Post Title: Looney Tunes Racing .SKN

*.bin contains TIM files (texture). Search for 1000000008 and save the bytes 'til the next pattern as .tim.
Open/convert with Mystical's Timviewer. Gives some exception for me but the continue button heals everything (wish I'd known that ages before when I thought this viewer were useless... )



TIMviewer.JPG (97.71 KiB) Viewed 56 times
