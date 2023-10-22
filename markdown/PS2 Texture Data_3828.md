## Post #1
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-03T00:08:43+00:00
- Post Title: PS2 Texture Data

Hello,
i am looking into some texture data and i am trying to determine the proper way to interpret the clut data for some of the unswizzled images.  Currently they all seem to be 4-bit indexed images but i cannot get the clut data to be interpreted correctly for them.  The method i am using is similar to that i derived for the PS2 TPL data for resident evil 4 but not exactly the same.  The image data in these file has already been unswizzled using writeTexPSMCT32 and readTexPSMT4 from some ps2 texture conversion code i came across when looking into this information for a few other games.  i am just unsure what i may be missing in this data that could be causing problems during conversion, so i am turning to those of you that probably have far more experience in ps2 swizzling methods than i do.  All of the image data was successfully un-swizzled with the above functions using the GsTex0 data found in the header information of the files.  As such i assumed that the same data would be used in order to handle the conversion of the clut data as well, but so far i have been unsuccessful in doing this properly for 4-bit images.  The clut may contain palette data for multiple images so the GsTex0 CBP and other values may come into play.  The data itself may also be swizzled in some way, hopefully those more accustomed to ps2 data formats can help me out here.

If anyone has some better un-swizzling reference code than the information i have found so far, that would be helpful as well.  I will probably take a closer look at the sparky swizzling code and see what i can make of it again.

i have included a binary template file for use with 010 Editor with the file structure (just a text file for those that don't use that hex editor).

Any information you could provide would be greatly appreciated.

In the meantime i will get back to attempting to finish up the Street Fighter 4 animation data, heh.

Thanks in advance.

- revel8n
[test.rar](https://xentaxbackup.github.io/file/2496_test.rar)
