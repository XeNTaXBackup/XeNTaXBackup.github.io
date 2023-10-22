## Post #1
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2020-04-03T14:09:37+00:00
- Post Title: EA Renderware Rw4/Rx2 Vertex format Array

I wonder if I could find help here to recognize a EA Xbox 360 renderware (rw4xb2 .rx2) vertex normals and color value types. EA's Simcity uses rw4 files and I can find out vertex array used there with simcitypak tool:


Rw4 vertexFormat hex:


Simcity rw4 first 3 normals stored in obj:
vn  -0.325490200000 0.003921569000 0.945098000000
first 3 normals stored in hex:
X:86 Y:128 Z:248 W:255
Values in obj is calculated by the following formula:
for example X: 86 + (86-255) / 255 = -0.325490200000

Rx2 vertexFormat:


I only need what means vertex normal values 00 2A 21 87 and vertex color values 00 18 28 86 and how it's converted in rx2 vertex block.

Here is samples if anyone is interested in. I split rx2 file to 2 part. part573 is descriptor file and part574 is data.

Rx2 Info for model researcher:
Vertices offset = 0 type float
Count = 824
Padding = 16
Face offset = 0x5A20
fCount= 618 triangles


 rwSamples.zip
(112.21 KiB) Downloaded 14 times
## Post #2
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2020-04-06T10:56:42+00:00
- Post Title: EA Renderware Rw4/Rx2 Vertex format Array

I found more information in this post:
[viewtopic.php?f=16&p=85953#p85953](https://forum.xentax.com/viewtopic.php?f=16&p=85953#p85953)

> Reply from debaser ↑Thu Jun 06, 2013 12:27 am at Thu Jun 06, 2013 12:27 am
>
> 
Hi b0ny and great work...

about weights order flag... some time ago I played with mariokart64n 3ds script.
I remember FVF_TYPE was the key for managing weights order...

copied from the script hoping it will be helpful

...
fn Get_D3DDECLTYPE id= 
(
	case id of 
	(
		...
		0x002C23A5: #FLOAT2
		0x002A23B9: #FLOAT3
		0x001A23A6: #FLOAT4
		...
		0x00182886: #D3DCOLOR
		0x001A2286: #UBYTE4
		0x001A2086: #UBYTE4N
		...
		0x001A2187: #DEC4N
		...
		0x002A2190: #HEND3N
		...
		0x002C235F: #FLOAT16_2
		0x001A2360: #FLOAT16_4
...

0x00182886 is #D3DCOLOR
but
0x002A2187 is still unknown
0x001A2187 is close to that value.

Here is all types that I found:

```
        case D3DDECLTYPE_FLOAT2:    return 1;
        case D3DDECLTYPE_FLOAT3:    return 2;
        case D3DDECLTYPE_FLOAT4:    return 3;
        case D3DDECLTYPE_D3DCOLOR:  return 4;
        case D3DDECLTYPE_UBYTE4:    return 5;
        case D3DDECLTYPE_SHORT2:    return 6;
        case D3DDECLTYPE_SHORT4:    return 7;
        case D3DDECLTYPE_UBYTE4N:   return 8;
        case D3DDECLTYPE_SHORT2N:   return 9;
        case D3DDECLTYPE_SHORT4N:   return 10;
        case D3DDECLTYPE_USHORT2N:  return 11;
        case D3DDECLTYPE_USHORT4N:  return 12;
        case D3DDECLTYPE_UDEC3:     return 13;
        case D3DDECLTYPE_DEC3N:     return 14;
        case D3DDECLTYPE_FLOAT16_2: return 15;
        case D3DDECLTYPE_FLOAT16_4: return 16;
        case D3DDECLTYPE_UNUSED:    return 17;
        default:                    return 17;
```
## Post #3
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2020-04-06T12:04:15+00:00
- Post Title: EA Renderware Rw4/Rx2 Vertex format Array

I found the types from the file in this post. I see normals are stored in value 0x002A2187: #DEC3N
[viewtopic.php?f=16&t=6392&start=555#p87737](https://forum.xentax.com/viewtopic.php?f=16&t=6392&start=555#p87737)

```
(
	case id of 
	(
		0x002C83A4: #FLOAT1
		0x002C23A5: #FLOAT2
		0x002A23B9: #FLOAT3
		0x001A23A6: #FLOAT4
		0x002C83A1: #INT1
		0x002C23A2: #INT2
		0x001A23A3: #INT4
		0x002C82A1: #UINT1
		0x002C22A2: #UINT2
		0x001A22A3: #UINT4
		0x002C81A1: #INT1N
		0x002C21A2: #INT2N
		0x001A21A3: #INT4N
		0x002C80A1: #UINT1N
		0x002C20A2: #UINT2N
		0x001A20A3: #UINT4N
		0x00182886: #D3DCOLOR
		0x001A2286: #UBYTE4
		0x001A2386: #BYTE4
		0x001A2086: #UBYTE4N
		0x001A2186: #BYTE4N
		0x002C2359: #SHORT2
		0x001A235A: #SHORT4
		0x002C2259: #USHORT2
		0x001A225A: #USHORT4
		0x002C2159: #SHORT2N
		0x001A215A: #SHORT4N
		0x002C2059: #USHORT2N
		0x001A205A: #USHORT4N
		0x002A2287: #UDEC3
		0x002A2387: #DEC3
		0x002A2087: #UDEC3N
		0x002A2187: #DEC3N
		0x001A2287: #UDEC4
		0x001A2387: #DEC4
		0x001A2087: #UDEC4N
		0x001A2187: #DEC4N
		0x002A2290: #UHEND3
		0x002A2390: #HEND3
		0x002A2090: #UHEND3N
		0x002A2190: #HEND3N
		0x002A2291: #UDHEN3
		0x002A2391: #DHEN3
		0x002A2091: #UDHEN3N
		0x002A2191: #DHEN3N
		0x002C235F: #FLOAT16_2
		0x001A2360: #FLOAT16_4
		default: #UNKNOWN
	)	
)
```
## Post #4
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2020-04-12T09:10:41+00:00
- Post Title: EA Renderware Rw4/Rx2 Vertex format Array

With the Samples Content Exporter [https://github.com/walbourn/contentexporter](https://github.com/walbourn/contentexporter) I managed to convert .fbx to xbox 360 format .xatg and .pmem. It compress normals to float16_4 by default in current version but maybe older version in xbox 360 sdk support dec3n.  
> It no longer supports compressing normals to the "dec3n" format as there is no DXGI equivalent to that Direct3D 9 format.
Here is my setup to get desired vertex format. I don't want to export binormals and vertextangents.

```
contentexporter -xbox360 -exportbinormals- -computevertextangents- test.fbx
```
