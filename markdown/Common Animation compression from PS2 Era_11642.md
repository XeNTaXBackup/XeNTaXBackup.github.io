## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-06-29T08:22:35+00:00
- Post Title: Common Animation compression from PS2 Era

Hi
I have been looking into some animation files from old ps2 games. Every time I manage to figure out the file structure i always get stuck at the very final step - getting the position or rotation data. 

I was wondering if i could get a compilation of games with extracted animation from the 2001-2006 era


```
struct File
{
    struct Header
    {
        uint64 id;        
        float lenght; //seconds
        uint sixty; //often 60
    }header;

    uint offset;
    uint zero[2];

    uint buff[((offset-20)/4)-2]; //This is a hack to make the template jump to the offset location

    uint tupleCount;
    struct Tuple
    {
        float time;
        uint addr; //164 or 176 intervals
    }tuple[tupleCount];

    //dont know the rest but they dont appear in a few older versions of this game.
   //They seem irrelevant

}animEntry;


```

[1.rar](https://xentaxbackup.github.io/file/7531_1.rar)
## Post #2
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-06-29T08:35:55+00:00
- Post Title: Common Animation compression from PS2 Era

I decided to add the data for a single frame animation. Most frames are 164b but some times they are over 176b i think these ones include extra bone/object data or maybe translation data (this is often not stored in game animation of ps2 era as translation is done by code).

when I assumed the extra value is 176-164 (12b) was a bone it did not add up cos 164/12 is not a whole number hence i am more inclined to think of it as a translation value hfloat x,y,z; ( i was half asleep i meant half float)

This example is a Konami Game (PES5) but I am after many other games as well


Most of the data only makes sense as half floats but I cannot seem to understand how 010 derive their half floats
[1_frame.rar](https://xentaxbackup.github.io/file/7533_1_frame.rar)
## Post #3
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-06-29T09:23:12+00:00
- Post Title: Common Animation compression from PS2 Era

I just found [This](http://number-none.com/product/Scalar%20Quantization/index.html) on Quaternion quantization 2002.

The problem with this iis that it will always return some valid data
