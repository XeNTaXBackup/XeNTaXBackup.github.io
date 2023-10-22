## Post #1
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-09-28T06:11:34+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

I'm trying to edit a .NIF with NifSkope; my goal is to remove a railing barrier so that I can walk onto the battle circle. I have deleted the block that highlights the railing in green (Catwalk_A_Railing_Posts03 [204]) although upon loading the area in game, the client crashes. 

Even without making any changes, and just saving a new .NIF in NifSkope from the original causes a crash in game upon loading that area.

can anyone get back to me with a way to edit Wizard101 .NIF's without it crashing?

EXAMPLE NIF HERE:

[http://www.mediafire.com/file/5vak6ptvq ... _Arena.nif](http://www.mediafire.com/file/5vak6ptvq0b4hd9/MB_Arena.nif)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-28T19:48:35+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

> Reply from ReedSteed
>
> I have deleted the block that highlights the railing in green (Catwalk_A_Railing_Posts03 [204])dunno what you mean exactly; you could try to get the submeshes and "zero" their vertices in a hexeditor.



MB_Arena-nif.jpg (93.4 KiB) Viewed 90 times

(vertex block of displayed submesh from 0x22C7 - 0x417A)
## Post #3
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-09-28T23:00:19+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

[/quote] you could try to get the submeshes and "zero" their vertices in a hexeditor.
(vertex block of displayed submesh from 0x22C7 - 0x417A)[/quote]

I don't know much about NIFs...  I've kinda done that using notepad, instead, changing the names of the submeshes so that they'd be unrecognizeable, but that caused a different kind of crash. I will 0 out with a hex editor and post the results.

Here is a RAR containing the entire unmodified RIP in case anyone wants to do it for me 

[http://www.mediafire.com/file/99ore2ia8 ... +Arena.rar](http://www.mediafire.com/file/99ore2ia8fmhml2/Marlybone+Arena.rar)
## Post #4
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-09-29T00:46:12+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

RESULTS: 

I opened the NIF in a hex editor and have 0'd out all lines identifying the railing name; (if thats what you meant... if not can you do it so I can test?) still crashed. Same as editing the NIF in NifSkope. Should I try 3DS MAX? or any other suggestions?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-29T04:05:19+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

> Reply from ReedSteed
>
> RESULTS: 

I opened the NIF in a hex editor and have 0'd out all lines identifying the railing name; (if thats what you meant...nope, I spoke of vertices, not names. The zipped nif is to big to be appended; just zero the nif out like such:



MB_Arena-nif-zeroed.jpg (190.38 KiB) Viewed 77 times
## Post #6
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-09-29T04:19:45+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

> Reply from shakotay2
>
> nope, I spoke of vertices, not names. The zipped nif is to big to be appended; just zero the nif out like such:[/quote]... (not good at quoting)


That's what I did, but I only replaced the hex code referring to the railing (exactly what is highlighted in the original nif here) with zeros

Are you saying I should zero out the entire nif? Sorry, I don't know what vertices are exactly.
[Snipped.JPG](https://xentaxbackup.github.io/file/13356_Snipped.JPG)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-29T05:16:55+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

> Reply from ReedSteed
>
> shakotay2 wrote:nope, I spoke of vertices, not names. The zipped nif is to big to be appended; just zero the nif out like such:

> ... (not good at quoting) just delete the slash from the first tag: [ quote]quoted text[ /quote]
(and don't type the blanks after the '['; I just put them to prevent the tags from being executed)

> That's what I did,Nope, you did not. In the picture you posted  there's strings. 

> but I only replaced the hex code referring to the railing (exactly what is highlighted in the original nif here) with zerosDON'T zero out any strings.

> Are you saying I should zero out the entire nif?NO!
Simply read what I wrote: zeroes from 0x22C7 to 0x417A
(Where's the difficulty to understand what to zero out from the picture I posted?  )
## Post #8
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-09-29T05:34:05+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

> Simply read what I wrote: zeroes from 0x22C7 to 0x417A

yay^

Sorry, I didn't know what blocks were. Not too much hex experience.

I'll try it and post results.
## Post #9
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-09-29T07:34:36+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

Nope... zeroing out from 0x22C7 - 0x417A still caused a crash..

I have also opened the NIF in a hex editor and simply replaced one zeroed out block with the same zeros and saved the file for a test, and even that caused a crash in game! 

I'm almost sure it's something about the way these programs are saving modifications to the file.
## Post #10
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-10-03T00:39:41+00:00
- Post Title: Wizard101 NIFs edited with NifSkope causes crash in game!

*Bump dance*
