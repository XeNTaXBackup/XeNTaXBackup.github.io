## Post #1
- Username: Reign
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 23, 2012 4:22 am
- Post datetime: 2013-09-22T16:12:22+00:00
- Post Title: Need help with deciphering an .ani file for Shaiya

Can anyone open this so I can see what is in it ? This is the last file in Shaiya Online that cannot seem to me modded. If someone can crack this format to where it can me edited, I will pay a bounty.

See attached  file for an example.

[http://www.mediafire.com/download/99y6d ... 01_run.ANI](http://www.mediafire.com/download/99y6dmvbed6x4v2/vehicle_Hu_01_run.ANI)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2013-09-26T23:04:07+00:00
- Post Title: Need help with deciphering an .ani file for Shaiya

This is the structure of the file.
Not sure if I'm right with the variable names (probably not).

```
short unknown2
short frame_size
short unknown3
short number_of_bones

for (number_of_bones) {
	int parent_bone_index
	float[16] bone_coords

	int number_of_rotation_keyframes
	for (num_rot_kf) {
		int timestamp
		float x
		float y
		float z
		float w
	}
	
	int number_of_translation_keyframes
	for (num_trans_kf) {
		int timestamp
		float dx
		float dy
		float dz
	}
}
```
short = 2 bytes
int/float = 4 bytes

Here's a part of your binary file converted to ASCII (structured and commented by me):

```
	-0.00830022
	-0.07654713
	-0.99703145
	0.00000000
	
	0.00000012
	0.99706578
	-0.07654977
	0.00000000
	
	0.99996555
	-0.00063551
	-0.00827585
	0.00000000
	
	-0.00177487
	1.56958711
	0.55003738
	1.00000000

11				# number_of_rotation_keyframes
0				# timestamp
	-0.02697162	# x
	0.70951426		# y
	-0.02719652	# z
	0.70364934		# w
2
	-0.00065384
	0.70907873
	-0.00080531
	0.70512855
4
	0.02657567
	0.70760036
	0.02649958
	0.70561552
6
	0.04644115
	0.70577073
	0.04642660
	0.70539033
8
	0.04918656
	0.70521206
	0.04920049
	0.70557493
10
	0.03363225
	0.70621276
	0.03363943
	0.70639986
12
	0.01599190
	0.70692539
	0.01599192
	0.70692647
14
	-0.00464240
	0.70709109
	-0.00464241
	0.70709199
16
	-0.01835814
	0.70686787
	-0.01835817
	0.70686895
18
	-0.02724872
	0.70639420
	-0.02723443
	0.70676941
20
	-0.02697162
	0.70951426
	-0.02719652
	0.70364934

11				# number_of_translation_keyframes
0				# timestamp
	-0.00177487	# dx
	1.56958711		# dy
	0.55003738		# dz
2
	-0.00113789
	1.48876774
	0.55939209
4
	-0.00043497
	1.40392208
	0.62869132
6
	0.00029851
	1.32984197
	0.70740324
8
	0.00090771
	1.28185070
	0.77578366
10
	0.00123781
	1.29034209
	0.81408834
12
	0.00104333
	1.34448195
	0.79524261
14
	0.00042637
	1.48098016
	0.73317516
16
	-0.00024654
	1.53006101
	0.66964787
18
	-0.00104064
	1.53991687
	0.61425620
20
	-0.00177487
	1.56958711
	0.55003738
```
