## Post #1
- Username: MilesPrower
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 10, 2020 4:54 pm
- Post datetime: 2020-02-16T13:01:34+00:00
- Post Title: [Help] The unsolvable Rotation

I need to ask you guys for help, since Im kinda stuck with my research. 
I working for weeks to rip the rig and animation from prince of persia.

[Prince of Persia Format Description]
[viewtopic.php?f=10&t=5112](https://forum.xentax.com/viewtopic.php?f=10&t=5112)
look at the last post in this thread. There is just one thing left and that is the rotation.

How would you convert this into sensefull rotation?? I provided all nessacary information in the following.

The rotation has just the length of 4 Byte. And thats all it is. I tried to find out how to make a sensefull rotation out of this. I still think it is some sort of packed quarternion:

For Example:
"Bone: 0" "Key Duration: 1" "Rotation: 0x6BCA4F18"

0x6B (107°) 0.297
0xCA (-54°) -0.15
0x4F (79°) 0.219
0x18 (24°) 0.06
reading 1 Byte as signed int (0° - 255°) cause normally you wouldnt need a 360° rotation in 1 frame
after that making a quaternion and normalize it
putting it in a NoKeyFramedValue -> collect in a list -> and assigning that to the keyFramedBones -> and voilá
This is the result:
pretty crazy... I tried many different things: changing the order of the quat elements.. normalizing before and after.. mulitpling it with the matrix of the bones.. reading the bytes as unsigned and signed values etc.


This is the static Skeleton in TPose:


These are all the Bones in its none animated State

```
ANGLES STATIC:  (0.0, 180.0, 89.98020935058594)
 
BONE STATIC:  (NoeBone:237,B_Pr_Bip Spine.gao,None,228)
ANGLES STATIC:  (270.0004577636719, 269.9998474121094, 89.04303741455078)
 
BONE STATIC:  (NoeBone:240,B_Pr_Bip Spine1.gao,None,237)
ANGLES STATIC:  (270.0004577636719, 269.9998474121094, 89.04303741455078)
 
BONE STATIC:  (NoeBone:241,B_Pr_Bip Spine2.gao,None,240)
ANGLES STATIC:  (270.0004577636719, 269.9998474121094, 89.04303741455078)
 
BONE STATIC:  (NoeBone:242,B_Pr_Bip Neck.gao,None,241)
ANGLES STATIC:  (270.0004577636719, 269.9998474121094, 89.04303741455078)
 
BONE STATIC:  (NoeBone:243,B_Pr_Bip Head.gao,None,242)
ANGLES STATIC:  (90.00005340576172, 89.99993896484375, 85.00452423095703)
 
BONE STATIC:  (NoeBone:6,B_Pr_Bip L Clavicle.gao,None,242)
ANGLES STATIC:  (1.0034841299057007, 357.7472839355469, 0.0024992155376821756)
 
BONE STATIC:  (NoeBone:7,B_Pr_Bip L UpperArm.gao,None,6)
ANGLES STATIC:  (356.3590087890625, 358.186767578125, 359.7752685546875)
 
BONE STATIC:  (NoeBone:8,B_Pr_Bip L Forearm.gao,None,7)
ANGLES STATIC:  (356.5675048828125, 14.435192108154297, 358.7642822265625)
 
BONE STATIC:  (NoeBone:9,B_Pr_Bip L Hand.gao,None,8)
ANGLES STATIC:  (80.7533187866211, 12.782612800598145, 349.7972412109375)
 
BONE STATIC:  (NoeBone:10,B_Pr_Bip L Finger0.gao,None,9)
ANGLES STATIC:  (87.09036254882812, 17.88710594177246, 313.18609619140625)
 
BONE STATIC:  (NoeBone:11,B_Pr_Bip L Finger01.gao,None,10)
ANGLES STATIC:  (87.2630844116211, 18.130970001220703, 316.67919921875)
 
BONE STATIC:  (NoeBone:12,B_Pr_Bip L Finger1.gao,None,9)
ANGLES STATIC:  (59.07767868041992, 21.662830352783203, 326.5828552246094)
 
BONE STATIC:  (NoeBone:13,B_Pr_Bip L Finger11.gao,None,12)
ANGLES STATIC:  (35.02534103393555, 349.3664245605469, 301.5862121582031)
 
BONE STATIC:  (NoeBone:14,B_Pr_Bip L Finger2.gao,None,9)
ANGLES STATIC:  (73.97798156738281, 9.413742065429688, 327.21026611328125)
 
BONE STATIC:  (NoeBone:15,B_Pr_Bip L Finger21.gao,None,14)
ANGLES STATIC:  (65.56539154052734, 357.63995361328125, 304.1197509765625)
 
BONE STATIC:  (NoeBone:17,B_Pr_Bip R Clavicle.gao,None,242)
ANGLES STATIC:  (178.9965057373047, 182.2527313232422, 0.0024992155376821756)
 
BONE STATIC:  (NoeBone:18,B_Pr_Bip R UpperArm.gao,None,17)
ANGLES STATIC:  (184.106689453125, 181.6647491455078, 359.8064880371094)
 
BONE STATIC:  (NoeBone:19,B_Pr_Bip R Forearm.gao,None,18)
ANGLES STATIC:  (183.87661743164062, 164.92369079589844, 358.6300048828125)
 
BONE STATIC:  (NoeBone:20,B_Pr_Bip R Hand.gao,None,19)
ANGLES STATIC:  (99.70173645019531, 166.6472625732422, 349.67608642578125)
 
BONE STATIC:  (NoeBone:21,B_Pr_Bip R Finger0.gao,None,20)
ANGLES STATIC:  (93.54728698730469, 161.92723083496094, 313.02703857421875)
 
BONE STATIC:  (NoeBone:22,B_Pr_Bip R Finger01.gao,None,21)
ANGLES STATIC:  (93.33560180664062, 161.6291961669922, 316.5180969238281)
 
BONE STATIC:  (NoeBone:23,B_Pr_Bip R Finger1.gao,None,20)
ANGLES STATIC:  (121.43087768554688, 157.96673583984375, 326.394775390625)
 
BONE STATIC:  (NoeBone:24,B_Pr_Bip R Finger11.gao,None,23)
ANGLES STATIC:  (145.8494110107422, 190.72727966308594, 301.6556396484375)
 
BONE STATIC:  (NoeBone:25,B_Pr_Bip R Finger2.gao,None,20)
ANGLES STATIC:  (106.56268310546875, 170.2282257080078, 327.1164855957031)
 
BONE STATIC:  (NoeBone:26,B_Pr_Bip R Finger21.gao,None,25)
ANGLES STATIC:  (115.26152801513672, 182.3934326171875, 304.1222229003906)
 
BONE STATIC:  (NoeBone:229,B_Pr_Bip L Thigh.gao,None,228)
ANGLES STATIC:  (144.81271362304688, 324.45721435546875, 277.4425354003906)
 
BONE STATIC:  (NoeBone:230,B_Pr_Bip L Calf.gao,None,229)
ANGLES STATIC:  (140.03616333007812, 319.63739013671875, 277.9391174316406)
 
BONE STATIC:  (NoeBone:231,B_Pr_Bip L Foot.gao,None,230)
ANGLES STATIC:  (0.0, 171.32479858398438, 270.0)
 
BONE STATIC:  (NoeBone:232,B_Pr_Bip L Toe0.gao,None,231)
ANGLES STATIC:  (270.0021057128906, 81.32479858398438, 359.9988708496094)
 
BONE STATIC:  (NoeBone:233,B_Pr_Bip R Thigh.gao,None,228)
ANGLES STATIC:  (35.187259674072266, 215.54281616210938, 277.4425354003906)
 
BONE STATIC:  (NoeBone:234,B_Pr_Bip R Calf.gao,None,233)
ANGLES STATIC:  (39.93235397338867, 220.3308563232422, 277.9354553222656)
 
BONE STATIC:  (NoeBone:235,B_Pr_Bip R Foot.gao,None,234)
ANGLES STATIC:  (0.0, 188.67459106445312, 270.0)
 
BONE STATIC:  (NoeBone:236,B_Pr_Bip R Toe0.gao,None,235)
ANGLES STATIC:  (269.9970703125, 98.6745834350586, 0.0044993869960308075)
```

And These are the parsed Animation Frames:
There are 34 Bones with an animationlength of 24 Frames:

```
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'6bca4f18'
BONE_ID:  0  KEY_DURATION:  2  Rotation:  b'633ef6be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'539e86be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'4cbe56be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'47be46be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'439a56be'
BONE_ID:  0  KEY_DURATION:  2  Rotation:  b'415a86be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ec205bf'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3dc2ff15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3cae6f15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ca61f15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ba2ef14'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ba2df14'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ba2df14'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ba2df14'
BONE_ID:  0  KEY_DURATION:  3  Rotation:  b'3ba6ef14'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3bae3f15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3bb24f15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3bb24f15'
 
BONE:  (NoeBone:228,B_Pr_Bip Pelvis.gao,None,228)
 
BONE:  (NoeBone:237,B_Pr_Bip Spine.gao,None,228)
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'f901f8df'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'00fe27e0'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'05fe37e0'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'0afe57e0'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'14fa97e0'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'23fa17e1'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'3dfaf7e1'
BONE_ID:  1  KEY_DURATION:  2  Rotation:  b'5efa07e3'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'a3fa67e5'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'bffe57e6'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'd0fee7e6'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'd9fe37e7'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'dffe67e7'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'e3fe97e7'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'e5fea7e7'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'e6fea7e7'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'e5fe97e7'
BONE_ID:  1  KEY_DURATION:  2  Rotation:  b'e3fe87e7'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'dffe67e7'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'defe67e7'
BONE_ID:  1  KEY_DURATION:  1  Rotation:  b'ddfe57e7'
 
BONE:  (NoeBone:240,B_Pr_Bip Spine1.gao,None,237)
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'8036e8df'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'78f677e2'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'78de37e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'7cc6b7e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'86a6f7e3'
BONE_ID:  2  KEY_DURATION:  2  Rotation:  b'957e17e4'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'b636f7e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'c316e7e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'cc02d7e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'd0fad6e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'd3f2d6e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'd5eed6e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'd5ead6e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'd6ead6e3'
BONE_ID:  2  KEY_DURATION:  2  Rotation:  b'd5eed6e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'd4f2d6e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'd4f2d6e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'd5f2d6e3'
BONE_ID:  2  KEY_DURATION:  1  Rotation:  b'd7f2d6e3'
 
BONE:  (NoeBone:241,B_Pr_Bip Spine2.gao,None,240)
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'050218e0'
BONE_ID:  3  KEY_DURATION:  2  Rotation:  b'191e58e0'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'445ad8e0'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'567218e1'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'617e78e1'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'667ed8e1'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'666e48e2'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'645ec8e2'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'604a38e3'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'5a3a98e3'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'5532c8e3'
BONE_ID:  3  KEY_DURATION:  2  Rotation:  b'4f2ee8e3'
BONE_ID:  3  KEY_DURATION:  3  Rotation:  b'3e2e08e4'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'213608e4'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'183af8e3'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'113ef8e3'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'0d42e8e3'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'0a42e8e3'
BONE_ID:  3  KEY_DURATION:  1  Rotation:  b'0b42e8e3'
 
BONE:  (NoeBone:242,B_Pr_Bip Neck.gao,None,241)
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'000208e0'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'fbf9f7df'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'f2f1f7df'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'ece9e7df'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'eeedf7df'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'000208e0'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'262a28e0'
BONE_ID:  4  KEY_DURATION:  2  Rotation:  b'5e6248e0'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'd8e2b8e0'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'0813d9e0'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'2533f9e0'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'344309e1'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'3f4b09e1'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'455319e1'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'485719e1'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'495719e1'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'475719e1'
BONE_ID:  4  KEY_DURATION:  2  Rotation:  b'455319e1'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'3f4b09e1'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'3c4b09e1'
BONE_ID:  4  KEY_DURATION:  1  Rotation:  b'3b4709e1'
 
BONE:  (NoeBone:243,B_Pr_Bip Head.gao,None,242)
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'ada986ea'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'deb906e9'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'18ee66e7'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'4c2ae7e5'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'6e5e97e4'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'736a77e3'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'574287e2'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'23f266e1'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'e29926e0'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'9e49d6de'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'600dc6dd'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'31f135dd'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'0de525dd'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'e9d445dd'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'c6c485dd'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'a5b8e5dd'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'86b065de'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'6aa8f5de'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'51a885df'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'3cac15e0'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'2ab085e0'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'1db8d5e0'
BONE_ID:  5  KEY_DURATION:  1  Rotation:  b'13b805e1'
 
BONE:  (NoeBone:6,B_Pr_Bip L Clavicle.gao,None,242)
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'010628ba'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'0e6e28ba'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'1af208ba'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'2666e9b9'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'35aac9b9'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'489209ba'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'630679ba'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'801ac8ba'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'990297ba'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'aceec5b9'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'b712a5b8'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'bd92c4b7'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c66644b7'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c83ae4b6'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c71ab4b6'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c40694b6'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c3fe93b6'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c202a4b6'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c20eb4b6'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c21ed4b6'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c22af4b6'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c13204b7'
BONE_ID:  6  KEY_DURATION:  1  Rotation:  b'c13604b7'
 
BONE:  (NoeBone:6,B_Pr_Bip L Clavicle.gao,None,242)
 
BONE:  (NoeBone:7,B_Pr_Bip L UpperArm.gao,None,6)
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'9852ecd8'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'5e66dcd7'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'23567cd6'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'e8255cd5'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'afdd0bd5'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'788dcbd5'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'3f31cbd7'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'03b96ada'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'cb1caadc'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'9d70f9dd'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'7dd858de'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'6c78f8dd'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'6554a8dd'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'5f3c68dd'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'5b30f8dc'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'5a3428dc'
BONE_ID:  7  KEY_DURATION:  2  Rotation:  b'5b4828db'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'638408d9'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'69a418d8'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'6eb868d7'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'71c428d7'
BONE_ID:  7  KEY_DURATION:  1  Rotation:  b'72c0f8d6'
 
BONE:  (NoeBone:8,B_Pr_Bip L Forearm.gao,None,7)
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'7e00f8df'
BONE_ID:  8  KEY_DURATION:  2  Rotation:  b'6ffcf7df'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'55fcf7df'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'44fcf7df'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'2efcf7df'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'10fc07e0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'130008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'3d0008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'6600f89f'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'8afc07a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'a10008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'a40008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'acfc07a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'b40008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'b90008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'b90008a0'
BONE_ID:  8  KEY_DURATION:  2  Rotation:  b'b70008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'ae0008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'ac0008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'ac0008a0'
BONE_ID:  8  KEY_DURATION:  1  Rotation:  b'adfc07a0'
 
BONE:  (NoeBone:9,B_Pr_Bip L Hand.gao,None,8)
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'587585c3'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'1b41e6c5'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'db4087c9'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'a42c28cd'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'7bc878cf'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'61d0d8ce'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'5808d8ca'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'6b5c6e25'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'd58ccd2b'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'504d2c31'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'c0016b34'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'0b223a35'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'16062a35'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'34ba9934'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'5a5a1933'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'7c028930'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'94ca282d'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'a1ae8829'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'a5a20826'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'a4a60823'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'a0b2d820'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'9db6f81f'
BONE_ID:  9  KEY_DURATION:  1  Rotation:  b'9db6e81f'
 
BONE:  (NoeBone:10,B_Pr_Bip L Finger0.gao,None,9)
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'e1d298de'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'e3d298de'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'e8d2a8de'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'ebd2a8de'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'ead2a8de'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'e1d298de'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'cfce78de'
BONE_ID:  10  KEY_DURATION:  2  Rotation:  b'b5c648de'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'7ab6d8dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'61b2a8dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'52aa88dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'50aa88dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'4baa88dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'45a678dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'41a678dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'3fa668dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'40a668dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'41a678dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'43a678dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'45aa78dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'46aa78dd'
BONE_ID:  10  KEY_DURATION:  1  Rotation:  b'46aa78dd'
 
BONE:  (NoeBone:11,B_Pr_Bip L Finger01.gao,None,10)
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'ff0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'01fe07e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'0502f8df'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'0802f8df'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'070208e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'00fe07e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'eefd07e0'
BONE_ID:  11  KEY_DURATION:  2  Rotation:  b'd60108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'9f0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'890108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'7b0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'790108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'740108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'6f0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'6b0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'6a0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'6a0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'6c0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'6e0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'6f0108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'700108e0'
BONE_ID:  11  KEY_DURATION:  1  Rotation:  b'700108e0'
 
BONE:  (NoeBone:12,B_Pr_Bip L Finger1.gao,None,9)
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'4816bae8'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'710e1ae9'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'7c023ae9'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'82e669e9'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'83ae99e9'
BONE_ID:  12  KEY_DURATION:  2  Rotation:  b'8062d9e9'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'74ba38ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'6e7668ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'6b4e78ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'6a4688ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'693a88ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'682a98ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'681e98ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'671aa8ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'681a98ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'681e98ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'682298ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'692a98ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'692a98ea'
BONE_ID:  12  KEY_DURATION:  1  Rotation:  b'692e98ea'
 
BONE:  (NoeBone:13,B_Pr_Bip L Finger11.gao,None,12)
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'000208e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'5c0208e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'be0208e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'190308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'620308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'920308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'a90308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'b10308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'ae0308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'a60308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'9b0308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'920308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'900308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'8a0308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'7e0308e0'
BONE_ID:  13  KEY_DURATION:  2  Rotation:  b'6e0308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'460308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'330308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'230308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'180308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'140308e0'
BONE_ID:  13  KEY_DURATION:  1  Rotation:  b'130308e0'
 
BONE:  (NoeBone:14,B_Pr_Bip L Finger2.gao,None,9)
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'912e28e2'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'913618e2'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'914218e2'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'924e08e2'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'924a08e2'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'912e28e2'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'90f257e2'
BONE_ID:  14  KEY_DURATION:  2  Rotation:  b'8f9a97e2'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'8cd636e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'8a8676e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'8952a6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'894aa6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'893ab6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'892ac6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'881ac6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'8816d6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'8816d6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'881ec6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'8822c6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'892ac6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'892eb6e3'
BONE_ID:  14  KEY_DURATION:  1  Rotation:  b'892eb6e3'
 
BONE:  (NoeBone:15,B_Pr_Bip L Finger21.gao,None,14)
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'000208e0'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'5afef7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'b9fe07e0'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'13fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'5afff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'89fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'9ffff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'a6fff7df'
BONE_ID:  15  KEY_DURATION:  2  Rotation:  b'a3fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'90fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'89fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'88fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'85fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'7ffff7df'
BONE_ID:  15  KEY_DURATION:  3  Rotation:  b'76fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'58fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'50fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'4bfff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'48fff7df'
BONE_ID:  15  KEY_DURATION:  1  Rotation:  b'48fff7df'
 
BONE:  (NoeBone:17,B_Pr_Bip R Clavicle.gao,None,242)
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'01fa5786'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'0e926786'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'1a0ea786'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'279af686'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'3656e686'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'486ef685'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'60fa2684'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'7aeae781'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'6f61a01b'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'6101f116'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'598d0113'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'55e1a110'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'530d720f'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'522da20e'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'513d220e'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'5149e20d'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'5049e20d'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'5045020e'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'503d320e'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'5031820e'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'5029c20e'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'5021f20e'
BONE_ID:  16  KEY_DURATION:  1  Rotation:  b'501d020f'
 
BONE:  (NoeBone:17,B_Pr_Bip R Clavicle.gao,None,242)
 
BONE:  (NoeBone:18,B_Pr_Bip R UpperArm.gao,None,17)
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'f0f124d6'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'0492b4d9'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'1642e4dd'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'2506e4e1'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'31d2d3e4'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'3e92d3e5'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'6a3a23e4'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'79cee2e0'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'775ab2dc'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'6bfa31d8'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'5ab621d4'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'4f9ab1d1'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'4b8e91d0'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'488ad1cf'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'488a61cf'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'499221cf'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'4b9a21cf'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'4ea251cf'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'50aab1cf'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'52b611d0'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'54be81d0'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'55c2e1d0'
BONE_ID:  17  KEY_DURATION:  1  Rotation:  b'56c611d1'
 
BONE:  (NoeBone:19,B_Pr_Bip R Forearm.gao,None,18)
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'a20008e0'
BONE_ID:  18  KEY_DURATION:  2  Rotation:  b'6a0008e0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'010008e0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'2afcf79f'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'4ffc07a0'
BONE_ID:  18  KEY_DURATION:  2  Rotation:  b'62fcf79f'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'950008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'aa0008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'b50008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'b50008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'b40008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'b40008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'b700f89f'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'bb0008a0'
BONE_ID:  18  KEY_DURATION:  2  Rotation:  b'c10008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'cefcf79f'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'd30008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'd80008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'dd0008a0'
BONE_ID:  18  KEY_DURATION:  1  Rotation:  b'e10008a0'
 
BONE:  (NoeBone:20,B_Pr_Bip R Hand.gao,None,19)
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'dabf4623'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'b0ed78fc'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'baf938f6'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'c20579ef'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'bf1519e9'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'a839f9e3'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'4e21a9e1'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'077199df'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'cbe869dd'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'9250eada'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'61989ad8'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'42c0fad6'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'33d80ad6'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'2ee46ad5'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'2fec2ad5'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'35ec1ad5'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'3fe83ad5'
BONE_ID:  19  KEY_DURATION:  2  Rotation:  b'4ce08ad5'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'69cc5ad6'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'76c4bad6'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'7fbcfad6'
BONE_ID:  19  KEY_DURATION:  1  Rotation:  b'82bc1ad7'
 
BONE:  (NoeBone:21,B_Pr_Bip R Finger0.gao,None,20)
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'c41a2d25'
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'2b1f6d22'
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'91fb5c1f'
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'2c1b67fb'
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'1683f6f6'
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'031fa6f3'
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'faeef5f1'
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'f7e285f1'
BONE_ID:  20  KEY_DURATION:  2  Rotation:  b'f9ead5f1'
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'011756f3'
BONE_ID:  20  KEY_DURATION:  11  Rotation:  b'031fa6f3'
BONE_ID:  20  KEY_DURATION:  1  Rotation:  b'031fa6f3'
 
BONE:  (NoeBone:22,B_Pr_Bip R Finger01.gao,None,21)
BONE_ID:  21  KEY_DURATION:  1  Rotation:  b'b8fc07e0'
BONE_ID:  21  KEY_DURATION:  1  Rotation:  b'b800f8df'
 
BONE:  (NoeBone:23,B_Pr_Bip R Finger1.gao,None,20)
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'ac4bd9a0'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'ab4bd9a0'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'aa4bc9a0'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'aa4bc9a0'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'aa4bc9a0'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'ac4bd9a0'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'b047e9a0'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'b63f09a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'bd3729a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'c42f49a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'ca2b69a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'cd2779a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'cf2379a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'd02389a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'd12389a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'd12389a1'
BONE_ID:  22  KEY_DURATION:  2  Rotation:  b'd12389a1'
BONE_ID:  22  KEY_DURATION:  2  Rotation:  b'd12389a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'd02379a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'cf2379a1'
BONE_ID:  22  KEY_DURATION:  1  Rotation:  b'cf2379a1'
 
BONE:  (NoeBone:24,B_Pr_Bip R Finger11.gao,None,23)
BONE_ID:  23  KEY_DURATION:  1  Rotation:  b'62ff07a0'
BONE_ID:  23  KEY_DURATION:  1  Rotation:  b'62ff07a0'
 
BONE:  (NoeBone:25,B_Pr_Bip R Finger2.gao,None,20)
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'b702989f'
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'0aff979f'
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'60ff979f'
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'adfba79f'
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'e9f7a79f'
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'f0f7a7df'
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'ddf7a7df'
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'd7f7a7df'
BONE_ID:  24  KEY_DURATION:  2  Rotation:  b'dbf7a7df'
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'ecf7a7df'
BONE_ID:  24  KEY_DURATION:  11  Rotation:  b'f0f7a7df'
BONE_ID:  24  KEY_DURATION:  1  Rotation:  b'f0f7a7df'
 
BONE:  (NoeBone:26,B_Pr_Bip R Finger21.gao,None,25)
BONE_ID:  25  KEY_DURATION:  1  Rotation:  b'd6fff79f'
BONE_ID:  25  KEY_DURATION:  1  Rotation:  b'd6ff07a0'
 
BONE:  (NoeBone:229,B_Pr_Bip L Thigh.gao,None,228)
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'c4cd5773'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'd3c97871'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'e5c9c96e'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'f5c59a6b'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'08ca1a68'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'13c67a65'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'13c65a64'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'09c6ea64'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'f8c58a66'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'e5c55a68'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'd5c5ca69'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'ccc58a6a'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'c8c5ca6a'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'c6c5ea6a'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'c5c50a6b'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'c5c90a6b'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'c6c90a6b'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'c7c9fa6a'
BONE_ID:  26  KEY_DURATION:  2  Rotation:  b'c9c9ea6a'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'cccdba6a'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'cdcd9a6a'
BONE_ID:  26  KEY_DURATION:  1  Rotation:  b'cecd9a6a'
 
BONE:  (NoeBone:230,B_Pr_Bip L Calf.gao,None,229)
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'6b0008e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'8b0008e0'
BONE_ID:  27  KEY_DURATION:  2  Rotation:  b'b70008e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'2c0108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'6801f8df'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'8c0108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'8d0108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'760108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'5a0108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'450108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'3dfd07e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'3e0108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'410108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'440108e0'
BONE_ID:  27  KEY_DURATION:  6  Rotation:  b'490108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'6c0108e0'
BONE_ID:  27  KEY_DURATION:  1  Rotation:  b'700108e0'
 
BONE:  (NoeBone:231,B_Pr_Bip L Foot.gao,None,230)
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'70fae6dc'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'6c7e27de'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'65f2d7df'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'5842b8e1'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'524268e2'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'4336b8e2'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'392298e2'
BONE_ID:  28  KEY_DURATION:  2  Rotation:  b'3c0618e2'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'54ceb7e0'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'5cb227e0'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'5ea2d7df'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'5c9aa7df'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'599697df'
BONE_ID:  28  KEY_DURATION:  6  Rotation:  b'559297df'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'349ec7df'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'2fa2d7df'
BONE_ID:  28  KEY_DURATION:  1  Rotation:  b'2ba2d7df'
 
BONE:  (NoeBone:232,B_Pr_Bip L Toe0.gao,None,231)
BONE_ID:  29  KEY_DURATION:  1  Rotation:  b'ff03f8df'
BONE_ID:  29  KEY_DURATION:  1  Rotation:  b'ffe767e0'
BONE_ID:  29  KEY_DURATION:  1  Rotation:  b'ff1b98df'
BONE_ID:  29  KEY_DURATION:  19  Rotation:  b'ff03f8df'
BONE_ID:  29  KEY_DURATION:  1  Rotation:  b'ff03f8df'
 
BONE:  (NoeBone:233,B_Pr_Bip R Thigh.gao,None,228)
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'660e866a'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'7b12a666'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'8c0a2662'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'980e465e'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'8862565e'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'77ba065f'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'60169760'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'5212d75f'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'421a5761'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'322ac763'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'23367765'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'193a3766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'143e5766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'113e7766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'0e429766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'0d42a766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'0c42b766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'0b42b766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'0c42c766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'0c46c766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'0c46b766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'0c46b766'
BONE_ID:  30  KEY_DURATION:  1  Rotation:  b'0c46b766'
 
BONE:  (NoeBone:234,B_Pr_Bip R Calf.gao,None,233)
BONE_ID:  31  KEY_DURATION:  1  Rotation:  b'5afcf7df'
BONE_ID:  31  KEY_DURATION:  1  Rotation:  b'9cfcf7df'
BONE_ID:  31  KEY_DURATION:  1  Rotation:  b'f8fcf7df'
BONE_ID:  31  KEY_DURATION:  3  Rotation:  b'4efd07e0'
BONE_ID:  31  KEY_DURATION:  1  Rotation:  b'c90108e0'
BONE_ID:  31  KEY_DURATION:  1  Rotation:  b'f50108e0'
BONE_ID:  31  KEY_DURATION:  1  Rotation:  b'e10108e0'
BONE_ID:  31  KEY_DURATION:  1  Rotation:  b'b00108e0'
BONE_ID:  31  KEY_DURATION:  1  Rotation:  b'940108e0'
BONE_ID:  31  KEY_DURATION:  11  Rotation:  b'8c0108e0'
BONE_ID:  31  KEY_DURATION:  1  Rotation:  b'a901f8df'
 
BONE:  (NoeBone:235,B_Pr_Bip R Foot.gao,None,234)
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'fc9a79e3'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'e59a79e2'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'b39a09e2'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'598219e2'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'4f6e29e2'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'4852a9e1'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'3a2e99e0'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'261e39e0'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'300a89df'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'48eeb8de'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'54d228de'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'57c2d8dd'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'54b6b8dd'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'51aea8dd'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'4eaaa8dd'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'4ba2b8dd'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'479ec8dd'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'449ad8dd'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'4196e8dd'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'3d92f8dd'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'3a9218de'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'378e28de'
BONE_ID:  32  KEY_DURATION:  1  Rotation:  b'348a28de'
 
BONE:  (NoeBone:236,B_Pr_Bip R Toe0.gao,None,235)
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'ff03f89f'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'fddb47a2'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'eebf77a4'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'c1e787a6'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'cfbb07a5'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'e61f18a1'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'ff03f89f'
BONE_ID:  33  KEY_DURATION:  3  Rotation:  b'ff03f89f'
BONE_ID:  33  KEY_DURATION:  4  Rotation:  b'ff03f8df'
BONE_ID:  33  KEY_DURATION:  4  Rotation:  b'ff03f89f'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'ff03f8df'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'ff03f89f'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'ff03f8df'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'ff03f89f'
BONE_ID:  33  KEY_DURATION:  1  Rotation:  b'ff03f89f'
```


I would be more than happy if anybody could help.. sorry to dimy and sir kane I couldn't find any hints of the rotation algorithm with disassembling.


 prince_skeleton_and_animation.rar
These are the decompresed files of the model and its bones and 1 animation file (192.72 KiB) Downloaded 23 times
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-16T17:05:51+00:00
- Post Title: [Help] The unsolvable Rotation

There can be bunch of ways for storing animation data, so some reverse engineering / disassembling might be better than trying to make sense of the data just by looking at it. First of all storing 4 components when you have just 32 bits seems like a waste, because the 4th component can be calculated assuming the quaternion is normalized. Still I don't want to misdirect you, since I don't have much knowledge on this format.

I can just list few common(ish) examples that I have seen for storing quaternions using 32 bits. No way to tell if they are what you need, but might give you an idea.

- X11_Y11_Z10 or X10_Y10_Z10 : Use 10/11 bits for storing X, Y, Z components; calculate W.

- Smallest three  : Store the smallest 3 components, like maybe 3 x 10 bits. Calculate the largest. Use 2 bits to tell which is the largest/calculated value. 0 for X, 1 for Y etc.

- Polar encoded : Quaternion stored using polar coordinates instead of cartesian. I have seen this for 48 bits, but I think 32 bit is also possible. I wouldn't expect to see this in PoP though.

Your data might use variations of these or maybe something completely different. Still I think that you might need to work at bit-level after all.

Good luck.
## Post #3
- Username: MilesPrower
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 10, 2020 4:54 pm
- Post datetime: 2020-02-16T17:48:31+00:00
- Post Title: [Help] The unsolvable Rotation

thank you so much for your feedback! thats something I was hoping for. Nice input I will defently try them out!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-18T20:57:29+00:00
- Post Title: [Help] The unsolvable Rotation

> Reply from MilesPrower ↑Sun Feb 16, 2020 9:01 pm at Sun Feb 16, 2020 9:01 pm
>
> 
And These are the parsed Animation Frames:
There are 34 Bones with an animationlength of 24 Frames:
Code: Select allBONE:  (NoeBone:228,B_Pr_Bip Pelvis.gao,None,228)
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'6bca4f18'
BONE_ID:  0  KEY_DURATION:  2  Rotation:  b'633ef6be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'539e86be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'4cbe56be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'47be46be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'439a56be'
BONE_ID:  0  KEY_DURATION:  2  Rotation:  b'415a86be'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ec205bf'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3dc2ff15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3cae6f15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ca61f15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ba2ef14'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ba2df14'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ba2df14'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3ba2df14'
BONE_ID:  0  KEY_DURATION:  3  Rotation:  b'3ba6ef14'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3bae3f15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3bb24f15'
BONE_ID:  0  KEY_DURATION:  1  Rotation:  b'3bb24f15'
 
BONE:  (NoeBone:228,B_Pr_Bip Pelvis.gao,None,228)It's hard to follow your explanation without a script.
Dynamic_Actions_Drink.bin seems to contain anim data for 37 bones, doesn't it?

Why 24 frames? keycount is 19 for B_Pr_Bip Pelvis. It's varying for the different bones - is it different from framecount?
First key duration is 64 for me here (following  rogueclarkey's PoP anim format description, where duration preceds the trans/rot data)

```
[translation data]
keyDuration – 1 byte
translation – 3*float [x,y,z]
END IF
IF keyType == 0x10 THEN
[rotation data]
keyDuration – 1 byte
rotation – 4 bytes [no idea how this breaks down]
END IF
```
(where keyType 0x08 seems to be rotation, isn't it? translation: type 0x10)

Quat values seems to make sense for me:

```
0. duration 64, quat 0.726783 0.411758 0.044907 -0.597203
1. duration 2, quat 1.584214 -0.362016 1.504023 0.341456
2. duration 1, quat 2.225675 0.167881 2.211473 0.186626
3. duration 1, quat 1.936693 0.344744 1.901964 0.120270
4. duration 1, quat 1.718679 0.344744 1.680886 0.098151
5. duration 1, quat 1.515850 0.145773 1.504023 0.120270
6. duration 2, quat 1.442904 -0.207952 1.415592 0.186626
7. duration 1, quat 2.746567 0.366161 2.697846 0.362193
8. duration 1, quat 0.876699 0.366161 0.796573 0.000000
9. duration 1, quat 0.819153 0.255622 0.752357 -0.199068
10. duration 1, quat 0.840609 0.211406 0.752357 -0.309661
11. duration 1, quat 0.823824 0.189298 0.708141 -0.376017
12. duration 1, quat 0.834152 0.189298 0.708141 -0.398135
13. duration 1, quat 0.834152 0.189298 0.708141 -0.398135
14. duration 1, quat 0.834152 0.189298 0.708141 -0.398135
15. duration 3, quat 0.829183 0.211406 0.708141 -0.376017
16. duration 1, quat 0.798283 0.255622 0.708141 -0.265424
17. duration 1, quat 0.798621 0.277730 0.708141 -0.243305
18. duration 0, quat 0.798621 0.277730 0.708141 -0.243305
```
## Post #5
- Username: MilesPrower
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 10, 2020 4:54 pm
- Post datetime: 2020-02-19T06:22:37+00:00
- Post Title: [Help] The unsolvable Rotation

PART 1
Your message contains 89579 characters.
The maximum number of allowed characters is 60000.


> It's hard to follow your explanation without a script.
Allright Sure, the script is still work in progress but this is my status quo:

```
#	|		ANIMATION			|
#	=================================	
	
	bs = NoeBitStream(anim_data)		
	addr = 0x00001823
	bs.seek(addr, NOESEEK_ABS)
	kfbones = []

	
	#	FOR EVERY AVAILABLE BLOCK
	#	FOR TESTING REASONS JUST 1 FOR NOW
	for m in range(0,1):
		
		#	CHECK THE BLOCK TAG == 99C0FFEE
		#	OTHERWISE SKIP
		bs.seek(4,NOESEEK_REL)				
		if bs.readUInt() == int(0xEEFFC099):
			bs.seek(-8,NOESEEK_REL)
		else:
			break
		
		blockSize = bs.readUInt() 
		blockTag = bs.readBytes(4)
		blockID = bs.readUShort()	
		bs.readBytes(2)
		addr = bs.tell()
		
	#	TO PREVENT FINDING AN 0x03FA INSIDE THE HEADER	
		bs.seek(40, NOESEEK_REL)
		
	#	INCREMENT UNTIL FINDING AN 0x03FA
	#	IF THERE IS NONE THE BLOCK DOESNT CONTAIN ANIM DATA
		for i in range(0,80):
			if bs.readUShort() == 64003:
				bs.seek(-2,NOESEEK_REL)
				break
		
		#	40 IS HARDCODED FOR TESTING REASON
		#	AND LAG OF INFORMATION
		#	range(0,AVAILABLE ANIMATION COUNT)
		for n in range(0,40):
		
			#	JUMP TO START 0x03FA
			if bs.readUShort() == 64003:
				bs.seek(-2,NOESEEK_REL)
			else:
			#	JUMP TO THE END OF THE BLOCK
				bs.seek(addr + blockSize, NOESEEK_ABS)
				break
		
			start = bs.readUShort()
			BoneID = int(bs.readUShort())
			
			bs.readBytes(4)
			keyCount = bs.readUInt()
			bs.readBytes(3)
			#	0x08 0x10 (rotate, translation)
			keyType = bs.readByte()
			bs.readBytes(2)

			translationKeys = []
			rotationKeys = []
	
			for i in range(0,keyCount):
				if keyType == 16:	#0x10	TRANSLATION
				
					keyDuration = int(bs.readByte())
					x = bs.readFloat()
					y = bs.readFloat()
					z = bs.readFloat()
					
					if keyDuration == 64 or keyDuration == 0:
						keyDuration = 1

					translationKeys.append(NoeKeyFramedValue(keyDuration, NoeVec3((x,y,z))))
					
				if keyType == 8:	#0x08	ROTATION
				
					#	ASSUMING THAT THERE IS XYZ WITH 10 BITS RESPECTIVLY
					#	AND 2 BIT FOR IDENTIFING THE MISSING VALUE
				
					keyDuration = int(bs.readByte())
					v1	= float(bs.readBits(10)) - 1024 
					v2	= float(bs.readBits(10)) - 1024
					v3	= float(bs.readBits(10)) - 1024
					vx = bs.readBits(2)
				
					if keyDuration == 64 or keyDuration == 0:
						keyDuration = 1
						
				#	x² + y² + z² + w² = 1
					if vx == 0:
						y = v1
						z = v2
						w = v3
						x = 1 - v1 - v2 - v3
					if vx == 1:
						x = v1
						z = v2
						w = v3
						y = 1 - v1 - v2 - v3
					if vx == 2:
						x = v1
						y = v2
						w = v3
						z = 1 - v1 - v2 - v3
					if vx == 3:
						x = v1
						y = v2
						z = v3
						w = 1 - v1 - v2 - v3
				
					rotationKeys.append(NoeKeyFramedValue(keyDuration, NoeQuat((x, y, z, w)).normalize() ))
				
			kfbone = NoeKeyFramedBone(BoneID)
			kfbone.setTranslation(translationKeys)
			kfbone.setRotation(rotationKeys)			
			kfbones.append(kfbone)	
	
	#	CORRECTING THE BONE INDECIES
	#	BY COPY THE INFORMATION FROM BONES TO KFBONES
	for i in range(0, len(kfbones)):
		kfbones[i].boneIndex = bones[kfbones[i].boneIndex].index

		
	#	THE ROTATIONDATA WAS MAYBE STORED FROM CHILD TO PARENT	
	revkfbones = []
	revbones = []

	for i in reversed(kfbones):
		revkfbones.append(i)
		
	for i in reversed(bones):
		revbones.append(i)
	
	anims = []
	anims.append(NoeKeyFramedAnim("Drink", revbones, revkfbones, 20, 0))
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdl.setAnims(anims)
	mdlList.append(mdl)
	
	rapi.setPreviewOption("setAngOfs", "0 0 0")
	return 1
```


> Reply from akderebur
>
> - Smallest three : Store the smallest 3 components, like maybe 3 x 10 bits. Calculate the largest. Use 2 bits to tell which is the largest/calculated value. 0 for X, 1 for Y etc.

I found an article about league of legends compressing their data.. And I also tried to replicate the same method with 32 bits.. I think your suggested approach could be the right direction
[https://technology.riotgames.com/news/c ... ation-data](https://technology.riotgames.com/news/compressing-skeletal-animation-data)

I downloaded gekko broadway (an additional language def for ghidra from aldelaro5)
and a new data type defenition from cuyler36 for gamecube and wii *.DOL 

[https://github.com/aldelaro5/ghidra-gekko-broadway-lang](https://github.com/aldelaro5/ghidra-gekko-broadway-lang)
[https://github.com/Cuyler36/Ghidra-GameCube-Loader](https://github.com/Cuyler36/Ghidra-GameCube-Loader)

After decompiling I indeed found the evidence that the last 2 Bit of every quarternion is used to check the validity.
I used the variant with 3 values beeing 10 bits and 2 bits to identify the missing value to be calculated.

This is the result:
As you can see . The Posture of the Skeleton starts to make sense.. He is leaning forward.. kinda using his hands..
But still useless. there must be a slighty different approach to this.. its a drinking animation by the way.






> Reply from shakotay2
>
> Dynamic_Actions_Drink.bin seems to contain anim data for 37 bones, doesn't it?
it contains data for 34 bones ! but some bones have 2 animation tracks (rotation AND translation). For example Bone0 (Pelvis) has a translation and rotation track.


> Reply from shakotay2
>
> Why 24 frames? keycount is 19 for B_Pr_Bip Pelvis. It's varying for the different bones - is it different from framecount?
First key duration is 64 for me here (following rogueclarkey's PoP anim format description, where duration preceds the trans/rot data)

There are 19 Keys yeah! but some keys has a longer Duration like 2 or 3.. if you sum the Duration up its 23 Frames actually. rogueclarkey made some mistakes in his describtion.. this is why I posted another post in this thread.

Unfortunatly I didnt found any hint for a Framecount.. this is why I always sum up the keyduration

Yeah Right the first key Duration is 64.. which is very odd!! I interpret the first and the last key (always 64 for the first key and 0 for the last) as 1.


> (where keyType 0x08 seems to be rotation, isn't it? translation: type 0x10)
yeah 0x08 is the rotation type and 0x10 the translation
## Post #6
- Username: MilesPrower
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 10, 2020 4:54 pm
- Post datetime: 2020-02-19T06:29:07+00:00
- Post Title: [Help] The unsolvable Rotation

PART 2


> Quat values seems to make sense for me:
Yeah I normalized the quaternion afterwards thats why the values are valid.
These are the new values with the 3 x 10 bits values and 2 bits check. (rotation animation tracks only)

```
BONE_ID:  0  Q:  (-0.31895750761032104, -0.4826838970184326, 0.8155426979064941, -0.013129002414643764)
BONE_ID:  0  Q:  (-0.33308467268943787, -0.46662911772727966, 0.8191243410110474, -0.01863410696387291)
BONE_ID:  0  Q:  (-0.33842986822128296, -0.4602956473827362, 0.8204595446586609, -0.020957812666893005)
BONE_ID:  0  Q:  (-0.34055495262145996, -0.4579344391822815, 0.8208841681480408, -0.021622536703944206)
BONE_ID:  0  Q:  (-0.33962708711624146, -0.4594505727291107, 0.8204474449157715, -0.02060658670961857)
BONE_ID:  0  Q:  (-0.3359469771385193, -0.46446359157562256, 0.8191995620727539, -0.018037421628832817)
BONE_ID:  0  Q:  (-0.3269619345664978, -0.4766378402709961, 0.8159516453742981, -0.011625313200056553)
BONE_ID:  0  Q:  (0.8153189420700073, -0.32226890325546265, -0.011433043517172337, -0.48090240359306335)
BONE_ID:  0  Q:  (0.8161503672599792, -0.31911760568618774, -0.014826260507106781, -0.4815004765987396)
BONE_ID:  0  Q:  (0.8163924813270569, -0.3172909617424011, -0.016145337373018265, -0.4822542071342468)
BONE_ID:  0  Q:  (0.8165419101715088, -0.3166896104812622, -0.016778258606791496, -0.4823749363422394)
BONE_ID:  0  Q:  (0.8164995312690735, -0.31640228629112244, -0.01676303520798683, -0.4826357364654541)
BONE_ID:  0  Q:  (0.8164995312690735, -0.31640228629112244, -0.01676303520798683, -0.4826357364654541)
BONE_ID:  0  Q:  (0.8164995312690735, -0.31640228629112244, -0.01676303520798683, -0.4826357364654541)
BONE_ID:  0  Q:  (0.8163180351257324, -0.31687408685684204, -0.01608853042125702, -0.48265591263771057)
BONE_ID:  0  Q:  (0.8160772323608398, -0.31869223713874817, -0.014773812144994736, -0.4819076657295227)
BONE_ID:  0  Q:  (0.8158918023109436, -0.31917011737823486, -0.014091395772993565, -0.48192575573921204)
BONE_ID:  0  Q:  (0.8158918023109436, -0.31917011737823486, -0.014091395772993565, -0.48192575573921204)
BONE_ID:  1  Q:  (-0.2909630239009857, -0.287038654088974, -0.28759926557540894, 0.866161584854126)
BONE_ID:  1  Q:  (-0.28872188925743103, -0.289285808801651, -0.2875940799713135, 0.8661656379699707)
BONE_ID:  1  Q:  (-0.2870230972766876, -0.2904198169708252, -0.28815531730651855, 0.8661643266677856)
BONE_ID:  1  Q:  (-0.28549695014953613, -0.2917528450489044, -0.2883405387401581, 0.8661590218544006)
BONE_ID:  1  Q:  (-0.2822106182575226, -0.2948298156261444, -0.2885202169418335, 0.8661342263221741)
BONE_ID:  1  Q:  (-0.2778181731700897, -0.2993679940700531, -0.28830185532569885, 0.8660704493522644)
BONE_ID:  1  Q:  (-0.26987284421920776, -0.30757126212120056, -0.28782448172569275, 0.8658669590950012)
BONE_ID:  1  Q:  (-0.25894269347190857, -0.31841278076171875, -0.2874387502670288, 0.8654136657714844)
BONE_ID:  1  Q:  (-0.23362530767917633, -0.34407854080200195, -0.28517013788223267, 0.8635433912277222)
BONE_ID:  1  Q:  (-0.22216545045375824, -0.3550494611263275, -0.2844548225402832, 0.8623618483543396)
BONE_ID:  1  Q:  (-0.21466071903705597, -0.3622399568557739, -0.28386056423187256, 0.8614673614501953)
BONE_ID:  1  Q:  (-0.2105940282344818, -0.3662194609642029, -0.28340959548950195, 0.8609369397163391)
BONE_ID:  1  Q:  (-0.20777204632759094, -0.36881333589553833, -0.28326016664505005, 0.8605644702911377)
BONE_ID:  1  Q:  (-0.2060367912054062, -0.37086623907089233, -0.28266802430152893, 0.860293984413147)
BONE_ID:  1  Q:  (-0.2050764113664627, -0.3717462718486786, -0.282614141702652, 0.8601614832878113)
BONE_ID:  1  Q:  (-0.20450957119464874, -0.37203335762023926, -0.28283238410949707, 0.860100507736206)
BONE_ID:  1  Q:  (-0.2049066722393036, -0.371438592672348, -0.28310427069664, 0.8601735830307007)
BONE_ID:  1  Q:  (-0.20586664974689484, -0.3705599904060364, -0.2831569314002991, 0.860305905342102)
BONE_ID:  1  Q:  (-0.20777204632759094, -0.36881333589553833, -0.28326016664505005, 0.8605644702911377)
BONE_ID:  1  Q:  (-0.2083309143781662, -0.3685302138328552, -0.28304269909858704, 0.860622227191925)
BONE_ID:  1  Q:  (-0.2087174952030182, -0.36794528365135193, -0.2833106815814972, 0.860690712928772)
BONE_ID:  2  Q:  (-0.23746010661125183, -0.3085744380950928, -0.3178502321243286, 0.8645031452178955)
BONE_ID:  2  Q:  (-0.24549056589603424, -0.3225195109844208, -0.2962169349193573, 0.8648532629013062)
BONE_ID:  2  Q:  (-0.24653351306915283, -0.3276631534099579, -0.2899284362792969, 0.8647540211677551)
BONE_ID:  2  Q:  (-0.24501849710941315, -0.33279573917388916, -0.28606539964675903, 0.8645111322402954)
BONE_ID:  2  Q:  (-0.23962096869945526, -0.33914607763290405, -0.28462913632392883, 0.864030122756958)
BONE_ID:  2  Q:  (-0.23109588027000427, -0.3469621539115906, -0.28457263112068176, 0.8632672429084778)
BONE_ID:  2  Q:  (-0.21164637804031372, -0.3610815405845642, -0.28796735405921936, 0.8613366484642029)
BONE_ID:  2  Q:  (-0.203693225979805, -0.3669048249721527, -0.28915441036224365, 0.8603950142860413)
BONE_ID:  2  Q:  (-0.19819733500480652, -0.37065476179122925, -0.2902175188064575, 0.8597131371498108)
BONE_ID:  2  Q:  (-0.19584569334983826, -0.37236449122428894, -0.29054737091064453, 0.8594018220901489)
BONE_ID:  2  Q:  (-0.1940002143383026, -0.3738210201263428, -0.2906780540943146, 0.8591437935829163)
BONE_ID:  2  Q:  (-0.1928194910287857, -0.374675989151001, -0.2908414304256439, 0.8589817881584167)
BONE_ID:  2  Q:  (-0.1926662027835846, -0.3750225305557251, -0.2906102240085602, 0.8589433431625366)
BONE_ID:  2  Q:  (-0.1921520084142685, -0.37527671456336975, -0.29080721735954285, 0.8588807582855225)
BONE_ID:  2  Q:  (-0.1928194910287857, -0.374675989151001, -0.2908414304256439, 0.8589817881584167)
BONE_ID:  2  Q:  (-0.1934870034456253, -0.3740748465061188, -0.29087546467781067, 0.8590822815895081)
BONE_ID:  2  Q:  (-0.1934870034456253, -0.3740748465061188, -0.29087546467781067, 0.8590822815895081)
BONE_ID:  2  Q:  (-0.19297300279140472, -0.3743289113044739, -0.2910729944705963, 0.8590202927589417)
BONE_ID:  2  Q:  (-0.19194269180297852, -0.37483757734298706, -0.2914685308933258, 0.8588950634002686)
BONE_ID:  3  Q:  (-0.28683578968048096, -0.28966453671455383, -0.2890987992286682, 0.8661648631095886)
BONE_ID:  3  Q:  (-0.28120505809783936, -0.29159867763519287, -0.29275351762771606, 0.8661347031593323)
BONE_ID:  3  Q:  (-0.26810339093208313, -0.2958798408508301, -0.3013143837451935, 0.8659014701843262)
BONE_ID:  3  Q:  (-0.26230448484420776, -0.298017293214798, -0.3047904074192047, 0.865727961063385)
BONE_ID:  3  Q:  (-0.25918760895729065, -0.3004078269004822, -0.3054042160511017, 0.865624189376831)
BONE_ID:  3  Q:  (-0.2581029534339905, -0.3027988374233246, -0.30405786633491516, 0.8655892014503479)
BONE_ID:  3  Q:  (-0.25867199897766113, -0.3059900403022766, -0.3003118634223938, 0.865604817867279)
BONE_ID:  3  Q:  (-0.2603224813938141, -0.3089749813079834, -0.2957061231136322, 0.8656354546546936)
BONE_ID:  3  Q:  (-0.2624724805355072, -0.31168606877326965, -0.2908649444580078, 0.8656544089317322)
BONE_ID:  3  Q:  (-0.2654934227466583, -0.31330740451812744, -0.28625476360321045, 0.8656846880912781)
BONE_ID:  3  Q:  (-0.26786914467811584, -0.31366410851478577, -0.283552348613739, 0.8657129406929016)
BONE_ID:  3  Q:  (-0.2706665098667145, -0.3131730258464813, -0.281293123960495, 0.8657577633857727)
BONE_ID:  3  Q:  (-0.2783188819885254, -0.3098616898059845, -0.2770819067955017, 0.8658810257911682)
BONE_ID:  3  Q:  (-0.2906782925128937, -0.30281516909599304, -0.271866112947464, 0.8659664392471313)
BONE_ID:  3  Q:  (-0.29428336024284363, -0.3003137707710266, -0.2707648277282715, 0.8659650087356567)
BONE_ID:  3  Q:  (-0.29725581407546997, -0.2984568476676941, -0.2696320414543152, 0.8659452199935913)
BONE_ID:  3  Q:  (-0.2988274097442627, -0.29703086614608765, -0.26948362588882446, 0.8659407496452332)
BONE_ID:  3  Q:  (-0.29999589920043945, -0.29641029238700867, -0.2689206302165985, 0.8659244179725647)
BONE_ID:  3  Q:  (-0.2996070086956024, -0.29661694169044495, -0.2691080868244171, 0.8659300804138184)
BONE_ID:  4  Q:  (-0.2885342538356781, -0.2885342538356781, -0.2885342538356781, 0.8661662936210632)
BONE_ID:  4  Q:  (-0.2898426949977875, -0.2881608307361603, -0.28760018944740295, 0.8661643266677856)
BONE_ID:  4  Q:  (-0.2927994728088379, -0.2872329652309418, -0.28556299209594727, 0.8661521077156067)
BONE_ID:  4  Q:  (-0.29443225264549255, -0.2866840362548828, -0.28447026014328003, 0.8661400079727173)
BONE_ID:  4  Q:  (-0.2940780222415924, -0.2868647873401642, -0.28464531898498535, 0.866142988204956)
BONE_ID:  4  Q:  (-0.2885342538356781, -0.2885342538356781, -0.2885342538356781, 0.8661662936210632)
BONE_ID:  4  Q:  (-0.2760694622993469, -0.29237738251686096, -0.2970367670059204, 0.866066038608551)
BONE_ID:  4  Q:  (-0.255660742521286, -0.2984747588634491, -0.31070733070373535, 0.8654544353485107)
BONE_ID:  4  Q:  (-0.20333828032016754, -0.313250869512558, -0.34416377544403076, 0.8614398837089539)
BONE_ID:  4  Q:  (-0.17858348786830902, -0.319722056388855, -0.3593272566795349, 0.8583528995513916)
BONE_ID:  4  Q:  (-0.16258054971694946, -0.32367634773254395, -0.3689613342285156, 0.8559606075286865)
BONE_ID:  4  Q:  (-0.1538606435060501, -0.32582253217697144, -0.37409254908561707, 0.8545299172401428)
BONE_ID:  4  Q:  (-0.14705151319503784, -0.3276277184486389, -0.37791478633880615, 0.8533559441566467)
BONE_ID:  4  Q:  (-0.1435280740261078, -0.3285027742385864, -0.37992727756500244, 0.852725625038147)
BONE_ID:  4  Q:  (-0.1416785717010498, -0.328786700963974, -0.3811461627483368, 0.8523814082145691)
BONE_ID:  4  Q:  (-0.14101646840572357, -0.32903844118118286, -0.3814380168914795, 0.8522635102272034)
BONE_ID:  4  Q:  (-0.1423395723104477, -0.3285351097583771, -0.3808545172214508, 0.8524985909461975)
BONE_ID:  4  Q:  (-0.1435280740261078, -0.3285027742385864, -0.37992727756500244, 0.852725625038147)
BONE_ID:  4  Q:  (-0.14705151319503784, -0.3276277184486389, -0.37791478633880615, 0.8533559441566467)
BONE_ID:  4  Q:  (-0.14899618923664093, -0.3268794119358063, -0.37705159187316895, 0.8536873459815979)
BONE_ID:  4  Q:  (-0.14950819313526154, -0.3270965814590454, -0.37642669677734375, 0.8537904024124146)
BONE_ID:  5  Q:  (-0.3328539729118347, -0.334532231092453, -0.1924399435520172, 0.8603855967521667)
BONE_ID:  5  Q:  (-0.31195124983787537, -0.3393755257129669, -0.21025285124778748, 0.8621509671211243)
BONE_ID:  5  Q:  (-0.28784486651420593, -0.3427005410194397, -0.2323993444442749, 0.8635346293449402)
BONE_ID:  5  Q:  (-0.2651243507862091, -0.34417518973350525, -0.25417885184288025, 0.8640865087509155)
BONE_ID:  5  Q:  (-0.24901506304740906, -0.3425505757331848, -0.2719343602657318, 0.8641194105148315)
BONE_ID:  5  Q:  (-0.24419867992401123, -0.33831050992012024, -0.28110527992248535, 0.8642296195030212)
BONE_ID:  5  Q:  (-0.25206807255744934, -0.33213678002357483, -0.2799438536167145, 0.8647418022155762)
BONE_ID:  5  Q:  (-0.26663723587989807, -0.3242129683494568, -0.27390408515930176, 0.8653132915496826)
BONE_ID:  5  Q:  (-0.28349027037620544, -0.31487295031547546, -0.26675283908843994, 0.8656391501426697)
BONE_ID:  5  Q:  (-0.29934197664260864, -0.30523067712783813, -0.2605747580528259, 0.8656381368637085)
BONE_ID:  5  Q:  (-0.31298768520355225, -0.2966862618923187, -0.2552340030670166, 0.8653737306594849)
BONE_ID:  5  Q:  (-0.32374951243400574, -0.28997868299484253, -0.2508045434951782, 0.8649830222129822)
BONE_ID:  5  Q:  (-0.33283761143684387, -0.28522640466690063, -0.24599123001098633, 0.864496111869812)
BONE_ID:  5  Q:  (-0.34183159470558167, -0.2813304364681244, -0.24027606844902039, 0.8638702630996704)
BONE_ID:  5  Q:  (-0.3505176603794098, -0.2779528796672821, -0.23424425721168518, 0.8631391525268555)
BONE_ID:  5  Q:  (-0.3588819205760956, -0.27490606904029846, -0.2281135469675064, 0.8623193502426147)
BONE_ID:  5  Q:  (-0.3669965863227844, -0.2721547484397888, -0.22184737026691437, 0.8614110350608826)
BONE_ID:  5  Q:  (-0.37436941266059875, -0.2699701189994812, -0.2157313972711563, 0.8604787588119507)
BONE_ID:  5  Q:  (-0.3812546730041504, -0.2676464319229126, -0.21023587882518768, 0.8595412969589233)
BONE_ID:  5  Q:  (-0.38733580708503723, -0.26559022068977356, -0.20532013475894928, 0.8586480021476746)
BONE_ID:  5  Q:  (-0.3923749625682831, -0.2637143135070801, -0.2013818472623825, 0.8578706979751587)
BONE_ID:  5  Q:  (-0.39618492126464844, -0.2619996666908264, -0.19868971407413483, 0.8572725057601929)
BONE_ID:  5  Q:  (-0.3986775577068329, -0.26102471351623535, -0.19676026701927185, 0.8568592071533203)
BONE_ID:  6  Q:  (-0.38314342498779297, -0.38314342498779297, 0.8375170230865479, -0.07048039883375168)
BONE_ID:  6  Q:  (-0.38720598816871643, -0.3770982027053833, 0.838168740272522, -0.07308707386255264)
BONE_ID:  6  Q:  (-0.39407607913017273, -0.366506963968277, 0.8392360806465149, -0.07784219086170197)
BONE_ID:  6  Q:  (-0.39985764026641846, -0.3568349778652191, 0.8402071595191956, -0.08267098665237427)
BONE_ID:  6  Q:  (-0.39970919489860535, -0.3535554111003876, 0.8412180542945862, -0.08708260953426361)
BONE_ID:  6  Q:  (-0.3899518549442291, -0.3651367425918579, 0.8410552740097046, -0.08508040755987167)
BONE_ID:  6  Q:  (-0.36493000388145447, -0.39497268199920654, 0.8394274115562439, -0.07864109426736832)
BONE_ID:  6  Q:  (-0.32913535833358765, -0.4337044060230255, 0.8356952667236328, -0.07199835777282715)
BONE_ID:  6  Q:  (-0.2916911542415619, -0.46800586581230164, 0.8311979174613953, -0.0706883892416954)
BONE_ID:  6  Q:  (-0.25917065143585205, -0.4916619658470154, 0.8278215527534485, -0.07622666656970978)
BONE_ID:  6  Q:  (-0.23681513965129852, -0.5038620233535767, 0.8263337016105652, -0.08493673801422119)
BONE_ID:  6  Q:  (-0.22455905377864838, -0.5089078545570374, 0.8259323835372925, -0.09177026152610779)
BONE_ID:  6  Q:  (-0.21640002727508545, -0.5120548605918884, 0.8256281614303589, -0.09648408740758896)
BONE_ID:  6  Q:  (-0.21236065030097961, -0.5132049322128296, 0.8256201148033142, -0.09937389940023422)
BONE_ID:  6  Q:  (-0.21095557510852814, -0.5135723352432251, 0.8256248235702515, -0.1004229411482811)
BONE_ID:  6  Q:  (-0.21131707727909088, -0.5129120349884033, 0.8258752822875977, -0.10097746551036835)
BONE_ID:  6  Q:  (-0.21146048605442047, -0.5129750967025757, 0.8258299231529236, -0.10072723031044006)
BONE_ID:  6  Q:  (-0.2123013436794281, -0.5127277374267578, 0.8258388638496399, -0.10014214366674423)
BONE_ID:  6  Q:  (-0.213004007935524, -0.5124152898788452, 0.8258928656578064, -0.09980376064777374)
BONE_ID:  6  Q:  (-0.2140367180109024, -0.5122073292732239, 0.8258586525917053, -0.09894149750471115)
BONE_ID:  6  Q:  (-0.21488462388515472, -0.5122092366218567, 0.8257516026496887, -0.09798198193311691)
BONE_ID:  6  Q:  (-0.21593359112739563, -0.5117422938346863, 0.8258275389671326, -0.09747472405433655)
BONE_ID:  6  Q:  (-0.21612927317619324, -0.5115285515785217, 0.8258983492851257, -0.09756305813789368)
BONE_ID:  7  Q:  (-0.2500421404838562, -0.16391651332378387, -0.4347954988479614, 0.8494487404823303)
BONE_ID:  7  Q:  (-0.2748226523399353, -0.15187567472457886, -0.4227534830570221, 0.8501092791557312)
BONE_ID:  7  Q:  (-0.2944745719432831, -0.14507657289505005, -0.4105358421802521, 0.8507043719291687)
BONE_ID:  7  Q:  (-0.31118208169937134, -0.1433991938829422, -0.39652490615844727, 0.8516867160797119)
BONE_ID:  7  Q:  (-0.3270096480846405, -0.146134153008461, -0.37939736247062683, 0.853092610836029)
BONE_ID:  7  Q:  (-0.3439127802848816, -0.1512579321861267, -0.35877320170402527, 0.854474663734436)
BONE_ID:  7  Q:  (-0.36378946900367737, -0.1589321345090866, -0.3323126435279846, 0.855550229549408)
BONE_ID:  7  Q:  (-0.3838309049606323, -0.16958802938461304, -0.3020473122596741, 0.8559679985046387)
BONE_ID:  7  Q:  (-0.39816147089004517, -0.182834193110466, -0.2744937837123871, 0.8559743762016296)
BONE_ID:  7  Q:  (-0.4049014151096344, -0.19614601135253906, -0.25452280044555664, 0.8560372591018677)
BONE_ID:  7  Q:  (-0.4058331251144409, -0.2067536860704422, -0.2433193027973175, 0.8563575148582458)
BONE_ID:  7  Q:  (-0.4037342071533203, -0.21244528889656067, -0.2402130365371704, 0.856833279132843)
BONE_ID:  7  Q:  (-0.4025720953941345, -0.21415264904499054, -0.2398858666419983, 0.8570467829704285)
BONE_ID:  7  Q:  (-0.4019676744937897, -0.2150462120771408, -0.23970946669578552, 0.8571560382843018)
BONE_ID:  7  Q:  (-0.4009341299533844, -0.2148628681898117, -0.24107614159584045, 0.8573028445243835)
BONE_ID:  7  Q:  (-0.39887961745262146, -0.2131059169769287, -0.24513587355613708, 0.8575484752655029)
BONE_ID:  7  Q:  (-0.3965745270252228, -0.2099762260913849, -0.2507813274860382, 0.8577571511268616)
BONE_ID:  7  Q:  (-0.39118844270706177, -0.20257218182086945, -0.26389360427856445, 0.8580771088600159)
BONE_ID:  7  Q:  (-0.38850027322769165, -0.199111670255661, -0.2701323926448822, 0.8581670522689819)
BONE_ID:  7  Q:  (-0.3862350583076477, -0.1969207227230072, -0.27467483282089233, 0.8582531809806824)
BONE_ID:  7  Q:  (-0.38535168766975403, -0.19584833085536957, -0.2766410708427429, 0.8582640886306763)
BONE_ID:  7  Q:  (-0.38440555334091187, -0.19600458443164825, -0.2775323688983917, 0.8583649396896362)
BONE_ID:  8  Q:  (-0.40025946497917175, -0.22821030020713806, -0.22865602374076843, 0.857571542263031)
BONE_ID:  8  Q:  (-0.403354674577713, -0.22663849592208862, -0.22663849592208862, 0.8570734858512878)
BONE_ID:  8  Q:  (-0.4089101254940033, -0.22339817881584167, -0.22339817881584167, 0.856141984462738)
BONE_ID:  8  Q:  (-0.4124460518360138, -0.22132304310798645, -0.22132304310798645, 0.8555235862731934)
BONE_ID:  8  Q:  (-0.4169127345085144, -0.21868735551834106, -0.21868735551834106, 0.8547137379646301)
BONE_ID:  8  Q:  (-0.4230020344257355, -0.21527782082557678, -0.21485817432403564, 0.8535576462745667)
BONE_ID:  8  Q:  (-0.4226117730140686, -0.21530072391033173, 0.8536337018013, -0.21530072391033173)
BONE_ID:  8  Q:  (-0.41426345705986023, -0.22025221586227417, 0.855198085308075, -0.22025221586227417)
BONE_ID:  8  Q:  (-0.4054911732673645, -0.225175142288208, 0.856721043586731, -0.22561493515968323)
BONE_ID:  8  Q:  (-0.3975832164287567, -0.23020336031913757, 0.8579899072647095, -0.22975462675094604)
BONE_ID:  8  Q:  (-0.3925323188304901, -0.23288127779960632, 0.8587496876716614, -0.23288127779960632)
BONE_ID:  8  Q:  (-0.39183664321899414, -0.23327948153018951, 0.8588511943817139, -0.23327948153018951)
BONE_ID:  8  Q:  (-0.3897731900215149, -0.23468737304210663, 0.8591479063034058, -0.2342298924922943)
BONE_ID:  8  Q:  (-0.3880804479122162, -0.23542320728302002, 0.859386682510376, -0.23542320728302002)
BONE_ID:  8  Q:  (-0.3868905305862427, -0.23610006272792816, 0.8595517873764038, -0.23610006272792816)
BONE_ID:  8  Q:  (-0.3868905305862427, -0.23610006272792816, 0.8595517873764038, -0.23610006272792816)
BONE_ID:  8  Q:  (-0.3873673975467682, -0.23582890629768372, 0.8594858050346375, -0.23582890629768372)
BONE_ID:  8  Q:  (-0.38949814438819885, -0.23461535573005676, 0.8591870665550232, -0.23461535573005676)
BONE_ID:  8  Q:  (-0.38996824622154236, -0.2343471199274063, 0.8591201901435852, -0.2343471199274063)
BONE_ID:  8  Q:  (-0.38996824622154236, -0.2343471199274063, 0.8591201901435852, -0.2343471199274063)
BONE_ID:  8  Q:  (-0.3895382285118103, -0.23482152819633484, 0.85918128490448, -0.23436377942562103)
BONE_ID:  9  Q:  (-0.25244081020355225, -0.2505846321582794, -0.35935690999031067, 0.8627535700798035)
BONE_ID:  9  Q:  (-0.2785837948322296, -0.2345968782901764, -0.34963956475257874, 0.8631961941719055)
BONE_ID:  9  Q:  (-0.3102896511554718, -0.21585367619991302, -0.3361150026321411, 0.8626437783241272)
BONE_ID:  9  Q:  (-0.3402593731880188, -0.1982208639383316, -0.3220594525337219, 0.8609353303909302)
BONE_ID:  9  Q:  (-0.36147576570510864, -0.18535161018371582, -0.31172773241996765, 0.8589562773704529)
BONE_ID:  9  Q:  (-0.3658314049243927, -0.18153446912765503, -0.3105818033218384, 0.8583422899246216)
BONE_ID:  9  Q:  (-0.3502597510814667, -0.19084665179252625, -0.31845197081565857, 0.8599326014518738)
BONE_ID:  9  Q:  (0.818632185459137, -0.5180715918540955, -0.059321172535419464, -0.2406744807958603)
BONE_ID:  9  Q:  (0.8245216012001038, -0.5171593427658081, -0.10011592507362366, -0.20660865306854248)
BONE_ID:  9  Q:  (0.8354765772819519, -0.4938212037086487, -0.17010992765426636, -0.1708276867866516)
BONE_ID:  9  Q:  (0.8452529907226562, -0.44955283403396606, -0.24975158274173737, -0.14516811072826385)
BONE_ID:  9  Q:  (0.8505432605743408, -0.40544450283050537, -0.3042857050895691, -0.14000380039215088)
BONE_ID:  9  Q:  (0.8513381481170654, -0.39804932475090027, -0.3111283481121063, -0.14134812355041504)
BONE_ID:  9  Q:  (0.8538252711296082, -0.37548720836639404, -0.3281431794166565, -0.14937859773635864)
BONE_ID:  9  Q:  (0.8572216629981995, -0.3425639569759369, -0.34581100940704346, -0.16803492605686188)
BONE_ID:  9  Q:  (0.8604671955108643, -0.30770623683929443, -0.35528966784477234, -0.19667822122573853)
BONE_ID:  9  Q:  (0.8629175424575806, -0.2782125771045685, -0.3531159460544586, -0.23082472383975983)
BONE_ID:  9  Q:  (0.8642052412033081, -0.2568467855453491, -0.3431941270828247, -0.2634325921535492)
BONE_ID:  9  Q:  (0.8645375967025757, -0.2427140325307846, -0.33014702796936035, -0.2909770607948303)
BONE_ID:  9  Q:  (0.86431884765625, -0.2342546433210373, -0.3170515298843384, -0.31233951449394226)
BONE_ID:  9  Q:  (0.8639585375785828, -0.23038895428180695, -0.30631259083747864, -0.3266025185585022)
BONE_ID:  9  Q:  (0.863792896270752, -0.22952580451965332, -0.30193957686424255, -0.33168095350265503)
BONE_ID:  9  Q:  (0.8637716770172119, -0.22934851050376892, -0.30170634388923645, -0.33207079768180847)
BONE_ID:  10  Q:  (-0.19234977662563324, -0.3082958161830902, -0.3585614562034607, 0.8598772287368774)
BONE_ID:  10  Q:  (-0.19127900898456573, -0.3087310194969177, -0.3590676188468933, 0.8597487807273865)
BONE_ID:  10  Q:  (-0.18874245882034302, -0.31007689237594604, -0.35995882749557495, 0.8594523072242737)
BONE_ID:  10  Q:  (-0.18711650371551514, -0.31073498725891113, -0.36072278022766113, 0.8592497706413269)
BONE_ID:  10  Q:  (-0.18765932321548462, -0.310515433549881, -0.36046791076660156, 0.8593177199363708)
BONE_ID:  10  Q:  (-0.19234977662563324, -0.3082958161830902, -0.3585614562034607, 0.8598772287368774)
BONE_ID:  10  Q:  (-0.2013593316078186, -0.3043496906757355, -0.3545244634151459, 0.8608936667442322)
BONE_ID:  10  Q:  (-0.21375957131385803, -0.29900509119033813, -0.3487316370010376, 0.8621420860290527)
BONE_ID:  10  Q:  (-0.23987293243408203, -0.2872324585914612, -0.3364371657371521, 0.8641576170921326)
BONE_ID:  10  Q:  (-0.2502496540546417, -0.28220924735069275, -0.33165618777275085, 0.8647180795669556)
BONE_ID:  10  Q:  (-0.25598353147506714, -0.27979594469070435, -0.3286114037036896, 0.8649861812591553)
BONE_ID:  10  Q:  (-0.25683122873306274, -0.2794228792190552, -0.3281732499599457, 0.8650218844413757)
BONE_ID:  10  Q:  (-0.2589394748210907, -0.2784932553768158, -0.32708144187927246, 0.8651067018508911)
BONE_ID:  10  Q:  (-0.2610890865325928, -0.277591347694397, -0.32591933012008667, 0.8651891350746155)
BONE_ID:  10  Q:  (-0.2627483606338501, -0.2768556475639343, -0.3250555992126465, 0.8652474284172058)
BONE_ID:  10  Q:  (-0.26339033246040344, -0.27629587054252625, -0.32498493790626526, 0.865257740020752)
BONE_ID:  10  Q:  (-0.2629777789115906, -0.2764788866043091, -0.32520022988319397, 0.8652439117431641)
BONE_ID:  10  Q:  (-0.2627483606338501, -0.2768556475639343, -0.3250555992126465, 0.8652474284172058)
BONE_ID:  10  Q:  (-0.26191994547843933, -0.277223140001297, -0.32548704743385315, 0.8652186989784241)
BONE_ID:  10  Q:  (-0.2612650394439697, -0.27718862891197205, -0.326138973236084, 0.8651823997497559)
BONE_ID:  10  Q:  (-0.2608485221862793, -0.2773728668689728, -0.3263557255268097, 0.8651672601699829)
BONE_ID:  10  Q:  (-0.2608485221862793, -0.2773728668689728, -0.3263557255268097, 0.8651672601699829)
BONE_ID:  11  Q:  (-0.28890976309776306, -0.2883465886116028, -0.2883465886116028, 0.8661661148071289)
BONE_ID:  11  Q:  (-0.2879706025123596, -0.2890976667404175, -0.28853413462638855, 0.8661659359931946)
BONE_ID:  11  Q:  (-0.28646120429039, -0.2892862558364868, -0.28985127806663513, 0.8661637306213379)
BONE_ID:  11  Q:  (-0.2853233516216278, -0.2898522913455963, -0.290418416261673, 0.8661601543426514)
BONE_ID:  11  Q:  (-0.2858901917934418, -0.289853036403656, -0.289853036403656, 0.8661624193191528)
BONE_ID:  11  Q:  (-0.2883465886116028, -0.28890976309776306, -0.2883465886116028, 0.8661661148071289)
BONE_ID:  11  Q:  (-0.2950209677219391, -0.2855580449104309, -0.28500139713287354, 0.8661370873451233)
BONE_ID:  11  Q:  (-0.3038436770439148, -0.28080859780311584, -0.28080859780311584, 0.8660093545913696)
BONE_ID:  11  Q:  (-0.32253730297088623, -0.2711643576622009, -0.2711643576622009, 0.8653956055641174)
BONE_ID:  11  Q:  (-0.329613596200943, -0.2674519121646881, -0.2674519121646881, 0.8650397658348083)
BONE_ID:  11  Q:  (-0.33400359749794006, -0.26513153314590454, -0.26513153314590454, 0.8647844791412354)
BONE_ID:  11  Q:  (-0.3346237242221832, -0.2648026943206787, -0.2648026943206787, 0.8647462725639343)
BONE_ID:  11  Q:  (-0.3361664116382599, -0.26398342847824097, -0.26398342847824097, 0.8646488189697266)
BONE_ID:  11  Q:  (-0.3376983404159546, -0.2631682753562927, -0.2631682753562927, 0.864548921585083)
BONE_ID:  11  Q:  (-0.33891621232032776, -0.26251906156539917, -0.26251906156539917, 0.8644670844078064)
BONE_ID:  11  Q:  (-0.3392196297645569, -0.2623571753501892, -0.2623571753501892, 0.8644464015960693)
BONE_ID:  11  Q:  (-0.3392196297645569, -0.2623571753501892, -0.2623571753501892, 0.8644464015960693)
BONE_ID:  11  Q:  (-0.3386123776435852, -0.26268112659454346, -0.26268112659454346, 0.8644877076148987)
BONE_ID:  11  Q:  (-0.3380034565925598, -0.26300573348999023, -0.26300573348999023, 0.8645285964012146)
BONE_ID:  11  Q:  (-0.3376983404159546, -0.2631682753562927, -0.2631682753562927, 0.864548921585083)
BONE_ID:  11  Q:  (-0.33739280700683594, -0.26333096623420715, -0.26333096623420715, 0.8645690679550171)
BONE_ID:  11  Q:  (-0.33739280700683594, -0.26333096623420715, -0.26333096623420715, 0.8645690679550171)
BONE_ID:  12  Q:  (-0.3192415237426758, -0.2749830484390259, -0.27062976360321045, 0.8655799031257629)
BONE_ID:  12  Q:  (-0.3010180592536926, -0.287438303232193, -0.2768762707710266, 0.8660870790481567)
BONE_ID:  12  Q:  (-0.29530954360961914, -0.2922651171684265, -0.27780407667160034, 0.866139829158783)
BONE_ID:  12  Q:  (-0.2912430763244629, -0.29810482263565063, -0.27599474787712097, 0.8661050200462341)
BONE_ID:  12  Q:  (-0.28789517283439636, -0.3060303032398224, -0.27127131819725037, 0.8659524321556091)
BONE_ID:  12  Q:  (-0.2855707108974457, -0.31531766057014465, -0.2640041708946228, 0.8656361699104309)
BONE_ID:  12  Q:  (-0.2825174033641815, -0.3324573338031769, -0.24898630380630493, 0.86467444896698)
BONE_ID:  12  Q:  (-0.2819797694683075, -0.33879658579826355, -0.24269899725914001, 0.8641767501831055)
BONE_ID:  12  Q:  (-0.281247615814209, -0.34235823154449463, -0.23958131670951843, 0.8638815879821777)
BONE_ID:  12  Q:  (-0.2814621031284332, -0.343161940574646, -0.23848021030426025, 0.8637975454330444)
BONE_ID:  12  Q:  (-0.28122591972351074, -0.34410443902015686, -0.2376946359872818, 0.8637160062789917)
BONE_ID:  12  Q:  (-0.2809698283672333, -0.3457030653953552, -0.23620747029781342, 0.8635690212249756)
BONE_ID:  12  Q:  (-0.2802692651748657, -0.34690192341804504, -0.23561853170394897, 0.8634766936302185)
BONE_ID:  12  Q:  (-0.2807140648365021, -0.3472892642021179, -0.2347291111946106, 0.8634187579154968)
BONE_ID:  12  Q:  (-0.28003641963005066, -0.34730008244514465, -0.2354227751493454, 0.8634456396102905)
BONE_ID:  12  Q:  (-0.2802692651748657, -0.34690192341804504, -0.23561853170394897, 0.8634766936302185)
BONE_ID:  12  Q:  (-0.2805024981498718, -0.3465030789375305, -0.23581460118293762, 0.8635076880455017)
BONE_ID:  12  Q:  (-0.28050220012664795, -0.34597569704055786, -0.2363937497138977, 0.8635608553886414)
BONE_ID:  12  Q:  (-0.28050220012664795, -0.34597569704055786, -0.2363937497138977, 0.8635608553886414)
BONE_ID:  12  Q:  (-0.28073617815971375, -0.3455745279788971, -0.2365909367799759, 0.8635914325714111)
BONE_ID:  13  Q:  (-0.2885342538356781, -0.2885342538356781, -0.2885342538356781, 0.8661662936210632)
BONE_ID:  13  Q:  (-0.25150543451309204, -0.30659711360931396, -0.30659711360931396, 0.8652985095977783)
BONE_ID:  13  Q:  (-0.20603887736797333, -0.32761460542678833, -0.32761460542678833, 0.861907958984375)
BONE_ID:  13  Q:  (-0.1573510766029358, -0.34876081347465515, -0.34876081347465515, 0.8555538654327393)
BONE_ID:  13  Q:  (-0.11318269371986389, -0.3667692244052887, -0.3667692244052887, 0.8474375009536743)
BONE_ID:  13  Q:  (-0.08143428713083267, -0.37903958559036255, -0.37903958559036255, 0.8402537703514099)
BONE_ID:  13  Q:  (-0.06542275846004486, -0.38501670956611633, -0.38501670956611633, 0.836208164691925)
BONE_ID:  13  Q:  (-0.05972956866025925, -0.38710808753967285, -0.38710808753967285, 0.8347018361091614)
BONE_ID:  13  Q:  (-0.06187206134200096, -0.38632312417030334, -0.38632312417030334, 0.8352728486061096)
BONE_ID:  13  Q:  (-0.06754113733768463, -0.3842340111732483, -0.3842340111732483, 0.836759626865387)
BONE_ID:  13  Q:  (-0.07523155212402344, -0.3813718259334564, -0.3813718259334564, 0.8387200832366943)
BONE_ID:  13  Q:  (-0.08143428713083267, -0.37903958559036255, -0.37903958559036255, 0.8402537703514099)
BONE_ID:  13  Q:  (-0.08280180394649506, -0.3785225450992584, -0.3785225450992584, 0.8405861854553223)
BONE_ID:  13  Q:  (-0.08688078820705414, -0.3769742548465729, -0.3769742548465729, 0.8415655493736267)
BONE_ID:  13  Q:  (-0.09493318200111389, -0.3738906979560852, -0.3738906979560852, 0.84344482421875)
BONE_ID:  13  Q:  (-0.10545310378074646, -0.3698081374168396, -0.3698081374168396, 0.8457916378974915)
BONE_ID:  13  Q:  (-0.1306944042444229, -0.35976094007492065, -0.35976094007492065, 0.8509189486503601)
BONE_ID:  13  Q:  (-0.1421688199043274, -0.35507529973983765, -0.35507529973983765, 0.8530129194259644)
BONE_ID:  13  Q:  (-0.1515817493200302, -0.35117581486701965, -0.35117581486701965, 0.8546192646026611)
BONE_ID:  13  Q:  (-0.15792323648929596, -0.3485202491283417, -0.3485202491283417, 0.8556444644927979)
BONE_ID:  13  Q:  (-0.16020336747169495, -0.3475598394870758, -0.3475598394870758, 0.8560018539428711)
BONE_ID:  13  Q:  (-0.16077125072479248, -0.34732016921043396, -0.34732016921043396, 0.8560899496078491)
BONE_ID:  14  Q:  (-0.2354992777109146, -0.32148540019989014, -0.3067265748977661, 0.8643529415130615)
BONE_ID:  14  Q:  (-0.23568062484264374, -0.3204486072063446, -0.30760496854782104, 0.8643763661384583)
BONE_ID:  14  Q:  (-0.23621957004070282, -0.3192504346370697, -0.3083083927631378, 0.8644220232963562)
BONE_ID:  14  Q:  (-0.23610422015190125, -0.31803110241889954, -0.309644877910614, 0.8644253015518188)
BONE_ID:  14  Q:  (-0.23592422902584076, -0.3184332549571991, -0.3094088137149811, 0.8644108772277832)
BONE_ID:  14  Q:  (-0.2354992777109146, -0.32148540019989014, -0.3067265748977661, 0.8643529415130615)
BONE_ID:  14  Q:  (-0.2338261753320694, -0.32786497473716736, -0.30181366205215454, 0.8641402125358582)
BONE_ID:  14  Q:  (-0.23111814260482788, -0.3369689881801605, -0.2950044572353363, 0.8637179136276245)
BONE_ID:  14  Q:  (-0.22577759623527527, -0.3562673330307007, -0.27979427576065063, 0.862446129322052)
BONE_ID:  14  Q:  (-0.2239924669265747, -0.36353856325149536, -0.2737020254135132, 0.8618319630622864)
BONE_ID:  14  Q:  (-0.22277110815048218, -0.3683148920536041, -0.2697015404701233, 0.8613815903663635)
BONE_ID:  14  Q:  (-0.2224460393190384, -0.3689638376235962, -0.2693080008029938, 0.8613110780715942)
BONE_ID:  14  Q:  (-0.22194653749465942, -0.3705027401447296, -0.2681114077568054, 0.8611525297164917)
BONE_ID:  14  Q:  (-0.2214483767747879, -0.3720332682132721, -0.2669191062450409, 0.8609912991523743)
BONE_ID:  14  Q:  (-0.22125285863876343, -0.37307000160217285, -0.2659741938114166, 0.860885500907898)
BONE_ID:  14  Q:  (-0.22123882174491882, -0.3736346960067749, -0.26536890864372253, 0.8608308434486389)
BONE_ID:  14  Q:  (-0.22123882174491882, -0.3736346960067749, -0.26536890864372253, 0.8608308434486389)
BONE_ID:  14  Q:  (-0.22141359746456146, -0.3727521598339081, -0.26616740226745605, 0.8609220385551453)
BONE_ID:  14  Q:  (-0.2215745449066162, -0.3724338114261627, -0.266360878944397, 0.8609585762023926)
BONE_ID:  14  Q:  (-0.2214483767747879, -0.3720332682132721, -0.2669191062450409, 0.8609912991523743)
BONE_ID:  14  Q:  (-0.22146205604076385, -0.3714657127857208, -0.26752617955207825, 0.8610444664955139)
BONE_ID:  14  Q:  (-0.22146205604076385, -0.3714657127857208, -0.26752617955207825, 0.8610444664955139)
BONE_ID:  15  Q:  (-0.2885342538356781, -0.2885342538356781, -0.2885342538356781, 0.8661662936210632)
BONE_ID:  15  Q:  (-0.2520122528076172, -0.30635613203048706, -0.30635613203048706, 0.865321695804596)
BONE_ID:  15  Q:  (-0.20836688578128815, -0.32688748836517334, -0.326250284910202, 0.8621418476104736)
BONE_ID:  15  Q:  (-0.16050918400287628, -0.3474312722682953, -0.3474312722682953, 0.8560490012168884)
BONE_ID:  15  Q:  (-0.1180562749505043, -0.36483654379844666, -0.36483654379844666, 0.8484405875205994)
BONE_ID:  15  Q:  (-0.08740047365427017, -0.3767768144607544, -0.3767768144607544, 0.8416885733604431)
BONE_ID:  15  Q:  (-0.07231715321540833, -0.3824608027935028, -0.3824608027935028, 0.8379843235015869)
BONE_ID:  15  Q:  (-0.06741758435964584, -0.3842802345752716, -0.3842802345752716, 0.8367271423339844)
BONE_ID:  15  Q:  (-0.06952337175607681, -0.3834998905658722, -0.3834998905658722, 0.8372707366943359)
BONE_ID:  15  Q:  (-0.08265282213687897, -0.37857943773269653, -0.37857943773269653, 0.8405497074127197)
BONE_ID:  15  Q:  (-0.08740047365427017, -0.3767768144607544, -0.3767768144607544, 0.8416885733604431)
BONE_ID:  15  Q:  (-0.08807479590177536, -0.37651973962783813, -0.37651973962783813, 0.8418482542037964)
BONE_ID:  15  Q:  (-0.09009195864200592, -0.3757493793964386, -0.3757493793964386, 0.8423231840133667)
BONE_ID:  15  Q:  (-0.09410006552934647, -0.3742119073867798, -0.3742119073867798, 0.8432533144950867)
BONE_ID:  15  Q:  (-0.10004710406064987, -0.37191423773765564, -0.37191423773765564, 0.8446005582809448)
BONE_ID:  15  Q:  (-0.11931447684764862, -0.364335298538208, -0.364335298538208, 0.8486952781677246)
BONE_ID:  15  Q:  (-0.12431030720472336, -0.36233630776405334, -0.36233630776405334, 0.849689245223999)
BONE_ID:  15  Q:  (-0.12740279734134674, -0.36109188199043274, -0.36109188199043274, 0.8502904772758484)
BONE_ID:  15  Q:  (-0.1292472928762436, -0.36034709215164185, -0.36034709215164185, 0.8506438732147217)
BONE_ID:  15  Q:  (-0.1292472928762436, -0.36034709215164185, -0.36034709215164185, 0.8506438732147217)
BONE_ID:  16  Q:  (-0.2246105670928955, -0.22592923045158386, 0.8566849231719971, -0.40570560097694397)
BONE_ID:  16  Q:  (-0.217651829123497, -0.23600801825523376, 0.8570587038993835, -0.4029618203639984)
BONE_ID:  16  Q:  (-0.21071301400661469, -0.24843324720859528, 0.857593297958374, -0.39801347255706787)
BONE_ID:  16  Q:  (-0.20400400459766388, -0.25964146852493286, 0.8578519225120544, -0.39377516508102417)
BONE_ID:  16  Q:  (-0.1971578299999237, -0.26646438241004944, 0.8575074076652527, -0.3934547007083893)
BONE_ID:  16  Q:  (-0.1899678111076355, -0.26465970277786255, 0.8561503887176514, -0.4010911285877228)
BONE_ID:  16  Q:  (-0.18174582719802856, -0.2525218427181244, 0.8532442450523376, -0.4185396730899811)
BONE_ID:  16  Q:  (-0.17389465868473053, -0.23096778988838196, 0.8485167622566223, -0.4432084560394287)
BONE_ID:  16  Q:  (0.8597614169120789, -0.2521710991859436, -0.38382208347320557, -0.22338443994522095)
BONE_ID:  16  Q:  (0.8625149130821228, -0.2528385818004608, -0.3617362678050995, -0.24756325781345367)
BONE_ID:  16  Q:  (0.8640382289886475, -0.252336323261261, -0.34375715255737305, -0.26757311820983887)
BONE_ID:  16  Q:  (0.8646304607391357, -0.25172320008277893, -0.3331739008426666, -0.27936482429504395)
BONE_ID:  16  Q:  (0.8648484349250793, -0.25145211815834045, -0.32780545949935913, -0.2852237820625305)
BONE_ID:  16  Q:  (0.8649656176567078, -0.25121355056762695, -0.3240874707698822, -0.289298415184021)
BONE_ID:  16  Q:  (0.8650202751159668, -0.2510641813278198, -0.32196149230003357, -0.2916291356086731)
BONE_ID:  16  Q:  (0.8650473952293396, -0.25096604228019714, -0.3207396864891052, -0.29297634959220886)
BONE_ID:  16  Q:  (0.8650599718093872, -0.2512288987636566, -0.3206089735031128, -0.29285693168640137)
BONE_ID:  16  Q:  (0.8650515079498291, -0.251332551240921, -0.32110655307769775, -0.29224714636802673)
BONE_ID:  16  Q:  (0.8650329113006592, -0.2514333128929138, -0.3219662010669708, -0.2912679612636566)
BONE_ID:  16  Q:  (0.8650020956993103, -0.25163698196411133, -0.3233242630958557, -0.28967511653900146)
BONE_ID:  16  Q:  (0.8649787902832031, -0.2518431842327118, -0.32432129979133606, -0.288448303937912)
BONE_ID:  16  Q:  (0.8649544715881348, -0.2519427239894867, -0.32518187165260315, -0.2874636948108673)
BONE_ID:  16  Q:  (0.8649423718452454, -0.25193917751312256, -0.32554352283477783, -0.28709349036216736)
BONE_ID:  17  Q:  (-0.23936787247657776, -0.3209705650806427, -0.3037433326244354, 0.8645350933074951)
BONE_ID:  17  Q:  (-0.2366769015789032, -0.34103837609291077, -0.2855963408946991, 0.8637775182723999)
BONE_ID:  17  Q:  (-0.2361825406551361, -0.362467885017395, -0.263174831867218, 0.8623072504997253)
BONE_ID:  17  Q:  (-0.23685358464717865, -0.3824562132358551, -0.2403440624475479, 0.8601524829864502)
BONE_ID:  17  Q:  (-0.2365499883890152, -0.3985075354576111, -0.22224459052085876, 0.8578130006790161)
BONE_ID:  17  Q:  (-0.2312338948249817, -0.4090270698070526, -0.2153044492006302, 0.8560792803764343)
BONE_ID:  17  Q:  (-0.20758867263793945, -0.4182451665401459, -0.22804075479507446, 0.8543859124183655)
BONE_ID:  17  Q:  (-0.1925119310617447, -0.41604241728782654, -0.2451942265033722, 0.8542409539222717)
BONE_ID:  17  Q:  (-0.18328823149204254, -0.40761810541152954, -0.2635059952735901, 0.8548787236213684)
BONE_ID:  17  Q:  (-0.17857395112514496, -0.3959491550922394, -0.28086814284324646, 0.8558321595191956)
BONE_ID:  17  Q:  (-0.17722782492637634, -0.38427361845970154, -0.29481974244117737, 0.8567411303520203)
BONE_ID:  17  Q:  (-0.17700675129890442, -0.3769058585166931, -0.302914559841156, 0.8572359681129456)
BONE_ID:  17  Q:  (-0.17656661570072174, -0.3737393915653229, -0.30666834115982056, 0.8573784232139587)
BONE_ID:  17  Q:  (-0.1764727234840393, -0.3713948428630829, -0.3092283308506012, 0.857496976852417)
BONE_ID:  17  Q:  (-0.17589612305164337, -0.3701813817024231, -0.311016321182251, 0.8574935793876648)
BONE_ID:  17  Q:  (-0.17541293799877167, -0.3692062795162201, -0.3124667704105377, 0.8574855327606201)
BONE_ID:  17  Q:  (-0.17492961883544922, -0.3690734803676605, -0.313031941652298, 0.8574353456497192)
BONE_ID:  17  Q:  (-0.17436113953590393, -0.36961349844932556, -0.3129661977291107, 0.8573426008224487)
BONE_ID:  17  Q:  (-0.1743658185005188, -0.37052735686302185, -0.3120017945766449, 0.8572986125946045)
BONE_ID:  17  Q:  (-0.17445716261863708, -0.3712286055088043, -0.3111828863620758, 0.8572743535041809)
BONE_ID:  17  Q:  (-0.1745448112487793, -0.3723350763320923, -0.3099393844604492, 0.857227087020874)
BONE_ID:  17  Q:  (-0.1747971773147583, -0.3733372986316681, -0.308658242225647, 0.8572020530700684)
BONE_ID:  17  Q:  (-0.17479994893074036, -0.373809278011322, -0.30815669894218445, 0.8571762442588806)
BONE_ID:  18  Q:  (-0.39230072498321533, -0.23301388323307037, -0.23301388323307037, 0.8587836027145386)
BONE_ID:  18  Q:  (-0.4048233926296234, -0.22578385472297668, -0.22578385472297668, 0.8568320870399475)
BONE_ID:  18  Q:  (-0.42606064677238464, -0.21323856711387634, -0.21323856711387634, 0.8529542684555054)
BONE_ID:  18  Q:  (-0.41771191358566284, -0.21821406483650208, 0.8545653820037842, -0.21821406483650208)
BONE_ID:  18  Q:  (-0.4103586971759796, -0.22276614606380463, 0.8558909893035889, -0.2223319113254547)
BONE_ID:  18  Q:  (-0.4061551094055176, -0.22500817477703094, 0.8566100597381592, -0.22500817477703094)
BONE_ID:  18  Q:  (-0.3952881991863251, -0.23130007088184357, 0.8583400845527649, -0.23130007088184357)
BONE_ID:  18  Q:  (-0.39043715596199036, -0.23407942056655884, 0.8590531945228577, -0.23407942056655884)
BONE_ID:  18  Q:  (-0.3878430724143982, -0.23555830121040344, 0.8594197630882263, -0.23555830121040344)
BONE_ID:  18  Q:  (-0.3878430724143982, -0.23555830121040344, 0.8594197630882263, -0.23555830121040344)
BONE_ID:  18  Q:  (-0.3880804479122162, -0.23542320728302002, 0.859386682510376, -0.23542320728302002)
BONE_ID:  18  Q:  (-0.3880804479122162, -0.23542320728302002, 0.859386682510376, -0.23542320728302002)
BONE_ID:  18  Q:  (-0.38717204332351685, -0.23570998013019562, 0.8595127463340759, -0.23617035150527954)
BONE_ID:  18  Q:  (-0.3864123821258545, -0.2363717406988144, 0.8596175312995911, -0.2363717406988144)
BONE_ID:  18  Q:  (-0.38497045636177063, -0.23718997836112976, 0.8598136901855469, -0.23718997836112976)
BONE_ID:  18  Q:  (-0.3814157545566559, -0.23920083045959473, 0.8602837324142456, -0.23920083045959473)
BONE_ID:  18  Q:  (-0.3805760443210602, -0.23967397212982178, 0.8603920936584473, -0.23967397212982178)
BONE_ID:  18  Q:  (-0.37933680415153503, -0.24037183821201324, 0.8605499863624573, -0.24037183821201324)
BONE_ID:  18  Q:  (-0.37808936834335327, -0.24107317626476288, 0.8607065677642822, -0.24107317626476288)
BONE_ID:  18  Q:  (-0.37708544731140137, -0.2416367381811142, 0.8608309030532837, -0.2416367381811142)
BONE_ID:  19  Q:  (0.8237915635108948, -0.02866673842072487, -0.44735202193260193, -0.34701842069625854)
BONE_ID:  19  Q:  (-0.44428083300590515, -0.339964896440506, -0.04277703911066055, 0.8277732729911804)
BONE_ID:  19  Q:  (-0.4134034514427185, -0.3196418285369873, -0.11151948571205139, 0.8452750444412231)
BONE_ID:  19  Q:  (-0.3821676969528198, -0.29761144518852234, -0.17643630504608154, 0.8568812608718872)
BONE_ID:  19  Q:  (-0.35850194096565247, -0.27524498105049133, -0.22802463173866272, 0.8623928427696228)
BONE_ID:  19  Q:  (-0.34920254349708557, -0.2525898516178131, -0.2613199055194855, 0.8636943101882935)
BONE_ID:  19  Q:  (-0.3677407205104828, -0.23450131714344025, -0.25901737809181213, 0.8617923855781555)
BONE_ID:  19  Q:  (-0.38444724678993225, -0.21217849850654602, -0.2621920108795166, 0.8593229055404663)
BONE_ID:  19  Q:  (-0.39815858006477356, -0.18913745880126953, -0.2686721682548523, 0.8564531803131104)
BONE_ID:  19  Q:  (-0.4080066382884979, -0.16915081441402435, -0.27603182196617126, 0.8536539673805237)
BONE_ID:  19  Q:  (-0.41430890560150146, -0.1546395719051361, -0.2820160984992981, 0.8514115214347839)
BONE_ID:  19  Q:  (-0.4172079265117645, -0.14632762968540192, -0.28612276911735535, 0.8500938415527344)
BONE_ID:  19  Q:  (-0.4182562530040741, -0.14185462892055511, -0.28886762261390686, 0.8494083285331726)
BONE_ID:  19  Q:  (-0.4177549481391907, -0.13967880606651306, -0.2913178503513336, 0.8491787314414978)
BONE_ID:  19  Q:  (-0.41709232330322266, -0.13874617218971252, -0.29286113381385803, 0.8491265177726746)
BONE_ID:  19  Q:  (-0.41567564010620117, -0.13912932574748993, -0.29409798979759216, 0.8493310809135437)
BONE_ID:  19  Q:  (-0.41386479139328003, -0.14039534330368042, -0.2950024902820587, 0.8496932983398438)
BONE_ID:  19  Q:  (-0.4118416905403137, -0.14249375462532043, -0.29541388154029846, 0.8501837849617004)
BONE_ID:  19  Q:  (-0.40747010707855225, -0.1476469486951828, -0.29573726654052734, 0.8512977361679077)
BONE_ID:  19  Q:  (-0.4055247902870178, -0.1499457061290741, -0.29586300253868103, 0.8517810702323914)
BONE_ID:  19  Q:  (-0.4040093719959259, -0.1517850160598755, -0.2959132194519043, 0.8521580100059509)
BONE_ID:  19  Q:  (-0.4037609398365021, -0.15220071375370026, -0.2958203852176666, 0.8522337079048157)
BONE_ID:  20  Q:  (0.8553368449211121, -0.28969606757164, -0.17051731050014496, -0.3942066729068756)
BONE_ID:  20  Q:  (0.8453846573829651, -0.2062622457742691, -0.17914795875549316, -0.45900610089302063)
BONE_ID:  20  Q:  (0.8245891332626343, -0.11040940135717392, -0.19296778738498688, -0.52021723985672)
BONE_ID:  20  Q:  (-0.20124244689941406, -0.5410763621330261, -0.07024500519037247, 0.8135131001472473)
BONE_ID:  20  Q:  (-0.19625864923000336, -0.509937047958374, -0.1216132715344429, 0.8286476731300354)
BONE_ID:  20  Q:  (-0.19512830674648285, -0.4882064163684845, -0.15270911157131195, 0.8368150591850281)
BONE_ID:  20  Q:  (-0.1942616105079651, -0.4782394468784332, -0.1668277233839035, 0.8400702476501465)
BONE_ID:  20  Q:  (-0.194450244307518, -0.4754858911037445, -0.17023567855358124, 0.8409056067466736)
BONE_ID:  20  Q:  (-0.19437360763549805, -0.47743478417396545, -0.16776733100414276, 0.8403148055076599)
BONE_ID:  20  Q:  (-0.19521497189998627, -0.48612356185913086, -0.1554064303636551, 0.8375105261802673)
BONE_ID:  20  Q:  (-0.19512830674648285, -0.4882064163684845, -0.15270911157131195, 0.8368150591850281)
BONE_ID:  20  Q:  (-0.19512830674648285, -0.4882064163684845, -0.15270911157131195, 0.8368150591850281)
BONE_ID:  21  Q:  (-0.38693374395370483, -0.23630596697330475, -0.23584532737731934, 0.8595456480979919)
BONE_ID:  21  Q:  (-0.38693374395370483, -0.23584532737731934, -0.23630596697330475, 0.8595456480979919)
BONE_ID:  22  Q:  (-0.06930200755596161, -0.3547602593898773, 0.8365741968154907, -0.41168689727783203)
BONE_ID:  22  Q:  (-0.07007462531328201, -0.35449516773223877, 0.8367735147476196, -0.41137927770614624)
BONE_ID:  22  Q:  (-0.07077326625585556, -0.353866308927536, 0.8369349837303162, -0.41147246956825256)
BONE_ID:  22  Q:  (-0.07077326625585556, -0.353866308927536, 0.8369349837303162, -0.41147246956825256)
BONE_ID:  22  Q:  (-0.07077326625585556, -0.353866308927536, 0.8369349837303162, -0.41147246956825256)
BONE_ID:  22  Q:  (-0.06930200755596161, -0.3547602593898773, 0.8365741968154907, -0.41168689727783203)
BONE_ID:  22  Q:  (-0.06620246171951294, -0.3566657602787018, 0.8358060717582703, -0.412110298871994)
BONE_ID:  22  Q:  (-0.061517391353845596, -0.3599598705768585, 0.8346413969993591, -0.41233280301094055)
BONE_ID:  22  Q:  (-0.055993787944316864, -0.36354175209999084, 0.8332210183143616, -0.4128497242927551)
BONE_ID:  22  Q:  (-0.05040890350937843, -0.3671448230743408, 0.8317468762397766, -0.41335299611091614)
BONE_ID:  22  Q:  (-0.04561961442232132, -0.37002575397491455, 0.8304459452629089, -0.4139557480812073)
BONE_ID:  22  Q:  (-0.04318247362971306, -0.3717079758644104, 0.8297808766365051, -0.41404372453689575)
BONE_ID:  22  Q:  (-0.04150809347629547, -0.3727257251739502, 0.8293147683143616, -0.41423383355140686)
BONE_ID:  22  Q:  (-0.04073392227292061, -0.37339431047439575, 0.8291050791740417, -0.41412821412086487)
BONE_ID:  22  Q:  (-0.03991474583745003, -0.37366998195648193, 0.8288679718971252, -0.4144339859485626)
BONE_ID:  22  Q:  (-0.03991474583745003, -0.37366998195648193, 0.8288679718971252, -0.4144339859485626)
BONE_ID:  22  Q:  (-0.03991474583745003, -0.37366998195648193, 0.8288679718971252, -0.4144339859485626)
BONE_ID:  22  Q:  (-0.03991474583745003, -0.37366998195648193, 0.8288679718971252, -0.4144339859485626)
BONE_ID:  22  Q:  (-0.040690984576940536, -0.37300071120262146, 0.8290788531303406, -0.4145394265651703)
BONE_ID:  22  Q:  (-0.04150809347629547, -0.3727257251739502, 0.8293147683143616, -0.41423383355140686)
BONE_ID:  22  Q:  (-0.04150809347629547, -0.3727257251739502, 0.8293147683143616, -0.41423383355140686)
BONE_ID:  23  Q:  (-0.1130843237042427, -0.3671661913394928, 0.8474166989326477, -0.3664504587650299)
BONE_ID:  23  Q:  (-0.1130843237042427, -0.3671661913394928, 0.8474166989326477, -0.3664504587650299)
BONE_ID:  24  Q:  (-0.20840880274772644, -0.32433223724365234, 0.862140953540802, -0.32876646518707275)
BONE_ID:  24  Q:  (-0.16477490961551666, -0.34361594915390015, 0.8566955327987671, -0.34763485193252563)
BONE_ID:  24  Q:  (-0.11366747319698334, -0.36444634199142456, 0.847533106803894, -0.36870887875556946)
BONE_ID:  24  Q:  (-0.0621262863278389, -0.3847338855266571, 0.8353365659713745, -0.38772791624069214)
BONE_ID:  24  Q:  (-0.017898280173540115, -0.4007658362388611, 0.822542667388916, -0.4031004011631012)
BONE_ID:  24  Q:  (-0.012507999315857887, -0.4026012420654297, -0.4049464762210846, 0.8208374381065369)
BONE_ID:  24  Q:  (-0.027022916823625565, -0.3976229131221771, -0.3999391794204712, 0.8253570795059204)
BONE_ID:  24  Q:  (-0.031530484557151794, -0.396053671836853, -0.3983607590198517, 0.8267139792442322)
BONE_ID:  24  Q:  (-0.028529491275548935, -0.39709967374801636, -0.3994128704071045, 0.8258131146430969)
BONE_ID:  24  Q:  (-0.01559426262974739, -0.4015522599220276, -0.4038914144039154, 0.8218176364898682)
BONE_ID:  24  Q:  (-0.012507999315857887, -0.4026012420654297, -0.4049464762210846, 0.8208374381065369)
BONE_ID:  24  Q:  (-0.012507999315857887, -0.4026012420654297, -0.4049464762210846, 0.8208374381065369)
BONE_ID:  25  Q:  (-0.03249217942357063, -0.3968687653541565, 0.8270033597946167, -0.3968687653541565)
BONE_ID:  25  Q:  (-0.03252296894788742, -0.3972448408603668, 0.8270126581192017, -0.39647048711776733)
BONE_ID:  26  Q:  (-0.3741985261440277, 0.8511053919792175, -0.34345144033432007, -0.13280121982097626)
BONE_ID:  26  Q:  (-0.3800484240055084, 0.8549383878707886, -0.315228670835495, -0.15897896885871887)
BONE_ID:  26  Q:  (-0.3812357187271118, 0.8586645126342773, -0.28150615096092224, -0.19521532952785492)
BONE_ID:  26  Q:  (-0.37949609756469727, 0.860578179359436, -0.24308067560195923, -0.23727576434612274)
BONE_ID:  26  Q:  (-0.35588881373405457, 0.8628891706466675, -0.23584695160388947, -0.2704472541809082)
BONE_ID:  26  Q:  (-0.33952271938323975, 0.8636136054992676, -0.23071017861366272, -0.29269200563430786)
BONE_ID:  26  Q:  (-0.33470821380615234, 0.8635879755020142, -0.22743865847587585, -0.3007621467113495)
BONE_ID:  26  Q:  (-0.34113502502441406, 0.8633496761322021, -0.2271972894668579, -0.2943391799926758)
BONE_ID:  26  Q:  (-0.3549024760723114, 0.862686038017273, -0.22863911092281342, -0.2784619629383087)
BONE_ID:  26  Q:  (-0.37028253078460693, 0.8614736199378967, -0.23013848066329956, -0.26036563515663147)
BONE_ID:  26  Q:  (-0.38280460238456726, 0.8601033091545105, -0.23106223344802856, -0.24554674327373505)
BONE_ID:  26  Q:  (-0.38955023884773254, 0.8592207431793213, -0.23138180375099182, -0.2375980168581009)
BONE_ID:  26  Q:  (-0.39214542508125305, 0.8588536977767944, -0.23128294944763184, -0.2347349375486374)
BONE_ID:  26  Q:  (-0.3934399485588074, 0.8586654663085938, -0.23123225569725037, -0.2333029955625534)
BONE_ID:  26  Q:  (-0.39438340067863464, 0.858526349067688, -0.23138080537319183, -0.23207148909568787)
BONE_ID:  26  Q:  (-0.3946804404258728, 0.858481764793396, -0.23086385428905487, -0.2322462797164917)
BONE_ID:  26  Q:  (-0.394330769777298, 0.8585341572761536, -0.23106399178504944, -0.23244760930538177)
BONE_ID:  26  Q:  (-0.3936828374862671, 0.8586298823356628, -0.2310897558927536, -0.2331654131412506)
BONE_ID:  26  Q:  (-0.3926825225353241, 0.8587766289710999, -0.23131564259529114, -0.23408588767051697)
BONE_ID:  26  Q:  (-0.3910272717475891, 0.8590120077133179, -0.2308724820613861, -0.2364189624786377)
BONE_ID:  26  Q:  (-0.3900790214538574, 0.859143853187561, -0.23072169721126556, -0.23765027523040771)
BONE_ID:  26  Q:  (-0.38972344994544983, 0.8591945767402649, -0.23092153668403625, -0.23785611987113953)
BONE_ID:  27  Q:  (-0.40460753440856934, -0.2259095460176468, -0.2259095460176468, 0.8568678498268127)
BONE_ID:  27  Q:  (-0.39755257964134216, -0.22999651730060577, -0.22999651730060577, 0.857994794845581)
BONE_ID:  27  Q:  (-0.3873673975467682, -0.23582890629768372, -0.23582890629768372, 0.8594858050346375)
BONE_ID:  27  Q:  (-0.35723304748535156, -0.252628892660141, -0.252628892660141, 0.8629842400550842)
BONE_ID:  27  Q:  (-0.33962932229042053, -0.26188284158706665, -0.26239433884620667, 0.8644179701805115)
BONE_ID:  27  Q:  (-0.32866156101226807, -0.26795336604118347, -0.26795336604118347, 0.8650916218757629)
BONE_ID:  27  Q:  (-0.32834330201148987, -0.2681208550930023, -0.2681208550930023, 0.8651086688041687)
BONE_ID:  27  Q:  (-0.33555060625076294, -0.2643106281757355, -0.2643106281757355, 0.8646880984306335)
BONE_ID:  27  Q:  (-0.34401705861091614, -0.2597886919975281, -0.2597886919975281, 0.8641018271446228)
BONE_ID:  27  Q:  (-0.350154310464859, -0.25647926330566406, -0.25647926330566406, 0.8636137843132019)
BONE_ID:  27  Q:  (-0.35224950313568115, -0.2555926442146301, -0.25509440898895264, 0.8634347915649414)
BONE_ID:  27  Q:  (-0.35216087102890015, -0.2553914487361908, -0.2553914487361908, 0.863442599773407)
BONE_ID:  27  Q:  (-0.3513032793998718, -0.2558567225933075, -0.2558567225933075, 0.8635164499282837)
BONE_ID:  27  Q:  (-0.35044214129447937, -0.2563233971595764, -0.2563233971595764, 0.8635895848274231)
BONE_ID:  27  Q:  (-0.3489989638328552, -0.2571042776107788, -0.2571042776107788, 0.8637096881866455)
BONE_ID:  27  Q:  (-0.3386123776435852, -0.26268112659454346, -0.26268112659454346, 0.8644877076148987)
BONE_ID:  27  Q:  (-0.33739280700683594, -0.26333096623420715, -0.26333096623420715, 0.8645690679550171)
BONE_ID:  28  Q:  (-0.22414648532867432, -0.32389166951179504, -0.31492578983306885, 0.863524317741394)
BONE_ID:  28  Q:  (-0.23402820527553558, -0.31570637226104736, -0.3139685392379761, 0.8642824292182922)
BONE_ID:  28  Q:  (-0.24638396501541138, -0.30932876467704773, -0.30872929096221924, 0.8650414943695068)
BONE_ID:  28  Q:  (-0.2610601484775543, -0.3053911030292511, -0.2986183166503906, 0.8656852841377258)
BONE_ID:  28  Q:  (-0.2657364010810852, -0.3065238296985626, -0.292928010225296, 0.8658062219619751)
BONE_ID:  28  Q:  (-0.2725202441215515, -0.30559009313583374, -0.2872179448604584, 0.8659406900405884)
BONE_ID:  28  Q:  (-0.2753461003303528, -0.3049987852573395, -0.2850286066532135, 0.8659786581993103)
BONE_ID:  28  Q:  (-0.27123236656188965, -0.30663660168647766, -0.28743430972099304, 0.865903377532959)
BONE_ID:  28  Q:  (-0.2545619606971741, -0.31225475668907166, -0.29798024892807007, 0.865391731262207)
BONE_ID:  28  Q:  (-0.24835586547851562, -0.31458407640457153, -0.3015749752521515, 0.8651062250137329)
BONE_ID:  28  Q:  (-0.2459612935781479, -0.3153953552246094, -0.30303844809532166, 0.8649834990501404)
BONE_ID:  28  Q:  (-0.24596771597862244, -0.3150729238986969, -0.3033601641654968, 0.8649864196777344)
BONE_ID:  28  Q:  (-0.24690298736095428, -0.31461161375045776, -0.30293771624565125, 0.8650360107421875)
BONE_ID:  28  Q:  (-0.2484213262796402, -0.3141627907752991, -0.30194535851478577, 0.865111231803894)
BONE_ID:  28  Q:  (-0.26303234696388245, -0.30706170201301575, -0.2950536906719208, 0.8657195568084717)
BONE_ID:  28  Q:  (-0.26538801193237305, -0.3059096336364746, -0.29392436146736145, 0.8657927513122559)
BONE_ID:  28  Q:  (-0.26698097586631775, -0.3051210939884186, -0.29316672682762146, 0.8658380508422852)
BONE_ID:  29  Q:  (-0.0007955465116538107, -0.4073198139667511, -0.40811535716056824, 0.8170262575149536)
BONE_ID:  29  Q:  (-0.0007955253240652382, -0.4128776490688324, -0.4025358259677887, 0.8170045018196106)
BONE_ID:  29  Q:  (-0.0007955253240652382, -0.4025358259677887, -0.4128776490688324, 0.8170045018196106)
BONE_ID:  29  Q:  (-0.0007955465116538107, -0.4073198139667511, -0.40811535716056824, 0.8170262575149536)
BONE_ID:  29  Q:  (-0.0007955465116538107, -0.4073198139667511, -0.40811535716056824, 0.8170262575149536)
BONE_ID:  30  Q:  (-0.2528231143951416, 0.8583653569221497, -0.39280080795288086, -0.212124764919281)
BONE_ID:  30  Q:  (-0.2336735874414444, 0.8602071404457092, -0.38204729557037354, -0.24388553202152252)
BONE_ID:  30  Q:  (-0.21509599685668945, 0.8609622120857239, -0.36890119314193726, -0.2763867974281311)
BONE_ID:  30  Q:  (-0.20148511230945587, 0.8607891798019409, -0.3565167188644409, -0.3022276759147644)
BONE_ID:  30  Q:  (-0.2115708589553833, 0.8620387315750122, -0.34661608934402466, -0.3032890856266022)
BONE_ID:  30  Q:  (-0.2237754762172699, 0.8632152676582336, -0.33822551369667053, -0.3006449043750763)
BONE_ID:  30  Q:  (-0.24117715656757355, 0.8644114136695862, -0.33103883266448975, -0.29161566495895386)
BONE_ID:  30  Q:  (-0.2449503093957901, 0.8647315502166748, -0.32584089040756226, -0.29337072372436523)
BONE_ID:  30  Q:  (-0.25584226846694946, 0.8650451302528381, -0.3269732892513275, -0.2816559374332428)
BONE_ID:  30  Q:  (-0.26983582973480225, 0.8649932742118835, -0.33057811856269836, -0.2639952301979065)
BONE_ID:  30  Q:  (-0.28135454654693604, 0.8647080659866333, -0.3320809304714203, -0.2506827712059021)
BONE_ID:  30  Q:  (-0.28777042031288147, 0.8644931316375732, -0.33208826184272766, -0.2440435141324997)
BONE_ID:  30  Q:  (-0.2903207540512085, 0.8644713759422302, -0.3310364782810211, -0.24252404272556305)
BONE_ID:  30  Q:  (-0.29187503457069397, 0.8644217848777771, -0.3307916820049286, -0.241165429353714)
BONE_ID:  30  Q:  (-0.2936324179172516, 0.8643878102302551, -0.3301890790462494, -0.239976704120636)
BONE_ID:  30  Q:  (-0.29421266913414, 0.8643602728843689, -0.33017855882644653, -0.23937945067882538)
BONE_ID:  30  Q:  (-0.29479265213012695, 0.8643320202827454, -0.3301677703857422, -0.23878203332424164)
BONE_ID:  30  Q:  (-0.29518041014671326, 0.8643307089805603, -0.3299421966075897, -0.2386189103126526)
BONE_ID:  30  Q:  (-0.2949844300746918, 0.8643044233322144, -0.3303825557231903, -0.23834742605686188)
BONE_ID:  30  Q:  (-0.2951924800872803, 0.8643235564231873, -0.33002516627311707, -0.23851551115512848)
BONE_ID:  30  Q:  (-0.2950003147125244, 0.8643509745597839, -0.32981035113334656, -0.23895026743412018)
BONE_ID:  30  Q:  (-0.2950003147125244, 0.8643509745597839, -0.32981035113334656, -0.23895026743412018)
BONE_ID:  30  Q:  (-0.2950003147125244, 0.8643509745597839, -0.32981035113334656, -0.23895026743412018)
BONE_ID:  31  Q:  (-0.4078557789325714, -0.224015012383461, -0.224015012383461, 0.8563224673271179)
BONE_ID:  31  Q:  (-0.39329659938812256, -0.23244372010231018, -0.23244372010231018, 0.8586371541023254)
BONE_ID:  31  Q:  (-0.37081581354141235, -0.24513983726501465, -0.24513983726501465, 0.861573338508606)
BONE_ID:  31  Q:  (-0.3473495543003082, -0.25824683904647827, -0.2577434480190277, 0.8638432621955872)
BONE_ID:  31  Q:  (-0.3083963692188263, -0.2784813642501831, -0.2784813642501831, 0.8659030199050903)
BONE_ID:  31  Q:  (-0.2926348149776459, -0.28647997975349426, -0.28647997975349426, 0.8661543130874634)
BONE_ID:  31  Q:  (-0.29992398619651794, -0.28280124068260193, -0.28280124068260193, 0.866078794002533)
BONE_ID:  31  Q:  (-0.31691572070121765, -0.2740892767906189, -0.2740892767906189, 0.8656296133995056)
BONE_ID:  31  Q:  (-0.32610300183296204, -0.2692979574203491, -0.2692979574203491, 0.8652248978614807)
BONE_ID:  31  Q:  (-0.32866156101226807, -0.26795336604118347, -0.26795336604118347, 0.8650916218757629)
BONE_ID:  31  Q:  (-0.3190533518791199, -0.27271339297294617, -0.27324604988098145, 0.8655454516410828)
... there is not enough space for the last 3 bones

```


Im still trying to find something by reverse engineering with ghidra.. but it seems to be the famous search for the needle in the haystack (since I never used disassembling software and try to fight my way with ghidra).

Thanks to both of you!! for your precious time and patience to empathize the problem 
本当にありがとう
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-19T13:09:48+00:00
- Post Title: [Help] The unsolvable Rotation

Please try to share the whole script code, or better yet the ".py" plugin. If we can see the same results you are seeing, it will be easier to understand and help. It is hard to help with animation research just by looking at some quaternion output logs
## Post #8
- Username: MilesPrower
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 10, 2020 4:54 pm
- Post datetime: 2020-02-19T13:47:43+00:00
- Post Title: [Help] The unsolvable Rotation

Allright sorry,

```
	anim_data = open("C:\\ABS\\PATH\\TO\\Dynamic_Actions_Drink.bin", "rb").read()

```

you should change absolute path to the Dynamic_Actions_Drink.bin inside the loading script.
and then you open the PrinceFinal_Shape_wow.bin.
Then you should have the same result like me.

Here is also the *.dol file for disassembling if needed
[https://filebin.net/twsl8rg5gcglmx89](https://filebin.net/twsl8rg5gcglmx89)

and the needed plugins .. if you use ghidra
[https://github.com/aldelaro5/ghidra-gekko-broadway-lang](https://github.com/aldelaro5/ghidra-gekko-broadway-lang)
[https://github.com/Cuyler36/Ghidra-GameCube-Loader](https://github.com/Cuyler36/Ghidra-GameCube-Loader)
[format_prince_persia.rar](https://xentaxbackup.github.io/file/17516_format_prince_persia.rar)
## Post #9
- Username: MilesPrower
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 10, 2020 4:54 pm
- Post datetime: 2021-01-29T22:07:52+00:00
- Post Title: [Help] The unsolvable Rotation

For the sake of completion. I  think I solved this problem around last year february.. but without sharing the final results. Im sorry. This is for you folks:

```

import noesis
import rapi
import struct
import binascii
import math

def registerNoesisTypes():
	handle = noesis.register("000_PrinceOfPersiaTT", ".bin")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	noesis.logPopup()
	return 1

def noepyCheckType(data):
	return 1

IDToIndex 						=	dict()
parentLocalQuat					=	[]
def getSkelleton():	
	data 						=	open("H:\\Programme\\PoPTools\\bf_repacker_2018_05_23_1419\\ROOT\\Bin\\extracted\\PrinceFinal_Shape_wow.bin", "rb").read()
	fs 							=	NoeBitStream(data)
	addr 						=	0x00013ADF
	fs.seek(addr, NOESEEK_ABS)
	bones 						=	[]
	bone_count 					=	34
	
	
	for i in range(0, bone_count):
		blockSize				=	fs.readUInt()
		blockTag				=	hex(fs.readUInt())
		blockID					=	fs.readUShort()
		unknown 				=	fs.readBytes(18)
		nameLength 				=	fs.readUInt()		
		name 					=	noeStrFromBytes(fs.readBytes(nameLength), "ASCII")
		unknown 				=	fs.readBytes(10)
		
		mat44 					=	NoeMat44.fromBytes(fs.readBytes(64))
		boneMat 				=	mat44.toMat43()
		
		unknown 				=	fs.readBytes(52)
		parentID				=	fs.readUShort()	
		IDToIndex[str(blockID)]	=	i
		bones.append( 				NoeBone(blockID, name, boneMat, None, parentID))

		fs.seek(addr + blockSize + 12)
		addr = addr + (blockSize + 12)	
	
#	bones.append( 					NoeBone(99, "B_Pr_Bip Root.gao", NoeMat43()))
#	IDToIndex["99"]				=	99
	
	#	LOCAL TO GLOBAL MATRIX
	for i in range(0,bone_count):
		if	bones[i].index 		!= 	8932:
			parentLocalQuat.append(	bones[IDToIndex[str(bones[i].parentIndex)]].getMatrix().toQuat()	)
			bones[i].setMatrix( bones[i].getMatrix() * bones[IDToIndex[str(bones[i].parentIndex)]].getMatrix() )
	
	#	CONVERT INDEX FORMAT
	for i in range(0,bone_count):
		if	bones[i].index != 8932:
			bones[i].index			=	IDToIndex[str(bones[i].index)]
			bones[i].parentIndex	=	IDToIndex[str(bones[i].parentIndex)]
		if	bones[i].index == 8932:
			bones[i].index			=	0
			bones[i].parentIndex	=	99
#			bones[i].parentIndex	=	-1
	return bones
	
flagListAnim 	= [hex(0xfa03),hex(0xfa00),hex(0xfe03),hex(0xea00),hex(0xf800),hex(0xfa07)]
flagListDiv		= [hex(0x4017),hex(0x0000),hex(0x4014)]
def validateBlock(trackSize, trackFrame, flag, boneID):
	if trackSize 	< 0:		return 0
	if trackFrame 	< 0:		return 0
	if boneID 		!= 0xFFFF:	return 0
	if flag in flagListAnim:	return 1
	return 0
	
def findAnimationBlocks(bs):
	#	=================================
	#	|			BLOCKS				|
	#	=================================
	#	BLOCK_HEAD
	#	[
	#		4	blockSize	00000000
	#		4	blockTag	99C0FFEE	(ALWAYS)
	#		4	blockID		00000000
	#	]
	#	TRAVERSE TROUGH ALL AVAIABLE BLOCKS
	blockArray			=	[]
	for i in range(0,1000):
		blockAddr		=	bs.tell()
		blockSize		=	bs.readUInt()
		blockTag		=	hex(bs.readUInt())
		blockID			=	hex(bs.readUInt())
		addr			=	bs.tell()
		
		#	REACHED END OF FILE
		if blockID ==	hex(0xff7c0de):
			return blockArray
	
		trackSize		=	bs.readUShort()
		trackFrame		=	bs.readUShort()
		flag			=	hex(bs.readUShort())
		boneID			=	bs.readUShort()
	
		if validateBlock(trackSize, trackFrame, flag, boneID) == 0:
			#	JUMP TO THE NEXT BLOCK
			bs.seek(addr + blockSize, NOESEEK_ABS)	
			continue
	
		blockArray.append(blockAddr)
		bs.seek(addr + blockSize, NOESEEK_ABS)
	return blockArray
	
def noepyLoadModel(data, mdlList): 
	#	=================================
	#	|			ANIMATION			|
	#	=================================	
	ctx 				=	rapi.rpgCreateContext()
	rapi.					rpgClearBufferBinds()
	keyDurations 		= 	[]
	bones				=	getSkelleton()
	kfbones 			=	[]
	bs 					=	NoeBitStream(data)
	fileSize 			=	bs.getSize()
	animBlocks 			=	findAnimationBlocks(bs)
	anim_bones_rot		=	dict()
	anim_bones_vec		=	dict()
	anim_tracks			=	dict()
	anims 				=	[]	
	anim_counter		=	0
		
	for animAddr in animBlocks:
		anim_counter	=	anim_counter + 1
		bs.seek(animAddr,	NOESEEK_ABS)
		kfbones 		=	[]
		blockSize		= 	bs.readUInt()
		blockTag		= 	hex(bs.readUInt())
		blockID			= 	hex(bs.readUInt())
		trackCount		= 	bs.readUShort()				#	trackCount
		trackFrame		= 	bs.readUShort()				#	trackFrameNum_A		
		for track in range(0, trackCount):
			frame 			=	1						#	init start frame
			flag_01			= 	hex(bs.readUShort())	#	flags
			boneID			= 	bs.readShort()			#	boneID
			trackSize		= 	bs.readUInt()			#	trackSize		
			trackFrameNum	=	bs.readUInt()			#	trackFrameNum_B
			frameLength		=	bs.readByte()			#	trackFrameLen	
			flag_02			=	bs.readByte()			#	trackFrameTypeFlags
			unknown			=	bs.readByte()			#	---			
			keyType			=	bs.readByte()			#	---
			unknown			=	bs.readBytes(2)			#	---
														#	0x90	uncrompressed quaternion	in BGE
														#	0x10	part3case0 quaternion		in BGE
														#	0x01	part3case1 vec3				in BGE
			if flag_01 in flagListDiv:	break			#	0x4017	skip programcode
			keyDurations.		append(trackFrameNum)
			anim_rot_frames		=	dict()
			anim_vec_frames		=	dict()
			
			for key in range(0,trackFrameNum):
				if hex(keyType) == hex(0x10):
					duration 	=	int(bs.readByte())	#	freq
					v1			=	bs.readFloat()		#	f1
					v2			=	bs.readFloat()		#	f2
					v3			=	bs.readFloat()		#	f3				
					anim_vec_frames[frame]	=	NoeVec3((v1, v2, v3))
					frame 					=	frame + (1 * duration)
					
				if hex(keyType) == hex(0x08):
					duration	=	int(bs.readByte())											
					compressed	=	bs.readUInt()
					v 			=	compressed & 0xC0000000
					#	range		=	1 / math.sqrt(2)
					#	norm		=	range / 512
					
					if duration == 64 or duration == 0:
						duration = 1
					#	continue
			
					if v == 0:
						v1		=	float(((compressed >> 20) & 0x3FF) * 0.0013810679 - 0.70710677);
						v2		=	float(((compressed >> 10) & 0x3FF) * 0.0013810679 - 0.70710677);
						v3		=	float(((compressed >> 00) & 0x3FF) * 0.0013810679 - 0.70710677);
						v0		=	float(math.sqrt(1.0 - pow(v1,2) - pow(v2,2) - pow(v3,2)))
					
					if v == 0x40000000:
						v0		=	float(((compressed >> 20) & 0x3FF) * 0.0013810679 - 0.70710677);
						v2		=	float(((compressed >> 10) & 0x3FF) * 0.0013810679 - 0.70710677);
						v3		=	float(((compressed >> 00) & 0x3FF) * 0.0013810679 - 0.70710677);
						v1		=	float(math.sqrt(1.0 - pow(v0,2) - pow(v2,2) - pow(v3,2)))

					if v == 0x80000000:
						v0		=	float(((compressed >> 20) & 0x3FF) * 0.0013810679 - 0.70710677);
						v1		=	float(((compressed >> 10) & 0x3FF) * 0.0013810679 - 0.70710677);
						v3		=	float(((compressed >> 00) & 0x3FF) * 0.0013810679 - 0.70710677);
						v2		=	float(math.sqrt(1.0 - pow(v0,2) - pow(v1,2) - pow(v3,2)))
						
					if v == 0xC0000000:
						v0		=	float(((compressed >> 20) & 0x3FF) * 0.0013810679 - 0.70710677);
						v1		=	float(((compressed >> 10) & 0x3FF) * 0.0013810679 - 0.70710677);
						v2		=	float(((compressed >> 00) & 0x3FF) * 0.0013810679 - 0.70710677);
						v3		=	float(math.sqrt(1.0 - pow(v0,2) - pow(v1,2) - pow(v2,2)))
														
					anim_rot_frames[frame]	=	NoeQuat((v0, v1, v2, v3)).transpose()
					frame 					=	frame + (1 * duration)			
			#END OF KEYS			
		#	if boneID == -1: boneID 	=	99
			if len(anim_rot_frames) != 0:	anim_bones_rot[boneID] = anim_rot_frames
			if len(anim_vec_frames) != 0:	anim_bones_vec[boneID] = anim_vec_frames
					
		#END OF TRACKS	
		for bone in anim_bones_rot:
			rotationKeys 					= 	[]
			translationKeys 				=	[]
			
			if bone in anim_bones_rot:
				for anim_frame in anim_bones_rot[bone]:
					frame						=	anim_frame
					quat 						=	anim_bones_rot[bone][anim_frame]				
					rotationKeys.					append(NoeKeyFramedValue(frame, quat	))	
			if bone in anim_bones_vec:
				for anim_frame in anim_bones_vec[bone]:
					frame						=	anim_frame
					vec							=	anim_bones_vec[bone][anim_frame]
					translationKeys.				append(NoeKeyFramedValue(frame, vec		))	

			skip							=	False
			for ele in kfbones:
				if ele.boneIndex == bone:
					if len(rotationKeys 	!= 0):	ele.setRotation(rotationKeys)
					if len(translationKeys 	!= 0):	ele.setTranslation(translationKeys)
					skip					=	True
					
			if not(skip):
				kfbone 						= 	NoeKeyFramedBone(bone)
				if len(rotationKeys) 	!= 0:	kfbone.setRotation(rotationKeys)	
				if len(translationKeys)	!= 0:	kfbone.setTranslation(translationKeys)	
				kfbones.						append(kfbone)		
		
		#if anim_counter == 42:
		anims.append(NoeKeyFramedAnim("anim_" + str(blockID), bones, kfbones, 1.0))				
		
	mdl = NoeModel()
	mdl.setBones(bones)
	mdl.setAnims(anims)
	mdlList.append(mdl)
	
	rapi.setPreviewOption("setAngOfs", "0 0 0")
	rapi.setPreviewOption("setAnimSpeed", "10")
	return 1

```


This is how the quaternion compression works

```

    switch (compressed & 0xC0000000) {
    case 0:
        destQuat[1] = (float)((double)((compressed >> 20) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[2] = (float)((double)((compressed >> 10) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[3] = (float)((double)((compressed >> 0) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[0] = (float) sqrt(1.0 - destQuat[1] * destQuat[1] - destQuat[2] * destQuat[2] - destQuat[3] * destQuat[3]);
        break;
    case 0x40000000:
        destQuat[0] = (float)((double)((compressed >> 20) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[2] = (float)((double)((compressed >> 10) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[3] = (float)((double)((compressed >> 0) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[1] = (float) sqrt(1.0 - destQuat[0] * destQuat[0] - destQuat[2] * destQuat[2] - destQuat[3] * destQuat[3]);
        break;
    case 0x80000000:
        destQuat[0] = (float)((double)((compressed >> 20) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[1] = (float)((double)((compressed >> 10) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[3] = (float)((double)((compressed >> 0) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[2] = (float) sqrt(1.0 - destQuat[0] * destQuat[0] - destQuat[1] * destQuat[1] - destQuat[3] * destQuat[3]);
        break;
    case 0xC0000000:
        destQuat[0] = (float)((double)((compressed >> 20) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[1] = (float)((double)((compressed >> 10) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[2] = (float)((double)((compressed >> 0) & 0x3FF) * 0.0013810679 - 0.70710677);
        destQuat[3] = (float) sqrt(1.0 - destQuat[0] * destQuat[0] - destQuat[1] * destQuat[1] - destQuat[2] * destQuat[2]);
        break;
    }  
}
```


just in case if you wonder where those number coming from

0.70710677 = 1/sqrt(2)

is the limit range of one component after omitting the largest value
the limitrange of the components can be calculate like this min/max [-1/sqrt(2), 1/sqrt(2)]

0.0013810679 = (1/sqrt(2)) / (2^10 / 2)

we have 10 bits for each component which mean 1024 steps for the range of [-1, 1].
0.707 / 512 = 0.00138...

And a final outcome of the prince drinking water:


thanks goes to andrax, shakotay2, rogueclarkey, akderebur for helping me out!
## Post #10
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-01-30T00:56:00+00:00
- Post Title: [Help] The unsolvable Rotation

Great job, thank you for sharing and congrats for solving it.
Why are you setting the anim's framerate to 1 here though ?

```
anims.append(NoeKeyFramedAnim("anim_" + str(blockID), bones, kfbones, 1.0))
```
## Post #11
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-27T15:51:52+00:00
- Post Title: [Help] The unsolvable Rotation

MilesPrower
It only for prince model or it be work on farah too? i've try prince final shape from GC version and anim. file drink work from GC and PC version as well.
I try change addr to 0x000ABA5 and bone_count to 33 for ACT_NPC_Farah_wow_ff0233a9.bin from GC version trying load model or anim file (as example drink) i got this error:

```
Traceback (most recent call last):
  File "E:\Noesis\plugins\python\fmt_princet2t.py", line 123, in noepyLoadModel
    bones				=	getSkelleton()
  File "E:\Noesis\plugins\python\fmt_princet2t.py", line 56, in getSkelleton
    parentLocalQuat.append(	bones[IDToIndex[str(bones[i].parentIndex)]].getMatrix().toQuat()	)
KeyError: '12807'

```


Here the ACT_NPC_Farah_wow_ff0233a9.bin if need (from GC, decompressed bin) [https://dropmefiles.com/N3OAN](https://dropmefiles.com/N3OAN)

Where i need to do changes to bring it work?
## Post #12
- Username: MilesPrower
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 10, 2020 4:54 pm
- Post datetime: 2021-03-03T10:18:31+00:00
- Post Title: [Help] The unsolvable Rotation

> Reply from JakeMiles ↑Sat Feb 27, 2021 11:51 pm at Sat Feb 27, 2021 11:51 pm
>
> 
MilesPrower
It only for prince model or it be work on farah too? i've try prince final shape from GC version and anim. file drink work from GC and PC version as well.

all the animations are acutally exclusively for the prince.. she could have a completly different bone structure. 
but many paths lead to rome:

1) export the skelleton from the prince
1b) export the skelleton from the girl
2) export all animations from the prince
3) import both skelletons into autodesk motion builder
4) match the source from the skeleton of the prince to hers
5) rerecord the animation from A to B
6) optional: proportion correction etc.

this process is called retargeting (mostly used for motion capturing). MotionBuilder has a nasty learningcurve but you could give it a try..
ue4 got a new feature recently where you could even retarget in real time.
## Post #13
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-03-03T16:05:06+00:00
- Post Title: [Help] The unsolvable Rotation

> Reply from MilesPrower ↑Wed Mar 03, 2021 6:18 pm at Wed Mar 03, 2021 6:18 pm
>
> 
JakeMiles wrote: ↑Sat Feb 27, 2021 11:51 pm
MilesPrower
It only for prince model or it be work on farah too? i've try prince final shape from GC version and anim. file drink work from GC and PC version as well.


all the animations are acutally exclusively for the prince.. she could have a completly different bone structure. 
but many paths lead to rome:

1) export the skelleton from the prince
1b) export the skelleton from the girl
2) export all animations from the prince
3) import both skelletons into autodesk motion builder
4) match the source from the skeleton of the prince to hers
5) rerecord the animation from A to B
6) optional: proportion correction etc.

