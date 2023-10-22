## Post #1
- Username: Arcane
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 19, 2010 2:16 am
- Post datetime: 2010-10-18T18:20:39+00:00
- Post Title: Dokapon Kingdom PAC/PAH.

Dokapon Kingdom's an interesting little Mario Party-like game for PS2 and Wii. I'm currently attempting to do some extensive hacking work on it, but I can't figure out what in the world's with its data formats.

It has two data files: DATA.PAC and DATA.PAH. The PAH file has some filenames listed in it, so I'm thinking it's a reference to the order in .PAC, but I'm not sure.

It's an Intrinsic Alchemy game that nobody seems to have worked on hacking-wise whatsoever, and I'd  be rather happy to get this thing cracked open. It's got a lot of potential.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-18T18:36:23+00:00
- Post Title: Dokapon Kingdom PAC/PAH.

your request is useless wo the files for us to examine!
## Post #3
- Username: Arcane
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 19, 2010 2:16 am
- Post datetime: 2010-10-18T18:43:39+00:00
- Post Title: Dokapon Kingdom PAC/PAH.

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-18T23:55:36+00:00
- Post Title: Dokapon Kingdom PAC/PAH.

a filecut of a few mb or so of that large file will be enough to both examine and keep legal. 

only data in the example are pointers and filenames - stuff thats useless without its counterpart!

scripts look cool though, so have a filename dump

```
get FHEADERS long # file headers
get FHEADPTR long # pointer to file headers
get FHEADEND long # pointer to end of file headers
# other pointers perhaps?

## file headers

goto FHEADPTR

append
log MEMORY_FILE 0 0

for i = 1 to FHEADERS

  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get ITEMPTR long # pointer to string

  savepos POS
  goto ITEMPTR
  get ITEMSTR string
  strlen ITEMLEN ITEMSTR

  log MEMORY_FILE ITEMPTR ITEMLEN
  set MEMORY_FILE binary "\xd\xa"

  goto POS

next i

append
get MEMSIZE asize MEMORY_FILE
log "Filename_Dump.txt" 0 MEMSIZE MEMORY_FILE

```
## Post #5
- Username: Arcane
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 19, 2010 2:16 am
- Post datetime: 2010-10-22T19:05:09+00:00
- Post Title: Dokapon Kingdom PAC/PAH.

What's the best way to go around splitting it without archiving it?
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-23T11:22:39+00:00
- Post Title: Dokapon Kingdom PAC/PAH.

> Reply from Arcane
>
> What's the best way to go around splitting it without archiving it?

Cutting it!

[http://www.xentax.com/downloads/tools/filecutter.zip](http://www.xentax.com/downloads/tools/filecutter.zip)
