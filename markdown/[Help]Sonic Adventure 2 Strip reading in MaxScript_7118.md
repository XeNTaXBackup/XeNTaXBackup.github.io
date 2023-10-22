## Post #1
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-08-05T03:49:43+00:00
- Post Title: [Help]Sonic Adventure 2 Strip reading in MaxScript

Hey all, I've been working with MaxScript a little bit, and I can read some of the SA2 format at this point. The issue now is I need some help making some sort of strip reading code to actually read the strips. I have chroxx's script, but it won't work with these models period due to the strips not being normal strips per say. There's also several different types of strips in the format as a whole, but SA2 only uses some of them as far as I know. Here's how the spec on how the strips work.

```
This is the good stuff - Geometry!

Flags : Bits 0-1
0x00 = No User Flags Present
0x01 = 1 User Flag WORD present
0x02 = 2 User Flag WORDs present
0x03 = 3 User Flag WORDs Present

WORD : Size of Chunk in WORDS (Size * 2 = Bytes)

WORD : Bits 14-15 User Offset (I have no clue what this
does)
Bits 0-13 Number of Strips in Chunk

-STRIP DATA STARTS HERE-

SHORT : Number of points in Strip
Number of Triangles = Number of Points - 2
If Value is positive, then strip winds CCW.
If Value is Negative, them strip winds CW.
Use the Absolute Value of this for the number of

There are 9 types of Strips...
Data is stored as SHORT type

0x40 STRIP_CS I0, I1, I2, UserFlags ( x Flags)
I3, UserFlags ( x FLags)...

0x41 STRIP_CS_UVN I0, U0, V0,
I1, U1, V1,
I2, U2, V2, WORD UserFLags (x FLags)
I3, U3, V3, UserFlags (x Flags)...

0x42 STRIP_CS_UVH I0, U0, V0,
I1, U1, V1,
I2, U2, V2, WORD UserFLags (x FLags)
I3, U3, V3, UserFlags (x Flags)

0x43 STRIP_CS_VN I0, nx0, ny0, nz0,
I1, nx1, ny1, nz1,
I2, nx2, ny2, nz2, UserFlags (x Flags)
I3, nx3, ny3, nz3, UserFlags (x Flags)...

0x44 STRIP_CS_UVN_VN I0, U0, V0, nx0, ny0, nz0
I1, U1, V1, nx1, ny1, nz1
I2, U2, V2, nx2, ny2, nz2, UserFlags ( x Flags)
I3, U3, V3, nx3, ny3, nz3, UserFlags ( x Flags)

0x45 STRIP_CS_UVH_VN I0, U0, V0, nx0, ny0, nz0
I1, U1, V1, nx1, ny1, nz1
I2, U2, V2, nx2, ny2, nz2, UserFlags ( x Flags)
I3, U3, V3, nx3, ny3, nz3, UserFlags ( x Flags)

0x46 STRIP_CS_DS I0, AR0, GB0
I1, AR1, GB1
I2, AR2, GB2, UserFlags( x Flags)
I3, AR3, GB3, UserFlags( x Flags) ...
0x47 STRIP_CS_UVN_DS I0, U0, V0, AR0, GB0
I1, U1, V1, AR1, GB1
I2, U2, V2, AR2, GB2, UserFlags( x Flags)
I3, U3, V3, AR3, GB3, UserFlags( x Flags) ...

0x48 STRIP_CS_UVH_DS I0, U0, V0, AR0, GB0
I1, U1, V1, AR1, GB1
I2, U2, V2, AR2, GB2, UserFlags( x Flags)
I3, U3, V3, AR3, GB3, UserFlags( x Flags) ...

I(n) is a Vertex Index - this is the Index of the
Vertex in the vertex buffer.
U(n),V(n) are the UV coordinates.
There are 2 formats, UVN, and UVH.
UVN Coordinates are stored 0x00 - 0xFF. Divide by
255 to get the Floating point value.
UVH Coordinates are Stored 0x0000 - 0x03FF. Divide
by 1023 to get the floating point value.
AR(n),GB(n) Are halves of a ARGB8888 Color Value.
```


Thanks to Kryslin and SANiK for the spec that documents all of these. SA2 uses type 0x40 and 0x41 from what I know, but I think there are some other types used. Since I'm such a novice, I really don't know what to use to try and read these. So if I can just get some help, it'd be very much appreciated. Thanks in advance!
## Post #2
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-08-29T14:04:06+00:00
- Post Title: [Help]Sonic Adventure 2 Strip reading in MaxScript

A bit late now, but MainMemory is looking into adding support for SA2 in SADXMDL.
## Post #3
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-10-06T03:25:36+00:00
- Post Title: [Help]Sonic Adventure 2 Strip reading in MaxScript

> Reply from ultimaespio
>
> A bit late now, but MainMemory is looking into adding support for SA2 in SADXMDL.
*Notices reply two months later* I already knew about this. I'm the guy who helped him with understanding how the format works. Doesn't change the fact that I still never got the strips loading in Max correctly though.
