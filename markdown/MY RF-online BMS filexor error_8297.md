## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-02-15T19:01:13+00:00
- Post Title: MY RF-online BMS filexor error

I try to wirte a bms script to auto extract and convert RF online RFS archive but get error on it!
I can't figure out the problem myself and hope someone can help me!
(Before you suggest to use other tools, I know there are tools for that, I just want to write a bms for it)

```
savepos OFSTBL
for i = 0 < NUMRES
   goto OFSTBL
   getdstring RESNAME 0x38
   get OFSRES long
   get RESSIZE long
   savepos OFSTBL
   goto OFSRES
   get DDSHDR long
   if DDSHDR == 0x561EC46A
      set DDSNAME RESNAME
      string DDSNAME -= 3
      string DDSNAME += dds
      filexor "\x2e \x80 \x4d \x76 \x2E \xF8 \xD1 \xF0 \xBD \x3F \x86 \x81 \x58 \x2C \x3F \x3F \x2E \x2E \x67 \x6F \x3F \x40 \x3F \x78 \x3C \x3F \xF1 \xC0 \xA5 \xF6 \x3B \x9F \xC1 \x20 \x3F \xD7 \xC8 \xC1 \xE9 \x85 \x86 \xBD \xEF \x56 \x3F \xA1 \xFB \x2E \x87 \x86 \x61 \x4C \x21 \x3B \x4E \xB4 \x78 \x57 \xAE \x97 \x3F \x2E \x4A \x2E \x3F \x4C \x2E \x44 \xCD \xC5 \x5F \xE8 \xE9 \xEC \xEB \xBD \x9E \xBB \xF7 \x6C \x2E \xF2 \xE4 \x2E \x3F \x3F \x97 \x9F \x9D \xB3 \x21 \xB9 \x76 \x65 \x54 \x3F \xE6 \xF6 \xC6 \xF0 \x79 \xDB \xE2 \xB2 \x4B \x2E \x2E \xEB \xD3 \xD3 \xCA \xAB \xEA \xC7 \xED \x9C \xC7 \xD9 \xD0 \x65 \x48 \xB4 \xFA \x35 \x2E \x2E \x6A \x9B"
      #log DDSNAME OFSRES RESSIZE
      log MEMORY_FILE OFSRES 0x80      
      filexor ""
      math OFSRES += 0x80
      math RESSIZE -= 0x80
      append 
      log MEMORY_FILE OFSRES RESSIZE
      append
      math RESSIZE += 0x80
      log DDSNAME 0 RESSIZE MEMORY_FILE
   else
      log RESNAME OFSRES RESSIZE
   endif
next i
```


edit:
It's actually crash the qucikbms.exe and quit!
[NPL1NPCT.rar](https://xentaxbackup.github.io/file/5071_NPL1NPCT.rar)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T20:28:52+00:00
- Post Title: MY RF-online BMS filexor error

What's the error?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-15T21:38:21+00:00
- Post Title: MY RF-online BMS filexor error

you must add OFSRES after filexor or using the encryption xor command because filexor uses the offset 0 as base offset for the xoring job.
then when if you use the \x notation it's better to not leave spaces, while if you use 0x it's ok as you did.

for the rest I see no errors or problems, everything gets extracted correctly.

the following is the script with the specified correction (so only one line changes):

```
savepos OFSTBL
for i = 0 < NUMRES
   goto OFSTBL
   getdstring RESNAME 0x38
   get OFSRES long
   get RESSIZE long
   savepos OFSTBL
   goto OFSRES
   get DDSHDR long
   if DDSHDR == 0x561EC46A
      set DDSNAME RESNAME
      string DDSNAME -= 3
      string DDSNAME += dds
      filexor "\x2e\x80\x4d\x76\x2E\xF8\xD1\xF0\xBD\x3F\x86\x81\x58\x2C\x3F\x3F\x2E\x2E\x67\x6F\x3F\x40\x3F\x78\x3C\x3F\xF1\xC0\xA5\xF6\x3B\x9F\xC1\x20\x3F\xD7\xC8\xC1\xE9\x85\x86\xBD\xEF\x56\x3F\xA1\xFB\x2E\x87\x86\x61\x4C\x21\x3B\x4E\xB4\x78\x57\xAE\x97\x3F\x2E\x4A\x2E\x3F\x4C\x2E\x44\xCD\xC5\x5F\xE8\xE9\xEC\xEB\xBD\x9E\xBB\xF7\x6C\x2E\xF2\xE4\x2E\x3F\x3F\x97\x9F\x9D\xB3\x21\xB9\x76\x65\x54\x3F\xE6\xF6\xC6\xF0\x79\xDB\xE2\xB2\x4B\x2E\x2E\xEB\xD3\xD3\xCA\xAB\xEA\xC7\xED\x9C\xC7\xD9\xD0\x65\x48\xB4\xFA\x35\x2E\x2E\x6A\x9B" OFSRES
      #log DDSNAME OFSRES RESSIZE
      log MEMORY_FILE OFSRES 0x80     
      filexor ""
      math OFSRES += 0x80
      math RESSIZE -= 0x80
      append
      log MEMORY_FILE OFSRES RESSIZE
      append
      math RESSIZE += 0x80
      log DDSNAME 0 RESSIZE MEMORY_FILE
   else
      log RESNAME OFSRES RESSIZE
   endif
next i
```
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-02-15T22:59:26+00:00
- Post Title: MY RF-online BMS filexor error

Thank you for your help!
