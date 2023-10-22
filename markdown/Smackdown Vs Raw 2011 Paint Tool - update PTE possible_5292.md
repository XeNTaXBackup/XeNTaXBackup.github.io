## Post #1
- Username: TZC
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jan 29, 2010 6:20 pm
- Post datetime: 2010-10-25T09:36:19+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

I wasn't sure if to carry on the old thread or not. 
But if this goes anywhere, I guess it'd be best to have the two split.


I'm hoping (without any idea) that it wouldn't be too much work to modify the PTExplorer for sdvr1010 to work on 2011.

There's 10 new slots this year from 20 to 30 and it seems that while you can import pictures still, they're garbled.


I've got a paint tool file from the new game attached- it isn't mine though Archer on .ws posted. I imagine all the slots are full because someone asked him to fill them but I can't look- I don't have the game yet..

If you could take a look it's greatly appreciated. Transparency options in caw mode have been taken out this year so, the paint tool hack if it worked, would be even more useful than before.
[SVR2011_00PaintTool.zip](https://xentaxbackup.github.io/file/3552_SVR2011_00PaintTool.zip)
## Post #2
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-10-28T06:24:58+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

I've taken a look at the file and the format of the texures is different. I have managed to successfully inject textures into the file but the game detects that the file has been tampered with and asks to create a new paint tool file. It then deletes the old file. My experiments so far:

1. Injected a texture and didnt resign the pt file. Game states that it can't access the file. 
2. Injected a texture and resigned/rehashed the pt file. Game states that the file is corrupted and needs to create a new file deleting the old one in the process. 
3. Tried using the reigned pt in caw mode without going into paint toll mode directly. The caw mode detects the old logo's in the pt file and not the injected ones. 
4. Reisgned and rehashed somone else's pt file and the game reads the file perfectly. Good news is that you can share your pt files with others. 

This leads me to beleive that there is a custom checksum somewhere which detects wether you tamper with the images in the pt file. changing the profile id and machine id works though.
## Post #3
- Username: bms
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 28, 2010 11:11 pm
- Post datetime: 2010-10-28T22:07:25+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

I've tried everything too and from now we can't do anything. We need an update to ptexplorer.

Hope it'll come soon!!
## Post #4
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-10-29T10:32:29+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

I've been coding support for pt files into xpacker. Injection, extraction isn't that difficult. The problem as I mentioned is that the game reports the file as corrupt when you inject custom textures into it. 

I'm not an expert on hashing and xbox saves but there must be a checksum in the file which is telling the game that something has changed. brienj or someone with more expertise in this area might be able to help:
## Post #5
- Username: Zig Zaggin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 11, 2010 8:27 pm
- Post datetime: 2010-11-05T05:59:11+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

Any progress?
Would we be able to just change the profile and machine I.D's then resign and rehash to use it in the mean time?
## Post #6
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-11-06T20:04:35+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

From what I've heard, Mr. Mouse said the format is different this year.  That's the problem, I would imagine.

If there is a check of some sort, which is possible, but doubtful, I can look into it later.  Once Mr. Mouse has the format for 2011 figured out, we can go from there.
## Post #7
- Username: Jezzes101
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 17, 2010 2:18 am
- Post datetime: 2010-11-12T05:08:37+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

something I've notice while trying it out with the current PT Explorer version is that when you get the game save, its around 8 megs in size, once you edit it and save the edit (before rehashing it) the new saved file is lowered to around 2 megs.

Is there a connection with that and to why Modio wont rehash/resign it?
## Post #8
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-11-14T16:01:27+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

The file format is different from last year. I can view, extract and inject but the ame doesn't read the edited files. The format doesn't have an alpha channel and seems to store the alpha information in the image itself. I seems to use black to indicate to the game what is transparent. 

I'm not certain how it distinguishes between black which should be visible though. I've attached two files, the first is meant to be transparent outside the white box but black inside the white box. The second is meant to be completly transparent except for the white lightning design. 

Anybody have any idea how to save the file in same format?
[pt.rar](https://xentaxbackup.github.io/file/3605_pt.rar)
## Post #9
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-11-15T05:09:50+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

Been experimenting more and I've created a file using paint.net (dxt5 with no mip maps). I then manually replaced the alhap values in the file using a hex editor to match the original file. The new file is identical to the old in the hex editor but when I inject the file into the paint tool file, the game still doesn't load it. 

I think there is another check in the paint tool file which the standard rehasher/resigner doesn't take care off. I've attached the two files.
[pt2.rar](https://xentaxbackup.github.io/file/3608_pt2.rar)
## Post #10
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-11-16T07:31:00+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

Managed to get the textures into the paint tool but using a very complex method to do it. Posted some pics on my site:

[http://sf4mods.blogspot.com/2010/10/hul ... -2011.html](http://sf4mods.blogspot.com/2010/10/hulk-hogan-caw-svr-2011.html)

still not having any luck injecting the images directly into the paint tool file.
## Post #11
- Username: Zig Zaggin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 11, 2010 8:27 pm
- Post datetime: 2010-11-16T14:17:18+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

Keep us posted
## Post #12
- Username: Jezzes101
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 17, 2010 2:18 am
- Post datetime: 2010-11-17T08:00:29+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

omg.....you did it............plodtrew your a freaking genius  long way or not I hope you show us how to do this  trust me its by far much appreciated that your working hard to crack this
## Post #13
- Username: dmasta
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 25, 2010 6:26 pm
- Post datetime: 2011-01-15T11:26:23+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

Any updates on this matter so far? Mr. Mouse have you looked into this or do you plan on updating the PTExplorer from last year?
## Post #14
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-01-20T11:54:43+00:00
- Post Title: Smackdown Vs Raw 2011 Paint Tool - update PTE possible?

No one has been able to recreate the paint tool dds files in the correct format for the game. It seems the game generates it's own dds file format. It's readable on the pc but I've failed to recreate the files with any of my graphics applications. I have been able to get textures into the paint using another method but it only works for jtag users:

[http://sf4mods.blogspot.com/2010/10/hul ... -2011.html](http://sf4mods.blogspot.com/2010/10/hulk-hogan-caw-svr-2011.html)

[http://sf4mods.blogspot.com/2010/10/gol ... -2011.html](http://sf4mods.blogspot.com/2010/10/goldberg-caw-svr-2011.html)
