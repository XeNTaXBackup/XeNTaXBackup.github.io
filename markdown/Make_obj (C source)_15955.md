## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-06T10:01:14+00:00
- Post Title: Make_obj (C source)

well, another year has come and gone and I think it's time to share some source (based on my Make_H2O project).
last updates: 14th Sept., 21th Nov., revised: 31st of March, 2021


 Make_obj-src 21-11-19, Rev.zip
(229.97 KiB) Downloaded 131 times


This project shall help to extract multi mesh models so is some kind of follow up to hex2obj.
You don't need to use hex2obj for analysing the model before (but  it's recommended).

Feel free to use Make_obj.exe in the zip (and ignore the source) if that fulfills your needs.  

Analysing of the (few) supported formats is far from being complete/perfect!

So it's up to you to improve the source but you can't make too much use of this project if you don't understand 'C', though.
(btw: it doesn't contain the Make_H2O_ForzaHor3 source, if you thought of that. Just some basic functions.)

-----------------------------------------------------------------------------------------------------
(hidden in this thread, so better link this here:)
SuperHeroGeneration auto correction

> Reply from shakotay2 ↑Sun Dec 23, 2018 8:42 am at Sun Dec 23, 2018 8:42 am
>
> 

"One for all" *.pmd

> Reply from shakotay2 ↑Tue Sep 10, 2019 2:47 am at Tue Sep 10, 2019 2:47 am
>
> 

Kamen Rider, 2nd submesh

> Reply from shakotay2 ↑Mon Mar 16, 2020 7:45 pm at Mon Mar 16, 2020 7:45 pm
>
> 
(This Kamen Rider patch is for people who know how to use code: "compile this project with CodeBlocks 13.12 for example".)

-----------------------------------------------------------------------------------------------------
Very rough explanation how the code was created using [X360] Star Wars Battlefront III pre-alpha (*.rax)
as an example:

I used the Han_stormtrooper.rax model as a startup which can be found here:
[http://forum.xentax.com/viewtopic.php?f ... er#p126467](http://forum.xentax.com/viewtopic.php?f=16&t=13867&p=126467&hilit=stormtrooper#p126467)
(Thx to AceWell)  

I've tested this one character model only so might not work for other characters
and will NOT work for static objects, I guess. Feel free to expand the code to do so.

The FVFsize is fixed; you might use the editbox to support different sizes (not implemented so far).

I'm a great fan of pattern (byte sequence) searching so here we go:

Find the counts (behind pattern 00 00 10 03, so search for that first)
find first "FACE " (46 41 43 45 00) after uvs
then find "pos ", get verts and uvs startaddress

and skip to the face indices table

--------------------------

I'm pretty sure we'll need some data alignment here (function DWORD dataAlignment(DWORD j) for example)
instead of simply adding 40 bytes here to skip to the face indices table:

pFBuf= pTmp + addrUV + 40 ; j= addrUV + 40 ; fprintf( stream, "# start of FIs: %x\n", j) ;
(where addrUV is the last uv's address +1)

[https://www.pic-upload.de/view-32802746 ... r.jpg.html](https://www.pic-upload.de/view-32802746/Han-startrooper.jpg.html)


here's the "main" function of the code, it's ugly and simple, but it works:

```
{                                                                         // only one model tested
   char * pFBuf, *pTmp, szNo[4] ;
   BYTE cnt, fCnt=0, i, SMcnt, FVFsize= 24 ;
   int k, nValue[16] ;
   WORD FI[3] ;
   DWORD FIcnt, FIcnt_arr[999], vCnt, vCnt_arr[999] ;         //
   DWORD addrUV, addrV, j=0, jOld, lastJ, offs2 ;  //
   DWORD minFaceInd = 16777215, maxFaceInd = 0, lastFaceInd=0 ;

   pFBuf = (char *) lpFBuf ; pTmp= pFBuf ;
   pFBuf += dwStart ;
   SendMessage(GetDlgItem(hwnd, ID_LIST), LB_ADDSTRING, 0, (LPARAM) " creating obj:") ;
   cnt= 0 ; lastJ= 0 ; j= 0 ;
   // get counts of submeshes
   nValue[0]= 0; nValue[1]= 0; nValue[2]= 0x10; nValue[3]= 3;    // there's counts behind that pattern
   do {
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 4) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 + 4 ; j += offs2 + 4 ;
            GetDW(pFBuf, j, vCnt, true) ; GetDW(pFBuf, j, FIcnt, true) ; // j not used here
            vCnt_arr[cnt]= vCnt ; FIcnt_arr[cnt]= FIcnt ; fprintf( stream, "# %d %d\n", vCnt, FIcnt) ;
            if (cnt<999) cnt++ ; else chMB("Too many submeshes!") ;
            pFBuf += 8 ; j += 8 ;
        }
   } while ((offs2!=0)&&(j<dwFileSize)) ;
    // get counts of last submesh
   offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 3) ;       // j is offset here
    if (offs2!=0) {
        pFBuf += offs2 + 4 ; j += offs2 + 4 ;
        GetDW(pFBuf, j, vCnt, true) ; GetDW(pFBuf, j, FIcnt, true) ; // j not used here
        vCnt_arr[cnt]= vCnt ; FIcnt_arr[cnt]= FIcnt ; fprintf( stream, "# %d %d\n", vCnt, FIcnt) ;
        pFBuf += 8 ; j += 8 ; cnt++ ;
    } else chMB("Error, last submesh not found!") ;
    // where's the stzartaddresses for vertices and uvs?
   nValue[0]= 0x46; nValue[1]= 0x41; nValue[2]= 0x43; nValue[3]= 0x45; nValue[4]= 0;    // 'FACE'
   offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 5) ;       // j is offset here
    if (offs2!=0) {
        pFBuf += offs2 ; j += offs2 ;
        pFBuf += 8 ; j += 8 ;
    } else chMB("Error, 'FACE ' after last counts not found!") ;    // evtl. erste von 2 'FACE'
   nValue[0]= 0x50; nValue[1]= 0x4F; nValue[2]= 0x53; nValue[3]= 0;     // 'POS '
   offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 4) ;       // j is offset here
    if (offs2!=0) {
        pFBuf += offs2 -32 ; j += offs2 - 32 ;                   //
        GetDW(pFBuf, j, addrV, true) ; pFBuf += 16 ; j += 16 ;
        GetDW(pFBuf, j, addrUV, true) ; fprintf( stream, "# %x %x\n", addrV, addrUV) ;
        pFBuf += 72 ; j += 72 ;
    } else chMB("Error, 'POS ' after 'FACE' not found!") ;
    if (j!=addrV) {chMB("address calculation went wrong! break...") ; return ;}
    SMcnt= cnt ;
    for (i=0;i < SMcnt;i++) {
        fprintf( stream, "# %x, %d\n", addrV, vCnt_arr[i]) ;
        log_short_Verts(addrV, vCnt_arr[i], FVFsize) ; addrV += FVFsize*vCnt_arr[i] ;
    }
    if (addrV!=addrUV) {chMB("UV address calculation went wrong! break...") ; return ;}
    // go for uvs, blocksize is 4
    for (i=0;i < SMcnt;i++) {
        log_short_UVs(addrUV, vCnt_arr[i], 4) ; addrUV += 4*vCnt_arr[i] ;
    }
    pFBuf= pTmp + addrUV + 40 ; j= addrUV + 40 ; fprintf( stream, "# start of FIs: %x\n", j) ;
    // go for face indices
    for (i=0;i < SMcnt;i++) {
        _itoa(i, szNo, 10) ; fprintf( stream, "g SM_%s\n", szNo) ;      // separating the submeshes (building groups)
        for (k=0;k<FIcnt_arr[i];k++) {       //
            //                       adding lastFaceInd in that function to get absolute FIs
            FI[fCnt]= (WORD) GetFaceIndexBigE(pFBuf, j, minFaceInd, maxFaceInd, lastFaceInd, false) ;	//
            fCnt++ ;
            if (fCnt==3) {
                fCnt=0 ;                        //
                fprintf( stream, "f %d/%d %d/%d %d/%d\n", FI[0],FI[0],FI[1],FI[1],FI[2],FI[2]) ;
            }
        }
        if (maxFaceInd<lastFaceInd) {
            fprintf( stream, "error! maxFI %d < lastFI %d\n\n", maxFaceInd, lastFaceInd) ;
        }
        else lastFaceInd = maxFaceInd ;         // needed to "convert" relative to absolute face indices
        fprintf( stream, "# next FI block: %x\n", j) ;
    }
}
```
(code doesn't care for normals)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-27T14:40:38+00:00
- Post Title: Make_obj (C source)

Make_obj-SPMan3.zip
(113.15 KiB) Downloaded 54 times


I've updated the source code for extracting an obj model from [CITY_PARAMEDIC-]dbd91b3e.36
which you need to extract from CITY_PARAMEDIC.PCPACK using chrrox' quickbms script.

The code can handle this one model only atm. (Feel free to expand it for other .36 models.)

This is a short and uncomplete description how it was coded:

```
rename it to SM_of_SpMan3_loop()

# we need a new entry for the select-game combobox:
in line 50: set model to 2, or active new model

In function DoFileOpenSave() in the SECOND
switch (model) selection for case 2: add SM_of_SpMan3_loop(hwnd, szFileName, 0) ;

In the callback function WndProc() in the case WM_CREATE: branch add
SendMessage(hwndCombo1, CB_ADDSTRING, 0, (LPARAM) "SpMan3") ;

as a new entry in the game-selection combo box.
Build and run to see how it works.
```

This was the simple part; now we have to fill our new function
SM_of_SpMan3_loop() with code to get all submeshes (SMs).

Best approach would be a full format analysis, but as you may know,
I really don't like such. But..

It's helpful to use magic tables, if any.
How to find them? Well, simply search for the counts.

hex2obj

If you're familiar with hex2obj you could try to extract the first submesh of the heli, [CA5_Heli-]63757bc7.36. 
You can calculate the face indices count from (endaddr -startaddress) / 2, which is (0xecc52 - 0xe7974) / 2 = 10607 (0x296F)

Entering startaddr and count into the go1 editboxes and pressing that button
you'll get the assumed vertex count in the lower left list box: 6269 (0x187D)

getting the offsets of the magic tables:
----------------------------------------------
Those values (7D180000 and 6F290000) to be found at offsets 0x0DF4 and 0x0E04 in the CA5_Heli-63757bc7.36 file.

I'll use the patterns 04 00000000 and 02 000000 to find those tables.
(Understanding how to define patterns is a matter of experience; there's no  general recipe.)

```

The FindBytes() function will return the offset addr (offs2) of a found pattern,
if any, otherwise offs2 will be zero!

Once a pattern is found we'd check for the second one (byte per byte) to avoid using
FindBytes() again (which doesn't make too much sense here).
```

Look at 0xDFF, the address of the first find, to understand why we check for
(*(pFBuf+9)==2) to assure that we didn't meet a false find 
(the 3 following bytes need to be checked for zero, too).

These are the results for the counts of each submesh then (vertex, FIs) in the log/obj file:
# 0. 6269 10607
# 1. 199 341
# 2. 898 1631
# 3. 208 422
# 4. 34 65
# 5. 548 919
# 6. 153 249
# 7. 34 65
# 8. 555 933
# 9. 153 253
# 10. 3582 6275
# 11. 1562 2761
# 12. 986 1787
# 13. 83 164
# 14. 58 103
# 15. 990 1809
# 16. 83 165
# 17. 58 103
# 18. 2440 4221

using a simpler model
---------------------------------

19 submeshes for CA5_Heli-]63757bc7.36, yeah, a little bit too many for a first approach, so let's stick to
CITY_PARAMEDIC-dbd91b3e.36, which has 5 only and, much more important, I've extraced 
a proper texture for it.

We go for the face indices now, using 0000 0100 0200 as a well-known search pattern
(which doesn't apply for all 3D formats, as you may know already).

Well, for .36 character models it seems to be some kind of signature, too, so an additional 
check for a following xx 00 is required, else we've get 60 findings!

```
[b]reinitialize[/b] some variables: cnt= 0 ; pFBuf= pTmp; j= 0 ;
```
And setting the new search pattern, of course.
In FindBytes() the last parameter is 6 now, the number of bytes to be searched for.

Sadly we've too many finds for FIs' blocks, though, 7 instead of 5:
# 0. 2180 4169
# 1. 1132 2875
# 2. 86 207
# 3. 1290 2781
# 4. 798 1747

# 0xe78
# 0x1098
# 0x83740
# 0x92c14
# 0x95404
# 0xa4784
# 0xaf2e0

So we have to exclude the first two ones, with a simple check, that works for this 
CITY_PARAMEDIC-dbd91b3e.36 file only.
The code change is expanding the if conditon if ((*(pFBuf+7)==0) by &&(j>0x40000),
where j is the actual address offset into the .36 file and pFBuf is just a char pointer to the file buffer.

(I'm sorry to say that this is my sloppy way to solve problems in a time saving manner.)

Now we have all we need: the counts, the FIs' starting addresses.
------------------------------------------------------------------------
We'll calculate the vertex address from FIstart - vCount * FVFsize,
where FVFsize is 48 for the PARAMEDIC character (52 for Fireman, for the Heli it was 36).

Sadly there's one different FVFsize to be found: 52 for submesh 3 (cnt==2).
(But we can replace this stupid solution by getting the FVFsize directly; it's 16 bytes before
the 0700000000000800 patterns.)

We need a loop controlled by SMcnt, the submesh count, to get all the submeshes.

I've placed some tristrips face index routine from my MakeH2O project in that loop.

We also need these vars:

```
int faceDir= 1 ;
DWORD minFaceInd = 16777215, maxFaceInd = 0, lastFaceInd=0 ;
DWORD f1,f2,f3 ;
```

Provided as is, don't blame me.
Works for CITY_PARAMEDIC-dbd91b3e.36 only atm.


And well, I didn't care for the textures; just used the "camera button" in TextureFinder.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-31T21:26:40+00:00
- Post Title: Make_obj (C source)

again another year has come and gone, so here's a small update integrating Kamen Rider CW prefab models
(only two models tested so may badly fail on others)

Make_obj, C source included
(see 
> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> )
## Post #4
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-04-01T00:35:15+00:00
- Post Title: Make_obj (C source)

> Reply from shakotay2
>
> again another year has come and gone, so here's a small update integrating Kamen Rider CW prefab models
(only two models tested so may badly fail on others)

Make_obj, C source included
Make_obj.zip

Thank you very much.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-03T11:19:56+00:00
- Post Title: Make_obj (C source)

another month has come and gone  so here's the next update (adding Skyforge mesh support)
see 
> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 

(where the lod (or whatever) submeshes are spoiled)
First and maybe 2nd SM should be okay; feel free to fix it in the source.
(The problem is that there's more vertex blocks than face indices blocks i.e. up to 4 vertex blocks share the same FIs block.)
Seems each submesh has one "copy" at least, up to a count of 4. But I have no idea how to get the count via code.
Even more annoying: the copies may not follow in sequence.
edit: seems it's 3 submeshes (dunno how I could assume 4)

The body sample (Base.Skin-Geometry.bin) to be found here (in slawdos' post as of Thu May 03, 2018 3:12 am):
[http://forum.xentax.com/viewtopic.php?f ... 7&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=13497&start=15)

code for Skyforge mesh:

```
{
   char * pFBuf, *pTmp ;            // , szNo[4]
   BYTE cnt= 0, i, SMcnt ;
   int nValue[16] ;
   //WORD wFaceIndCnt, wVertsCnt, wOffs2VBlock ;         //
   DWORD FIaddr_arr[999], FIcnt=0, FIcnt_arr[999], uvAddr_arr[999], uvCnt, Vaddr_arr[999], vCnt, vCnt_arr[999] ;
   DWORD minFaceInd = 16777215, maxFaceInd = 0, lastFaceInd=0, startFI ;
   DWORD addrFI=0, addrUV, addrV, jOld, lastJ, offs2 ;  //
   DWORD j=0 ;
   float *pFloat ;
   float fData = 0.0f;      // 
   bool bStop= false, bUV ;

   pFBuf = (char *) lpFBuf ; pTmp= pFBuf ;
   dwStart = 0 ; pFBuf += dwStart ;            //
   SendMessage(GetDlgItem(hwnd, ID_LIST), LB_ADDSTRING, 0, (LPARAM) " creating obj:") ;
   cnt = 0 ;
   nValue[0]= 0; nValue[1]= 0; nValue[2]= 1; nValue[3]= 0; nValue[4]= 2; //nValue[5]= 0;    // 0000 0100 02
   do {
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 5) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ; fprintf( stream, "#") ;
            FIaddr_arr[cnt]= j ; if (cnt<511) cnt++ ; else chMB("Too many submeshes!") ;
            fprintf( stream, "%x\n", j) ;
            pFBuf += 6 ; j += 6 ;
        }
   } while ((offs2!=0)&&(j<dwFileSize)) ;
   FIaddr_arr[cnt] = dwFileSize ;               // but not sure if every Geometry.bin file has FIs 'til their ending!
   SMcnt = cnt ;
   for (i=0;i<SMcnt;i++) {
       FIcnt_arr[i] = (FIaddr_arr[i+1]-FIaddr_arr[i]) / 2 ;
            //fprintf( stream, "%d, ", FIcnt_arr[i]) ;
       FIcnt += FIcnt_arr[i] ;
   }
   pFBuf= pTmp ; pFBuf += 4 ;
   GetDW(pFBuf, j, vCnt, false) ;
   fprintf( stream, "\n# vCnt?: %d, FIs %d\n", vCnt/72, FIcnt) ;
   addrV = 8 ; startFI = 0;
   for (i=0;i<SMcnt;i++) {
        log_FIs(stream, FIaddr_arr[i], minFaceInd, maxFaceInd, lastFaceInd, FIcnt_arr, i) ;
        vCnt_arr[i] = lastFaceInd - startFI ; startFI = lastFaceInd ;
        fprintf( stream, "# vAddr: %x, %d\n", addrV, vCnt_arr[i]) ;
        log_short_Verts(addrV, vCnt_arr[i], 24) ;          // vertex stride: 24
       log_short_UVs(addrV+8, vCnt_arr[i], 24) ;
        addrV += vCnt_arr[i]*24 ;
   }
   fprintf( stream, "# v end: %x\n", addrV) ;
}
```

This line, calculating the address of the next vertex block, is the problematic one:
addrV += vCnt_arr*24 ;

There are more vertex blocks than face indices blocks, so some (nearly identical) vertex blocks have to be skipped.

edit: fixed a small bug "precalculating" vCnt
added uvs support in above code (zip not updated!)

in void log_short_UVs(DWORD addrUV, DWORD Vcnt, BYTE vStride)
you need to uncomment the following line and comment out the "big endian" one:
lPosXYZ= nValue[0] + nValue[1]*256 ;
//lPosXYZ= nValue[0]*256 + nValue[1] ;            // big endian for BF3

(or introduce a parameter bool bIsBigEndian for example)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-10T16:47:38+00:00
- Post Title: Make_obj (C source)

here's an update to the code after akderebur gave some hint
('%" means: modulo, i.e.   5 % 3 is 2)

Update of  the code of the previous post (replacement for the for (i=0;i<SMcnt;i++) {...} loop ):

```
{
   char * pFBuf, *pTmp ;            // , szNo[4]
   BYTE vStride= 24 ;     			// stride autoset now
   int cnt= 0, i, ii, SMcnt, nValue[16] ;
   //WORD wFaceIndCnt, wVertsCnt, wOffs2VBlock ;         //
   DWORD FIaddr_arr[999], FIcnt=0, FIcnt_arr[999], vCnt, vCnt_arr[999], vCntSum=0 ;	// uvCnt,
   DWORD minFaceInd = 16777215, maxFaceInd = 0, lastFaceInd=0, startFI ;
   DWORD addrV, offs2 ;  //
   DWORD j=0 ;
   //bool bStop= false, bUV ;

   //chMB("vStride is 24 atm") ;
   pFBuf = (char *) lpFBuf ; pTmp= pFBuf ;
   dwStart = 0 ; pFBuf += dwStart ;            //Triangles 54 72 69 61 Positions  50 6F 73 69
   SendMessage(GetDlgItem(hwnd, ID_LIST), LB_ADDSTRING, 0, (LPARAM) " creating obj:") ;
   cnt = 0 ;
   nValue[0]= 0; nValue[1]= 0; nValue[2]= 1; nValue[3]= 0; nValue[4]= 2; //nValue[5]= 0;    // 0000 0100 02
   do {
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 5) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ; fprintf( stream, "#") ;
            FIaddr_arr[cnt]= j ; if (cnt<511) cnt++ ; else chMB("Too many submeshes!") ;
            fprintf( stream, "%lx\n", j) ;
            pFBuf += 6 ; j += 6 ;
        }
   } while ((offs2!=0)&&(j<dwFileSize)) ;
   FIaddr_arr[cnt] = dwFileSize ;               // but not sure if every Geometry.bin file has FIs 'til their ending!
   SMcnt = cnt ; fprintf( stream, "#") ;
   for (i=0;i<SMcnt;i++) {
       FIcnt_arr[i] = (FIaddr_arr[i+1]-FIaddr_arr[i]) / 2 ;
            fprintf( stream, "%lu, ", FIcnt_arr[i]) ;
       FIcnt += FIcnt_arr[i] ;
   }
   pFBuf= pTmp ; pFBuf += 4 ;
   GetDW(pFBuf, j, vCnt, false) ;       // vCnt is size of the vertex block here; pFBuf increased

   fprintf( stream, "\n# vCnt?: %ld, FIs %ld\n", vCnt/vStride/3, FIcnt) ;

   addrV = 8 ; startFI = 0; i= 0 ;
    // erster Durchlauf zur Bestimg des ersten vertex
   	//fflush(stream) ;
   for (ii=0;ii<SMcnt*3;ii++) {
        i = ii / 3 ;
        if ((ii % 3)==0) {
            fprintf( stream, "# FIaddr: %lx, %lu\n", FIaddr_arr[i], FIcnt_arr[i]) ;
            log_FIs(stream, FIaddr_arr[i], minFaceInd, maxFaceInd, lastFaceInd, FIcnt_arr, i, false) ;
            vCnt_arr[i] = lastFaceInd - startFI ; startFI = lastFaceInd ;
        }
   }
   for (i=0;i<SMcnt;i++) vCntSum += vCnt_arr[i] ;
   vStride = (BYTE) (vCnt / vCntSum / 3) ;    // /3 doesn't apply for all Geometry.bin, you have been warned!
   for (ii=0;ii<SMcnt*3;ii++) {
        i = ii / 3 ;
        if ((ii % 3)==0) {
            fprintf( stream, "# vAddr: %lx, %lu\n", addrV, vCnt_arr[i]) ;
            log_short_Verts(addrV, vCnt_arr[i], vStride) ;          // vertex stride: 24
            log_short_UVs(addrV+8, vCnt_arr[i], vStride) ;
        }
        addrV += vCnt_arr[i]*vStride ;
        fprintf( stream, "# [%d] v end: %lx, vStride: %d\n", ii, addrV, vStride) ;
   }

}
```


edit: checked with Base.Skin-Geometry.bin, 960.928 bytes as of 10th of July 2012, 5:00
>>> worked, so don't blame me...  

remark: the code may appear to be more complicated than it is. It's originally one loop only but it had to be split up into two loops because of the auto calculation of vStride which requires vCntSum.
The modulo thingie just chooses the first of the 3 mesh copies to be logged.

Pay attention to the line calculating the vStride:
vStride = (BYTE) (vCnt / vCntSum / 3) ;

The /3 doesn't apply for all Geometry.bin, this one for example has only one mesh "copy" (although it looks like two, hehehe):



Wings Geometry-bin.jpg (191.08 KiB) Viewed 1544 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-23T20:27:58+00:00
- Post Title: Make_obj (C source)

added support for Super Hero Generation, PS3 (tested with 2 mbg files only)
(There's double submeshes for some unknown reason, so instead of 4 it's 2x2.)

(thread: [viewtopic.php?f=16&t=16861](http://forum.xentax.com/viewtopic.php?f=16&t=16861))



PS3_SuperHeroGeneration.jpg (66.29 KiB) Viewed 1394 times



As you may know I'm not a friend of full 3D format analysing.
Lack of time, lack of knowledge, whatever.

So I'd like to give some advice for my kind of sloppy but time saving approach 
to extract 3D data from mbg to wavefront obj.

You'll need some basic understanding of 'C' to use it with the Make_obj project.

(Feel free to use this approach with Noesis python or max script.)

First thing is the patterns, if any.

for mbg I found
a) "-mesh" which is 2D 6D 65 73 68 in hexadecimal notation
b) 01 000000 04
c) 01 000000 0C

and 0000 0001 0002 (big endian face indices)

getting the counts
With some experience you find the counts (see picture in post 
[viewtopic.php?f=16&t=16861&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=16861&start=15))

and it's plain to see (for me at least) that the pattern search 
01 000000 04 00 3F3F3F 01 000000 04 will help to get vertex count
and face indices count (where 3F being a wildcard for search in a hex editor)

(This is the idea, in the code I made a backwards search instead, to circumvent multiple findings)

getting the start of vertices
search for -mesh
search for the next 01 000000 0C

vertices start after the 0C of previous pattern

getting the start of face indices (see above)

To get all submeshes (it's 4 for the two mbg samples I have)
we have to do this in a loop.

exe with source in zip file:
(view attachment in next post)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-06T15:36:53+00:00
- Post Title: Make_obj (C source)

Scion of Fate, 101.YOM tested only (may fail on others, adding of unrecognized FI blocks to the source is required then).
see 
> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 
yeah, that's not nice: all objects are clumped together. Maybe there's offsets in the 101.txt file to move them into correct positions (position in World Matrix is a candidate). 
Also uvs of some objects seem to be missing.

You have the source, so don't complain, improve it.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-07T09:16:38+00:00
- Post Title: Make_obj (C source)

I've updated the code (see previous post) to load 101_type2.YOM sucessfully, though there is 8 QNANs (not a number).

The correction is simple but not logical, imho.
In Make_log.obj replace the 504 vertices after the two lines below by 504 lines with: v 0.0 0.0 0.0

# error vertex counts (calc versa file): 504 != 38
# (256dae) vAddr: 256da2, 504

The vts of this submesh are spoiled, too. But you don't need to correct them since you'll delete this submesh anyways.
(For those who don't read readmes: vStart is 0x21F8 for this YOM.)



101_type2-YOM.jpg (98.62 KiB) Viewed 1416 times


Technical background: the vertex counts are calculated automatically in the source (vCnt_arr). They may be different from the file data (vCnt).
I've commented out the "correction" in the source because it spoils the mesh.

```
            fprintf( stream, "# error vertex counts (calc versa file): %d != %d\n", vCnt_arr[i], vCnt) ;
            //if (vCnt<128000) vCnt_arr[i] = vCnt ;
        }
```


btw: for those who REALLY do read the source: there's a copy&paste error in a comment // vertex stride: 94
It's 32 of course.
## Post #10
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2018-08-03T14:22:44+00:00
- Post Title: Make_obj (C source)

An error occurred while opening.
sample data
[http://www.mediafire.com/file/sxmq277zzo5iyz4/mbg/file](http://www.mediafire.com/file/sxmq277zzo5iyz4/mbg/file)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-03T17:56:23+00:00
- Post Title: Make_obj (C source)

thanks for reporting!  This will take some time to fix.
You might use this H2O file with hex2obj (view 2nd link in my sig) to get that mbg mesh:

0x182E5 2010
Vb1
94 17
0x326 1045
120000
0x0 255

----------------------
I've added autocorrection for SuperHeroGen mbg files to the attached zip in the post as of Fri Jul 06, 2018 4:36 pm.
(Hopefully it doesn't spoil other mbgs.)
## Post #12
- Username: asphyxiazation
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 13, 2017 1:19 pm
- Post datetime: 2018-10-31T07:44:35+00:00
- Post Title: Make_obj (C source)

> Reply from shakotay2
>
> again another year has come and gone, so here's a small update integrating Kamen Rider CW prefab models
(only two models tested so may badly fail on others)

Make_obj, C source included
The attachment Make_obj.zip is no longer available


shakotay2, I tried converting this prefab file (MDL__B00007_7.prefab) from this thread (forum.xentax.com/viewtopic.php?f=16&t=17900), but the resulting Makeobj_log.obj file is only 125kb and seems to be corrupted that it can't be opened in Windows 3D Builder.

the screenshot is in the attachment.

I've tried several times, the result is the same.

can you help me with this, shakotay2?

EDIT:
I forgot to mention the name of the game. it's Kamen Rider City Wars, Android version.
[125kb.jpg](https://xentaxbackup.github.io/file/15103_125kb.jpg)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-31T09:54:10+00:00
- Post Title: Make_obj (C source)

> Reply from asphyxiazation
>
> shakotay2, I tried converting this prefab file (MDL__B00007_7.prefab) from this thread (forum.xentax.com/viewtopic.php?f=16&t=17900), but the resulting Makeobj_log.obj file is only 125kb and seems to be corrupted that it can't be opened in Windows 3D Builder.No, it's not corrupted, it just starts with face indices instead of vertices:
# FIs: 5802
g SM_0
f 1/1 2/2 3/3
f 1/1 3/3 4/4
f 5/5 1/1 4/4
f 5/5 4/4 6/6

Some wavefront obj importers can't handle this.
Try blender, it's free and it works (using the importer from Campbell Barton et al.).

(As a simple workaround you might select and cut the face indices block in the obj file, then move it to file's end and save.)
## Post #14
- Username: asphyxiazation
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 13, 2017 1:19 pm
- Post datetime: 2018-10-31T10:23:32+00:00
- Post Title: Make_obj (C source)

> Reply from shakotay2
>
> asphyxiazation wrote:shakotay2, I tried converting this prefab file (MDL__B00007_7.prefab) from this thread (forum.xentax.com/viewtopic.php?f=16&t=17900), but the resulting Makeobj_log.obj file is only 125kb and seems to be corrupted that it can't be opened in Windows 3D Builder.No, it's not corrupted, it just starts with face indices instead of vertices:
# FIs: 5802
g SM_0
f 1/1 2/2 3/3
f 1/1 3/3 4/4
f 5/5 1/1 4/4
f 5/5 4/4 6/6

Some wavefront obj importers can't handle this.
Try blender, it's free and it works (using the importer from Campbell Barton et al.).

(As a simple workaround you might select and cut the face indices block in the obj file, then move it to file's end and save.)

I imported the resulting Makeobj_log.obj file into Rhino 5 and it stated:
"Encountered mesh face with bogus vertex index (count is 0). Search for "1/1" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "2/2" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "3/3" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "1/1" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "3/3" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "4/4" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "5/5" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "1/1" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "4/4" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "5/5" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "4/4" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "6/6" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "7/7" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "5/5" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "6/6" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "7/7" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "6/6" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "8/8" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "9/9" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "7/7" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "8/8" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "9/9" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "8/8" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "10/10" in your file.
Encountered mesh face with bogus vertex index (count is 0). Search for "11/11" in your file.
Encountered 25 bogus mesh faces. No longer displaying errors to command line.
File had 5802 bogus indexes in it."



then I followed your suggestion to cut the face indices block in the obj file and move it to the file's end, and imported to Rhino 5, and it worked!   

so, out of curiosity, what are the other contents of the prefab file that its size reaches 1.829kb while the actual mesh is only 126kb?

thanks, shakotay2.
you're the man.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-31T11:18:40+00:00
- Post Title: Make_obj (C source)

> Reply from asphyxiazation
>
> so, out of curiosity, what are the other contents of the prefab file that its size reaches 1.829kb while the actual mesh is only 126kbIt's normals which I usually skip; and weight data, I guess; there's positions and rotations for the skeleton bones, and some other data that would require a deeper look.
## Post #16
- Username: asphyxiazation
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 13, 2017 1:19 pm
- Post datetime: 2018-10-31T11:41:47+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2
>
> asphyxiazation wrote:so, out of curiosity, what are the other contents of the prefab file that its size reaches 1.829kb while the actual mesh is only 126kbIt's normals which I usually skip; and weight data, I guess; there's positions and rotations for the skeleton bones, and some other data that would require a deeper look.

thanks for the insight, shakotay2!
## Post #17
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2018-12-22T09:57:03+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2
>
> Scion of Fate, 101.YOM tested only (may fail on others, adding of unrecognized FI blocks to the source is required then).
Make_obj.zip
yeah, that's not nice: all objects are clumped together. Maybe there's offsets in the 101.txt file to move them into correct positions (position in World Matrix is a candidate). 
Also uvs of some objects seem to be missing.

You have the source, so don't complain, improve it.

Please help me.
Some files cause problems
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-23T00:42:02+00:00
- Post Title: Re: Make_obj (C source)

thanx for reporting, leyme!  
Here's an update for the SuperHeroGeneration auto correction (which had a problem; checked hg009_0001_01_m01.mbg only!):


 Make_obj-ZoE.zip
(44.08 KiB) Downloaded 49 times


(no source update this time because ZoE source part is not ready for release and I'm too lazy to cut it from the actual source)
## Post #19
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2018-12-23T08:59:25+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2
>
> thanx for reporting, leyme!  
Here's an update for the SuperHeroGeneration auto correction (which had a strange bug; checked hg009_0001_01_m01.mbg only!):
Make_obj-ZoE.zip
(no source update this time because ZoE source part is not ready for release and I'm too lazy to cut it from the actual source)

Thanks shakotay2.
Other files are  error.
[https://www.mediafire.com/file/j322x7ag ... g.zip/file](https://www.mediafire.com/file/j322x7ag87d4bip/other_sample_file_mbg.zip/file)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-23T14:02:54+00:00
- Post Title: Re: Make_obj (C source)

well, too bad. The "bug" was not a bug, it worked as expected but I didn't get the real problem so far (need more time, next year, I assume  )

I made a workaround (see updated zip in my previous post) so that you can load the meshes at least into blender for example. Then erase the spoiled submeshes (hopefully one intact one will remain):



SHeroGen-probs.png (213.81 KiB) Viewed 435 times
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-24T03:48:47+00:00
- Post Title: Re: Make_obj (C source)

well, thing is, there's unrecognized vertex blocks:



hg010_0002-SM02.png (91.23 KiB) Viewed 416 times
## Post #22
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2018-12-24T23:59:36+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2
>
> well, thing is, there's unrecognized vertex blocks:
hg010_0002-SM02.png
wow.I salute you for your enthusiasm
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-25T14:18:45+00:00
- Post Title: Re: Make_obj (C source)

yeah, I'm totally surprised, too.  (made an update to the previous zip) But I really need a break here.

Still some spoiled meshes, with er045_0001_02_m01.mbg for example.
You may check out for yourself (using hex2obj for example) which correction might be false;
or maybe vBlock and FIblock pairs don't fit together.

(abbreviations: vCnt= vertex count; FIcnt= face indices count)
# start of vertices
#0 59e
 # UV01 0x7859c (2574) (name is uv01, but appears to be a vertex block for me)
#1 b6517
#2 c30de
#3 d202d
#4 e933a
#5 13cd61
 # UV01 0x1db03f (2574)
#6 233baa
#7 247c2c
#8 270d6e

# FIs at:
# 0x70819
# 0xb36c9
# 0xc1d74
# 0xc3783
# 0xd12d9
# 0xe8058
# 0x10a80d
# 0x1acfdc
# 0x21616c
# 0x23f407
# 0x25dc57
# 0x292241
# SubMesh count and FIs block count are different!
Some SM may be missing. 11 != 12
#0 vCnt: 7461 (at 0x496), FIcnt: 21738
correction counts: 4887 / 16002
#1 vCnt: 502 (at 0xb6413), FIcnt: 2292
corr: FIcnt 5736
#2 vCnt: 613 (at 0xc2fd6), FIcnt: 1557
corr: FIcnt 2292
#3 vCnt: 959 (at 0xd1f29), FIcnt: 2226
corr: FIcnt 42
#4 vCnt: 1451 (at 0xe9236), FIcnt: 6603
corr: FIcnt 1515
#5 vCnt: 7461 (at 0x13cc59), FIcnt: 21738
corr: 4887 / 2226 
#6 vCnt: 502 (at 0x233aa6), FIcnt: 2292
corr: FIcnt 6603 
#7 vCnt: 959 (at 0x247b28), FIcnt: 2226
corr: FIcnt 16002
#8 vCnt: 1451 (at 0x270c6a), FIcnt: 6603
corr: FIcnt 5736
## Post #24
- Username: wjj162446
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 10, 2019 7:01 pm
- Post datetime: 2019-07-10T11:18:59+00:00
- Post Title: Re: Make_obj (C source)

Thanks sir,they are helpful
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-09T18:47:00+00:00
- Post Title: Re: Make_obj (C source)

"One for all" pmd models, tested chr_body_rank_104_a_slender.pmd only!


 Make_obj-pmd.zip
(43.97 KiB) Downloaded 53 times



(no source code update this time because the pmd2obj code is dead ugly  )

last source code version (without .pmd support) to be found in the opening post:

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
>
## Post #26
- Username: wjj162446
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 10, 2019 7:01 pm
- Post datetime: 2020-03-12T09:42:39+00:00
- Post Title: Re: Make_obj (C source)

Sir,I have a question,when I ues make_boj to extract kamen rider thouser from citywar,it has some trouble
[QQ图片20200312174128.png](https://xentaxbackup.github.io/file/17701_QQ图片20200312174128.png)
## Post #27
- Username: wjj162446
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 10, 2019 7:01 pm
- Post datetime: 2020-03-12T09:48:25+00:00
- Post Title: Re: Make_obj (C source)

> Reply from wjj162446 ↑Thu Mar 12, 2020 5:42 pm at Thu Mar 12, 2020 5:42 pm
>
> 
Sir,I have a question,when I ues make_boj to extract kamen rider thouser from citywar,it has some trouble
[https://drive.google.com/file/d/1hvxbP4 ... sp=sharing](https://drive.google.com/file/d/1hvxbP4E86ln_1hJ1MFflXMj1iUWkLgc2/view?usp=sharing)
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-12T12:30:32+00:00
- Post Title: Re: Make_obj (C source)

yeah, I see. It's the first submesh only - will take some time to patch the tool.

Feel free to do it for yourself - the 'C' source code is available here: 
> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 
.



2_submeshes.png (90.71 KiB) Viewed 287 times


(need to check the patch before releasing it..)
## Post #29
- Username: wjj162446
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 10, 2019 7:01 pm
- Post datetime: 2020-03-16T00:48:04+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2 ↑Thu Mar 12, 2020 8:30 pm at Thu Mar 12, 2020 8:30 pm
>
> 
yeah, I see. It's the first submesh only - will take some time to patch the tool.

Feel free to do it for yourself - the 'C' source code is available here: shakotay2 wrote: ↑Mon Mar 06, 2017 6:01 pm
.
2_submeshes.png
(need to check the patch before releasing it..)

Will sir update the tool
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-16T11:45:41+00:00
- Post Title: Re: Make_obj (C source)

This is the patch for KamenRider, submesh 2, very ugly but works for MDL__B00092_92.prefab (only tested model, so don't blame me).
.



submesh_2.png (90.02 KiB) Viewed 258 times


Replace the function void SM_of_KR_CW_loop(HWND hwnd, char szPathname[], DWORD dwStart)  in the source here:

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 
by

```
{                                                                         // Kamen Rider City Wars
   char * pFBuf, *pTmp ;            // , szNo[4]
   BYTE cnt= 0 ;
   int nValue[16] ;
   //WORD wFaceIndCnt, wVertsCnt, wOffs2VBlock ;         //
   DWORD FIaddr_arr[9], FIcnt, FIcnt_arr[9], uvCnt, vCnt, UVaddr_arr[9], Vaddr_arr[9], vCnt_arr[9] ;  //
   DWORD minFaceInd = 16777215, maxFaceInd = 0, lastFaceInd=0 ;
   DWORD addrFI=0, addrUV, addrV, offs2 ;  //
   DWORD j=0 ;
   bool bUV ;

   pFBuf = (char *) lpFBuf ; pTmp= pFBuf ;
   //if ((*pFBuf!=0xww)&&(*(pFBuf+3)!=0xyy)) {
   //     chMB("This doesn't seem to be a Kamen Rider CW prefab file!") ; return ;
   //}
   dwStart = 0 ; pFBuf += dwStart ;            //Triangles 54 72 69 61 Positions  50 6F 73 69
   SendMessage(GetDlgItem(hwnd, ID_LIST), LB_ADDSTRING, 0, (LPARAM) " creating obj:") ;
   cnt= 0 ; lastJ= 0 ;
   nValue[0]= 0x54; nValue[1]= 0x72; nValue[2]= 0x69; nValue[3]= 0x61;          // Tria

        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 4) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ; fprintf( stream, "#") ;
            if (*(pFBuf+8)!= 0x73) {
                chMB("String 'Triangles' not found! - EXIT") ; return ;
            }
            addrFI = j ;
            fprintf( stream, " Triangles string at %lx\n", j) ;
        }
        else {
            chMB("String 'Triangles' not found! - EXIT") ; return ;
        }

   nValue[0]= 0; nValue[1]= 0; nValue[2]= 1; nValue[3]= 0; nValue[4]= 2; nValue[5]= 0;          // 0000 0100 0200
   do {
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 6) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ;
            addrFI = j ;
            fprintf( stream, "# 0000 0100 0200 at %lx\n", j) ;
        }
        else
            if (cnt==0) { chMB("0000 0100 0200 not found! - EXIT") ; return ; }
        FIaddr_arr[cnt]= j ; pFBuf -= 4 ; j -= 4 ;
        GetDW(pFBuf, j, FIcnt, false) ; FIcnt_arr[cnt]= FIcnt /2 ;
        fprintf( stream, "# FIs: %ld\n", FIcnt_arr[cnt]) ;
        log_FIs(stream, FIaddr_arr[cnt], minFaceInd, maxFaceInd, lastFaceInd, FIcnt_arr, cnt, false) ;
        pFBuf += 6 ; j += 6 ; if (cnt<7) cnt++ ; else {chMB("Too many submeshes!"); return ; }
        if (cnt==2) offs2= 0 ;  //break
   } while ((offs2!=0)&&(j<dwFileSize)) ;
   cnt= 0 ;
   nValue[0]= 7; nValue[1]= 0; nValue[2]= 0; nValue[3]= 0; nValue[4]= 3;    // Normals, BiNormals, Positions
   do {
        pFBuf = pTmp ; pFBuf += FIaddr_arr[cnt] ; j = FIaddr_arr[cnt] ;
        offs2 = FindBytes(lpFBuf, FIaddr_arr[cnt], dwFileSize-FIaddr_arr[cnt], nValue, 5) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ;
            if (*(pFBuf+8)==1) {
                    //fprintf( stream, "sig 07000000 at %lx\n", j) ;
                addrV= j + 17  ; Vaddr_arr[cnt]= addrV ;
                pFBuf += 8 + 5 ; j += 8 + 5 ;
                GetDW(pFBuf, j, vCnt, false) ;      //  size vBlock
                vCnt = vCnt/12 ; vCnt_arr[cnt]= vCnt ;
                fprintf( stream, "# verts at %lx, count: %ld\n", addrV, vCnt) ;
                cnt++ ; if (cnt==2) offs2= 0 ;
                //if (cnt==3) {             // we search behind FIS, so Normals/BiNorm sig is skipped
                //    offs2= 0 ; addrV= j + 17 ;
                //    fprintf( stream, "verts at %lx\n", addrV) ;
                //}
            }
        }
   } while ((offs2!=0)&&(j<dwFileSize)) ;
        //if (cnt!= 3) chMB("not all sigs for Norm/BiNorm/Pos found!\nModel will be faulty.") ;
   if (cnt==0) { chMB("Pos sig not found, no verts in model!\nExit.") ; return ; }
   log_Verts(Vaddr_arr[0], vCnt_arr[0], 12) ;
   fprintf( stream, "# SM 1 at %lx\n", Vaddr_arr[1]) ;
   log_Verts(Vaddr_arr[1], vCnt_arr[1], 12) ;

   pFBuf = (char *) lpFBuf ; j= 0 ; cnt=0 ;
   nValue[0]= 7; nValue[1]= 0; nValue[2]= 0; nValue[3]= 0; nValue[4]= 2;    // UVx
   do {
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 5) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ; fprintf( stream, "#") ;
            if (*(pFBuf+8)==1) {
                bUV= true ;
                //fprintf( stream, "sig 07000000 at %lx\n", j) ;
                addrUV= j + 17 ; UVaddr_arr[cnt]= addrUV ;
                fprintf( stream, "uvs at %lx\n", addrUV) ;
            }
            else bUV= false ;
        }

           pFBuf += 13 ; j += 13 ;                  // advance to UVs blocksize, DWord
           GetDW(pFBuf, j, uvCnt, false) ; uvCnt = uvCnt/8 ;
           if (uvCnt!=vCnt_arr[cnt]) {
               chMB("uv cnt doesn't match vCnt!") ;
               fprintf( stream, "uvs_%d cnt: %d at %lx != %d\n", cnt, uvCnt, j-4, vCnt_arr[cnt]) ;
               if (vCnt_arr[cnt]>100000) vCnt_arr[cnt]= 11174 ;
           }
           addrUV= UVaddr_arr[cnt] ;
           logUVs(addrUV, vCnt_arr[cnt], 8) ;
           if (cnt<1) cnt++ ; else offs2=0 ;        //break after submesh 2

    } while ((offs2!=0)&&(j<dwFileSize)) ;
}
```
(You'll need to patch this code again in case there's more than 2 submeshes!)
## Post #31
- Username: wjj162446
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 10, 2019 7:01 pm
- Post datetime: 2020-03-16T12:26:46+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2 ↑Mon Mar 16, 2020 7:45 pm at Mon Mar 16, 2020 7:45 pm
>
> 
This is the patch for KamenRider, submesh 2, very ugly but works for MDL__B00092_92.prefab (only tested model, so don't blame me).
.
submesh_2.png
Replace the function void SM_of_KR_CW_loop(HWND hwnd, char szPathname[], DWORD dwStart)  in the source here:
shakotay2 wrote: ↑Mon Mar 06, 2017 6:01 pm
by
Code: Select allvoid SM_of_KR_CW_loop(HWND hwnd, char szPathname[], DWORD dwStart)      //
{                                                                         // Kamen Rider City Wars
   char * pFBuf, *pTmp ;            // , szNo[4]
   BYTE cnt= 0 ;
   int nValue[16] ;
   //WORD wFaceIndCnt, wVertsCnt, wOffs2VBlock ;         //
   DWORD FIaddr_arr[9], FIcnt, FIcnt_arr[9], uvCnt, vCnt, UVaddr_arr[9], Vaddr_arr[9], vCnt_arr[9] ;  //
   DWORD minFaceInd = 16777215, maxFaceInd = 0, lastFaceInd=0 ;
   DWORD addrFI=0, addrUV, addrV, offs2 ;  //
   DWORD j=0 ;
   bool bUV ;

   pFBuf = (char *) lpFBuf ; pTmp= pFBuf ;
   //if ((*pFBuf!=0xww)&&(*(pFBuf+3)!=0xyy)) {
   //     chMB("This doesn't seem to be a Kamen Rider CW prefab file!") ; return ;
   //}
   dwStart = 0 ; pFBuf += dwStart ;            //Triangles 54 72 69 61 Positions  50 6F 73 69
   SendMessage(GetDlgItem(hwnd, ID_LIST), LB_ADDSTRING, 0, (LPARAM) " creating obj:") ;
   cnt= 0 ; lastJ= 0 ;
   nValue[0]= 0x54; nValue[1]= 0x72; nValue[2]= 0x69; nValue[3]= 0x61;          // Tria

        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 4) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ; fprintf( stream, "#") ;
            if (*(pFBuf+8)!= 0x73) {
                chMB("String 'Triangles' not found! - EXIT") ; return ;
            }
            addrFI = j ;
            fprintf( stream, " Triangles string at %lx\n", j) ;
        }
        else {
            chMB("String 'Triangles' not found! - EXIT") ; return ;
        }

   nValue[0]= 0; nValue[1]= 0; nValue[2]= 1; nValue[3]= 0; nValue[4]= 2; nValue[5]= 0;          // 0000 0100 0200
   do {
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 6) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ;
            addrFI = j ;
            fprintf( stream, "# 0000 0100 0200 at %lx\n", j) ;
        }
        else
            if (cnt==0) { chMB("0000 0100 0200 not found! - EXIT") ; return ; }
        FIaddr_arr[cnt]= j ; pFBuf -= 4 ; j -= 4 ;
        GetDW(pFBuf, j, FIcnt, false) ; FIcnt_arr[cnt]= FIcnt /2 ;
        fprintf( stream, "# FIs: %ld\n", FIcnt_arr[cnt]) ;
        log_FIs(stream, FIaddr_arr[cnt], minFaceInd, maxFaceInd, lastFaceInd, FIcnt_arr, cnt, false) ;
        pFBuf += 6 ; j += 6 ; if (cnt<7) cnt++ ; else {chMB("Too many submeshes!"); return ; }
        if (cnt==2) offs2= 0 ;  //break
   } while ((offs2!=0)&&(j<dwFileSize)) ;
   cnt= 0 ;
   nValue[0]= 7; nValue[1]= 0; nValue[2]= 0; nValue[3]= 0; nValue[4]= 3;    // Normals, BiNormals, Positions
   do {
        pFBuf = pTmp ; pFBuf += FIaddr_arr[cnt] ; j = FIaddr_arr[cnt] ;
        offs2 = FindBytes(lpFBuf, FIaddr_arr[cnt], dwFileSize-FIaddr_arr[cnt], nValue, 5) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ;
            if (*(pFBuf+8)==1) {
                    //fprintf( stream, "sig 07000000 at %lx\n", j) ;
                addrV= j + 17  ; Vaddr_arr[cnt]= addrV ;
                pFBuf += 8 + 5 ; j += 8 + 5 ;
                GetDW(pFBuf, j, vCnt, false) ;      //  size vBlock
                vCnt = vCnt/12 ; vCnt_arr[cnt]= vCnt ;
                fprintf( stream, "# verts at %lx, count: %ld\n", addrV, vCnt) ;
                cnt++ ; if (cnt==2) offs2= 0 ;
                //if (cnt==3) {             // we search behind FIS, so Normals/BiNorm sig is skipped
                //    offs2= 0 ; addrV= j + 17 ;
                //    fprintf( stream, "verts at %lx\n", addrV) ;
                //}
            }
        }
   } while ((offs2!=0)&&(j<dwFileSize)) ;
        //if (cnt!= 3) chMB("not all sigs for Norm/BiNorm/Pos found!\nModel will be faulty.") ;
   if (cnt==0) { chMB("Pos sig not found, no verts in model!\nExit.") ; return ; }
   log_Verts(Vaddr_arr[0], vCnt_arr[0], 12) ;
   fprintf( stream, "# SM 1 at %lx\n", Vaddr_arr[1]) ;
   log_Verts(Vaddr_arr[1], vCnt_arr[1], 12) ;

   pFBuf = (char *) lpFBuf ; j= 0 ; cnt=0 ;
   nValue[0]= 7; nValue[1]= 0; nValue[2]= 0; nValue[3]= 0; nValue[4]= 2;    // UVx
   do {
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 5) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ; fprintf( stream, "#") ;
            if (*(pFBuf+8)==1) {
                bUV= true ;
                //fprintf( stream, "sig 07000000 at %lx\n", j) ;
                addrUV= j + 17 ; UVaddr_arr[cnt]= addrUV ;
                fprintf( stream, "uvs at %lx\n", addrUV) ;
            }
            else bUV= false ;
        }

           pFBuf += 13 ; j += 13 ;                  // advance to UVs blocksize, DWord
           GetDW(pFBuf, j, uvCnt, false) ; uvCnt = uvCnt/8 ;
           if (uvCnt!=vCnt_arr[cnt]) {
               chMB("uv cnt doesn't match vCnt!") ;
               fprintf( stream, "uvs_%d cnt: %d at %lx != %d\n", cnt, uvCnt, j-4, vCnt_arr[cnt]) ;
               if (vCnt_arr[cnt]>100000) vCnt_arr[cnt]= 11174 ;
           }
           addrUV= UVaddr_arr[cnt] ;
           logUVs(addrUV, vCnt_arr[cnt], 8) ;
           if (cnt<1) cnt++ ; else offs2=0 ;        //break after submesh 2

    } while ((offs2!=0)&&(j<dwFileSize)) ;
}(You'll need to patch this code again in case there's more than 2 submeshes!)

How to use the code,sir,I don't know about C source too much
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-16T17:53:48+00:00
- Post Title: Re: Make_obj (C source)

> Reply from wjj162446 ↑Mon Mar 16, 2020 8:26 pm at Mon Mar 16, 2020 8:26 pm
>
> How to use the code,sir,I don't know about C source too muchBut this thread is for people who know how to use code: "compile this project with CodeBlocks 13.12 for example".

(PMed u)
## Post #33
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-31T15:14:06+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2 ↑Fri May 11, 2018 12:47 am at Fri May 11, 2018 12:47 am
>
> 
here's an update to the code after akderebur gave some hint
('%" means: modulo, i.e.   5 % 3 is 2)
Replacement for the for (i=0;i<SMcnt;i++) {...} loop in the code of the previous post:
Code: Select all   for (ii=0;ii<SMcnt*3;ii++) {
        i = ii / 3 ;
        if ((ii % 3)==0) {
            log_FIs(stream, FIaddr_arr[i], minFaceInd, maxFaceInd, lastFaceInd, FIcnt_arr, i) ;
            vCnt_arr[i] = lastFaceInd - startFI ; startFI = lastFaceInd ;
        }
   }
   for (i=0;i<SMcnt;i++) vCntSum += vCnt_arr[i] ;
   vStride = (BYTE) (vCnt / vCntSum / 3) ;
   for (ii=0;ii<SMcnt*3;ii++) {
        i = ii / 3 ;
        if ((ii % 3)==0) {
            fprintf( stream, "# vAddr: %x, %d\n", addrV, vCnt_arr[i]) ;
            log_short_Verts(addrV, vCnt_arr[i], vStride) ;          // vertex stride: 24 or 28 or ...
            log_short_UVs(addrV+8, vCnt_arr[i], vStride) ;
        }
        addrV += vCnt_arr[i]*vStride ;
   }
You'll have to introduce two BYTE variables, ii and vStride and a DWORD var vCntSum which has to be set to 0 when initializing.

remark: the code may appear to be more complicated than it is. It's originally one loop only but it had to be split up into two loops because of the auto calculation of vStride which requires vCntSum.
The modulo thingie just chooses the first of the 3 mesh copies to be logged.

Pay attention to the line calculating the vStride:
vStride = (BYTE) (vCnt / vCntSum / 3) ;

The /3 doesn't apply for all Geometry.bin, this one for example has only one mesh "copy" (although it looks like two, hehehe):
Wings Geometry-bin.jpg

Hello Shakotay! This code was included in your latest release of the tool? I'm trying to open skyforge models and got this error. Thanks for the tool!



skyforge.png (10.29 KiB) Viewed 152 times
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-31T18:02:49+00:00
- Post Title: Re: Make_obj (C source)

> Reply from moonpaladin ↑Wed Mar 31, 2021 11:14 pm at Wed Mar 31, 2021 11:14 pm
>
> Hello Shakotay! This code was included in your latest release of the tool?
Nope, as stated in the post you had to copy the code snippet into the project all by yourself!  

I've modified that post so that there's the whole Skyforge function in the code tags to simplify the thing.

> Reply from shakotay2 ↑Fri May 11, 2018 12:47 am at Fri May 11, 2018 12:47 am
>
> 

> I'm trying to open skyforge models and got this error. Thanks for the tool!Whatever exe you used it expects a vhm file (don't remember why, maybe another format version?)

As I wrote it's up to the users to update the code, I don't remember having released a patched exe version.

btw: if you meet an error message when compiling such as "too many parameters for log_FIs()" then you need the main.cpp from a more recent zip as a base.
## Post #35
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-31T18:47:26+00:00
- Post Title: Re: Make_obj (C source)

> Whatever exe you used it expects a vhm file (don't remember why, maybe another format version?)
>
> 
>
> As I wrote it's up to the users to update the code, I don't remember having released a patched exe version.
>
> 
>
> btw: if you meet an error message when compiling such as "too many parameters for log_FIs()" then you need the main.cpp from a more recent zip as a base.

Hello, Shakotay, I will try to compile it, I just hope that later it does not keep asking me for a "vhm" file because otherwise it will not work xD.
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-31T19:21:22+00:00
- Post Title: Re: Make_obj (C source)

> Reply from moonpaladin ↑Thu Apr 01, 2021 2:47 am at Thu Apr 01, 2021 2:47 am
>
> 
I just hope that later it does not keep asking me for a "vhm" file because otherwise it will not work xD.edit: simply use the latest source and you're done. Don't change the code.

btw: for the latest model you uploaded, it doesn't work anyways, as I wrote here:

> Reply from shakotay2 ↑Thu Apr 01, 2021 2:30 am at Thu Apr 01, 2021 2:30 am
>
>
## Post #37
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-31T20:26:32+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2 ↑Thu Apr 01, 2021 3:21 am at Thu Apr 01, 2021 3:21 am
>
> 
moonpaladin wrote: ↑Thu Apr 01, 2021 2:47 am
I just hope that later it does not keep asking me for a "vhm" file because otherwise it will not work xD.You need to overwrite an existing void SM_of_Skyforge_loop() {...} function in the code (if any), of course!  

btw: for the latest model you uploaded, it doesn't work anyways, as I wrote here:
shakotay2 wrote: ↑Thu Apr 01, 2021 2:30 am
 Shakotay!I'm trying to build it but got this error! any advices? xD



codeblock.png (76.13 KiB) Viewed 134 times
## Post #38
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-01T10:21:27+00:00
- Post Title: Re: Make_obj (C source)

1) which source did you use (from which zip)?
#include <windows.h> is required

Update the source! You have 45 warnings - the last revised source creates 11 only for me!

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 
2) check your "build log" window for used libraries (it's .a here, not .lib):

-------------- Build: Release in Makeobj-obj (compiler: GNU GCC Compiler)---------------

mingw32-g++.exe -LD:\projects\Make_H2O\bin\Release 
-o bin\Release\Make_obj.exe obj\Release\main.o  obj\Release\Menu.res 
-s  -lgdi32 bin\Release\libDLL_MakeH2O.a 
...
"C:\Program Files (x86)\CodeBlocks\MinGW\lib\libcomdlg32.a" 
D:\projects\Make_H2O\bin\Release\libDLL_MakeH2O.a 
...
 -mwindows

btw: there's a reference to the (old) base \Make_H2O directory in my Make_obj project, shouldn't matter here
## Post #39
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-01T15:40:36+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2 ↑Thu Apr 01, 2021 6:21 pm at Thu Apr 01, 2021 6:21 pm
>
> 
1) which source did you use (from which zip)?
#include <windows.h> is required

Update the source! You have 45 warnings - the last revised source creates 11 only for me!
shakotay2 wrote: ↑Mon Mar 06, 2017 6:01 pm
2) check your "build log" window for used libraries (it's .a here, not .lib):

-------------- Build: Release in Makeobj-obj (compiler: GNU GCC Compiler)---------------

mingw32-g++.exe -LD:\projects\Make_H2O\bin\Release 
-o bin\Release\Make_obj.exe obj\Release\main.o  obj\Release\Menu.res 
-s  -lgdi32 bin\Release\libDLL_MakeH2O.a 
...
"C:\Program Files (x86)\CodeBlocks\MinGW\lib\libcomdlg32.a" 
D:\projects\Make_H2O\bin\Release\libDLL_MakeH2O.a 
...
 -mwindows

btw: there's a reference to the (old) base \Make_H2O directory in my Make_obj project, shouldn't matter here

Shakotay! ok I got the latest source it had two functions related to skyforge, I just deleted them and place the snippet code that you mention. As you can see in the image it show some warnings and also an error, that function need a boolean value at the end, I suppose it should be true, or replace that  log_FIs for log_FIsBigE, anyways I tested both cases and it compiles but the .obj generated of using the tool cannot be opened. Any advices? 



error7.jpg (247.16 KiB) Viewed 111 times
## Post #40
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-01T15:55:38+00:00
- Post Title: Re: Make_obj (C source)

In case it helps, this is the error that jumps in blender.



error8.jpg (55.73 KiB) Viewed 109 times
## Post #41
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-01T17:18:06+00:00
- Post Title: Re: Make_obj (C source)

Simply use the latest source/main.cpp as of yesterday, 21:49 and you're done. Don't change the code. Don't insert anything, don't delete anything.

(Or even simpler use the contained Make_obj-GodSu.exe and switch to Skyfo in the right lower combo box.)
## Post #42
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-01T18:26:54+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2 ↑Fri Apr 02, 2021 1:18 am at Fri Apr 02, 2021 1:18 am
>
> 
Simply use the latest source/main.cpp as of yesterday, 21:49 and you're done. Don't change the code. Don't insert anything, don't delete anything.

(Or even simpler use the contained Make_obj-GodSu.exe and switch to Skyfo in the right lower combo box.)

Yep, I tried with it and got an error on blender or it load but looks like a square with a lot of mess inside.
## Post #43
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-01T18:37:44+00:00
- Post Title: Re: Make_obj (C source)

Without the model sample in question I can't help. You should know that.
## Post #44
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-01T19:11:33+00:00
- Post Title: Re: Make_obj (C source)

> Reply from shakotay2 ↑Fri Apr 02, 2021 2:37 am at Fri Apr 02, 2021 2:37 am
>
> 
Without the model sample in question I can't help. You should know that.
Here you have:

[https://www.mediafire.com/file/vygr6dig ... y.bin/file](https://www.mediafire.com/file/vygr6digmpngi2i/Ripper-Base-Geometry.bin/file)

[https://www.mediafire.com/file/ms52gdk6 ... y.bin/file](https://www.mediafire.com/file/ms52gdk6gdmoeiz/Raptor-Base-Geometry.bin/file)
## Post #45
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-01T19:55:31+00:00
- Post Title: Re: Make_obj (C source)

Thanks - well, did you read here?

> Reply from shakotay2 ↑Thu Apr 01, 2021 2:30 am at Thu Apr 01, 2021 2:30 am
>
> 

Maybe I was not clear enough: Make_obj Skyforge version DOESN'T work with those samples,
because their first face indices blocks doesn't start with 000001000200.

You need to be a coder to adjust the code or simply use hex2obj.

But, of course, there is a way, which I'm confused to not see it earlier:  

just patch 000001000200 into the ripper bin at 0xD4950 (insert mode, NO overwrite), then 
replace
vStride = (BYTE) (vCnt / vCntSum / 3) ; 
by
vStride = 24 ;

result:
.



ripper.png (46.95 KiB) Viewed 87 times
## Post #46
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-01T20:28:09+00:00
- Post Title: Re: Make_obj (C source)

Thanks gonna try that!
