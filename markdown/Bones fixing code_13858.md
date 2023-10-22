## Post #1
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2016-01-21T11:35:09+00:00
- Post Title: Bones fixing code

hello, i want to start a thread in fixing the way bones are defined by/in (most) all scripts i saw in this Forum.

first of.. the Definition of the bonestruktur is flawless but then there is a lack of how the bonelenght is defined. is the scripts to get past this Problem the bonelenght is defined by something like (Zero + 0.00001).

as it is till now is in the first Picture bonelenght = 0.00000001 





and with lenght but flawed


the Problem is beside worng orientation the actual bones are more then the bonecount. like on the chest. there is one bonepelvis but "there are 2 bones missing to "Bip01 L Thigh" and  "Bip01 R Thigh" thats why there are more bones then bonecount tells.


this isnt a big Problem after all but i want make a clean Code for that. right now i get it nearly done but still there are some flaws if there is an interest i will post the Code i use right now
## Post #2
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2016-01-21T14:03:41+00:00
- Post Title: Bones fixing code

the Code i use for Picture 2 is

for i=1 to bonecount do 

(

if bonecount != i   and (BoneParent+1) <= (BoneParent[i+1]+1)   then
(
newBone = bonesys.createbone   \
matrix1.pos  \
(matrix1[i+1].pos) \
(normalize (matrix1).row3 )
)



else  	
(
newBone = bonesys.createbone   \
matrix1.pos			\
(baa.matrix1.pos) \
(normalize (baa.matrix1).row3)
)

newBone.name = baa.boName 
newBone.width  = 1																
newBone.height = 1																
newbone.transform=baa.matrix1 
newBone.setBoneEnable false 0																
newBone.wirecolor = white																
newbone.showlinks = true																
newBone.pos.controller      = TCB_position ()																
newBone.rotation.controller = TCB_rotation ()	

if (BoneParent != -1) then	newBone.parent = BNArr[(BoneParent+1)] 

append BNArr newBone 

)
