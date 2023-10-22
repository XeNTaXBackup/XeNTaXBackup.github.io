## Post #1
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-03-02T05:25:19+00:00
- Post Title: Unity .model

Sorry if this is been approached before but not being able to find is part of the problem as I'll illustrate. I run into common Unity files as do you of course, .43 being one. I can open that in a variety of programs just fine. The other common are ones with the extension .model. As a common keyword and one that of course is just the generic for 3d types period I can't seem to find squat out about it. Other engines tend to have things like this, TMNT Secret Of The Ooze for example uses the same filename yet I doubt is a related file. Still makes searching and Googling it difficult. Thanks anyone who replies. I will provide an example if needed but figure it's commonplace and anyone has run into it already. Also as a sidenote yet related anyone have any luck with the official Unity engine and game maker/editors? I've had it for over a year now, licensed and still I can import it's filetypes yet do nothing with them much less never even see a preview or something.
## Post #2
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-03-11T12:45:00+00:00
- Post Title: Unity .model

Sorry, I had my drive tied up doing something for my mums. Here's a sample, the title character from Hello Kitty Cruisers for Wii U. Unlike the Kart series the driver model seems to be separate from the vehicles which are .43 files instead.
[https://onedrive.live.com/?authkey=%21A ... 051B80B2EF](https://onedrive.live.com/?authkey=%21ALhBPJE4ALrwbn8&id=756B9A051B80B2EF%21687&cid=756B9A051B80B2EF)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-13T06:26:44+00:00
- Post Title: Unity .model

HelloKitty_Standing.mesh ?  



HelloKitty_Standing_mesh.png (53 KiB) Viewed 154 times
## Post #4
- Username: tr1cky
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Oct 05, 2017 8:01 pm
- Post datetime: 2018-03-13T17:13:39+00:00
- Post Title: Unity .model

brilliant models thx
## Post #5
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-03-15T11:25:25+00:00
- Post Title: Unity .model

Kewl. So any to go from there to a script? Coding isn't my strong suit and I've never been able to use that program properly despite a year or better of trying to learn. Ty, the intention is to distribute them for modders as well cobble up some mods for Mario Kart.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-15T18:13:12+00:00
- Post Title: Unity .model

> Reply from SickAlice
>
> Kewl. So any to go from there to a script?you'll need a formula to calculate the offset address of the vertex block. I came thus far:
size  of face indices block at 0x40: 0x4CF8
first address after FI block at 0x44 + 0x4CF8 = 0x4D3C
DWORD 0x848= 2120, vertex count
0x4D40 +2120x32= 0x4D40 + 0x10900 = 0x15640

then stumbled over the unknown offset (0x15B20 - 0x15640):
unknown offset 0x4E0= 1248
to start address of vertices at 0x15B20
## Post #7
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-03-16T02:47:17+00:00
- Post Title: Unity .model

I believe in learning to fish as much as the rest but I went through all this more times than I count and still failed. I'm only on polynomials in school myself to get a picture of my level and more studied and leaned to artistic skills whereas the calculation side has been neglected.
## Post #8
- Username: tr1cky
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Oct 05, 2017 8:01 pm
- Post datetime: 2018-03-17T16:13:43+00:00
- Post Title: Unity .model

> Reply from AceWell
>
> HelloKitty_Standing.mesh ?  
HelloKitty_Standing_mesh.png

you uploading hello kitty by any chance plz
