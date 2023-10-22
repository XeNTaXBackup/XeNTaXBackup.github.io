## Post #1
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-08-07T17:13:16+00:00
- Post Title: [Mobile]KHUx Save Extractor

PS: YOU CAN MOD YOUR SAVE WITH THIS, BUT YOU NEED FURTHER MODIFICATION TO THE TOOLS.

Okay so I've created a SaveFile Extractor. You grab your "Cocos2dxPrefsFile.xml" from your device and place it with the tool, then you run it and the tool will convert the save into a decoded BGAD file. (There are other tools to extract each BGAD alone as well).

Note that you can't modify the save and repack it with this tool, as to what I've understood that it's against the rules of this site.

You will need khuxdecrypt. Link to the tool on my [GitHub Here.](https://github.com/thethiny/Modding-Database/tree/master/KHUx/SaveExtractor)
## Post #2
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-09T13:09:49+00:00
- Post Title: [Mobile]KHUx Save Extractor

This is probably unlikely but...is it possible to extract the assets of the game with this tool? If this is in fact capable of extracting the assets, is having a rooted device the only way to get the file "Cocos2dxPrefsFile.xml"?
## Post #3
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-09T13:17:39+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from Rhaes
>
> This is probably unlikely but...is it possible to extract the assets of the game with this tool? If so, is having a rooted device the only way to get the file "Cocos2dxPrefsFile.xml"?
Which asset exactly? This tool can extract your save, if you want to get the medals and the scripts of the game you need to get the M and R files and use KHUx decrypt.
## Post #4
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-09T13:36:18+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from thethiny
>
> Rhaes wrote:This is probably unlikely but...is it possible to extract the assets of the game with this tool? If so, is having a rooted device the only way to get the file "Cocos2dxPrefsFile.xml"?
Which asset exactly? This tool can extract your save, if you want to get the medals and the scripts of the game you need to get the M and R files and use KHUx decrypt.

Oh, sorry about that. I was in a hurry there.    I am interested in collecting all of the avatar parts, medal icons (the actual pictures), background images, keyblade images etc etc. Basically, stuff like this:



Is this at all possible?
## Post #5
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-09T14:14:07+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from Rhaes
>
> thethiny wrote:Rhaes wrote:This is probably unlikely but...is it possible to extract the assets of the game with this tool? If so, is having a rooted device the only way to get the file "Cocos2dxPrefsFile.xml"?
Which asset exactly? This tool can extract your save, if you want to get the medals and the scripts of the game you need to get the M and R files and use KHUx decrypt.

Oh, sorry about that. I was in a hurry there.    I am interested in collecting all of the avatar parts, medal icons (the actual pictures), background images, keyblade images etc etc. Basically, stuff like this:



Is this at all possible?

Yes, use KHUx decrypt on your misc.mp4 file (found in the games folder under files) and then use the tool in my github called PNG2BMP.
## Post #6
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-09T14:32:58+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from thethiny
>
> 
Yes, use KHUx decrypt on your misc.mp4 file (found in the games folder under files) and then use the tool in my github called PNG2BMP.

Thanks! I found the file exactly where you said it would be. 

May I ask how to use the KHUx Decrypt on the misc.mp4 file though? I thought perhaps having it in the directory with the .exe might have done it (sorta like PS2 patching), but the command prompt only appears for a second before closing without any results.
## Post #7
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-09T15:10:22+00:00
- Post Title: [Mobile]KHUx Save Extractor

You open a CMD on that place and use this syntax
KHUxdecrypt File Output
## Post #8
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-09T16:48:28+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from thethiny
>
> You open a CMD on that place and use this syntax
KHUxdecrypt File Output

It was just like using the terminal in Linux, which is to say easy. It all worked out! I've got my files (just gotta sort through 'em now), so thank you so much! I would have had to manually edit out screenshots if not for this extractor!
## Post #9
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-09T16:56:00+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from Rhaes
>
> thethiny wrote:You open a CMD on that place and use this syntax
KHUxdecrypt File Output

It was just like using the terminal in Linux, which is to say easy. It all worked out! I've got my files (just gotta sort through 'em now), so thank you so much! I would have had to manually edit out screenshots if not for this extractor!
MP4 files are a BGAD structure, they contain all the files. PNG files can be BGAD listings of their MP4 counterparts or a BMP  image. 
I'm unsure what the gif contains but the M folder contains the scripts.
## Post #10
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-10T14:39:18+00:00
- Post Title: [Mobile]KHUx Save Extractor

Hmm. How would one going about trying to open the .gif file? I'd be interested in learning what methods might work or set me towards the right path.

Oh, and I finished sorting through the massive dump of images, but a good chunk of them seem to be corrupted or too big (it reports). Could this be due to the specific file I used?
## Post #11
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-10T15:05:27+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from Rhaes
>
> Hmm. How would one going about trying to open the .gif file? I'd be interested in learning what methods might work or set me towards the right path.

