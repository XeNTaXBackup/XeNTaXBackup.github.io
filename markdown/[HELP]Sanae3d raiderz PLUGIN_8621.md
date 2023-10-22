## Post #1
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-23T13:56:02+00:00
- Post Title: [HELP]Sanae3d raiderz PLUGIN

Hi users , i have got a sanae3d plugins for raiderZ but i don't know how i can use it with blender.
Can somebady shows me how can i use it please ? i have tryied to follow the tutorial on the tutorial 's area but it doesn't work. I hope that you will help me soon
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-23T14:13:28+00:00
- Post Title: [HELP]Sanae3d raiderz PLUGIN

If the tutorial doesn't work then I'm not sure what the issue is.
I don't use blender all that much (it is for blender 2.49 only) so if something goes wrong I don't know what the problem would be.

It is (supposed to be) a full blender plugin, not an import script. You need to copy the whole Sanae3D package into the blender plugin folder as I have mentioned in the readme.

Neither the Raiderz script nor the blender scripts are complete, so unless you are interested in adding on to the script it is useless.
## Post #3
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-23T14:47:34+00:00
- Post Title: [HELP]Sanae3d raiderz PLUGIN

> Reply from finale00
>
> If the tutorial doesn't work then I'm not sure what the issue is.
I don't use blender all that much (it is for blender 2.49 only) so if something goes wrong I don't know what the problem would be.

It is (supposed to be) a full blender plugin, not an import script. You need to copy the whole Sanae3D package into the blender plugin folder as I have mentioned in the readme.

Neither the Raiderz script nor the blender scripts are complete, so unless you are interested in adding on to the script it is useless.
 i use blender 2.49b and i have done everythink written in the readme , but when i , in blender , select sanae importer appears an error : python script error , check console <_>
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-23T15:12:31+00:00
- Post Title: [HELP]Sanae3d raiderz PLUGIN

What error does it say in console?

If you have questions about this tool just post in the tutorial thread.
## Post #5
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-23T15:27:33+00:00
- Post Title: [HELP]Sanae3d raiderz PLUGIN

> Reply from finale00
>
> What error does it say in console?
[http://i42.tinypic.com/hvv0x0.png](http://i42.tinypic.com/hvv0x0.png)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-23T18:01:25+00:00
- Post Title: [HELP]Sanae3d raiderz PLUGIN

hmm I probably should have taken out the test codes.
Didn't know cProfile isn't a standard module.

EDIT: hmm it looks like a lot of the modules don't come with blender or python 2.6.2
I might have to re-do the entire blender thing (which means I have to refresh my memory on how blender works)

I'll want to re-do the entire plugin system to not rely on external libraries if blender doesn't come with these things. Or just provide it I guess.
## Post #7
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-23T18:13:54+00:00
- Post Title: [HELP]Sanae3d raiderz PLUGIN

> Reply from finale00
>
> hmm I probably should have taken out the test codes.
Didn't know cProfile isn't a standard module.

EDIT: hmm it looks like a lot of the modules don't come with blender or python 2.6.2
I might have to re-do the entire blender thing (which means I have to refresh my memory on how blender works)

I'll want to re-do the entire plugin system to not rely on external libraries if blender doesn't come with these things. Or just provide it I guess.
i will wait for you ..... i don't know other ways to open .elu models <_>
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-23T19:23:41+00:00
- Post Title: [HELP]Sanae3d raiderz PLUGIN

Here is someone that looked into it and wrote his own viewer

[http://forum.ragezone.com/f697/model-formats-761223/](http://forum.ragezone.com/f697/model-formats-761223/)

I am not sure whether he went any further or not, or whether it works (I never tried it).

Since he released source people can use that for their own scripts.

I also cannot seem to bump the topic because I don't know how to log-in LOL
