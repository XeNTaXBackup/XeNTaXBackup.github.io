## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-10-25T02:51:24+00:00
- Post Title: [Request]COD3 mesh fix and import script

shakotay2 has found the way for convert the meshes from call of duty 3 to obj with uv, but the face indices are damaged
he say that the models are in half floats





someone knows how to fix this? and... is possible create a importer script?

the eichar.cod contains all data including textures, and the single ps3mesh file is the model:
[http://www.mediafire.com/download/m1hvj ... acters.RAR](http://www.mediafire.com/download/m1hvj5w0h9gvk5s/Characters.RAR)
here other bundles: [http://www.mediafire.com/download/1ncp0 ... c/char.rar](http://www.mediafire.com/download/1ncp0x1pdc4bjhc/char.rar)


thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-25T11:23:43+00:00
- Post Title: [Request]COD3 mesh fix and import script

The faces are tri stripped:
[](http://www.pic-upload.de/view-21126415/pnzgren_head.jpg.html) [](http://www.pic-upload.de/view-21142651/head_tris_prob.jpg.html)

The problem is to replace the FF FF indices. I used the previous index but this does not seem to be correct.

edit: hmm, yes, the solution seems to be to start a new read of f1 and f2 after encountering FF FF.

edit2: weird. Seems FF FF indicates a change of the faces' orientation. Means half of the texture is outside the other half inside.

So I changed the orientation of the newly read f1,f2,f3 but at no avail.
This seems to be above my imagination.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-10-26T00:25:33+00:00
- Post Title: [Request]COD3 mesh fix and import script

if you are using c++ i can give my strip cut index code. u don't change the winding order on every reset, though I've seen a problem like this before (tekken hybrid). rich though i might have been missing a flag or something but i could never find it so i did what only the desperate would do... the vertex normals were good so based on that i flipped the polygons.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-26T05:09:08+00:00
- Post Title: [Request]COD3 mesh fix and import script

> Reply from howfie
>
> if you are using c++ i can give my strip cut index code.Yep - (it's "normal" C but) that would be very nice.

> rich though i might have been missing a flag or something butthis seems to be my problem, too.

> i could never find it so i did what only the desperate would do... the vertex normals were good so based on that i flipped the polygons.Yes, desperate I am...  
I'm calculating surfcace normals but I have no clue how to decide whether they point into or outside the head.

For example these two having the same direction:
[](http://www.pic-upload.de/view-21134885/in_out.jpg.html)

I know "normals point towards the side from which the vertices appear in counterclockwise order"
but seems I'll have to understand back face culling, too?
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-10-26T14:14:43+00:00
- Post Title: [Request]COD3 mesh fix and import script

Pseudo-code to convert tristrips with strip-cut indices to triangle lists.

```
 boost::shared_array<uint16> data;
 uint32 n_indices;
 uint32 triangles;
};

bool ConvertStripCutToTriangleList(const uint16* src, uint32 n, TriangleList& dst, uint16 terminal = 0xFFFF)
{
 // validate
 if(!src || !n) return false;
 if(n < 3) return false;

 // compute number of triangles
 uint32 n_triangles = 0;
 uint32 a = 0;
 uint32 b = 0;
 for(;;)
    {
     // must stop
     if(b == n) {
        if(src[n - 1] != terminal) {
           uint32 distance = b - a;
           if(distance < 3) return false;
           n_triangles += distance - 2;
          }
        break;
       }

     // hit terminal index
     if(src[b] == terminal) {
        uint32 distance = b - a;
        if(distance < 3) return false;
        n_triangles += distance - 2;
        a = b + 1;
        b = a;
       }
     // non-terminal index
     else
        b++;
    }

 // initialize destination data
 dst.triangles = n_triangles;
 dst.n_indices = n_triangles * 3;
 dst.data.reset(new uint16[dst.n_indices]);

 // initialize second pass data
 uint16* ptr = dst.data.get();
 uint32 dst_index = 0;
 uint32 src_index = 0;

 // second pass through source
 do {

     // keep track of tristrip index
     uint32 tristrip_index = 0;

     // copy first triangle
     uint16 a = src[src_index++];
     uint16 b = src[src_index++];
     uint16 c = src[src_index++];
     ptr[dst_index++] = a;
     ptr[dst_index++] = b;
     ptr[dst_index++] = c;
     tristrip_index++;
    
     // copy other triangles
     while(src_index < n) {
         a = b;
         b = c;
         c = src[src_index++];
         if(c == terminal) break;
         if(tristrip_index % 2) {
            ptr[dst_index++] = a;
            ptr[dst_index++] = c;
            ptr[dst_index++] = b;
           }
         else {
            ptr[dst_index++] = a;
            ptr[dst_index++] = b;
            ptr[dst_index++] = c;
           }
         tristrip_index++;
        }
    }
 while(src_index < n);

 return true;
}

```
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-26T20:03:25+00:00
- Post Title: [Request]COD3 mesh fix and import script

Thank you very much!  

Just to be sure : I need the boost library to use this?

Hopefully it will solve this prob:
[](http://www.pic-upload.de/view-21142438/normals4ever.jpg.html)

It's the "submesh" before the first FF FF separator ("terminal") where I think the normals marked with a thin white line have the wrong direction.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-10-27T06:05:58+00:00
- Post Title: [Request]COD3 mesh fix and import script

oh, the geometry even before the first terminal is messed up? you dont need boost, just replace it with you own memory management scheme.
## Post #8
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-10-27T21:05:28+00:00
- Post Title: [Request]COD3 mesh fix and import script

> Reply from luxox18
>
> shakotay2 has found the way for convert the meshes from call of duty 3 to obj with uv, but the face indices are damaged
he say that the models are in half floats

Hey, have you checked this blender add-on? it has export-import functions for many COD titles, not entirely sure if COD3 works, but code can help.

[https://code.google.com/p/blender-cod/](https://code.google.com/p/blender-cod/)
## Post #9
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-10-28T00:01:09+00:00
- Post Title: [Request]COD3 mesh fix and import script

> Reply from Bastien
>
> 
Hey, have you checked this blender add-on? it has export-import functions for many COD titles, not entirely sure if COD3 works, but code can help.

https://code.google.com/p/blender-cod/

This script is for import models to a call of duty format , not for convert the models from COD3 to obj , etc.

Call of duty 3 not use xmodels.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-28T14:55:46+00:00
- Post Title: [Request]COD3 mesh fix and import script

> Reply from howfie
>
> oh, the geometry even before the first terminal is messed up?it's the first "submesh" only. Don't think it's messed up but the normals directions are, imho.

Finally I managed to use your code but maybe I did something wrong:
[](http://www.pic-upload.de/view-21162016/pnzgren_head_missing_faces.jpg.html)

edit: yes, I surely did  :
[](http://www.pic-upload.de/view-21163147/pzngren_head-ok.jpg.html) Very fine!

Few normals at ears and mouth pointing inside. But does not seem to affect the texture.
This is how I used your code (in case someone else faces this prob):

```
const WORD* src ;

struct TriangleList {
boost::shared_array<WORD> data;
DWORD n_indices;
DWORD triangles;
} dst ;

//Modification in ConvertStripCutToTriangleList() due to big endian indices:

     WORD aBE = src[src_index++]; WORD a= (aBE % 256) * 256 + aBE/256 ;
     WORD bBE = src[src_index++]; WORD b= (bBE % 256) * 256 + bBE/256 ;
     WORD cBE = src[src_index++]; WORD c= (cBE % 256) * 256 + cBE/256 ;

     ...
     cBE = src[src_index++]; c= (cBE % 256) * 256 + cBE/256 ;

   main() {
         boost::shared_array<WORD> dst.data(new WORD[65535]);
	// loading of model data at lpFBuf, face indices start address= 0xAB30        // 2* 0x5598 
	 src = (WORD *) lpFBuf ; src += 0x5598 ;
	 ConvertStripCutToTriangleList(src, 4417, dst, 0xFFFF) ;   // 4417= face indices count
}
```
Thx again, sire!
## Post #11
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-10-28T22:07:11+00:00
- Post Title: [Request]COD3 mesh fix and import script

> Reply from shakotay2
>
> 

edit: yes, I surely did  :
 Very fine!

Wow! good news!
## Post #12
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-11-06T23:40:19+00:00
- Post Title: [Request]COD3 mesh fix and import script

with the HEX2OBJ tool we can convert all models from this game. [viewtopic.php?f=29&t=10894](http://forum.xentax.com/viewtopic.php?f=29&t=10894)

thanks to shakotay2

this is the results
