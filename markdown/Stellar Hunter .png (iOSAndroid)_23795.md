## Post #1
- Username: simple
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Sep 29, 2007 6:52 am
- Post datetime: 2021-04-26T13:35:34+00:00
- Post Title: Stellar Hunter .png (iOS/Android)

I have extracted the png files from the Android version of Stellar Hunter apk file, but the png files are unviewable by normal means. I tried opening them in a hex editor but they don't seems to have any PNG header? Not really familiar with hex editing yet so I am unsure...

I have uploaded some samples and wondering if anyone can take a look.

[https://www.mediafire.com/folder/7w4lmxle4wimm/png](https://www.mediafire.com/folder/7w4lmxle4wimm/png)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-26T14:37:23+00:00
- Post Title: Stellar Hunter .png (iOS/Android)

It uses Deflate compression, so you can extract with Offzip, something like: offzip -a -z -15 anim_tex.png "output_folder" 0

They aren't PNG files.  The decompressed data has a "PKM 20" header, which Noesis will load.
## Post #3
- Username: simple
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Sep 29, 2007 6:52 am
- Post datetime: 2021-04-26T19:11:52+00:00
- Post Title: Stellar Hunter .png (iOS/Android)

Hi DKDave,

Thank you for your quick reply.

I used the Offzip tools and confirmed I can extract and view the images in Noesis. 
Thank you again for the help.
