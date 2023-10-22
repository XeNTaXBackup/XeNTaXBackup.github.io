## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-31T19:52:16+00:00
- Post Title: double floats in quickbms

I have this script, big endianness if it matters:

```
   get VX longlong
   get VY longlong
   get VZ longlong
   get DUMMY long
   string VX p= "v %.16f " VX
   string VY p= "%.16f " VY
   string VZ p= "%.16f" VZ
   putCt VX string -1 MEMORY_FILE
   putCt VY string -1 MEMORY_FILE
   putCt VZ string -1 MEMORY_FILE
   put 0x0a0d short MEMORY_FILE
next i
```

But it doesn;t print the correct values. How am I supposed to do it?
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-01T05:25:47+00:00
- Post Title: double floats in quickbms

I think I figured it out...

So first of all, quickbms only reads the integer part of floats?!
> FLOAT       32 bit, 123.345 is got as 123
>
>     DOUBLE      64 bit, 123.345 is got as 123

And second, quickbms.exe can't read 64-bit numbers, and I have to use quickbms_4gb_files.exe.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-08-01T15:41:23+00:00
- Post Title: double floats in quickbms

yeah quickbms doesn't handle full floating point values because everything inside it is integer.
So when you use float/double as type of value, it saves only the integer part of the value.

Yes also for the second point, quickbms.exe uses 32bit integers and so reads a 64bit field but stores it inside a 32bit variable.
You must use quickbms_4gb_files to have full 64bit capabilities.
## Post #4
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-02T09:45:50+00:00
- Post Title: double floats in quickbms

Is there any way for the script to check if quickbms_4gb_files.exe is used, something like quickbmsver?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-08-02T16:08:25+00:00
- Post Title: double floats in quickbms

```
math TMP *= 16
if TMP == 0
    print "Error: you must use quickbms_4gb_files.exe for this archive"
    cleanexit
endif
```
