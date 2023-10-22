## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-03-12T16:26:18+00:00
- Post Title: Haunted Hotel II: Believe the Lies - Archive

I'll appreciate any help or guidance to unpack the "main.pak" archive (hex start: 9025B0F9) from "Haunted Hotel II - Believe the Lies". 
The head.bin and tail.bin may be downloaded here: [http://motionpress.com/uploads/Haunted_ ... d_tail.rar](http://motionpress.com/uploads/Haunted_Hotel_head_and_tail.rar)

Thanks in advance!
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-12T16:33:35+00:00
- Post Title: Haunted Hotel II: Believe the Lies - Archive

its xored with 0x50 6F 70 43 61 70 53 65 78 79 46 72 61 6D 65 77 6F 72 6B
also this spells the word
PopCapSexyFramework
use this program
[http://aluigi.altervista.org/mytoolz/xor.zip](http://aluigi.altervista.org/mytoolz/xor.zip)
c:\xor\xor.exe C:\head.bin C:\head.bin.xor 0x506F70436170536578794672616D65776F726B
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-04T03:49:48+00:00
- Post Title: Haunted Hotel II: Believe the Lies - Archive

script for QuickBMS compatible with all the games developed (till now) by Specialbit:
[http://aluigi.org/papers/bms/specialbit.bms](http://aluigi.org/papers/bms/specialbit.bms)
