## Post #1
- Username: Arcalane
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 11, 2009 10:01 pm
- Post datetime: 2009-01-12T01:34:21+00:00
- Post Title: Requesting Assistance w/ Hostile Waters mbx archives

I was poking around on the net, looking for ways to extract the voice-overs from Hostile Waters' mbx files, but MultiEx Commander can't read them*, and Game Extractor is outputting tons of errors† into the logs that just go on ad-infinitum. Additionally when I did manage to extract audio from one of the mng files, whilst they claimed to be .wav they were unusuable in Winamp and Audacity refuses to have anything to do with them unless they're loaded as raw data. If necessary I can upload one of them. They were extracted using MultiEx Commander if it makes any difference.

Ed: I fixed those sound problems, but those aren't what I want. I need voice overs, not game sound effects!

I really want to get my hands on these voice overs, so any help would be appreciated. I already saw the older thread [here](http://forum.xentax.com/viewtopic.php?f=10&t=1242) but it hasn't been of much assistance to me so far. I made sure my java stuff is up to date, so I don't think that's the cause of the problem.

*

This is the most confounding error. I get the feeling that I could probably pull this off if it weren't for this.

†

```
java.lang.NullPointerException
org.watto.manipulator.FileBuffer.makeDirectory(FileBuffer.java:454)
Task_ExportFiles.redo(Task_ExportFiles.java:100)
Task_ExportFiles.run(Task_ExportFiles.java:128)
java.lang.Thread.run(Unknown Source)
-======================-
ERROR: java.io.FileNotFoundException:  (The system cannot find the path specified)
java.io.FileNotFoundException:  (The system cannot find the path specified)
java.io.RandomAccessFile.open(Native Method)
java.io.RandomAccessFile.<init>(Unknown Source)
org.watto.manipulator.FileBuffer.<init>(FileBuffer.java:78)
org.watto.manipulator.FileManipulator.<init>(FileManipulator.java:170)
Resource.extract(Resource.java:208)
Task_ExportFiles.redo(Task_ExportFiles.java:103)
Task_ExportFiles.run(Task_ExportFiles.java:128)
java.lang.Thread.run(Unknown Source)
-======================-
ERROR: java.lang.NullPointerException
java.lang.NullPointerException
org.watto.manipulator.FileBuffer.forceWrite(FileBuffer.java:278)
org.watto.manipulator.FileBuffer.checkWrite(FileBuffer.java:165)
org.watto.manipulator.FileBuffer.write(FileBuffer.java:1030)
org.watto.manipulator.FileManipulator.write(FileManipulator.java:1119)
org.watto.manipulator.FileManipulator.writeByte(FileManipulator.java:1146)
org.watto.manipulator.FileManipulator.write(FileManipulator.java:1246)
ExporterPlugin.extract(ExporterPlugin.java:51)
Resource.extract(Resource.java:230)
Resource.extract(Resource.java:210)
Task_ExportFiles.redo(Task_ExportFiles.java:103)
Task_ExportFiles.run(Task_ExportFiles.java:128)
java.lang.Thread.run(Unknown Source)
```

The last block just repeats for every file in the archive, so I only posted this excerpt.
## Post #2
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-01-21T21:00:36+00:00
- Post Title: Requesting Assistance w/ Hostile Waters mbx archives

Just look for this link:
[viewtopic.php?f=10&t=3081](http://forum.xentax.com/viewtopic.php?f=10&t=3081)
I have written an extractor for the .MNG-format a long time ago. Just download the latest version.
Edit: The .MBX-files seem to contain only sounds with special compiled data. To recompile these files it is needed to create a special compiler...
## Post #3
- Username: Arcalane
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 11, 2009 10:01 pm
- Post datetime: 2009-01-21T21:11:06+00:00
- Post Title: Requesting Assistance w/ Hostile Waters mbx archives

I have no problem working with/extracting files from the MNG 'archives'. The issue is the MBX files which nothing will read properly right now.
## Post #4
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-01-21T21:29:59+00:00
- Post Title: Requesting Assistance w/ Hostile Waters mbx archives

The problem is: The sound-data is stored in an MBX-file and the associated indexes are stored in a corresponding DAT-file. There are no file-names stored there, but only "hints", so it is difficult to make "links" between these two corresponding files.

Edit:

The MBX-files are PCM wave data files actually and have these formats:

PCM, unsigned 8bit, 11025Hz, mono;
PCM, signed 16bit, 22050Hz, mono/stereo

The DAT-files hold offsets and lengths respectively.

(I used GOLDWAVE to find that out)
