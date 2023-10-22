## Post #1
- Username: TomatoJuice17
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 18, 2019 2:10 am
- Post datetime: 2019-05-18T23:39:14+00:00
- Post Title: SDD header (Just Dance 2015-2019 Wii)

I'm trying to create my own textures for JD2019, but when I open the .tga.ckd files in HxD, the header instead of saying DDS says SDD, and when I open it in Photoshop or Paint.net it opens with error.

someone has a solution?


This is what the header looks like: 



SDD Header example.PNG (1.72 KiB) Viewed 131 times
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-05-21T01:15:55+00:00
- Post Title: SDD header (Just Dance 2015-2019 Wii)

you must provide samples for examination.
## Post #3
- Username: TomatoJuice17
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 18, 2019 2:10 am
- Post datetime: 2019-05-25T13:32:04+00:00
- Post Title: SDD header (Just Dance 2015-2019 Wii)

> Reply from Acewell ↑Tue May 21, 2019 9:15 am at Tue May 21, 2019 9:15 am
>
> 
you must provide samples for examination.
1)  Here is an example of the textures of Havana:
[http://www.mediafire.com/folder/fg3nosd ... 20textures](http://www.mediafire.com/folder/fg3nosdzarr0d/Havana%20textures)

2) I opened the textures with your JD2018 script for Noesis, and when I combine them by hand or modify these textures, and open them in Noesis or Dolphin, they come out corrupt and duplicated:




Captura.PNG (55.62 KiB) Viewed 111 times


I need to know how to correct this error  


PD: I'm making a VIPMADE mod, that's why I'm modifying the textures.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-05-26T02:08:53+00:00
- Post Title: SDD header (Just Dance 2015-2019 Wii)

modding is not my area so i can't help you with putting the modified texture back into the game,   
but exporting the ckd textures from Noesis as dds and combining the alpha layer with the color layers is easy
in Photoshop, just open the color image dds and alpha image dds and add alpha channel to color image 
(if it doesn't already have one) then select all of alpha image and copy it to alpha channel in color image.
## Post #5
- Username: Miner737
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 16, 2021 3:20 am
- Post datetime: 2021-01-15T19:37:34+00:00
- Post Title: SDD header (Just Dance 2015-2019 Wii)

try renaming them
