## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-26T00:01:59+00:00
- Post Title: Revelations(Megami Tensei): Persona (SGB spritesheet PSX)

[Devil Sprite Sheet Archive](http://www.megaupload.com/?d=UB9X4BHE)

Now I'm uncertain why PSicture does not load them as they seems to be standard SGB0 (In the respect that PSicture was able to read the others) images and are not compressed it seems in any way. But when I do try to view them I get an error so somthing is off one way or another.

Originally I submitted this to the author of PSIcture who many may know now is has sunk into obscurity before he could fix up a plugin.

Thanks anyone who helps, this has been a request I made around 3-4 years ago and did not pick it back up until now.

-Darkfox
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-28T02:11:58+00:00
- Post Title: Revelations(Megami Tensei): Persona (SGB spritesheet PSX)

Here is a single SGB file that I extracted from inside the BIN.
[SGB.rar](https://xentaxbackup.github.io/file/1107_SGB.rar)
## Post #3
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-28T09:02:26+00:00
- Post Title: Revelations(Megami Tensei): Persona (SGB spritesheet PSX)

If you write "standard SGB0" image, do you know of a format description somewhere? I can identify the image data in the file you posted, but I do not yet know what to do with the rest of the information (which probably contains a palette of some sort).
[sgb.jpg](https://xentaxbackup.github.io/file/1110_sgb.jpg)
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-28T16:29:24+00:00
- Post Title: Revelations(Megami Tensei): Persona (SGB spritesheet PSX)

Well I use that term because others such as the magic animations were read correctly by PSicture so they must also be used elsewhere in other games. The rest are like this. I know this because I used a hex editor to look at them and they too seems to be SGB0s.

Also, yeah, that other stuff seems to be a palette. I believe these can take on more than one palette which could be confusing. O_o
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-29T12:16:45+00:00
- Post Title: Revelations(Megami Tensei): Persona (SGB spritesheet PSX)

Current theory: starting from offset 8, there might be four uint16 values specifying numbers of entries. I would guess that four types of blocks follow, where the the first three are filled with structures of size 8 and the fourth has structures of size 4. That would match the values in the header.
No idea yet for the rest of the file or the meaning of those blocks, though ...
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-04-12T06:16:16+00:00
- Post Title: Revelations(Megami Tensei): Persona (SGB spritesheet PSX)

Hmm. Possible. But I'm pretty certain the palettes are in there too at the top. Hm, tough call.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-12-12T17:42:36+00:00
- Post Title: Revelations(Megami Tensei): Persona (SGB spritesheet PSX)

Sorry to bump. Just there has been no updates for a while and Atlus' format continues to be elusive. Perhaps somebody could fill in the gaps of the data? Like what format the palettes are and the like?

Perhaps some of the extra data on the SGB files is animation data. Not sure.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-02-22T03:11:58+00:00
- Post Title: Revelations(Megami Tensei): Persona (SGB spritesheet PSX)

Sorry again to bump, I am still not certain of this format. Though the confusing bytes are certainly the palette.
