## Post #1
- Username: queoLita
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2009 8:42 am
- Post datetime: 2009-08-03T20:13:05+00:00
- Post Title: SmackDown5 replacing models

Hello.
I've recently became able to replace models inside SmackDown 5 HCTP game with models from SmackDown 4 SYM.
With GameShark codes from Code-X it is possible to adjust the model's height, the character's attributes, name and etc. to fit the model modifications.

The problem is though that the TXC files from SYM do not appear compatible with HCTP. I read on this forum that the TXC files are TIM2 of sorts. I assume that the exact compression of the SYM TXCs is a little different from that of HCTP.
This is what you get (the models do not have all of their textures applied on them).
NOTE: Only Jeff Hardy's model is the fully polygonal one. Due to space and size issues I had to use the lower polygonal models from SYM for Molly, Billy and Ivory (there's little difference really). The VS screen displays how the model appears during cut scenes and entrances. In ring the textures are a little bit more readable.
NOTE 2: Not all textures are applied to the imported models because until I can make them readable it doesn't seem to matter.
Molly Holly

Billy Gunn

Jeff Hardy

Ivory


The TXC files in SYM and HCTP have repeating sizes (exact byte count) all throughout the texture folders- 65 kb, 33 kb, 17 kb, 9.06 kb and similar. I suppose they're all the same size like 128x128, 64x64 and etc.
I hope anyone here might be able to help me with those files. I can send a copy of a couple of TXC samples from SYM and HCTP of same size to compare.
Note: Replacing headers (first 64 bytes) inside the TXCs (RTX8?) of files of the same size doesn't seem to work. The files do not have footers (end headers?) the way I read it.
Note 2: I'm using PS2 emulator to play the game and therefore it's not a real PS2 quality (I'm talking about the original superstars). I wouldn't want to burn a new DVD every time I change something.
## Post #2
- Username: queoLita
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2009 8:42 am
- Post datetime: 2009-08-06T22:27:01+00:00
- Post Title: SmackDown5 replacing models

Small Update
OK. So I decided to add all of the textures on all superstars. There was small improvement and some parts became invisible (like when it's rendered in cutscene mode, which I take as a good sign). Mostly their hair, eyes, teeth and may be a thing or two would be rendered under cutscene/entrance mode. In ring, they still look unreadable, only with some improvements such as hair is visible (for some only) and colorless alpha textures can be recognized. Ivory became completely invisible, but her hair which is the only thing rendered is as it should be (cutscene and in-ring modes yield the same results).

Raven had pretty decent results as most of his lower body is visible, and of course hair and etc.
I was able to dig up Stacy's recycled attire (in SD5 she has her SD4's blue skirt attire, I guess they decided never to have it available though) and compared textures. Size wise they're the same, but their coding does not match; nor does their header.
Obviously the format is ... upgraded? TIM1 to TIM2? Is it possible that they used TIM1 textures for SD3 & 4? Is anyone willing to try and open some textures at least? I tired everything to get them to work as TIM2s, but no joy.
## Post #3
- Username: queoLita
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2009 8:42 am
- Post datetime: 2009-08-21T18:04:52+00:00
- Post Title: SmackDown5 replacing models

Big Updade
I managed to get the textures open.They are all indeed TIM2s; need a custom header. The format is the same for both SD4 and SD5. They're 8bit TIM2s using 16 bytes alignment and 32 bit CLUT (Colour Look Up Table) CSM1.
Even so I haven't gotten them to work correctly in-game. The format is the same, but they aren't being opened correctly.
Here are some faces from SmackDown 5- Batista, Ric Flair, Stacy Keibler and Victoria.

These are some faces from SmackDown 4- Jeff Hardy, Bradshaw, Billy Gunn and Molly Holly.

I think the key is in the header.

The RTX38 thing is to be ignored.
The next number ('24') defines the size of the image (this would vary depending on the size of the image). Follow two empty values ('00 00').
Follows what I believe is the key to the whole ordeal (highlighted part). This is different for every texture. I think it's related to the loading ... erhm ... order/ID? I don't know yet, but it seems as if it is somehow related to the loading of the texture, because some textures end up being loaded correctly in cutscene mode and aren't in in-ring game. To me it seems like a loading issue. I could as well be wrong.
The rest (until the end of the 64 byte header) remains constant throughout all textures.
Any suggestions anyone?
EDIT: I forgot to mention. I replaced Stacy's SD5 model with her SD4 model (blue skirt) that was left in SD5, but not used (Has anyone stumbled upon it anywhere in-game actually?). The model worked perfectly. Loaded correctly and everything, which is no step forward as it's just another model form SD5 replacing a model from SD5. Once again, this model was converted by the makers. I guess they just never got to actually use it.
I also did an experiment where I replaced an SD5 texture with an SD4 texture. The results were the same as before. Cutscene mode yielded invisible texture. In-game it was unreadable/messy.
This is what makes me believe that the highlighted part contains an ID/loading information of sorts.
EDIT2: Modding the highlighted part does little to nearly no good. Still unreadable. I still think that that is where something needs to be corrected, but not sure.
## Post #4
- Username: queoLita
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2009 8:42 am
- Post datetime: 2009-08-21T23:09:36+00:00
- Post Title: SmackDown5 replacing models

Some progress
Well, I decided to re-index the textures for some reason and that yielded some results. I re-indexed Billy Gunn's SD4 textures. That seemed to have made his textures readable in cutscene mode (there was the loss of the Alpha though). In-game he's still unreadable, only slightly better unreadable (heh!).

The problem is that SmackDown 4's indexing of textures is incompatible with SmackDown 5. Since they're both the same TIM2 formats, a loss of indexing and re-indexing to the images is needed in order to get rid of SD4's "thinking". I think it's SD4's alpha that seems incompatible, otherwise there isn't any real difference, I think. Probably correcting just the alpha without the re-indexing could work too. Anyway, the only way of making them readable was to get rid of the alpha actually.
The previously highlighted part of the textures' hex is still the original one (SD4) by the way. It worked without changing that, yet tweaking it seemed to make the textures equally readable in both cutscene and in-game mode.
Any suggestions? Does anyone know of a quick good way to change alpha to all indexed colours in a file?
EDIT: As previously thought SD4's alpha is the reason textures appeared as invisible whenever read before. The default value in the SmackDown 4 CLUTs for a visible color is Alpha= 0 (ergo- no invisible stuff). But in SmackDown 5 the default value for completely visible color is Alpha= 128 (as standard). WEIRD THING: the other textures that were visible before (usually hair) actually utilize Alpha= 0 as invisible which is why they were displaying before. The only thing that is needed really is to discard the Alpha information from the invisible textures in order to get them looking back to normal in SmackDown 5.
In cutscene mode the models now appear perfectly- textured and everything. In-ring = unreadable. Ivory though, who previously always rendered invisible (as in cutscene mode) is rendered nearly perfect. Still think the highlighted part needs to be tweaked some.
EDIT 2: In cutscene mode the textures are read just fine. If a model is loaded in player slots 3, 4, 5 or 6 they would be read fine. In winning mode though they'd be read bad again. With slots 1 and 2 it's the oppposite (unreadable in match, normal in cutscene). Definately a loading issue. Posting pictures of the models as read in cutscene mode.
Billy Gunn (Attire1 and 2), Billy Kidman, Hardcore Holly, Molly Holly (Attire 1 and 2), Raven, Maven (I've missed one elbow pad during conversion), Ivory. Below Bradshaw, Farooq, Jeff Hardy (Attire 1 and 2).
## Post #5
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2009-08-24T17:48:59+00:00
- Post Title: SmackDown5 replacing models

> Reply from queoLita
>
> Some progress
Well, I decided to re-index the textures for some reason and that yielded some results. I re-indexed Billy Gunn's SD4 textures. That seemed to have made his textures readable in cutscene mode (there was the loss of the Alpha though). In-game he's still unreadable, only slightly better unreadable (heh!).

The problem is that SmackDown 4's indexing of textures is incompatible with SmackDown 5. Since they're both the same TIM2 formats, a loss of indexing and re-indexing to the images is needed in order to get rid of SD4's "thinking". I think it's SD4's alpha that seems incompatible, otherwise there isn't any real difference, I think. Probably correcting just the alpha without the re-indexing could work too. Anyway, the only way of making them readable was to get rid of the alpha actually.
The previously highlighted part of the textures' hex is still the original one (SD4) by the way. It worked without changing that, yet tweaking it seemed to make the textures equally readable in both cutscene and in-game mode.
Any suggestions? Does anyone know of a quick good way to change alpha to all indexed colours in a file?
EDIT: As previously thought SD4's alpha is the reason textures appeared as invisible whenever read before. The default value in the SmackDown 4 CLUTs for a visible color is Alpha= 0 (ergo- no invisible stuff). But in SmackDown 5 the default value for completely visible color is Alpha= 128 (as standard). WEIRD THING: the other textures that were visible before (usually hair) actually utilize Alpha= 0 as invisible which is why they were displaying before. The only thing that is needed really is to discard the Alpha information from the invisible textures in order to get them looking back to normal in SmackDown 5.
In cutscene mode the models now appear perfectly- textured and everything. In-ring = unreadable. Ivory though, who previously always rendered invisible (as in cutscene mode) is rendered nearly perfect. Still think the highlighted part needs to be tweaked some.
EDIT 2: In cutscene mode the textures are read just fine. If a model is loaded in player slots 3, 4, 5 or 6 they would be read fine. In winning mode though they'd be read bad again. With slots 1 and 2 it's the oppposite (unreadable in match, normal in cutscene). Definately a loading issue. Posting pictures of the models as read in cutscene mode.
Billy Gunn (Attire1 and 2), Billy Kidman, Hardcore Holly, Molly Holly (Attire 1 and 2), Raven, Maven (I've missed one elbow pad during conversion), Ivory. Below Bradshaw, Farooq, Jeff Hardy (Attire 1 and 2).
Can you post the custom Header?
## Post #6
- Username: queoLita
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2009 8:42 am
- Post datetime: 2009-08-28T17:44:11+00:00
- Post Title: SmackDown5 replacing models

> Reply from QISE
>
> Can you post the custom Header?
OK, I'm assuming that you want the header to open the textures as TIM2s.
Prerequisite knowledge:
Hex editing, CLUT images
SmackDown 4&5's images have a custom header which tells the game what kind of image it is. Most importantly there is a number which tells the game the image's dimensions (256x256, 256x128, 256x64, 128x128 and etc). I am attaching TIM2 files of each separate image size that I've come up against while working with those games.
[http://www.freewebs.com/queo_lita/SD6/TIM2samples.rar](http://www.freewebs.com/queo_lita/SD6/TIM2samples.rar)
Each of those has its own 64 byte TIM2 header. What you need to do is copy the first 64 bytes and replace them in the SmackDown TXC image file. To know which one is right just look at the size: 256x256 is 64.0 kB and 17.0 kB is usually 128x128. WARNING: This is not always true. 256x64 and 128x128 are of the same size. 128x128 is more often used though. You will know which one is right after you've opened the image though.
I hope this would be of help for people out there. Have fun and toodles!
## Post #7
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2009-08-28T18:53:49+00:00
- Post Title: SmackDown5 replacing models

> Reply from queoLita
>
> QISE wrote:Can you post the custom Header?
OK, I'm assuming that you want the header to open the textures as TIM2s.
Prerequisite knowledge:
Hex editing, CLUT images
SmackDown 4&5's images have a custom header which tells the game what kind of image it is. Most importantly there is a number which tells the game the image's dimensions (256x256, 256x128, 256x64, 128x128 and etc). I am attaching TIM2 files of each separate image size that I've come up against while working with those games.
http://www.freewebs.com/queo_lita/SD6/TIM2samples.rar
Each of those has its own 64 byte TIM2 header. What you need to do is copy the first 64 bytes and replace them in the SmackDown TXC image file. To know which one is right just look at the size: 256x256 is 64.0 kB and 17.0 kB is usually 128x128. WARNING: This is not always true. 256x64 and 128x128 are of the same size. 128x128 is more often used though. You will know which one is right after you've opened the image though.
I hope this would be of help for people out there. Have fun and toodles!

Hmm something not right i change RTX38 To TIM2 whats wrong?  

Did i do it right?
## Post #8
- Username: queoLita
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2009 8:42 am
- Post datetime: 2009-08-28T22:27:54+00:00
- Post Title: SmackDown5 replacing models

> Reply from QISE
>
> 
Hmm something not right i change RTX38 To TIM2 whats wrong? 
Did i do it right?

Nope.
You have to copy the whole first 64 bytes of the provided TIM2s header (depending on the size of the TXC file you're working with). TIM2 would actually replace only the RTX3 part of the TXC file's header, which doesn't even matter cause all of the first 64 bytes of the TXC file should be replaced.
Example. Let's say you want to open a TXC texture (let's call it image.txc) that is 64.0 kB. Now the only 64.0 kB is the 256x256 texture.
Step 1: Go to the folder where you have the TIM2 files I provided. Open 256x256.tm2 (size 64.0 kB) with a hex editor. Copy the first 64 bytes of that file with the hex editor.
Step 2: Open image.txc with a hex editor. Select the first byte, then paste on it, overwriting the previous data. (This is likely to be different for different hex editors. You may need to first delete the 64 bytes of data in texture.txc and then paste/insert at the beggining).
Step 3: Save the changes made to image.txc and rename it to image.tm2. Open with appropriate software.
Did that help?
Note: To turn it back into a SmackDown readable TXC you'll need to give it its original TXC header back, therefore you'd need another (untouched) copy of the same image.
## Post #9
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2009-09-11T18:24:02+00:00
- Post Title: SmackDown5 replacing models

Hi any update on how your doing with this?
## Post #10
- Username: Teeceezy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 17, 2009 1:28 am
- Post datetime: 2009-09-21T07:40:48+00:00
- Post Title: SmackDown5 replacing models

queoLita... if i converted the indexed smackdown 4 image to direct color, then re-indexed it and created an alpha based on this re-indexed image would that work?

EDIT: I think I've made a discovery.   The alpha for images in SD4 is adapted to each image, while all the alpha's I've opened from HCTP are just a single color.



The four textures on the left are the Rock's face and skin from Shut Your Mouth, while the four on the right are Rock and Austin's faces from Here Comes The Pain. The top row is the images themselves and the bottom row is the alpha's of each image.

So maybe if we give the SD4 textures alphas like those from SD5 and then re-index the image palette, the textures will be completely readable in the game. Which would be
## Post #11
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2009-09-21T22:35:34+00:00
- Post Title: SmackDown5 replacing models

> Reply from Teeceezy
>
> queoLita... if i converted the indexed smackdown 4 image to direct color, then re-indexed it and created an alpha based on this re-indexed image would that work?

EDIT: I think I've made a discovery.   The alpha for images in SD4 is adapted to each image, while all the alpha's I've opened from HCTP are just a single color.



The four textures on the left are the Rock's face and skin from Shut Your Mouth, while the four on the right are Rock and Austin's faces from Here Comes The Pain. The top row is the images themselves and the bottom row is the alpha's of each image.

So maybe if we give the SD4 textures alphas like those from SD5 and then re-index the image palette, the textures will be completely readable in the game. Which would be
That a real good start but how do repack the pac.files?
## Post #12
- Username: Teeceezy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 17, 2009 1:28 am
- Post datetime: 2009-09-22T11:11:52+00:00
- Post Title: SmackDown5 replacing models

> That a real good start but how do repack the pac.files?

I'd love to know but I'm afraid that queoLita seems to be the only person to ever do it for HCTP. I have no idea.
## Post #13
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2009-09-22T20:18:12+00:00
- Post Title: SmackDown5 replacing models

> Reply from Teeceezy
>
> That a real good start but how do repack the pac.files?

I'd love to know but I'm afraid that queoLita seems to be the only person to ever do it for HCTP. I have no idea.
Damn.
## Post #14
- Username: queoLita
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2009 8:42 am
- Post datetime: 2009-09-25T19:23:01+00:00
- Post Title: SmackDown5 replacing models

Excellent work Teeceezy - discarding Alpha is how I did it before. It will get the textures properly displayed, but their IDs need to be changed as well, because it will cause wrong graphics throughout the game (mainly with blood, arena elements and such). Player slots 1 and 2 would be displayed unreadable. It's a bit of work.
I've dropped my work on that so I'll just tell you how to replace things. As I am short on time I'll tell it my way and if it's hard to understand I hope someone would take the time to put it in simple words.
What I've noticed about the CH#.PAC files is that they contain smaller PAC files. But because the big PAC file can only map certain sizes the original small PAC files are patted with zeroes in the end. CH#.PAC only tells the system this is where a PAC file begins and ends. The smaller PAC file then says - this is how far away from me a certain thing is.
Following this logic - if you take a full SD4 small PAC file of size equivalent or smaller (smaller would need more zeroes in the end in order to match size) than a SD5 small PAC file and swap them inside SD5 CH#.PAC it'll work. So this hierarchy can easily be manipulated to your advantage. And the good thing about SD4 is that it contains two types of each model for each wrestler in its PACs. One regular around 500 kB and one smaller (less polygonal) around 420 kB. This way you can replace any models from SD4 in to SD5 whatsoever because if you need it smaller, you already have it.
Same thing for textures - once you've discarded the Alpha, give it its original 64 byte header and save it. Go inside the PAC of the wrestler you took it from and replace the thing.
I hope this made sense. The tools you would need are:
A good HEX editor - one that can copy and paste blocks. And search for exact data match.
Apache - if you have an ISO version of your game you can replace the newly created CH#.PAC with the old one.
Suggestion: Once you've located an SD4 superstar's small PAC. Copy it from start to finish (they begin with PAC then some data and there should be a YOBJ and more data. You start copying from "PAC" included all the way until you meet another "PAC" - you stop before "P") and save it as a separate file. From then on you can cut, edit and re-insert textures and once its done, patty it with zeroes to match a small PAC of an SD5 superstar. Save it (do that frequently frequently). Go to the begining of the smaller PAC inside the SD5 CH#.PAC and overwrite the data with that of your work.
I hope this made any sense.
BTW the file - Moves.PAC contains the names of the moves. If you open it with HEX editor and modify the window so you can see each move name begin on a separate line (because there is a limit on how long a move can be called) and edit the text, you can change the name of the move in game. I think the damage can be modified too because I did it once, but I wouldn't recommend it because it is both untested and I think it would dis-balance the game. I reversed that damage change BTW so I never did test it in game.
Anyway. I was surprised to see this thread as still active. I hope I was of some help.
Good modding out there, happy days and PLEASE stay environmentally safe.
## Post #15
- Username: Teeceezy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 17, 2009 1:28 am
- Post datetime: 2009-09-25T20:24:47+00:00
- Post Title: SmackDown5 replacing models

Awesome stuff. Your work is greatly appreciated. Just to clarify, I reinsert the edited files with a hex editor right?
## Post #16
- Username: queoLita
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2009 8:42 am
- Post datetime: 2009-09-26T18:44:47+00:00
- Post Title: Re: SmackDown5 replacing models

Yes, because what you're doing is you're taking data and replacing it.
I recommend that you extract a CH#.PAC with the PACeXtractor and once you've located something, open it with hex, copy a bunch of lines, look for them in the original CH#.PAC, then copy the PAC block and save this thing as a separate file. This way you would have the smaller PACs, which are otherwise unattainable, in a separate small file which you can more easily edit and have more than one copy of.
I used the FRhead hex editor, because it is free and has so many helpful features which make the load of work you might need to do so much lighter.
God luck.
