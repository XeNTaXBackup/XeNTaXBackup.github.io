## Post #1
- Username: danny
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Apr 11, 2011 6:16 pm
- Post datetime: 2012-03-11T19:15:37+00:00
- Post Title: Help with .pak archive agency 2

I want to decompress the archive data.pak but the code for agency of anomalies Hospital Mystic Not function

The Archive

<link removed due forum rules violation>

Thanks for Help!  And sorry for my bad english
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-12T15:56:36+00:00
- Post Title: Help with .pak archive agency 2

the format is the same of the other Orneon games but the xor key is different (unknown).

the following is the reference thread (echoes of the past):
[viewtopic.php?f=10&t=3919](http://forum.xentax.com/viewtopic.php?f=10&t=3919)
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-12T19:11:42+00:00
- Post Title: Help with .pak archive agency 2

key - a26551. here script 

```
get ZSIZE short
savepos OFFSET
clog MEMORY_FILE OFFSET ZSIZE 0x10000

get DUMMY byte MEMORY_FILE  # zip?
get FILES short MEMORY_FILE
for i = 0 < FILES
    math OFFSET += ZSIZE
    get NAMESZ byte MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get SIZE long MEMORY_FILE

    # thanx bacter
    filexor  "0x61 0x32 0x36 0x35 0x35 0x31" OFFSET   # The Agency of Anomalies 2 - Cinderstone Orphanage CE
    clog NAME OFFSET ZSIZE SIZE
    filexor ""
next i

```


enjoy
## Post #4
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2012-04-15T18:25:49+00:00
- Post Title: Help with .pak archive agency 2

Hi Ekey
How do you determine the Xor password? Echoes = e34596; Secrets = tm7224; Anomalies = a26551
I'll appreciate help with the Xor password and the modified lines for the QuickBMS script for "Echoes of the Past The Revenge of the Witch".
The head and tail of the data.pak file may be downloaded here:
<link removed due forum rules violation>
Regards, and thanks
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-16T16:23:13+00:00
- Post Title: Help with .pak archive agency 2

Upload only main executable with all modules (dlls)
