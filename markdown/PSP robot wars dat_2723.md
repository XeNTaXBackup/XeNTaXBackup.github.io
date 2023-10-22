## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-07-25T14:59:04+00:00
- Post Title: PSP robot wars dat

I want to open this psp archive. It doesn't have any compression. Just two tables at the beginning of the archive. The first one should be general info.(filesize, start offset etc). And the second one is names table!

But I couldn't found out the format of the 1st table. please help!
[psp.dat.zip](https://xentaxbackup.github.io/file/1286_psp.dat.zip)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-25T22:43:06+00:00
- Post Title: PSP robot wars dat

Ok, I'm on it. Nearly got it sussed.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-26T10:37:28+00:00
- Post Title: PSP robot wars dat

Ok, I have 90% of the format complete I think. Will write a mexCom plugin. 

I've attached the table of contents of this archive (tab delimited text file). 
Also a shot from Hex Workshop bookmarks to show you the format. 

The general structure is : 

```
// Resource Information Table
// String Table
// Raw Data

```


Raw files are padded in blocks of 2048 bytes I assume. 

The last 6 entries in the bookmark shot comprise 1 Resource Information Table entry. 

Again, the full paths are not saved in the string table, just the single folders and files. Start with folder 0 and then work your way into subfolders, moving out of them as you go, until you're back at folder 0. 
If you stumble upon a subfolder, this has priority, so check that one first until there are no more files and folders in there, then move on with the original sorting.
[sorted.zip](https://xentaxbackup.github.io/file/1290_sorted.zip)

[pak_format.JPG](https://xentaxbackup.github.io/file/1289_pak_format.JPG)
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-07-26T14:03:03+00:00
- Post Title: PSP robot wars dat

Can't wait for the plugin! Because I have 6~8 archive files of this.

Thank you very much!
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-26T22:02:20+00:00
- Post Title: PSP robot wars dat

The plugin. Should work. They are for .DAT files right ? Just create a DAT folder in the Plugins folder and put the dll there. Then open an archive as a Robor Wars file.
[RobotWarsPSP.zip](https://xentaxbackup.github.io/file/1292_RobotWarsPSP.zip)
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-07-28T19:38:33+00:00
- Post Title: PSP robot wars dat

Mr.Mouse, the plugin works fine for half of the dat but run into problem with others due to a little different in the dat format. I had upload another sample for you. Could you support it as well!

Thanks
[fileset.dat.zip](https://xentaxbackup.github.io/file/1294_fileset.dat.zip)
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-29T20:19:55+00:00
- Post Title: PSP robot wars dat

Okay, this format I can handle via a MexScript. See below and attached .txt file to run in MultiEx Commander. Note that you will extract yet another bunch of files and archives that are undefined. The "filedat.dat" and ".bin" are added by the MexScript to the filenames. 

```
# By Mr.Mouse. Juli 2007
IDString 0 PIDX ;
ImpType Standard ;
Set S Long 32 ;
GoTo S 0 ;
Get STOff Long 0 ;
GoTo STOff 0 ;
Get AN String 0 ;
String AN += "_" ;
Set S Long 80 ;
GoTo S 0 ;
Get FileNum Long 0 ;
Get EntryStart Long 0 ;
Math S += EntryStart ;
GoTo S 0 ;
For T = 1 To FileNum ;
Get NOff Long 0 ;
SavePos B 0 ;
Math NOff += STOff ;
GoTo NOff 0 ;
Get FN String 0 ;
GoTo B 0 ;
Get U1 Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get U2 Long 0 ;
Set N String AN ;
String N += FN ;
String N += ".bin" ;
Log N FO FS FOO FSO ;
Next T ;

```

[mexscript_robotwars_ps_fileset.zip](https://xentaxbackup.github.io/file/1296_mexscript_robotwars_ps_fileset.zip)
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2007-07-30T09:19:55+00:00
- Post Title: PSP robot wars dat

Good job Mr.Mouse
