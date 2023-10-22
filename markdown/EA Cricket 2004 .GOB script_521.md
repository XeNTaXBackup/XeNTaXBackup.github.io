## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-30T08:37:06+00:00
- Post Title: EA Cricket 2004 *.GOB script

Compile this in MexScriptor to support *.GOB files from EA Cricket 2004   Thanks to Samric! 
Note: copy it to notepad.exe first then remove the extra spaces at the end of each line. 
ImpType Standard ;
GoTo EOF 0 ;
SavePos END 0 ;
Math END -= 2047 ;
GoTo END 0 ;
Get DUM Long 0 ;
Get FNU Long 0 ;
Get DJ Long 0 ;
Math END -= DJ ;
Set DJJ Long 24 ;
Math DJJ *= FNU ;
Math END -= DJJ ;
GoTo END 0 ;
For T = 1 to FNU ;
GetDString DUMM 16 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log "" FO FS FOO FSO ;
Next T ;
