## Post #1
- Username: ThatOtherSiteKappa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 01, 2016 12:57 am
- Post datetime: 2017-07-28T17:20:00+00:00
- Post Title: Futurama (PS2)

Sample: [https://mega.nz/#!clhByKhb!UzmNA35Jedzv ... 4VCID3UvMs](https://mega.nz/#!clhByKhb!UzmNA35JedzvqQIQGduhuJN0WN_blYFGg4VCID3UvMs) won't open in vgmtoolbox.
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-07-29T01:26:17+00:00
- Post Title: Futurama (PS2)

It won't open in VGMToolbox because it's an archive. Found this over on PS23DFormat, for QuickBMS:

```
Get end long 0 ;
SavePos base 0 ;
Do ;
GoTo base 0 ;
Get name String 0 ;
log MEMORY_FILE1 0 0 ;
GoTo 0 MEMORY_FILE1 ;
Put name String MEMORY_FILE1 ;
Get test ASIZE MEMORY_FILE1 ;
Math testbase = 0 ;
Math testtest = 0 ;
For x = 1 To test ;
GoTo testbase MEMORY_FILE1 ;
Get t Byte MEMORY_FILE1 ;
SavePos testbase MEMORY_FILE1 ;
If t = 0x2E ;
Math testtest += 1 ;
EndIF ;
Next x ;
If testtest = 0 ;
GoTo base 0 ;
GoTo 0x1 0 SEEK_CUR ;
Get name String 0 ;
Padding 4 ;
Get section Long 0 ;
SavePos base 0 ;
EndIF ;



GoTo base 0 ;
Get name String 0 ;
log MEMORY_FILE1 0 0 ;
GoTo 0 MEMORY_FILE1 ;
Put name String MEMORY_FILE1 ;
Get test ASIZE MEMORY_FILE1 ;
Math testbase = 0 ;
Math testtest = 0 ;
For x = 1 To test ;
GoTo testbase MEMORY_FILE1 ;
Get t Byte MEMORY_FILE1 ;
SavePos testbase MEMORY_FILE1 ;
If t = 0x2E ;
Math testtest += 1 ;
EndIF ;
Next x ;
If testtest = 0 ;
GoTo base 0 ;
GoTo 0x1 0 SEEK_CUR ;
Get name String 0 ;
Padding 4 ;
Get section Long 0 ;
SavePos base 0 ;
EndIF ;




GoTo base 0 ;
Get name String 0 ;
log MEMORY_FILE1 0 0 ;
GoTo 0 MEMORY_FILE1 ;
Put name String MEMORY_FILE1 ;
Get test ASIZE MEMORY_FILE1 ;
Math testbase = 0 ;
Math testtest = 0 ;
For x = 1 To test ;
GoTo testbase MEMORY_FILE1 ;
Get t Byte MEMORY_FILE1 ;
SavePos testbase MEMORY_FILE1 ;
If t = 0x2E ;
Math testtest += 1 ;
EndIF ;
Next x ;
If testtest = 0 ;
GoTo base 0 ;
GoTo 0x1 0 SEEK_CUR ;
Get name String 0 ;
Padding 4 ;
Get section Long 0 ;
SavePos base 0 ;
EndIF ;



GoTo base 0 ;
Get name String 0 ;
log MEMORY_FILE1 0 0 ;
GoTo 0 MEMORY_FILE1 ;
Put name String MEMORY_FILE1 ;
Get test ASIZE MEMORY_FILE1 ;
Math testbase = 0 ;
Math testtest = 0 ;
For x = 1 To test ;
GoTo testbase MEMORY_FILE1 ;
Get t Byte MEMORY_FILE1 ;
SavePos testbase MEMORY_FILE1 ;
If t = 0x2E ;
Math testtest += 1 ;
EndIF ;
Next x ;
If testtest = 0 ;
GoTo base 0 ;
GoTo 0x1 0 SEEK_CUR ;
Get name String 0 ;
Padding 4 ;
Get section Long 0 ;
SavePos base 0 ;
EndIF ;



GoTo base 0 ;
Get name String 0 ;
log MEMORY_FILE1 0 0 ;
GoTo 0 MEMORY_FILE1 ;
Put name String MEMORY_FILE1 ;
Get test ASIZE MEMORY_FILE1 ;
Math testbase = 0 ;
Math testtest = 0 ;
For x = 1 To test ;
GoTo testbase MEMORY_FILE1 ;
Get t Byte MEMORY_FILE1 ;
SavePos testbase MEMORY_FILE1 ;
If t = 0x2E ;
Math testtest += 1 ;
EndIF ;
Next x ;
If testtest = 0 ;
GoTo base 0 ;
GoTo 0x1 0 SEEK_CUR ;
Get name String 0 ;
Padding 4 ;
Get section Long 0 ;
SavePos base 0 ;
EndIF ;



GoTo base 0 ;
Get name String 0 ;
log MEMORY_FILE1 0 0 ;
GoTo 0 MEMORY_FILE1 ;
Put name String MEMORY_FILE1 ;
Get test ASIZE MEMORY_FILE1 ;
Math testbase = 0 ;
Math testtest = 0 ;
For x = 1 To test ;
GoTo testbase MEMORY_FILE1 ;
Get t Byte MEMORY_FILE1 ;
SavePos testbase MEMORY_FILE1 ;
If t = 0x2E ;
Math testtest += 1 ;
EndIF ;
Next x ;
If testtest = 0 ;
GoTo base 0 ;
GoTo 0x1 0 SEEK_CUR ;
Get name String 0 ;
Padding 4 ;
Get section Long 0 ;
SavePos base 0 ;
EndIF ;






GoTo base 0 ;
Get name String 0 ;
Padding 4 ;
Get filesize long 0 ;
Get fileoffset long 0 ;
SavePos base 0 ;
Log name fileoffset filesize 0 ;
While base < end ;

```
