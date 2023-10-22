## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2015-06-13T02:33:11+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

Edit; I now have a decompressed model file which is .psp.orb but I don't know what to do with it. Can someone help?
[https://mega.co.nz/#!C5E3waBS!Y5OdUUlM_ ... zRrT19ZNQU](https://mega.co.nz/#!C5E3waBS!Y5OdUUlM_U8pDPtbH39iBAioDqy9N1yh4zRrT19ZNQU)

I need some help being able to import the models for this game. I think the model/texture format is .psp.org and .giz file type. I'm not sure if they're compressed files or something, but I can't find anything to open, view, or extract them. I don't mind what program is used, just please help! I'm not very knowledgeable in binary and such. xD;

 Is what the models look like if you wanted to know~

Thanks in advance!
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-06-13T14:48:27+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

quickbms script to get decompressed models

```
#extract GAMEDATA.CFI from Conception_Ore_no_Kodomo_wo_Undekure
get SUBFILES byte
set COUNT 0
comtype gzip
for a = 0 < SUBFILES
get NSIZE byte
getdstring FOLDER NSIZE
savepos tmp
get test byte
if test == 0xFC
get FILES short
else
goto tmp
get FILES byte
endif
for i = 0 < files
get NSIZE byte
math NSIZE -= 4
getdstring FILE NSIZE
getdstring EXT 4
get OFFSET long
get SIZE long
set NAME FOLDER
string NAME += FILE
        putarray 0 COUNT OFFSET
        putarray 1 COUNT SIZE
        putarray 2 COUNT NAME 
        putarray 3 COUNT EXT 
math COUNT += 1
next i
next a
savepos BASEOFF
for i = 0 < COUNT
        getarray OFFSET 0 i
        getarray ZSIZE 1 i
        getarray NAME 2 i
        getarray EXT 3 i
	if EXT == ".giz"
	set EXT ".gim"
	endif
	string NAME += EXT
        math OFFSET += BASEOFF
	if EXT == ".txt"
	log NAME OFFSET ZSIZE
	elif  EXT == ".dat"
	log NAME OFFSET ZSIZE
	elif  EXT == ".PNG"
	log NAME OFFSET ZSIZE
	elif  EXT == ".sbk"
	log NAME OFFSET ZSIZE
	else
	goto OFFSET
	get SIZE long
        math ZSIZE -= 4
	savePOS OFFSET
        clog NAME OFFSET ZSIZE SIZE
	endif
next i


```


.giz are just renamed .gim psp textures.
## Post #3
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2015-06-15T02:42:15+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

> Reply from chrrox
>
> quickbms script to get decompressed models]

Thank you!! What do I do with the .psp.orb files now though? I assume thats the mesh.
## Post #4
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2015-07-08T21:41:25+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

Bump~~~~.
## Post #5
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2015-10-24T22:54:31+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

Still looking for someone to help with the model file! :'3
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-25T08:19:16+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

> Reply from anime663
>
> Still looking for someone to help with the model file! :'3that's the fate of those who are waiting for the mysterious Mr. Someone who's hiding in this forum (we all know that).  

Why not use hex2obj to get some promissing point cloud since there seem to be some:



Someone'sHidingInThisPointCloud.JPG (42.22 KiB) Viewed 319 times


(FVF 12 (just guessed)
format: ShortAll
start of vertices: 0x9E50, first attempt)
## Post #7
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2015-11-20T05:18:48+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

> Reply from shakotay2
>
> anime663 wrote:Still looking for someone to help with the model file! :'3that's the fate of those who are waiting for the mysterious Mr. Someone who's hiding in this forum (we all know that).  

Why not use hex2obj to get some promissing point cloud since there seem to be some:
Someone'sHidingInThisPointCloud.JPG
(FVF 12 (just guessed)
format: ShortAll
start of vertices: 0x9E50, first attempt)

See, I would try to use hex2obj but I have like 0 experience in scripting and stuff xD. I'm currently taking a CS class but I'm just a beginner.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-06T02:24:30+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

trying to read the bonenames reveals a strange format: varying blocklength (70, 74, 110 bytes) + 1 + name length:



bones_psp_orb.JPG (38.99 KiB) Viewed 281 times

(thus the bone ids start from 0 again for each new starting point)

