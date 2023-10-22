## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-17T21:30:25+00:00
- Post Title: Age of Empires Online (*.BAR)

[http://ageofempiresonline.com/](http://ageofempiresonline.com/)

just found out about this game. addictive!  

```
# Script for QuickBMS by WRS

idstring "ESPN"
get DUMMY long
get ENDIAN long

# possible endian check. not sure if aoeo is pc only atm
if ENDIAN == 0x44332211
 # little (pc)
elif ENDIAN == 0x11223344
 # big (xbox ?)
  endian big
else
  print "failed at endian check"
  cleanexit
endif

goto 276

get DUMMY long
get FILES1 long
get OFFSET long

goto OFFSET

string LASTSTR = ""
callfunction getstr 1
string DIR = LASTSTR

get FILES2 long # again, may only be files in LASTSTR ? todo: compare w/ prev FILES

if FILES1 != FILES2
  print "file count mismatch  %FILES1% != %FILES2%"
  cleanexit
endif

for f = 0 < FILES2
  get PNTR long
  get SIZE1 long
  get SIZE2 long
  get DUMMY long
  get DUMMY long
  get DUMMY long
  get DUMMY long
  string LASTSTR = ""
  callfunction getstr 1

  if SIZE1 != SIZE2 
    print "%FNAME% may be compressed. skipping"
  else
    string FNAME p= "%s%s" DIR LASTSTR
    log FNAME PNTR SIZE1
  endif

next f



cleanexit

startfunction getstr

  get STRLEN long
  math STRLEN *= 2 # 16-bit / unicode
  getdstring UNISTR STRLEN
  set LASTSTR unicode UNISTR

endfunction

```


i made a new thread because there is binary xml (XMB) format which i might look into + post something on later

update apparently both the bar and xmb formats are used in other age of empires games ..
