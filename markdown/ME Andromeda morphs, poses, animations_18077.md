## Post #1
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-05-08T20:45:51+00:00
- Post Title: ME Andromeda morphs, poses, animations

Hello!
I'm trying to figure out the poses and morphs from ME Andromeda.
Used frosty, I extracted several models like fbx and bin.
The format is quite clear - I wrote two simple scripts for parsing StaticPoses and Blueprints. 
It seems StaticPoses use Quaternions Rotations, BLUEPRINTS - matrix3 transforms.
Now we need to apply these transformations to the models.
Here with this problem - I did not work with skeletons and skin and now I act at random.
Can anybody help?
In the application archive with source files and scripts.

[https://www.dropbox.com/s/igfvfwwtb8nu4 ... ce.7z?dl=0](https://www.dropbox.com/s/igfvfwwtb8nu4wz/tur_source.7z?dl=0)
## Post #2
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-05-09T04:38:11+00:00
- Post Title: ME Andromeda morphs, poses, animations

Some progress with morph (blueprint files)

[](http://vfl.ru/fotos/18d7e8b421669915.html)

[](http://vfl.ru/fotos/5fef526e21669957.html)
## Post #3
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2018-05-11T13:05:54+00:00
- Post Title: ME Andromeda morphs, poses, animations

At last someone look me Andromeda morphs. I can't wait as soon as it can be used:) 

What about Dragon Age inquisition? I think  Andromeda morph and DAI morph are the same.
## Post #4
- Username: padme4000
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 27, 2014 1:46 am
- Post datetime: 2018-05-13T08:59:17+00:00
- Post Title: ME Andromeda morphs, poses, animations

Oh wow this is brilliant. I have been waiting for someone to make progress on the morphs in Andromeda. I can't help with coding but once you have the morph applied to a model you should be able to transfer that data to a skin/skeleton model using the morpher modifier in 3DS Max. Since technically they both should still have the same vertex etc

[https://youtu.be/HuLsQNjo8Qo](https://youtu.be/HuLsQNjo8Qo) at 4:20 i show how to use the morpher modifier in max. I hope this helps somewhat.
## Post #5
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-05-13T18:45:24+00:00
- Post Title: ME Andromeda morphs, poses, animations

The problem is that I do not understand why some bones are not in their positions.
Look at the tongue.
Most likely there are some transformations of the positions regarding the parents/childrens.
## Post #6
- Username: padme4000
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 27, 2014 1:46 am
- Post datetime: 2018-05-14T12:05:42+00:00
- Post Title: ME Andromeda morphs, poses, animations

Having looked at the messed up versions with skeletons and played around with the bones I definitely think you are right. I have no idea why Bioware did that with the Dynamic Morphs but it may be due to something with how they animated the models? All I know is that the Dynamic Morph moves bones from the base model to make it look like how it looks like in game. 

So the base models look like the left side in your image and then the dynamic morph moves bones in order to get it to look like what we see in game. Again no idea why they do that.

I haven't managed to test your script yet as I haven't been able to go on the pc but I will see if I can test it later and tell you anything I find out.

Update: Can I ask which version of 3ds max the script is for? As it didn't work on 2015 + 2018 for me. Unless I did something wrong.
## Post #7
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-05-16T04:25:06+00:00
- Post Title: ME Andromeda morphs, poses, animations

The script is very raw.
To make it work, you need to import fbx from the archive and manually register the file paths, the number of bones and the offset of the data fields from the beginning of the file.
## Post #8
- Username: Horsey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 17, 2018 8:29 am
- Post datetime: 2018-05-17T00:35:19+00:00
- Post Title: ME Andromeda morphs, poses, animations

Looks really promising.  Thanks and good luck!
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-23T16:49:34+00:00
- Post Title: ME Andromeda morphs, poses, animations

Will be posted there in my facefixing thread
[viewtopic.php?p=146911#p146911](http://forum.xentax.com/viewtopic.php?p=146911#p146911)

[https://youtu.be/CmhcSO-eXHw](https://youtu.be/CmhcSO-eXHw)
