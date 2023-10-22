## Post #1
- Username: Amran
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 01, 2010 1:53 pm
- Post datetime: 2014-02-21T16:37:58+00:00
- Post Title: XWC File Comparison (Starbreeze Engine - Now With Bounty)

[Edit: I've been able to deconstruct the sound format and rebuild working sound files. The bounties no longer apply.]

A while back I had made a post in the Audio Format forum, but sadly didn't make any headway with the problem. I'm now  offering a (PayPal or Steam Wallet) bounty to hopefully garner more interest. The original topic is below with the information I had posted earlier:
[viewtopic.php?f=17&t=11120](http://forum.xentax.com/viewtopic.php?f=17&t=11120)

N/A for information that directly leads to being able to load the Enclave XWC files in the editors sound browser.
N/A for finding a way to successfully load the Enclave XWC files in the editors sound browser.

The first step would probably be finding the differences between the files (one which works, and one that doesn't), I've posted samples of these in the original thread. However, if anyone would like a full copy of the game, Steam keys are free with registration on dlh.net ( [http://www.dlh.net/en/register](http://www.dlh.net/en/register) ). The editor is also available at MODDB ( [http://www.moddb.com/games/enclave/downloads](http://www.moddb.com/games/enclave/downloads) ).

I'd love to see progress on solving this drawback with the editor, but sadly this specific area isn't my strong suit!
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-21T18:20:04+00:00
- Post Title: XWC File Comparison (Starbreeze Engine - Now With Bounty)

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "MOS DATAFILE2.0\x00"
get NULL longlong
get TABLEOFFSET long
goto TABLEOFFSET

getdstring VERSION 24
get NEXTPOS long
goto NEXTPOS

getdstring WAVEDATA 24
get NEXTPOS long
goto NEXTPOS

getdstring WAVEINFO 24
get UNKNOWN long
get NULL long
get NAMES long
get UNKNOWN long
get FILES long
goto NAMES

for i = 0 < FILES
   get OFFSET long
   math OFFSET += 0x24
   get SIZE long
   get NSIZE long
   getdstring NAME NSIZE
   
   do
       savepos TEMP
       get TERMINATOR byte
   while TERMINATOR == 0x20
    
   goto TEMP	
     
   log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Amran
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 01, 2010 1:53 pm
- Post datetime: 2014-02-22T15:50:14+00:00
- Post Title: XWC File Comparison (Starbreeze Engine - Now With Bounty)

The above script is handy. Any idea if there's a way to replace ogg files in a xwc with custom ones? [Edit: Can be done now that I've decompiled the files]
