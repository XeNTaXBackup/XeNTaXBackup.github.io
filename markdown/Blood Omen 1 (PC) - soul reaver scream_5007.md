## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-09-11T17:02:50+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

I have a problem: I can't find a certain sound (namely, the scream of the soul reaver weapon when swung).
I tried using this
[viewtopic.php?f=17&t=3652&hilit=blood+omen](http://forum.xentax.com/viewtopic.php?f=17&t=3652&hilit=blood+omen)
but if gives me "state error" when converting 3 files. can someone post the sound effect here? or tell me how to fix the SOX problem?
thank you
## Post #2
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-16T18:42:37+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

the dumper gets it, BUT it does not sound right. think you can have a look at it?
## Post #3
- Username: dla
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 24, 2010 11:56 am
- Post datetime: 2010-10-24T04:08:55+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

I think it's item number 2340(pill_2340) not counting empty files in PILL.BIG. 
I haven't played the game for a long time so i could be incorrect.
It is a WAV file so you can play it directly.
## Post #4
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-24T07:42:39+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

I checked it but, again, it does NOT sound right... like slower than it should be!
## Post #5
- Username: dla
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 24, 2010 11:56 am
- Post datetime: 2010-10-24T18:15:45+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

if you change sample rate to 16000
with
play -r 16k pill_2340.wav
or
sox -r 16000 pill_2340.wav test.wav

it should be fine?
## Post #6
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-24T18:28:01+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

I tried that, but it still is not like in-game. It's me seeing phantoms or I'm doing something wrong?
and thanks for the help
## Post #7
- Username: dla
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 24, 2010 11:56 am
- Post datetime: 2010-10-26T04:20:49+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

What does it sound like?
## Post #8
- Username: dla
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 24, 2010 11:56 am
- Post datetime: 2010-10-26T05:18:28+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

Just to make sure we have the same file.

item number 2340(including empty files whithin PILL.BIG)
file size for 'item number 2340' = 48884 bytes
MD5 for 'item number 2340' = 420ecbee48681cf5bdc7c2dfce372a40
## Post #9
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-26T07:29:32+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

I lost all the files, could someone repost the latest "blood pill" utility release?
## Post #10
- Username: dla
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 24, 2010 11:56 am
- Post datetime: 2010-10-27T02:06:34+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

[http://darkmaster.quakedev.com/files/bo/bpill_0.8c.zip](http://darkmaster.quakedev.com/files/bo/bpill_0.8c.zip)
## Post #11
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-27T08:26:29+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

It does not extract them all. it shows this:

> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\bigfile.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\bigfile.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\bloodpill.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\bloodpill.dsp
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\bloodpill.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\bloodpill.vcproj
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\BO1.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\cmdlib.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\cmdlib.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\jamfile.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\mem.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\mem.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\rawfile.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\rawfile.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\soxsupp.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\soxsupp.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\sprfile.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\sprfile.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\timfile.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\timfile.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\vagfile.c
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bloodpillsource\vagfile.h
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bo_filetypes.txt
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bpill.exe
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bpill.txt
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in bpill_ru.txt
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in cyggomp-1.dll
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in cygwin1.dll
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in klist.txt
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in samples\extract_file.bat
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in samples\samples.txt
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in samples\samples_ru.txt
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in samples\unpack_oggsounds.bat
>
> !   C:\Users\Domenico\Downloads\bpill_0.8c.zip: Unknown method in sox.exe
## Post #12
- Username: dla
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 24, 2010 11:56 am
- Post datetime: 2010-10-27T23:41:54+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

I had trouble with this one too, i don't remember which program i used to extract it.
But if you only want the sound files.

This should work

[http://darkmaster.quakedev.com/files/bo/bpill_0.8b.zip](http://darkmaster.quakedev.com/files/bo/bpill_0.8b.zip)
## Post #13
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-28T12:17:32+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

I open the exe file and it says "error, bad commandline". any idea why?
## Post #14
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-11-07T08:57:52+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

no one has encountered that error before?
## Post #15
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-02-27T11:13:45+00:00
- Post Title: Blood Omen 1 (PC) - soul reaver scream

is there an updated version of Blood Pill?
