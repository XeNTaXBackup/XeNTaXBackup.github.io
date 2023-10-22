## Post #1
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2017-11-04T00:02:33+00:00
- Post Title: [MOBILE] DC Legends .dds ( ATC RGBA Explicit )

I've been trying to convert this file format all night without success. I've used Compressonator and it will save the RGB but the not the alpha, plus it comes out in a weird way. I can get the RGB, using Compressonator, I can't however get the Alpha layer. I was wondering if anyone has looked into converting this format. Here are the RGB + Alpha images:





I've also supplied some examples, which can be downloaded at:
[https://drive.google.com/open?id=0B2nb4 ... Wd0aktkV2c](https://drive.google.com/open?id=0B2nb4mY93-PXZHJIbWd0aktkV2c)

Thanks, for taking the time have a look, and hope to hear from someone soon!
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-11-04T16:06:52+00:00
- Post Title: [MOBILE] DC Legends .dds ( ATC RGBA Explicit )

I haven't seen (ever) any game that uses explicit alpha, devs are just trolling you.
Those images have interpolated alpha.
So just rename ATCA to ATCI in header and they should work just fine.

However when I converted image in Comressonator into ARGB8 it swapped red and blue channel for me, bug I suppose.

Anyway here is result image.
## Post #3
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2017-11-05T09:56:49+00:00
- Post Title: [MOBILE] DC Legends .dds ( ATC RGBA Explicit )

> Reply from PredatorCZ
>
> I haven't seen (ever) any game that uses explicit alpha, devs are just trolling you.
Those images have interpolated alpha.
So just rename ATCA to ATCI in header and they should work just fine.

However when I converted image in Comressonator into ARGB8 it swapped red and blue channel for me, bug I suppose.

Thanks you so much mate. I had to wait until my missus stopped playing the Sims on my computer, than took another half hour figuring out I had to type "ATCI" instead of just changing the "A" to "I". For the "BUG", I haven't noticed it on my end mate. The "updated" files extract in Compressonator the same way that the originals appeared. Thanks again for helping mate, I owe you.
