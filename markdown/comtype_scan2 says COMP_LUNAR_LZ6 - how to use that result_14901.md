## Post #1
- Username: BlackDog
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 11, 2015 4:51 am
- Post datetime: 2016-08-21T08:02:59+00:00
- Post Title: comtype_scan2 says COMP_LUNAR_LZ6 - how to use that result?

Hi,

So I've gone about trying to figure out the compression used in a file. I've run Aluigi's comtype_scan2 and I get what lookslike an almost OK result with #256.
According to def.h, it's "COMP_LUNAR_LZ6".
How do I move forward from there?
Actually, let me ask that question more precisely. How can I decompress, in a way that I can later re-compress?
I mean, I've seen scripts for decompression but people don't always manage to recompress from the same script. So either a BMS script that can be reversed, or a pointer to the source files where I can cut & paste into my custom program.
(I've tried looking into the quickbms code, but it looks like there's linking to a library.)

Thank you!
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-21T09:00:15+00:00
- Post Title: comtype_scan2 says COMP_LUNAR_LZ6 - how to use that result?

The name COMP_LUNAR_LZ6 sounds to me like its using LunarCompress.dll to do its magic. And checking what LunarCompress.dll has to say about the LZ6 format, its a format used on some games for the GameBoy so I doubt it would be showing up elsewhere.
What game is this from?
## Post #3
- Username: BlackDog
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 11, 2015 4:51 am
- Post datetime: 2016-08-21T21:03:51+00:00
- Post Title: comtype_scan2 says COMP_LUNAR_LZ6 - how to use that result?

Lost Heroes 3DS.
Well, if it's not that, then I really have to re-run the thing...
Any map file is expected to start with:
- "DGMP", which is clearly visible in the compressed version of the file. 
- file size
- version of the map (usually 1.00)
- sizeof the map (31*31, which means 1e000000 twice)
