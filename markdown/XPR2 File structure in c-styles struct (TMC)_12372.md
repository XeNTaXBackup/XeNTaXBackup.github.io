## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-10T23:18:50+00:00
- Post Title: XPR2 File structure in c-styles struct (TMC?)

Hi guys
It seems this file format has already been discovered
I dont know if there is a bitmap/png or tga converter
but my problem is i can understand quick bms script
I always get lost and confused pretty quickly
Would someone be nice enough to provide me a c, c++, C# styled class structure for this file type?
Even a 010 template would be appreciated

Thanks

(I attached a small file)

```
struct XPR
{
    struct XPR_Header
    {
        char name[4];
        uint addr;
        uint size;
        uint count;
    }xprHeader;

    struct TX2D_entry
    {
        char name[4];
        uint addr; //+4?
        uint offset; //always 52? Oddset size to next
        uint size;
    }tx2dHeader; //[xprHeader.count];
    
    uint zero;
    struct TX2D_names
    {
        string name;
    }tx2dNames[xprHeader.count];
}xpr;

```

[MODEL_EFF.zip](https://xentaxbackup.github.io/file/8241_MODEL_EFF.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-10T23:30:28+00:00
- Post Title: XPR2 File structure in c-styles struct (TMC?)

take a look at this neosis plugin, written in python

[viewtopic.php?p=65649#p65649](http://forum.xentax.com/viewtopic.php?p=65649#p65649)
## Post #3
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-10T23:35:27+00:00
- Post Title: XPR2 File structure in c-styles struct (TMC?)

I was just coming to post that I found this
Holy god it is quite a lot (Never used python either but i will look into it)
I guess I'll settle for conversion without understanding it for now

That said. I'll still accept help
