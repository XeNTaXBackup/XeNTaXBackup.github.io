## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-03T11:42:12+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

Hi guys! Here's maxscript to import F.E.A.R [PC] 2005 character models with bones+weights (3ds max 2009-2012). Feel free to test it and send bug-reports here!


[FEAR_1.7z](https://xentaxbackup.github.io/file/10098_FEAR_1.7z)
## Post #2
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2015-12-03T21:05:13+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

Omg thanks so much! =)
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-04T21:14:12+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

No problem  Let's hope you and others will find script useful xD Game is pretty old
## Post #4
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-12-04T22:16:45+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

Have messed around a tiny bit with this script over the past two days, and it works great. Fantastic work, Zaramot.

Only issue I seem to be having is the bones. I recall you saying that they were a mess, so something like this should be expected?



Assuming this has to do with the weights, any way I can fix this?
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-05T10:56:26+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

Nooo, that shouldn't be expected. What model causing this (models)? Attach it here or in PM. Also, what 3ds max version you are using?
## Post #6
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-12-05T16:52:13+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

> Reply from zaramot
>
> Nooo, that shouldn't be expected. What model causing this (models)? Attach it here or in PM. Also, what 3ds max version you are using?

Every model gave me this issue in Max 2013, but I just tried it in Max 2010, and there's no problem at all.
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-05T17:58:44+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

Hmm, good too know it's working now! But I was sure script should work fine in 3ds 2013, I tested it in 2012... but not 2013. I should change compatibility in the first post then
## Post #8
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2015-12-06T10:47:11+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

Script works fine on almost all files i tested =) However there's this one which causes 3ds Max to not respond anymore. Is it one of the animation files or a model that doesn't work?
[file.zip](https://xentaxbackup.github.io/file/10109_file.zip)
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-06T16:49:14+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

Thanks for the bug report! Here's an update, if you will encounter another crash or error, please send me samples  

P.S. One section of data in this model differs from others, I'm curios if there will be other models with such differences, in order to parse this section correctly in need at least two models with similar ones (though, if this model is only one, that's okay lol   )
[FEAR_1_Fix.7z](https://xentaxbackup.github.io/file/10119_FEAR_1_Fix.7z)
## Post #10
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2015-12-06T17:08:51+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

Oh thanks that was quick 
I actually found another file which had the same error with the previous script version but that one loads fine with this update too ^_^
## Post #11
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-12-06T18:55:45+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

I think I've found an error when trying to load the weapons. Even with the new fix, Max still tells me "unable to convert: undefined to type: Integer."

Everything is working just fine though.

Here's some weapon samples if you'd like to take a look, Zaramot.

[http://www.mediafire.com/download/3rfmn ... amples.rar](http://www.mediafire.com/download/3rfmncvp5y59rfb/FEAR+Weapon+Samples.rar)
## Post #12
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2015-12-06T19:27:40+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

I actually found another one that doesn't load (causes the not responding error). Tested many other files but they all load fine except weapons as DXFan619 said =)
[player.7z](https://xentaxbackup.github.io/file/10121_player.7z)
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-25T15:47:29+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

Small update for weapons (some may crash, I've had only a few weapons to test) and for model which wasn't working (thanks Crofty  ) Sorry, took me so long because I was working on other games!


[FEAR_1.7z](https://xentaxbackup.github.io/file/10218_FEAR_1.7z)
## Post #14
- Username: y2keeth
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Sep 19, 2021 5:36 pm
- Post datetime: 2022-07-24T10:37:58+00:00
- Post Title: [PC] F.E.A.R (2005) import maxscript

is there a export script ?
also works in 2017
