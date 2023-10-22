## Post #1
- Username: SPRlover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 12, 2016 1:51 pm
- Post datetime: 2016-03-12T08:13:57+00:00
- Post Title: Help with .SPR files.

Hello everyone! 
I'm in the need of some help here.
I need to know how to open these .SPR files, since I'm trying to make my very own private server for this already dead/closed online game and I want to translate every bit of it.

I really don't like to beg, but I've been searching through the whole internet and I really didn't found any answer.  :'(
If someone knows how to open this certain kind of files, please let me know.
[event1.rar](https://xentaxbackup.github.io/file/10579_event1.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-12T09:10:41+00:00
- Post Title: Help with .SPR files.

> Reply from SPRlover
>
> [...]but I've been searching through the whole internet and I really didn't found any answer.  :'(You didn't find any answer?
I can't believe this - it's totally simple using Gimp (or IrfanView):



event1-spr.jpg (141.94 KiB) Viewed 119 times



btw: didn't check for palette data so the ingame colors might be different
## Post #3
- Username: SPRlover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 12, 2016 1:51 pm
- Post datetime: 2016-03-12T21:29:42+00:00
- Post Title: Help with .SPR files.

> Reply from shakotay2
>
> SPRlover wrote:[...]but I've been searching through the whole internet and I really didn't found any answer.  :'(You didn't find any answer?
I can't believe this - it's totally simple using Gimp (or IrfanView):
The attachment event1-spr.jpg is no longer available

btw: didn't check for palette data so the ingame colors might be different

Oh!!! thanks for your reply.    
Well... opening @ RAW image would function, yes, it also shows the pallete and stuff, BUT.... how do I edit these files?

Let's suppose I want to edit it, translate it, etc.. then... how do I pack it as the same .SPR format again?.
That's the big deal. 

Also, not all the .SPR files from this game are the same size, I tried to open this one:
[http://www.mediafire.com/download/93371 ... _Awake.spr](http://www.mediafire.com/download/93371cyy4j9zbgi/Chunho_Awake.spr)

What can I do?   I seriously need help opening these files.  
[chunho1.jpg](https://xentaxbackup.github.io/file/10583_chunho1.jpg)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-12T22:27:58+00:00
- Post Title: Help with .SPR files.

> Reply from SPRlover
>
> Let's suppose I want to edit it, translate it, etc.. then... how do I pack it as the same .SPR format again?.
That's the big deal.yep, it is.
You'll need to understand the 80 bytes header (I've marked the size in the pic, 800x600).



spr-x_y_size.jpg (68.87 KiB) Viewed 107 times


(36 bytes from 0x20 to 0x43 are identical for your two samples.)
DWORD at 0x44: picture count

For the big spr you posted you can split it up into 369(?) smaller pieces, I guess, like this:

first pic at 0x50

0x50 + 0x5820= 0x5870   (0x5820= 0x5E*0x78*2)
0x5870 60 000000 79 000000
2nd pic: 0x5878

0x5870+5AC0= B330   (5AC0= 0x60*0x79*2)

B338: 61 000000 79 000000

3rd pic: B340

and  so on.

Don't have the time to investigate in editing/repacking, sry.
## Post #5
- Username: SPRlover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 12, 2016 1:51 pm
- Post datetime: 2016-03-12T23:07:12+00:00
- Post Title: Help with .SPR files.

> Reply from shakotay2
>
> SPRlover wrote:Let's suppose I want to edit it, translate it, etc.. then... how do I pack it as the same .SPR format again?.
That's the big deal. yep, it is.
You'll need to understand the 80 bytes header (I've marked the size in the pic, 800x600).
spr-x_y_size.jpg
(36 bytes from 0x20 to 0x43 are identical for your two samples.)
DWORD at 0x44: picture count

For the big spr you posted you can split it up into 369(?) smaller pieces, I guess, like this:

first pic at 0x50

0x50 + 0x5820= 0x5870   (0x5820= 0x5E*0x78*2)
0x5870 60 000000 79 000000
2nd pic: 0x5878

0x5870+5AC0= B330   (5AC0= 0x60*0x79*2)

B338: 61 000000 79 000000

3rd pic: B340

and  so on.

Don't have the time to investigate in editing/repacking, sry.

OMG you are a MASTER! But... this is just plain TOO COMPLICATED for me. Hahahahaha. I think I'm damned, I will never get to edit the sprites