Oh, and I finished sorting through the massive dump of images, but a good chunk of them seem to be corrupted or too big (it reports). Could this be due to the specific file I used?
I never encountered too big files. Some images aren't corrupted, they're simply 4 bit PNGs, my tool handles only 0x20 Bits. You can open hex and in the first few bytes replace 2p with 04. But they're mostly useless files. 
Open the gif the same way you open the misc.
## Post #12
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-10T15:56:27+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from thethiny
>
> Rhaes wrote:Hmm. How would one going about trying to open the .gif file? I'd be interested in learning what methods might work or set me towards the right path.

Oh, and I finished sorting through the massive dump of images, but a good chunk of them seem to be corrupted or too big (it reports). Could this be due to the specific file I used?
I never encountered too big files. Some images aren't corrupted, they're simply 4 bit PNGs, my tool handles only 0x20 Bits. You can open hex and in the first few bytes replace 2p with 04. But they're mostly useless files. 
Open the gif the same way you open the misc.

What if there is no 2p (though I am seeing 42 4D in them all via HxD)? I guess if they are useless I don't need to access them.   

Ah! I ran it and they seem to be scripts or something too. The jpgs seem to be useless for me, as well. Well, my interest was met regardless! Thanks for answering my questions and helping me out. I appreciate it.
## Post #13
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-10T15:58:45+00:00
- Post Title: [Mobile]KHUx Save Extractor

20** note 2P, autocorrect. 

Anyways I'm glad to help ^_^ you can always ask me!
## Post #14
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-10T17:38:17+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from thethiny
>
> 20** note 2P, autocorrect. 

Anyways I'm glad to help ^_^ you can always ask me!

Oh! I hate autocorrect sometimes. 

I'll try it again tonight. When I make the corrections to the file though, what is next? I extract them after the changes with khuxdecrypt, right?
## Post #15
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-10T17:49:01+00:00
- Post Title: [Mobile]KHUx Save Extractor

> Reply from Rhaes
>
> thethiny wrote:20** note 2P, autocorrect. 

Anyways I'm glad to help ^_^ you can always ask me!

Oh! I hate autocorrect sometimes. 

I'll try it again tonight. When I make the corrections to the file though, what is next? I extract them after the changes with khuxdecrypt, right?

What do you mean by corrections?
## Post #16
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-10T20:13:40+00:00
- Post Title: Re: [Mobile]KHUx Save Extractor

> Reply from thethiny
>
> Rhaes wrote:thethiny wrote:20** note 2P, autocorrect. 

Anyways I'm glad to help ^_^ you can always ask me!

Oh! I hate autocorrect sometimes. 

I'll try it again tonight. When I make the corrections to the file though, what is next? I extract them after the changes with khuxdecrypt, right?

What do you mean by corrections?

Oh, I meant the whole "replacing 20**" thing.
## Post #17
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-10T20:16:43+00:00
- Post Title: Re: [Mobile]KHUx Save Extractor

> Reply from Rhaes
>
> thethiny wrote: 
What do you mean by corrections?

Oh, I meant the whole "replacing 20**" thing.
Windows will be able to display the images.
## Post #18
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-11T11:31:55+00:00
- Post Title: Re: [Mobile]KHUx Save Extractor

> Reply from thethiny
>
> Rhaes wrote:thethiny wrote: 
What do you mean by corrections?

Oh, I meant the whole "replacing 20**" thing. 
Windows will be able to display the images.

It might be because I'm new tot his kind of thing, but to be able to open an image, change a few numbers and then be able to open it after is just incredibly weird and cool. I'm gonna have to try it tonight, as I accidentally deleted my decrypted data trying to organize things.   

Ah, before I get off for the night, I do have one more question and it doesn't exactly relate to your tools/location of files, but the .bmp files themselves after conversation with the tool. Do you have a suggestion for a program to mass convert the bmps to pngs (there is about 1000 files)? The bmps don't seem to want to open correctly for me in GIMP (no longer transparent and tiny + pixelized look) and ImageBatch refuses the files altogether.
## Post #19
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-11T11:37:03+00:00
- Post Title: Re: [Mobile]KHUx Save Extractor

Well, I personally use an Action script for photoshop. It is indeed not transparent but there's an alpha channel. I tried studying the PNG files but unfortunately they are completely different.

An alpha channel is a channel where Black means Hidden, White means visible, and the variations of grayscale indicate transparency.
## Post #20
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-11T13:01:46+00:00
- Post Title: Re: [Mobile]KHUx Save Extractor

> Reply from thethiny
>
> Well, I personally use an Action script for photoshop. It is indeed not transparent but there's an alpha channel. I tried studying the PNG files but unfortunately they are completely different.

An alpha channel is a channel where Black means Hidden, White means visible, and the variations of grayscale indicate transparency.

That info was incredibly useful, thank you! By googling some of that (alpha channels), it led me to a program called "Advanced Batch Image Converter" (via a Ubuntu ask thread) that did the trick (except a very small few it couldn't convert) perfectly! It is strange that Paint.net can open the images as they should be, but not GIMP. Silly, even.
## Post #21
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-11T14:13:53+00:00
- Post Title: Re: [Mobile]KHUx Save Extractor

They can open them, but because I wanted the tool to be very fast I removed part of the header. You can fix it easily by fixing the header. Go to Wikipedia, it's windows BMP  header.

Edit: open it in windows ms paint and save it again and it will fix the header.
