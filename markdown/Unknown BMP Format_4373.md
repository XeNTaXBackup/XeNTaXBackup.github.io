## Post #1
- Username: Cyrem
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 18, 2010 12:38 pm
- Post datetime: 2010-04-23T02:22:02+00:00
- Post Title: Unknown BMP Format

I've been trying to figure this out for weeks but have not been able really figure out anything about it. The BMP is from LEGO Racers 1. I've tried every BMP opener I could find and nothing has helped.

What I have found is where to find the Width and Height of the image. I also know it is 256 colour or less because in the EXE there is a error "Palettes larger than 256 colors not supported".

At position 2 you will see the HEX: 8002. Which Reversed is 0280 which = 640
At position 4 you will see the HEX: E001. Which Reversed is 01E0 which = 480

So the image is 640x480px.

EDIT: Looking at it more, it's missing a proper BMP header. Though, I'm not sure if it is given a proper header it will work.
Thanks for your help.
[BACKDRP.zip](https://xentaxbackup.github.io/file/2965_BACKDRP.zip)
## Post #2
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2010-09-09T13:16:20+00:00
- Post Title: Unknown BMP Format

I opened it with irfan-view asa raw file with 1 byte per pixelasagrayscale image but it gives only a random picture which only goes to the half of the height (I think,that this file isnt a bitmap image instead ithink it is compressed because the bytes are not very repetive and didnt look like a color-flow)
[BACKDRP.zip](https://xentaxbackup.github.io/file/3419_BACKDRP.zip)
