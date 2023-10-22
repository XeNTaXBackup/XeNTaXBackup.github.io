## Post #1
- Username: moordact
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 04, 2011 10:18 pm
- Post datetime: 2011-07-04T14:23:13+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

Hello.

I am looking for some mysterious heroe who can make us a script for quickBMS that finds the correct filenames.

Or just a complete new method to unpack the .pak files together with their correct filenames.

this is the current script , that doesn't unpack the filenames. because they have not yet been found inside the files.

```

get ONE long
get FILESIZE long
get PADDING long
get HSIZE long

math HEADERS = HSIZE
math HEADERS /= 60 # size of this structure:

for h = 1 to HEADERS
  getdstring UNKNOWN 20 # 5*4
  get ZSIZE long
  get SIZE long
  get UNKNOWN long
  get POINTER long
  getdstring UNKNOWN 24 # 6*4

  if ZSIZE == SIZE
    log "" POINTER ZSIZE
  else
    clog "" POINTER ZSIZE SIZE
  endif
next h

```


if u need a .pak file to look into , I could upload one on to a mirror somewhere .
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-07-04T20:26:54+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

how you can extract the files with names if these names don't exist at all?

anyway you have the extensions, it's a good starting point.
## Post #3
- Username: moordact
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 04, 2011 10:18 pm
- Post datetime: 2011-07-05T09:35:59+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

, well there must be a way the game calls it's files:-/
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-05T11:00:09+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

a game does not need file names to run correctly a lot of games have no file names just hashes.
## Post #5
- Username: moordact
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 04, 2011 10:18 pm
- Post datetime: 2011-07-05T17:11:33+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

hmm , then how can you inject edited files from inside the .pak archive back in ?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-07-05T17:43:33+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

quickbms will load them automatically, you must not rename them.
just use the reimport feature as usual by clicking on the reimport link or by creating a link by yourself as explained in the section 3 of quickbms.txt
## Post #7
- Username: moordact
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 04, 2011 10:18 pm
- Post datetime: 2011-07-05T20:03:47+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

that's whats not working.

it keeps saying the filenames don't match.

the reason herefore is.

inside the .pak files there r no filesnames.
and what i think QuickBMS does is replacing the file inside the .pak file , with your newer upgraded file.
But since there is no file inside named the same.
It can't be replaced.


Because when extracting with QuickBMS , QuickBMS Generates his own logical names for the nameless files.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-05T20:15:28+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

Think about this.
I have 10 apples each a different color.
the only thing about the apples that matters is their color.
now i replace a green apple with another green apple and no one notices the difference.
I did not need to name the apples even tho i could have and they still did the same thing.
There will not be any file names for these files they are just extracted in order.
so when quickbms packs them back it just does the same thing so its entirely possible to edit the files as long as they are the same size or less.
If you can not understand this you should not be modding games.
## Post #9
- Username: moordact
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 04, 2011 10:18 pm
- Post datetime: 2011-07-05T21:05:39+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

il try again , allthough i was pretty sure my files where the same size or less :-/

i'l keep u updated
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-23T06:08:22+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

For New Client (1.9+) - New format.

```
#  
# Written by Ekey (h4x0r) 
# http://www.progamercity.net 
#  
# script for QuickBMS http://quickbms.aluigi.org 

comtype unzip_dynamic 

idstring "TWAD" 
get VERSION long
get DUMMY long
get DUMMY long
get FILES long

for i = 0 < FILES 
  get ID1 long # Pointer for Manifest ?
  get ID2 long # Pointer for Manifest ?
  get OFFSET long 
  get SIZE long 
  get SIZED long 
  get DUMMY long 
  getdstring SHA1 0x14 
  string NAME p= "%08X%08X" ID1 ID2 
  clog NAME OFFSET SIZE SIZE 
next i
```
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-12-21T10:37:22+00:00
- Post Title: [REQUEST]RIFT planes of telara QuickBMS script WITH filename

Coming soon



Hashes -> FNV1a
