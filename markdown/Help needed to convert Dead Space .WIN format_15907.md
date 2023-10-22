## Post #1
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-02-21T14:12:41+00:00
- Post Title: Help needed to convert Dead Space .WIN format

I'm in need of a tool or a script that can convert the Dead Space animation .WIN format into readable file formats, such as .BNK and Havoc .HKX

A friend of mine has a tool that can open the animations, but because they are hidden behind the .WIN format, they are currently not accessible.

Here are two examples from the first Dead Space game:
[https://www.dropbox.com/s/vp1wkb3atasm6 ... s.rar?dl=0](https://www.dropbox.com/s/vp1wkb3atasm6wl/dead%20space%20brute%20anims.rar?dl=0)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-22T15:40:16+00:00
- Post Title: Help needed to convert Dead Space .WIN format

> Reply from MaZTeR
>
> as far as I know, it doesn't really matter how the model is posed as the animations will readjust the bones anyways.

Animations are complex things to convert. It usually requires exact knowledge on everything about the model, including correct bone ids, which in many cases can only be found in original model file, not converted. The original default pose is also usually required. The fact that you have to "fix" some rigs is a bad sign. Most probably it means that the format is not correctly researched.

Locomotive is a term for walking or running. I checked some files and from the first look it seems they are not too heavily compressed, which means they will be not too hard to research. 

What do you want to do with these animations?
## Post #3
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-02-22T20:14:43+00:00
- Post Title: Help needed to convert Dead Space .WIN format

> Reply from daemon1
>
> MaZTeR wrote:as far as I know, it doesn't really matter how the model is posed as the animations will readjust the bones anyways.

Animations are complex things to convert. It usually requires exact knowledge on everything about the model, including correct bone ids, which in many cases can only be found in original model file, not converted. The original default pose is also usually required. The fact that you have to "fix" some rigs is a bad sign. Most probably it means that the format is not correctly researched.

Locomotive is a term for walking or running. I checked some files and from the first look it seems they are not too heavily compressed, which means they will be not too hard to research. 

What do you want to do with these animations?Thanks for responding, I was afraid this was just going to be forgotten to the depths of this forum.

Yeah, the person who made the bone import script said that it is not perfectly correct as it imports the weights incorrectly, only putting red weights to each bone on 3D Max. The amount of the affected area is also sometimes either too little or too much and the area affected doesn't cover multiple bones, just one bone. It doesn't give the bones their exact names either like I mentioned but rather the name "bone" and number in the end in an order as to how many of them there are in a specific skeleton. The model script also isn't perfect either, it puts the face part of them backwards and doesn't import the UVs of LOD models properly and instead, just gives them as a random mess. It's not able to import some models either.

However, if this stuff isn't too hard to decipher, that's good news, just have to wait for someone with the right knowledge to crack this open. I heard someone say that apparently the animation files are similar to what you find from Battlefield series. Dead Space and Battlefield are from EA so it's not too big of a surprise that they share similarities with the code, Dead Space 2 and 3 use apparently a heavily modified variant of the Frostbite engine.

As for the reason I need these animations, I have uploaded mods to Left 4 Dead 2 workshop where I've used the enemy models found from the series. However, some of the models are way too different as to what the enemies in L4D2 are, so they look horribly deformed. So if I was able to get the original animations, I would be able to fix the deformities.

Here's an example model that looks broken because it doesn't have the right skeleton:
[http://steamcommunity.com/sharedfiles/f ... =813068504](http://steamcommunity.com/sharedfiles/filedetails/?id=813068504)

it's supposed to look like this:
[http://vignette2.wikia.nocookie.net/dea ... 0212005133](http://vignette2.wikia.nocookie.net/deadspace/images/1/1d/Pack-full-body.jpg/revision/latest?cb=20130212005133)

They would look cooler with their original looks from the game as well. Also my buddy was planning to make a mod to Garry's Mod where he'd port the enemies with their original models, sounds and animations to it. He has everything but these animations. He already made bunch of threads to here and to Facepunch asking about this but there hasn't been any progress.

Oh and for the T-pose, the models come in that pose by default with the script I use, it was just that model I accidentally moved out of the t-pose. I have other models that are in T-pose and use the same animations here:

[https://sketchfab.com/models/5dfe049b70 ... 2c6f315dae](https://sketchfab.com/models/5dfe049b708a4f1583d8832c6f315dae)
[https://sketchfab.com/models/41661dda6f ... 6d3f770c45](https://sketchfab.com/models/41661dda6fa546d6954a466d3f770c45)
## Post #4
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-02-27T19:47:02+00:00
- Post Title: Help needed to convert Dead Space .WIN format

Oh hey, here's also the bone script if anyone can fix it so that it displays the bone names and weights:

```
If (fname!=undefined) and ((DoesFileExist fname)==true) then (--)
g = fopen fname "rb"   --open file in read only format
clearlistener()
fscale=100
-- delete $*

fn ReadFixedString bstream fixedLen = (
   local str = ""
   for i = 1 to fixedLen do
   (
      str += bit.intAsChar (ReadByte bstream #unsigned)
   )
   str
)
fn GetName bstream Offset = (
	fseek bstream Offset #seek_set
	MeshName = readstring bstream
	return MeshName
)

BoneNameOffset=#()
BoneNameLength=#()
BoneName=#()
BoneParentID_Array=#()
BoneArrayNameOffset=#()
BoneName=#()
BoneCount=#()
BoneIDTable=#()
BoneStart=#()

FileLength = readlong g
ukw =readlong g	--always 0x1a
ukw2 = readlong g
fseek g 0xc #seek_cur

SkelCount = readlong g	-- always 1, prob count
DataOffset = readlong g
ukw4 = readlong g	-- same as ukw 3
DataOffset2 = readlong g
fseek g 0x10 #seek_cur
ukw5 = readlong g
ukw6 = readlong g	-- same as ukw 4 and 3
DataOffset3 = readlong g

fseek g DataOffset #seek_set

for x=1 to SkelCount do (
	ukw7 = readlong g
	BoneArrayNameOffset[x] = readlong g
	BoneCount[x] = readlong g
	BoneIDTable[x] = readlong g
	BoneStart[x] = readlong g
	ukwtableoffset = readlong g
	
	Print ("BoneStart @ 0x"+((bit.intAsHex(BoneStart[x]))as string))
	Print ("BoneCount @ 0x"+((bit.intAsHex(BoneCount[x]))as string))

)

for x=1 to SkelCount do (
	BoneName[x] = GetName g BoneArrayNameOffset[x]
	print BoneName[x]
)


For x=1 to SkelCount do (
	BoneParentID=#()

	fseek g BoneIDTable[x] #seek_set
	For y=1 to BoneCount[x] do (
		BoneParentID[y] = Readlong g + 1
		fseek g 0xc #seek_cur
	)
	BoneParentID_Array[x] = BoneParentID
)

For x=1 to SkelCount do (
	fseek g bonestart[x] #seek_set
	
	BoneColor = random black white

	BNArr = #()
	for y=1 to BoneCount[x] do (
		
		m11 = readfloat g; m12 = readfloat g; m13 = readfloat g; m14 = readfloat g
		m21 = readfloat g; m22 = readfloat g; m23 = readfloat g; m24 = readfloat g
		m31 = readfloat g; m32 = readfloat g; m33 = readfloat g; m34 = readfloat g
		m41 = readfloat g; m42 = readfloat g; m43 = readfloat g; m44 = readfloat g
		tfm = matrix3 [m11,m21,m31,m41] [m12,m22,m32,m42] [m13,m23,m33,m43] [m14,m24,m34,m44]	
		
		newBone = bonesys.createbone	\
		tfm.row4	\
		(tfm.row4 + 0.01 * (normalize tfm.row1)) \
		(normalize tfm.row3)
		newBone.width = 0.1
		newBone.height = 0.1
		If SkelCount == 1 then newBone.wirecolor = yellow
		Else newBone.wirecolor = BoneColor
		
		newbone.showlinks = true
		newBone.transform = inverse tfm

		
		pos = [m41,m42,m43]
		pos = pos * tfm

		newBone.pos.x += ((fscale)*pos.x)
		newBone.pos.y += (-1*(fscale)*pos.z)
		newBone.pos.z += (-1*(fscale)*pos.y)	

		newBone.setBoneEnable false 0
		newBone.pos.controller = TCB_position ()
		newBone.rotation.controller = TCB_rotation ()
		
		
		if (BoneParentID_Array[x][y] != 0) then (
		newBone.parent = BNArr[BoneParentID_Array[x][y]]
	   )
	   else (
			newbone.name = BoneName[x]
		)
		append BNArr newBone
	)
)




select $*
deselect $*

Print ("Last Read @ 0x"+((bit.intAsHex(ftell g))as string))
)

gc()
fclose g
```
## Post #5
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2017-04-25T02:03:41+00:00
- Post Title: Help needed to convert Dead Space .WIN format

Have to necro this can we get some help!
## Post #6
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-04-25T13:48:26+00:00
- Post Title: Help needed to convert Dead Space .WIN format

> Reply from Braintwistah
>
> Have to necro this can we get some help!
edited the thread to suit the current situation
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-25T15:27:02+00:00
- Post Title: Help needed to convert Dead Space .WIN format

> Reply from MaZTeR
>
> I'm in need of a tool or a script that can convert the Dead Space .WIN encryption format of the files protected by it

They are NOT encrypted. Encryption is when files are encrypted with some key and cipher. This is not present here. They are just normal animation files. So you better edit your description.
## Post #8
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-04-25T18:59:38+00:00
- Post Title: Help needed to convert Dead Space .WIN format

> Reply from daemon1
>
> MaZTeR wrote:I'm in need of a tool or a script that can convert the Dead Space .WIN encryption format of the files protected by it

They are NOT encrypted. Encryption is when files are encrypted with some key and cipher. This is not present here. They are just normal animation files. So you better edit your description.
Oh, right :D
## Post #9
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2017-04-28T19:48:52+00:00
- Post Title: Help needed to convert Dead Space .WIN format

Bump help us with this it can open so many opportunitys!
## Post #10
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2017-05-04T16:55:02+00:00
- Post Title: Help needed to convert Dead Space .WIN format

bump
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-05T15:46:25+00:00
- Post Title: Help needed to convert Dead Space .WIN format

> Reply from Braintwistah
>
> Bump help us with this it can open so many opportunitys!

what many opportunities?
## Post #12
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2017-05-12T00:14:48+00:00
- Post Title: Help needed to convert Dead Space .WIN format

> Reply from daemon1
>
> Braintwistah wrote:Bump help us with this it can open so many opportunitys!

what many opportunities?

NPCS, Mods, Shit Like That
## Post #13
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2017-06-12T13:28:41+00:00
- Post Title: Help needed to convert Dead Space .WIN format

BUMP
## Post #14
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2017-06-14T15:09:58+00:00
- Post Title: Help needed to convert Dead Space .WIN format

Bump
## Post #15
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2017-11-01T02:50:37+00:00
- Post Title: Help needed to convert Dead Space .WIN format

Posting to update you on some misinformation in the thread:
The HKX files are strictly for model collisions, and have no animation data associated with them. They use Havok versions 6 for DS1, 6.5 for DS2 and DS3.

The BNK files are the ones you should focus on. They definitely contain the animation data, and I have tried to find a way to extract/convert them for a while now, but with no results.
Wish someone with more experience could actually look into reverse engineering this.
