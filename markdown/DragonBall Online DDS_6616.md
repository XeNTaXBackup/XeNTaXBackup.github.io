## Post #1
- Username: DJRehab
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 15, 2011 5:18 am
- Post datetime: 2011-05-14T21:25:06+00:00
- Post Title: DragonBall Online DDS

The game I'm working with has .DDS files packed in files that dont come with header, filename, or offset position (because this data is stored in a seperate encrypted file)... basically i want a push in the right direction towards a script that will search the file for "44 44 53 20 7C" and copy this data (starting with the original 0x44 up until the beginning of the following search for "44 44 53 20 7C"

this is the DDS file format header, and the files are in no way encrypted i can rip them manually with a hex editor no problem.

EXAMPLE:
  44 44 53 20 7C ......... 44 44 53 20 7C

I would want to extract "44 44 53 20 7C ........." as "0.dds" and then start with the following DDS header to the one after this and save as "1.dds" etc

any suggestions?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-14T21:32:04+00:00
- Post Title: DragonBall Online DDS

post some samples?
## Post #3
- Username: DJRehab
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 15, 2011 5:18 am
- Post datetime: 2011-05-14T21:35:42+00:00
- Post Title: DragonBall Online DDS

they are copywritten....but here i will make a mock example


Say this was the hex for the package file:
44 44 53 20 7C 00 21 32 42 32 54 A2 CF 44 44 53 20 7C 73 82 91 55 AB


Heres hex with signatures in [ ]
[44 44 53 20] 7C 00 21 32 42 32 54 A2 CF [44 44 53 20] 7C 73 82 91 55 AB

Heres hex of the files it would make (seperated in brackets)
[44 44 53 20 7C 00 21 32 42 32 54 A2 CF] 
[44 44 53 20 7C 73 82 91 55 AB]

understand?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-14T21:36:55+00:00
- Post Title: DragonBall Online DDS

what is the game then without files no one will help you.
## Post #5
- Username: DJRehab
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 15, 2011 5:18 am
- Post datetime: 2011-05-14T22:22:24+00:00
- Post Title: DragonBall Online DDS

Here is the .pak file

Its a small one and only contains 2 DDS image files (note that the name and file structure, NOR the size of the dds file are in the files!!)

I need it to search for the DDS signature to find the offsets and math subtract it from the next offset to get the actual file length 

Note that in the example DDS File 1 starts at offset 0x00 (THERE ARE NO HEADERS AT ALL!)

DDS file 2 starts offset 0x155F0 (found this in hex editor by searching...dont want to do this with packages containing hundreds/thousands of DDS files)

EDIT - When I manually split this by using hex editor into two .dds files split at that offset...the DDS images are perfect and in-tact....any help would much be appreciated, I'm wanting MultiEx script if u need to know what language 
[example.zip](https://xentaxbackup.github.io/file/4241_example.zip)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-14T22:28:53+00:00
- Post Title: DragonBall Online DDS

I can help but i need to know the name of the game first.
## Post #7
- Username: DJRehab
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 15, 2011 5:18 am
- Post datetime: 2011-05-14T22:31:37+00:00
- Post Title: DragonBall Online DDS

Dragonball Online (its korean we are working on some translation patching)
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-14T22:33:25+00:00
- Post Title: DragonBall Online DDS

just use this
[http://www.jaedernaub.com/](http://www.jaedernaub.com/)
## Post #9
- Username: DJRehab
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 15, 2011 5:18 am
- Post datetime: 2011-05-14T22:49:25+00:00
- Post Title: DragonBall Online DDS

very nice tool 

does this extract 3D as well? sorry if this is offtopic but possibly terrains or model files as well?
