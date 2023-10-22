## Post #1
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-09-04T21:36:30+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

Hello everybody! The .xessb file from Spider-Man 3 (X360) is an FSB3 file that contains XMAs.
The problem is: I used fsbii to extract the archives and it gives me several "embedded_(offset)".fsb and I convert them with towav, but they cut off just too fast, for example there's a file that have to be 1 minute longer. I think it's somehow corrupted.

Link: [https://mega.nz/#!GgcUgKaS!3b9BZv3xSDxw ... HEXrb3LXLQ](https://mega.nz/#!GgcUgKaS!3b9BZv3xSDxwUotMC4pnw257ra1uEyTg3HEXrb3LXLQ)

Thanks in advance.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-09-05T14:21:13+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

You have to manually cut the files at the FSB headers using VGMToolbox.

I've attached an XML plugin file you can put in the plugins\AdvancedCutter folder of VGM Toolbox

There are six FSB files in that FSB but you only need the three biggest ones from it. Just delete the smaller sized FSBs as you won't need them.

After that, just convert them using ToWAV 
[FSB_Cutter.zip](https://xentaxbackup.github.io/file/9684_FSB_Cutter.zip)
## Post #3
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-09-05T14:33:17+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

I posted a lot of threads and you helped a lot, thank you. Anyway is there a problem? The files start and end strangely and there are 5 FSBs inside the .xessb while only 3 are converted.
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-09-05T19:09:03+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

Forgot to mention that when you use the FSB cutter, make sure the box down the bottom "Cut to EOF when Terminator Not Found" is ticked. That will give you the six of them.

They should all convert fine. There's nothing missing when they convert. That's all there is to them. Not sure why they are even there in the first place.

Two of the smaller FSB files are just the first 20 seconds of the longer versions. The smallest FSB isn't even 1 second long and it's the start of one of the three larger files.

Regardless, you only need the three biggest FSB files like I've uploaded.

[FSB files](http://www7.zippyshare.com/v/acNmXayB/file.html)
## Post #5
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-09-05T21:03:47+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

Thank you very much.
## Post #6
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-09-05T21:25:42+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

Do you know if the files have to be joined or it's single loopable?
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-09-06T00:16:29+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

They're not so much sequenced as they could be segmented but loopable all on their own. For this game I think the filenames (after running the FSBs through ToWAV) give an indication of the order with the numbers.
## Post #8
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-09-06T07:15:24+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

For Bolt it was easy, I had for example "MX_Action_1_LOOP" and I had to merge "MX_Action_1_START" , "MX_Action_1_LOOP" and "MX_Action_1_END".
For this game there's a MX_MB03 for example but when I search there's only one MB03 filename so the start and end is a completly different filename..
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-09-06T09:16:47+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

Look for files named MX_MB02 or MX_MB04.

I don't think there are 'start, loop, and end' parts but there might be multiple loop parts e.g. MX_MB02, MX_MB03, MX_MB04 that could all be part of the same track/level but for different areas of the game.

If there are files like that but they don't sound correct when put together, I'd suggest leaving each part on its own and looping them individually.
## Post #10
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-09-06T09:48:57+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

I don't have MB04 or MB03.
## Post #11
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-09-06T11:04:08+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

I guess they're just meant to be individual parts that are looped then.
## Post #12
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-10-27T13:26:52+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

Sorry but there's other problem. For example I extract soundtrack_scorpion.xessb and it gives me 15 cutted fsb files. When I convert them with towav I have only 8 of them, but I want to convert all the files because some music are missing. Could you please help on this one?
## Post #13
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-10-27T14:50:06+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

Post the scorpion one here.
## Post #14
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-10-27T22:22:30+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

It's fixed, I just extracted one by one classed with folders, and I can join them. It's a mess in the filenames. Thanks Anyway.
## Post #15
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-10-28T09:59:58+00:00
- Post Title: Spider-Man 3 (.XESSB) 360

For example, the soundtrack_bank.xessb ; soundtrack_petty.xessh ; soundtrack_voluntary.xessb contains the same tracks in them.
But when I apply the script to the archive it gives 5 fsb files, but I can only convert 3 files, which is strange.
Now, I play the tracks and miss a lot of songs that plays in the Petty levels...
I don't have the track that plays 0:01 to 0:31, and I looked to all of the archives in the game and I can't find it so I think there's a problem with the script or I don't know... Look:

I only have these files:
[https://mega.nz/#!up9B2KRb!KZnADdiU-2eY ... CVHIBj56hk](https://mega.nz/#!up9B2KRb!KZnADdiU-2eYGR10pcZjpz9_Z2AsUj7eKCVHIBj56hk)
[https://mega.nz/#!P9sk3I7A!YV8PhR-d9ke7 ... X72-JA6SIg](https://mega.nz/#!P9sk3I7A!YV8PhR-d9ke7Eko1ngYF9M6FN5Uhw5BwQX72-JA6SIg)
[https://mega.nz/#!3osjFSBT!i0Yl5wBysI8d ... pDXFkY3vbM](https://mega.nz/#!3osjFSBT!i0Yl5wBysI8dEhwl8icTW2cWNeZg_aGDMpDXFkY3vbM)
## Post #16
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-10-29T14:07:38+00:00
- Post Title: Re: Spider-Man 3 (.XESSB) 360

And also, on PS3 I can't extract the files, I just don't have header.
[https://mega.nz/#!Sh9DQbhD!gLEttnFG-zcf ... a2o0ofECkc](https://mega.nz/#!Sh9DQbhD!gLEttnFG-zcf0FWlStbzW5cpLlUCvisq7a2o0ofECkc)
