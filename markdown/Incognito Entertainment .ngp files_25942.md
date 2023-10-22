## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-10-28T14:30:24+00:00
- Post Title: Incognito Entertainment .ngp files

When trying to export some twisted metal black files, i noticed that the .ngp .tex .rtt structure seems to be similar across the few other games they produced.
Attatched are 2 .ngp files from war of the monsters and downhill domination:
[https://cdn.discordapp.com/attachments/ ... iclops.zip](https://cdn.discordapp.com/attachments/553220665692651542/1035560118319845487/Kineticlops.zip)

the files contain the same model of kineticlops from both games each:


i tried a twisted metal tool for .ngp and it seems to do something and then dies.

could you guys please have a look at this?

thanks for reading and nice weekend
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-31T17:45:23+00:00
- Post Title: Incognito Entertainment .ngp files

Used offzip on the smaller ngp and got a ncp file. Some small point clouds contained (using byte face indices (not supported by H2O, btw) at no avail):
.



unzipped2nfc.jpg (77.04 KiB) Viewed 140 times

(Biggest sub mesh with around 188 vertices)
## Post #3
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-11-03T05:51:07+00:00
- Post Title: Incognito Entertainment .ngp files

> Reply from shakotay2 ↑Tue Nov 01, 2022 1:45 am at Tue Nov 01, 2022 1:45 am
>
> 
Used offzip on the smaller ngp and got a ncp file. Some small point clouds contained.

Ouuuhhh nice!
Thanks for the start! Imma See If i can fiddel around with that now.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-20T01:18:07+00:00
- Post Title: Incognito Entertainment .ngp files

> Reply from Henchman800 ↑Thu Nov 03, 2022 1:51 pm at Thu Nov 03, 2022 1:51 pm
>
> 
Ouuuhhh nice!
Thanks for the start! Imma See If i can fiddel around with that now.Haha, seems you didn't fiddle any minute, did you?

Fact is, I gave a wrong FVFsize, sorry for that; it's 16, not 12.

From the .ncp file (NOT .ngp) I gathered 6 sub meshes (there may be 3 more or so) then used a point cloud skinner:
.



KCLOPS.png (55.16 KiB) Viewed 65 times



btw: the twisted metal tool you mentioned in the OP expects a .vram file after you dragged&dropped KCLOPS.NGP onto it:
'Could not find file 'D:\...\NGP\KCLOPS.vram'.'

And this is what daemon1 wrote:
"Corresponding .VRAM file must be in the same folder".
## Post #5
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-08-24T06:56:16+00:00
- Post Title: Incognito Entertainment .ngp files

> Reply from shakotay2 ↑Sun Aug 20, 2023 9:18 am at Sun Aug 20, 2023 9:18 am
>
> 
Haha, seems you didn't fiddle any minute, did you

Its on "the list" haha
Very busy with yt at the Moment and irl Jobs.
But i linked the thread Here to a Kid in the Forum wanting to dig deeper.
Very cool to hear from you though this messge again fellow shakotay 2