this process is called retargeting (mostly used for motion capturing). MotionBuilder has a nasty learningcurve but you could give it a try..
ue4 got a new feature recently where you could even retarget in real time.
MilesPrower
I got it, i've see what it retargeting animation, in UE4, in some other software it will be a bit same or not too difficult. I think script will can work on farah too, because files strucrure are same a bit, just different bones start pos. and counts, and may just change some parameters in script and it will work, just load farah skel, without anim? Where farah anims place i don't know right now, as you say it for prince and you are better know you own script i will trust you.

Edited:
MilesPrower do you research only prince of persia t2t for gc? or other versions (WW, SoT for GC as example) may have same format with bit different changes? Ive interested in SoT animations, maybe i can found something, just need know where to start, build skel. etc.  

And no weight info, it not researched at this time and need attack skel to mesh it self (re-rig)?
## Post #14
- Username: princeteam
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 27, 2020 11:12 pm
- Post datetime: 2021-05-10T14:21:22+00:00
- Post Title: [Help] The unsolvable Rotation

> Reply from MilesPrower ↑Sat Jan 30, 2021 6:07 am at Sat Jan 30, 2021 6:07 am
>
> 
For the sake of completion. I  think I solved this problem around last year february.. but without sharing the final results. Im sorry. This is for you folks:

And a final outcome of the prince drinking water:


thanks goes to andrax, shakotay2, rogueclarkey, akderebur for helping me out!

Omg Thank you !

I will try it too. Hope i dont need that lost files you send.
## Post #15
- Username: princeteam
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 27, 2020 11:12 pm
- Post datetime: 2021-05-15T12:08:33+00:00
- Post Title: [Help] The unsolvable Rotation

Seems like Prince 's basic animations (walk, run, primary weapon) in his model (PrinceFinal_Shape_wow.bin)  . And because it has Mesh script is failing.

or AMIR_wow_ff068e34.bin containing skeleton files too. seems like its a animation manager

Edit:



But this is missing some bones too soo i loaded Princeloading_shape.bin to blender and saw all bones
