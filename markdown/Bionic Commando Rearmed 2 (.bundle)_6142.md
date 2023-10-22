## Post #1
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2011-02-26T17:22:40+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

Hi all,

Bionic Commando Rearmed 2 seems to use a new version of the GRIN .bundle, which has previously been used in games like Ghost Recon Advanced Warfighter 2 and Bionic Commando. This new version no longer seems to have the BNDL header, and the data now seems to be compressed or encrypted. Would anyone be willing to give it a shot? Big thanks in advance!

* snip
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-26T19:51:00+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

I have figured it and I have written the script but I have seen that the current quickbms crashes so I must first check it (and possibly fixing it).
anyway just to tell you that job is done, only a bit delayed :)
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-26T22:01:29+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

Thanks luigi
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-26T22:44:52+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

ok released the new version, you can also use a version <= 0.4.7 because the bug I have fixed has been introduced in 0.4.8:
[http://aluigi.altervista.org/papers/quickbms.zip](http://aluigi.altervista.org/papers/quickbms.zip)

and the script:
[http://aluigi.altervista.org/papers/bms ... mando2.bms](http://aluigi.altervista.org/papers/bms/bionic_commando2.bms)

obviously let me know if you receive an error with some files
## Post #5
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2011-02-26T23:13:03+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

Thanks so much, Luigi! Works great so far!
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-27T02:29:18+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

The one bundle named "all" won't work with the script, here is a cut.

*snip *
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-27T16:13:33+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

this one is problematic.
in short at a first look it seems a non-compressed archive but in reality it's format is different than the other file I reversed because that one had a simple sequence of OFFSET+CRC while here it's complex and indeed I see OFFSET+SIZE+LOT_OF_GARBAGE.

is this file a cut or the original uncutted one?
if it's a cut, how big is the original one? (exact size in bytes!)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-27T16:27:36+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

in the meantime I have found the solution and when I will arrive at home I will update the script :)
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-27T17:23:50+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

just updated to version 0.1.1, refresh the previous link to the bms file.

as usual keep me update if some archives give problems
## Post #10
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-27T17:57:43+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

Nice we can still pry into the .bundle files.
Still too bad we cant do anything with the GRIN .diesel models still

(as posted here as well) [viewtopic.php?f=16&t=5051&p=42743&hilit=diesel#p42743](http://forum.xentax.com/viewtopic.php?f=16&t=5051&p=42743&hilit=diesel#p42743) 

Still. Cant look into the assets until you can look into the archive!
Thanks!
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-03T22:04:22+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

I just found a bundle that's not working with the script: * snip *
An update would be nice.
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-09T16:08:23+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

fixed, it was just an uncompressed chunk:
[http://aluigi.org/papers/bms/bionic_commando2.bms](http://aluigi.org/papers/bms/bionic_commando2.bms)
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-09T23:25:35+00:00
- Post Title: Bionic Commando Rearmed 2 (.bundle)

Hehe, cool thing. Thanks Luigi!
