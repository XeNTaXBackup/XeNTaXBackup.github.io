## Post #1
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-03T07:41:50+00:00
- Post Title: Red Ninja PS2 Models .QMX

Hi guys, is there a way to extract models from this game?, model files are .QMX

The model is made by a lot of submeshes, I analyzed the file "000163.QMX" first submesh is at 0x2C00, this is some kind of header(all submeshes have this).
then at 0x2C30 I think 1st byte is vertices count, 2nd byte is always 80, 0x2C50 is the start of vertices(1st submesh). I am not sure about UVs maybe at 0x2C60?

There is no faces data so maybe are autogenerated. I don't know if all this info is correct, here is the sample:


 000163.rar
(62.91 KiB) Downloaded 18 times



Thanks!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-03T12:03:53+00:00
- Post Title: Red Ninja PS2 Models .QMX

I could have sworn I'd checked for vertices, but seems I got uvs and normals:
.



Qmx.jpg (86.85 KiB) Viewed 200 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-03T12:10:26+00:00
- Post Title: Red Ninja PS2 Models .QMX

on another try:
.



Qmx_betterOne.png (14.73 KiB) Viewed 200 times
## Post #4
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-03T19:31:06+00:00
- Post Title: Red Ninja PS2 Models .QMX

> Reply from shakotay2 ↑Mon Apr 03, 2023 8:03 pm at Mon Apr 03, 2023 8:03 pm
>
> 
I could have sworn I'd checked for vertices, but seems I got uvs and normals:

Yeah, I got something similar, vertices, Uvs and normals at the same time, that is so weird.. I will try to check Xbox version, maybe it will be more easy. I will upload the Xbox sample later, thanks!
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-03T20:47:37+00:00
- Post Title: Red Ninja PS2 Models .QMX

> Reply from roocker666 ↑Tue Apr 04, 2023 3:31 am at Tue Apr 04, 2023 3:31 am
>
> 
, that is so weird..No. It's simply a matter of starting with vertices at 0x2C70 instead of 0x2C50, imho (uvs assumed to be at 0x2C50 then, but didn't check this).

And 'yes', autocreation of faces needs some trick, I guess (maybe some vertex grouping required?):
edit: nope, the "only" problem was: there's two different FVF sizes
.



Qmx_littleBitStrange.jpg (100.79 KiB) Viewed 178 times
## Post #6
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-04T00:23:23+00:00
- Post Title: Red Ninja PS2 Models .QMX

> Reply from shakotay2 ↑Tue Apr 04, 2023 4:47 am at Tue Apr 04, 2023 4:47 am
>
> 
roocker666 wrote: ↑Tue Apr 04, 2023 3:31 am
, that is so weird..No. It's simply a matter of starting with vertices at 0x2C70 instead of 0x2C50, imho (uvs assumed to be at 0x2C50 then, but didn't check this).

And 'yes', autocreation of faces needs some trick, I guess (maybe some vertex grouping required?):

NIce, it is looking better. I guess you are right, I found a 2nd group at 0x39980. It seems like ID for groups is 03 04 01 00, so in total two groups of submeshes.
## Post #7
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-09T04:03:46+00:00
- Post Title: Red Ninja PS2 Models .QMX

All right, I did a deep research. We have 2 main groups but each main group has more groups with submeshes.

So it is something like this:

0x2AD0 MAIN GROUP1(ID 03 04 01 00)

	0x2B00 1ST GROUP HEADER(48 SUBMESHES). 0x2B88 IS SUBMESHES COUNT
  	0x2C00 1ST GROUP-1ST SUBMESH, 2ND SUBMESH, 3RD SUBMESH, ETC..

  	0x114B0 2ND GROUP HEADER(110 SUBMESHES). 0x11508 IS SUBMESHES COUNT
  	0x11580 2ND GROUP-1ST SUBMESH..

	0x325E0 3RD GROUP HEADER(25 SUBMESHES). 0x32608 IS SUBMESHES COUNT
	0x32680 3RD GROUP-1ST SUBMESH..



