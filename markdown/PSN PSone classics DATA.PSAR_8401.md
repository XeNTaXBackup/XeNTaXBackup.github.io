## Post #1
- Username: Burnt Lasagna
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Feb 20, 2012 11:52 pm
- Post datetime: 2012-02-24T19:13:09+00:00
- Post Title: PSN PSone classics DATA.PSAR

Okay, so this has been a theory that I've had for a long time and it has slowly been driving me insane the more I think about as the years go by.
I’ve been wondering if it is possible to extract a working PS1 ISO from a legit PSone classic downloaded from PSN. A while back I tried to look into this myself so I transferred one of my PS1 games from my PS3 to my PSP and extracted the eboot.pbp in my PC using PBP Unpacker. 

Now before I continue I would like to make one thing clear. The PS3 stores its PSone classics the same way as the PSP, well for the most part that is. Instead of just having an eboot.pbp the PS3 has an eboot.bin, which houses the PSP eboot.pbp along with the virtual manual and one other file that I believe tells the PS3 how to boot into the eboot.pbp. When transferred over to the PSP it just copy’s the eboot.pbp over. 

Now onto the unpacked eboot. When I extracted it I looked for the largest file since that would most likely be housing the ISO. The file DATA.psar was the largest (later on I found out that this is a common file to have in a eboot.pbp).  I put the Data.psar into a hex editor and found proof in the header that it must be housing the ISO. 
(img of the header)

“PSISOIMG” which most likely stand for “Playstation ISO Image”.  Sadly I never got any farther than that. From what I heard no one has ever successfully done this. Though I don’t think anyone has ever felt the need to seriously look into this either.     

I thought I should finally ask around here if anyone can crack this or at least ask if you can share your two scents about it. Hopefully then I can cure my two year long headache that I’ve had with this.
## Post #2
- Username: Burnt Lasagna
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Feb 20, 2012 11:52 pm
- Post datetime: 2012-02-27T21:45:16+00:00
- Post Title: PSN PSone classics DATA.PSAR

Sorry, I know bumping topics is the devils work.
But please, for the love of God, can someone share there thoughts on this?
As I've said before, this has been driving me insane for two years now and I  would really like to hear someone elses research into this matter then just my own.
## Post #3
- Username: Burnt Lasagna
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Feb 20, 2012 11:52 pm
- Post datetime: 2012-02-28T19:54:58+00:00
- Post Title: PSN PSone classics DATA.PSAR

Okay, found out back in 2007 Dark_AleX created a tool named psxdecrypt that runs on the PSP and can do this very thing!
...that is it can, only on CFW 3.03 OE.

Does anyone know if it's possible to run this on 6.60? To be more specific 6.60 PRO-B10.
I have the tool as an attachment, source included.
[psxdecrypt.zip](https://xentaxbackup.github.io/file/5115_psxdecrypt.zip)
## Post #4
- Username: Burnt Lasagna
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Feb 20, 2012 11:52 pm
- Post datetime: 2012-03-01T17:27:17+00:00
- Post Title: PSN PSone classics DATA.PSAR

...anyone
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-01T19:04:25+00:00
- Post Title: PSN PSone classics DATA.PSAR

You may have better luck with more specialized communities that deal with PSP's and related mods/hacks.
## Post #6
- Username: Burnt Lasagna
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Feb 20, 2012 11:52 pm
- Post datetime: 2012-03-01T20:42:02+00:00
- Post Title: PSN PSone classics DATA.PSAR

Yeah, you’re probably right. I already tried GBAtemp but it doesn't seem to be getting much of a buzz there.
My next thought would be psx-scene, or is there a different site more geared towards this kind of thing?
