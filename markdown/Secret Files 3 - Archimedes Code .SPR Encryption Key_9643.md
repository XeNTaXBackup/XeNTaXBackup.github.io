## Post #1
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-09-17T06:18:09+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

Greetings. The third installment of Secret Files series also uses the SPR archive format. Now these tools over here:
[http://oezmen.eu/gameresources/files/tunguska.zip](http://oezmen.eu/gameresources/files/tunguska.zip)
support the SPR format but they don't have the key embedded. They only have the keys for SF1 demo, SF1 retail and SF2 retail... and Lost Horizon. Can anyone please check for the encryption key?

Sample archive available in PM on request.
## Post #2
- Username: hqqttjiang
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 19, 2012 10:27 am
- Post datetime: 2012-09-17T09:42:27+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

I  have the same problem，these unpack tools works fine，but repacking SPR files can not be accept by the game Secret Files 3
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-17T15:35:02+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

I unpacked them successfully using unpakke: [viewtopic.php?f=33&t=6168](http://forum.xentax.com/viewtopic.php?f=33&t=6168)
## Post #4
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-09-17T16:23:57+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

And what about packing the files back?
## Post #5
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-09-19T01:52:41+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

> Reply from Vash
>
> I unpacked them successfully using unpakke: viewtopic.php?f=33&t=6168

Hi , I want to know when you unpacked them using unpakke
But which *.dll is used??
## Post #6
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-09-19T04:49:44+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

The game uses the key value of the Lost Horizon in the .spr files.
## Post #7
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-09-19T07:09:08+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

Bacter -- THANK YOU! That's PRECISELY what I needed to know!
## Post #8
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-09-19T10:06:46+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

Thanks Bacter
key=0x08A0DC??
[viewtopic.php?f=10&t=4911&p=42449&hilit ... zon#p42449](http://forum.xentax.com/viewtopic.php?f=10&t=4911&p=42449&hilit=Lost+Horizon#p42449)
but I sprext loca.spr wit this key, it don't work.
and makspr with this key , game don't work.
Why?
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2012-10-07T10:16:14+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

> Reply from warwar
>
> but I sprext loca.spr wit this key, it don't work.
and makspr with this key , game don't work.
Could you describe your problem a bit more in detail? Do the tools generate any error messages?

SPRExt should work with Secret Files 3 data files out of the box (though it will tell you that it has detected Lost Horizon data files, but that doesn't matter). Conversely, when using MakSPR, just specify the Lost Horizon key ("/key:lh").

If unpacking fails due to an unknown key, please issue the following command and come back to us with the results:

```
sprext my_problematic_file.spr /force /keyonly
```
## Post #10
- Username: sidclaynt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 20, 2017 1:48 am
- Post datetime: 2017-06-19T17:51:05+00:00
- Post Title: Secret Files 3 - Archimedes Code *.SPR Encryption Key

> Reply from warwar
>
> Thanks Bacter
key=0x08A0DC??
viewtopic.php?f=10&t=4911&p=42449&hilit ... zon#p42449
but I sprext loca.spr wit this key, it don't work.
and makspr with this key , game don't work.
Why?

Worked for me perfectly...
