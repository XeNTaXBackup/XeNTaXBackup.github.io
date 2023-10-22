## Post #1
- Username: Kanbaru
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 27, 2018 5:49 pm
- Post datetime: 2018-05-08T02:58:35+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

I added a function to import motion files based on [https://github.com/C4nf3ng/Nier2Blender](https://github.com/C4nf3ng/Nier2Blender)

References: [https://github.com/Kerilk/bayonetta_too ... on-Formats](https://github.com/Kerilk/bayonetta_tools/wiki/Motion-Formats)



This is my current work,


Action files can be read in, but there may be problems with the mapping of the bones, and there may be problems with the rotation of the bones.


visit plugin code: [https://github.com/lihaochen910/Nier2Blender](https://github.com/lihaochen910/Nier2Blender)
Please help me 
[plugin_and_test_motion_file.zip](https://xentaxbackup.github.io/file/14336_plugin_and_test_motion_file.zip)
## Post #2
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2018-05-09T23:27:34+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

> Reply from Kanbaru
>
> I added a function to import motion files based on https://github.com/C4nf3ng/Nier2Blender

References: https://github.com/Kerilk/bayonetta_too ... on-Formats



This is my current work,


Action files can be read in, but there may be problems with the mapping of the bones, and there may be problems with the rotation of the bones.


visit plugin code: https://github.com/lihaochen910/Nier2Blender
Please help me
Just a few remarks, I may have more time later:
 - I have implemented the specs in the Bayonetta plug-in for Noesis, it might help desambiguating
 - The bone translation table is inside the wmb file. Its format is identical to bayonetta's. There should be a binary template for nier automata models in the bayonetta_tools repository showing where this table is
 - default value for translation is relative position to parent

Don't hesitate if you have specific questions. I have one for you: in which files did you find type 14 an 15 tracks, I will take a look at them?
## Post #3
- Username: Kanbaru
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 27, 2018 5:49 pm
- Post datetime: 2018-05-10T02:56:34+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

@Kerilk:
thank you for your reply,
I found TrackType:14,15 in 
    "data006/pl/pl000f.dat/pl0000_0a00.mot",
    "data006/pl/pl000f.dat/pl0000_ffff.mot",

and i viewed your repository, but the Ruby language is strange to me.
## Post #4
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2018-05-10T12:43:44+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

Thanks for the motion files I'll take a look.

I was more thinking of these scripts:
[https://github.com/Kerilk/bayonetta_too ... _templates](https://github.com/Kerilk/bayonetta_tools/tree/master/binary_templates)
which are used with 010 Editor [https://www.sweetscape.com/010editor/](https://www.sweetscape.com/010editor/)
They allow to view the structure of model files and animation files.

And this repository:
[https://github.com/Kerilk/noesis_bayonetta_pc](https://github.com/Kerilk/noesis_bayonetta_pc)
which implements a plugin for Noesis (in c++ for now, maybe I'll do a python version sometimes) and decodes animations for Bayonetta and Bayonetta 2.
## Post #5
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2018-06-11T16:27:28+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

I have added Nier Automata models and motions to the plugin. I can confirm that the motion format is identical to the one used by Bayonetta2. Track 14 and 15 are used for bones which are not in the model, so perhaps they are used to change the camera settings?
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2018-11-25T11:54:37+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

I am trying to translate the "class FloatDecompressor" code
to the Python code, but I'm stuck while understanding what is happening with the value of "v.ui = value;".
I do not know where it is passed on and what is "union Bits" - the equivalent of "class" in Python?

class FloatDecompressor:

[https://github.com/Kerilk/noesis_bayone ... c.cpp#L544](https://github.com/Kerilk/noesis_bayonetta_pc/blob/9f9dc1932c8c857d5c193934075df981e0240b01/bayonetta_pc/bayonetta_pc.cpp#L544)

```
	{
		Bits v;
		v.ui = value;  ??????????????????????????????????????????????????????? 
		int sign = v.si & signH;
		v.si ^= sign;

		sign <<=  shiftSign;
		int exponent = v.si & exponentH;
		int significand = v.si ^ exponent;
		significand <<= shiftBits;
```


And that's a piece of translated code.
Unfortunately, I always get the value at output 0.

```
	
#static FloatDecompressor C(6, 9, 47)

class Bits():
	def __init__(self):
		self.f=0.0 #float
		self.si=0 #int
		self.ui=0 #Uint
		
value=5685#short Unsigned Int from file
		

eHBits=6
sHBits=9
bH=47
	
exponentHBits=eHBits
significandHBits=sHBits
biasH=bH	
	
significandFBits = 23	
exponentFBits = 8
biasF = 127
exponentF    = 0x7F800000
significandF = 0x007fffff
signF        = 0x80000000
signH        = 0x8000

tmp = 0
for i in range(eHBits):
	tmp <<= 1
	tmp += 1
	
tmp <<= sHBits
exponentH = tmp

tmp = 0
for i in range(eHBits):
	tmp <<= 1
	tmp += 1

significandH = tmp
shiftSign = significandFBits + exponentFBits - significandHBits - exponentHBits
shiftBits = significandFBits - significandHBits


print significandH,shiftSign,shiftBits


v=Bits()

v.ui = value
sign = v.si & signH
v.si ^= sign

sign <<=  shiftSign;
exponent = v.si & exponentH
significand = v.si ^ exponent
significand <<= shiftBits

v.si = sign | significand;
if exponent == exponentH:
	v.si |= exponentF;
elif exponent != 0:
	exponent >>= significandHBits
	exponent += biasF - biasH
	exponent <<= significandFBits
	v.si |= exponent;
elif significand:
	magic=Bits()
	magic.ui = (biasF - biasH + biasF) << significandFBits
	v.f *= magic.f
	
print v.f

```
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-25T15:36:26+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

> Reply from Szkaradek123
>
> I am trying to translate the "class FloatDecompressor" code
to the Python code, but I'm stuck while understanding what is happening with the value of "v.ui = value;".
I do not know where it is passed onHi Mariusz,
you know this has already been done? (View zip in Kanbaru's opening post, mot.py, #thanks Phernost (stackoverflow)
class FloatDecompressor(object): )

Dunno if I understood correctly but "value" is the parameter which is passed to the C function float decompress()
so if value= 123 the call would be decompress(value), a call-by-value with a float being returned.
(would make sense to name the variable nValue, imho)

from your python code (I'm not very good at python, puuh)
elif significand:
   magic=Bits()
   magic.ui = (biasF - biasH + biasF) << significandFBits
   v.f *= magic.f

I wouldn't wonder why v.f is always 0.0 because I don't see where the default 0.0 of magic.f is "overwritten".
## Post #8
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2018-11-25T16:30:44+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

I'm stupid. I do not know how I missed it. I have focused too much on this original code.
Thank you shakotay2 

But there must be a mistake with naming in Kerilk/noesis_bayonetta_pc.
I think that everywhere instead of "v.si" should be "v.ui", as it was done by Kanbaru and that's why it fooled me.

"v.f is always 0.0" because "v.ui" as input value was not converted at all.

This data compression format in animation is something new to me and it's worth getting to know it.
## Post #9
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2018-11-25T20:21:08+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

The real reason for using the signed representation of the data is that the exponent needs to be signed due to the subtraction. You avoid unnecessary casting that would obfuscate the code.
This code is derived from the one Phernost gave here:
[https://stackoverflow.com/questions/165 ... conversion](https://stackoverflow.com/questions/1659440/32-bit-to-16-bit-floating-point-conversion)

I just broke it down until I could understand what it was doing.

As far as what an union does, it does not convert anything as it uses the same data to represent the three numbers, so setting all three members to 0 is meaningless.
Maybe this example will make it seem clearer:

```

union bits {
	float f;
	unsigned int ui;
	int si;
};

int main() {
	union bits n;
	n.f = -49.5f;
	printf("%f (%x), %u, %d\n", n.f, n.ui, n.ui, n.si);
	return 0;
}
```


so the code

```
	n.f = -49.5f;
```


Will actually put the following binary number in n:
1 10000100 10001100000000000000000
(sign exponent mantissa)
or in hexa:
0xc2460000

This means that the code will display:

> -49.500000 (c2460000), 3259367424, -1035599872
float (hexa), unsigned int, signed int
You can play with:
[https://www.h-schmidt.net/FloatConverter/IEEE754.html](https://www.h-schmidt.net/FloatConverter/IEEE754.html)
to learn a bit about float representation.
## Post #10
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2018-11-26T15:06:27+00:00
- Post Title: Any one help~Import Nier Automata motion file to blender

I tried to adapt the Kanbaru plugin to Blender 249 today.

Comparing the information from 
  "[https://github.com/Kerilk/bayonetta_too ... mot-files)](https://github.com/Kerilk/bayonetta_tools/wiki/Motion-Formats-%28mot-files%29) "
it seems to me that the values of "coeffs" in the code of Kanbaru are incorrectly counted, because they do not include the earlier "keyframe".
Current "keyframe" = keys [i + 1]
Earlier "keyframe" = keys

As Kerilk wrote:

```

float p0 = value.p + value.dp * keys [i] .cp
float m0 = value.m1 + value.dm1 * keys [i] .cm1
float p1 = value.p + value.dp * keys [i + 1] .cp
float m1 = value.m0 + value.dm0 * keys [i + 1] .cm0
float t = (float) (index - keys [i] .index) / (keys [i + 1] .index - keys [i] .index)
float val = (2 * t ^ 3 - 3 * t ^ 2 + 1) * p0 + (t ^ 3 - 2 * t ^ 2 + t) * m0 + (-2 * t ^ 3 + 3 * t ^ 2 ) * p1 + (t ^ 3 - t ^ 2) * m1;
```



Here, what I managed to write for "Type 0x06" type animation.
Bone rotation is probably good, but I'm not sure about the translation.

[http://www.mediafire.com/file/sygsic4c8 ... 1-26%5D.7z](http://www.mediafire.com/file/sygsic4c88z72nc/Blender249%5BBayonetta%5D%5BPC%5D%5Bmot%5D%5B2018-11-26%5D.7z)

You need:
[http://download.blender.org/release/Ble ... indows.exe](http://download.blender.org/release/Blender2.49b/blender-2.49b-windows.exe)
and
[https://www.python.org/ftp/python/2.6.6 ... -2.6.6.msi](https://www.python.org/ftp/python/2.6.6/python-2.6.6.msi)

Unpack archive, doubleclick on file "Blender249.blend" , press alt+p in Blender Text Window and 
1.
 - import  "*.wmb" from folder "pl0044_dat"
2.
 - select "skeleton" in Blender 3D View
3.
 - import "*.mot" file

Script is not for Blender 278 only for oldie version 249b
[sr.jpg](https://xentaxbackup.github.io/file/15242_sr.jpg)
