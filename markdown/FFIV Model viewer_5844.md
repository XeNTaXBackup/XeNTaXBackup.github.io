## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-18T21:13:28+00:00
- Post Title: FFIV Model viewer

any advance in FFIV model viewer or ripping?
## Post #2
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-01-19T11:35:29+00:00
- Post Title: FFIV Model viewer

yes, the model vewer already exists. search on google for more informations. this is the link of the source code:

[https://github.com/nohbdy/ffxivmodelviewer](https://github.com/nohbdy/ffxivmodelviewer)
## Post #3
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2011-01-19T16:47:17+00:00
- Post Title: FFIV Model viewer

Here's another one: [http://cosmosa.jp/ffxivtool/ffxivtool10102500.zip](http://cosmosa.jp/ffxivtool/ffxivtool10102500.zip)
## Post #4
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-19T20:38:02+00:00
- Post Title: FFIV Model viewer

Those are both for XIV, whereas the OP appeared to ask about IV. (I'd assume he meant the DS remake, unless it was a typo.)
## Post #5
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-02-11T09:07:31+00:00
- Post Title: FFIV Model viewer

Here is my maxscript code,,it can only extract head or small pieces of mesh.
and distorted,If you know correct pattern to decompress floats and location of
scale factor container,please let me know.
script:

update,fixed one major bug in stms loading,support type1 uv,ver 0.48
[http://www.sendspace.com/file/467p4d](http://www.sendspace.com/file/467p4d)
## Post #6
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-11T11:24:56+00:00
- Post Title: FFIV Model viewer

That is great falcon cool
## Post #7
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-02-11T22:50:03+00:00
- Post Title: FFIV Model viewer

In order to transform the distorted model into corrrect shape.I need ppl can read
Shader information for help.You can use model viewer to decompile them.in Sdrb section
 "file" chunck.

i find few quaternion vectors value store there.likely be the answer.
like the picture i showed.please help if you know this kind of stuff.




Here is one of the Registers definition .

```
//
//   Name                Reg   Size
//   ------------------- ----- ----
//   isSkining           b0       1
//   worldMatrix         c0       4
//   worldITMatrix       c4       3
//   worldViewProjMatrix c8       4
//   worldViewMatrix     c12      4
//   viewITMatrix        c16      4
//   jointMatrices       c21    144
//   ModelBBoxScale      c169     1
//   ModelBBoxOffSet     c170     1
//   PointLightPositions c171     2
//   PointLightColors    c173     2
//   PointLightParams    c175     2
//   EnableShadowFlag    c177     1
//   uvofs0              c178     1
//   uvofs1              c179     1
//   fogParam            c180     1


```


I know,c169,c170 is the value i want,but when i look back into hexeditor to seach the data stored in Shader chunck,I can't find any index help me to allocate c169,c170,
## Post #8
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-02-14T13:26:46+00:00
- Post Title: FFIV Model viewer

All known problems solved except still freeze when loading background objects.
Importer version 0.52. Gonna try skeleton and animation from now on.
[http://www.sendspace.com/file/9qrim2](http://www.sendspace.com/file/9qrim2)
## Post #9
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-02-16T22:30:20+00:00
- Post Title: FFIV Model viewer

This is what i'm trying to fix :/


The FF14's bones data use relative coordinate system(relative to parent)
I have to use parent's coordinate system to apply current one.

You can see it's direction is not correct.but offset values are okay.

This is it's source code come from
[https://github.com/nohbdy/ffxivmodelvie ... alFrame.cs](https://github.com/nohbdy/ffxivmodelviewer/blob/master/src/ModelViewer/Renderer/SkeletalFrame.cs)

my script for the bones is here.

```
----skl_Hierachy_array ----pattern [parent,children,Sibling]
----skl_Boneindex_array-----pattern [string index,bone index]

location_array = #()
rotation_array = #()
for cor_i = 1 to skl_bone_count do(

  qx = skl_Rotation_array[cor_i][1]
  qy = skl_Rotation_array[cor_i][2]
  qz = skl_Rotation_array[cor_i][3]
  qw = skl_Rotation_array[cor_i][4]
  skl_tfm = (quat qx qy qz qw) as matrix3  

  if skl_Hierachy_array[cor_i][1] > 0 do ( -----parent index>0,,parent exit!
  
    in coordsys parent xtmp = skl_Translation_array[cor_i][1] + location_array[(skl_Hierachy_array[cor_i][1])][1]
    in coordsys parent ytmp = skl_Translation_array[cor_i][2] + location_array[(skl_Hierachy_array[cor_i][1])][2]
	in coordsys parent ztmp = skl_Translation_array[cor_i][3] + location_array[(skl_Hierachy_array[cor_i][1])][3]

    append location_array[xtmp,ytmp,ztmp]
	
	in coordsys parent pa_qx = rotation_array[(skl_Hierachy_array[cor_i][1])][1]
	in coordsys parent pa_qy = rotation_array[(skl_Hierachy_array[cor_i][1])][2]
	in coordsys parent pa_qz = rotation_array[(skl_Hierachy_array[cor_i][1])][3]	
	in coordsys parent pa_qw = rotation_array[(skl_Hierachy_array[cor_i][1])][4]
    pa_tfm = (quat pa_qx pa_qy pa_qz pa_qw) as matrix3
    rotation_tfm = (skl_tfm * pa_tfm) as quat
	xro = rotation_tfm.x
	yro = rotation_tfm.y
	zro = rotation_tfm.z
	wro = rotation_tfm.w
	append rotation_array[xro,yro,zro,wro]	
    
  )----end ofif skl_Hierachy_array[cor_i][1] > 0 
  
  if skl_Hierachy_array[cor_i][1] == 0 do ( -----Parent bone index =0.means no parent bone!
  
   xtmp = skl_Translation_array[cor_i][1]
   ytmp = skl_Translation_array[cor_i][2]
   ztmp = skl_Translation_array[cor_i][3]  
   
   append location_array[xtmp,ytmp,ztmp]
   append rotation_array[qx,qy,qz,qw]
  
  )---- end of if skl_Hierachy_array[cor_i][1] == 0


)----end of for cor_i = 1 to skl_bone_count 


print " location array count check"
print location_array.count  

BNArr = #()

for bonebuild_i = 1 to skl_bone_count do(
  qx = rotation_array[bonebuild_i][1]
  qy = rotation_array[bonebuild_i][2]
  qz = rotation_array[bonebuild_i][3]
  qw = rotation_array[bonebuild_i][4]
  skl_tfm = (quat qx qy qz qw) as matrix3  --     define transform matrix
    
  skl_tfm.row4 = location_array[bonebuild_i]  
  
  
  newBone = bonesys.createbone \
                skl_tfm.row4 \
				(skl_tfm.row4 + 0.05* (normalize skl_tfm.row1))\ 
				(normalize skl_tfm.row3)
	
    			
    newBone.name = skl_String_tb[(skl_Boneindex_array[bonebuild_i][1])]
    newBone.width = 0.01
    newBone.height = 0.01
    newBone.transform = skl_tfm	
	 --newBone.scale = scm  --         don't work here,how to apply scale matrix?
    newBone.setBoneEnable false 0
    newBone.wirecolor = yellow
    newbone.showlinks = true	
    newBone.pos.controller      = TCB_position ()
    newBone.rotation.controller = TCB_rotation ()
	
    append BNArr newBone

  
)----for bonebuild_i = 1 to skl_bone_count

with undo off with redraw off for a = 1 to skl_bone_count Do (
select BNArr[a]
if skl_Hierachy_array[a][1] != 0 then
$.parent = BNArr[(skl_Hierachy_array[a][1])]
)


```


Anyidea how to add translate value acoording to parent's coordinate and fix this?
## Post #10
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-04-12T16:00:45+00:00
- Post Title: FFIV Model viewer

The contents of this post was deleted because of possible forum rules violation.
[ff14.jpg](https://xentaxbackup.github.io/file/4209_ff14.jpg)
## Post #11
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-06-14T19:00:40+00:00
- Post Title: FFIV Model viewer

The contents of this post was deleted because of possible forum rules violation.
