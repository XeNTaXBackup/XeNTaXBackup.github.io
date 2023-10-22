## Post #1
- Username: monoag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 01, 2006 8:22 pm
- Post datetime: 2006-05-01T12:54:03+00:00
- Post Title: Virtua Fighter 2 PC

An oldie but a goodie! I've been recently fiddling with the bitmap backgrounds in an attempt to make this game look a wee bit mroe up to date. And they aren't turning out too bad either! But I'd like to have a crack at doing the same with the character textures... which are in a .bin format. I've had no luck opening them with other programs, so thought I'd make a request here! Hope you can help!
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-01T13:10:05+00:00
- Post Title: Virtua Fighter 2 PC

I would need one or 2 of these binfiles for analyzation before i can
say anything =D
## Post #3
- Username: monoag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 01, 2006 8:22 pm
- Post datetime: 2006-05-01T13:22:38+00:00
- Post Title: Virtua Fighter 2 PC

I tried to attach the files, but this site won't let me attach .bin files. If you PM me your email, I'd be happy to send a few files your way. Ta!
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-01T15:07:55+00:00
- Post Title: Virtua Fighter 2 PC

Results so far. its a proprieatry format without header.
there is not even information about the dimensional size or depth
used by the pictures. 

and i dont know if these are Black&White images or if
they use colors. but this is what ive got out so far from
one of the bin files.

Edit: also I had to skip the first byte of the image in order
to view them correctly. and there is another image
right after this first one, that is in the resolution
of 144x100<--something

whats funny is that they are stacked ontop of eachother, and nothing that shows that they are separate. so my guess is that the engine is hardcoded for this textureformat for the face files.

i would need more Player faces files to check if this is true though. :O
[rip1.gif](https://xentaxbackup.github.io/file/729_rip1.gif)
## Post #5
- Username: monoag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 01, 2006 8:22 pm
- Post datetime: 2006-05-02T00:30:42+00:00
- Post Title: Virtua Fighter 2 PC

I have no idea why it is black and white! The game uses different textures for both 256 and 16-bit colour modes, so maybe that has something to do with it? The pic you showed looks like a profile i on the character select screen. I've attached a few more face files for you. Thanks again!
[vf2faces.zip](https://xentaxbackup.github.io/file/733_vf2faces.zip)
## Post #6
- Username: monoag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 01, 2006 8:22 pm
- Post datetime: 2006-05-02T01:03:51+00:00
- Post Title: Virtua Fighter 2 PC

Hey Strobe- I've also emailed you all the files I think relate to the character Akira (file size too big to post). Perhaps there is some more useful stuff contained in them? Apart from that, not really sure what files I should be looking at. Ta!
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-02T06:57:57+00:00
- Post Title: Virtua Fighter 2 PC

Testing some stuff here. i am still only able to extract 16 bit textures as black and white. they must have some sort of palette data hidden somewhere,
but i dont understand why they would create palette data for 16 bit images? :/

also, ive solved a problem why some of the textures where so damn scrambled and unreadable.......Because they where soundfiles =D
[untitled.zip](https://xentaxbackup.github.io/file/734_untitled.zip)
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-02T06:59:46+00:00
- Post Title: Virtua Fighter 2 PC

> The game uses different textures for both 256 and 16-bit colour modes, so maybe that has something to do with it?

aaaaaaa, that could be it. maybe they have the same textures for
the both modes. but they might be read differently.....hmmmms...
## Post #9
- Username: monoag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 01, 2006 8:22 pm
- Post datetime: 2006-05-03T00:03:14+00:00
- Post Title: Virtua Fighter 2 PC

lol Akira's voices sound funny when all played at once! Silly me only sent  you files from the main VF2 folder and not the Model2 and Pctex subfolders.... both of which sound pretty useful to me! The game uses 2 different model kinds based on whether you choose "original" (Saturn versions) or "model2" (arcade versions), so I think that maybe these folders correspond to these setups? They both have "256" and "65536" subfolders, which I assume is for the colour depth. Anyway, I've emailed you samples from both the model2 and pctex folders, see what you think!

btw a demo of the game is available from:

[http://www.gamespot.com/pc/action/virtu ... id=2531770](http://www.gamespot.com/pc/action/virtuafighter2/download.html?sid=2531770)

As long as the link still works anyway!

Thanks again, you're doing great!
## Post #10
- Username: monoag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 01, 2006 8:22 pm
- Post datetime: 2006-05-13T12:52:27+00:00
- Post Title: Virtua Fighter 2 PC

Hi Strobe,
Just wondering if you had any luck extracting any textures from the files I sent- If so, how do I go about accessing them myself? Thanks!
## Post #11
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-15T03:42:18+00:00
- Post Title: Virtua Fighter 2 PC

Ive been looking and extracting, and hexxing, and importing as raw in
photoshop. i still only get black and white pictures =(

they must store the palette data somewhere else.
I dont know why they store the 16bit textures as palettized images =(

once i get hold of the colors i could possibly create a converter
for them ://
## Post #12
- Username: monoag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 01, 2006 8:22 pm
- Post datetime: 2006-05-17T22:08:02+00:00
- Post Title: Virtua Fighter 2 PC

Hmm odd! Again, I really have idea what files to send over. Did that vf2 demo link work? Maybe there is a .bin of use in that. 
VF2 doesn't work when the desktop is in 32bit colour, even when using the direct 3d patch. I have no real idea, but maybe this has something to do with the palette thing? Or it could be due to the fact that it's based on the Saturn version perhaps?
Thanks again!
## Post #13
- Username: monoag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 01, 2006 8:22 pm
- Post datetime: 2006-06-23T00:50:10+00:00
- Post Title: Virtua Fighter 2 PC

Just thought I'd check again to see if you've had any luck- or if its pretty much impossible. Ta!
