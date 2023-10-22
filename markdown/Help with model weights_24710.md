## Post #1
- Username: Puxtril
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 24, 2018 5:13 am
- Post datetime: 2021-11-09T03:01:21+00:00
- Post Title: Help with model weights

So I've got this model mostly extracted, but the format for the weights recently changed. I'm new to asset extraction and I'm just not sure what I'm looking at. Previously the weights could be read as reader.readByte() / 255.0 but now it's reading jibberish. Here's a screenshot of the before/after - so the bones are fine, just strange weight values. Would appreciate any help with this.



Attached are the header and body files, though the body files has all the relevant data. Vertices start at 0x2B26, count is 3537. Indices start right after, they're 16-bit ints, first LOD has 17721 indices.

```
// Custom scale for positions, extracted from the header but I hardcoded for this model example
Vector3 pos = ( 
	reader.ReadInt16() / 32767.0 * 0.6387201,
	reader.ReadInt16() / 32767.0 * 1.69796109,
	reader.ReadInt16() / 32767.0 * 0.262121439
);
reader.Seek(0x6, SeekOrigin.Current); //Normals?
reader.Seek(0x4, SeekOrigin.Current); //Tangent?
Vector2 texCords1 = (
	reader.readHalfFloat(),
	reader.readHalfFloat()
);
Vector2 texCords2 = (
	reader.readHalfFloat(),
	reader.readHalfFloat()
);
byte[4] boneLocals = (
	reader.ReadByte(),
	reader.ReadByte(),
	reader.ReadByte(),
	reader.ReadByte()
);
float[4] weights = (
	reader.ReadByte() / 255.0,
	reader.ReadByte() / 255.0,
	reader.ReadByte() / 255.0,
	reader.ReadByte() / 255.0
);

```

[Excalibur.zip](https://xentaxbackup.github.io/file/21191_Excalibur.zip)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-09T12:51:50+00:00
- Post Title: Help with model weights

They're unsigned 10-bit integers packed into one uint32 element. So you need to do something like this:

```
for i in range(0, 4):
	weights[i] = (value & 0x3FF) / 0x3FF
	value >>= 10

```
## Post #3
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-09T15:11:02+00:00
- Post Title: Help with model weights

Jeez, that was a quick fix by Ghost. Maybe one day I'll find peace in this puzzle solving game indeed and figure out bones and weights  .
## Post #4
- Username: Puxtril
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 24, 2018 5:13 am
- Post datetime: 2021-11-10T02:35:23+00:00
- Post Title: Help with model weights

Yep, that was it!  Big thanks  

Only change I made is the 4th weight. I AND the uint 3 times and then subtract all those values from 1 to get the final weight.
