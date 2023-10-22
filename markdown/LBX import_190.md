## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-03-04T09:31:29+00:00
- Post Title: LBX import?

Hello,
Is it possible to enable import of files into LBX archive?
I'm a great fan of Master of Magic by Microprose...

Thanx for doing a good job for all of us  

PS:  That Yuri Gagarin's face on your avatar is cool
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-03-04T13:37:55+00:00
- Post Title: LBX import?

Well, you can utilize this script in Mex3Scriptor (start from within the program). Then save it as lbx.bms and Use Custom BMS On...

Select the created lbx.bms and then select an archive of your choice. 
This will probably let you import into it, but it is not flawless. 
The last file of each archive will be corrupted. So it isn't much use eh. 
Anyway, here's the script. And perhaps I will look into it some other time. 

ImpType SFileOff ;
Get FC Int 0 ;
Get D Int 0 ;
Get D Long 0 ;
SavePos TO 0 ;
For T = 1 to FC ;
GoTo TO 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos TO 0 ;
Get FS Long 0 ;
Math FS -= FO ;
Log "" FO FS FOO 0 ;
Next T ;
