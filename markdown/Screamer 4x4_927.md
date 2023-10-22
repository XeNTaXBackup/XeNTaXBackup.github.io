## Post #1
- Username: kjelle69b
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-26T11:29:35+00:00
- Post Title: Screamer 4x4

I have tried to get extractor for screamer 4x4 Â´s game.cod file.

Is there support anywhere for .cod archives?
I have found a loader to change textures, and that works, but no cod extractor.
## Post #2
- Username: kjelle69b
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-26T11:37:43+00:00
- Post Title: Screamer 4x4

[http://formula1.jatekok.hu/screamerutil_eng.shtml](http://formula1.jatekok.hu/screamerutil_eng.shtml)
## Post #3
- Username: Phil
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-08T15:20:01+00:00
- Post Title: Screamer 4x4

> http://formula1.jatekok.hu/screamerutil_eng.shtml
Sorry Kjelle, but on this website you only find the extractor for textures, and that's all   

Anyone can help for  the Screamer 4x4 .cod archives?
Thanks
Phil
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-09T10:48:49+00:00
- Post Title: Screamer 4x4

Hey,

If anyone is able to post a small *.cod archive, then we will be able to take a look at it. Alternatively, if the file is too big to be posted here, you can email it to us. My address is [watto@watto.org](mailto:watto@watto.org) , and Mr Mouse's email is in his profile, or on the main Xentax webpages.)

Thanks.


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-09T18:02:31+00:00
- Post Title: Screamer 4x4

Many thanks for your reply, Watto (Oh, Watto is my favorite character in the Star Wars prequels, among a lot of very bad things - I'm definitively an Original trilogy fan    

I have a little .cod, it's a patch you can open with notepad. But the others are at least 37 Mb (language.cod) or 416 Mb (game.cod)
There is also a 105 Mb one (bigtextures.cod), this is the one we can extract with deCODer.exe to modify the textures. But this decoder extracts only the bigtextures.cod...

I will send you the patch12.cod (14 kb) and deCoder.exe (48 kb), but the others are too big. Could I publish the 37 Mb one on my website, so you can access it?

Thanks in advance
Phil
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T02:31:46+00:00
- Post Title: Screamer 4x4

Hey,

Yeah Watto is a pretty cool character  - he has a great voice and everything!

As for the *.cod files, you can send the small patch file to us, preferably by attaching it to the forums here so we can all download it and look at it. The bigger files - if you put one of them on a webserver then we will download it and have a look at it too, but make sure you zip it up as small as you can.

Thanks mate, I hope we can help

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: Phil
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 10, 2005 3:24 pm
- Post datetime: 2005-02-10T07:34:44+00:00
- Post Title: Screamer 4x4

Hello Watto

So here it is, the little patch12.cod and the utility deCODer.exe to extract the
bigtextures.cod, hoping it will help...

Thanks
Phil
[scr4x4files.zip](https://xentaxbackup.github.io/file/117_scr4x4files.zip)
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T11:02:02+00:00
- Post Title: Screamer 4x4

Piece of cake. Mr Mouse, here is the structure for you so you can knock up a MexCom script - shouldn't take long to do.

```
| Screamer 4x4 *.cod |
+--------------------+

21 - Header (->Unique Pc HUNGARY<-)
3 - null
4 - Directory Length

// for each file
  128 - Filename (null terminated, then filled with "." for the remaining bytes)
  4 - Offset
  4 - Length
```


I have also attached a Game Extractor plugin to open the archives - you can download Game Extractor from [http://www.watto.org/extract](http://www.watto.org/extract) and unzip the plugin into the plugins/ directory.

Have fun.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_COD_UNIQUE.zip](https://xentaxbackup.github.io/file/121_Plugin_COD_UNIQUE.zip)
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T11:28:44+00:00
- Post Title: Screamer 4x4

I also just wrote up this script for MultiEx Commander to open the archives - so give it a go and see if it works. Take note though, this is my first script I've ever done for MultiEx Commander so it may be buggy.

```
Get FNum Long 0 ;
Math FNum /= 136 ;
For n = 1 to FNum ;
Get FN String 0 ;
Set Off Long 136 ;
Math Off *= n ;
Math Off -= 8 ;
Math Off += 28 ;
GoTo Off 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FO FS FOO FSO ;
Next n ;

```


Or just use the attached BMS script. Here is how to use the BMS Script in MultiEx Commander...
1. Unzip the BMS script file, then load up the MexBinder program.
2. Click the "Open MRF" button and choose the file called mc.mrf
3. Click the "Add Single Format" button and choose the file you unzipped
4. Type the game name
5. Click the "Create MRF" button and choose the mc.mrf file 

Good Luck!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[cod.zip](https://xentaxbackup.github.io/file/122_cod.zip)
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-10T12:41:12+00:00
- Post Title: Screamer 4x4

W00t ! Nice job!   

[EDIT]
Just get the MC.MRF file below and replace the original in your data/config directory of MultiEx Commander.   See below for the post with the file!!
## Post #11
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T12:55:28+00:00
- Post Title: Screamer 4x4

Excellent - glad it worked. It isn't really that hard to write a script, just needed a bit of mathematical thinking to get around the fixed-length strings.  . If I crack open a format, I will try to write the Mex Scripts for them from now on - after all it is your board 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-10T13:15:33+00:00
- Post Title: Screamer 4x4

Nice ! Okay, so but MultiEx Commander can even handle importation for cod, as you saved the positions of the offset and size variables. 

I have rewritten it slightly :

```
GoTo 24 0 ;
Get FNum Long 0 ;
Math FNum /= 136 ;
For n = 1 To FNum ;
SavePos JP 0 ;
Get FN String 0 ;
Math JP += 128 ;
GoTo JP 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FO FS FOO FSO ;
Next n ;

```


Thus, not only can you extract, but also replace the files with MultiEx Commander. 

Here's the final MC.MRF with this script:
[mc.mrf](https://xentaxbackup.github.io/file/124_mc.mrf)
## Post #13
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T13:22:45+00:00
- Post Title: Screamer 4x4

Yes, I thought the offsets were saved to allow importing, so I thought I should stick them in the script. I didn't know about the ImpType command though - thats pretty important to have in there. Also, thanks for fixing up the maths stuff - your way is much better so I will remember that structure for next time.

Thanks mate, I hope the next version of MexCom is coming along smoothly.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #14
- Username: Phil
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 10, 2005 3:24 pm
- Post datetime: 2005-02-10T15:07:12+00:00
- Post Title: Screamer 4x4

WHOW guys! Faster than the Millenium Falcon jumping in lightspeed   

Now I will try to find a way to modify the files in the .cod, so I can create or modify cars and characters and landscapes.

Thanks again, you are definitively the bests   
Phil
## Post #15
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T21:40:18+00:00
- Post Title: Screamer 4x4

Thanks mate, glad we could help.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #16
- Username: jpbiaggi
- Rank: Banned
- Number of posts: 2
- Joined date: Fri Aug 11, 2006 1:32 pm
- Post datetime: 2006-08-11T05:33:57+00:00
- Post Title: I need this game

please...i want this game....
where i can download this game?!?!?!
thanks
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-11T06:34:25+00:00
- Post Title: I need this game

> Reply from jpbiaggi
>
> please...i want this game....
where i can download this game?!?!?!
thanks
Banned


Read our policy. Now warez, no illegal conduct.
## Post #18
- Username: TimB
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 22, 2014 8:42 pm
- Post datetime: 2014-07-23T13:00:42+00:00
- Post Title: I need this game

> Reply from kjelle69b
>
> http://formula1.jatekok.hu/screamerutil_eng.shtml

Is there a new link for this???
## Post #19
- Username: cxt
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 20, 2014 10:20 pm
- Post datetime: 2014-08-21T08:02:30+00:00
- Post Title: I need this game

> Reply from TimB
>
> Is there a new link for this???
[Archived page copy](https://web.archive.org/web/20050830094119/http://formula1.jatekok.hu/screamerutil_eng.shtml) (files not available) and [files from that page](http://www.mmnt.net/db/0/0/www.hsw.hu/hsw/screamer/) (in the "util" folder).
