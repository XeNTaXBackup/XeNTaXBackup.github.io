## Post #1
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2020-06-16T09:31:18+00:00
- Post Title: Saving skeleton without mesh from UE4 game

Hey!
I have a "model" which does not have a mesh only a skeleton and I have no idea how to export it in a format which I can later open in for example Blender.

Do you guys have any idea how to do this?

Edit: I managed to serialize the uexp and uasset files of the skeleton, now every bone has it's rotation and other values

```
		"x": -0.02200039,
		"y": -0.92349243,
		"z": 0.009121282,
		"w": 0.38287663
	},
	 "translation": {
		"x": -4.518637e-17,
		"y": 2.3959422,
		"z": 4.5245463e-17
	},
	"scale_3d": {
		"x": 1,
		"y": 1,
		"z": 1
	}
```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-16T14:00:02+00:00
- Post Title: Saving skeleton without mesh from UE4 game

Assumed you've got the bones' hierarchy/parenting IDs already SMD format is a good choice, imho. But you need to do a Quaternion2Euler transform of the rotation values for such.
