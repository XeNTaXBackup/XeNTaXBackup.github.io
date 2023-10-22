## Post #1
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-08-05T09:29:04+00:00
- Post Title: Soul Calibur 3 [PS2 / Mega-Thread]

Welcome to the Mega-Thread for Soul Calibur 3 [PS2]. In this thread, you can find information about game in it's entirety as it is being throughly researched and analyzed.

This mega-thread serves as the index to find information about Soul Calibur 3 and as such, it does contain some formats common with other Namco and some Tacmo games. The index is still being constructed as information comes and goes, so this thread may be updated several times through it's lifespan.

 Archive Formats:

 Namco/Tecmo Root Archive [*.OLK | PS2/XBOX]
 Namco Archive [*.PKG | PS2/XBOX]
 Namco Text Archive [*.TXT | PS2/XBOX]

 Texture Formats:

 Soul Calibur 3 - Texture Bundle [*.VXT | PS2] (Prepping Thread)
 Soul Calibur 3 - Font File [*.UNK | PS2] (Research Ongoing)

 3D Formats:

 Soul Calibur 3 - Model Format [*.VMP | PS2] [Reply Post]
 Soul Calibur 3 - Motion Data [*.MOT | PS2] (Research Ongoing)

 Sound Formats:

 Soul Calibur 3 - Sound Format [*.MMP | PS2] (Research Ongoing)
 Sofdec - ADX Format [*.AFS | PS2/XBOX/Dreamcast] [Wiki Post]

 Scripting Formats:

 Soul Calibur 3 - Tales of Souls Script [*.TOS | PS2] (Research Rapidly Ongoing)

 Common Resources:

 Soul Calibur 3 - Modding 101 (Prepping Thread)
 Soul Calibur 3 - Modding Tools Resource


NOTE: The threads currently being prepared will take a maximum of 12 hours to publish and update the links of.
NOTE 2: The reserved space is there just in case.
## Post #2
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-08-05T09:31:36+00:00
- Post Title: Soul Calibur 3 [PS2 / Mega-Thread]

Reserved. Just in case...
## Post #3
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2020-08-05T10:11:16+00:00
- Post Title: Soul Calibur 3 [PS2 / Mega-Thread]

Do you plan to analyze the animation format?
## Post #4
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-08-05T14:41:25+00:00
- Post Title: Soul Calibur 3 [PS2 / Mega-Thread]

> Reply from Skykila ↑Wed Aug 05, 2020 6:11 pm at Wed Aug 05, 2020 6:11 pm
>
> 
Do you plan to analyze the animation format?

Thanks for reminding me those exist. Let me edit the mega thread.
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-08-05T15:13:54+00:00
- Post Title: Soul Calibur 3 [PS2 / Mega-Thread]

