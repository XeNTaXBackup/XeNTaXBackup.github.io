## Post #1
- Username: PenneyM19
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Apr 07, 2019 6:14 am
- Post datetime: 2019-07-17T22:05:04+00:00
- Post Title: Help with noesis python export script (help still needed.)

Hello, i am writing a script for noesis to export animation files for the game Spongebob battle for bikini bottom. And i have only one question, how do i get XYZ position and Rotation info and write it using noesis's python language? I've looked everywhere and cannot find it. Thanks if anyone can help!
Here is my code:

```

def registerNoesisTypes():
	handle = noesis.register("Heavy Iron", ".anim")
	noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
	#noesis.logPopup()
	return 1
	
def noepyWriteAnim(anims, bs):
	bs.writeUInt(0x31424B53)
	bs.writeUInt(0)
	for anim in anims:
		bs.writeUShort(len(anim.bones)) 
		bs.writeUShort(anim.numFrames - 1)
		bs.writeUInt(len(anim.frameMats))
		bs.writeFloat(0) #need position X
		bs.writeFloat(0) #Y
		bs.writeFloat(0) #Z
	return 1
```
## Post #2
- Username: PenneyM19
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Apr 07, 2019 6:14 am
- Post datetime: 2019-07-20T18:17:51+00:00
- Post Title: Help with noesis python export script (help still needed.)

Also, here is the anim file structure if needed!   [https://battlepedia.org/ANIM](https://battlepedia.org/ANIM)
