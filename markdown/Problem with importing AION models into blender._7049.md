## Post #1
- Username: marsata
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 23, 2011 8:16 pm
- Post datetime: 2011-07-24T04:45:01+00:00
- Post Title: Problem with importing AION models into blender.

So I use:
Blender 2.49b
Pyton 2.6.5
PyFFI 2.1.4
ColladaCFG 0.3.9

First,I tried to import a model of a bow and it worked.

Screen:
[](http://imageshack.us/photo/my-images/823/bowdk.jpg/)

Then,I tried to load the other weapons of that set and I get an error on all of them:

Screen:
[](http://imageshack.us/photo/my-images/808/failnt.jpg/)

I'll be really grateful if someone helps me
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-24T19:34:45+00:00
- Post Title: Problem with importing AION models into blender.

why use blender when can import into 3D Studio Max? anyway I see you got error in line 489, try search this line what information have there.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-24T19:42:12+00:00
- Post Title: Problem with importing AION models into blender.

Cause 3D max is expensive and blender is free.
## Post #4
- Username: marsata
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 23, 2011 8:16 pm
- Post datetime: 2011-07-24T20:02:56+00:00
- Post Title: Problem with importing AION models into blender.

> Reply from finale00
>
> Cause 3D max is expensive and blender is free.

I have 3D Max 7 and 2011 so the money aren't the problem here 

~Regarding the previous post.
Would you tell me what plugin do I need for 3ds max to import .cfg files?
And regarding the "489 line"- the .cfg file has only 388 lines O.O (Opened with notepad ++)
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-24T20:05:12+00:00
- Post Title: Problem with importing AION models into blender.

> Reply from marsata
>
> finale00 wrote:Cause 3D max is expensive and blender is free.

I have 3D Max 7 and 2011 so the money aren't the problem here 

~Regarding the previous post.
Would you tell me what plugin do I need for 3ds max to import .cfg files?
And regarding the "489 line"- the .cfg file has only 388 lines O.O (Opened with notepad ++)you can use batch convertor of 3D Object Converter to OBJ.
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-24T20:07:03+00:00
- Post Title: Problem with importing AION models into blender.

If you are a student or faculty member of a university (I am the latter), 3D Studio Max 2012 and Maya 2012 are both free. Sign up on autodesk's student web site . I was about to fork over $300 to JourneyEd before I found out there was a free way to get it .
## Post #7
- Username: marsata
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 23, 2011 8:16 pm
- Post datetime: 2011-07-24T20:08:25+00:00
- Post Title: Problem with importing AION models into blender.

> Reply from CriticalError
>
> marsata wrote:finale00 wrote:Cause 3D max is expensive and blender is free.

I have 3D Max 7 and 2011 so the money aren't the problem here 

~Regarding the previous post.
Would you tell me what plugin do I need for 3ds max to import .cfg files?
And regarding the "489 line"- the .cfg file has only 388 lines O.O (Opened with notepad ++)you can use batch convertor of 3D Object Converter to OBJ.

Yup,that worked.I'm so distracted these days ;x Anyway really thanks for the great help :3
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-08-23T23:22:18+00:00
- Post Title: Problem with importing AION models into blender.

Its True the script of Skaradek fail to load 60% of the models in blender
## Post #9
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-08-26T14:42:15+00:00
- Post Title: Problem with importing AION models into blender.

I had some emailing back and forth with him because I could not open anything. He told me to use the provided zip but to uninstall pyffi, it does not use the installed pyffi folder, but blender always tries to use it first.

That did not work at first but I also realized that in the registry, there was still traces of pyffi like this:

pyffi path = c:\pyffi

for example, so I had to delete those lines in registry to. So try to uninstall and get rid of all traces of pyffi