some progress:
1 *base* 0
2 *base Pelvis* 1
3 *base Spine* 2
4 *base Spine1* 3
5 *base Neck* 4
6 *base Head* 5
7 *face_pos* 6
8 *mouth* 7
9 *lip_UpC* 8
10 *jaw* 8
11 *lip_UpR* 8
12 *lip_UpL* 8
13 *lip_SR* 8
14 *lip_SL* 8
15 *lip_LoR* 8
16 *lip_LoC* 8
17 *lip_LoL* 8
18 *head_pos* 6
19 *hair_01* 22
20 *hair_02* 23
21 *hair_03* 24
22 *hair_04* 25
23 *acce_head* 6
24 *acce_ear_L* 6
25 *acce_ear_R* 6
26 *acce_eye* 6
27 *base L Clavicle* 5
28 *base L UpperArm* 34
29 *base L Forearm* 35
30 *base L Hand* 36
31 *base L Finger0* 37
32 *base L Finger01* 38
33 *base L Finger02* 39
34 *base L Finger1* 37
35 *base L Finger11* 41
36 *base L Finger12* 42
37 *base L Finger2* 37
38 *base L Finger21* 44
39 *base L Finger22* 45
40 *base L Finger3* 37
41 *base L Finger31* 47
42 *base L Finger32* 48
43 *base L Finger4* 37
44 *base L Finger41* 50
45 *base L Finger42* 51
46 *col_L_arm* 35
47 *cape_SfL* 34
48 *cape_SL* 34
49 *cape_SbL* 34
50 *cape_FoL* 34
[...]
85 *bust_L* 4
86 *col_body03* 4
87 *col_body01* 4
88 *col_body02* 4
89 *acce_body* 4
90 *base L Thigh* 2
91 *base R Thigh* 2

(From bone IDs > 27 the parenting IDs seem to have a wrong offset of 7, though.)
## Post #9
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-01-24T02:42:21+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

Anyone?
## Post #10
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-01-24T02:43:01+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

> Reply from shakotay2
>
> trying to read the bonenames reveals a strange format: varying blocklength (70, 74, 110 bytes) + 1 + name length:
bones_psp_orb.JPG(thus the bone ids start from 0 again for each new starting point)

some progress:
1 *base* 0
2 *base Pelvis* 1
3 *base Spine* 2
4 *base Spine1* 3
5 *base Neck* 4
6 *base Head* 5
7 *face_pos* 6
8 *mouth* 7
9 *lip_UpC* 8
10 *jaw* 8
11 *lip_UpR* 8
12 *lip_UpL* 8
13 *lip_SR* 8
14 *lip_SL* 8
15 *lip_LoR* 8
16 *lip_LoC* 8
17 *lip_LoL* 8
18 *head_pos* 6
19 *hair_01* 22
20 *hair_02* 23
21 *hair_03* 24
22 *hair_04* 25
23 *acce_head* 6
24 *acce_ear_L* 6
25 *acce_ear_R* 6
26 *acce_eye* 6
27 *base L Clavicle* 5
28 *base L UpperArm* 34
29 *base L Forearm* 35
30 *base L Hand* 36
31 *base L Finger0* 37
32 *base L Finger01* 38
33 *base L Finger02* 39
34 *base L Finger1* 37
35 *base L Finger11* 41
36 *base L Finger12* 42
37 *base L Finger2* 37
38 *base L Finger21* 44
39 *base L Finger22* 45
40 *base L Finger3* 37
41 *base L Finger31* 47
42 *base L Finger32* 48
43 *base L Finger4* 37
44 *base L Finger41* 50
45 *base L Finger42* 51
46 *col_L_arm* 35
47 *cape_SfL* 34
48 *cape_SL* 34
49 *cape_SbL* 34
50 *cape_FoL* 34
[...]
85 *bust_L* 4
86 *col_body03* 4
87 *col_body01* 4
88 *col_body02* 4
89 *acce_body* 4
90 *base L Thigh* 2
91 *base R Thigh* 2

(From bone IDs > 27 the parenting IDs seem to have a wrong offset of 7, though.)
Sorry I don't understand this stuff ^^" I have basically no knowledge of scripting whatsoever...
## Post #11
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-11T22:24:18+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

Ah, the ever-present quest to obtain more low-poly models of anime girls through tedious binary observation. Life is too short, gentlemen. Too short.
## Post #12
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-12T13:02:45+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

Bumping is broken, it shouldn't change the actual post date to the bump date.
## Post #13
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-06-24T05:48:20+00:00
- Post Title: [PSP] Conception Model File Help! (.psp.org/.giz)

I'm female lol. I just find the models to be quite pretty. Still looking for a kind soul to help me.
