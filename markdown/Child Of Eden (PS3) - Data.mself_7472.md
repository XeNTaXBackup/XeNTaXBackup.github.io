## Post #1
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-10-08T04:19:46+00:00
- Post Title: Child Of Eden (PS3) - Data.mself

The singlular archive from the PS3 version of Child Of Eden.

Might contain a file table, I'm not 100% sure on that.

Could someone write a BMS script to extract it please? 

[http://www.mediafire.com/?rtc9dc6htr6w8tf](http://www.mediafire.com/?rtc9dc6htr6w8tf)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-08T08:54:08+00:00
- Post Title: Child Of Eden (PS3) - Data.mself

it does contain some data but the mself file looks too small to contain it. uncomment the log call to see what i mean

```

idstring "MSF\0"

get DUMMY long # 1
get DUMMY long # 0
get SOMESIZE long # expected filesize?
get FILES long
get START long

goto START

for i = 0 < FILES
  getdstring NAME 32
  get DUMMY long
  get PNTR long
  get DUMMY long
  get SIZE long
  get DUMMY long
  get DUMMY long
  get DUMMY long
  get DUMMY long

  print "%NAME% @ %PNTR%, %SIZE% bytes"
#  log NAME PNTR SIZE
next i

```
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-10-10T06:01:38+00:00
- Post Title: Child Of Eden (PS3) - Data.mself

I did what you said and yeah, it only unpacks .dat files.

I see comments of VirtualDub inside some of them too so I'm not exactly sure.
