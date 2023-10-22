## Post #1
- Username: grenadier42
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 18, 2011 11:53 pm
- Post datetime: 2016-08-13T17:15:35+00:00
- Post Title: Kritika Online animations (.anim)

I feel like I've almost gotten this figured out, but I'm hitting a wall.

The quaternion rotation data is stored as a int16[4], where the first three int16s are three encoded components (the encoding is simply mapping the range [0,65535] to [-0.707,0.707], and the fourth is a value from 0 to 3 which designates which component is missing (which I guess is necessary because unit quaternions can have at most a single component greater than 0.707, which is outside of the range of their serialized data format). So, for instance:

```
FF 7F FF FF FF 7F 03 00
```


is the quaternion (0.0, 0.707, 0.0) with a missing fourth component of 0.707, recalculated during deserialization. Now I have the issue of not knowing which axes each of those fourth values maps to, which is an issue since the missing value also determines the mapping of the first three values. (I'm pretty sure 3 means the missing component is W, which logically would make 0, 1, 2 -> X, Y, Z, but beyond that it's guesswork.)

Complicating things further, setting all rotation data to (0.0, 0.0, 0.0, 1.0) (xyzw), aka no rotation, causes all bones in the model to become parallel ingame, which implies that bone rotations are actually stored relative to the parent bone's world rotation or something along those lines.

Luckily, there're a few animation files that exist that have a single frame in them, used for posing characters in dioramas. The sample I'm linking in particular has three files: the bones file, which contains the bind pose and all bones; the "_Freeze.anim" animation file, which has one rotation quat for each bone, starting at 0x2C22; and the camera animation file, which is for the camera panning around the diorama (you'd need to look at the translation data as well in this one).

The other good thing about this sample is that the bind pose here is actually pre-posed; that is to say, the animation data seems identical to the bind pose in the bones file, it's just stored differently. My knowledge of matrices and quaternions fails me here, though, especially when dealing with conversion to Blender's coordinate system and stuff.

[Sample](http://www.mediafire.com/download/tkqrfqacu61oho3/Kritika_WarriorCreate.rar)

Szkaradek123 posted an import script for Blender 2.49b [in a previous thread](http://forum.xentax.com/viewtopic.php?f=16&t=11967), so that's a good reference for the bone format. Conveniently, the bone matrices are all stored in world space.
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-14T05:15:36+00:00
- Post Title: Kritika Online animations (.anim)

Since this kind of storing quaternions was described in some old 3d-modelling book, its highly possible that they do it like everybody else:

axis == 3 ---->   q = [x, y, z, w]
axis == 2 ---->   q = [x, y, w, z]
axis == 1 ---->   q = [x, w, y, z]
axis == 0 ---->   q = [w, x, y, z]
