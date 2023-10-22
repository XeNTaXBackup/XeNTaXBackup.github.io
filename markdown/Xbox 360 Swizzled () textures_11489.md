## Post #1
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-05-05T16:23:20+00:00
- Post Title: Xbox 360 Swizzled (???) textures

Lately i am working on some xbox 360 model files (xpr2 files), which contain some textures that i am not able to properly preview them.

I discovered that the format is fully supported from Noesis, but i would like to write my own texture reader in order to learn more stuff about tiling and swizzling.

To be honest i think that i have slightly understood what swizzling is, but i have no idea how it works on the bit level.  I found some articles in google but they confused me even more.

Now in the model i am working on, i've located the texture blocks and i am pretty sure that there are some dxt1 textures in there, and well as some raw textures, on which i am working on right now. I thought that it would be the easiest way to understand what is going on with the raw textures and then apply the methodology on the dxt textures.

Here is the texture i am working on right now:


And here is the correct image exported from noesis:



I got that layout by simply applying tiling. I tested various tile sizes and the one that seems to be producing the best visual result is a 32x64 tile.

I did try to test all the possible tile sizes that could exist in that tile but all the results are just sucking, so i guess that i don't need any more tiling. I guess that its that swizzling thing.

I anyone has any experience on the field please, i am asking for your help guys
## Post #2
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-05-10T15:19:17+00:00
- Post Title: Xbox 360 Swizzled (???) textures

Ok found the solution myself 

They are swizzled indeed, i used an article written in dageron.com which explains everything and taught me a lot, although i did not fully get what is going on
