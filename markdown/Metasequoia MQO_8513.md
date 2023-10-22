## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-10T06:31:50+00:00
- Post Title: Metasequoia MQO

[http://db.tt/5hKTlxiL](http://db.tt/5hKTlxiL)

Common japanese model format, since it is a very simple format and easy to understand.
The tool is also pretty easy to use as well and has a bunch of plugins.

A good format for getting to know how the basics in 3D work since you can just throw together some 3D model in the editor and then look at the file in notepad.

Also a good exercise for text parsing.
How I'm parsing it is actually pretty crude; especially when extracting the different values.

Anyone have any better ideas how I should be parsing the file?
Actually, I think trying to split each field in each line is actually a great programming exercise LOL

Some samples from FF11

[https://docs.google.com/open?id=0BxmE9E ... EyYzkyMGJl](https://docs.google.com/open?id=0BxmE9EG7QMMRMGI2NjdlODYtNWQ3ZS00MDc5LWJmOTYtZWRjMWEyYzkyMGJl)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-03-10T07:23:46+00:00
- Post Title: Metasequoia MQO

Thanks for sharing, there is also an *.mqo import/export plugin that works with the free [Softimage Modtool 7.5](http://usa.autodesk.com/adsk/servlet/pc/item?id=13571257&siteID=123112) explained here:
[http://nullorempry.jimdo.com/work-list/softimage/](http://nullorempry.jimdo.com/work-list/softimage/)

You can download it here:
[https://skydrive.live.com/?cid=CE4C74ED ... 3245%21164](https://skydrive.live.com/?cid=CE4C74EDA2A73245&id=CE4C74EDA2A73245%21164)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-10T07:51:54+00:00
- Post Title: Metasequoia MQO

Cool, it's nice to see more MQO support out there lol

But man, how do I actually parse these things.

```

```


I guess I'll need to come up with a regex to split this...

EDIT: stackoverflow is awesome.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-10T16:13:24+00:00
- Post Title: Metasequoia MQO

Here's something I hacked together.
Clearly text parsing can get a little messy especially when trying to convert values from string to float/int, with calls to the map function everywhere (it's similar to the map function in lisp languages). A simple analysis would show that there's huge overhead just to throw stuff in one place, then pick them out and throw them into another place while converting from string to float to bytes...

It's even worse when UV's are stored per-face.

[http://db.tt/2yDxygHC](http://db.tt/2yDxygHC)

Maybe I should try doing it in immediate mode to see if it is any better.
## Post #5
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-10T19:37:19+00:00
- Post Title: Metasequoia MQO

There is a java applet you could rip the parser out of, it's down atm, so uploaded the java code for you as well.
Applet :- [http://d00.cool.ne.jp/metase/mqov/v1_3/ku.html](http://d00.cool.ne.jp/metase/mqov/v1_3/ku.html) 
Java code :- [http://uppit.com/w6c0zl719mol/mqo3k.zip](http://uppit.com/w6c0zl719mol/mqo3k.zip)

There's also 3dsmax plugins for this format.

I hate writing mqo converters, when exporting to that format I always resort to dumping the UVs to a temp file - lazy.
And for importing mqo files, you got to evade the vertex colors, weights and blobs, as well as contend with 2,3 and 4 vertex polygons.

Seriously though, it is pretty easy to convert, and very useful software, my main modeler, use 3dsmax for the stuff it can't do, like render.
Use it to view vertices only, 2 V(0,0), great for making random point clouds.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-10T20:02:36+00:00
- Post Title: Metasequoia MQO

MQO is structured pretty well so if I'm reading a struct that I want, I can parse it, else I just skip. The regex I got for parsing each line into tokens makes it much easier to work with.

I use a "skip to next struct" function which will just keep skipping lines until I read a line starting with Scene, Material, Object, or EOF. Of course atm noesis will crash on non-utf8 strings cause I can't specify the encoding I want to use when reading lines.

I think the main problem I'm having with per-face formats is that...well it's per-face lol the output looks kind of funny and wrong when I use immediate mode rendering for unknown reasons.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T20:58:20+00:00
- Post Title: Metasequoia MQO

Wow, the author decided to mix binary data and text data together...

I mean I guess everything can be parsed as a binary file, but really..? It looks like it was meant to be a text file!

This occurs in the Object struct where it says "BVertex" rather than "vertex". The file uses 3 floats, in binary, to define the coords.
