## Post #1
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-01-10T12:07:12+00:00
- Post Title: Disgaea Dat Files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-01-11T23:05:03+00:00
- Post Title: Disgaea Dat Files

anyone?
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2007-01-12T01:20:19+00:00
- Post Title: Disgaea Dat Files

Dude..
u gotta leave it longer then a day msot of the time.

il take a look at it and see waht i can get.
What do you want from it anyways?
Music, models, textures?
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-01-12T01:24:29+00:00
- Post Title: Disgaea Dat Files

i think that could be text and some textures...

sorry for the hurry
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2007-01-12T02:04:19+00:00
- Post Title: Disgaea Dat Files

> Reply from Vash
>
> i think that could be text and some textures...

sorry for the hurry

the start.dat contains RAW PCM audio(cant figure out hwo to play it now actually) and also contains textures the formats being TX2, cant remember what opens them yet, i know theyre in there jsut extracting them is takign em a while for some reason.

I dont know anything about the tx2 format lol.
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-01-12T02:18:32+00:00
- Post Title: Disgaea Dat Files

my objective, rellay, is not to view some textures or listen some music but to translate the game  do you think that in one of the archives there could be the text? (maybe in the talk.dat)
## Post #7
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2007-01-12T11:11:31+00:00
- Post Title: Disgaea Dat Files

> Reply from Vash
>
> my objective, rellay, is not to view some textures or listen some music but to translate the game  do you think that in one of the archives there could be the text? (maybe in the talk.dat)
oh u wanna TRANSALTE...
into what language and from what language?
I dont know much about translatign GAMES lol, movies and music yeah i know cos thats what i do but games are a new one on me really.
I wodner if anyone else here will try help out other then me.
Maybe we will get soem coherant results.

Also u shud state what you want to do with a game, as i spent 2 hours rummiging through them files u know, and it seems like i wasted my time.
## Post #8
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-01-12T12:02:04+00:00
- Post Title: Disgaea Dat Files

lol, i thought that you would have created the usually script for open the archive  and then i would have done it by myself.....anyway, if you really wanna help me, don't mind about this sucking game, but think about this [viewtopic.php?t=2275....trying](http://forum.xentax.com/viewtopic.php?t=2275....trying) to have the text of Disgaea was only for helping a friend of mine....  

thanks anyway
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-12T22:22:44+00:00
- Post Title: Disgaea Dat Files

I can write a Mexscript for MultiEx Commander for the .dat file.
## Post #10
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-01-12T22:26:40+00:00
- Post Title: Disgaea Dat Files

that's could be a great idea, many thanks....if you could even take a look at the other topic, I would be even more thankful
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-13T12:21:08+00:00
- Post Title: Disgaea Dat Files

```
Set OFF Long FNum ;
Set PO Long 0 ;
Set PS Long 0 ;
Math OFF *= 32 ;
Math OFF += 16 ;
Get D1 Long 0 ;
Get D2 Long 0 ;
Get D3 Long 0 ;
Set FO Long OFF ;
For T = 1 To FNum ;
SavePos FOO 0 ;
Get ENDOFFSET Long 0 ;
Set FileSize Long ENDOFFSET ;
Math FileSize -= PS ;
GetDString FileName 28 0 ;
Log FileName FO FileSize FOO 0 ;
Set PO Long FO ;
Set PS Long ENDOFFSET ;
Math FO += FileSize ;
Next T ;

```


Ok, this will open the start.dat. Just copy this into a text file and use that in the Run Mexscript on.. option.
## Post #12
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-01-13T12:23:17+00:00
- Post Title: Disgaea Dat Files

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-01-13T17:01:43+00:00
- Post Title: Disgaea Dat Files

Actually usually when it says "Talk" or "Speech" it is audio voices.
## Post #14
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-01-13T17:05:01+00:00
- Post Title: Disgaea Dat Files

i know but

1- the file is 540 kb
2- there is a SNDPAK.PAK that is 606 MB
