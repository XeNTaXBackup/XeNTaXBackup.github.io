## Post #1
- Username: cascraft
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 22, 2016 7:33 am
- Post datetime: 2017-09-10T20:57:27+00:00
- Post Title: update python version 2to3

Hello friends,

does anyone how to update that python script(form [http://zenhax.com/viewtopic.php?t=1287](http://zenhax.com/viewtopic.php?t=1287)) to version 3.x ?




i was trying to update it but it gives me error:
## Post #2
- Username: philgrf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 07, 2017 1:11 am
- Post datetime: 2017-09-12T18:46:29+00:00
- Post Title: update python version 2to3

I understand that you try to convert the script "starter.py" from python 2 to python 3.

This script not a standalone. 

It imports the library "NewGameLib" with the first instruction of the script : import NewGameLib.
Some of the function used in "starter.py" are defined in "NewGameLib".

The script probably won't work outside of blender as it relies too on blender : import blender.
And it seems the NewGameLib itself relies too on blender.

I feel not only the python script need to be translated from python 2 to python 3 but also blender instruction need to be translated from blender 2.49 API to blender 2.7x API.

This website provides some insight about changes from blender API 2.49 to blender API 2.5x (there were later changes that one was the major change) :
[https://mogurijin.wordpress.com/2010/08 ... s-to-2-5x/](https://mogurijin.wordpress.com/2010/08/17/how-to-update-blender-2-49-bge-scripts-to-2-5x/)

I have had some success some years ago converting with this script :
[https://blenderartists.org/forum/showth ... -progress)](https://blenderartists.org/forum/showthread.php?229419-BGE-Python-2-4-to-2-5-converter-%28in-progress%29)
I was using blender 2.5x then.

Not used lately.
