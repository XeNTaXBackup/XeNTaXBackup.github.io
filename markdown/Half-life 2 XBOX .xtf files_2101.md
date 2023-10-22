## Post #1
- Username: ash_link
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 09, 2006 12:23 pm
- Post datetime: 2006-09-16T16:17:38+00:00
- Post Title: Half-life 2 XBOX *.xtf files

Valve had made custom vtf-like textures inside of the XZP files. Is it possible if anyone can crack the format?

Alyx's Hair and face in xtf format
[http://rapidshare.de/files/33336041/aly ... r.xtf.html](http://rapidshare.de/files/33336041/alyx_faceandhair.xtf.html)
## Post #2
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2018-04-07T22:27:07+00:00
- Post Title: Half-life 2 XBOX *.xtf files

I've got a work in progress tool that can convert to a .dds file (the format is pretty similar to the .vtf file format - texture data seems to be stored the same way, though the low res image data may not be, and there is new fallback image data too - the header is in the Source SDK anyway).

Interestingly the file you linked is actually stored as IMAGE_FORMAT_P8 which I don't think the PC version of the engine even supports. I guess Valve needed a way to keep texture memory low and using palettised textures was one of the options they chose.
## Post #3
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2018-04-08T05:41:03+00:00
- Post Title: Half-life 2 XBOX *.xtf files

Alright so I've got extraction of DXT1 and DXT5 textures working but not P8 (and they're the only three formats I've come across).
Turns out the P8 images are swizzled. It looks like the swizzling/deswizzling code is in the SourceSDK:

```
 * 
 * Swizzler
 *
 * Purpose: To allow simple manipulations of a swizzled texture, without the 
 * hassle or overhead of unswizzling the whole thing in order to tweak a few 
 * points on the texture. This works with both 2D and 3D textures.
 * 
 * Notes: 
 *   Most of the time when messing with a texture, you will be incrementing
 *   by a constant value in each dimension.  Those deltas can be converted
 *   to an intermediate value via the SwizzleXXX(num) methods which can be
 *   used to quickly increment a dimension.
 *
 *   The type SWIZNUM is used to represent numbers returned by the SwizzleXXX()
 *   methods, also known as "intermediate values" in this documentation.
 * 
 *   Code in comments may be uncommented in order to provide some sort of 
 *   parameter sanity. It assures that any number passed to num will only 
 *   alter the dimension specified by dim.
 * 
 * Elements:
 *   
 *   m_u = texture map (converted) u coordinate
 *   m_v = texture map (converted) v coordinate
 *   m_w = texture map (converted) w coordinate
 * 
 *   m_MaskU = internal mask for u coordinate
 *   m_MaskV = internal mask for v coordinate
 *   m_MaskW = internal mask for w coordinate
 *
 *   m_Width = width of the texture this instance of the class has been initialized for
 *   m_Height = height of the texture this instance of the class has been initialized for
 *   m_Depth = depth of the texture this instance of the class has been initialized for
 * 
 * Methods:
 *   SWIZNUM SwizzleU(DWORD num) -- converts num to an intermediate value that
 *     can be used to modify the u coordinate
 *   SWIZNUM SwizzleV(DWORD num) -- converts num to an intermediate value that
 *     can be used to modify the v coordinate
 *   SWIZNUM SwizzleW(DWORD num) -- converts num to an intermediate value that
 *     can be used to modify the w coordinate
 *
 *   DWORD UnswizzleU(SWIZNUM index) -- takes an index to the swizzled texture, 
 *     and extracts & returns the u coordinate
 *   DWORD UnswizzleV(SWIZNUM index) -- takes an index to the swizzled texture, 
 *     and extracts & returns the v coordinate
 *   DWORD UnswizzleW(SWIZNUM index) -- takes an index to the swizzled texture, 
 *     and extracts & returns the w coordinate
 *
 *   SWIZNUM SetU(SWIZNUM num) -- sets the U coordinate to num, where num is an intermediate 
 *     value returned by Convert; returns num.
 *   SWIZNUM SetV(SWIZNUM num) -- sets the V coordinate to num, where num is an intermediate 
 *     value returned by Convert; returns num.
 *   SWIZNUM SetW(SWIZNUM num) -- sets the W coordinate to num, where num is an intermediate 
 *     value returned by Convert; returns num.
 *
 *   SWIZNUM AddU(SWIZNUM num) -- adds num to the U coordinate, where num is an intermediate value 
 *     returned by Convert; returns the new (swizzled) U coordinate
 *   SWIZNUM AddV(SWIZNUM num) -- adds num to the V coordinate, where num is an intermediate value 
 *     returned by Convert; returns the new (swizzled) V coordinate
 *   SWIZNUM AddW(SWIZNUM num) -- adds num to the W coordinate, where num is an intermediate value 
 *     returned by Convert; returns the new (swizzled) W coordinate
 *
 *   SWIZNUM SubU(SWIZNUM num) -- subtracts num from the U coordinate, where num is an intermediate value 
 *     returned by Convert; returns the new (swizzled) U coordinate
 *   SWIZNUM SubV(SWIZNUM num) -- subtracts num from the V coordinate, where num is an intermediate value 
 *     returned by Convert; returns the new (swizzled) V coordinate
 *   SWIZNUM SubW(SWIZNUM num) -- subtracts num from the W coordinate, where num is an intermediate value 
 *     returned by Convert; returns the new (swizzled) W coordinate
 *
 *   SWIZNUM IncU() -- increments the U coordinate by 1, returns the new (swizzled) U coordinate.
 *   SWIZNUM IncV() -- increments the V coordinate by 1, returns the new (swizzled) V coordinate.
 *   SWIZNUM IncW() -- increments the W coordinate by 1, returns the new (swizzled) W coordinate.
 *
 *   SWIZNUM DecU() -- decrements the U coordinate by 1, returns the new (swizzled) U coordinate.
 *   SWIZNUM DecV() -- decrements the V coordinate by 1, returns the new (swizzled) V coordinate.
 *   SWIZNUM DecW() -- decrements the W coordinate by 1, returns the new (swizzled) W coordinate.
 *
 *   SWIZNUM Get2() -- returns the index to the swizzled volume texture, based on 
 *     the U, and V coordinates, as modified by the previous methods.
 *
 *   SWIZNUM Get3() -- returns the index to the swizzled volume texture, based on 
 *     the U, V, and W coordinates, as modified by the previous methods.
 *
 * Performance:
 *   The algorithm used in most methods of this class require only Subtraction and a binary And
 *   operation to complete the operation. In the AddXXX methods, a negation, a subtraction, and two
 *   binary And operations are required. For this reason, the SubXXX methods are actually faster than
 *   AddXXX. Inc and Dec are roughly the same speed however.
 *
 ****************************************************************************/
#pragma once

#ifndef DWORD
typedef unsigned long DWORD;
#endif

typedef DWORD SWIZNUM;

class Swizzler 
{
public:

    // Dimensions of the texture
    DWORD m_Width;
    DWORD m_Height;
    DWORD m_Depth; 

    // Internal mask for each coordinate
    DWORD m_MaskU;
    DWORD m_MaskV;
    DWORD m_MaskW; 

    // Swizzled texture coordinates
    DWORD m_u;
    DWORD m_v;
    DWORD m_w;     

    Swizzler(): m_Width(0), m_Height(0), m_Depth(0),
        m_MaskU(0), m_MaskV(0), m_MaskW(0),
        m_u(0), m_v(0), m_w(0)
        { }

    // Initializes the swizzler
    Swizzler(
        DWORD width, 
        DWORD height, 
        DWORD depth
        )
    { 
        Init(width, height, depth);
    }

    void Init(
        DWORD width,
        DWORD height,
        DWORD depth
        )
    {
        m_Width = width; 
        m_Height = height; 
        m_Depth = depth;
        m_MaskU = 0;
        m_MaskV = 0;
        m_MaskW = 0;
        m_u = 0;
        m_v = 0;
        m_w = 0;

        DWORD i = 1;
        DWORD j = 1;
        DWORD k;

        do 
        {
            k = 0;
            if (i < width)   
            { 
                m_MaskU |= j;   
                k = (j<<=1);  
            }

            if (i < height)  
            { 
                m_MaskV |= j;   
                k = (j<<=1);  
            }

            if (i < depth)   
            {
                 m_MaskW |= j;   
                 k = (j<<=1);  
            }

            i <<= 1;
        } 
        while (k);
    }

    // Swizzles a texture coordinate
    SWIZNUM SwizzleU( 
        DWORD num 
        )
    {
        SWIZNUM r = 0;

        for (DWORD i = 1; i <= m_MaskU; i <<= 1) 
        {
            if (m_MaskU & i) 
            {
                r |= (num & i);
            }
            else
            {
                num <<= 1;
            }
        }

        return r;
    }

    SWIZNUM SwizzleV( 
        DWORD num 
        )
    {
        SWIZNUM r = 0;

        for (DWORD i = 1; i <= m_MaskV; i <<= 1) 
        {
            if (m_MaskV & i)
            {
                r |= (num & i);
            }
            else
            {
                num <<= 1;
            }
        }

        return r;
    }

    SWIZNUM SwizzleW( 
        DWORD num 
        )
    {
        SWIZNUM r = 0;

        for (DWORD i = 1; i <= m_MaskW; i <<= 1) 
        {
            if (m_MaskW & i)
            {
                r |= (num & i);
            }
            else
            {
                num <<= 1;
            }
        }

        return r;
    }

    SWIZNUM Swizzle(
        DWORD u, 
        DWORD v, 
        DWORD w
        )
    {
        return SwizzleU(u) | SwizzleV(v) | SwizzleW(w);
    }
    
    // Unswizzles a texture coordinate
    DWORD UnswizzleU( 
        SWIZNUM num
        )
    {
        DWORD r = 0;

        for (DWORD i = 1, j = 1; i; i <<= 1) 
        {
            if (m_MaskU & i)  
            {   
                r |= (num & j);   
                j <<= 1; 
            } 
            else               
            {   
                num >>= 1; 
            }
        }

        return r;
    }

    DWORD UnswizzleV( 
        SWIZNUM num 
        )
    {
        DWORD r = 0;

        for (DWORD i = 1, j = 1; i; i <<= 1) 
        {
            if (m_MaskV & i)  
            {   
                r |= (num & j);   
                j <<= 1; 
            } 
            else
            {   
                num >>= 1; 
            }
        }

        return r;
    }

    DWORD UnswizzleW( 
        SWIZNUM num 
        )
    {
        DWORD r = 0;

        for (DWORD i = 1, j = 1; i; i <<= 1) 
        {
            if (m_MaskW & i)  
            {   
                r |= (num & j);   
                j <<= 1; 
            } 
            else               
            {   
                num >>= 1; 
            }
        }

        return r;
    }

    // Sets a texture coordinate
    __forceinline SWIZNUM SetU(SWIZNUM num) { return m_u = num /* & m_MaskU */; }
    __forceinline SWIZNUM SetV(SWIZNUM num) { return m_v = num /* & m_MaskV */; }
    __forceinline SWIZNUM SetW(SWIZNUM num) { return m_w = num /* & m_MaskW */; }
    
    // Adds a value to a texture coordinate
    __forceinline SWIZNUM AddU(SWIZNUM num) { return m_u = ( m_u - ( (0-num) & m_MaskU ) ) & m_MaskU; }
    __forceinline SWIZNUM AddV(SWIZNUM num) { return m_v = ( m_v - ( (0-num) & m_MaskV ) ) & m_MaskV; }
    __forceinline SWIZNUM AddW(SWIZNUM num) { return m_w = ( m_w - ( (0-num) & m_MaskW ) ) & m_MaskW; }

    // Subtracts a value from a texture coordinate
    __forceinline SWIZNUM SubU(SWIZNUM num) { return m_u = ( m_u - num /* & m_MaskU */ ) & m_MaskU; }
    __forceinline SWIZNUM SubV(SWIZNUM num) { return m_v = ( m_v - num /* & m_MaskV */ ) & m_MaskV; }
    __forceinline SWIZNUM SubW(SWIZNUM num) { return m_w = ( m_w - num /* & m_MaskW */ ) & m_MaskW; }

    // Increments a texture coordinate
    __forceinline SWIZNUM IncU()              { return m_u = ( m_u - m_MaskU ) & m_MaskU; }
    __forceinline SWIZNUM IncV()              { return m_v = ( m_v - m_MaskV ) & m_MaskV; }
    __forceinline SWIZNUM IncW()              { return m_w = ( m_w - m_MaskW ) & m_MaskW; }

    // Decrements a texture coordinate
    __forceinline SWIZNUM DecU()              { return m_u = ( m_u - 1 ) & m_MaskU; }
    __forceinline SWIZNUM DecV()              { return m_v = ( m_v - 1 ) & m_MaskV; }
    __forceinline SWIZNUM DecW()              { return m_w = ( m_w - 1 ) & m_MaskW; }

    // Gets the current swizzled address for a 2D or 3D texture
    __forceinline SWIZNUM Get2D()          { return m_u | m_v; }
    __forceinline SWIZNUM Get3D()          { return m_u | m_v | m_w; }
};
```


But I'm not too sure how to use it. For each pixel I've called UnswizzleU and UnswizzleV which both seem to return correct-looking values (spot-checking I see UnswizzleU returns values in the range of the width and UnswizzleV returns values in the range of the height).
I then index the image data like so: m_pImageData[0][(m_Header.iWidth * v) + u]
But writing that out to files doesn't anything that looks right. Anyone got any idea how to use code correctly?
## Post #4
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2018-04-20T10:54:35+00:00
- Post Title: Half-life 2 XBOX *.xtf files

The code at [https://github.com/Cxbx-Reloaded/Cxbx-R ... .cpp#L1339](https://github.com/Cxbx-Reloaded/Cxbx-Reloaded/blob/793354701f1ebe0a379e3d8524bdf8575eda4fd2/src/CxbxKrnl/EmuD3D8/Convert.cpp#L1339) seems to work.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-29T07:10:15+00:00
- Post Title: Half-life 2 XBOX *.xtf files

here is Noesis python script for fun to open some xtf samples i had from this game  


 tex_Half-Life2_Xbox_xtf.zip
(888 Bytes) Downloaded 63 times


supports dxt1, dxt5, paletted morton swizzled rgba8888 and morton swizzled rgba8888 
not 100% sure of the last two but they looked okay to me
## Post #6
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2018-05-03T10:23:19+00:00
- Post Title: Half-life 2 XBOX *.xtf files

Ah thanks, I took a quick look and hopefully I'll be able to simplify what I have.
## Post #7
- Username: gongagaga
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 18, 2020 5:03 pm
- Post datetime: 2020-11-18T13:48:00+00:00
- Post Title: Half-life 2 XBOX *.xtf files

> Reply from Acewell ↑Sun Apr 29, 2018 3:10 pm at Sun Apr 29, 2018 3:10 pm
>
> 
here is Noesis python script for fun to open some xtf samples i had from this game  
tex_Half-Life2_Xbox_xtf.zip
supports dxt1, dxt5, paletted morton swizzled rgba8888 and morton swizzled rgba8888 
not 100% sure of the last two but they looked okay to me

im getting error from this script
ModuleNotFoundError: No module named 'inc_noesis'
## Post #8
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-11-18T17:30:20+00:00
- Post Title: Half-life 2 XBOX *.xtf files

Just out of curiosity... why? Is there anything the Xbox port has that the PC game doesn't?
## Post #9
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2020-11-20T11:06:51+00:00
- Post Title: Half-life 2 XBOX *.xtf files

Some of the maps are different.
Not sure if there are any other changes - the textures are definitely lower resolution at least.
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-11-22T13:52:11+00:00
- Post Title: Half-life 2 XBOX *.xtf files

> Reply from gongagaga ↑Wed Nov 18, 2020 9:48 pm at Wed Nov 18, 2020 9:48 pm
>
> im getting error from this script
ModuleNotFoundError: No module named 'inc_noesis'
its a script for Noesis, you must place the script in 
the Noesis\plugins\python folder.
## Post #11
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2020-12-22T21:54:52+00:00
- Post Title: Half-life 2 XBOX *.xtf files

I've got a tool which will do the conversion now: [https://www.moddb.com/games/half-life/d ... gssmt-v004](https://www.moddb.com/games/half-life/downloads/gssmt-v004)
## Post #12
- Username: swiggy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 08, 2023 8:18 pm
- Post datetime: 2023-03-26T03:20:34+00:00
- Post Title: Half-life 2 XBOX *.xtf files

> Reply from tschumann ↑Sun Apr 08, 2018 1:41 pm at Sun Apr 08, 2018 1:41 pm
>
> 
Alright so I've got extraction of DXT1 and DXT5 textures working but not P8 (and they're the only three formats I've come across).
Turns out the P8 images are swizzled. It looks like the swizzling/deswizzling code is in the SourceSDK:
Code: Select all/*****************************************************************************
 * 
 * Swizzler
 *
 * Purpose: To allow simple manipulations of a swizzled texture, without the 
 * hassle or overhead of unswizzling the whole thing in order to tweak a few 
 * points on the texture. This works with both 2D and 3D textures.
 * 
 * Notes: 
 *   Most of the time when messing with a texture, you will be incrementing
 *   by a constant value in each dimension.  Those deltas can be converted
 *   to an intermediate value via the SwizzleXXX(num) methods which can be
 *   used to quickly increment a dimension.
 *
 *   The type SWIZNUM is used to represent numbers returned by the SwizzleXXX()
 *   methods, also known as "intermediate values" in this documentation.
 * 
 *   Code in comments may be uncommented in order to provide some sort of 
 *   parameter sanity. It assures that any number passed to num will only 
 *   alter the dimension specified by dim.
 * 
};

But I'm not too sure how to use it. For each pixel I've called UnswizzleU and UnswizzleV which both seem to return correct-looking values (spot-checking I see UnswizzleU returns values in the range of the width and UnswizzleV returns values in the range of the height).
I then index the image data like so: m_pImageData[0][(m_Header.iWidth * v) + u]
But writing that out to files doesn't anything that looks right. Anyone got any idea how to use code correctly?

I'm trying to unswizzle images into my convert tool, I've read up and understand the concept of swizzling im lost on how to implement and unswizzle code wont work  

Did you get the unswizzle image c++ code working in the end?
## Post #13
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2023-03-26T06:52:07+00:00
- Post Title: Half-life 2 XBOX *.xtf files

Yes I used that exact code.
I don't really understand swizzling to be honest.
