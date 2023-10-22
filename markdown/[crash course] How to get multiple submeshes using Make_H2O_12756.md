## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-08T23:25:45+00:00
- Post Title: [crash course] How to get multiple submeshes using Make_H2O

As you may know it's a little bit tedious to use hex2obj on models with more than 3 or 4 submeshes.

So after you got the format parameters for the first submesh you very likely would code some maxscript
to get the whole model.

If you don't own 3dsmax but know "C" here's another way to get the submeshes (bones/weights not handled).

It's a crash course in three parts:

1. part: How to analyse simple 3D formats with multiple submeshes
2. part: How to write a "collect multiMeshes" function in "C" for Make_H2O
3. part: How to create and import the obj files

We will use Make_H2O, hex2obj and blender (v2.49b or v2.69 and above).

requirements:
Basic understanding of "C" coding
Basic knowledge about 3D models


 Part 1: "How to analyse simple 3D formats"
--------

As always you've to analyse the format and create a H2O file for the first submesh using hex2obj.
Some formats like MLX for example use tables which contain the counts for all submeshes.

But often formats use repeating structures to define a submesh header. For Sly Cooper TiT
you can get the required params from this picture: 1807_MDL.jpg:
[](http://www.pic-upload.de/view-27180258/1807_MDL.jpg.html)

 Part 2: How to write a "collect multiMeshes" function in "C" for Make_H2O
--------

subject: "Sly Cooper: Thieves in Time" mdl model

abstract: After we've understood the mdl format we're going to create H2O files
 for all submeshes contained in the sample mdl to be found here:

[viewtopic.php?f=16&t=11229&p=93788&hili ... ves#p93788](http://forum.xentax.com/viewtopic.php?f=16&t=11229&p=93788&hilit=sly+cooper+thieves#p93788)
(Thx to o0demonboy0o)

(If you want to skip the coding part just head to Part 3 now.)


Introduction: What is Make_H2O? - It's a Codeblocks 13.12 project written in "C"
              to create H2O files for hex2obj.

preparations: To get the count of submeshes search for "MHDR" in the Mesh_1807.mdl file.
 It's found 5 times.
vertex stride is 26 (gained by basic knowledge)

Though "SMSH" is probably the start of the submesh headers we will use "MHDR".

start of first submesh block: 0x30  ("MHDR")
offset to vertex count: 9
relative offset to face indices count: 2

That's all to know.


Now we simply have to use the above infos and implement the two formulaes shown in 1807_MDL.jpg 
The following code is used to get the submeshes from Mesh_1807.mdl.

We are using a pointer to char (char *pFBuf) to scan the file data in a static buffer.

(You don't need to care for create_H2O(): It should be useable with all models hex2obj can handle.)

remark: the code of this function is updated in the zip

```
{
   char * pFBuf ;
   BYTE * pByte, cnt, i ;
   int cnt1, nValue[16] ;        //
   WORD  wFaceIndCnt, wVertsCnt ;
   DWORD addrFI, addrUV, addrV, j, offs2, oldJ ;  //

    // ###  line to be changed for other models than MLX! ###
    //char lines[6][20]= {"","Vb1","76 40","","021000","0x0 255"} ;   // [6][16] sollte reichen?
    //char lines[6][20]= {"","Vb1","12 99","","120300",""} ;          // Capt'n A.
    char lines[6][20]= {"","Vb1","26 10","","120201",""} ;            // Sly Cooper TiT

    //0x124D0 1469          this is the ref H2O file for the first submesh of "DL020A_SD002J.MLX"
    //Vb1 -> lines[1]       which you'll get after having found out the format and saving the H2O in hex2obj
    //76 40 -> [2]
    //0x1BC20 701           this line's contents varies (same with first line)
    //021000 -> [4]
    //0x0 255- > [5]

   pFBuf = (char *) lpFBuf ; j= 0 ;
   pFBuf += dwStart ; j += dwStart ;                            // dwStart: start of first submesh at 0x30, from editbox
   addrUV = 0 ;     // zero for VB mode (hex2obj)
   for (cnt=0;cnt<5;cnt++) {                                    // 5: count of submeshes
        pFBuf += 9 ; j += 9 ;                                   // point to vertex count
        pByte = (BYTE*) &wVertsCnt ;						    // get vertex count
        for (i=0;i<2;i++) {									//
            *pByte = *pFBuf &255 ; pByte++; pFBuf++; j++ ;
        }
        pByte = (BYTE*) &wFaceIndCnt ;						//
        for (i=0;i<2;i++) {									//
            *pByte = *pFBuf &255 ; pByte++; pFBuf++; j++ ;
        }
        // with cnt==0, first submesh, we are at file offset 0x3D now. We have to skip 123 bytes to vertex start: 0xB8
        pFBuf += 123 ; j += 123 ;
        addrV = j ;                                             // parameter (start of vertices) for create_H2O()
        offs2 = wVertsCnt*26 ;                                  // use vertex stride to calculate size of vertex data block
        pFBuf += offs2 ; j += offs2 ; oldJ = j ;                //
        cnt1 = j/4 ; cnt1++ ;
        if ((j%4)!=0) j = cnt1*4 ;                              // 4 byte alignment
        pFBuf += (j-oldJ) ;                                     // yeah, don't forget to update the pointer
            //fprintf( stream, "debug: pos of MDIX=%x?\n", j) ;
        pFBuf += 8 ; j += 8 ;                                   // skip 8 bytes ("MIDX" and DWORD)
        addrFI = j ;
        offs2 = wFaceIndCnt*2 ;                                 // size of face indices block with word indices
        pFBuf += offs2 ; j += offs2 ;                           //
        // we could do a simple byte alignment here, then skip another 8 bytes
        // but I would like to introduce a search feature; we search for "MHDR"
        // j is the current position in the model file
        nValue[0]= 0x4D; nValue[1]= 0x48; nValue[2]= 0x44; nValue[3]= 0x52;		// "MHDR": signature start of submesh block
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 4) ;
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ;
                //fprintf( stream, "       pos of MHDR=%x?\n", j) ;
            create_H2O(szPathname, cnt, lines, addrFI, wFaceIndCnt, addrUV, 255, addrV, wVertsCnt, 2) ;
        }
        else {
            if (cnt!=4) {    // last submesh? -> no error
                chMB("Damn', MHDR header signature not found\nhave to break here...") ; return ; }
            else create_H2O(szPathname, cnt, lines, addrFI, wFaceIndCnt, addrUV, 255, addrV, wVertsCnt, 2) ;
        }
   }
   if (strlen(szErrMess)>17) MessageBox(NULL, szErrMess, "error", MB_ICONINFORMATION);
}
```


Yeah, that was very short but sadly I can't spend too much time on this. 

Feedbacks on this crash course are welcome. Is there any vagueness?
But keep in mind: this is not a basic tutorial for beginners.

Make_H2O - Codeblocks 13.12 project


 Make_H2O.zip
(85.59 KiB) Downloaded 96 times
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-08T23:28:13+00:00
- Post Title: [crash course] How to get multiple submeshes using Make_H2O

Part3: How to create and import the obj files
-------

start Make_H2O.exe in \Make_H2O\bin\Release and load Mesh_1807.mdl. 
5 H2O files should be created.

In hex2obj_0.23b load the model fileMesh_1807.mdl then choose File "SaveAs Mmesh"
to create obj files from all contained submeshes.

After hex2obj processed the 5 H2O files there should exist 5 obj files in the same folder
named from *_0.obj to *_4.obj with these sizes: 4 kB, 381 kB, 243 kB, 48 kB and 10 kB.

When executing load_multi_obj_blender2.69.py in a blender Text Editor window make sure
to have set "path_to_obj_dir" to YOUR mdl directory.

Also be sure that there are no obj files in a maybe contained subdirectory.



TheResult_Metalman_5_submeshes.JPG (117.9 KiB) Viewed 761 times



shak-otay, April 2015

FAQs:
Q: why the heck didn't you save them all into ONE obj file?
A: yeah, I was thinking about this. For some technical reason I decided to create single objs.

Q: From the picture 1807_MDL.jpg vertexcount and face indices are in little endian, aren't they?
.... Why the heck does hex2obj use big endian for this format?
A: well, the face indices are notated as big endians, imho. So do the half floats.
... That's strange with the counts.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-09T08:22:28+00:00
- Post Title: [crash course] How to get multiple submeshes using Make_H2O

This mdl format uses different types:



Header_Mesh_193.JPG (224.31 KiB) Viewed 761 times



Will have to investigate further. For models with a headersize of 144 there's additional code required.
In other words: models with "MEDG" in their submesh headers don't work.
(Really hope "MEDG" doesn't mean "edge".)

updated the code to handle submesh count automatically: (now to be found in the updated zip of the opening post)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-10T22:51:23+00:00
- Post Title: [crash course] How to get multiple submeshes using Make_H2O

CaptainAmerica mesh file, 2nd try

Examining submesh headers is really more effective than doing a "blind search" 



captnAmerica-0102_mesh.JPG (214.64 KiB) Viewed 739 times


For those who may have missed the code for CaptainAmerica's mesh (didn't check other mesh files):
(now included in zip of opening post)

```
    int cnt ;

    cnt = j/16 ; cnt++ ;
    if ((j%16)!=0) { j = cnt*16 ; }
    return j ;
}

void GetWord(char * &pFBuf, DWORD &j, WORD &w, bool bBigE) {
    BYTE * pByte, i ;
    WORD wLo, wHi ;

    pByte = (BYTE*) &w ;
    for (i=0;i<2;i++) {
        *pByte = *pFBuf &255 ; pByte++; pFBuf++; j++ ;
    }
    if (bBigE) {
        wLo= w % 256 ; wHi= w / 256 ;           // little to big endian correction
        w= wLo * 256 + wHi ;
    }
}

void SM_of_CA_mesh_loop(HWND hwnd, char szPathname[], DWORD dwStart)      // scanning the submeshes params for Captn America
{                                                                         // only model tested
   char * pFBuf, *pTmp ;
   BYTE cnt ;
   int delta, nValue[16] ;
   WORD wFaceIndCnt, wVertsCnt, wOffs2VBlock ;
   DWORD addrFI=0, addrUV, addrV, j, jOld, lastJ, offs2 ;
   char lines[6][20]= {"","Vb1","12 99","","120300",""} ;
   bool bStop= false ;

   pFBuf = (char *) lpFBuf ; pTmp= pFBuf ;
   //dwStart = 0 ;                                        // unneeded here
   //pFBuf += dwStart ;

   cnt= 0 ; lastJ= 0 ;
   do {
        pFBuf= pTmp ; j= lastJ ;                                // restore from previous run
        nValue[0]= 0; nValue[1]= 6; nValue[2]= 0; nValue[3]= 0xFF;		// assumed signature of submesh header
        nValue[4]= 0x12; nValue[5]= 0;
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 6) ;
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ;
            pFBuf += 6 ; j += 6 ;                               // skip signature bytes
            GetWord(pFBuf, j, wVertsCnt, true) ;   			    // get vertex count
            GetWord(pFBuf, j, wFaceIndCnt, true) ;
            pFBuf += 8 ; j += 8 ;                               // skip FFFFFFFF and 4 bytes
            GetWord(pFBuf, j, wOffs2VBlock, true) ;
            pTmp= pFBuf ; lastJ= j ;                            // backup current file buffer pos
            delta= j - addrFI ;                                      // addrFI from previous run
            if (delta<=0) {                                          // avoid finding the same addrFI again
                pFBuf -= delta ; j -= delta ;
                pFBuf++ ; j++ ;
            }
                    //pFBuf += 14*16 + 4 ; j += 14*16 + 4;            // simply skip bytes before face indices block; nope
            nValue[0]= 0; nValue[1]= 0; nValue[2]= 0; nValue[3]= 1;	  // first face
            nValue[4]= 0; nValue[5]= 2;
            offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 6) ;
            if (offs2!=0) {
                pFBuf += offs2 ; j += offs2 ;
                addrFI= j ;                                         // start of face indices
                pFBuf += wFaceIndCnt * 2 ; j += wFaceIndCnt * 2 ;   // skip face indices
                jOld= j ; j = dataAlignment(j) ;                   // data alignment
                pFBuf += (j-jOld) ;                                // don't forget to update the pointer
                // now we are at start of vertex block (are we?)
                addrV = j ;
                pFBuf += wVertsCnt * 12 ; j += wVertsCnt * 12 ;
                fprintf(stream, "SM %d, UV block: 0x%x\n", cnt, j) ;
                jOld= j ; j = dataAlignment(j) ;                   // data alignment
                pFBuf += (j-jOld) ;                                 // don't forget to update the pointer
                // point to uv set
                addrUV = j + 24 ;
                create_H2O(szPathname, cnt, lines, addrFI, wFaceIndCnt, addrUV, 40, addrV, wVertsCnt, 2) ;
                //  code might come in handy when search for 0000 0001 0002 results in problems
/*                pFBuf += wVertsCnt * 40 ; j += wVertsCnt * 40 ;     // skip uvs (and other) block
                jOld= j ; j = dataAlignment(j) ;                   // data alignment
                pFBuf += (j-jOld) ;
                pFBuf += wVertsCnt * 8 ; j += wVertsCnt * 8 ;      // skip unknown block
                jOld= j ; j = dataAlignment(j) ;                   // data alignment
                pFBuf += (j-jOld) ;                                // don't forget to update the pointer   */
                    //offs += 96 ;                          // skip unknown bytes
            }
        }
        else bStop= true ;
        cnt++ ;                                                 // next submesh
   } while (!bStop&&(j<dwFileSize)) ;

   if (strlen(szErrMess)>17) MessageBox(NULL, szErrMess, "error", MB_ICONINFORMATION);
}
```
Don't forget to set
BYTE model = 2 ; 
at start of main.cpp

links to Make_H2O exe files:

Wipeout HD/Fury
[viewtopic.php?f=16&t=12906&p=106658&hil ... bj#p106658](http://forum.xentax.com/viewtopic.php?f=16&t=12906&p=106658&hilit=+hex2obj#p106658)

Shining Resonance .MLX
[viewtopic.php?f=16&t=12392&hilit=hex2obj&start=30](http://forum.xentax.com/viewtopic.php?f=16&t=12392&hilit=hex2obj&start=30)
## Post #5
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-03-23T04:57:04+00:00
- Post Title: [crash course] How to get multiple submeshes using Make_H2O

Please bear with me if i'm asking a noobish question,is this tutorial for extracting mesh from models having multiple objects within them?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-05T05:04:19+00:00
- Post Title: [crash course] How to get multiple submeshes using Make_H2O

sry, must have overlooked that post.
Depends on what you understand by "multiple objects".
If you mean submeshes then: 'yes'.

If you mean a hierarchical 3D mesh (as can be found in fbx files for example) then: 'no'.

But if you know C coding (which is required to make use of this tutorial) then you can implement everything you want.
## Post #7
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-30T09:50:46+00:00
- Post Title: [crash course] How to get multiple submeshes using Make_H2O

> Reply from shakotay2
>
> 
TheResult_Metalman_5_submeshes.JPG

1) where hell you find clank in a medioeval armor
2) please gave me that model (with textures)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-30T12:50:27+00:00
- Post Title: [crash course] How to get multiple submeshes using Make_H2O

I dunno, mate. That's about 1 and a half years ago and I was treating hundreds of models meanwhile.

Think I got it out of some post, you might search backwards from this one
[viewtopic.php?f=16&t=10977&p=106153&hil ... ng#p106153](http://forum.xentax.com/viewtopic.php?f=16&t=10977&p=106153&hilit=+dividing#p106153)
(or forwards to newer ones).

Not only that thread but other threads, too, of course.

(If you don't have any luck finding it there, then sorry, can't help. I don't own those games.)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-19T20:27:27+00:00
- Post Title: [crash course] How to get multiple submeshes using Make_H2O

While this project was abandoned (i.e. substituted by the Make_obj project) I decided to release an updated source for Fahrenheit (Indigo Prophecy) 2005 EU PC
(see [viewtopic.php?f=16&t=23441](https://forum.xentax.com/viewtopic.php?f=16&t=23441))

Didn't care for uvs but maybe the exe is helpful to check some .dat files (tested 2 of them only so don't blame me).
The function in question is void SM_of_Fahrenheit_loop() with an ugly check for getting the start of face indices block.
Feel free to improve this.
.


 Make_H2O-Rel_FH.zip
(148.28 KiB) Downloaded 22 times



edit: uv's address is easy to calculate: vert_addr + 32 * vertex_count for v16 block, n16 block, t8 block
(For v16, n16, uva8, uvb8 you might try 40* vertex_count, didn't check this neither sure about uva, uvb.)
To not confuse: it's always all vertices of a sub mesh then all normals etc.
