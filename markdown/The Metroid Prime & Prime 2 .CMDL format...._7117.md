## Post #1
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2011-08-05T01:54:44+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

im wanting to try and figure out the format and make a program which will enable me to view these files (compressed or uncompressed)
i will post a .cmdl file from both prime 1 and prime 2.

i have found that the prime 1 CMDL files start with the following Hexadecimal sequence: "DE AD BA BE" and the prime 2 CMDL files are compressed.

this can be done because someone over on the emutalk forums has achieved this, but source material is VERY limited.
I myself have a vry limited experience with programming but im hoping someone can help me out with this.

attached in a zip archive are an example of a prime 1 CMDL file and a prime 2 one.
1_1dd9e368.CMDL - prime 1
1_1ab696a1.CMDL - prime 2

Someone PLEASE get back to me on this ASAP!
[CMDL.zip](https://xentaxbackup.github.io/file/4578_CMDL.zip)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-05T02:10:25+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

prime 2 is compressed with zlib just use offzip to extract it.
prime 1 is a weird one i have one compression in quickbms that looks very close but i am not sure its right.

please post an original pack file also that might fix the problem i am having with prime 1.
## Post #3
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2011-08-05T02:13:46+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

you dont need the .pak files the CMDL files ARE the models, thats the format im aiming to crack, and seeing as each CMDL points to it associated TXTR files, i just need to be able to view and export the models and textures.

There is a program called mpxviewer, which has a source SVN download which has ALOT of usefull code.
## Post #4
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-08-07T15:48:12+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

The mpxviewer code will be cleaned up eventually.  Will probably also be converting it to a Noesis plugin before that point though.

Just made a few new finding in that regard, and hope to apply them.  Once i have a better debugging option than Dolphin (or can get it to stop where i told it to again...heh) i should hopefully be able to decipher more.

But it really all comes down to seeing if i can make time for getting back to investigating things again.

```
	struct CMDL_HEADER
	{
		// 0x00
		uint32 fileID <format = hex>;
		uint32 fileVersion; // MP1 = 2, MP2 = 4, MP3 = 5
		uint32 fileFormat; // seems to specify data format and layout of file - when 5 (MP3 = 1) normals are floats, when 6 (MP3 = 2) normals are signed short, when 0 normals are float and empty section is omitted
		float3 boundingBox[2];
		uint32 sectionCount; // includes header count
		uint32 headerCount; // number of header sections
		uint32 sectionSizes[sectionCount] <format = hex>;
	} fileHeader;

```


Following this, are 'sectionCount' sections of the size in 'sectionSizes'.  The first 'headerCount' number of sections contain texture, material, and other geometry/object information.

The sections after the header information contain the base geometric information, vertices, normals, texture coordinates, etc. as well as information on the object data sections, which are then followed by indexing data in the standarg gamecube/wii format based on information located in the material header sections.

The compressions used are LZO and zlib.  mpakdump and mdecomp support decompressing them both, and should be simple enough to do with quickbms as well if needed.
## Post #5
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2011-08-24T23:57:27+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

MAN THIS IS CONFUSING!
ok so ive been looking through MPxViewers code, and ive seen how it decompresses the files for viewing in the program, now IF i could edit the source code and recompile (<-which never works in C#,C or C++, idk why) i may be able to get MPxViewer with an exporter and be able to export the models withought texture screwups etc...

but since i can hardly code anything, im gonna need help, and ALOT of it....
## Post #6
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2011-09-10T21:59:48+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

well im stumped, i tried a very weird thing in 3ds max and got 1 tri out of a CMDL file from prime 2 which was the dark suit....but then it caused my pc to bluescreen, so i was wondering if anyone else has made any progress on this.
## Post #7
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2011-11-04T17:56:14+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

well ive given up trying to use the source code to make a decompressore and converter, i guess ill leave that to revalation, which by the way, id like to hear from on this subject of exporting them.
## Post #8
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2012-02-19T22:00:32+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

I can't even get the MPXViewer to load up the models even though I've extracted from every pak file, gives me an error about an texture reference that isn't there, but this happens with every model though. But it could be because I'm using Metroid Prime Trilogy?
## Post #9
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2012-03-09T02:30:31+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

I have a question. Does anyone know how to decompress the CMDL files from Metroid Prime 3? I'm testing or trying to in the MPXViewer to see if it will even load which it does not. Could it be because I'm using Metroid Prime Trilogy instead of the GC/Wii Version that it should normally be?

Only reason I'm asking, is since I want to use what was done with the MPXViewer but put it into a Maxscript. I just need to test out Prime 3 models so I can have it all sorted out. Since I tried using Mdecomp.exe which didn't do anything to it. So I'm wondering if anyone possibly revalation may know about going around doing it?

Edit: Also since this is Retro Studios who did this game they also worked on Donkey Kong Country Returns which also uses CMDL as well seems like a different compression probably some more to it as well.
[1_7c3b28a5848f77e.zip](https://xentaxbackup.github.io/file/5169_1_7c3b28a5848f77e.zip)
## Post #10
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2012-03-10T09:16:13+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

Here is the model sample for DKCR.
[1_b6f701783fca5df.zip](https://xentaxbackup.github.io/file/5175_1_b6f701783fca5df.zip)
## Post #11
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2012-03-21T00:35:26+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

Been busy.  Will definitely be getting back to this format as well when i get the chance.  As far as exporting them, it is no harder than any of the other formats that can be viewed, just need port the code into a framework that has conversion support.
## Post #12
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-04-08T14:37:27+00:00
- Post Title: The Metroid Prime & Prime 2 .CMDL format....

Thats excelent to hear revelation, i hope that we will have a new extraction tool for prime and prime 2 in the near future  (which also doesnt make the textures in the previes quite so dark)

Good Luck!
