## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-31T03:34:43+00:00
- Post Title: Touhou Koumajou Densetsu

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-03T11:30:05+00:00
- Post Title: Touhou Koumajou Densetsu

bit of searching would have taken you to : [http://asmodean.reverse.net/](http://asmodean.reverse.net/)

i ported the method to bms for you though:

```
get dataOffset long
get files long
get dummy long

for i = 0 < files

  getdstring name 16
  get dummy long		# -1

  get seed_0 byte
  get seed_1 byte
  get seed_2 byte
  get seed_3 byte

  get offset long
  math offset += dataOffset	#offset relative to the start of data section
  get size long

  log MEMORY_FILE offset size
  callfunction unobfuscate
  log name 0 size MEMORY_FILE

next i

cleanexit

# ported to bms by WRS

# source: http://asmodean.reverse.net/misc/_/exdpmx.zip
# exdpmx.cpp
# coded by asmodean

startfunction unobfuscate

  set SEED2 byte 0xAA
  set SEED3 byte 0x55

  set SEED1 byte seed_0
  math SEED1 += SEED3	# 55
  math SEED1 ^= seed_2

  set SEED4 byte seed_1
  math SEED4 += SEED2	# AA
  math SEED4 ^= seed_3

  set MUT1 byte SEED1
  math MUT1 += SEED2

  set MUT2 byte SEED3
  math MUT2 += SEED4

  set KEY byte 0
  
  for i = 0 < size

    getvarchr BUFF MEMORY_FILE i

    math BUFF -= MUT2
    math BUFF ^= MUT1
    math KEY += BUFF

    putvarchr MEMORY_FILE i KEY

  next i

endfunction

```
