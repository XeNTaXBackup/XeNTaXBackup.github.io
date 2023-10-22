## Post #1
- Username: Lecht
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 02, 2012 11:33 am
- Post datetime: 2012-01-02T03:45:18+00:00
- Post Title: Working on Tales of Xillia

Progress so far: [http://i.imgur.com/LHJL1.jpg](http://i.imgur.com/LHJL1.jpg)

There's a few issues with some of the extracted language files being incomplete. For the most part I used chrrox's quickbms script to extract the language file. But a few proprietary tools of my own to translate the text, and then rebuild the other files.

Hopefully I can figure out what's going wrong with the script. If anyone knows of an MSF compression C# library let me know .
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-03T11:27:03+00:00
- Post Title: Working on Tales of Xillia

are you talking about this? 
[http://www.codeproject.com/KB/files/CAB ... tract.aspx](http://www.codeproject.com/KB/files/CABCompressExtract.aspx)
## Post #3
- Username: Lecht
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 02, 2012 11:33 am
- Post datetime: 2012-01-03T18:58:00+00:00
- Post Title: Working on Tales of Xillia

hehe not quite. That's microsoft's cab algorithm. MSF is much different. I do have a few leads that it might be LZMA compression or some variation of it, but thanks for the reply and trying to help. I'm getting closer to figuring it out. 

Evidently MSF is encrypted with a xor table, I've implemented it in my code. It seems a game called RaiderZ has a file that's encrypted/compressed with MSF. I'm not entirely sure if it's the same algorithm that Tales of Xillia uses though. However the xor look up table is 65536 in size, and the last 4 bytes before the encrypted data in the Tales of Xillia MSF file = 65536.
## Post #4
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-03T19:08:14+00:00
- Post Title: Working on Tales of Xillia

[Universal Extractor](http://legroom.net/software/uniextract) has support for a number of interesting/obscure formats; have you tried it on the archive(s) (I only bring this up because you make it sound like the MSF format isn't just another one-off, game-specific format)?
## Post #5
- Username: Lecht
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 02, 2012 11:33 am
- Post datetime: 2012-01-04T07:46:43+00:00
- Post Title: Working on Tales of Xillia

Thanks, but I think I've got it. Thanks to Luigi, I've converted his MSF algorithm to C#. If anyone is interested, the code is here: [http://pastebin.com/C9GFjiZF](http://pastebin.com/C9GFjiZF) . Note: I take absolutely no credit for this code except for converting it to C#, the method behind the madness is 100% Luigi.

My program is querying the hell out of google translate right now to translate the japanese. Got my fingers crossed that this stabilizes the game and fixes the (null) errors. Will post again in a few hours to let you guys know what happened.
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-04T10:14:44+00:00
- Post Title: Working on Tales of Xillia

lol sorry. I got confused becase the CAB header is MSCF and plus because the tales of in the wii/gamecube versions uses that compression
## Post #7
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-04T10:54:19+00:00
- Post Title: Working on Tales of Xillia

how are querying Google translate if they shutdown their API, or are you using raw http requests and parse the result manually?
## Post #8
- Username: Lecht
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 02, 2012 11:33 am
- Post datetime: 2012-01-04T18:20:58+00:00
- Post Title: Working on Tales of Xillia

Yeah, I'm just using http get and parsing the json array that google returns. Here's the code if you're interested: [http://pastebin.com/KFUvJLDE](http://pastebin.com/KFUvJLDE)

Also the code there, it's hardcoded for japanese -> english. And it uses my custom WebSession class, which you can just use a simple WebClient then call DownloadString().

Forgot to include progress lol.

Well turns out my language file re-builder is off in a few places, I'll be correcting those issues shortly. Progress report later on.
## Post #9
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-04T22:11:08+00:00
- Post Title: Working on Tales of Xillia

thanks for that,
I'm a tales fan myself and I wonder what you're doing...
## Post #10
- Username: Lecht
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 02, 2012 11:33 am
- Post datetime: 2012-01-04T22:41:35+00:00
- Post Title: Working on Tales of Xillia

Looks like everything was a success .

[http://i.imgur.com/2wkMR.jpg](http://i.imgur.com/2wkMR.jpg)

[http://i.imgur.com/qqDAi.jpg](http://i.imgur.com/qqDAi.jpg)

I'm going to playtest it for a bit, and see if everything is stable, but it seems to be great.

drfail, I'm working on translating Tales of Xillia to English.
## Post #11
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2012-01-04T22:56:32+00:00
- Post Title: Working on Tales of Xillia

> Reply from Lecht
>
> Looks like everything was a success .

epic

> drfail, I'm working on translating Tales of Xillia to English.

you have a PM