0x39980 MAIN GROUP2(ID 03 04 01 00) 

	0x399B0 1ST GROUP HEADER(6 SUBMESHES). 0x39A0A8 IS SUBMESHES COUNT
  	0x39A80 1ST GROUP-1ST SUBMESH..


I still don't know about vertices count, for example in MAIN GROUP1/1st GROUP-1ST SUBMESH, it could be at  0x2C30 or 0x2C4E(1BYTE).
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-09T06:58:43+00:00
- Post Title: Red Ninja PS2 Models .QMX

> Reply from roocker666 ↑Sun Apr 09, 2023 12:03 pm at Sun Apr 09, 2023 12:03 pm
>
> 
All right, I did a deep research. We have 2 main groups but each main group has more groups with submeshes.Cool! 

> I still don't know about vertices count, ...I'd already forgotten how I got it. Here's the code. The trick is:  vCnt-32768 to find the real value.

```
        nValue[0]= 0xDD; nValue[1]= 0xDD; nValue[2]= 0xDD; nValue[3]= 0xDD;    // assumed signature of vBlock headers
        nValue[4]= 0xEE; nValue[5]= 0xEE; nValue[6]= 0xEE; nValue[7]= 0xEE;
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 8) ;
        if (offs2!=0) {
            pFBuf += offs2 -4; j += offs2 -4;
            addr[cnt]= j +32 +32;  // vertex block, FVF= 48
            GetDW(pFBuf, j, vCnt, false) ;
            if (vCnt>32767) {
                fprintf(stream, "DD...EE...: %lx, %lx\n", vCnt-32768, addr[cnt]) ;
                dwVertsCnt[cnt]= vCnt-32768;
                if (cnt<197) cnt++ ;                                                 // next submesh
            } else chMB("vCnt error!") ;
            //wVertsCnt= (WORD) vCnt ;
            pFBuf += 16 ; j += 16 ;                               // skip signature bytes
        }
        else bStop= true ;
   } while (!bStop&&(j<dwFileSize)) ;
```


When I collect the first 48 sub meshes only it looks like so (degenerated faces erased, thus a lot of faces are missing):
.



Qmx_48_sub_meshes.png (12.46 KiB) Viewed 126 times
## Post #9
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-09T22:52:41+00:00
- Post Title: Red Ninja PS2 Models .QMX

> Reply from shakotay2 ↑Sun Apr 09, 2023 2:58 pm at Sun Apr 09, 2023 2:58 pm
>
> 
roocker666 wrote: ↑Sun Apr 09, 2023 12:03 pm
All right, I did a deep research. We have 2 main groups but each main group has more groups with submeshes.Cool! 

I still don't know about vertices count, ...
I'd already forgotten how I got it. Here's the code. The trick is:  vCnt-32768 to find the real value.


When I collect the first 48 sub meshes only it looks like so (degenerated faces erased, thus a lot of faces are missing):

If our info is correct, Why do We still got wrong or missing polygons? BTW, UVs in 1st submesh are at 0x2C50, so you were right about that.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-10T06:21:12+00:00
- Post Title: Red Ninja PS2 Models .QMX

> Reply from roocker666 ↑Mon Apr 10, 2023 6:52 am at Mon Apr 10, 2023 6:52 am
>
> If our info is correct, Why do We still got wrong or missing polygons?Seems half of the vertices are doubles (one of the the main problems when "extracting" PS2 models). But about 50% that's really a lot - I have no idea, why.
## Post #11
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-11T05:25:01+00:00
- Post Title: Red Ninja PS2 Models .QMX

> Reply from shakotay2 ↑Mon Apr 10, 2023 2:21 pm at Mon Apr 10, 2023 2:21 pm
>
> 
Seems half of the vertices are doubles (one of the the main problems when "extracting" PS2 models). But about 50% that's really a lot - I have no idea, why.

