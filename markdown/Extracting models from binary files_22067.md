## Post #1
- Username: rithesh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 27, 2020 1:05 am
- Post datetime: 2020-04-26T17:23:06+00:00
- Post Title: Extracting models from binary files

I am trying to build a tool to export and import binary models from an old DX9 game. The models are packed in a single file and I have managed to extract the relevant parts in hexadecimal.

The data below corresponds to a simple rectangle plane in the game. (First image is the Vertex Buffer and the second image is the Indices)



Vertex Buffer

```
[8B F6 00 00] [9B F6 03 00] [80 FF 80 FF] [FF FF FF FF] [00 00 00 00] [00 00 80 3F]
[75 09 00 00] [65 09 03 00] [80 FF 80 FF] [FF FF FF FF] [00 00 80 3F] [00 00 00 00]
[75 09 00 00] [9B F6 03 00] [80 FF 80 FF] [FF FF FF FF] [00 00 80 3F] [00 00 80 3F]
```


Indices

```
[00 00] [01 00] [02 00] [03 00] [02 00] [01 00]
```


By analyzing the Vertex buffer, I have concluded that it was using the following format. Basically the stride is 24 bytes.

```
{
    CUSTOMVERTEX(FLOAT fx, FLOAT fy, FLOAT fz, DWORD dwcolor, FLOAT fu, FLOAT fv) :
        X(fx), Y(fy), Z(fz), COLOR(dwcolor), U(fu), V(fv) {}
    FLOAT X, Y, Z;
    DWORD COLOR;
    FLOAT U, V;
};

```


I believe the vertex buffer is not in the correct format since i am getting NAN values when I convert them to 32bit floats. Any idea how I can convert these vertices and indices to any 3D file format so that I can open them using blender or 3DS?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-26T17:38:18+00:00
- Post Title: Extracting models from binary files

Sample file?
## Post #3
- Username: rithesh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 27, 2020 1:05 am
- Post datetime: 2020-04-26T18:13:35+00:00
- Post Title: Extracting models from binary files

Here you go:
[https://drive.google.com/file/d/1VvkQHn ... sp=sharing](https://drive.google.com/file/d/1VvkQHn564_x2HzjLYsIkfbxohbNzsjZO/view?usp=sharing)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-26T18:46:22+00:00
- Post Title: Extracting models from binary files

here's your cube (file 2):
.



cube.png (100.31 KiB) Viewed 114 times


File 1: there's floats (6x4 floats) (bounding box I think, not tested) and float uvs, funny. Strange combination with short vertices.

(Correct me if I'm wrong: are there 321 identical cubes in file 1?  )

(Sword is from file 2.)
## Post #5
- Username: rithesh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 27, 2020 1:05 am
- Post datetime: 2020-04-26T20:38:28+00:00
- Post Title: Extracting models from binary files

Thanks a lot! I didn't expect short vertices.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-27T06:52:31+00:00
- Post Title: Extracting models from binary files

Here's a tool for conversion to obj, roughly tested only:


 Make_obj-Project3-test.zip
(56.11 KiB) Downloaded 21 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-27T06:54:57+00:00
- Post Title: Extracting models from binary files

File 1 (1696 meshes, maybe more), all in one clump:
.



file 1.jpg (149.81 KiB) Viewed 88 times
## Post #8
- Username: rithesh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 27, 2020 1:05 am
- Post datetime: 2020-04-27T14:05:32+00:00
- Post Title: Extracting models from binary files

Works great! Thanks a ton.

How are the short vertices converted to float in your tool?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-27T14:46:55+00:00
- Post Title: Extracting models from binary files

```
{
    char *pFBuf ;
    BYTE i, l ;
    int nValue[2] ;
    DWORD k ;
    float lPosXYZ ;

    pFBuf = (char *) lpFBuf ;
    pFBuf += addrV ;
    for (k=0;k < Vcnt;k++) {
        fprintf( stream, "v ") ;
	for (l=0;l<3;l++) {
	    for (i=0;i<2;i++) {						// 1x Word
		nValue[i] = (*pFBuf & 255) ; pFBuf++ ;
	    }
            lPosXYZ= nValue[0] + nValue[1]*256 ;
            if (lPosXYZ>32767) lPosXYZ -= 65536;
	    fprintf( stream, "%f ", lPosXYZ/256.0) ;
	}
	fprintf( stream, "\n") ;
	pFBuf += vStride-6 ;
    }
}
```
