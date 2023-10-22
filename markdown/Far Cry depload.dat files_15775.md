## Post #1
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-22T22:10:10+00:00
- Post Title: Far Cry depload.dat files

I suspect the Far Cry games preload files/resources in memory based on entries in a world's binary depload.dat file. I would very much like to know what's defined in the ige_map_depload.dat file used by Custom Maps created for the games.

Now, unpacking Far Cry dat/fats with the Dunia Tools/[daemon's Far Cry Primal extractor](http://forum.xentax.com/viewtopic.php?f=16&t=15735) sometimes yields a depload in both *.DAT (binary) and *.XML (readable) format. I'm assuming the DAT's are compressed versions of the XML's, but am unable to decompress it. I know Far Cry uses LZO-X1 for some files, I'm not sure if that's the case here. lzop can't seem to unpack the file, and that's the only option I have for LZO so far. 

Would anyone be able to shed some light on this? You can find the example files at [http://steve.farcry.eu/files/FarCry4_deploads.zip](http://steve.farcry.eu/files/FarCry4_deploads.zip)
## Post #2
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-05-10T23:36:08+00:00
- Post Title: Far Cry depload.dat files

hmm, nowadays I think it probably isn't possible to add fcc_main assets to the multicommon 'custom map' experience. So never mind the depload I guess...
