## Post #1
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-02-25T00:23:56+00:00
- Post Title: HELP with Switch Textures (*.dds, *.png, *.tga)

I have textures from the console Torchlight 2 game. 

Textures example: [https://yadi.sk/d/uMjQmMvBFyx2xA](https://yadi.sk/d/uMjQmMvBFyx2xA)
Switch textures have "_" sign in titles, unsigned - original PC textures.

But I don’t understand how to convert this to the usual format. 

ScarletConvert-v123 gives me this:


I believe that daemon1's ["Raw texture cooker"](https://forum.xentax.com/viewtopic.php?f=18&t=16461#p131699) can help me, but I don’t know how to work with patterns and how to find the right settings.
## Post #2
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-02-25T05:11:49+00:00
- Post Title: HELP with Switch Textures (*.dds, *.png, *.tga)

If this helps, here 8*4 pixel blocks are laid out this way:
## Post #3
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-02-26T00:27:32+00:00
- Post Title: HELP with Switch Textures (*.dds, *.png, *.tga)

More detailed scheme:



It's time to get into a hex-editor
## Post #4
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-02-26T03:33:52+00:00
- Post Title: HELP with Switch Textures (*.dds, *.png, *.tga)

Ok, I think I understand how this "Raw texture cooker" works.   



The main problem is that I did not understand what offset means until I looked at the file structure in hex- editor.
## Post #5
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-02-26T03:50:09+00:00
- Post Title: HELP with Switch Textures (*.dds, *.png, *.tga)

Ок, everything seems to work out for me. Still have questions with tga files.
Thanks to everyone who read.   Many thanks to @daemon1 for ["Raw texture cooker"](https://forum.xentax.com/viewtopic.php?f=18&t=16461#p131699) utility.
## Post #6
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-02-27T00:17:09+00:00
- Post Title: HELP with Switch Textures (*.dds, *.png, *.tga)

If it helps someone else, that's how I chose the Offset.



As I understand it, for *.dds you need "BC"-options, for *.png,*.tga - something like "b8g8r8a8"-options or similar. I understand that every problem is individual, but in my case it works.



Of course, I don’t know what all these options mean and how these work, but maybe this information will help someone find the right solution in the future.
