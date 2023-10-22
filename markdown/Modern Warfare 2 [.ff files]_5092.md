## Post #1
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-09-26T18:38:48+00:00
- Post Title: Modern Warfare 2 [.ff files]

How can I compress/decompress the .ff files?
[http://www.gamevicio.com.br/i/traducao/ ... index.html](http://www.gamevicio.com.br/i/traducao/402-call-of-duty-modern-warfare-2-para-portugues-brasil/index.html)
There is a translate here.
## Post #2
- Username: tkGr33N
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Sep 26, 2010 3:43 am
- Post datetime: 2010-09-26T19:22:28+00:00
- Post Title: Modern Warfare 2 [.ff files]

> Reply from qabRieL
>
> How can I compress/decompress the .ff files?
http://www.gamevicio.com.br/i/traducao/ ... index.html
There is a translate here.

As far as now,
You can only export scripts, not models and textures. 
You CAN use 3DRipperDX to get your hands on models and textures (From my experience, models show up crunched up and need some editing, plus it exports the WHOLE view, so you might need to zoom in multiple times, and it will export the view AS IS meaning the angle you view it. E.G if you look at a model at 45 Degrees upward, it will appear rotated and deformed at that angle)

To export scripts: google ff Viewer, you will get loads of results regarding your topic.
Google 3DRipperDX To 'rip' the models
## Post #3
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-09-26T19:46:33+00:00
- Post Title: Modern Warfare 2 [.ff files]

Like you said, I tried .ff Viewer.
When I opened "cliffchanger.ff", maps/cliffchanger_anim.gsc, I found these text: (there is lot of them.)

```
    //You take the one on the left.     
    level.scr_sound[ "price" ][ "cliff_pri_youtakeleft" ]         = "cliff_pri_youtakeleft";
    //On three. One...two...three.    
    level.scr_sound[ "price" ][ "cliff_pri_onthree" ]         = "cliff_pri_onthree";
    
//SECOND ENCOUNTER    ---
    //Same plan.    
    level.scr_sound[ "price" ][ "cliff_pri_sameplan" ]         = "cliff_pri_sameplan";
```


Is that work?
## Post #4
- Username: tkGr33N
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Sep 26, 2010 3:43 am
- Post datetime: 2010-09-26T19:58:14+00:00
- Post Title: Modern Warfare 2 [.ff files]

> Reply from qabRieL
>
> Like you said, I tried .ff Viewer.
When I opened "cliffchanger.ff", maps/cliffchanger_anim.gsc, I found these text: (there is lot of them.)
Code: Select all//FIRST ENCOUNTER    ---
    //You take the one on the left.     
    level.scr_sound[ "price" ][ "cliff_pri_youtakeleft" ]         = "cliff_pri_youtakeleft";
    //On three. One...two...three.    
    level.scr_sound[ "price" ][ "cliff_pri_onthree" ]         = "cliff_pri_onthree";
    
//SECOND ENCOUNTER    ---
    //Same plan.    
    level.scr_sound[ "price" ][ "cliff_pri_sameplan" ]         = "cliff_pri_sameplan";

Is that work?

That text (GSC) are game command scripts. It basically tells the game what to do when something happens.
You can edit them, with caution. always keep a copy though.

Unless some people find a way to export other things from ff, thats all you get.

P.S I think Models and Textures are in the .iwd files. Look into that, i think iwd files are just zip files, try renaming them to zip and extract. see if it works. backup before doing so, though
