## Post #1
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2021-04-16T14:51:14+00:00
- Post Title: VW Infotainment 3d model

Hi all,

5 years ago, this helped me a lot in reverse engineering the graphics for my car's infotainment system. 
(read here: [viewtopic.php?f=10&t=14607](https://forum.xentax.com/viewtopic.php?f=10&t=14607)) 

Ever since, I've had a lot of fun modifying graphics, and eventually [released a toolbox](https://github.com/jilleb/mib2-toolbox) that has all kinds of modding-tools and scripts to customize the car's infotainment.
Almost all graphics can be changed now, but I have one final hurdle: the Navigation Arrow, also known as "Carsor".

The carsor is a 3d model with a texture and it looks like this:


I found that the contents of this arrow are inside carsor.sfc, a file that looks like a container with 3D-data and a PNG:


I tried Model Researcher, and found some vertices:


And later was able to get it to draw some faces too:


But that's it.. I feel like I'm close to finding the right format and how to convert between this SFC format and OBJ, but I'm not exactly there yet.

I wrote a quick and dirty 010 editor template, but it's not complete.

```
//--- 010 Editor Binary Template
//
// File:        sfc.bts
// Author:      Jille
// Revision:    1
// Purpose:     Discover Pro MIB2 scf file parser
// Comments:    SFC files can be found in objects.cff
// Colorcoding: Red = unknown, Green = known. Yellow = not sure
//--------------------------------------

////////////////////////////////////////////////////////////

LittleEndian();
byte header[16]<bgcolor=cYellow>;
long num_files;
struct {
    long id <bgcolor=cLtGreen>;
    long unknown <bgcolor=cRed>;
    long start_offset <bgcolor=cGreen>;
    long size <bgcolor=cDkGreen>;
} toc[num_files]<optimize=false>;


local int i =0;
while( i < num_files )
{
    FSeek(toc[i].start_offset);
    struct{
    short unknown_1_0000<bgcolor=cRed>;
    short part_id<bgcolor=cRed>;
    short unknown_2_0100<bgcolor=cDkRed>;

    short zeroes[5];
    long amount_of_faces;
    long amount_of_vertices;
    if (amount_of_vertices > 0 && amount_of_vertices <1000){
        long amount_of_z;
        short _unknown_0100[8];
        float start_coordinate;
        struct{
            float x_coordinate<bgcolor=cLtGreen>;
            float y_coordinate<bgcolor=cLtGreen>;
            float z_coordinate<bgcolor=cLtGreen>;
        } vertex_data[amount_of_vertices+2]<optimize=false>;

    } else if (amount_of_vertices > 1000){
            struct{
            float x_coordinate<bgcolor=cLtGreen>;
            float y_coordinate<bgcolor=cLtGreen>;
            float z_coordinate<bgcolor=cLtGreen>;
        } vertex_data[amount_of_faces+2]<optimize=false>;
}        
    } object;
    i = i + 1;
}

```


I'm drawing blanks.. who can help me find the last piece of this puzzle?
The carsor.sfc file I've used for this research can be downloaded here:
[https://www.dropbox.com/sh/hl4ih60fgmsx ... dn4a?dl=0
](https://www.dropbox.com/sh/hl4ih60fgmsxxef/AABmN_ZAnm6k2mLidKaJVdn4a?dl=0)

Thanks in andvance for any assistance or pointers in the right direction.

(note:
SFC format is also used by SNES games and Autodesk SXF format. Autodesk drawing format could be something of use however SXF viewer can't open the files either)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-16T19:30:56+00:00
- Post Title: VW Infotainment 3d model

I'm more familiar with hex2obj, so (carsor.sfc):
.



VW_infotainment.png (81.18 KiB) Viewed 62 times


(You'll need some fiddling to get addresses of uv blocks.)
## Post #3
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2021-04-19T15:16:18+00:00
- Post Title: VW Infotainment 3d model

wow, that's quick!! Thanks! I'll get to it right away, thank you!
## Post #4
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2021-04-20T14:42:21+00:00
- Post Title: VW Infotainment 3d model

Update: I'm currently writing a tool to convert between SFC and OBJ files, and after that, I'll go vice-versa  
Thanks again!

hex2obj is indeed a great tool!
