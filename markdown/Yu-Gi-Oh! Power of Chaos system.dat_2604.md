## Post #1
- Username: jdmx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 03, 2007 11:17 pm
- Post datetime: 2007-05-03T17:53:30+00:00
- Post Title: Yu-Gi-Oh! Power of Chaos system.dat

I am trying to figure out how to decode the main system.dat file for the program so I can merge two files together due to an error if the 3 programs are installed and run in the wrong order.

With the help of this thread, I am able to decode the files so I now have access to the data.

[viewtopic.php?p=17538&highlight=#17538](http://forum.xentax.com/viewtopic.php?p=17538&highlight=#17538)

This has allowed me to see that although there are 3 programs, each expanding upon the last, the card list is identical for all 3.  Thus the file size for the system.dat never changes because there is no new data needed to be added from version to version.


The zip contains a few examples of the system file in various forms.  system1 and system2 are the before/after files after a game is play and one but without any settings changed.

This is a list of all of the bytes that are different and their positions.

00, A1, 9D
18, 24, AC
3C0, 05, 81
1317, 00, 40
131B, F3, 7F
132D, 0F, 49
132E, 3B, 3A
13C1, 87, D7
13C2, C7, 26
13C3, 08, 1D

system-orig and system-setting are the before and after effects of a settings change.

Again the byte changes.
00, D5, CD
02, 7D, 97
03, 55, 16
13, 00, 40
14, 36, 3E
16, 1A, 00
17, 01, 00
13C1, 17, 97
13C2, 0E, ED
13C3, 0C, 13

The first thing I looked for is some sort of counter that would indicate the victory or card total has increased by 1.  I also believe the cards won list starts are byte 1A and proceeds until byte 1316 with every after 09e0? being for future reference.


Without knowing the file structure, I am having a hard time trying to figure out how to merge the data.  Any failure in loading the file causes it to revert back to its original form when the program first starts.  I have a feeling that this file is encrypted in some way like the compression form the link above or the filenames in the other .dat files.

Does anyone know of a good method to find what the format is?
[system.zip](https://xentaxbackup.github.io/file/1145_system.zip)