I had written a maxscript to import geometry from SC3 into 3dsmax here;
[viewtopic.php?p=162231#p162231](https://forum.xentax.com/viewtopic.php?p=162231#p162231)

I was asked to share a break down on the mesh format...

To get started I recommend downloading this package I have provided:


 sc3_vmp_demo_package.zip
(82.51 KiB) Downloaded 31 times



..and you can follow along with me as I step through the format. its important that you refer to the file in the package named "vmp_format.h"
This contains C style structures which I will be referring to as I walk through the format.

However if you wish to make your own implementation, read my maxscript which is in the package called "vmp_imp__by_mariokart64n.ms" everything is shown in black and white

I will now attempt to explain this the best I can, just be aware this just gives a very basic outline

Myself
Hi my Name is Corey I joined Xentax 15 years ago being interested in modding but having no background in computer science or programming. However throughout the years I have explored file formats in my spare time and have enjoyed writing mesh import and export plugins in 3dsmax.

History
Format was initially broken by fanfurry then probably factduck and then zaramot gained interest in it. He contacted me while I was working on SC2 and I provided some info I had. I believe that all three parties had created a version of importer however none had released anything to the public. I had held out looking at the format hoping one of them would just drop a program but decade later nothing. So with some extra time I had, I spent 3 months plotting and reversing and coding my own version of importer. I would like to credit pringerx, whom gave the most complete summarization of the format that help me in my discovery phase of the format
[viewtopic.php?p=47019#p47019](https://forum.xentax.com/viewtopic.php?p=47019#p47019)

Overview
**Please refer to “block_diagram.png” 
The mesh data is stored in a rather typical PS2 way, the trick had always been how the hell do you get there?! In the diagram I supplied you can see arrows which represent the pointers that you must to read in order to follow to the next block. So for example to get to the geometry block you need to parse the following blocks, read the pointer and jump to the next block read the next pointer and so on until you reach the geometry.

[HEADER] -> [TABLE4] -> [TABLE1A] - > [TABLE1B] -> [TABLE1C] -> [TABLE1D] -> [GEOMETRY]

Ironically there are multiple ways you can get to the geometry by reading different blocks that end up pointing to the same spot.. so just refer to the block out diagram “block_diagram.png” and be as inventive as you want!




**BEFORE YOU ASK EVERYTHING REFERRED TO IN THE EXAMPLE VMP IS LITTLE ENDIAN **
**USED DATA TYPES** 
Char = 8bit signed integer
Unsigned char = 8bit unsigned integer
Unsigned short = 16bit unsigned integer
Unsigned long = 32bit unsigned integer
Float = 32bit single-precision floating-point standard: IEEE 754
Header
**please refer to file “vmp_format.h” and open “vmp_sample.vmp” in a hex editor and follow along


```
	unsigned long filetype;
	unsigned char unk001;
	unsigned char unk002;
	unsigned char unk003;
	unsigned char unk004;
	unsigned short table1_count;
	unsigned short bone_count;
	unsigned long unk005; // total number of vertices
	unsigned long unk006;
	unsigned long unk007;
	unsigned long unk008;
	unsigned long unk009;
	unsigned long bone_addr;
	unsigned long tex_file_addr;
	unsigned long table1a_addr;
	unsigned long table5_addr;
	unsigned long table4_addr;
	unsigned long table7_addr; 
	unsigned long unk016; 
	unsigned long table1_addr;
	unsigned long table2_addr;
	unsigned long table3_addr;
	unsigned long table6_addr;
	};
```


```
00000000   09 0E 1C 0B 00 00 01 02  02 00 02 00 88 04 00 00
00000010   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00
00000020   B0 57 00 00 80 58 00 00  80 00 00 00 4C 01 00 00
00000030   B0 00 00 00 60 0D 01 00  00 00 00 00 4C 00 00 00
00000040   A0 00 00 00 A4 00 00 00  08 05 00 00
```


Pretty much self-explanatory, uh but Lets Go!!! Yoooo!!

In the Hex snippet above I will chart out what my return values we would return to the variables in the “vmp_header” structure

```
unk001 = 0x00
unk002 = 0x00
unk003 = 0x01
unk004 = 0x02
table1_count = 0x0002
bone_count = 0x0002
unk005 = 0x00000488
unk006 = 0x00000000
unk007 = 0x00000000
unk008 = 0x00000000
unk009 = 0x00000000
bone_addr = 0x000057B0
tex_file_addr = 0x00005880
table1a_addr = 0x00000080
table5_addr = 0x0000014C
table4_addr = 0x000000B0
table7_addr = 0x00010D60
unk016 = 0x00000000
table1_addr = 0x0000004C
table2_addr = 0x000000A0
table3_addr = 0x000000A4
table6_addr = 0x00000508
```


If you can follow along with this then you will be able to follow the rest of the structures on your own

Table1

```
	unsigned long addr_table2_entry;
	};
```


As per table1_addr and table1_count Offset to 0x4C and your going to read 2 “unsigned long” as per “vmp_table1” 
You will get the following addresses:

```
00000050   8C 00 00 00
```


Table1a

```
	unsigned char* indices;
	};
```


```
	unsigned long unk1;
	float unk2;
	float unk3;
	};
```


```
	float unk1;
	unsigned long unk2;
	unsigned long unk3;
	unsigned long unk4;
	};
```


```
	unsigned char unk[156];
	};
```


```
	unsigned char type;	// 0 = Static Mesh | 1 = Skinned Mesh
	unsigned char count;
	unsigned char unk023;
	unsigned char unk024;
	vmp_table1a_type_1 type1_data;
	vmp_table1a_type_2 type2_data;
	vmp_table1a_type_3 type3_data;
	vmp_table1a_type_4 type4_data;
	unsigned long unk025;
	unsigned char* addrs;
	};
```

In Table1 you would have obtained the offset to each table1a entry. The first entry is at 0x80 and the second entry is at 0x8C

```
00000084   00 00 00 00 90 05 00 00  00 01 03 01
00000090   00 00 00 00 98 05 00 00
```


Using this I will show what values I get on the first entry in the structure “vmp_table1a”

```
count = 0x01
unk023 = 0x07
unk024 = 0x00
unk025 = 0x00000000
addrs = {0x00000590}
```


Note that “count” decides how many “unsigned long” values to read into “addrs” and that if you have a “type” value greater then 0 then additional data it will present itself after “unk024”. Values 1 – 4 have been documented as values for “type” in the event 1 is read refer to the struct “vmp_table1a_type_1” on how to read that data and so forth for vmp_table1a_type_x (1 - 4)

Table1b

```
	unsigned char unk025;
	unsigned char unk026;
	unsigned char unk027;
	unsigned char unk028;
	unsigned long addr; // table1c_addr
	};
```


```
00000598   00 00 00 00 80 04 00 00
```


From reading the structure in table1a you should have collected 2 pointers; vmp_table1a::addrs{0x 00000590 , 0x 00000598} Follow these offsets to get to each respective Table1b entry 

For example this is what I get for the first entry 

```
unk026 = 0x00 
unk027 = 0x00
unk028 = 0x00
addr = 0x 00000380
```

Table1c

```
	unsigned char type;
	unsigned char size;
	unsigned char unk072;
	unsigned char unk073;
	};
```


```
	};
```


```
	unsigned long unk083;
	unsigned long unk084;
	unsigned long unk085;
	unsigned long unk086;
	unsigned long unk087;
	};
```


```
	unsigned long unk088; // texture addrress
	unsigned long unk089; // texture addrress
	float unk090;
	float unk091;
	};
```


```
	unsigned long table1d_addr; // address to mesh table
	};
```


```
	unsigned long mat_addr; // address to floats, seems like diffuse colours etc
	};
```


```
	unsigned char unk079;
	unsigned char unk080;
	unsigned char unk081;
	unsigned char unk082;
	};
```


```
	vmp_table1c_chunk header;
	vmp_table1c_cmd01* cmd01_info;
	vmp_table1c_cmd02* cmd02_info;
	vmp_table1c_cmd03* cmd03_info;
	vmp_table1c_cmd05* cmd05_info;
	vmp_table1c_cmd10* cmd10_info;
	vmp_table1c_cmd11* cmd11_info;
	};
```


The way this block works is you read a ID and according to the id you are presented with different data. I refer to this as a id chunk format, or a tag format..

Lets read the first chunk header at 0x380 into the struct “vmp_table1c_chunk”

```
00000380   0B 0C 87 00
```


```
type = 0x0B
size = 0x0C
unk072 = 0x87
unk073 = 0x00

```

type is 0x0B or 11 in decimal so refer to structure “vmp_table1c_cmd11” on how to read the preceding data.

```
00000380   0B 0C 87 00 00 00 01 00  00 00 00 00
```


In general reading of this area is fairly safe as when you encounter a unknown id, you simply use the size to skip past the unknown block. 

Note that I never found out how the file defines the amount of chunks to read, or if they use a termination id to stop. I just read until I reached the end of that section, you can refer to the block diagram to see which section proceeds which is table6. So.. read until a few conditions are met, until you reach 0, or if you reach the end of the stream, or until you reach table6.

for reading of the next table you must read data from type5, here is an example of what I read from entry 1 of table1c

```
000003A0               05 08 00 00  A0 05 00 00
```


```
vmp_table1c_cmd05::table1d_addr = 0x 000005A0
```


Table1d

```
	};
```


```
	unsigned long addr;
	};
```


```
	};
```


```
	unsigned char unk094;
	unsigned char unk095;
	unsigned char unk096;
	unsigned char unk097; // type?
	vmp_table1d_type16* table1d_type16;
	vmp_table1d_type48* table1d_type48;
	vmp_table1d_type96* table1d_type96;
	};
```


```
000005A0   62 00 00 30
```


I believe this is another chunk format, however I wasn’t sure, in my structure for “vmp_table1d”
The id or tag is “vmp_table1d:: unk097”

In the entry I had gotten from the address in table1c type5 I got 
unk097 = 0x30 or 48 in decimal

```
000005A0   62 00 00 30 90 08 00 00 
```


So I will use the structure “vmp_table1d_type48” to read the preceding data..

```
vmp_table1d_type48::addr = 0x00000890
```

Geometry

```
	unsigned char unk100;	// 1
	unsigned char unk101;	// 1
	unsigned char unk102;	// 0
	unsigned char unk103;	// 1
	unsigned char unk104;
	unsigned char unk105;
	unsigned char unk106;
	unsigned char unk107;
	unsigned long unk108;
	unsigned char unk109;
	unsigned char unk110;
	unsigned char unk111;
	unsigned char unk112;
	unsigned long unk113;
	unsigned long unk114;
	};
```


```
00000890   01 01 00 01 00 80 01 6C  26 80 00 00 00 40 3E 30
000008A0   12 04 00 00 0F 00 00 00  04 01 00 01 03 80 26 6C
```

** If things were not shady enough, this entire section here is comprised of hacks and guesses**
**YOU’VE BEEN WARNED!**

I never formed any strong functions around the PS2 VIF format, so this is all rather sketchy, here are the value read into the vif_header structure

```
unk101 = 0x01
unk102 = 0x00
unk103 = 0x01
unk104 = 0x00
unk105 = 0x80
unk106 = 0x01
unk107 = 0x6C
unk108 = 0x00008026
unk109 = 0x00
unk110 = 0x40
unk111 = 0x3E
unk112 = 0x30
unk113 = 0x00000412
unk114 = 0x0000000F
```

AND I UNDERSTAND NONE OF IT :’(

However I do extrapolate the buffer size from “vif_header” by doing this calculation:

```
buffer_size = ((((unk107 & 0x0F) / 4) + 1) * 4) * unk106) - 8
```


If the buffer size is 8 then the data is stored in format 0 else its stored in format 1.
In this example its in format 0 which means the data is a STATIC mesh and has no blend weights

Unfortunately my understanding of the VIF header is so poor so I look ahead and try to identify a particular signature. 
 In this example this is what I read

```
000008A0                            04 01 00 01 03 80 26 6C
```


I’ll just give this structure a struct for now but in my maxscript I don’t have one

```
	unsigned char h1;
	unsigned char h2;
	unsigned char h3;
	unsigned char h4;
	}
```


```
	unsigned char c1;
	unsigned char c2;
	unsigned char c3;
	unsigned char c4;
	}
```


Because I’ll be using the vif_strip_info values I’ll show how they would be read here

```
C2 = 0x80
C3 = 0x26
C4 = 0x6C
```


If I see the number 0x80 at offset 0x05 then I then read the data, else I skip it! 
In the example above I happened to have 0x80 (c2) at offset 0x08AD so I did a read.

C1 values should be between 0 – 4 and depending on which value it indicates which data is in the buffer

```
	0x00: No_data
	0x01: uvs
	0x02: colours
	0x03: positions
	0x04: normals
	};
```

The structs for each are as such

```
	float u; float v;
	};
```


```
	unsigned char r; unsigned char g; unsigned char b; unsigned char a;
	};
```


```
	float x; float y; float z;
	char unk1
	char unk2
	char unk3
	char unk4
	};
```


```
	float x; float y; float z;
	};
```


In the event a value on c1 was not in out of bounds, we can skip the entire buffer this way
b
```
uffer_size = (((((c4 & 0x0F) / 4) + 1) * 4) * c3))
```


so in my example these were the values I plugged in

```
(((((0x6C & 0x0F) / 4) + 1) * 4) * 0x26)) = 608 bytes
```


The vertex compo type was 3 so the data was vertex positions

```
00002224   1F DA 67 BE 52 75 99 3C  67 00 BA BC F0 8F 00 00
00002240   1F DA 67 BE EA 59 B5 39  C0 E2 0D BD F0 8F 00 00
00002256   BF EE 6E BE EA 59 B5 39  1A 98 47 BC F0 0F 00 00 
00002272   1F DA 67 BE 49 6F 93 BC  67 00 BA BC F0 0F 00 00 
00002288   1F DA 67 BE 49 6F 93 BC  CD C4 47 BA F0 0F 00 00
00002304   1A 74 E1 3D 49 6F 93 BC  CD C4 47 BA F0 8F 00 00
00002320   0A D0 48 BE EA 59 B5 39  B3 5A 28 3C F0 8F 00 00
00002336   1A 74 E1 3D EA 59 B5 39  B3 5A 28 3C F0 0F 00 00
00002352   0A D0 48 BE 52 75 99 3C  CD C4 47 BA F0 0F 00 00
00002368   1A 74 E1 3D 52 75 99 3C  CD C4 47 BA F0 0F 00 00 
00002384   0A D0 48 BE 52 75 99 3C  67 00 BA BC F0 0F 00 00
00002400   1A 74 E1 3D 52 75 99 3C  67 00 BA BC F0 0F 00 00
00002416   0A D0 48 BE EA 59 B5 39  C0 E2 0D BD F0 0F 00 00 
00002432   1A 74 E1 3D EA 59 B5 39  C0 E2 0D BD F0 0F 00 00
00002448   0A D0 48 BE 49 6F 93 BC  67 00 BA BC F0 0F 00 00
00002464   1A 74 E1 3D 49 6F 93 BC  67 00 BA BC F0 0F 00 00 
00002480   0A D0 48 BE 49 6F 93 BC  CD C4 47 BA F0 0F 00 00
00002496   1A 74 E1 3D 49 6F 93 BC  CD C4 47 BA F0 0F 00 00
00002512   0A D0 48 BE EA 59 B5 39  B3 5A 28 3C F0 0F 00 00
00002528   1F DA 67 BE 49 6F 93 BC  CD C4 47 BA F0 8F 00 00
00002544   1F DA 67 BE EA 59 B5 39  B3 5A 28 3C F0 8F 00 00
00002560   BF EE 6E BE EA 59 B5 39  1A 98 47 BC F0 0F 00 00  
00002576   1F DA 67 BE 52 75 99 3C  CD C4 47 BA F0 0F 00 00 
00002592   1F DA 67 BE 52 75 99 3C  67 00 BA BC F0 0F 00 00
00002608   1F DA 67 BE EA 59 B5 39  B3 5A 28 3C F0 8F 00 00
00002624   0A D0 48 BE 49 6F 93 BC  CD C4 47 BA F0 8F 00 00 
00002640   1F DA 67 BE 49 6F 93 BC  CD C4 47 BA F0 0F 00 00 
00002656   0A D0 48 BE 49 6F 93 BC  67 00 BA BC F0 0F 00 00
00002672   1F DA 67 BE 49 6F 93 BC  67 00 BA BC F0 0F 00 00
00002688   0A D0 48 BE EA 59 B5 39  C0 E2 0D BD F0 0F 00 00 
00002704   1F DA 67 BE EA 59 B5 39  C0 E2 0D BD F0 0F 00 00
00002720   0A D0 48 BE 52 75 99 3C  67 00 BA BC F0 0F 00 00
00002736   1F DA 67 BE 52 75 99 3C  67 00 BA BC F0 0F 00 00
00002752   0A D0 48 BE 52 75 99 3C  CD C4 47 BA F0 0F 00 00
00002768   1F DA 67 BE 52 75 99 3C  CD C4 47 BA F0 0F 00 00
00002784   0A D0 48 BE EA 59 B5 39  B3 5A 28 3C F0 0F 00 00
00002800   1F DA 67 BE EA 59 B5 39  B3 5A 28 3C F0 0F 00 00
00002816   0A D0 48 BE 49 6F 93 BC  CD C4 47 BA F0 0F 00 00
```


CONCLUSION
I'm terribly sorry if this walk through was very disjointed, I pulled an all nighter just to get this post up for TopazTK in time and I'm legit running off 3 hours sleep. Also I wrapped this project up several months ago now so I likely left a lot important nuggets of info   

I can tell you for sure that I remember that my maxscript failed on Character Creator Models, so there is certainly data blocks in the file that still need to be deciphered 

If you have any questions please let me know
## Post #6
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-08-05T15:27:15+00:00
- Post Title: Soul Calibur 3 [PS2 / Mega-Thread]

> Reply from mariokart64n ↑Wed Aug 05, 2020 11:13 pm at Wed Aug 05, 2020 11:13 pm
>
> 
I was asked to share a break down on the mesh format...

Absolute excellence! I have updated the mega-thread to redrect people to this reply for the VMP format. However, a seperate thread may be needed to encourage discussion. Thank you so much for this post!
