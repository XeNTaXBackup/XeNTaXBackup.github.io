## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-05-14T21:26:40+00:00
- Post Title: Quickbms Hex string?

I know I can convert a decimal value as string like:

```
string stgvalue = value
string stgvalue += ".dat"    #become 50000163.dat
```


Is there a way to convert it as as hex string?
eg: output as "02FAF123.dat" string

Thanks in advance.
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-05-15T21:13:31+00:00
- Post Title: Quickbms Hex string?

Since I need a converter badly, I wrote a stupid function to do this work!
Hope this help some people out here as well.

```
StartFunction DEC2HEX_OUTPUT
   set STG ""
   math VALUE = YOUR_INPUT_VALUE     #change this  YOUR_INPUT_VALUE  to your variable
   for kk = 1 to 8
      math VALUE l= 4
      math TMP = VALUE
      math TMP &= 0xF   
      if TMP == 15
         string STG += "F"
      elif TMP == 14
         string STG += "E"
      elif TMP == 13
         string STG += "D"
      elif TMP == 12
         string STG += "C"
      elif TMP == 11
         string STG += "B"
      elif TMP == 10
         string STG += "A"
      else
         string STG += TMP
      endif
   next kk
   #print "%STG%"
EndFunction
```
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-05-21T19:01:34+00:00
- Post Title: Quickbms Hex string?

do you mean something like the following?

```
string NAME p= "%08x.dat" VALUE
```
