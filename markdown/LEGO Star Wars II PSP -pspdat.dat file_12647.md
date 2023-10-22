## Post #1
- Username: SSSerek
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 21, 2014 3:33 am
- Post datetime: 2015-02-24T18:32:16+00:00
- Post Title: LEGO Star Wars II PSP -pspdat.dat file

Hi. I want to make Polish translation of LEGO SW II PSP, but I can't unpack it by aluigi's quickmbs script. Can someone look in this? Link to the file: [https://mega.co.nz/#!ztMlACwD!hFRHuhgyT ... fh-jjVsGYw](https://mega.co.nz/#!ztMlACwD!hFRHuhgyTzRlELywFHYyvej5tJtQ8be03fh-jjVsGYw) .
## Post #2
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-02-28T20:21:21+00:00
- Post Title: LEGO Star Wars II PSP -pspdat.dat file

This script extracts the files without any filename:

```

Get TableOffset Long 0;
GoTo TableOffset 0;

Get D1 Long 0;
Get NFiles Long 0;

For T = 1 To NFiles;

Get FileOffset Long 0;
Get UFileSize Long 0;
Get CFileSize Long 0;
Get D1 Long 0;

Log T FileOffset UFileSize 0 0;

Next T;

```


A table with the directory structure and file names is in the file, bu I don't think that I can do the extraction with MultiEx. If you want, i can try to develop a script to extract all the information from the archive.
## Post #3
- Username: ekanspt
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-02-28T23:58:21+00:00
- Post Title: LEGO Star Wars II PSP -pspdat.dat file

Hi there. I've been looking at this for the past two days, with a severe cold, and recorded some real-time footage of the analysis process. 
However, for the purpose of this Let's MultiEx video I choose just to summarize the results, as my voice was rather creaky in the other footage, cause of the cold. 

[https://www.youtube.com/watch?v=TLW6wgQTuds](https://www.youtube.com/watch?v=TLW6wgQTuds)


The script will give you a preliminary filename list to use as well, along with the folder they are in. 

```
SavePos TailOffOff 0 ;
Get TailOff Long 0 ;
SavePos TailSizeOff 0 ;
Get TailSize Long 0;
GoTo TailOff 0 ;
Get Minus Long 0 ;
Get FileNum Long 0 ;
Set Jump Long FileNum ;
Math Jump *= 16 ;
SavePos Jump2 0 ;
SavePos Table1 0 ;
Math Jump2 += Jump ;
GoTo Jump2 0 ;
Get DirNum Long 0 ;
Set Jump3 Long DirNum ;
Math Jump3 *= 8 ;
SavePos STable 0 ;
Math STable += Jump3 ;
Math STable += 4 ;
SavePos Jump2 0 ;
Math Jump2 += 8 ;
Set Folder String "" ;
Set Fol String "\" ;
Set T Long 0 ;
Do ; 
GoTo Jump2 0 ;
Get Type Int 0 ;
Get I2 Int 0 ;
Get STPos Long 0; 
SavePos Jump2 0;
If Type > 0 ;
Set Folder String "" ;
Set Jump3 Long STable ;
Math Jump3 += STPos ;
GoTo Jump3 0 ;
Get FN String 0 ;
String Folder += FN ;
String Folder += Fol ;
Else ;
Set Jump3 Long STable ;
Math Jump3 += STPos ;
GoTo Jump3 0 ;
Get FN String 0 ;
Set FileName String Folder ;
String FileName += FN ;
GoTo Table1 0 ;
Get FOffset Long 0 ;
Get FCSize Long 0 ;
Get FUCSize Long 0 ;
Get D1 Long 0 ;
SavePos Table1 0 ;
Log FileName FOffset FCSize 0 0 ;
Math T += 1; 
EndIf ; 
While T < FileNum ;

```


Next up is figuring out the complete order of folders from the root folder. Anyway, have fun, and until the next Let's MultiEx video! (see the playlist here: [https://www.youtube.com/playlist?list=P ... GrVNJ2kS2f](https://www.youtube.com/playlist?list=PLP26ZYnLb5EVqqBHDgltL6oGrVNJ2kS2f) )
## Post #4
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-01T00:37:43+00:00
- Post Title: LEGO Star Wars II PSP -pspdat.dat file

Hi Mr. Mouse,

So i think that I have a clue for figuring out the directories order. Actually I only extracted the files without any file name because I don't know how to code what I'm thinking in MEX script.

If you start from address 0x3497A804 and you read two bytes, you see 0x10, the end of ats folder (folder itself plus 15 files) and the second two bytes are 0 (probably related to root?). 

Skipping 15 entries (0x3497A884) you see the audio entry. First two bytes: 0x14, the end of the audio folder and Second two bytes: 0x01, the offset of the folder level (at the same level of ats folder, which is entry 1).

Skipping 2 entries, you see the _soundfx folder, first 2 bytes: 0x2D03, the folder ends at 813 and second two bytes 0x13, the folder is at the level of entry 19, that means, music.txt. And so on.

Here is a txt file with all file names so you can take a better look on what i'm saying.
[filenames.zip](https://xentaxbackup.github.io/file/8774_filenames.zip)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-03-01T10:52:42+00:00
- Post Title: LEGO Star Wars II PSP -pspdat.dat file

Hi, and thanks for the list. I discuss this also in the video I posted. 

The script above will enable this type of filenaming:



pspdat.png (39.64 KiB) Viewed 99 times
## Post #6
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-01T16:05:32+00:00
- Post Title: LEGO Star Wars II PSP -pspdat.dat file

Yes. As you say too in the video the "_soundfx" folder should be inside the "audio" folder and the "amidala" inside the "_soundfx" one. I think that the explanation that i give above is partially correct, but I can't code this in MEX, because I'm a total noob in MEX Script and the job is partially done by you. 

So if you want, try to code it in MEX, if not, I will make a simple program to test if my theory is right.
## Post #7
- Username: SSSerek
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 21, 2014 3:33 am
- Post datetime: 2015-03-04T16:04:21+00:00
- Post Title: LEGO Star Wars II PSP -pspdat.dat file

Big thanks for helping me. I've extracted all files and I will look into PC version for folders order. Can I, after translating the game, reimport translated files into the game?
