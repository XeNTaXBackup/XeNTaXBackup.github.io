## Post #1
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2018-02-06T01:17:12+00:00
- Post Title: question about import model 3ds max

Hi there
Can anyone update this script to import r3cb files
there's problem here (fseek f (0x107	- bonename.count)#seek_cur)
and i tried with old files from this game and the script had worked perfectly
I think i must change this offset , because the game has updated her files
but idk how i can get aright offset 
I tried to get aright offset but i can't 

```
(
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"
)

fname = GetOpenFileName caption:"Open c9 Model File" types:"c9 Model File(*.r3cb)|*.r3cb"
f = fopen fname "rb"   --open file in read only format


fn PrintOffset Var =(
        local Var = Var
        print ("This is the offset 0x" + (bit.intAsHex Var) as string)
        Var
    )

fn PrintCount Var = (
        local Var = Var
        print ("This is the Count 0x" + (bit.intAsHex Var) as string)
        Var
    )

fn Readword fstream = (
    return readshort fstream #unsigned
)

fn ReadFixedString bstream fixedLen =(
	local str = ""
	for i = 1 to fixedLen do(
		str += bit.intAsChar (ReadByte bstream #unsigned)
	)
	str
)
BNArr = #()
bonecount = readlong f
for a = 1 to bonecount do (
bonename = readstring f
fseek f (0x107	- bonename.count)#seek_cur
boneid2 = readlong f
boneparent = readlong f + 1
BoneID = (a + 1)
m11 = readfloat f; m12 = readfloat f; m13 = readfloat f; m14 = readfloat f
m21 = readfloat f; m22 = readfloat f; m23 = readfloat f; m24 = readfloat f
m31 = readfloat f; m32 = readfloat f; m33 = readfloat f; m34 = readfloat f
m41 = readfloat f; m42 = readfloat f; m43 = readfloat f; m44 = readfloat f
tfm = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]
m11 = readfloat f; m12 = readfloat f; m13 = readfloat f; m14 = readfloat f
m21 = readfloat f; m22 = readfloat f; m23 = readfloat f; m24 = readfloat f
m31 = readfloat f; m32 = readfloat f; m33 = readfloat f; m34 = readfloat f
m41 = readfloat f; m42 = readfloat f; m43 = readfloat f; m44 = readfloat f
tfm2 = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]
	newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name   = BoneName
			newBone.width  = 0.3
			newBone.height = 0.3
			newBone.transform = tfm2
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.setBoneEnable false 0
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
print bonename
print boneid2
print boneparent
 if (BoneID == 3) then
 newBone.parent = BNArr[1]
 if (boneparent != 0) then
 newBone.parent = BNArr[boneparent]
append BNArr newBone

fseek f 0x24#seek_cur
nullcount = readlong f
fseek f (0x4 * nullcount)#seek_cur					  
  

)
select $'Scene Root'
rotate $ (angleaxis 90.0 [1,0,0])
rotate $ (angleaxis 180.0[0,0,1])

fclose f

```


i have tried with this file
plz help if you can  
[ph0000.rar](https://xentaxbackup.github.io/file/13883_ph0000.rar)
## Post #2
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2018-02-07T00:14:16+00:00
- Post Title: question about import model 3ds max

Anyone can help
## Post #3
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2018-02-07T15:27:51+00:00
- Post Title: question about import model 3ds max

hey guys 
no one here can helped me 
i will pay for that   
send msg if you want help me for money
## Post #4
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2018-02-10T19:40:57+00:00
- Post Title: question about import model 3ds max

thx guys
fixed
