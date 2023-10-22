## Post #1
- Username: feber12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2015 6:23 am
- Post datetime: 2016-02-07T14:24:35+00:00
- Post Title: help with this command

Hi, I wanted to know what the problem with this script , apparently does conflict , if I can say that I can change in command line

```
animate on
(
	noda = getnodebyname"em003_bone_243"
	noda = getnodebyname"em003_bone_179"
	at time 0
	(
	noda += [-0.304131,-0.095595,-0.081600]
	)
	noda = getnodebyname"em003_bone_179"
	at time 0
	(
		noda.scale = [1.000000,1.000000,1.000000]
	)
	noda = getnodebyname"em003_bone_62"
	at time 0
	(
		noda.rotation.x_rotation = 22.043932; noda.rotation.y_rotation = -8.398624; noda.rotation.z_rotation = 8.102036;
	)
	at time 1
	(
		noda.rotation.x_rotation = 22.011135; noda.rotation.y_rotation = -7.976318; noda.rotation.z_rotation = 8.308508;
	)
	at time 2
	(
		noda.rotation.x_rotation = 21.947784; noda.rotation.y_rotation = -7.330198; noda.rotation.z_rotation = 8.527365;
	)
	at time 3
	(
		noda.rotation.x_rotation = 21.858635; noda.rotation.y_rotation = -6.483333; noda.rotation.z_rotation = 8.757195;
	)
	at time 4
	(
		noda.rotation.x_rotation = 21.748981; noda.rotation.y_rotation = -5.459695; noda.rotation.z_rotation = 8.997394;
	)
	at time 5
```


```
>> MAXScript FileIn Exception: -- Unknown property: "pos" in undefined <<
```
[/color]

use 3d studio max 11
[https://mega.nz/#!I5pHgLDS!KKOYu3eJhfof ... tdjz-PP9uU](https://mega.nz/#!I5pHgLDS!KKOYu3eJhfofthMHqqfjj9rRq6Qx_BqPVtdjz-PP9uU)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-07T18:25:32+00:00
- Post Title: help with this command

> Reply from feber12
>
> Hi, I wanted to know what the problem with this script , apparently does conflict ,em003_0.ms, here is the problem:
noda = getnodebyname"em003_bone_62"

There's no such bone created in em003.mod.ms but
em003_bone_0 up to em003_bone_43

Seems most of the bone numbers in the first script don't match.
There's even em003_bone_254.

You could try to rename them but there's only 34 (so the anim will be f..ed up if you name 'em from em003_bone_0 to ..._33).

btw: who is the author of these scripts?

