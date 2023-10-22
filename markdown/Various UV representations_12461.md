## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-01-03T03:53:15+00:00
- Post Title: Various UV representations

Hi guys I am having a ridiculously difficult time figuring out the UV files for a model I ripped.
I have been able to extract everything from this game except UV
So i am hoping to compile here a list of every method UV can be represented to aid my research

First question, is there a special way UV's are organized when the texture is tiled or swizzled?

You will find below an example of said file

```
{
    int vertCount; //or id
    int type; //14, 15 or 16
    int size; //size of each uv
    int dataSize; //vertCount * size = dataSize
}
//Type is associated with size
//Type:Size 14:8, 15:12, 16:16
//I assume in some cases they have 2 UVs

struct UnknStruct00
{
    int i0; //always 1
    int i1; //always 1
    int i2; //always 0
    int i3; //always 0
    int i4; //always 0
    int i5; //Always a Constant -65536 (which is the minimum short value)
    int i6; //UV offset
    ushort s0,s1; //always 4096 and another increasing value
};

This class doesn't seem important
I had originally thought [b]i5[/b] was a bias but i did not know what to scale it to and why that was necessary.

```


The UV's always have a prefix of 0xFFFF regardless of data being read 4,12,16
0xFFFF word (word, word)

I tried reading the word values as half floats and floats but I always come across negative values or so ridiculous E value
Hence I believe them to be integers

