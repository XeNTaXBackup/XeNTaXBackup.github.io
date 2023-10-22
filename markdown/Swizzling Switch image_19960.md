## Post #1
- Username: masagrator
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 17, 2018 7:45 am
- Post datetime: 2019-04-08T17:10:15+00:00
- Post Title: Swizzling Switch image

I was thinking if someone will be kind to write script for swizzling texture for Nintendo Switch.
Or if it's possible to use rawtex for this case.

This is what f.e. i was looking to show in game UI


And how it looks like in-game


I have generated this mess with rawtex and this is the same texture that is showing after swapping texture that I created with Unreal Engine 4 for Windows.
So it should be possible to swizzle it backwards so after reading it by game it will look properly.
This file has 194 offset, 512x256 texture size, when original size is 499x258, b8g8r8a8_unorm (but it's only white, so r8g8b8a8_unorm will work too).

Here's the guy who wrote it how to manage swizzling as image.
[https://www.vg-resource.com/thread-3392 ... #pid647504](https://www.vg-resource.com/thread-33929-post-647504.html#pid647504)
[UiTX_Title_logo_00.zip](https://xentaxbackup.github.io/file/16005_UiTX_Title_logo_00.zip)
## Post #2
- Username: masagrator
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 17, 2018 7:45 am
- Post datetime: 2019-04-10T05:58:08+00:00
- Post Title: Swizzling Switch image

I have modified Noesis to correctly unswizzling textures for Switch UE4 games. Swizzling works too, but with limitations.

[https://gbatemp.net/threads/noesis-mod- ... e4.535571/](https://gbatemp.net/threads/noesis-mod-tiling-texture-for-ue4.535571/)
