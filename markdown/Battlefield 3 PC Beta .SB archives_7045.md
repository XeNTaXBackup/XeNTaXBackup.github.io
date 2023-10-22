## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-07-23T22:39:02+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

Can someone help crack the new frostbite engine archives? Thanks.

[http://www.megaupload.com/?d=A4GR59AG](http://www.megaupload.com/?d=A4GR59AG)
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-07-25T17:08:42+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

Appears to be uncompressed, search for hex value "4800000C" which is the BC2 audio tag for frequency, and it appears alot. My guess is, the TOC files have a list, since they have offest and size repeating ALOT. these files seem alot more friendly than fbrb format used previously, before hiding everything away. maybe a sign of mod tools being likely, or just most trust in the pc community. or it's just that the game's only in alpha possibly.

Edit: Oh.. sorry, I'm talking about the large Chunks0.sb and Chunks0.toc, global could be different.
## Post #3
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-07-28T22:33:25+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

.toc are fairly simple, they're metadata structure format (shared with other files) that have a basic id/offset/size in two sections, bundles, and chunks.

bundles have string id/int64 offset/int64 size, and point to their respective locations in the .sb file.
chunks have hash id/int64 offset/int32 size (hash = uint8[16], md5?), and also point to their respective locations in the .sb file.

chunks seem to have varying data types (image data, etc), bundles seem to be a more complicated archive format (with actual compression).
## Post #4
- Username: Tosh1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 02, 2011 12:35 am
- Post datetime: 2011-08-01T16:39:24+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

I´ve the same interest as the threadstarter but I don´t have any skills in doing this. I would be very thankful if anyone could help by providing a tool or anything comparable
## Post #5
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-08-03T20:11:18+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

Also very interested. (bump)
## Post #6
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2011-09-27T16:18:53+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

Hi guys .

I found some " 48 00 00 0C " values in the .SB file . So , I tried to extract sounds from it , with the same technique for BFBC2  , but it did not work . Maybe we have to find an other technique ...?

Thank's dudes .

Vosvoy
## Post #7
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-09-27T20:10:16+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

bf3 and bc2 level_00.fbrb contained audio are the same or similar format, that nobody has decoded on pc yet, there are instructions for xbox, but its just ea type xma.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-09-27T21:24:36+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

Yes i posted a sample in the audio section. Im checking the xbox360 version, usaully that will use Packed xma.
## Post #9
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2011-09-28T15:04:07+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

> Reply from Pepper
>
> bf3 and bc2 level_00.fbrb contained audio are the same or similar format, that nobody has decoded on pc yet, there are instructions for xbox, but its just ea type xma.

" Argh ... mah shame " . Sorry , but I totally forgot that we only can extract the sounds with the Xbox360 version ...

So , we have to wait for the final Battlefield 3 Xbox360 version ...
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-09-28T18:48:32+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

I got the beta for xbox, but the tools for extracting live dlc/betas/etc dont work on the chunk file, its too big for it to handle i guess. the tool itself is called x360Tool.exe, and apears to be working on smaller dlc's/betas. 

edit: worded that confusingly, the dlc/beta format is a 1.5gb numerical (4C207D8B97D4F42D1A2C2E201490E71651835FA045) file with no extension. (only 1.5gb... no caspian border on 360 maybe?) and i can see the files inside, but i can't extract the one with most of the sounds.

Oh wait (edit 2) it's working, its just going slow. REALLY slow.
## Post #11
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-09-28T19:57:19+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

Is anyone happened to extract the texts of the game?
## Post #12
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-09-28T22:33:43+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

I doubt it. and why would you even want to. beta is mp only, and most of the text is on the battlelog, which is a website..
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-09-29T02:30:52+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

Checked the beta as well and it indeed used ea packed xma. could convert audio but no music in there.
## Post #14
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2011-09-29T07:10:01+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

So ? It's possible to extract it now ?

Otherwise , we can wait the final version ^^' . It does not matter   .

PS : If someone could send us Xbox360 Beta files , that would be nice .

Vosvoy
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-09-29T16:14:48+00:00
- Post Title: Battlefield 3 PC Beta .SB archives

Well there are no tools yet to extract it i just did it with vgmtoolbox and extracted the audio files.
## Post #16
- Username: Orion
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 30, 2011 12:29 am
- Post datetime: 2011-09-29T16:31:30+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Hey guys, I'm new here, but I've been doing some modding in different games for a while.  I was in the  BF3 alpha and did a bit of poking around, it looks like they've changed the .toc files since then.  Anyone know how they are encoded?  I'm just trying some different stuff with the raw bytes from the file atm.
## Post #17
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-29T17:28:37+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

I'll take a look again but I'm sure they encrypted the TOC to slow people down from poking around.
## Post #18
- Username: Orion
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 30, 2011 12:29 am
- Post datetime: 2011-09-29T19:53:32+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Yeah that's what it looked like to me too.  Interestingly, in the three TOC files I've looked at, there are sections that look like hex values - from ascii (so, when the bytes are put into ascii, the results are hex characters) enclosed within the 'x' character.  The hex values don't correspond to characters themselves though as far as I can tell.
## Post #19
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2011-09-29T20:53:45+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from OrangeC
>
> Well there are no tools yet to extract it i just did it with vgmtoolbox and extracted the audio files.

Ow ... Can you share the Xbox360 files ( .sb ) to us ? I would like to analyze these files .

( Please )

Vosvoy
## Post #20
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-29T21:47:22+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

New obfuscation on .toc is extremely simple.

If the first dword is 0x00CED100 (D1CE) then the file is obfuscated, otherwise it's normal.

Magic data starts at 0x128 and is 257 bytes.
Real data starts at 0x22C until end of file.

```
{
  data[i] = data[i] ^ magic[i % 257] ^ 0x7B;
}
```
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-30T02:42:23+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from Pepper
>
> I got the beta for xbox, but the tools for extracting live dlc/betas/etc dont work on the chunk file, its too big for it to handle i guess. the tool itself is called x360Tool.exe, and apears to be working on smaller dlc's/betas. 

edit: worded that confusingly, the dlc/beta format is a 1.5gb numerical (4C207D8B97D4F42D1A2C2E201490E71651835FA045) file with no extension. (only 1.5gb... no caspian border on 360 maybe?) and i can see the files inside, but i can't extract the one with most of the sounds.

Oh wait (edit 2) it's working, its just going slow. REALLY slow.
It's default XBOX Pirs file. Use wxPirs tool for unpack. x360Tool not correctly work with big files.
## Post #22
- Username: redspider
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2010 10:48 pm
- Post datetime: 2011-10-01T18:50:31+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Also VERY interested in this. Anybody have any tools/guides?

thanks
## Post #23
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-10-02T00:10:20+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

@Rick
have you ever thought making a tool to edit .sb and .toc files? 
and 0x00D1CE00 is nice header DICE
## Post #24
- Username: redspider
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2010 10:48 pm
- Post datetime: 2011-10-02T18:53:07+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from OrangeC
>
> Well there are no tools yet to extract it i just did it with vgmtoolbox and extracted the audio files.
Do you have a tut for this?
## Post #25
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-10-02T21:47:06+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from rengareng
>
> @Rick
have you ever thought making a tool to edit .sb and .toc files? 
and 0x00D1CE00 is nice header DICEIt's beta so no. I have a working unpacker but I doubt I'll push the code anywhere until the game is actually out.
## Post #26
- Username: redspider
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2010 10:48 pm
- Post datetime: 2011-10-02T22:04:13+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from Rick
>
> It's beta so no. I have a working unpacker but I doubt I'll push the code anywhere until the game is actually out.
Can you take a request then?  I'm after the Battlefield theme that plays when you about to win a round... i want it for my ringtone
## Post #27
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-10-02T22:53:06+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Sorry, taking a quick look I have no idea where any of the music is, it's probably buried in the chunks data somewhere.
## Post #28
- Username: redspider
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2010 10:48 pm
- Post datetime: 2011-10-02T22:55:24+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from Rick
>
> Sorry, taking a quick look I have no idea where any of the music is, it's probably buried in the chunks data somewhere.
Damn. Thanks for taking a look. Any chance you can post (or PM) details on how i could try and unpack? Then i can have a good ol' nosy myself
## Post #29
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-10-02T23:05:05+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from redspider
>
> Damn. Thanks for taking a look. Any chance you can post (or PM) details on how i could try and unpack? Then i can have a good ol' nosy myself.toc format is self-describing once you get past the obfuscation...
## Post #30
- Username: redspider
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2010 10:48 pm
- Post datetime: 2011-10-02T23:08:45+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from Rick
>
> redspider wrote:Damn. Thanks for taking a look. Any chance you can post (or PM) details on how i could try and unpack? Then i can have a good ol' nosy myself .toc format is self-describing once you get past the obfuscation...
How would one do this? As my forum rank states, im an ultra-n00b at this :p
## Post #31
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-02T23:26:16+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

There isn't any music in the beta or so i haven't found it yet.
## Post #32
- Username: redspider
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2010 10:48 pm
- Post datetime: 2011-10-02T23:28:33+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from OrangeC
>
> There isn't any music in the beta or so i haven't found it yet.
There is music at the end of the round. 2 different tracks, one for if you loose and one if you win
## Post #33
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-03T00:21:25+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

How long are they?
## Post #34
- Username: redspider
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2010 10:48 pm
- Post datetime: 2011-10-03T16:43:27+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from OrangeC
>
> How long are they?
I wouldn't say very long as they just loop over and over. I'd say no more than 15-20 seconds each

EDIT:
Here is the "Round Lost" music:
[http://www.youtube.com/watch?v=YvrHlKVImfY](http://www.youtube.com/watch?v=YvrHlKVImfY)

EDIT #2:
You can just about hear the round win music in this vid:
[http://youtu.be/pU1lloF65Sk?t=43s](http://youtu.be/pU1lloF65Sk?t=43s)
## Post #35
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-05T06:20:06+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

I will upload X360 version very soon...

EDIT :
To bad so far coz that beta is only in GOD format and files cannot be seen.
## Post #36
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-05T14:36:50+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

That wasn't the case for me. It was a normal Xbox live file.
## Post #37
- Username: Duck
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 06, 2011 1:41 am
- Post datetime: 2011-10-05T17:44:35+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

I'm looking for a tool to extract sounds from the .SB archives.

I only have the BF3 beta, I'm not going to buy the game.
## Post #38
- Username: salut333
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2011 11:07 pm
- Post datetime: 2011-10-09T22:18:02+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Anyone works on this?
## Post #39
- Username: Spy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 10, 2011 6:41 pm
- Post datetime: 2011-10-10T16:21:15+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from Rick
>
> New obfuscation on .toc is extremely simple.

If the first dword is 0x00CED100 (D1CE) then the file is obfuscated, otherwise it's normal.

Magic data starts at 0x128 and is 257 bytes.
Real data starts at 0x22C until end of file.
Code: Select allfor (int i = 0; i < length; i++)
{
  data[i] = data[i] ^ magic[i % 257] ^ 0x7B;
}

Thanks to this I managed to successfully remove obfuscation, but it will quite hard to interpret data.

I've already dropped this thing and waiting for full game, but I have one question for Rick. Why did you added that 0x7B XOR and how did you figured out that value ? I don't really have much experience with this sort of things, however I do understand them, but I can't figure out why there is that xor 0x7B.
## Post #40
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2011-10-16T16:18:18+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

The actual list of files inside the chunk/bundles is inside the bom.fb2 file. Its an archive (ZIP) that have .rm files for every file in the Data directory, this files seems to be a meta files, describing the files inside the sb/chunk archives. The bom.fb2 archive from the beta can be found [here](http://www.mediafire.com/?ggjcpdt5docsadg).

The RM files seems to have a name, sha, offset, type,size,decSize,salt and few others.
## Post #41
- Username: Orion
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 30, 2011 12:29 am
- Post datetime: 2011-10-21T21:11:16+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Hey, I'm trying to work with the files in the real game now that they've been released.  I'm looking through the TOC files - why do you say there are 257 bytes of magic?  I only see 256 bytes enclosed between the two bytes 120 (ASCII x).
## Post #42
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-25T14:44:06+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Any progress on it since the full game is out?
## Post #43
- Username: RGGZOR
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 30, 2011 5:38 pm
- Post datetime: 2011-10-27T20:33:43+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Is there any way to extract images(textures)?
## Post #44
- Username: mitsuhiko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 29, 2011 9:30 pm
- Post datetime: 2011-10-29T13:33:28+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from OrangeC
>
> Any progress on it since the full game is out?

This is how far I currently am in regards to reading all the files: [https://github.com/mitsuhiko/frostbite2-stuff](https://github.com/mitsuhiko/frostbite2-stuff)

The dumpall.py script dumps all the data files that are in the .cas files but that alone does not give you too much. The files are named by their content hashes and the top up at around 110.000 files. So there is still a lot of stuff that needs to be done.

The libsb.py file also has ways to read the actual .sb/.toc files and to decrypt files by themselves. The bom.fb2 file for instance is just a XOR encrypted zip file which contains of more .m files which are of the same format as the .sb/.toc files but I did not manage to read them properly so far. As it seems there are some unimplemented type codes and handling of blobs is wrong.

If someone wants to have a look at that, every help is appreciated.
## Post #45
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-30T02:34:46+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

I used both python scripts with both versions 272 and 322 but they don't work on the sb/toc files.

322 gives me a module not found error on string IO import. 277 version does nothing.
## Post #46
- Username: mitsuhiko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 29, 2011 9:30 pm
- Post datetime: 2011-10-30T11:33:24+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

It only works with Python 2.x. So that's expected. The libsb.py file is a library not an application. You have to use it from an interactive Python shell or a script.
## Post #47
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-11-01T15:54:30+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Oh, hopefully someone implements it into a sb extraction tool.
## Post #48
- Username: mitsuhiko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 29, 2011 9:30 pm
- Post datetime: 2011-11-03T22:33:12+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from OrangeC
>
> Oh, hopefully someone implements it into a sb extraction tool.

The SB files are not that interesting in retail but it already can do that. Most data is in the CAS files. For those a script is provided now.
## Post #49
- Username: Duck
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 06, 2011 1:41 am
- Post datetime: 2011-11-05T16:19:19+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from mitsuhiko
>
> The SB files are not that interesting in retail but it already can do that. Most data is in the CAS files. For those a script is provided now.
Huh? I have only sb files and no cas files. All the goodies are in the sb files.
## Post #50
- Username: nickcas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 06, 2011 11:50 pm
- Post datetime: 2011-11-06T16:26:33+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

For those who do not want to mess with python, I created a small app to decrypt/re-encrypt the encrypted (DICE Header) files. Thanks to Rick for the crypto routine.


Edit: Works with Xbox and PC, haven't tested anything else. Also if in wrong section please move.
[Battlefield 3 Editor.rar](https://xentaxbackup.github.io/file/4828_Battlefield 3 Editor.rar)
## Post #51
- Username: RGGZOR
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 30, 2011 5:38 pm
- Post datetime: 2011-11-08T08:13:50+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

You know where to find the files.dds?
## Post #52
- Username: Ponderance
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 10, 2011 6:42 pm
- Post datetime: 2011-11-10T10:45:01+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Been trying to open up the .cas files, myself.  Assuming that the sounds are in there (for the final release of BF3.)  I assumed that it would just be a standard archive file of one format or another but I'm realizing after days of snooping around off and on, this is proving to be much more complicated than the vast majority of other games I pretty much got right in to.  

Must hear audio samples without the rest of the layers of the game!
## Post #53
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2011-11-10T18:31:58+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

The contents of this post was deleted because of possible forum rules violation.
## Post #54
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2011-11-13T09:33:26+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

The contents of this post was deleted because of possible forum rules violation.
## Post #55
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-11-14T17:35:26+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

it is not surprising, since it uses same game engine with Battlefield 3.
## Post #56
- Username: TonyRPG
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 02, 2011 11:20 am
- Post datetime: 2011-12-02T03:24:16+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Someone has been able to extract the sounds of the weapons?
## Post #57
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-12-02T16:40:58+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

That is not possible as of this time due to custom EA audio format being used.
## Post #58
- Username: MichaelJim
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 08, 2011 1:08 am
- Post datetime: 2012-01-07T14:31:14+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

anyone extracted images from the bf3 archives?
## Post #59
- Username: XStalker
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Sep 16, 2010 9:28 pm
- Post datetime: 2012-01-11T16:29:39+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

Anyone found how to open/extract/ or edit the SB files? im talking about the UI.sb from Battlefield 3\Data\Win32 folder.

Opened it with wordpad trying to find something about spectator mode, and there are some spectator lines in it. Wondering if we could activate spectator mode from it.
## Post #60
- Username: hpqeungfw
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 09, 2012 11:38 pm
- Post datetime: 2012-01-14T11:26:42+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

@mitsuhiko
im not very into Python, can you explain how to use your files?
running dumpall does nothing.
I use Python 2.6
## Post #61
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-07-27T09:00:26+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

So, can anybody please guide me, how to extract texture data from .sb - .toc files.

I have read the whole thread, and quite confuse.
## Post #62
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-07-30T17:15:20+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

I have extracted .sb and .toc file from XBOX 360 "Battlefield 3 HD texture pack" which I downloaded from xbox360iso.com

You can download the sample .sb and .toc from :- [http://www.mediafire.com/?lxjqisoduepy36f](http://www.mediafire.com/?lxjqisoduepy36f)

I have used "wx Pirs" to extract .sb and .toc from XBOX 360 data file.

If anybody please try to extract texture data from this .sb file would be great.

Please please... make a bms script to extract data from this .sb file.
## Post #63
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-06T14:14:00+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

[http://aluigi.org/papers/bms/frostbite.bms](http://aluigi.org/papers/bms/frostbite.bms)
## Post #64
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-03-06T18:51:20+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

> Reply from aluigi
>
> http://aluigi.org/papers/bms/frostbite.bms
## Post #65
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2013-06-21T18:57:43+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

This "frostbite.bms" works great on sb and toc file. 
But after extracting data from sb file I got some unknown files.

So can any body guide me how to extract texture from these files.



The mp_subway file is 3,783 KB. So may be this file contains the texture data.

Please Help
## Post #66
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2015-08-23T19:55:56+00:00
- Post Title: Re: Battlefield 3 PC Beta .SB archives

someone can help please 
i try extract sound voice
