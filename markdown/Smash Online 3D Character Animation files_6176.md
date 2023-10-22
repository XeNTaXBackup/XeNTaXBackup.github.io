## Post #1
- Username: jildert
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 27, 2010 12:06 am
- Post datetime: 2011-03-04T11:58:15+00:00
- Post Title: Smash Online: 3D Character Animation files

Game: Smash Online
fatduck asked the same question some years back so I figured he solved the format and could give it to me but he didn't have the files anymore  and he didn't really want to get into it again. 
So I hope someone else can help me by giving me some help on figuring out the fileformat or by giving me some pointers what to look for. 
I can already load in levels and characters with items and stuff. I just have no idea how to figure out the animation fileformat. The most info for the other fileformats I found on the net but can get any further with the animation fileformat.

This is what fatduckposted a while back. Put in some edit commets on stuff I figured out myself and of stuff I think is wrong.

```
dword          nVersion     //4
dword          unknown1
dword          unknown2
word           nBones
word           nFrames     //??
word           nFPS         //??
word           unknown3                    (edit: Total length in bytes for all bones) 
dword          unknown4
dword          uknRef1                      (edit: should be word?)
dword          uknRef2                      (edit: should be word?)

Struct BoneArray {
   char[]      szBoneName
}
Struct BoneData {                          (edit: no idea what todo with the BoneData struct or if the info is even correct couldn't correct xyz values)
   word        uknB01
   word        uknB02
   word        uknB03     //Related to uknRef2
   word        uknB04     //Related to uknRef1
   float X 3   posXYZ    //should be Initial Position
   Byte X 12   ??         //should be Initial Rotation   
}
<data> ??

```


Wat I got so far (C#) is the standard info with all bone names but after that I have no clue what to look for.

```
Console.WriteLine("Version: " + reader.ReadUInt32()); // nVersion
Console.WriteLine("Unknown 1: " + reader.ReadUInt32()); // Unknown1
Console.WriteLine("Unknown 2: " + reader.ReadUInt32()); // Unknown2
int numberOfBones = reader.ReadUInt16();
Console.WriteLine("Number of Bones: " + numberOfBones); // numberOfBones
Console.WriteLine("Number of Frames: " + reader.ReadUInt16()); // numberOfFrames
Console.WriteLine("Frames per Second: " + reader.ReadUInt16()); // numberOfFPS (most of the time 30)
int bonesStringLength = reader.ReadUInt16();
Console.WriteLine("BoneStringLength: " + bonesStringLength); // Total length of bytes for all bones
Console.WriteLine("Unknown 4: " + reader.ReadUInt32()); // Unknown 4
Console.WriteLine("Unknown Ref 1: " + reader.ReadUInt16()); // UnknownRef 1
Console.WriteLine("Unknown Ref 2: " + reader.ReadUInt16()); // UnknownRef 2

// print all bone names used in the animation file
for (int i = 0; i < numberOfBones; i++)
{
  string boneName = "";
  char c;
  while ((c = (char)reader.ReadByte()) != 0)
    boneName += c.ToString();
  Console.WriteLine(boneName);
}

```


Example Animation files (posted by fatduck):
[download/file.php?id=1494](http://forum.xentax.com/download/file.php?id=1494)

Trying to get everything working as a learning project.
Would be cool if I could get the animations working. This is what I've got so far. 
[](http://img43.imageshack.us/i/naamlooscs.jpg/)