Been staring at this for a long time
[uvChunk.rar](https://xentaxbackup.github.io/file/8419_uvChunk.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-03T08:18:24+00:00
- Post Title: Various UV representations

did you try out unsigned shorts?

# 0x34 (UVBlockSize= 8 )
vt 0.125702 0.332901 
vt 0.375687 0.852448 
vt 0.360168 0.661026 
vt 0.188293 0.196213 
vt 0.875824 0.817276 
vt 0.782074 0.352463 
vt 0.305557 0.832901 
vt 0.266495 0.368088 
vt 0.200104 0.793839 
vt 0.262604 0.329025 
vt 0.000900 0.754776 
vt 0.039963 0.317307 
vt 0.125702 0.332901 
vt 0.360168 0.661026 
vt 0.375687 0.852448 
vt 0.188293 0.196213 
vt 0.875824 0.817276 
vt 0.782074 0.352463 
vt 0.305557 0.832901 
vt 0.266495 0.368088 
vt 0.200104 0.793839 
vt 0.262604 0.329025 
vt 0.000900 0.754776 
vt 0.039963 0.317307 
vt 0.149307 0.813339 
vt 0.047745 0.625732 
vt 0.297760 0.219604 
vt 0.289948 0.563248 
vt 0.422775 0.032120 
vt 0.602463 0.125778 
vt 0.188171 0.688354 
vt 0.000366 0.719559 
vt 0.016418 0.844589 
vt 0.063263 0.063263 
vt 0.875824 0.469589 
vt 0.125824 0.375717 
vt 0.297760 0.219604 
vt 0.047745 0.625732 
vt 0.149307 0.813339 
vt 0.125824 0.375717 
vt 0.875824 0.469589 
vt 0.063263 0.063263 
vt 0.016418 0.844589 
vt 0.000366 0.719559 
vt 0.188171 0.688354 
vt 0.602463 0.125778 
vt 0.289948 0.563248 
vt 0.422775 0.032120 
vt 0.000916 0.277924 
vt 0.000916 0.020416 
vt 0.121979 0.277924 
vt 0.778214 0.082916 
vt 0.286011 0.277924 
vt 0.879745 0.875885 
vt 0.160965 0.277924 
vt 0.559387 0.586838 
vt 0.144989 0.277924 
vt 0.144989 0.524338 
vt 0.160965 0.277924 
vt 0.559387 0.586838 
vt 0.286011 0.277924 
vt 0.879745 0.875885 
vt 0.778214 0.082916 
vt 0.121979 0.277924 
vt 0.286011 0.277924 
vt 0.778214 0.082916 
vt 0.121979 0.762619 
vt 0.160965 0.277924 
vt 0.144989 0.277924 
vt 0.160965 0.277924 
vt 0.286011 0.277924 
vt 0.778214 0.082916 
vt 0.121979 0.277924 
vt 0.000916 0.020416 
vt 0.000916 0.277924 
vt 0.000916 0.762619 
vt 0.000916 0.020416 
vt 0.000916 0.277924 
vt 0.000916 0.020416 
vt 0.000916 0.277924 
vt 0.121979 0.277924 
vt 0.121979 0.762619 
vt 0.000916 0.762619 

If these don't work you'll need an "unswizzle expert".
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-03T09:25:15+00:00
- Post Title: Various UV representations

It's hard to tell with such a small UV set. Can you upload something bigger?

@shakotay2 you're reading little endian in a big endian file
## Post #4
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-01-03T14:55:24+00:00
- Post Title: Various UV representations

I don't know how you got those values but here  is something bigger
The whole UV set for a model.
20 shapes in order.  I couldn't auto calculate the offsets but here are the copied headers

```
struct UVHeader
{
    int vertCount; //or id
    int type; //14,15,16
    int uvSize; //8,12,16  (single uv size)
    int totalSize; //vertCount * uvSize= totalSize
}uvHeader[20]

```

[wholeUV.rar](https://xentaxbackup.github.io/file/8424_wholeUV.rar)
## Post #5
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-01-04T05:12:09+00:00
- Post Title: Various UV representations

I don't know if I need to post textures also.
They are all crazy like this (used [this](http://forum.xentax.com/viewtopic.php?f=18&t=8102)).
[horibe_1p_eye.jpg](https://xentaxbackup.github.io/file/8430_horibe_1p_eye.jpg)
## Post #6
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-04T09:30:55+00:00
- Post Title: Various UV representations

They are definitely half floats, I don't know how you missed them. Are you sure you tried reading them as big endian halves and not little endian?

Here is U #20 - type 14 - 1558 vertices:
[](http://www.imagebam.com/image/1940e5378677553) 

UV #1 - type 15 - 439 vertices - this could be your eye (unswizzled):
[](http://www.imagebam.com/image/11b4b4378678336) 

UV #17 - type 16 - 2257 vertices:
[](http://www.imagebam.com/image/eb4da9378674672)
## Post #7
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-01-04T13:12:48+00:00
- Post Title: Various UV representations

I saw negative values along the way
Never heard of negative uvs.
Half floats were my first thought as well
But I came across version 15 and 16 this confused me. still confuses me

I also do not know how to represent half floats in C# without reverting to unsafe code so I was easily persuaded

I cannot believe I never thought to plot them out. Cos I did so for the bones and verts. 
This game stored bone weights in vector3's

After figuring this out, I hope it will be easy to find out how textures are assigned from xpr2 
cos the texture names are magic
## Post #8
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-04T15:08:39+00:00
- Post Title: Various UV representations

Negative values for UV coordinates are not unheard of.
Yes, in most cases they range from 0 to 1.0, but for example the artist could scale the UV for a tiled texture and not care if it gets negative coordinates.
Other times the whole UV may be shifted by a multiple of +/-1.0, as you can see in my third screenshot. Anything can happen in the mapping process, and if the format allows negative coordinates, the artist won't care.

As for the various types, here's how I see it:
type14 (8bytes):
uint8 color.R
uint8 color.G
uint8 color.B
uint8 color.A
half texture0.x
half texture0.y

type15 (12bytes):
uint8 color.R
uint8 color.G
uint8 color.B
uint8 color.A
half texture0.x
half texture0.y
half texture1.x
half texture1.y

type16 (16bytes):
uint8 color.R
uint8 color.G
uint8 color.B
uint8 color.A
half texture0.x
half texture0.y
half texture1.x
half texture1.y
half texture2.x
half texture2.y

So there are up to 3 UV channels. Yes, some coordinates are 0, but not all. I did plot the other two UVs and they look good.
I'm not 100% sure about the color, but it wouldn't be uncommon to store it along UVs, and white opaque would be default (FF FF FF FF).

I've used this in the past for reading half floats, maybe it will help: [http://csharp-half.sourceforge.net/](http://csharp-half.sourceforge.net/)

Good luck!
## Post #9
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-01-04T15:20:18+00:00
- Post Title: Various UV representations

Thank you so very much. Please don't take 2 weeks holiday ever again 
I read a lot about half floats after seeing your post ( I went to bed with the laptop lol)

I'll check out that library. This is what I found before.

```
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace HalfFloat
{
    class Program
    {
        static void Main(string[] args)
        {
            {
                string hex = "0x3862";
                short h = Convert.ToInt16(hex, 16);

                //From this paper ftp://www.fox-toolkit.org/pub/fasthalffloatconversion.pdf
                float f = ((h & 0x8000) << 16) | (((h & 0x7c00) + 0x1C000) << 13) | ((h & 0x03FF) << 13);
                Console.Write("Short h {0}: is Float {1}  //" + h.ToString("X"), h, f);

                //Same as the half float in 010 Editor
                //http://codereview.stackexchange.com/questions/45007/half-precision-reader-writer-for-c
                f = HalfFloat(Convert.ToInt32(hex, 16));
                Console.Write("\nShort h {0}: is Float {1}  //" + h.ToString("X"), h, f);
            }

            //I thought we had to flip the hex for  Big endians? This failed
            {
                string hex = "0x6238";
                short h = Convert.ToInt16(hex, 16);
                float f = ((h & 0x8000) << 16) | (((h & 0x7c00) + 0x1C000) << 13) | ((h & 0x03FF) << 13);
                Console.Write("\nShort h {0}: is Float {1}  //" + h.ToString("X"), h, f);

                f = HalfFloat(Convert.ToInt32(hex, 16));
                Console.Write("\nShort h {0}: is Float {1}  //" + h.ToString("X"), h, f);
            }
            Console.ReadKey();
        }

        // ignores the higher 16 bits
        public static float HalfFloat(int hbits)
        {
            int mant = hbits & 0x03ff;            // 10 bits mantissa
            int exp = hbits & 0x7c00;            // 5 bits exponent
            if (exp == 0x7c00)                   // NaN/Inf
                exp = 0x3fc00;                    // -> NaN/Inf
            else if (exp != 0)                   // normalized value
            {
                exp += 0x1c000;                   // exp - 15 + 127
                if (mant == 0 && exp > 0x1c400)  // smooth transition
                    return BitConverter.ToSingle(BitConverter.GetBytes((hbits & 0x8000) << 16
                                                    | exp << 13 | 0x3ff),0);
            }
            else if (mant != 0)                  // && exp==0 -> subnormal
            {
                exp = 0x1c400;                    // make it normal
                do
                {
                    mant <<= 1;                   // mantissa * 2
                    exp -= 0x400;                 // decrease exp by 1
                } while ((mant & 0x400) == 0); // while not normal
                mant &= 0x3ff;                    // discard subnormal bit
            }                                     // else +/-0 -> +/-0
            return BitConverter.ToSingle(
                BitConverter.GetBytes(          // combine all parts
                (hbits & 0x8000) << 16          // sign  << ( 31 - 15 )
                | (exp | mant) << 13),0);         // value << ( 23 - 10 )
        }

    }
}

```
