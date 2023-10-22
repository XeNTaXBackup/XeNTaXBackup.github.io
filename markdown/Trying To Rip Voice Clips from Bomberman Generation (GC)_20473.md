## Post #1
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-15T20:46:37+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

Hello all. I've been struggling with this for a while and could use some help. I extracted the files from the iso using Dolphin and it seems the voice clips are in the .MDT files. Is there anyway to extract these or explore them further? I've tried just about everything I can think of.
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-05-16T05:18:22+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

Can you upload some sample MDT? We may be able to help.
## Post #3
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-16T06:53:04+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

Sure thing. This link has all the MDT files I found. 

[https://mega.nz/#F!uWh2BYAY!yx9KYjjiAWZhs8sCpH8VgA](https://mega.nz/#F!uWh2BYAY!yx9KYjjiAWZhs8sCpH8VgA)
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-16T17:20:22+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

I'm not sure if the .mdt files contain any audio.  As far as I can tell, the .seb files are the ones that contain the voices.

I've tried experimenting with various GENH audio formats, but can only get very crackly and barely audible voices at best.  I can't find the correct audio format for these files, which would make things much easier!
## Post #5
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-05-16T20:14:04+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

I have a slight feeling that these are headerless DSP files, as just scrolling through the files I can see sample rates, and possibly a coefficient table for it. I just need to figure out how to parse it, as there seems to be several tables before the data starts (Still can't find the data start ).

Looking at "1000.seb" here are the values I've found thus far:

```
0xA uint16 # of samples in file (?)
0x1c uint32 Start offset of sample data (probably acts as a base-offset)

```


EDIT: Was able to manually extract one sample from the SEB and have figured out it is DSP. Now that I know how to convert the data, I have to figure out how to link it all together in order to create a cohesive script.
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-16T22:50:25+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

Also what I've worked out in combination with yours:

0x04 - size of file (maybe used for calculating the size of the final entry in table 3, as it doesn't seem to store file lengths)
0x0A - number of entries in table 1
0x0C - offset to 'table 1' (8 bytes per entry)
0x10 - offset to 'table 2' (first entry in this table is the size of the data)
0x14 - offset to 'table 3' (32 bytes per entry) + a chunk of other data, see below
0x18 - offset to 'table 4'
0x1C - offset to start of sample data

What I've managed to work out of table 3 is as follows:

Offset 0x00 - not sure, but if 0xFFFF, this signifies the end of the entries in this table.
Offset 0x04 - offset to the start of this entry's audio data (relative to the start of the audio offset at 0x1C), so first file is at 0x2EC60.
Offset 0x0E - sample rate.
Offset 0x1C - this is an offset to some other data for each entry, relative to start of table 3 - so first entry is at 0x1464 (0x7C0 + 0xCA4).

That should be enough to at least extract the raw data files.

Pingu - did you manage to get your extracted data to play correctly?  If so, what did you use?  Thanks.
## Post #7
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-05-17T02:46:30+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

I utilized vgmstream. The problem with GENH is that it doesn't provide the ability to provide decoding coefficients. Currently working on a BMS implementation for this. The pointer at address 0x1C of table 3 points to each set of decoding coefficients, which usually is seen as 16 sets of uint16s. They are necessary to implement with the stream for decoding. You are correct with the file offsets, but obviously you can just subtract the current offset from the next offset to get the size, and if it's a case where its the last element , itll utilize EOF as the endpoint.

As well, the uint16 at 0x8 seems to be constant through other SEB so I assume it's some type of version ID. Since there's seems to be no entry count for table three, I guess I'd just read up to the next offset value, and if the next read offset = the 0xFFFFFFFF then break the script...
## Post #8
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-05-17T04:22:00+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

Script is complete. So, here's how to extract and convert these files:

Firstly. download QuickBMS:
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Next, download Foobar2000 + the latest vgmstream component (you can find this under "Components" on the main website):
[https://www.foobar2000.org/](https://www.foobar2000.org/)

Finally download this pack of tools, which has a .bms , .vgmstream.txth and an example picture:


 SEB.zip
(26.86 KiB) Downloaded 20 times

 (NOTE! Sometimes windows can be temperamental and rename the txth to "vgmstream.txth" you need to have the dot in front of it so it stays named ".vgmstream.txth") 

Firstly, run the BMS script on the SEB archive, which should extract custom .vgmstream files (The GUI can show you how if you're confused)

Next, once you extracted the files to the folder of your choice, place the TXTH in the same folder as the .vgmstream files (See example photo please!!!)

Finally, open up foobar, and from that folder just drag and drop the .vgmstream 's from the folder to the foobar program, and they should be able to play fine and you can convert them. 

Cheers!
## Post #9
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-17T09:31:21+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

Sorry for the trouble but I've never used QuickBMS before. I'm trying different combination of files but I can't seem to get it to extract. I'm sure it's something simple but here's what I have so far.

[https://imgur.com/vN5P5s8](https://imgur.com/vN5P5s8)
## Post #10
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-05-17T14:45:21+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

You’re opening the input archive wrong. You should first select the *.bms, and then a *.seb (not the vgmstream.txth file!) and then an output folder.
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-17T15:44:09+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

Good work, Pingu
## Post #12
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-17T22:39:50+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

Just an update:

I have discovered that the MDT files do in fact contain voice samples, contrary to my initial assumption.  The normal .seb files seem to be just sound effects.

The MDT files contain various file types, but there is definitely a .seb file structure within each one - I've managed to extract them manually as there doesn't seem to be an easy way to do it.  They're in exactly the same format as the stand-alone .seb files, so they're easy to recognise.

For example, in 1110.mdt, the .seb file is at location 0x217C0.
## Post #13
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-18T13:28:58+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

Ah good news! I tried the steps again and got it working this time. This has been invaluable to me and I thank you both for your hard work. 

While some voices are here, there are still quite a few that are not contained in these .seb files. Many of the game's bosses and villain voices are still out there. I'm thinking they're still hiding in the .MDT files as DKDave pointed out.
## Post #14
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-18T19:23:49+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

I have now extracted all of the voice files from the MDT archives, and all the dialogue seems to be there.

I'm not sure if I'm allowed to attach the .seb files here that are contained within the MDT files - but all you need to do is find them within the MDT files and use the same procedure to convert them as previously.

Let me know if you need any help on getting to them.
## Post #15
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-19T13:14:30+00:00
- Post Title: Trying To Rip Voice Clips from Bomberman Generation (GC)

How do I extract the .seb files from the .MDT files? I'm not sure how to explore it.
## Post #16
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-05-19T15:44:02+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

Haven't gotten the chance to look at the MDT archives yet. But, I will hopefully get the chance soon to figure out the structure of it.
## Post #17
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-19T19:20:00+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

I've just discovered that the offset 0xB4 in the MDT archive contains the location of the .seb file.  This value is zero if there isn't a .seb file present.

If you use the attached prog to extract .seb files from the MDTs, you should then be able to extract all the voices using Pingu's earlier method.  Place all MDTs and the 2 attached files in the same folder and run the batch file to extract all .seb files in one go.

Enjoy!
[mdtex.zip](https://xentaxbackup.github.io/file/16265_mdtex.zip)
## Post #18
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-19T22:44:27+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

When I try to open the program you provided, the window appears then vanishes. I disabled Windows Firewall and my anti-virus but it didn't change anything. 

Sorry to be a bother lol.
## Post #19
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-19T22:59:20+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

No bother - just double-click the convert.bat file, not the program directly.  That will extract all the .seb files from the MDTs in one go.
## Post #20
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-05-19T23:08:36+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

Awesome. Going to port that idea toward a bms script as well because why not
## Post #21
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-20T13:22:16+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

Hey guys. Last night I was able to extract those .seb files from the .mdt files and I got what I was looking for. I am beyond happy and on behalf of the Bomberman community, I thank you both. This is the first time we've ever had these silly, cringey English voices made available. Thanks to your efforts, voices like this are now out in the wild: [https://mega.nz/#!OGAWUYID!shPwzRbghjT5 ... 2TOH7-VRZM](https://mega.nz/#!OGAWUYID!shPwzRbghjT5DGR8hs2pPCmr4NiApEPGD2TOH7-VRZM)

Anywho, the only voices I could not find were the ones from Battle mode. It's voices that say the names of the battle modes like "Standard Battle" or "Dodge Battle" as well as things like "Just One More!"

I'm not sure if you guys have stumbled across them, but let me know. I'll look around in the mean time to see what I can find.
## Post #22
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-20T15:49:27+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

The battle mode voices are in the file btl.seb in the battle folder.

That should be everything
## Post #23
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-05-20T16:00:00+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

Just double check every folder, there should be some .seb in there around somewhere . Glad we could help! @DKDave if you want to collab on a project... let me know at some point and we could figure something out
## Post #24
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-20T17:14:09+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

Thanks, Pingu.  It's always good doing stuff like this, so if there's any other projects to work on, I'll be happy to help if I can.


Dave
## Post #25
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-21T03:01:56+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

Ah I found it! I now have everything I was looking for. I wanna express again how thankful I am to you two. I went to several forums looking for help and was either ignored or treated somewhat rudely. Not only did you guys help me but you were very kind to me through this process. I really appreciate kind attitudes on the internet so thank you again!

I'll be on the sounds resource website if anyone wants them.
## Post #26
- Username: heraldino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 01, 2023 1:54 am
- Post datetime: 2023-03-13T13:49:21+00:00
- Post Title: Re: Trying To Rip Voice Clips from Bomberman Generation (GC)

Guys, please help me, I really want to translate this game to my language, Portuguese, can someone tell me where the text files are? I found the textures, not the texts, can someone give me this help and how to extract and import it if there is already some kind of tool for this?
