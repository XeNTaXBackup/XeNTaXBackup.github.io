## Post #1
- Username: ThunderFlame
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 09, 2018 4:02 am
- Post datetime: 2018-01-12T18:57:17+00:00
- Post Title: Converting tfd files from Star Conflict.

I can't get to wrap my head around how to convert or even open the tfd files, I know that they are supposed to be the headerless bodies, but how do I open them along with the headers? I tried Texture Finder and no matter the combinations I couldn't get anything legible enough, maybe some of the more experienced folks can help me out of this predicament.
Here is an example folder, it might not be much, I managed to decompile every model folder so we have a wide variety to try from:
[cabin.rar](https://xentaxbackup.github.io/file/13785_cabin.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-12T22:29:40+00:00
- Post Title: Converting tfd files from Star Conflict.

your sample looks similar to Crossout tfh/tfd but there may be slight difference. 
the sample was too tiny (60x36 dxt5) to be certain my analysis is close to correct, 
need more samples to examine and expand support.
## Post #3
- Username: ThunderFlame
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 09, 2018 4:02 am
- Post datetime: 2018-01-13T08:44:32+00:00
- Post Title: Converting tfd files from Star Conflict.

Ask and you shall receive.
[big_pgun.rar](https://xentaxbackup.github.io/file/13788_big_pgun.rar)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-15T06:33:13+00:00
- Post Title: Converting tfd files from Star Conflict.

okay try this Noesis python script  


 tex_StarConflict_tfh_tfd.zip
(767 Bytes) Downloaded 76 times


supports dxt1 and dxt5
the script will open all your samples but i still don't know how accurate it is
because your samples never exceeded 64x64 and i just can't tell if they are correct.
## Post #5
- Username: ThunderFlame
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 09, 2018 4:02 am
- Post datetime: 2018-01-16T14:10:47+00:00
- Post Title: Converting tfd files from Star Conflict.

It seems to be able to open tfh files for the most part, but not tfds.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-16T23:47:12+00:00
- Post Title: Converting tfd files from Star Conflict.

then it works as designed, this format works in tfh/tfd pairs or header/data pairs  
you aren't supposed to open the tfd files, the script will do that automatically.
## Post #7
- Username: ThunderFlame
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 09, 2018 4:02 am
- Post datetime: 2018-01-18T15:58:55+00:00
- Post Title: Converting tfd files from Star Conflict.

Nice, now to find a way to convert the meshes to obj, and wrap the textures around them, any good tips?
## Post #8
- Username: kodi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 13, 2018 6:17 am
- Post datetime: 2018-02-12T23:19:47+00:00
- Post Title: Converting tfd files from Star Conflict.

It is very similar to Crossout and plugin from [viewtopic.php?p=134377#p134377](http://forum.xentax.com/viewtopic.php?p=134377#p134377) seems to somewhat work.
It can open the Mesh files in Noesis. I had some success with it, however it looks like it's a little different approach to the one in Crossout and each ship is made from multiple objects attached to a skeleton. And unfortunately it doesn't work with all models from SC. 
If you are just after meshes 3D Object converter can open most of them (but not object trees), but tbh I would love the Noesis solution working 



If more samples are needed, just let me know - I can upload the whole unpacked game somewhere.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-12T23:38:50+00:00
- Post Title: Converting tfd files from Star Conflict.

> Reply from kodi
>
> It is very similar to Crossout ..
If more samples are needed, just let me know - I can upload the whole unpacked game somewhere.
never count on a script for one game to work for another.   
i have made a texture script for this game in this thread already, but the previous samples i looked at were tiny, 
so a better group of larger samples would be better so i can confirm the file structure and extend functionality,
i don't need the whole game for that though.
## Post #10
- Username: kodi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 13, 2018 6:17 am
- Post datetime: 2018-02-13T00:26:55+00:00
- Post Title: Converting tfd files from Star Conflict.

I have to thank you for your willingness to help  
More samples [here](https://drive.google.com/open?id=1_46j0ycE6osk0xxaGLjs9Rr0gzoEo1Dv) and [here](https://drive.google.com/open?id=1pX1Gmha1bo0vgl5F5OPP6o6CDNlot3NE).
please let me know if you need anything else
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-17T08:16:39+00:00
- Post Title: Converting tfd files from Star Conflict.

> Reply from kodi
>
> More samples here and here.

this second version of the Noesis python "Star Conflict" tfh/tfd script will open your texture samples  


 tex_StarConflict_tfh_tfd_v2.zip
(805 Bytes) Downloaded 85 times


supports dxt1, dxt3, dxt5 main mip only
maybe later i will combine the 2 script versions so only one is needed, 
but the other is a mess and i don't want to bother with it right now.   
this script will conflict with other tfh/tfd scripts in your python folder,
so you will have to move them out temporarily while you use this one,
there was no way to give it a proper type check.
## Post #12
- Username: kodi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 13, 2018 6:17 am
- Post datetime: 2018-02-22T11:38:10+00:00
- Post Title: Converting tfd files from Star Conflict.

Hey it works for most of them, awesome!
Any chance for model reader? The one from crossout works only on some of them unfortunately :/
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-22T14:44:25+00:00
- Post Title: Converting tfd files from Star Conflict.

it works for all the samples you provided, except for the one without a tfd file. 
there is 2 scripts in this thread, if one script doesn't work with a texture try the other one.   
if you have seen more textures of large size not working please upload them so i can improve script.
Crossout is a different game with similarities, never count on a script for different games to work on another.  
i have not looked at the model files for this game yet, maybe later i will.
## Post #14
- Username: kodi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 13, 2018 6:17 am
- Post datetime: 2018-03-05T01:15:41+00:00
- Post Title: Converting tfd files from Star Conflict.

Please, please do
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-07T04:54:53+00:00
- Post Title: Converting tfd files from Star Conflict.

okay here is Noesis python script to open your mdl-msh000 through mdl-msh009 samples  
*script updated March 11, 2018*


 fmt_StarConflict_mdl-msh000.zip
(917 Bytes) Downloaded 66 times


this script will conflict with the Crossout script so you have to move that one out of python folder when using this one.
## Post #16
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2018-03-10T12:33:04+00:00
- Post Title: Re: Converting tfd files from Star Conflict.

> Reply from AceWell
>
> okay here is Noesis python script to open your mdl-msh000 samples
Thank you 

Some models doesn't work or has bugs, uploaded samples [here](http://www.mediafire.com/file/c87a7pmyt3oqqgy/StarConflict_sample_ships.zip).
bigship - causes error at loading.
race_1\h - have bad and missing polygons.
specialships\ship_ufo - normals looks weird (it's supported?).
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-11T05:28:58+00:00
- Post Title: Re: Converting tfd files from Star Conflict.

i updated the model script to open that big ship and the other LOD/parts files  
it can also now open *.mdl-msh000 through *.mdl-msh009

the script doesn't read normals, if they are there they are stored in only 4 bytes
and i've never had success with this. i usually only focus on the meat and potatoes
but if you can tell me how to construct the normals i will try to add it to the script.
## Post #18
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2018-03-11T08:15:54+00:00
- Post Title: Re: Converting tfd files from Star Conflict.

> Reply from AceWell
>
> but if you can tell me how to construct the normals i will try to add it to the script.
Maybe one of [these methods](https://aras-p.info/texts/CompactNormalStorage.html)?
## Post #19
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-07-08T21:32:57+00:00
- Post Title: Re: Converting tfd files from Star Conflict.

Hey, guys!
Can someone extract this cool ship Ze'Ta for me? I need print it 



MwavVuajXas.jpg (137.69 KiB) Viewed 60 times
