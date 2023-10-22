## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-02-19T22:07:13+00:00
- Post Title: Supreme Snowboarding (1999) *.hx files

.hx file (SurRender 3D model): [https://mega.nz/file/oSBQwRjI#P-92an4o0 ... zQxe0TnjHI](https://mega.nz/file/oSBQwRjI#P-92an4o0VJr6owUV1mElpBXunW566yE2zQxe0TnjHI)
.skn file (skin weights): [https://mega.nz/file/ceI0iLKR#AmOmpIlqW ... bMrszKpB00](https://mega.nz/file/ceI0iLKR#AmOmpIlqWeVwPkaODVk7N91fsLWv-9Lm2bMrszKpB00)
.skl files (animations): [https://mega.nz/file/BGQyRZ5b#3VsOTNOI_ ... IfEa8NvBvQ](https://mega.nz/file/BGQyRZ5b#3VsOTNOI_y3PQZEPp2aC7y0Ua8LI8rAfUIfEa8NvBvQ)





I tried Hex2Obj with vincent.hx, but the 3D model seems broken.

I need to convert .skl to .fbx
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-19T22:51:34+00:00
- Post Title: Supreme Snowboarding (1999) *.hx files

> Reply from mrmaller1905 ↑Sun Feb 20, 2022 6:07 am at Sun Feb 20, 2022 6:07 am
>
> I tried Hex2Obj with vincent.hx, but the 3D model seems broken.
I wouldn't know, why  :
.



Vincent-hx.png (85.68 KiB) Viewed 99 times

(seems I missed a face at the back)

> I need to convert .skl to .fbxSounds hard to me.
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-20T14:32:00+00:00
- Post Title: Supreme Snowboarding (1999) *.hx files

> Reply from mrmaller1905 ↑Sun Feb 20, 2022 6:07 am at Sun Feb 20, 2022 6:07 am
>
> 
I need to convert .skl to .fbx
here's a good start for you. 
I made plugins that parse .skn and .skl files. you just need to tweak it a little.
(create matrices in .skl and deal with weights in .skn).

also i write here pseudocode:
.skn

```
int ver?
int num_bone

for num_bone:
	int id
	string name

seek(5)#SIGN
string nameModel
int count

for count:
	int idBone
        [float*4] data 
        int idVert

seek(10)#SIGN SIGN

```

.skl

```
int numBone
int unk

for numBone:
	seek(5)#SIGN
        string name
        string parentName
        int numFrame
        int unk
        
	for numFrame:
		28 bytes to matrix

seek(10)#SIGN SIGN

```

[Supreme.zip](https://xentaxbackup.github.io/file/21822_Supreme.zip)
## Post #4
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-04-19T16:48:50+00:00
- Post Title: Supreme Snowboarding (1999) *.hx files

Can you make a Noesis plugin for the *.hx format also?
