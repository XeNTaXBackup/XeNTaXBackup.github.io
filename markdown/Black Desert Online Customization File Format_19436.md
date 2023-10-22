## Post #1
- Username: akyryz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 28, 2010 10:18 am
- Post datetime: 2019-02-02T12:08:43+00:00
- Post Title: Black Desert Online Customization File Format

I believe the black desert online customization file is compressed since multiple parts share the same address and I can't figure out how.

Reference thread: [viewtopic.php?f=16&t=11849](http://forum.xentax.com/viewtopic.php?f=16&t=11849)

I think the game slides should be a Vector3 or CompressedVector3 for X, Y and Z slides but if you change the value too much at that address it change other parts too.
The address changes 8 bytes and the more strange thing is the other part affected changes the next 8 bytes ahead too and in turn changes another part, the cycle repeats.

C7 4E 88 73 8B 51 4C 88 00 FB 28 48 EA F2 9E 19 - Original Data
DF EF 87 D1 FB B6 5D 8C 00 FB 28 48 EA F2 9E 19 - Part 1 Changed Only
98 FB 7F 6E 81 04 1E 84 FC B2 02 FA 86 CB 60 E5 - Part 2 Changed Only

The default value for the 8 bytes seems to be: 41 EF 58 6A F7 CA 4F 0E
Starting from address 92 you can set to 00 and the file will load with defaults.
## Post #2
- Username: Bahamut082
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 07, 2015 6:40 pm
- Post datetime: 2019-12-27T08:33:01+00:00
- Post Title: Black Desert Online Customization File Format

Hi, 

I'm interested in this topic too, I searched a lot online but didn't find any tool to decrypt/decompress the customization file.
All i know is, it's a text file containing a long list of the bones values (scale, position, rotation) so in order to recreate your custom char 
in blender or any other 3d editor you need those values else any char exctracted will have the default appareance.

The top would be a blender/3dsmax script that decompress/decrypt the file and append those values directly on the model,
but anything else that would make those files at least readable would be enough.

Is there any update about this?

Thanks in advance.
