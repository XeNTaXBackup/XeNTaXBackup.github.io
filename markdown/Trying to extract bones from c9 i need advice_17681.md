## Post #1
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2018-02-09T22:38:05+00:00
- Post Title: Trying to extract bones from c9 i need advice

Hi guys
Can anyone help me to update this script to import r3cb files
there's problem here (fseek f (0x107	- bonename.count)#seek_cur)
and i tried with old files from this game and the script in blew had worked perfectly
I think i must change this offset , because the game has updated her files
but idk how i can get aright offset 
I tried to get aright offset but i can't 
anyone can tell me how i can get aright offset

i had uploaded file that i used at attachment

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


sorry if my english is bad
[ph0000.rar](https://xentaxbackup.github.io/file/13893_ph0000.rar)
## Post #2
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2018-02-10T19:40:20+00:00
- Post Title: Trying to extract bones from c9 i need advice

thx guys 
fixed
