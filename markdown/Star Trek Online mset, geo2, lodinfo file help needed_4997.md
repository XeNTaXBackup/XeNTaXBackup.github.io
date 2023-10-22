## Post #1
- Username: pokute
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 09, 2010 5:58 pm
- Post datetime: 2010-09-09T10:18:18+00:00
- Post Title: Star Trek Online mset, geo2, lodinfo file help needed

I've been chipping away at this supposed character/object model format used in Star Trek Online (made by the same company using the same base engine as Champion Online).  These files have the .mset extension.  The mset file seems to be a container file including packing lists and offset/size information for internal chunks.  

I've managed to extract the two chunks present in the file F_Belt_Metalbikinibottom_Orion_01.mset, but this is where I'm stuck.  I've included everything in the zip file, including a gif showing highlighted hexdump of the offset/sizes.

F_Belt_Metalbikinibottom_Orion_01.chunk1 is supposed to be of the .Geo2 file type.
F_Belt_Metalbikinibottom_Orion_01.chunk2 is supposed to be of the .Lodinfo file type.

I'm guessing they contain geometry and level of detail data respectively, but I have no idea how to deal with either of these file types, nor can I tell if the chunks are in usable raw format or under some sort of compression or encryption (It's unlikely but the appearance of another size descriptor at the beginning and the "Default" at the end of each chunk makes me wonder if there's another layer of processing to be done).  

Hopefully someone here knows what to do next!
[STO mset WIP.zip](https://xentaxbackup.github.io/file/3416_STO mset WIP.zip)
## Post #2
- Username: pokute
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 09, 2010 5:58 pm
- Post datetime: 2010-09-11T18:44:48+00:00
- Post Title: Star Trek Online mset, geo2, lodinfo file help needed

I see it's been downloaded a few times.  Anyone have anything to add?  Or is it hopeless?
## Post #3
- Username: suricata
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 18, 2011 10:59 pm
- Post datetime: 2011-06-18T15:06:16+00:00
- Post Title: Star Trek Online mset, geo2, lodinfo file help needed

Apologies for the necro, but this thread is asking the exact same thing I would like to know.

I have the MSET files and I can see in the Hexidecimal editor that there are geo2 and lodinfo files in there, how do I extract them though? Are there any specific programs and scripts out there now that do this?

Also, what file format is .geo2? I've heard of lodinfo before (used in 3d for scaling and texture co-ordinates), but i can't find anything about geo2 files. any help regarding this would be much appriciated!

I've attached a file as well, so peopel can have a peak at it.
[Geo_Hull_Tahoe.zip](https://xentaxbackup.github.io/file/4350_Geo_Hull_Tahoe.zip)
## Post #4
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-07-04T17:26:10+00:00
- Post Title: Star Trek Online mset, geo2, lodinfo file help needed

Sorry for another Necro post but, if from what your saying is that the .mset file is just an archiving format, then there may be a way to get files out of that header, so that we can then view the geometry itself, im going to make a new thread on this and ask around to see if anyone who knows how to reverse engineer file formats can help out.
