## Post #1
- Username: Mercen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 05, 2011 9:27 pm
- Post datetime: 2011-08-05T13:50:29+00:00
- Post Title: Corpse Party: Blood Covered Repeated Fear

Hopefully I put this in the right space....

Hiya! I brought this game back from a holiday in Japan - was a big fan of the original PC Corpse Party; and when I found this gem sitting on a department store shelf in Kyoto I grabbed it!

Now, because everyone could benefit from watching high school students die horribly, I'm working on translating it to English (and gleaning as much cool stuff as possible out of it). Naturally, I need some help...

I've managed extract the image.bin from the ISO, and got a look into it using a hexadecimal viewer... what I found was:

Map data is stored as .dat
Voice data is in Playstation's favourite format,  .vag
Image data is another old friend, .gim

Now, here are the tricky parts... 

There are MORE image files, but they've got a double extension I couldn't find any info on - .bmp.ata in name. I figure it's either additional encoding or padding, but I can't figure out how to get them out...

There are text files with the extension .lst - I'm pretty sure those are the text banks and the goal of this little endeavour, but again, I can't figure out how to get them out...

There are also .inc files. Dunno what these are.

Now, the whole thing appears to follow a standard filetree system - once decoded, the directory instructions read in pretty standard format...

TEXTURE/FACE/06_YUKA_L.GIM
SOUND/CHAP2/COP-SE019.VAG
TEXTURE/BS/YSE_BA01.GIM 

...and so on and so forth.

Now, there is some good news here - after some hunting around, and some invaluable threads on this very forum, I WAS able to get some gear out of this big file. Namely, I was able to extract all of the .vag files; and I have a converter handy. Still sifting through them (there's over three thousand!) and so far all I've found is sound effects and voiceovers. But, I did manage to find the creepy "Got Item" tone that plays - I've uploaded it to this thread as a treat and also proof I'm serious about this project. I also managed to extract several of the .gim files; but for some reason the only ones my scanner could lift are from the Game Over sequence. 

So, question time! Aside from the obvious "would anyone like to help me give an English patch to horror lovers everywhere", I'm looking for any and all assistance that can be offered. Once I can get into the text bank, I'm planning on translating it and then finding out how to make a patch with it; but first I need help getting in....
## Post #2
- Username: Mercen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 05, 2011 9:27 pm
- Post datetime: 2011-08-09T09:07:41+00:00
- Post Title: Corpse Party: Blood Covered Repeated Fear

Update time! And apologies for the double post...

Still haven't been able to locate the text bank, but using the Dissidia Modding Suite I *was* able to extract the .at3 files. So now I have all of the music, SE and voice files - oh wait, ALL of the sound in this game!

Still working on the text bank, and pulling as many graphics as I can... they appear to be in .gim and .bmp.ata format, and that's as much as I can get. Considering that the ATRAC format is another Sony favourite and the similarities in filetype name between .at3 and .ata, I wonder if it's a similar encoding; not that it's something I can do so far...
## Post #3
- Username: Ander0072
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 29, 2011 2:08 pm
- Post datetime: 2011-08-30T02:30:01+00:00
- Post Title: Corpse Party: Blood Covered Repeated Fear

I only know as much as you about this 
(there is also LZSS compression in it, but I think you already know that)

anyways, I hope you can at least extract the stuff 
(xseed might be bringing it to America so I don't know if you should start a full blown translation)

I don't know much about BMS, but seriously, if you can extract everything, if possible, tell me? xD

Anyways, thank you for being someone who loves this game enough to do all this. ^_^

also, I believe there are AROUND 30315 items. (make that, over 35000)

(also, all the at3 have the audio? so the .vag extension was  a mask so it was an at3 type encoding? Well, if you need a list of all files in the thing just ask)
## Post #4
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-11T11:07:15+00:00
- Post Title: Corpse Party: Blood Covered Repeated Fear

Don't know if this post still alive.... just want to know how you doin' on the translation?
I to also doing a translation right now on another game.