I see. Well, at least We tried lol, Thank you for all your help man!
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-11T06:40:12+00:00
- Post Title: Red Ninja PS2 Models .QMX

PS2 character models are almost always a pita to convert to .obj.  A static mesh (chest, table, plank or something similar) might be easier to get a clue.
## Post #13
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-11T07:23:25+00:00
- Post Title: Red Ninja PS2 Models .QMX

> Reply from shakotay2 ↑Tue Apr 11, 2023 2:40 pm at Tue Apr 11, 2023 2:40 pm
>
> 
PS2 character models are almost always a pita to convert to .obj.  A static mesh (chest, table, plank or something similar) might be easier to get a clue.

I know!, that sucks.. Ok, ok, I found something weird, some submeshes have other format, I mean vertices, Uvs and normals are in other place and use other padding(if you compare this submesh#8 with submesh#1). So we have two different submeshes format.(I did not check the other groups yet..)

Here is a picture:



submesh_8.jpg (201.86 KiB) Viewed 79 times



I am pretty sure that blue square is vertices count, green square could be related to faces(I really don't know...)

You can see that submesh#1 and submesh#8 also have different padding. I am not sure if in submesh#8 vertices and Uvs offsets are correct, I am still trying to find the answer. Submesh header in both looks the same, so no problem with that.
## Post #14
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-11T07:45:31+00:00
- Post Title: Red Ninja PS2 Models .QMX

It is hard to identify all models because there are no names, just numbers. But here is a weapon(katana), it has only 7 submeshes:


 000170 katana.rar
(2.79 KiB) Downloaded 14 times
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-11T09:01:31+00:00
- Post Title: Red Ninja PS2 Models .QMX

Thanks to your hint concerning the different FVF sizes (48 and 64 so far) we get more vertices now:
.



163_qmx.png (34.41 KiB) Viewed 55 times


(H2O files see next post)
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-11T09:52:08+00:00
- Post Title: Re: Red Ninja PS2 Models .QMX

000163.QMX_188-uvs.zip
(28.79 KiB) Downloaded 16 times


Load 000163.qmx into hex2obj then
use "Fake FIs" and File/SaveAs Mmesh

(for FVFsize=48 the uv address is vAddr-32, as mentioned already.
 For FVFsize=64 I chose 64 16, not sure whether that's correct.)

Use this py script for importing multiple obj files into blender (adjust drive letter and the path to the obj files):

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
# this line will only work on windows ie C:\objects
path_to_obj_dir = os.path.join('D:\\', 'path to\\obj files')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```
## Post #17
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-12T00:00:06+00:00
- Post Title: Re: Red Ninja PS2 Models .QMX

> Reply from shakotay2 ↑Tue Apr 11, 2023 5:52 pm at Tue Apr 11, 2023 5:52 pm
>
> 

(for FVFsize=48 the uv address is vAddr-32, as mentioned already.
 For FVFsize=64 I chose 64 16, not sure whether that's correct.)

ok!, Thanks for H2O files and Blender script. I guess we got it, I deleted those extra polygons and applied the texture, it looks good but in some submeshes UVs are wrong. Maybe are those FVFsize=64, I think UVs should be same formula as FVFsize=48(vAddr-32)

Here is my result:
[RED NINJA1.jpg](https://xentaxbackup.github.io/file/23657_RED NINJA1.jpg)
## Post #18
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-12T00:01:14+00:00
- Post Title: Re: Red Ninja PS2 Models .QMX

UVs:



RED NINJA2.jpg (140.33 KiB) Viewed 61 times
## Post #19
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-12T07:47:23+00:00
- Post Title: Re: Red Ninja PS2 Models .QMX

> Reply from shakotay2 ↑Tue Apr 11, 2023 5:52 pm at Tue Apr 11, 2023 5:52 pm
>
> 

 For FVFsize=64 I chose 64 16, not sure whether that's correct.)

Oh, now I understand. UVs for FVFsize=64 looks better with 64 32. Maybe that is the correct value..
