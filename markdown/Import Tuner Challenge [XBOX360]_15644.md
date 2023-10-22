## Post #1
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-12-25T21:08:42+00:00
- Post Title: Import Tuner Challenge [XBOX360]

Hi guys, I got a little progress with the opening of Import Tuner Challenge, unfortunately I am not a programmer and can not are allowed to do all the questions fully.


- Archive opened from QuickBMS
I used this script: [http://aluigi.altervista.org/bms/tokyo_xtreme_racer.bms](http://aluigi.altervista.org/bms/tokyo_xtreme_racer.bms)
[Structure is not folders, all in one]

- Textures in archive from TGA and XPR format
Cars Livery in TGA format [please view Hex code and find in final file "TRUEVISION-XFILE" and rename this dat to * .tga]

Others main cars textures in XPR format [XPR2, Xbox Bundle Container] opened from Noesis script this: [https://www.dropbox.com/s/yehlij6vwpaxd ... R.zip?dl=0](https://www.dropbox.com/s/yehlij6vwpaxd3o/fmt_XBOX_360_XPR.zip?dl=0)
(Noesis XPR Script error from using big size textures files) 
UPDATE: XPR2TGA Tool : [https://www.dropbox.com/s/ecaid3jdks78h ... a.zip?dl=0](https://www.dropbox.com/s/ecaid3jdks78he1/xpr2tga.zip?dl=0)

- Geometry is not converted yet.  
Finally what need help to create script to import geometry from this game ...

Geometry alleged in these files [Perhaps it *.XBM -Xbox360 Genki Model file format [viewtopic.php?f=16&t=12373&p=102509&hilit=xbm#p102509](http://forum.xentax.com/viewtopic.php?f=16&t=12373&p=102509&hilit=xbm#p102509) ]:
[https://www.dropbox.com/s/bnvw5wm9m081z ... 8.dat?dl=0](https://www.dropbox.com/s/bnvw5wm9m081zxw/00000538.dat?dl=0)
[https://www.dropbox.com/s/2ahiuw43bu1e5 ... a.dat?dl=0](https://www.dropbox.com/s/2ahiuw43bu1e5f6/00000c3a.dat?dl=0)

Example extracted textures:
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-25T23:37:59+00:00
- Post Title: Import Tuner Challenge [XBOX360]

00000538_dat_.JPG (79.72 KiB) Viewed 1136 times


(unsure about uvs start address)
## Post #3
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-12-26T06:19:14+00:00
- Post Title: Import Tuner Challenge [XBOX360]

I am so bookmarking this topic. Finally! I'll help if i can though hehehe
## Post #4
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-12-26T08:48:14+00:00
- Post Title: Import Tuner Challenge [XBOX360]

Oh yes what better christmas should we get. I'm so happy I could cry.
## Post #5
- Username: lratafia
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2015 9:27 am
- Post datetime: 2016-12-29T16:37:50+00:00
- Post Title: Import Tuner Challenge [XBOX360]

cool, I hope some good stuff comes out for Assetto Corsa
## Post #6
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-12-29T18:50:35+00:00
- Post Title: Import Tuner Challenge [XBOX360]

We were able to extract all files from game archive, thanks Aluigy
Get access to all textures but with this there are some nuances.

In this moment I'm looking for a versatile way to extract 3d models from this game, very much hope to the aid of those who have an idea of Noesis and 3D Max Script

UPDATE
It was possible to find a way to extract all textures from * .XPR with no errors
[xpr2tga.zip](https://xentaxbackup.github.io/file/12138_xpr2tga.zip)
## Post #7
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-01-14T02:46:45+00:00
- Post Title: Import Tuner Challenge [XBOX360]

Send me the files. If it is anything like their other games then i can help you with the uv
The only problem is knowing what textures go where
## Post #8
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-01-14T12:50:43+00:00
- Post Title: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski
>
> Send me the files. If it is anything like their other games then i can help you with the uv
The only problem is knowing what textures go where
I sent you files in PM
## Post #9
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-01-14T13:44:43+00:00
- Post Title: Import Tuner Challenge [XBOX360]

> Reply from shakotay2
>
> 00000538_dat_.JPG
(unsure about uvs start address)

Quick question. Does it use triangles (list) or triangle strips?
## Post #10
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-01-14T14:30:40+00:00
- Post Title: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski
>
> 

Quick question. Does it use triangles (list) or triangle strips?
As far as I know it uses a Strips
## Post #11
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-01-15T09:29:32+00:00
- Post Title: Import Tuner Challenge [XBOX360]

I tested the sample files you sent with my 010 template and it worked perfectly. 
The only problem is that it's been almost 2 years since i touched this so I have forgotten what some of the data types mean but i got your UVs

Here is the c# version of the data structures (using unity3d)

```
using System;
using System.Collections.Generic;

namespace XBM
{
    //Helper Classes
    
    public struct XBMHeader
    {
        public uint ID;  //00 20 00 00 - Package type (in your game it is different)
        public uint lightCount;
        public uint otherCount; //mesh? group?
        public uint shapeCount;
//------------Line 2---------------
        public uint other2Count;
        public uint[] addrs; //12
        public uint triangleSize;
        public uint shdAddr; //ShaderAddress
        public uint unkn3;
    }

    
    public struct KengoLight
    {
        public char[] name; //[32];
        public float []f0; //[20]
        public char[] data; //[144];
    }

    
    public struct Other //Bone?
    {
        public char[] name; //[32];
        public int[] unkn; //[8];
        public char[] data; //[128];
    } //other[header.otherCount]

    
    public struct Other2 //Bone?
    {
        public char[] data;
    }

    public struct Shape
    {
        public char[] name; //[32];
        public float[] matrix1; //[16];
        //public Vector3[] bbox; //[8]; 
        public Bounds bBox;
        public float[] chnk1; //[4];

        public struct Header
        {
            public int vertCount; //or id
            public int dataType; //0,5,7
            public int unitSize; //Has to do with read size
            public int totalSize; //floatCount or datatsize(float size* 3 or 4)
        } //header0[3]
        public Header hUVs;
        public Header hVerts;
        public Header hNorms;

        public struct UnknStruct00
        {
            public int i0;
            public int i1;
            public int i2;
            public int i3;
            public int i4;
            public int i5; //Constant -65536
            public int i6;
            public int i7; //268435554, 268435746, 268435458
        }
        public UnknStruct00[] sChnk; //[3]; 

        public int addrUV;    //0 = -1s
        public int addrVerts;  //1 = vertices floats
        public int addrTriStr; //2 = faces? shorts?
        public int addr0;      //3 = addr in un02 hdr(size,size,0,size)?
        //------------below are weird ints at the bottom of un03
        public int addrSkVertices;// Verts for skinned mesh
        public int addrSkNormals; // norms for skinned mesh or bone weights
        public int addrSkWeights;
        public int[] chunk3; //[33];
    }

    public struct Addr0
    {
        public uint count;
        public uint size;
        public int unkn0;
        public int unkn1;
        
        public struct Data
        {
            public Vector3 pos;
            public Vector3 rot;
            public Vector3 scale;
            //skip 332
            public const int SKIP0 = 332;

            public uint size;
            public uint addr;

            public const int SKIP1 = 124;
        }

        public Data[] data;
        //float[] f; //[(hdr.size-64)/4];
    }

    
    public struct Addr1 //Skin Verts
    {
        public struct Header
        {
            public uint id;
            public uint fileSize;
            //convert to size
            public uint offset0; //ints
            public uint offset1; //float[4]s
            public uint offset2; //ints
            public uint[] pad; //Pad to next line
        }
        public Header hdr;

        public int[] i0; //[(hdr.addr1-hdr.addr0)/4]; 
        public Vector4[] vec4; //[(hdr.addr2-hdr.addr1)/16]; 
        public int[] i1; //[(hdr.fileSize - hdr.addr2 + hdr.addr0 -32 )/4]; 
    }

    
    public struct Addr1_2 //Skin Verts and normal (addr1 and addr2
    {
        public struct Header
        {
            public uint id;
            public uint unkn0;
            public uint unkn1;
            public uint size;
        }   //hdr <bgcolor=cLtGray>; 
        public Header hdr;

        public Vector4[] vec4; //[hdr.size/16] <bgcolor=cLtBlue>; 
        //float f[hdr.size/4];
    }

    
    public struct XBM_UN03
    {
        public struct UN03_Header
        {
            public uint id;
            public uint count0;
            public uint zero;
            public uint count1;
            //Chunk0
            public uint addr;

            //TRS
            public uint[] transforms; //[3]; Addresses
            //Matrices
            public uint[] matrices; //[3]; Addresses

            public uint[] unkn; //[5];
        }
        public UN03_Header un03_Hdr;

        public struct Item
        {
            //160
            public char[] name; //[32];
            public char[] data; //[128];
        }
        public Item[] item; //[un03_Hdr.count0];
    

        public Vector4[] pos; //[un03_Hdr.count0];
        public Vector4[] rot; //[un03_Hdr.count0];
        public Vector4[] scale; //[un03_Hdr.count0];
    
        public struct Mat4x4
        {
            public Vector4 v0, v1, v2, v3;
        }
        public Mat4x4[] matrix0; //[un03_Hdr.count0];
        public Mat4x4[] matrix1; //[un03_Hdr.count0];
        public Mat4x4[] matrix2; //[un03_Hdr.count0];
    }

    
    public struct Un04_09 //packs of 32
    {
        /*
        
        public struct Pack
        {
            uint id;
            float []data; //7
        }
        */
        //shape related
        // 0 - might be an id/int or 2 shorts
        public float[] un04; //[(header.addrs[5]-header.addrs[4])/4];
        public float[] un05; //[(header.addrs[6]-header.addrs[5])/4];
        public float[] un06; //[(header.addrs[7]-header.addrs[6])/4];   //shape related
        public float[] un07; //[(header.addrs[8]-header.addrs[7])/4];   //shape related
        public float[] un08; //[(header.addrs[9]-header.addrs[8])/4];   //shape related
        public float[] un09; //[(header.addrs[10]-header.addrs[9])/4];   //shape related
    }

    
    public class KengoXBM 
    {
        public XBMHeader xbmHeader;
        public Other[] other; //other[header.otherCount]
        public Shape[] shape; //[header.shapeCount]

        //public Un02 un02; // if((header.addrs[3]-header.addrs[2]) > 0)
        public XBM_UN03 un03; //if((header.addrs[4]-header.addrs[3]) > 0)
        public Un04_09 un04_09;

        //un10 is best not read as it is just a data dump
        //un11 is padding
        //un12 is shaders
    }
}

```


(You can find the UV address in the ShapeHeader struct)
There are 3 types of uv and they have a mixture of float32 float16 or random -1 separators
You will need to use the "Header hUVs;" to decipher its format

```
    public struct UVContainer
    {
        public List<Vector2> UVs0;
        public List<Vector2> UVs1;
        public List<Vector2> UVs2;

        public Vector2[] GetUVs()
        {
            return UVs0 != null? UVs0.ToArray() :  null;
        }
    }

    /// <summary>
    /// 
    /// </summary>
    /// <param name="reader"></param>
    /// <param name="hUV"></param>
    /// <param name="uvC"></param>
    /// <param name="flipVertical"></param>
    void ReadUVChunk(BinaryReader reader, Shape.Header hUV, out UVContainer uvC, bool flipVertical = true)
    {
        List<Vector2> UVs0 = new List<Vector2>();
        List<Vector2> UVs1 = new List<Vector2>();
        List<Vector2> UVs2 = new List<Vector2>();
        
        Byte[] bytes;
        uvC = new UVContainer();
        switch (hUV.dataType)
        {
        case 0:
            for (int i = 0; i < hUV.vertCount; ++i)
            {
                UVs0.Add(Vector2.zero);
            }
            break;
        case 14:
            for (int i = 0; i < hUV.vertCount; ++i)
            {
                //bytes = reader.ReadBytes(4); //White? 0xFFFF
                reader.BaseStream.Position += 4;
                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                float x = BitConverter.ToInt16(bytes, 0).HalfFloat();
                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                float y = BitConverter.ToInt16(bytes, 0).HalfFloat() * (flipVertical? -1:1);
                UVs0.Add(new Vector2(x, y));
            }
            break;
        case 15:
            for (int i = 0; i < hUV.vertCount; ++i)
            {
                //bytes = reader.ReadBytes(4); //White? 0xFFFF
                reader.BaseStream.Position += 4;
                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                float x = BitConverter.ToInt16(bytes, 0).HalfFloat();
                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                float y = BitConverter.ToInt16(bytes, 0).HalfFloat() * (flipVertical ? -1 : 1);
                UVs0.Add(new Vector2(x, y));

                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                x = BitConverter.ToInt16(bytes, 0).HalfFloat();
                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                y = BitConverter.ToInt16(bytes, 0).HalfFloat() * (flipVertical ? -1 : 1);
                UVs1.Add(new Vector2(x, y));
            }
            break;
        case 16:
            for (int i = 0; i < hUV.vertCount; ++i)
            {
                //bytes = reader.ReadBytes(4); //White? 0xFFFF
                reader.BaseStream.Position += 4;
                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                float x = BitConverter.ToInt16(bytes, 0).HalfFloat();
                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                float y = BitConverter.ToInt16(bytes, 0).HalfFloat() * (flipVertical ? -1 : 1);
                UVs0.Add(new Vector2(x, y));

                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                x = BitConverter.ToInt16(bytes, 0).HalfFloat();
                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                y = BitConverter.ToInt16(bytes, 0).HalfFloat() * (flipVertical ? -1 : 1);
                UVs1.Add(new Vector2(x, y));

                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                x = BitConverter.ToInt16(bytes, 0).HalfFloat();
                bytes = reader.ReadBytes(2);
                Array.Reverse(bytes);
                y = BitConverter.ToInt16(bytes, 0).HalfFloat() * (flipVertical ? -1 : 1);
                UVs2.Add(new Vector2(x, y));
            }
            break;
        default:
                if(enableLoging) log += "Unknown UV data type" + hUV.dataType;
            Debug.LogError("Unknown UV data type" + hUV.dataType);
            return;
        }

        uvC.UVs0 = UVs0;
        uvC.UVs1 = UVs1;
        uvC.UVs2 = UVs2;
    }

        //Half float converter
        public static float HalfFloat(this short hbits)
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
                                                    | exp << 13 | 0x3ff), 0);
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
                | (exp | mant) << 13), 0);         // value << ( 23 - 10 )
        }

```
## Post #12
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-01-15T23:05:15+00:00
- Post Title: Import Tuner Challenge [XBOX360]

I am slightly surprised by the level of intrest in this game.
I am doing a 12-hour shift at work tonight when I get back I will give y'all some proper TLC
lmao
## Post #13
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-01-25T17:46:00+00:00
- Post Title: Import Tuner Challenge [XBOX360]

I am having some problems extracting the triangle list for these models.
I previously only focused on skinned meshes for this format and the skinned mes triangles are kept separately from the regular ones


Guys the moral of the story is to always comment your code
## Post #14
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-01-26T07:35:49+00:00
- Post Title: Import Tuner Challenge [XBOX360]

This is bad   , there is a chance of success?
I, too, is unable to get any progress...
## Post #15
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-02-01T02:37:46+00:00
- Post Title: Import Tuner Challenge [XBOX360]

I did get the UV's I just cant get the triangle indices
## Post #16
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2017-02-01T08:09:25+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I looked a file that was posted above named "00000c3a.dat" 
I'm not sure if thats even the same thing you guys are looking at. But the format had geometry in it so I imported it, looks like a light :/ *boring*
## Post #17
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-01T09:12:49+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

mariokart64n
This is very good news)), I sent you a few models of the PM for the test.
## Post #18
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-02-16T14:04:49+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Untitled.png (143.03 KiB) Viewed 520 times


i think i am missing some triangles but the code itself is mostly
I can add a unity script that converts it to OBJ I dont know what exactly you want to use it for
## Post #19
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2017-02-16T16:42:51+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Finally some impressive progress, awesome! 
I'm wondering, what's the polycount for a complete car in stock form?
## Post #20
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-16T20:22:51+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from AMG
>
> Finally some impressive progress, awesome! 
I'm wondering, what's the polycount for a complete car in stock form?
polycount ~50.000 triangles together engine model and high lod interior 
Not all cars have the engine and full interior model such as boss cars, polycount ~35.000


In game Mitsubishi Eclipse Mk.IV boss car model:




Wireframe Mitsubishi Eclipse Mk.IV boss car model, screenshot from JohnHudeski:
[Untitled.png](https://xentaxbackup.github.io/file/12455_Untitled.png)
## Post #21
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-02-17T05:26:13+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I'm glad to see someone's able to get the meshes! Nice to see you alive and kickin' mariokart64n 
Let's hope this one ends in a success.
## Post #22
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-02-17T08:42:45+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

There might be some mistakes regarding my conversion from Trianglestrip to triangle list
I think the last triangle in every submesh is missing

Also most of the cars are made up of parts that you have to combine
eg interior, wheels
I would like to know if the dashboard is also customizable
## Post #23
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-17T09:29:01+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

JohnHudeski

As far as I know, that game menu uses a model with a detailed description of the interior and the engine, but during the race replaced by a low poly interior models
Yes, the interior customized in menu, consist of different models, steering wheel, seats, gauges.

You can put scripts for unity here, I look at the models and say which triangles does not exist, but I do not think it will be a problem as most will have, thanks to you))

I will try to collect a car from models parts and try to describe the process here
## Post #24
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-02-17T14:33:05+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I will post it all on saturday night when I have got a chance to clean it up. It is remarkably similar to the first code I posted
## Post #25
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-17T15:02:44+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Ок, we will wait
## Post #26
- Username: streetracer23
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 28, 2014 8:51 pm
- Post datetime: 2017-02-21T12:50:18+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

How progress ?
## Post #27
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-05T17:05:12+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Things have gotten quiet... I sure hope this does not stop here. Meanwhile on another thread, they're working on Wangan Midnight Maximum Tune related stuff, which is also great.
## Post #28
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-05T18:35:07+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

No work is not stopped)) I do not have enough knowledge on this point to fully implement, as will be the possibility JohnHudeski provide a script for Unity.
And I'll put it in the ImporterTool and its functionality will be ready.
## Post #29
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-08T07:06:48+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I am super sorry guys. I have a part time job that is killing me at the moment.
I will be up for the next 12 hours if blackracer is awake I will transfer my code to his tool

I did not back up my own code so it only works on the import racer for now (No more Kengo support)

edit (1 hour later)
I am removing all the crap functionality as well.
You will need to find away to add multiple models together in your program cos wheels are stored seperately from chassi
as well as lights

edit 2
Wireframe is done
Just last minute checks on triangles

edit 3
After a terrible wild goose chase I have fixed the missing triangles although it adds 1 more for some reason.

Final edit. 
I think it is 100% done. There are some hacks in the code i can't be bothered to fix.
I need an image of the driver's side to confirm something (Mistibushi)
other than that the code should be flawless. Works on my old xbm files as well
## Post #30
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-08T20:49:21+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Untitled.png (79.05 KiB) Viewed 348 times


What is that?
## Post #31
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-08T20:50:44+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Untitled0.png (144.75 KiB) Viewed 263 times


This is my main problem. I think my original fix was deleting triangles
## Post #32
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-08T20:57:50+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Untitled0.png (191.53 KiB) Viewed 262 times


There are even more errors
## Post #33
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-03-08T22:00:16+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Oh shi* this is awesome. Just fantastic. You guys made my day.
## Post #34
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-08T23:07:56+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski
>
> Untitled.png
What is that?
I've looked at images from the real car, and i can tell that the unknown square is the car door's keyhole. The reason for it being square is to save up triangle count by using alpha texture like most racing games.
## Post #35
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-09T00:56:11+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I will just state once again
The source of all our problems come from the fact that the game uses triangle strips and unity does not support this
So I am forced to convert from triangle strips to a triangle list and I am very unsure of the code's accuracy.
## Post #36
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-09T01:23:48+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

```
public static int[] ConvertStripToTriangle(int[] triStrip, Vector3[] vert)
    {
        List<int> triList = new List<int>(); //our new list

        for (int i = 2; i < triStrip.Length; i++)
        {
            bool isEven = (i % 2 == 0);
            int a = triStrip[i - 2];
            int b = triStrip[isEven ? i - 1 : i];
            int c = triStrip[isEven ? i : i - 1];
            string s = string.Format("a:{0}, b:{1}, c:{2}", a, b, c);

            //Tests if we are using over stretched triangles from origin
            if (a == 0 || b == 0 || c == 0)
            {
                float l0 = Vector3.Distance(vert[a], vert[b]);
                float l1 = Vector3.Distance(vert[a], vert[c]);
                float l2 = Vector3.Distance(vert[c], vert[b]);
                float min = Mathf.Min(l0, l1, l2);
                float max = Mathf.Max(l0, l1, l2);
                if ((max / min) > 20)
                {
                    Debug.Log("Potentially faulty triangle" + s);
                    continue;
                }
            }
            triList.Add(a);
            triList.Add(b);
            triList.Add(c);
        }
        return triList.ToArray();
    }

```




Untitled.png (84.95 KiB) Viewed 248 times


No more errors
Please send textures
## Post #37
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-09T13:01:56+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Guys, JohnHudeski is very cool, he did it, it works   

ToyotaVitz Traffic Model in 3ds Max:
## Post #38
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-09T13:05:21+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I am taking a break for a while. Sent the code to Blackracer. It works but could be better
eg need to combine meshes
Texturing is a pain for me.
But you guys should be good

I will come back with improvements
## Post #39
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-09T13:22:05+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski
>
> I am taking a break for a while. Sent the code to Blackracer. It works but could be better
eg need to combine meshes
Texturing is a pain for me.
But you guys should be good

I will come back with improvements
Big thanks man. You and blackracer have done a very great job. BIG thumbs up!
## Post #40
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-09T15:53:53+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

RB26DETT
## Post #41
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-09T15:56:44+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from blackracer
>
> RB26DETT
YES!!! That's exactly the reason why i want to extract models from this game! And also the R34 and it's C-West N2 kit   .
Can't wait until the tool is completely finished!
## Post #42
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-09T16:01:15+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I'm all looking at the models and I cannot begin to refine tool   
Models are excellent!!!
## Post #43
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-10T11:04:58+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

You have to explain to me how you are finding what textures go where
seriously
## Post #44
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-10T14:23:02+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Textures are determined only by the model of the engine and the car, that is, I look at the model let's say this CA18DET means I need to look for Nissan180sx, in hex I do a search through TotalComander. I find XPR and unpack them.



Unfortunately there are no references in * .dat about names   
I did easily separate the files containing Shapes from others * .Dat. I come to the conclusion that need to do the BatchConvert function, there are a lot of files and they need to be sorted somehow.
## Post #45
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-11T10:55:52+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Happy weekend interiors.jpg (85.06 KiB) Viewed 147 times



I have never heard of total commander

How do you know the model is a  CA18DET from the .dat file?
also how is a CA18DET related to a Nissan180sx.

I dont know anything about cars

ps I found the solution to my strip problem
[NvTriStrip](https://github.com/turbulenz/NvTriStrip/blob/master/NvTriStrip/README.txt)
## Post #46
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-11T11:10:18+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski
>
> I have never heard of total commander

How do you know the model is a  CA18DET from the .dat file?
also how is a CA18DET related to a Nissan180sx.

I dont know anything about cars

ps I found the solution to my strip problem
NvTriStrip
CA18DET is the engine used in Nissan 180SX. Found it on wikipedia. I thought it was SR20DET, which was Silvia's engine (cmiiw).
## Post #47
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-11T16:37:46+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

My first car was the Nissan 180 Kouki and it was I who driving it for the first time on a racing track)) 
I will try to sort by file names for the defined auto, but it will take a very long time.
The initial task is to make a fully functional tool.

> Reply from JohnHudeski
>
> I have never heard of total commander

How do you know the model is a CA18DET from the .dat file?
also how is a CA18DET related to a Nissan180sx.

ps I found the solution to my strip problem
NvTriStrip

This is a very common and functional program for working with a large number of files.

I rely only on visual model parts, I have not yet found another way to sort them.

This is very good, as far as I understood in Import Tuner, another method of constructing a triangles is used, has differences from standard.
## Post #48
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-13T11:36:45+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Ok I finally reviewed the code and finished it 99.999%
So you guys can now bug blackracer
## Post #49
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-13T12:47:42+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I'm almost ready for this
## Post #50
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-13T17:08:47+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Oh boy, oh boy!   
Can you explain to me what kind of things that the tool supports? Like besides extracting models of cars for example.
## Post #51
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-13T20:33:54+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

All that is related to cars, wheels, body kits, engines, mufflers and others.
Import of tracks is not supported, it is not needed since it is for WanganMidnight it is made.
We now have a lot of unique tuning parts, and perfect models of cars
## Post #52
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-13T23:41:45+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Ahhh... it'll be great for other games if tracks are supported. But at least it works for cars. Hoping it gets released soon!
## Post #53
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-03-15T11:07:17+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Ah the tracks, that would be awesome, the Shinjuku and Shibuya lines + a lot of highly detailed parking areas are not present in WMPS3.

BTW did you guys know there's a glitch in Import Tuner Challenge that catapults your car in the air? xD
## Post #54
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-15T13:28:08+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from Takukun
>
> BTW did you guys know there's a glitch in Import Tuner Challenge that catapults your car in the air? xD
I don't know that, but i found out that with a max tuned subaru impreza, the car could do a stoppie when you brake at high speed. The back side of the car flying up and the car almost do a front flip. Mind telling me about the catapult glitch? I might try bringing my x360 back to life just to play the game again.

Also, is the tool not yet finished? I'm itching to get my hands on the game's models!
## Post #55
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-03-15T14:44:47+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from REDZOEU
>
> I don't know that, but i found out that with a max tuned subaru impreza, the car could do a stoppie when you brake at high speed. The back side of the car flying up and the car almost do a front flip.

I tried as you suggested with both imprezas but it's not working for me sadly.

I'll just upload a video and link it here (filmed with my shitty smartphone camera as I don't have a capture card).

EDIT: [https://www.youtube.com/watch?v=UhIdr0wdkxI](https://www.youtube.com/watch?v=UhIdr0wdkxI)
## Post #56
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-16T11:21:41+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Wow. Didn't know there's a glitch like that. I might try bringing my x360 back to life and play the game again until i can show you the frontflip glitch (or stoppie glitch).

For now, i'll just wait until the tool is released by JohnHudeski or Blackracer.
## Post #57
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-17T00:40:20+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I can easily support tracks. In fact I was considering porting the game to unity at some stage. Just a few problems exist
-Identifying objects/ naming them from the extractor (Currently the export code provided is not good)
-I don't understand how to read lights or convert them to unity
-placement of car parts. The cars are very customization = many small parts i have to manually place
-biggest problems is identifying what textures go where



Untitled.png (213.21 KiB) Viewed 147 times


Normals and materials are now fixed
## Post #58
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-17T00:42:32+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Untitled.png (65.22 KiB) Viewed 147 times


Reduced number of submeshes for vastly improved performance and easier texturing.
## Post #59
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-03-17T01:07:33+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from REDZOEU
>
> Wow. Didn't know there's a glitch like that.
Well I discovered it on incident. I was slowly driving around Shuto Expwy and enjoying the view when suddenly my car jumped in the air 

@JohnHudeski
That's great news! I personally have no problem with waiting to get a more quality product but everyone's so hyped
## Post #60
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-17T08:07:04+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Hi guys, I'm a little distracted, I'm here again.
Yes, we can try to make support for tracks, the main problem is how to sort and impose textures... With file names complete chaos.
## Post #61
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-17T11:36:55+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

So far, did you search the texture manually for the models?
## Post #62
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-17T14:38:42+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from REDZOEU
>
> So far, did you search the texture manually for the models?
Yes, for me it doesn't seem difficult, I rely on models and features of cars, it will not be easy for other users to do, who do not understand car parts and specs.
## Post #63
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-17T14:54:40+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from blackracer
>
> REDZOEU wrote:So far, did you search the texture manually for the models?
Yes, for me it doesn't seem difficult, I rely on models and features of cars, it will not be easy for other users to do, who do not understand car parts and specs.

This is why i was surprised you got any of them in the first place
## Post #64
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-17T15:08:16+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Hmm what's this?
[http://zenhax.com/viewtopic.php?t=1013](http://zenhax.com/viewtopic.php?t=1013)
[http://zenhax.com/viewtopic.php?f=9&t=957](http://zenhax.com/viewtopic.php?f=9&t=957)

The answer to figuring out what files are what might come from the above 2


[viewtopic.php?f=16&t=12775](http://forum.xentax.com/viewtopic.php?f=16&t=12775)
Is this the same game/format?
## Post #65
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-17T16:29:07+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski
>
> Hmm what's this?
http://zenhax.com/viewtopic.php?t=1013
http://zenhax.com/viewtopic.php?f=9&t=957

The answer to figuring out what files are what might come from the above 2


viewtopic.php?f=16&t=12775
Is this the same game/format?
I don't know what to say about the zenhax webs, but for the xentax one, probably not. I haven't touched the game files since 2015
## Post #66
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-17T21:58:28+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

JohnHudeski
The first topic is my way on zenhax we were able to extract files from the archives. Wangan Midnight uses a completely different structure and file formats.

At the moment I'm analyzing structure of the course map.
## Post #67
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-17T23:32:19+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

The course map should be the same as the regular models for the most part. This is what I believe
We need to figure out how files cross reference each other
Eg how a model id's its texture from an xpr file


Kengo might be an older game than import tuner so maybe it is a bit more naive in implementation (still similar to the PS2)

here is a scene file script

```
SCENE		"STG_06_TONSHO_BG"		"-P3"		"-Z0"	# ‚a‚f
SCENE		"STG_06_TONSHO_GROUND"		"-P3"		"-Z0"	# ’n–Ê
SCENE		"STG_06_TONSHO_GROUND_01"	"-P3"		"-Z0"	# ’n–Êi’ëj
SCENE		"STG_06_TONSHO_NIWA"		"-P2"		"-Z0"	# ’ë
SCENE		"STG_06_TONSHO_WATER"		"-P2"		"-Z0"	# …–Ê
SCENE		"STG_06_TONSHO_GRASS"		"-P2"		"-Z0"	# ‘
SCENE		"STG_06_TONSHO_HEI"				"-Z0"	# •»ˆÍ‚¢
SCENE		"STG_06_TONSHO_MON"		"-P1"		"-Z0"	# –å
SCENE		"STG_06_TONSHO_TATEMONO"	"-P1"		"-Z0"	# “ÔŠŒš•¨
SCENE		"STG_06_TONSHO_TATEMONO_01"	"-P1"		"-Z0"	# “ÔŠŒš•¨
SCENE		"STG_06_TONSHO_TATEMONO_02"	"-P1"		"-Z0"	# “ÔŠŒš•¨
SCENE		"STG_06_TONSHO_TATEMONO_03"	"-P1"		"-Z0"	# “ÔŠŒš•¨
SCENE		"STG_06_TONSHO_TATEMONO_BG"	"-P1"		"-Z0"	# Žü•ÓŒš•¨
SCENE		"STG_06_TONSHO_KOMONO"				"-Z0"	# ¬•¨
SCENE		"STG_06_TONSHO_KOMO_A"				"-Z0"	# ¬•¨(“§–¾j
SCENE		"STG_06_TONSHO_MOTION"				"-Z0"	# “®‚­ƒ‚ƒfƒ‹iŠøj
SCENE		"STG_06_TONSHO_MOTION_01"			"-Z0"	# “®‚­ƒ‚ƒfƒ‹iŽ÷–Øj
SCENE		"STG_06_TONSHO_MOTION_02"			"-Z0"	# “®‚­ƒ‚ƒfƒ‹iƒRƒCj
SCENE		"STG_06_TONSHO_SHADOW"				"-Z0"	# ‰e—pƒ‚ƒfƒ‹
SCENE		"STG_06_TONSHO_KAGE_A"				"-Z0"	# ‰e—pƒ‚ƒfƒ‹
SCENE		"STG_06_TONSHO_KAGE_B"				"-Z0"	# ‰e—pƒ‚ƒfƒ‹
SCENE		"STG_06_TONSHO_FOGCUT"				"-Z0"	# ƒtƒHƒOƒJƒbƒgƒ‚ƒfƒ‹
SCENE		"STG_06_TONSHO_DOOR"				"-Z0"	

SCENE		"STG_06_TONSHO_CHUN"				"-Z0"	# B

TEXTURE		"TON_ALL"

SOUND		"SOUND_06_TONSHO"				# ŠÂ‹«‰¹

OBJ		"OBJ_TON_HEI_WOOD"
OBJ		"OBJ_TON_SHOUJI_A"
OBJ		"OBJ_TON_SHOUJI_B"
OBJ		"OBJ_TON_OKE_A"
OBJ		"OBJ_TON_OKE_B"
OBJ		"OBJ_TON_ANDON_A"
OBJ		"OBJ_TON_ANDON_B"

#LIGHT		"STG_06_TONSHO_LIGHT"					# ƒ‰ƒCƒg
LIGHT		"TONSHO_LIGHT"


RAIL		"RAIL_06_TONSHO"					# ƒŒ[ƒ‹

STATE		"STG_06_TONSHO_STATE"					# ƒGƒfƒBƒbƒgƒf[ƒ^


HIT			"HIT_06_TONSHO.HIT"				# ƒqƒbƒg
CAMERA		"CAM_06_TONSHO.KCF"					# ƒJƒƒ‰




# EOF

```


I was able to recreate the level with the exception of objects (OBJ_....) as there was no instruction on where to place them
and Light cos I could not understand what values were color or rotation but i could figure out directional and point light

lastly i could not figure out wat -P1 or -Z0 meant

If i could a file like this in import tuner then the tracks are done
## Post #68
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-23T17:00:25+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Any new progress here? I'm dying to check out all car models and their tuning parts from this game. If track support has a long way to go, we'll just have to wait until someone's willing enough to help us, or else this project is never going to be completed
## Post #69
- Username: SpulX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 26, 2017 9:45 pm
- Post datetime: 2017-03-26T13:56:16+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Is there any progress i would love my hands on the ae86 levin/trueno files for bodykits etc.
## Post #70
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-03-26T18:11:12+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

ask blackracer
## Post #71
- Username: TyreRubber
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 24, 2016 7:18 pm
- Post datetime: 2017-04-21T00:02:20+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

The original road texture & shader where terrible, hated them. Also the genki decals on highway walls ruined a bit the visuals. Would it be possible to modify and compress back to play in the xbox but with modified resources? I know it would need a chiped console tho.
## Post #72
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-05-22T15:54:14+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Unfortunately, this project is on hold until blackracer comes back. I've sent him a pm but i've never heard from him since. The tool is almost ready though.
## Post #73
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-05-24T10:36:01+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I'm okay with waiting as long as there's a happy end
## Post #74
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-08-07T19:17:49+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Aaand i guess this thread has been abandoned. Nice...
## Post #75
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-08-08T08:09:56+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Man, they were so close... Maybe something happened irl.

At least you can expect me releasing the Minato Mirai area in the next days.
## Post #76
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-08-09T03:28:17+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from Takukun
>
> Man, they were so close... Maybe something happened irl.

At least you can expect me releasing the Minato Mirai area in the next days.

What game are you going to convert the map to? Assetto Corsa?
## Post #77
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-08-09T21:17:40+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from REDZOEU
>
> What game are you going to convert the map to? Assetto Corsa?
I'll convert it to GTA 4 just for fun and then release the .max  or .obj 3D model files directly.
I seriously need SB01/TXR3's textures though, I've tried all kinds of programs (Texmod, Umod, Ninjaripper) with different versions of PCSX2 to rip them but either the emulator crashes or the textures come out flat, for example 128x1, 256x1...
## Post #78
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-08-10T06:33:44+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

If i'm not mistaken, a guy on another topic (GT6 models topic) said that he converted cars from GT PSP, and used textures from GT4 (GT PSP is more like the mobile version of GT4 anyway). Might wanna ask him how he got the textures from PS2 games.

And if he did answer your question and it works, could you share the method here? I'm kinda interested too.
## Post #79
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-08-10T15:26:14+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from REDZOEU
>
> And if he did answer your question and it works, could you share the method here? I'm kinda interested too.
Took my older pc with WinXP x86, installed PCSX2 and now everything works like it should.  Umod still crashes the emulator but Texmod and Ninjaripper work like a charm.
The annoying part though is that they flip the blue and red channels thus leading to have to manually fix 300+ textures, unless there's a simpler way...

EDIT: [Released](http://forum.xentax.com/viewtopic.php?f=16&t=12775&p=133157#p133157)
## Post #80
- Username: Nix56
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 03, 2017 7:39 am
- Post datetime: 2018-07-25T16:24:03+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

this might be a year old but can someone give me a link to the crimson devils car model file from import tuner challenge?
## Post #81
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-07-26T05:32:34+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from Nix56
>
> this might be a year old but can someone give me a link to the crimson devils car model file from import tuner challenge?
We will if we can, but the tools to get the models are not released (yet?). Blackracer was the guy who made the tool. Said he'll release it soon when it's finished, but i never heard from him since.
## Post #82
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-04-13T08:56:04+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from shakotay2 ↑Mon Dec 26, 2016 7:37 am at Mon Dec 26, 2016 7:37 am
>
> 
00000538_dat_.JPG
(unsure about uvs start address)

Hey there shako! been using some of the files of this game to understand more simple structures, and so far worked for traffic cars and engine models, now i have a question, the cars for the player cars might be stored in the xmd files, from which i dont even seem to find face indices, kinda lost there....here a file for demostration... if anyone could be so kind to help in that regard would be much apreciated.

[https://www.mediafire.com/file/ij5jvacs ... e.xmd/file](https://www.mediafire.com/file/ij5jvacsts2631l/00001d7e.xmd/file)
## Post #83
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-05-18T21:51:01+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I am really confused. Why is this not yet a finished project?
I gave Blackracer a lot of time and i posted the code i had.
Where you all just waiting or wasnt it a group project?
I dont understand
## Post #84
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2019-05-19T14:10:02+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski ↑Sun May 19, 2019 5:51 am at Sun May 19, 2019 5:51 am
>
> 
I am really confused. Why is this not yet a finished project?
I gave Blackracer a lot of time and i posted the code i had.
Where you all just waiting or wasnt it a group project?
I dont understand

If I recall correctly, Blackracer doesn't have the skills to properly finalize this. He can only work on cars, but not the map, this is what he said.
## Post #85
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-05-19T14:25:55+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Blackracer just dissapeared and gave away a non working tool XDDD and no, he was kinda alone on his side of the project, me working with srp guys
## Post #86
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-05-19T17:08:36+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Ok. I have the ISO somewhere
Tell me what exactly is remaining.
What doesnt work
## Post #87
- Username: TonySSS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 03, 2017 8:29 pm
- Post datetime: 2019-05-19T17:12:55+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski ↑Mon May 20, 2019 1:08 am at Mon May 20, 2019 1:08 am
>
> 
Ok. I have the ISO somewhere
Tell me what exactly is remaining.
What doesnt work

Yeah hope you would fix his tool he made so that I could convert all of the obscure cars of that game which I happen to have inside my 360 RGH to Assetto Corsa
## Post #88
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-05-19T18:22:05+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski ↑Mon May 20, 2019 1:08 am at Mon May 20, 2019 1:08 am
>
> 
Ok. I have the ISO somewhere
Tell me what exactly is remaining.
What doesnt work

There have been multiple development lines, we have investigated the files, we have already batch extracted the course files for the whole map and parking areas, also kind of having understood a bit of how the cars work, our main problem so far has been both that we dont seem to link UVs properly and the BMS script does some mishaps on the unpacking... I would like to invite you to our srp itc research team to check all what we have done so far, we have a github repository with c code for a custom extraction(to solve tri strips problem) but we havent yet managed to implement it compile it or make it work, also some ideas for python script, even a pseudocode, further more qe can provide the files, we have both a library of the .dat files for cars and the .sdb for tracks, tracks also have been extracted to raw data .obj, we would also like to understand how to deal with ucl, we plan to unpack other txr games from genki, specially the ones from ps2 with another locations and rework both cars and tracks. If you you like to join check our progress and ideas, hit me up om discord at srp, Takkukun and Trawa should also help you if you cant find me, we would be very thankfull for your help!
## Post #89
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-05-19T18:31:08+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

How many of you here can actually program? I did not use BMS for my extraction
also How did you figure out what texture matches  what models
## Post #90
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-05-19T19:00:02+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski ↑Mon May 20, 2019 2:31 am at Mon May 20, 2019 2:31 am
>
> 
How many of you here can actually program? I did not use BMS for my extraction
also How did you figure out what texture matches  what models

we have one programer on C, one for Javascript, and i kind of understand a bit python, but being honest, we are rather new to it and not really what you would call very helpfull, with textures here comes one of the problems, we know that textures are stored in xpr, in cars... we dont fully understand but we can check in xenia with intel GPA for the correct textures on each material, for tracks there is something peculiar going on, most of the sdb are more like a package, those packages might contain the texture inside depending whether it is stand alone; that means, things like roads, lamps and so on, as are the same all across the whole map, use comon textures that are stored separately, but buildings, or signs, have the textures stored in the sdb file, at least, thats what i have understood so far, we are actually working with csplit to split the textures from sdb files while trying to keep the naming to know exactly to which file it does belong to
## Post #91
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-05-19T19:00:49+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from JohnHudeski ↑Mon May 20, 2019 2:31 am at Mon May 20, 2019 2:31 am
>
> 
How many of you here can actually program? I did not use BMS for my extraction
also How did you figure out what texture matches  what models

Did you use oberhummers ucl compression library to open the files?
## Post #92
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-05-19T19:17:49+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

> Reply from Machinedramon ↑Mon May 20, 2019 3:00 am at Mon May 20, 2019 3:00 am
>
> 
JohnHudeski wrote: ↑Mon May 20, 2019 2:31 am
How many of you here can actually program? I did not use BMS for my extraction
also How did you figure out what texture matches  what models


we have one programer on C, one for Javascript, and i kind of understand a bit python, but being honest, we are rather new to it and not really what you would call very helpfull, with textures here comes one of the problems, we know that textures are stored in xpr, in cars... we dont fully understand but we can check in xenia with intel GPA for the correct textures on each material, for tracks there is something peculiar going on, most of the sdb are more like a package, those packages might contain the texture inside depending whether it is stand alone; that means, things like roads, lamps and so on, as are the same all across the whole map, use comon textures that are stored separately, but buildings, or signs, have the textures stored in the sdb file, at least, thats what i have understood so far, we are actually working with csplit to split the textures from sdb files while trying to keep the naming to know exactly to which file it does belong to

Holy cow. That is dedication. You run xenia and manually identify what textures. Cos this was a problem i faced. I got all the models and i could not match the textures

I wrote my own extractor. It was the easiest thing about reversing this game
## Post #93
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-05-19T19:24:12+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

yeah... we have to work with the tools we have, even if that means brute forcing it, as i said, as long as it works, we trying as much as we can with what we have in our hands
## Post #94
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-10-27T20:06:18+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

So, its been some months already and though it might look like the thing has been stuck, been working lots on the hex part and using Model Researcher Pro to come to a semi finished import script for MRP, the script has explained all the steps for any newcomers, im not quite sure if anyone is interested into researching further, i have few theories of my own how the common texture container works, its kinda stated something about it between D0 and 130...

anyways, feel free to dig in and question anything related to it
sorry for the long ass common variable, 800 texts packed there
the image is from the segment B4.sdb
note: this script only works for the course files (sdb) up to 176(thats the first common texture container), subsequent files have their own code for textures in the next texture folder(its the separation between weathers and also types of geometry(parkings and test area are after the 3 instances of the whole map(night, midnight, dawn) and also, given that .obj might only handle 1 uv channel, i did the code to create a mesh for each subsequent uv block(there might be up to 3 uv blocks(uv channels) for each part of the geometry, depending what type of texture it uses might be mapped differently(diffuse, normal, emmisive...)

```
import random
f = mrp.get_bfile()
f.set_byte_order(">")
#these are the header statements, mrp is the module for model researcher pro, random is to create
#random numbers, f= mrp.get_file() is a shortcut for the mrp statements, f.set_byte_order(">") is
#a statement to make the program read the bytes in Big endian order.

#-----------------------------------------------------------------------------------------------
#this is the common texture folder located in 176.dat
common = ['mat_4go_ro_kakiwari','4go_ro_parts00','4go_ro_waku00','4go_ro_waku01','4go_ro_waku03','4go_ro_waku04','4go_ro_waku05','4go_ro_waku06','4go_ro_waku07','4go_ro_waku08','4go_ro_waku09','4go_ro_waku10','4go_ro_waku11','4go_ro_wall00','4go_ro_wall01','4go_ro_wall02','4go_ro_wall03','4go_ro_window00','4go_ro_window01','4go_ro_window02','4go_ro_window03','4go_ro_window05','4go_ro_window09','4go_ro_window10','4go_ro_window11','4go_ro_window12','4go_ro_window_black','HF_TS_a','HF_TS_waku','HF_TS_waku_nml','LD0730m_j','able_00','able_01','able_02','able_03','able_sibuya_00','able_sibuya_01','able_sibuya_02','ami','aruze_00','aruze_01','asagami_00','asagami_01','asahi_a_00','asahi_a_01','asahi_a_02','asahi_b_00','asahi_b_01','asfa00','asfa01','asfa02','auto_back_tx','botom_s_01','botom_s_01_dirty','botom_s_01_nml','botom_s_02','botom_s_02_dirty','botom_s_02_nml','botom_s_03','botom_s_03_nml','botom_s_04','botom_s_04_nml','botom_u_01','botom_u_01_nml','botom_u_02','botom_u_02_nml','botom_u_03','botom_u_03_nml','botom_u_05','botom_u_05_nml','botom_u_06','botom_u_06_nml','botom_u_07','botom_u_07_nml','botom_u_09','botom_u_09_nml','botom_u_10','botom_u_10_nml','brother_00','brother_01','brother_02','brother_03','brother_04','brother_05','brother_06','brother_07','cbon_00','cbon_01','check_00','check_01','chika2_01','chika2_01_00','chika2_01_00_nml','chika2_01_01','chika2_01_02','chika2_01_03','chika2_01_nml','chiobita_a_00','chiobita_a_01','chiobita_a_02','chiobita_a_03','chiobita_a_04','chiobita_a_05','chiobita_a_06','chiobita_b','chiobita_b_00','chiobita_b_01','chiobita_b_02','chiobita_b_03','chiyoda_tnl_top','chiyoda_tnl_top_nml','chiyoda_tnl_wall_01','chiyoda_tnl_wall_01_nml','chiyoda_tnl_wall_02','chiyoda_tnl_wall_02_nml','clarion_00','clarion_01','clarion_02','clarion_03','clarion_04','cora_00','cora_01','cora_02','cora_03','cora_04','cora_05','cup_00','daikan_00','daikan_01','dc_card_00','dc_card_01','denko_r_00','denko_r_00_nml','denko_r_01','denko_r_02','denko_r_03','dhc_00','dhc_01','excelHuman_00','excite_00','excite_01','excite_02','excite_03','excite_04','fence_01','fence_01_nml','fence_02','fence_02_nml','fence_03','fence_03_nml','fence_04','fence_04_dirty','fence_04_nml','fence_05','fence_05_nml','fence_06','fence_06_nml','fence_07','fence_07_nml','fence_09','fence_09_nml','fence_10','fence_10_nml','fence_11','fence_11_door','fence_11_door_nml','fence_12','fence_12_nml','fence_13','fence_13_nml','fence_14','fence_14_grass','fence_16','fence_16_nml','fence_18','fence_18_nml','fence_19','fence_19_nml','fence_20','fence_20_nml','fence_4go_01','fence_4go_01_nml','fence_b','fence_kanaami','fence_kanaami2','fence_kanaami3','fence_kanaami3_nml','fence_kanaami_nml','fence_top','fence_top_nml','first_00','first_01','fujitsu_00','fujitsu_01','g4_ro_a','g4_ro_b','g4_ro_c','gensan_tx','gr3_car','gr3_eneos','gr3_uwall','gr3_wall','gr3_wall2','gr3_wall3','gr3_wall4','gr3_wall5','gr3_wallw','grd_01','grd_01_nml','gyakusou_00','gyakusou_01','hanaharu_a_00','hanaharu_a_01','hanaharu_a_02','hanaharu_a_03','hanaharu_a_04','hanaharu_b_00','hanaharu_b_01','hanaharu_b_02','hanaharu_b_03','hanaharu_b_04','hashira_4go_01','hashira_4go_01_nml','hashira_kon_01','hashira_kon_01_dirty','hashira_kon_01_nml','hashira_kon_02','hashira_kon_02_dirty','hashira_kon_02_nml','hashira_tetsu_01','hashira_tetsu_01_dirty','hashira_tetsu_01_nml','hashira_yoko_01','hashira_yoko_03','hasira_b02','hokusin_00','hokusin_01','hokusin_02','hyundai_00','hyundai_01','jinro_00','jinro_01','jinro_02','jinro_03','jinro_04','jinro_05','jinro_06','jinro_07','jinro_08','jinro_09','jinro_10','jinro_11','joint_a','joint_a_nml','kan_p1_00','kan_p1_01','kan_p1_02','kan_p1_03','kan_p1_04','kan_p1_05','kan_p1_06','kan_p1_07','kan_p1_08','kan_p1_09','kan_p1_10','kan_p1_11','kan_p1_12','kan_p1_13','kan_p1_14','kan_p1_15','kan_p1_16','kan_p1_17','kan_p1_18','kan_p1_19','kan_p1_20','kan_p1_21','kan_p1_22','kan_p1_23','kan_p1_24','kan_p1_25','kan_p1_26','kan_p1_27','kan_p1_28','kan_p1_29','kan_p1_30','kan_p1_31','kan_p1_32','kan_p1_33','kan_p1_34','kan_p1_35','kan_p1_36','kan_p1_37','kan_p1_38','kan_p1_39','kan_p1_40','kan_p1_41','kan_p1_42','kan_p1_43','kan_p1_44','kan_p1_45','kan_p1_46','kan_p1_47','kan_p1_48','kan_p1_49','kanban3go_a','kanban3go_b','kanban3go_c','kanban4go_a','kanban4go_c','kanban4go_e','kanban9go_a','kanban9go_b','kanban9go_c','kanban_4gro_01','kanban_4gro_02','kanban_4gro_03','kanban_4gro_04','kanbanc1_a','kanbanc1_b','kanbanc1_c','kanbanc1_d','kansai_a_00','kansai_a_01','kansai_b','katoolec_00','katoolec_01','katoolec_02','katoolec_03','keep_out_00','keep_out_01','keep_out_02','keep_out_03','keep_out_04','keep_out_05','keep_out_06','keep_out_07','keep_out_08','keep_out_09','keep_out_10','keep_out_11','keep_out_12','keep_out_13','keep_out_14','keep_out_15','ken_00','ken_01','kk_00','kk_01','kk_02','koga_a_00','koga_a_01','koga_a_02','koga_a_03','koga_a_04','koga_a_05','koga_a_06','koga_a_07','koga_b_00','kyosera_00','kyosera_01','kyosera_02','kyosera_03','kyosera_04','lake_00','lake_01','lamp101','lamp201','lamp301','lamp311','lamp701','lamp801','lamp_a','lamp_h','lamp_obj_a','lamp_tnl_01','lanb_gray','leiku_sibu_00','leiku_sibu_01','light','line','line_br','line_br_02','line_br_02_nml','line_br_nml','line_nml','line_y','line_y_nml','mikipuru_00','mikipuru_01','mikipuru_02','mikipuru_03','mikipuru_04','mitui_00','mitui_01','mitui_11go_00','mitui_11go_01','mmc_00','mmc_01','mmc_02','nikon_00','nikon_01','nikon_02','nikon_03','nikon_04','nikon_05','obj_dkk_a','obj_dkk_a_00','obj_dkk_a_00_nml','obj_dkk_a_01','obj_dkk_a_nml','obj_kjkb_01','obj_kjkb_01_nml','obj_pylon_01','obj_pylon_01_nml','oki_00','oki_01','onward_00','onward_01','pa_00','pa_01','parts','parts10','parts11','parts12','parts13','parts14','parts15','parts16','parts17','parts18','parts19','parts2','parts20','parts21','parts22','parts23','parts24','parts25','parts26','parts27','parts28','parts29','parts3','parts30','parts31','parts32','parts33','parts4','parts5','parts8','parts9','parts_hiru00','parts_hiru01','parts_hiru02','parts_ripu00','parts_sibu','parts_sibu2','parts_sibu_ripu','parts_sita00','pentax_00','pentax_01','pilar_foot_1','pilar_foot_1_nml','pl_light','pl_red_01_00','pl_red_01_01','pl_red_01_02','pl_red_02_00','pl_red_02_01','pl_red_02_02','road_01','road_01_dirty','road_01_nml','road_02','road_02_nml','road_haisui_02','road_haisui_02_nml','road_ip_01','rolex_00','rolex_01','saisoncard_00','saisoncard_01','saku_01','saku_01_nml','saku_02','saku_02_nml','saku_03_02','saku_03_02_nml','saku_04','saku_04_nml','saku_05','saku_06','saku_08','saku_08_01','saku_08_02','saku_08_nml','saku_09','saku_09_nml','saku_10','saku_10_nml','saku_11','saku_11_nml','saku_12','saku_12_nml','saku_13','saku_13_nml','saku_14','saku_14_nml','saku_15','saku_15_nml','saku_17','saku_17_nml','samsung_00','sato','sato_4go_00','sato_4go_01','sato_4go_02','sato_4go_03','sato_4go_04','sato_4go_05','sato_4go_06','sato_anim_00','sato_anim_01','sato_yunke','senda_4__5','sglgta_00','sglgta_01','sglgta_02','sglgta_03','shingou_light_0','shingou_light_00','shingou_light_01','shingou_light_02','shingou_light_03','shingou_light_b','shinnihon_00','shinnihon_01','shlgta_00','shlgta_01','shlgta_02','shlgta_03','shock_rw','shock_rw_nml','shock_rwyb','shock_rwyb_nml','shock_shingou','shock_shingou_0','shock_shingou_00','shock_shingou_01','shock_shingou_02','shock_shingou_03','shock_shingou_nml','shock_yb','shock_yb_nml','sibu_car','singou_e','sitamiti00','sitamiti01','starts_00','starts_01','starts_02','starts_03','sumitomo_00','sumitomo_01','syowa_00','syowa_01','syowa_02','syowa_03','syowa_04','syowa_05','syowa_06','syowa_07','syowa_08','syowa_09','syowa_10','syowa_11','syowa_12','syowa_13','syowa_14','syowa_15','syowa_16','syowa_17','syowa_18','syowa_19','syowa_20','syowa_21','syowa_22','syowa_23','syowa_24','syowa_25','syowa_26','syowa_27','syowa_28','syowa_29','syowa_30','syowa_31','syowa_32','syowa_33','syowa_34','syowa_35','syowa_36','syowa_37','syowa_38','syowa_39','syowa_40','syowa_41','syowa_42','syowa_43','syowa_44','syowa_45','syowa_46','t00','t00w','takefuji_00','takefuji_01','tate_kanban00','tate_kanban01','tdk_00','tdk_01','tdk_02','tdk_03','tdk_04','tdk_05','tele_00','tele_01','tele_02','tele_03','tele_04','tele_05','tikei_11go','tochou00','tochou01','tochou02','tochou03','tochou04','tokyotower','toshiba_00','toshiba_01','totan','train_monorail','train_soubu','train_tyuou','train_window','train_yamanote','train_yurikamome','tree_00','tree_01','tree_02','tree_02_lod','tree_03','tree_03_lod','tree_04','tree_04_lod','tree_05','tree_05_lod','tree_06','tree_06_01','tree_06_02','tree_06_nml','tree_07','tree_08_01','tree_11','tree_11_01','tree_grass_01','tree_kakiwari_01','u_wall','u_window','u_window_auto','ufj_00','ufj_01','w_wall_hiru00','w_wall_hiru01','w_wall_hiru02','wal_01','wal_01_dirty','wal_01_nml','wal_02','wal_02_dirty','wal_02_nml','wal_03','wal_03_dirty','wal_03_nml','wal_04','wal_04_dirty','wal_04_nml','wal_05','wal_05_dirty','wal_05_nml','wal_07','wal_07_dirty','wal_07_nml','wal_08','wal_08_nml','wal_11_nml','wal_13','wal_13_nml','wal_14','wal_14_nml','wal_out_01','wal_out_01_nml','wal_pan_01','wal_pan_01_nml','wal_tesuri_01','wal_tesuri_02','wal_tesuri_02_nml','wal_tesuru_01','wall_aka','wall_aka2','wall_aka3','wall_aka4','wall_aka5','wall_ao','wall_ao2','wall_ao3','wall_ao4','wall_ao5','wall_block','wall_bunka','wall_cha','wall_cha2','wall_cha3','wall_cha4','wall_cha5','wall_cha6','wall_cha7','wall_gray','wall_gray10','wall_gray11','wall_gray2','wall_gray3','wall_gray4','wall_gray5','wall_gray6','wall_gray7','wall_gray8','wall_gray9','wall_hiru00','wall_hiru01','wall_hiru02','wall_hiru03','wall_ki','wall_kuro','wall_kuro2','wall_kuro3','wall_kuro4','wall_kuro5','wall_midori','wall_siro','wall_siro2','wall_siro3','wall_siro4','wall_siro5','wall_siro6','wall_toumei','walls_sibu','wallw_aka','wallw_aka10','wallw_aka11','wallw_aka12','wallw_aka13','wallw_aka14','wallw_aka2','wallw_aka3','wallw_aka4','wallw_aka5','wallw_aka6','wallw_aka7','wallw_aka8','wallw_aka9','wallw_ao','wallw_ao2','wallw_ao3','wallw_ao4','wallw_ao5','wallw_ao6','wallw_cha','wallw_cha10','wallw_cha11','wallw_cha12','wallw_cha13','wallw_cha14','wallw_cha15','wallw_cha18','wallw_cha2','wallw_cha3','wallw_cha4','wallw_cha5','wallw_cha6','wallw_cha7','wallw_cha8','wallw_cha9','wallw_glass','wallw_gray','wallw_gray2','wallw_gray3','wallw_gray4','wallw_gray5','wallw_gray6','wallw_gray7','wallw_gray8','wallw_gray9','wallw_kuro','wallw_kuro10','wallw_kuro11','wallw_kuro2','wallw_kuro3','wallw_kuro4','wallw_kuro5','wallw_kuro6','wallw_kuro7','wallw_kuro8','wallw_kuro9','wallw_lodat','wallw_siro','wallw_siro10','wallw_siro11','wallw_siro12','wallw_siro13','wallw_siro14','wallw_siro15','wallw_siro16','wallw_siro17','wallw_siro18','wallw_siro19','wallw_siro2','wallw_siro20','wallw_siro21','wallw_siro22','wallw_siro23','wallw_siro24','wallw_siro25','wallw_siro26','wallw_siro27','wallw_siro28','wallw_siro3','wallw_siro4','wallw_siro5','wallw_siro6','wallw_siro7','wallw_siro8','wallw_siro9','window','window2','window3','window4','window5','window6','window7','window8','window_lod','windowtt','wktunnel_ceil','wktunnel_wall','yahoo_00','yahoo_01','yahoo_02','yoyogi_st_home','zeb','zeb_b','zeb_b_nml','gt_sky0','gt_sky1','gt_sky2','gt_sky3','cube_a_0']
#-----------------------------------------------------------------------------------------------
anim = mrp.create_material("Null")
anim.set_color(10, 10, 10)
#just a material with null, its used for anims given those are special, color (10, 10, 10)

xpr = []
xprmat = {}
#xpr is a container for the selfcontained textures, and xprmat is a dictionary(descontinued in the code)

verts = []
#faces = []
uvs = []
#verts is the vertex container, faces has been moved to per mesh faces container and uvs might have been discontinued

uv1 = []
uv2 = []
uv3 = []
#these are containers just for the uvblocks, that can be up to 3

materials = []
magic_byte = 32
#mat = open('mat.txt', 'w')
#materials is a container for material names, might be discontinued.
#magic_byte is a really interesting thing about the binaries of ITC, most offsets for data fetch are
#by a 0x20 offset, thus why 32

#endofvariables

#f.seek is a move pointer statement, this way i tell the program to go to a certain byte offset
#if f.seek has only one number (656), means that offset from the start, if it has (656, 1), 1 means
#to add that value to current pointer offset, 2 means to count from the end of the file backwards
f.seek(656)
lenght = f.readInt() #number of meshes in the file
#print (str(lenght) + " Elements",file = mat)
f.seek(672)
#print (f.tellHex())

f.seek(1076)
uvblocks = 0 #this is just a initiator for the variable
for i in range(lenght): #this is a loop for as many elements handled
    cursize = f.readInt() #we read a value
    #print (uvblocks, f.tellHex())
    if cursize > uvblocks: # compare the value, if it is bigger it will take the new value
        uvblocks = cursize
    f.seek(508,1)
#this is a loop to check that all the meshes have a certain ammount of uvblocks for the data collection
uvpadding = (uvblocks*4)
#creating the uvpadding by knowing the ammount of uv blocks handled

#print("---------next section----------")
#print("------"+str(uvblocks)+" uv blocks found-------")
#uvpadding = 12
#---------------UVS-------------------
#currentuv = 1
materia = {} #this might have been discontinued
#-------------------------------------
#print (uvblocks)
f.seek(96)
uvstart = (f.readInt() + 32) #where the uv bytes start
f.seek(352)
vc = (f.readInt()) #vertex count
f.seek(8,1)
vertstart = (f.readInt() + uvstart) #start of vertex bytes
f.seek(vertstart)
for i in range(int(vc)): # repeat as many times as vertex count in integer form(real number)
    verts.append(f.read3Float()) #data fetch, means to grab 3 floats in form (x, y, z)
for i in range(uvblocks): #repeat as many times as uvblocks are in the file
    startjump = (i+1)*4 #we create a start jump for each time the file goes through, this means that for each time it will add 1(because i starts at 0) and multiply by 4; 1st time = 4, 2nd time = 8....
    f.seek(uvstart)
    f.seek(startjump,1)
    curruv = i + 1 #given i starts at 0 we add 1, this will be the current uv block handled
    for i in range(int(vc)): #there are as many uvs as Vertex count
        u = f.readHalfFloat()
        v = f.readHalfFloat() *(-1) #we flip vertical
        exec('uv'+str(curruv)+'.append((u,v))') #this is a execution rutine, here we make the programm add the current uv to the variable string and add the uvs to the corresponding uv block container
        f.seek(uvpadding,1) #lastly, we jump the padding we calculated before

#so this part might be a bit confusing, a little explanation, given each file might have own textures, we have to grab them before creating materials, here the break down
#print(uvblocks, len(uv3))
f.seek(104)
jump = (f.readInt()+32) #so, at 104 we find the first clue, we jump to that adress
f.seek(jump)
extra = (f.readInt()*32 + 40)#we come to the shader properties, we want to jump these too, so read how many we have first
jump = (f.readInt() + extra)#also the container has a length of its own, we add them and jump them
f.seek(jump,1)
#time to grab xprtexts
f.seek(12,1) #a very last jump to skip the 0000 indicators for the game
xprtexnum = f.readInt() #number of textures in the xpr container
jump = (xprtexnum*16 + 4) #we jump the offsets for each texture(those will be usefull for the xpr2tga)
f.seek(jump,1)
#print("---------Materials----------",file = mat)
xprcur = 0 #we initialize the current xpr by 0
name = "" #and create an empty name for the code to add characters to
while xprcur < xprtexnum: #while the current xpr is less than the number of textures, loop
    byte = f.readByte() #we read byte by byte
    char = chr(byte) #we convert that byte to character
    if byte == 0: #if the byte is 0, means its end of line(full name completed)
        xpr.append(name) #so we add the name to the container
        xprmat[xprcur] = name #this is the dictionary, means that for the current xpr = name
        name = "" #we reset our name string for the next name
        byte = f.readByte() #and start reading again the first byte
        char = chr(byte)
        xprcur = xprcur + 1 #and lastly we add 1 to the current xpr count
    name = str(name) + str(char) #this is the magic, we add each character to the name as long as we dont get a 0

#this is the mesh creation loop
for i in range(lenght): #for as many elements we have
    curmesha = 0 #initialization for three meshes
    curmeshb = 0
    curmeshc = 0
    faces = [] #and reseting the faces so each mesh has its own faces(that can be used in the three abc, but not along different elements
    #print("Element " + str(i+1),file = mat)
    jump = (672 + i*512) #this is a correcter for the offsets starts, we know that each segment for each element in the header list is 0x200 bytes long(512) and starts at 0x2A0(672)
    f.seek(jump)
    f.seek(128,1)#we jump inside the segment where we locate the information about materials
    texnum = f.readInt()#this is the number of textures each element uses
    #print (str(texnum) + " Tex",file = mat)
    f.seek(12,1)
    a = f.readInt()#here are the indicators for what type of texture(1 is the common folder, 2 is self contained ones)
    b = f.readInt()
    c = f.readInt()
    #print(c , f.tellHex())
    f.seek(20,1)#jump to the exact numbering for each texture
    curelement = i + 1#we create a current element variable that starts by 1(0+1=1)
    numa = f.readInt()#this will be then the number for the exact texture within the folder specified for the uv1
    #print(numa)
    #print(f.tellHex())
    if a == 1:#if the texture is from the common folder
        #print ("UV1 common " + common[numa],file = mat)
        crmta = ('mat_'+common[numa]+' = mrp.create_material("'+str(common[numa])+'")')#we create 2 variables that will be executed to create a mesh with the name of the texture and also the texture path
        crtexa = ('mat_'+common[numa]+'.set_texture(r\"E:\\itc\\textures\\'+str(common[numa])+'.tga\")')#texture path will be E:\itc\textures\(here the texture name).tga
        random0 = random.randint(0,255)#these are random numbers created from 0 to 255 for the color of the faces, might be discontinued
        random1 = random.randint(0,255)
        random2 = random.randint(0,255)
        ran = (random0, random1, random2)#now we jam the 3 together for the (r, g, b)
        crclra = ('mat_'+common[numa]+'.set_color'+str(ran))#and create a code to run an create the color dinamic varibale that uses the name of the material created before
        exec (crmta)#now we execute the 3 codes for the dinamic variables
        exec (crclra)
        exec (crtexa)
        curmesha = common[numa]+str(i)#and then we create a current mesh a name
        curmata = 'mat_'+common[numa]#and also the current material a
        #uv1.append(common[num])
    if a == 2:#if the texture is from the self contained xpr
        #print ("UV1 xpr " + xpr[numa]+" = mat"+str(i),file = mat)
        crmta = ('mat_'+xpr[numa]+' = mrp.create_material("'+str(xpr[numa])+'")')
        crtexa = ('mat_'+xpr[numa]+'.set_texture(r\"E:\\itc\\textures\\'+str(xpr[numa])+'.tga\")')
        random0 = random.randint(0,255)
        random1 = random.randint(0,255)
        random2 = random.randint(0,255)
        ran = (random0, random1, random2)
        crclra = ('mat_'+xpr[numa]+'.set_color'+str(ran))
        exec (crmta)
        exec (crclra)
        exec (crtexa)
        curmesha = xpr[numa]+str(i)
        curmata = 'mat_'+xpr[numa]
        #uv1.append(xpr[num])
    if a == 0:#with a might be special, cause animations might have a 0 index, unlike b or c, so we create 2 instances
        if texnum == 1:#if there is a texture but the index tells us that is 0, we asume its an animation
            #print ("Anim",file = mat)
            curmesha = 'Anim'+(str(curelement))#and just asign the name Anim+number of element
            curmata = 'anim'#just a simple material that is common for all animations(those need to be reworked in 3d editor)
            #uv1.append("Anim")
        else:#but if for some reason we dont have any texture listed and also no index, then we will set the current mesh to Zero(this will also be done for b and c)
            #print ("Null",file = mat)
            curmesha = 0
            #uv1.append("null")
    numb = f.readInt()#this is the number for b texture
    #print(numb)
    if b == 1:#for more information read how a works
        #print ("UV2 common " + common[numb],file = mat)
        crmtb = ('mat_'+common[numb]+' = mrp.create_material("'+str(common[numb])+'")')
        crtexb = ('mat_'+common[numb]+'.set_texture(r\"E:\\itc\\textures\\'+str(common[numb])+'.tga\")')
        random0 = random.randint(0,255)
        random1 = random.randint(0,255)
        random2 = random.randint(0,255)
        ran = (random0, random1, random2)
        crclrb = ('mat_'+common[numb]+'.set_color'+str(ran))
        exec (crmtb)
        exec (crclrb)
        exec (crtexb)
        curmeshb = common[numb]+str(i)
        curmatb = 'mat_'+common[numb]
        #uv2.append(common[num])
    if b == 2:
        #print ("UV2 xpr " + xpr[numb]+" = mat"+str(i),file = mat)
        crmtb = ('mat_'+xpr[numb]+' = mrp.create_material("'+str(xpr[numb])+'")')
        crtexb = ('mat_'+xpr[numb]+'.set_texture(r\"E:\\itc\\textures\\'+str(xpr[numb])+'.tga\")')
        random0 = random.randint(0,255)
        random1 = random.randint(0,255)
        random2 = random.randint(0,255)
        ran = (random0, random1, random2)
        crclrb = ('mat_'+xpr[numb]+'.set_color'+str(ran))
        exec (crmtb)
        exec (crclrb)
        exec (crtexb)
        curmeshb = xpr[numb]+str(i)
        curmatb = 'mat_'+xpr[numb]
        #uv2.append("mat"+str(i))
    if b == 0:
        #print ("Null",file = mat)
        curmeshb = 0
        #uv2.append("null")
    numc = f.readInt()#number for texture C
    #print(numc)
    #print (numa, numb, numc)
    #print(f.tellHex(), len(faces), curmesha, curmeshb, curmeshc)
    
    if c == 1:#same as b and a
        #print ("UV3 common " + common[numc],file = mat)
        crmtc = ('mat_'+common[numc]+' = mrp.create_material("'+str(common[numc])+'")')
        crtexc = ('mat_'+common[numc]+'.set_texture(r\"E:\\itc\\textures\\'+str(common[numc])+'.tga\")')
        #print (crtexc)
        random0 = random.randint(0,255)
        random1 = random.randint(0,255)
        random2 = random.randint(0,255)
        ran = (random0, random1, random2)
        crclrc = ('mat_'+common[numc]+'.set_color'+str(ran))
        exec (crmtc)
        exec (crclrc)
        exec (crtexc)
        curmeshc = common[numc]+str(i)
        curmatc = 'mat_'+common[numc]
        #uv3.append(common[num])
    if c == 2:
        #print ("UV3 xpr " + xpr[numc]+" = mat"+str(i),file = mat)
        crmtc = ('mat_'+xpr[numc]+' = mrp.create_material("'+str(xpr[numc])+'")')
        crtexc = ('mat_'+xpr[numc]+'.set_texture(r\"E:\\itc\\textures\\'+str(xpr[numc])+'.tga\")')
        random0 = random.randint(0,255)
        random1 = random.randint(0,255)
        random2 = random.randint(0,255)
        ran = (random0, random1, random2)
        crclrc = ('mat_'+xpr[numc]+'.set_color'+str(ran))
        exec (crmtc)
        exec (crclrc)
        exec (crtexc)
        curmeshc = xpr[numc]+str(i)
        curmatc = 'mat_'+xpr[numc]
        #uv3.append("mat"+str(i))
    if c == 0:
        #print ("Null",file = mat)
        curmeshc = 0
        #uv3.append("null")
    #for i in range(1):
        #a mesh

    f.seek(jump)#now we jump back to the start of the segment(didnt want to variably calculate the offsets)
    f.seek(336,1)#and jump the material data
    fic = f.readInt ()   #here we read the Face indices for the current segment
    f.seek(44,1)
    fis = (f.readInt() + 32) #and here the start of those faces
    f.seek(fis) #we jump there
    for i in range(int(fic)):#and for as many as there are we scan them and add them to the container faces
        fi = f.readShort()
        #if fi == 65535:
        #    fuckc = fuckc + 1
        faces.append(fi)
    #last = faces[-1]
    #materials.append(last)
    faces.append(65535)#we add as last FFFF to separate each element, else we get faulty tris(well maybe not now that each element is separated xD)
    
    if curmesha != 0:#if the current mesh a is different than 0
        #print(curmesha)
        mrp.create_mesh(curmesha)#we create a mesh with the name of current mesh a
        mesh = mrp.get_mesh(curmesha)#we retrieve the mesh
        mesh.set_vertices(verts)#set vertices the common vertex container
        mesh.swap_vertices("XYZ", "x")#we flip x
        mesh.set_uvs(uv1)#set the uvs for a as uv1(b is uv2 and c uv3)
        mesh.set_uvs_indices(faces,fm="TStripFF")#set the indices of those uvs to be the same as the face indices, in triangle strip FFFF format
        mesh.set_faces(faces,fm="TStripFF")#now the faces
        exec('mesh.set_material('+str(curmata)+')')#and last we set the material for that element
    if curmeshb != 0:#same thing for current mesh b(uv2)
        #print(curmeshb)
        mrp.create_mesh(curmeshb)
        mesh = mrp.get_mesh(curmeshb)
        mesh.set_vertices(verts)
        mesh.swap_vertices("XYZ", "x")
        mesh.set_uvs(uv2)
        mesh.set_uvs_indices(faces,fm="TStripFF")
        mesh.set_faces(faces,fm="TStripFF")
        exec('mesh.set_material('+str(curmatb)+')')
    if curmeshc != 0:#and also for current mesh c(uv3)
        #print(curmeshc)
        mrp.create_mesh(curmeshc)
        mesh = mrp.get_mesh(curmeshc)
        mesh.set_vertices(verts)
        mesh.swap_vertices("XYZ", "x")
        #print(uv3)
        mesh.set_uvs(uv3)
        mesh.set_uvs_indices(faces,fm="TStripFF")
        mesh.set_faces(faces,fm="TStripFF")
        exec('mesh.set_material('+str(curmatc)+')')
    #f.seek(324,1)            
    #end of loop, it will restart faces for the next segment
#this all after is discontinued and thus why as comentary, used most of it for debuging
#crmt = (xpr[i]+' = mrp.create_material("'+str(xpr[i])+'")')
#random0 = random.randint(0,255)
#random1 = random.randint(0,255)
#random2 = random.randint(0,255)
#ran = (random0, random1, random2)
#crclr = (xpr[i]+'.set_color'+str(ran))
#exec (crmt)
#exec (crclr)

#exec('print(dir())')

#for i in range(3):
#    print(uv1[i+640],uv2[i+640],uv3[i+640])
#print ("---------------ok-----------------")
#print(xprmat)
print("check no problems")#if the file has been parsed from start to finish without any problem, it should print this in the console

```

[b4.png](https://xentaxbackup.github.io/file/16957_b4.png)
## Post #95
- Username: TheFalcon19
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 25, 2019 9:42 pm
- Post datetime: 2020-02-12T03:40:39+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Great job figuring out how everything is connected in the course files AND putting together a script.
But because I didn't check this thread since it was posted, I did it the hard way and extracted things without materials and assigned them one by one...oh well.

[https://www.youtube.com/watch?v=GGIQO3jiM20](https://www.youtube.com/watch?v=GGIQO3jiM20)
## Post #96
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2020-02-12T17:05:42+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Wow! Are you gonna release that track? You should get yourself involved with SRP via discord. Or are you already involved? I’m way behind the news, so idk.
## Post #97
- Username: TheFalcon19
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 25, 2019 9:42 pm
- Post datetime: 2020-02-25T01:50:27+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Sorry for the late reply.

Well I plan to release it, I just don't know if there's a "demand" for it, I mean srp already added Shibuya with correct window textures and soon will have Shinjuku. The only things my maps would look different is the objects with multiple uv channels, since I use a different solution for them, but probably even people who played the original games wouldn't really notice it.

I didn't make much progress with my ITC map since that video, because I was also looking at Wangan Midnight's extractor if I can fix it or at least modify it to get correct file1 uv maps...let's just say there's probably going to be video about it in Wangan Midnight thread in a week or two.
## Post #98
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2020-02-28T07:54:28+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

I basically did the whole script as a way of helping SRP, and yeah shinjuku might be on the works.

Also, did you do it through ninja ripping???? XD
## Post #99
- Username: TheFalcon19
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 25, 2019 9:42 pm
- Post datetime: 2020-03-03T01:49:39+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

no, for the most of it I used the free version of model researcher manually putting in adresses and counts
## Post #100
- Username: edy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 15, 2023 2:43 pm
- Post datetime: 2023-06-19T07:53:58+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

Hey, I've been following this topic for a bit now and have been trying to extract the models on my own. I managed to extract the textures but I'm stuck on trying to get the actual 3D models itself. Is there anyway I can convert/extract anything out of the .xmd files? Any help would be great, thanks!
## Post #101
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-14T12:54:19+00:00
- Post Title: Re: Import Tuner Challenge [XBOX360]

any idea where can I find the ITC mesh converter tool? I just wanted to convert Mitsubishi Concept X car into the game and, I looked at this forum but I had no luck for that but only I got luck for textures script part.

link is appreciated.
