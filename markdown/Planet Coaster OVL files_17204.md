## Post #1
- Username: GrandpaMizery
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 30, 2017 2:28 am
- Post datetime: 2017-10-29T18:58:13+00:00
- Post Title: Planet Coaster OVL files

I have recently found that by using CobraOverlayExtractor ([https://github.com/ESugata/CobraOverlayExtractor](https://github.com/ESugata/CobraOverlayExtractor)) I am able to get at the structure of the .ovl files. It produces 2 files:
1) First file is an XML file of files structure.
2) Second file contains the uncompressed data from the zlib portion of the .ovl file.

The XML file gives what I think is 1 or more directory names. Each directory contains a specified number of elements/( filenames??). They are also providing a <hash> value </hash>.

My question is: Is the hash value a reference to the elements location in the data file? And, can I use this knowledge to get at the elements.

I am in unfamiliar territory here and could use some help with this. I can provide more information on my findings if needed.
