## Post #1
- Username: jackblack
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri May 20, 2011 7:56 am
- Post datetime: 2019-03-24T02:10:04+00:00
- Post Title: 3dmigoto model ripping

Hi, everybody, there is dx11 wrapper called 3dmigoto, among many other options it can dump index and vertex buffers as a text file. There is a blender importer but it says "Only draw calls using single vertex buffer and single index buffer are supported". Every game I've tried to rip models from apparently uses more. Is there any way to update blender importer or maybe make obj converter or noesis plugin? By the way, it says it rips more stuff than ninja ripper.
[ib and vb example and importer.rar](https://xentaxbackup.github.io/file/15954_ib and vb example and importer.rar)
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2019-03-26T03:17:46+00:00
- Post Title: 3dmigoto model ripping

I can rip rigged models from certain games like doa6 and doaxv. I hope someone can make a tutorial about how to rip models, should be useful.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-27T20:59:24+00:00
- Post Title: 3dmigoto model ripping

> Reply from jackblack ↑Sun Mar 24, 2019 10:10 am at Sun Mar 24, 2019 10:10 am
>
> Is there any way to update blender importerAssumed you don't need tangents and binormals simply delete this from the vb0 txt file:

```
  SemanticName: TANGENT
  SemanticIndex: 0
  Format: R16G16B16A16_SNORM
  InputSlot: 1
  AlignedByteOffset: 0
  InputSlotClass: per-vertex
  InstanceDataStepRate: 0
element[4]:
  SemanticName: BINORMAL
  SemanticIndex: 0
  Format: R16G16B16A16_SNORM
  InputSlot: 1
  AlignedByteOffset: 8
  InputSlotClass: per-vertex
  InstanceDataStepRate: 0

```
 remove the vb1 txt file from the folder, import the ib txt file and you're done. (Well, nearly, you need to scale down the whole thing to make it visible?)



IB_VB.jpg (191.72 KiB) Viewed 277 times
## Post #4
- Username: eArmada8
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 26, 2022 2:13 am
- Post datetime: 2022-04-25T18:24:22+00:00
- Post Title: 3dmigoto model ripping

Sorry to bring up an old topic, but I ran into the same issue and was able to work around it.  I wrote a pair of python scripts that 1. merge the vertex buffers into a single buffer compatible with the import plugin, and 2. split them back up for re-injection into the game (assuming you want to do that).  I'm posting here because this thread comes up when I search for the error message, so hopefully this helps someone at some point!

[https://github.com/eArmada8/vbuffer_mer ... t/releases](https://github.com/eArmada8/vbuffer_merge_split/releases)

I wrote this using trails of cold steel 4, and I didn't find any other games using multiple vertex buffers so it's untested with other games.  I'm not a programmer by trade, and I hope others can take these scripts and make them better.
