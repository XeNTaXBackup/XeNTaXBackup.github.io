## Post #1
- Username: Just
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 22, 2009 3:38 pm
- Post datetime: 2009-02-23T00:05:52+00:00
- Post Title: Problem with BMS script or Game Extractor

I've written a BMS script for the Empire: Total War demo, and I've tried to to use it with Game Extractor (because MultiEx doesn't allow the use of my own scripts).

However, when I try to use the script it doesn't extract any files (even though the files are listed with the right name and size in the program and I get a message saying the files have been extracted successfully). The error log shows the following message:

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
org.watto.manipulator.FileBuffer.close(FileBuffer.java:184)
org.watto.manipulator.FileManipulator.close(FileManipulator.java:280)
Resource.extract(Resource.java:211)
Task_ExportFiles.redo(Task_ExportFiles.java:103)
Task_ExportFiles.run(Task_ExportFiles.java:128)
java.lang.Thread.run(Unknown Source)
-======================-
ERROR: java.lang.NullPointerException
java.lang.NullPointerException
org.watto.manipulator.FileBuffer.close(FileBuffer.java:187)
org.watto.manipulator.FileManipulator.close(FileManipulator.java:280)
Resource.extract(Resource.java:211)
Task_ExportFiles.redo(Task_ExportFiles.java:103)
Task_ExportFiles.run(Task_ExportFiles.java:128)
java.lang.Thread.run(Unknown Source)
-======================-
```


The script I wrote is:
```
ImpType SFileSize ;
IDString 0 PFH0 ;
GoTo 16 0 ;
Get FileCount Long 0 ;
Get DataOffset Long 0 ;
Math DataOffset += 24 ;
For n = 1 To FileCount ;
SavePos FileSizeOffset 0 ;
Get FileSize Long 0 ;
Get FileName String 0 ;
Log FileName DataOffset FileSize 0 FileSizeOffset ;
Math DataOffset += FileSize ;
Next n ;
</bms>
```


I run Game Extractor as administrator on Windows Vista.

Does anyone have any idea what might be wrong with my script or the way I am using Game Extractor?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-23T18:53:27+00:00
- Post Title: Problem with BMS script or Game Extractor

First of all, MultiEx will allow you to use your own scripts. 

Second, the script you pasted is not correct. You do not need to use it like it is used at the wiki (it was meant for automatic processing, which has been disabled and will in the future be removed.). 

So the header and tail tags can go. 

```
IDString 0 PFH0 ;
GoTo 16 0 ;
Get FileCount Long 0 ;
Get DataOffset Long 0 ;
Math DataOffset += 24 ;
For n = 1 To FileCount ;
SavePos FileSizeOffset 0 ;
Get FileSize Long 0 ;
Get FileName String 0 ;
Log FileName DataOffset FileSize 0 FileSizeOffset ;
Math DataOffset += FileSize ;
Next n ;

```


Now you can try again.
## Post #3
- Username: Just
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 22, 2009 3:38 pm
- Post datetime: 2009-02-25T06:16:22+00:00
- Post Title: Problem with BMS script or Game Extractor

MultiEx asks me for a registration code when I try to load a BMS script  

I managed to get it to work in Game Extractor, instead of right clicking and selecting extract I used the extract option in the file menu, didn't even need to remove the tags.