The code you posted and the script you uploaded are different. (If you've cut the missing 10 bones then that was a bad idea...  )

```
animate on
(
	noda = getnodebyname"em003_bone_62"
	at time 0
	([...]
```
## Post #3
- Username: feber12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2015 6:23 am
- Post datetime: 2016-02-08T11:17:01+00:00
- Post Title: help with this command

If I had realized , of that mistake in the bones, but do not try to change
and I tried it to rename the bones gives inseperado result , would have to find which are the bones indicated or names of the bones. 

The author is the user Surveyor


is a program that I think, if you had raised the problem apparently did not respond . I'm sorry for my English
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-08T11:27:11+00:00
- Post Title: help with this command

> Reply from feber12
>
> If I had realized , of that mistake in the bones, but do not try to change
and I tried it to rename the bones gives inseperado result , would have to find which are the bones indicated or names of the bones. 

The author is the user SurveyorThx, but Surveyor's last post is from 4 years ago.

Is the code you posted public, in any forum? If so, could you give a link, please?
(Might be helpful to have the original em003_0.ms.)

> is a program that I think, if you had raised the problem apparently did not respond . I'm sorry for my English(Talking about an exe file built by Surveyor?) yeah, your last sentence is a little bit hard to understand.  
Could you rephrase that, please (say it in other words), 'cause I'm not a native speaker, too.

btw: which game is the model from?
This? [viewtopic.php?f=10&t=3057&p=41809#p41809](http://forum.xentax.com/viewtopic.php?f=10&t=3057&p=41809#p41809)
## Post #5
- Username: feber12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2015 6:23 am
- Post datetime: 2016-02-08T12:50:41+00:00
- Post Title: help with this command

if , it is the author of the program used 

Well, there you leave the entire original file and programs used . game is devil may cry 4
[https://mega.nz/#!FsRHkboA!iDygk2kjCak7 ... 8pZ9gTtdwE](https://mega.nz/#!FsRHkboA!iDygk2kjCak7vZyAYdB7b8t6Og4SALf7e8pZ9gTtdwE)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-08T13:10:25+00:00
- Post Title: help with this command

Thank you!  
I'll see what I can do. But don't expect it too soon.

btw: it could be helpful if you provided one model (.lmt and .mod) where the generated .ms files create a working animation in 3dsmax.
## Post #7
- Username: feber12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2015 6:23 am
- Post datetime: 2016-02-08T13:15:15+00:00
- Post Title: help with this command

thanks!  


yes eh provided , LMT and mod files , I am a noob at this  , but try to learn .
## Post #8
- Username: feber12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2015 6:23 am
- Post datetime: 2016-02-08T14:30:07+00:00
- Post Title: help with this command

I climbed back here are mod. and LMT   
[https://mega.nz/#!F5RwBLDR!3qmXT8EtAXfA ... oB3q6vRhT4](https://mega.nz/#!F5RwBLDR!3qmXT8EtAXfA-aMw2ZZMeWLyF-wolmYHDoB3q6vRhT4)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-08T14:55:32+00:00
- Post Title: help with this command

But that's the ones which were already included in the Model and Animation folder of your previous upload, aren't they?

What I meant was a model (.lmt, .mod) which you could successfully create a working animation from using Surveyor's tools. Or don't you have such?
## Post #10
- Username: feber12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2015 6:23 am
- Post datetime: 2016-02-08T15:38:33+00:00
- Post Title: help with this command

ah already understood , but the model is the em003.mod.ms maxscript when you run the model is imported, and the animation is em003_0.ms also runs when the animation is connected to the model, but there is conflict I ​​meant. Also I leave the model in .max version 11 3d studio max , but I leave you maxscript is for all versions , I think.
[https://mega.nz/#!dphwHbCJ!bMDnseLUQzTM ... RB0Q5k5D04](https://mega.nz/#!dphwHbCJ!bMDnseLUQzTMw4yRUnmIn44dvt3FrsBr8RB0Q5k5D04)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-08T19:02:41+00:00
- Post Title: help with this command

ok, that didn't help, to be honest (there's nothing new compared to what you provided so far.  )

Anyway, I got one animation working, not perfectly but in a decent way (more or less).

Here's a short guidance but I can't guarantee that it will work for 3dsmax versions other than the one I use (2013, Student version):
 drag em003.mod (340602 bytes) onto Noesisv4176 (should work with elder version of Noesis, too. Didn't check it, though.)
export to fbx (File/export, main output type: .fbx)
import .fbx into 3dsmax
load and execute the maxscript from this post
run the animation

That broaster doesn't fly, though. It's just twisting. Maybe due to the fact that there's 10 bones missing in the script
as explained in a previous post.

(Use the appended script as instructed - it won't work with the 8.4 MB em003.mod.ms.
You have been warned.  )


 em003_0-ok.zip
(75.65 KiB) Downloaded 17 times



btw: reading here: [viewtopic.php?f=10&t=3057&p=66213&hilit ... ion#p66213](http://forum.xentax.com/viewtopic.php?f=10&t=3057&p=66213&hilit=dmc4motion#p66213)
I've come to the assumption that animations never worked properly using Dmc4Motion, did they?
## Post #12
- Username: feber12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2015 6:23 am
- Post datetime: 2016-02-09T22:29:50+00:00
- Post Title: help with this command

good thanks, I tested this pretty decent but lack the animation as I mentioned it.  

maybe , I'm using a version of devil may cry 4 special edition might work with devil may cry 4 ? surely now I 'm downloading to prove it.  

if something haci said in his post , but did not follow your project or program update.
