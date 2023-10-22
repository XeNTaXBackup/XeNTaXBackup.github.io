## Post #1
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-02-16T09:42:50+00:00
- Post Title: Extract scripts from Adventure Game Studio's CRM files

Hello all,

I was curious if there is a way to extract the contents of a compiled CRM file from Adventure Game Studio.
First of all, there is this great tool called GoBread, created by asmxtx.
GoBread successfully extracts the contents of AGS VOX/EXE packed files, some of those extracted files are .crm files. 
Those .crm files are room files, they establish a scene where the player wanders, including graphics. 
Then there are the .asc files (not included in the compiled game), these files contain plain-text scripting that creates animations, interactions, etc inside the rooms/scenes. 

When an AGS game is compiled, the .asc contents are embedded inside the .crm files that GoBread can extract. 
The problem is that the scripting content isn't plain-text anymore once embedded inside the .crm room files (duh!). 
Is it possible to reverse these scripts from the compiled versions? 
I attach a zip with 2 files for you to look at, one compiled .crm and one plain .asc. 
I imagine such a task must be very demanding and unfortunately I don't think I got the skills, I am able to do some basic analysis, debugging and disassembling but that's about it. 

Thank you for your thoughts.
[Room1_ASC-CRM.zip](https://xentaxbackup.github.io/file/5075_Room1_ASC-CRM.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-02-23T23:25:00+00:00
- Post Title: Extract scripts from Adventure Game Studio's CRM files

it does look like your script has been compiled down to bytecode which means you will never get a full conversion back to your sourcecode. and looking at the complexity of the asc language from your sample, it would indeed be very demanding to reverse it back into a human-readable state.

not for me
## Post #3
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-02-24T00:35:21+00:00
- Post Title: Extract scripts from Adventure Game Studio's CRM files

> Reply from WRS
>
> it does look like your script has been compiled down to bytecode which means you will never get a full conversion back to your sourcecode. and looking at the complexity of the asc language from your sample, it would indeed be very demanding to reverse it back into a human-readable state.

not for me
Thank you for your input, much appreciated.
