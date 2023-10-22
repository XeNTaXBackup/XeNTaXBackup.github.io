## Post #1
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-03-02T16:55:59+00:00
- Post Title: TIM2 - TGA

I know there's been a few topics on TIM2 but i'm trying to write an app for DMC3 that supports dumping the models in OBJ and in TGA and supports reinjecting (from there an ips patch will fix the loss of bones on the model (no vertices can be added or anything))

Here's what i've discovered on the TIM2 file type (any info would be much appreciated)



green background = Header
Red background = Alpha flag,  the 01 in the middle is either 01 for alpha or 00 for none
Pink background = All data added when alpha is flagged, when not flagged there's nothing there.
White background = unknown
blue background = stays the same on all tim 2 files (checked 4)
yellow background =  Size of file, read as x = 0080 y = 0080    (0080 = 128 - 16bit signed)

TGA is the format i'm trying to convert it to because none of the colour data is changed, only the header.
The bad part is that i don't know how to handle alpha data in a TGA as XNview deletes alphas from TIM2s.

Hmm i'm nearly there in understanding this , cept for this one thing.

the tga file seems to leave out a fair amount of data at the end, this may be optimizing the tga as it is a little ugly looking.  and the alpha data of the TIM2 is always at the very bottom, still don't know what flags the beginning of alpha.


EDIT:

probably should've added the files XD


 14_pl000.rar
TIM2 of dante and TGA output (101.75 KiB) Downloaded 124 times
## Post #2
- Username: PiotrekPL
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 01, 2008 9:23 pm
- Post datetime: 2008-04-21T20:04:26+00:00
- Post Title: TIM2 - TGA

Try program called Optipx iMage Studio. It can handle alpha channel and save it in to many different formats including the one You need - TGA. But make sure that file extension is not .tim2 when trying to open the file but .tm2 , hope this help.
## Post #3
- Username: PiotrekPL
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 01, 2008 9:23 pm
- Post datetime: 2008-04-22T12:53:43+00:00
- Post Title: TIM2 - TGA

Sorry program is called OPTPiX iMageStudio 3
## Post #4
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-04-23T19:06:38+00:00
- Post Title: TIM2 - TGA

kk, thanks man

I'll take a look at it.
Some guy's been talking to me about modding DMC3 so i'll probably look back into this.
## Post #5
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-04-26T22:18:43+00:00
- Post Title: TIM2 - TGA

Sorry for double posting
but where exactly can i get this?

Unless of course it's magical and you have to PM it to me ^_^.
## Post #6
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-04-27T22:59:52+00:00
- Post Title: TIM2 - TGA

Ahh nvm, got it
Finished TIM2 - TGA
but now i'm stuck on TGA - TIM2
Unless of course, i keep everything static

I'll upload the TIM2 - TGA in a bit (probs after school tomorrow(DEATH TO HIGHSCHOOL))

edit: 
Here's TIM2 to TGA

[FileFront](http://files.filefront.com/TIM2rar/;10093520;/fileinfo.html)

still some troubles with alpha
No TGA to TIM2, at least not yet.
source is packaged with (C)
pm if you want the Python source code 
(i originally did it in python and ported it to C for convenience)

PS:
Sorry about the triple post.
