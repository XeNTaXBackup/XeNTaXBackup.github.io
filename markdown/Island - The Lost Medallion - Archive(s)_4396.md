## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-04-26T22:49:18+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

I'll appreciate any help or guidance to unpack the "*.pak"-archives from "Lost Medallion". 
The head.bin and tail.bin may be downloaded here: [http://www.motionpress.com/uploads/Lost ... adTail.rar](http://www.motionpress.com/uploads/LostMedallionHeadTail.rar)

Thanks in advance!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-26T23:39:37+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

```

filexor "0x73 0x70 0x65 0x63 0x69 0x61 0x6c 0x62 0x69 0x74" # "specialbit"
get DUMMY long
get DUMMY long
for EXTRACT = 0 < 2
    goto 8
    for
        get LAST byte
        if LAST != 0
            break
        endif
        get NAMESZ byte
        getdstring NAME NAMESZ
        get SIZE long
        get TIMESTAMP longlong
        if EXTRACT != 0
            log NAME OFFSET SIZE
            math OFFSET += SIZE
        endif
    next
    savepos OFFSET
next EXTRACT
```
## Post #3
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-04-27T17:47:42+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

Thanks.

When I run the script, I receive the following error: "invalid datatype longlong at line 16"
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-27T18:05:27+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

update to a  newer quickbms.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-27T18:20:01+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

argh, I wasn't fast enough to login to beat you in the reply :)
anyway, yes, when quickbms reports these types of errors is EVER needed to verify if there is a newer version available because 99% of times that's the cause
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-04-29T15:27:33+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

@aluigi: i'm curious how you guessed the xor key - i can only guess the developers have made other games using it too?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-29T16:28:14+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

when you open the sample file with a hex editor you can see various "SPECIALBIT" strings which are just the key xored with the space char.
## Post #8
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-10-24T01:21:43+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

How about this game Haunted Hotel: Lonely Dream?
It seems the xor key has benn changed. 
Anyone can help me to extract the .pak file?
Thanks very much.

a sample can be download here
[http://www.bigfishgames.com/download-ga ... index.html](http://www.bigfishgames.com/download-games/9028/haunted-hotel-lonely-dream/index.html)
## Post #9
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-24T06:26:43+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

This is the Xor password of the game: "AhCTuT3G5#Ui3P09BgiUiO5"
## Post #10
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-10-24T06:59:33+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

> Reply from bacter
>
> This is the Xor password of the game: "AhCTuT3G5#Ui3P09BgiUiO5"

Thanks very much!
How do you find the xor password?
## Post #11
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-25T08:13:18+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

More Xor passwords for Specialbit Studio games:
Island: The Lost Medallion password: "specialbit"
Haunted Hotel password (one character): "0x7F"
Haunted Hotel II: Believe the Lies password: "PopCapSexyFramework"
Haunted Hotel 3: Lonely Dream password: "AhCTuT3G5#Ui3P09BgiUiO5"
## Post #12
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-10-25T11:19:26+00:00
- Post Title: Island - The Lost Medallion - Archive(s)

> Reply from bacter
>
> More Xor passwords for Specialbit Studio games:
Island: The Lost Medallion password: "specialbit"
Haunted Hotel password (one character): "0x7F"
Haunted Hotel II: Believe the Lies password: "PopCapSexyFramework"
Haunted Hotel 3: Lonely Dream password: "AhCTuT3G5#Ui3P09BgiUiO5"

Wow! Thank you very much!
