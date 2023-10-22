## Post #1
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-01-23T17:05:39+00:00
- Post Title: Assassins Creed Batching

I have been messing around with this title and I have found some things. I was wanting to process these assets outside of tools. Since the tools are done 1 by 1. So here is what I found.

[STEP 1]
Dump the .FORGE file with assassins_creed_raw.bms that will give you tons of .dat files.
If you run Delutto's tool you can process names of the files by game type.
[https://zenhax.com/viewtopic.php?t=9138](https://zenhax.com/viewtopic.php?t=9138)
Although it is not needed since I had someone write a "renamer" script provided in the archives. 
Now to make things easy i have a folder called "scripts" with both renamer.bms and assassins_creed_raw.bms inside along with quickbms_4gb_files.exe
If you click on the FORGER.bat it will process all .FORGE files in the folder.

[STEP 2]
Same goes for the RENAMER.bat it will scan recursively through the .dat files renaming them into the folder in which .bat is located. 
**NOTE**
I deleted all files 0kb-10kb due to how many there was. Maybe all text or information files/ materials. Not needed for this. 
Now that you have all your .dat's renamed to the correct files put them into a folder called DATA
Take this DATA folder and search with VGM toolbox this string
"68955D410000"
[](https://ibb.co/nzbgzVK)
This is put the output as .acvmesh 
Now drop DATA onto VGM to start extracting _CUT folders. These are all models /LOD's.
Take all the folders put into one so you have just .acvmesh's. 
[](https://ibb.co/3MRX6KK)
Open fmt_acVlh.py and change this part here from 

#handle = noesis.register("Assassin's Creed: Odyssey model", ".dat1") 
to
handle = noesis.register("Assassin's Creed: Odyssey model", ".acvmesh")

Then be sure to # out line 52 so its no longer reading .acvlh_1096652136. Or you can rename your meshes this in VGM Toolbox. Either way it works the same, I just named it this for size/ext.
If you choose to use the original name .acvlh_1096652136 no need to change script.
That script can be found here:
[viewtopic.php?f=16&t=21959](https://forum.xentax.com/viewtopic.php?f=16&t=21959)
Place script in python folder for Noesis and you can now load meshes.
[](https://ibb.co/vj6Y5js)

[Step 3]
[](https://imgbb.com/)
Textures are a bit more tricky but thanks to id-daemons rawtex tool I'm able to get something from them. 
Dumped the same way from the script you will see many textures. I searched for DIFFUSE NORMAL MASK EMISSIVE. Then placed all the files into corresponding folders.
After that I ran these .bat files I created after looking at some of the texture data. Now some might not work for all types. I think I will need to cut the files yet again now they are named so all the offsets start out the same. As of now they vary here and there. But still was able to get many to read correctly.
[](https://ibb.co/sHrnvhR)
A3874B1D00004000 = 4096
A3874B1D00002000 = 2048
A3874B1D00001000 = 1024
A3874B1D1A000800 = 512
A3874B1D00000400 = 256
A3874B1D1A000200 = 128
***NOTE***
[](https://imgbb.com/)
I did not include quick bms or the assassins_creed_raw.bms script they can both be found here:
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
Or rawtex by id-daemon that is found here:
[https://zenhax.com/viewtopic.php?t=7099](https://zenhax.com/viewtopic.php?t=7099)

Assassins Creed Odyssey, Valhalla and Origins are all able to be batched this way. I was wondering... If anyone would care to look into the other titles. I can post samples of the mesh data. I found it uses the same header just the scripts do not work for them. 
Unity
Rouge
Syndicate
Black Flag
[ACBatching.zip](https://xentaxbackup.github.io/file/21667_ACBatching.zip)
## Post #2
- Username: leckock
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 04, 2020 11:48 pm
- Post datetime: 2022-11-06T00:16:40+00:00
- Post Title: Assassins Creed Batching

Hello, thank you for writing this guide, it's very helpful but i'm little bit confuse, when i try to start to rename the .dat files the script doesn't change anything, any idea ? it's for AC Vallhalla
