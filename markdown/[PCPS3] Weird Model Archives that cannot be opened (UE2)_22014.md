## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-04-15T19:22:36+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

Hello, everyone! I managed to rip some weird files from Splinter Cell Double Agent on the PS3 and PC, more specifically, Spies vs Mercs.
PS3
There are two file types I can make out: .ULL and .ULLskin, I was trying to get the multiplayer models from the game but I can't figure out how to export the meshes or textures.

[Here ](https://mega.nz/file/4UwyQCDZ#5DgWWeirCo13sMPraf2ynuCj0MgvL62NI3fU7GlwuTA) are some PS3 sample files.
PC
Files are supposedly stored in the classic .UKX unreal archives however Gildor has no support for this and it crashes instantly. 

[Here ](https://mega.nz/file/cMYl2AIA#Sgw8OQjjlXk72Ms57Wzql1K2WoYxD3VAN4tIr6uVW30) are some PC sample files.

Really want to get those awesome spy models..
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-16T09:57:18+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

> Reply from Pepsee ↑Thu Apr 16, 2020 3:22 am at Thu Apr 16, 2020 3:22 am
>
> Files are supposedly stored in the classic .UKX unreal archivesWhat exactly does that mean? Like "Unreal Tournament 4"?

(unpacker extract.exe: "ERROR: Serialized FString is not null-terminated")
## Post #3
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-04-16T10:47:27+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

> Reply from shakotay2 ↑Thu Apr 16, 2020 5:57 pm at Thu Apr 16, 2020 5:57 pm
>
> 
Pepsee wrote: ↑Thu Apr 16, 2020 3:22 amFiles are supposedly stored in the classic .UKX unreal archives What exactly does that mean? Like "Unreal Tournament 4"?

(unpacker extract.exe: "ERROR: Serialized FString is not null-terminated")

.UKX was used in Splinter Cell 1 and 2 (I think it's the same in Unreal Tournament 2004, but I'm not really sure, all Splinter Cells were on Unreal Engine 2 and heavily modified versions of it), however from Splinter Cell 3 upwards, they're still .UKX but with a different header I assume.

[Here ](https://mega.nz/file/xY41UDSI#-Hi-GtkdesHEJ4doc_qm7pKBhV5_Nv8gsP47CaeqAYM) are some samples from Splinter Cell 1.
I might be able to extract the .UKX files with Drago's Game Extractor, but I only get .SkeletalMesh and .StaticMesh however, I still can't import them in Blender or Noesis with Unreal Engine plugins..
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-04-18T20:36:10+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

*bump* Has anyone managed to get a lead? I only found a way to hex edit the save file in order to get access to a specific skin,but that's about it...
I managed to get the files extracted with Dragon UnPACKer.
The animations are stored in .MeshAnimation and models in .SkeletalMesh, however I can't open them, they're the same output files as Chaos Theory and Versus models...

[Here ](https://mega.nz/file/AJRW1AYC#FEB5nnWOwgvlDsmfqXqSuQ0V97MRWsnuwmv3KtGq9pc) are the Double Agent output files.

[Here ](https://mega.nz/file/BVwQEIKD#_YEazQ97NeEA9mA_c8JWjZY2odGUhiKeXQYqFRztUQA) are the Chaos Theory output files.

[Here ](https://mega.nz/file/wVwHjDbK#Q4j9u0tc7jgPhfp7YPCOYfY9PN-uym0YtXE4KoTKnhw) are the Versus output files.

This is as far as I can get with archive decompression/decompiling. I'm pretty much stuck here, I have tried renaming them to .psk but it doesn't work sadly, lol (if only it were that easy).

Neither Noesis, 3ds Max nor Blender plugins can open them.. I don't know what else to do at this point..
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-18T23:06:46+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

MegaPhone_NPC-StaticMesh.png (100.44 KiB) Viewed 106 times
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-04-18T23:09:19+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

Shako, you always surprise me with how quick you can cook up a model in Hex2Obj haha. If only I had any vague clues of how to use it properly or even know Hexadecimal, I sadly can only rely on scripts, plugins and other such importers... Great work as usual though!  

P.S: Do the files share any similarities? Or does each one have a different version of the .SkeletalMesh/.StaticMesh filetypes?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-19T09:00:04+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

> Reply from Pepsee ↑Sun Apr 19, 2020 7:09 am at Sun Apr 19, 2020 7:09 am
>
> P.S: Do the files share any similarities? Or does each one have a different version of the .SkeletalMesh/.StaticMesh filetypes?Different versions? Dunno what you mean exactly.

Got a point cloud from the SkeletalMesh and a head:
.



NPCA.png (90.25 KiB) Viewed 90 times
## Post #8
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-04-19T09:56:31+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

> Reply from shakotay2 ↑Sun Apr 19, 2020 5:00 pm at Sun Apr 19, 2020 5:00 pm
>
> 
Pepsee wrote: ↑Sun Apr 19, 2020 7:09 amP.S: Do the files share any similarities? Or does each one have a different version of the .SkeletalMesh/.StaticMesh filetypes?
Different versions? Dunno what you mean exactly.

Got a point cloud from the SkeletalMesh and a head:
.
NPCA.png

I meant if the .SkeletalMesh from Double Agent is the exact same as the .SkeletalMesh from Chaos Theory and Versus, or if any of them are structurally identical.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-19T10:57:04+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

> Reply from Pepsee ↑Sun Apr 19, 2020 5:56 pm at Sun Apr 19, 2020 5:56 pm
>
> I meant if the .SkeletalMesh from Double Agent is the exact same as the .SkeletalMesh from Chaos Theory and Versus, or if any of them are structurally identical.Supposedly not. Checked SPY_01_SC4 only and it looks different (FVFsize=38, still an unknown problem here):
.



SPY_01_SC4-SkeletalMesh.png (69.79 KiB) Viewed 85 times

(3 parts exploded)
## Post #10
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-04-19T11:24:21+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

> Reply from shakotay2 ↑Sun Apr 19, 2020 6:57 pm at Sun Apr 19, 2020 6:57 pm
>
> 
Pepsee wrote: ↑Sun Apr 19, 2020 5:56 pmI meant if the .SkeletalMesh from Double Agent is the exact same as the .SkeletalMesh from Chaos Theory and Versus, or if any of them are structurally identical.Supposedly not. Checked SPY_01_SC4 only and it looks different (FVFsize=38, still an unknown problem here):
.
SPY_01_SC4-SkeletalMesh.png(3 parts exploded)

Oh boy, just what I feared.. This really complicates things.
## Post #11
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-04-21T08:32:08+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

Is it possible (and reasonable) for a Noesis import/export script for these formats? (Rigging would be bliss, but I won't complain even with obj's)
 It would be of immense help in the projects I'm working on and I'd appreciate it from the bottom of my heart.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-21T09:31:20+00:00
- Post Title: [PC/PS3] Weird Model Archives that cannot be opened (UE2)

> Reply from Pepsee ↑Tue Apr 21, 2020 4:32 pm at Tue Apr 21, 2020 4:32 pm
>
> 
Is it possible (and reasonable) for a Noesis import/export script for these formats?Someone needs to take a closer look at the format(s) data before. (Export script are very rare, one of a thousand formats, I guess.  )
