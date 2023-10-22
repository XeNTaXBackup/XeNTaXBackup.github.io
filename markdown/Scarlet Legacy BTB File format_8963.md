## Post #1
- Username: cmb
- Rank: Banned
- Number of posts: 1
- Joined date: Tue Oct 26, 2010 4:02 pm
- Post datetime: 2012-05-21T02:19:08+00:00
- Post Title: Scarlet Legacy BTB File format

Hi, I've recently started playing this game, and was wanting to take a look at the tables (like exp to level up, items, npc, etc...) but the format is in this wierd btb format, that has to be their own doing. Can anyone assist me in decrypting these files? I noticed that somebody had worked on the .pak files for this game, but no mention of these exact ones. I've upload a couple different ones of varying sizes aswell as the main client exe. Please let me know if there is anything else that you might need to help me!!! I'd really appreciate the help!! thanks! 

* snip *
## Post #2
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2012-05-22T06:07:55+00:00
- Post Title: Scarlet Legacy BTB File format

File Data zlib compression 

```
#BY Allen May 2012
#script for QuickBMS http://quickbms.aluigi.org
Comtype Zlib
Idstring "umy="
Goto 0x40
get zsize long
savepos OFFSET
set OFFSET2 OFFSET
math OFFSET2 += ZSIZE
goto OFFSET2
get SIZE long
get name filename
Clog NAME OFFSET ZSIZE SIZE

```
