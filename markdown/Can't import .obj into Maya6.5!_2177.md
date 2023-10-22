## Post #1
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2006-10-27T22:35:54+00:00
- Post Title: Can't import .obj into Maya6.5!

PLEASE, anybody with Maya, do you know what I can do? I used to be able to import .obj files into Maya5 (or open), but now I have Maya 6.5 and its not working.... I get a file error. In the script editor it says:

Error: line 1: OBJ file line #####: index out of range for face creation. //
Error: Error reading file

The .obj plugin is enabled, AND I've even read that the file has to have .obj at the end of its name for Maya to recognise it, but reguardless, I can't import .obj, and I really need to! These are the files I am dealing with the most right now, and I'm really getting frustrated because I can't find the solution anywhere on the internet, and I just don't know what to do....

So please if ANYBODY finds a fix or what is going wrong here, PLEASE let me in on it! Thanks ever so much!
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-28T00:12:12+00:00
- Post Title: Can't import .obj into Maya6.5!

Maybe try makign a BASIC object from SCRATCH in maya and them exporting it with its texture to an OBJ file.
then RE-IMPORT the .obj fiel into MAYA once you have closed and reopened the program.
Then youl be able to tell if its a problem with the GENERAL obj plugin or just a certian thing about the MGS2 OBJ files that MAYA import doesnt like.
## Post #3
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2006-10-28T03:38:57+00:00
- Post Title: Can't import .obj into Maya6.5!

Wow, this is REALLY strange.....

I've tried making an object from scratch and saving it. I did this both with a polygon and a nurbs object. The nurbs object look like it opened (the file message) but nothing showed up. The polygon object worked fine. Ofcourse the MGS2 models are polygons.

And the MGS2 models still didn't show up when I changed the solidus settings, AND it still doesn't work whether I do or don't turn the .objexport plugin on.

The OTHER information I can tell you is, the .obj models I was tweaking before in Maya5 and saved (MGS2 models), they work. Ofcourse I saved them in the Maya .mb format, and they work, but whatever INFORMATION they contained still would have been there from MGS2, no?

So, we have a former .obj file, now .mb, works fine, and a Maya made .obj file, shows up fine. but FRESH .obj files, atleast from MGS2, don't seem to be working anymore,and it doesn't make a BIT of sense!  This is whether it originated as a .kmy or a .evx, it really doesn't matter, they don't work.

I've also tried to turn the MGS2 .mb files back into .obj, and sure enough, they won't open. I don't know if its more about these particular files or this plugin is messed up, but something sure is screwy here!
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-28T13:17:58+00:00
- Post Title: Can't import .obj into Maya6.5!

> Reply from TheDyingInformant
>
> 
I've also tried to turn the MGS2 .mb files back into .obj, and sure enough, they won't open. I don't know if its more about these particular files or this plugin is messed up, but something sure is screwy here!
How did u make them into MB files?
if your jsut renaming the extension then its DEFFINATLY not gonna work.
## Post #5
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2006-11-02T01:47:09+00:00
- Post Title: Can't import .obj into Maya6.5!

Well no, actually back when the .objs worked great (when I used Maya 5) when I was working on the models, I saved them in the standard Maya format, so it loads THOSE, but when I exported those back into OBJ, it won't work.

Now however I have figured out what's going on!  But.... alas, it is not time to celebrate for me.... I know now what the problem is, but not how to go about solving it for MGS2 files.

Apparantely, it seems to me, that the newer Maya versions handle .obj differently, and it doesn't like importing multiple objects/meshes. Really a shame!  It let me know this warning/limitation for a different .obj file, which was originally my robot character made up of seperate objects for limbs (instead of a skeleton and one mesh). It imported him but turned it into just one mesh/object.

But for these pesky MGS2 files, I think somehow it doesn't recognise or doesn't like the fact that a single mesh can have seperated sections to determine how the UV mapping is applied onto it.  So what I tried to do is I saved one of those previous .mb files I told you about , I selected the whole character, and I chose "combine" turning it into just one thorough mesh, unfortunately sacrificing the UV maps, but its what I have to do for now.  I exported this SINGLE mesh as an .obj, and NOW Maya will open it....  But this means that I can no longer open ANY of these files from Solidus unless I can convince Turfster to add another option to Solidus for me....

I wonder if there is a Maya workaround for importing .objs that ARE made up of multiple meshes...  Cause basically, now I know whats going on here, but I don't know what I can DO about it.  What did they have to go and change the .obj format for???  Anyway, Lionheart, take a look if you have Maya and let me know if you get the same problem. You probably do.
## Post #6
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-03T09:58:24+00:00
- Post Title: Can't import .obj into Maya6.5!

I installed maya 7.0 2 days ago now ~(Yes i had to get a new laptop and everything DAMMIT)
And in  7.0 im unable to import the MGS2 PC obj files.
its true that MAYA has changed some code within their OBJ importer.
I get a little warnign though saying that there is an abnormality in the OBJ files which is perfectly uderstandable.

But the best thing to do is to downlaod MILKSHAPE  and then import the files into that and from there export them as .3DS or something along those lines.

Alternitavly you could get 3D SUTIO MAX 7.0 (The version I own, through a shared liscense with my University) as i KNOW that opens the OBJ files fine as its what i have always used.

I only started using MAYA 1 day ago so behond my 1st ever MAYA 7.0 models.


I can now model a fair bit in MAYA along with use fur hair and soem nice texturing.
i bet you can do that in  a few seconds though lol
## Post #7
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2006-11-05T07:23:47+00:00
- Post Title: Can't import .obj into Maya6.5!

It's really such a shame you know..... It used to work in Maya5, why did they ever change the way it recognises .obj format?  Do they have some sort of problem with this format? Are they trying to steer you away from using it?  This doesn't make a whole lot of sense...

I'm used to Maya, but I'm still not a pro by any means, I have the majority of tools to learn, but I know alot of the modelling basics. I've never done anything more complex like animation, effects, and I've never had anything finished enough to get to rendering either. but that fur sure looks slick....

Anyhow, this is what sucks, to grab another program just to convert to .obj format, when Maya is SUPPOSED to support it...  I keep searching online, but I can't seem to find ANYTHING, but it must be SOMEWHERE there!  If I can't find anything, I guess really my only CHOICE will be Milkshape or whatever. There is a Maya conversion tool called Polytrans, but in the trial version it takes out every 5th polygon.... I can't imagine what a complete MESS it would make out of those already weird .evx files. It might be too hard to fix!  But maybe I'll try that again too and see if I can find any luck there.  MAN, this is sure annoying....  So I might have to ask you for a particular model that I need very soon. I'll PM you about that.

In the meantime, if anybody has any direct solution for how to solve this in Maya 6.5 or 7 (its probably the same fix), I'd really appreciate it!  Until then, I guess I'll just have to sniff around some more..... Thanks for trying though. And now that you have Maya, let me know if you figure it out
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-19T20:08:02+00:00
- Post Title: Can't import .obj into Maya6.5!

I been searchign about for a way to fix this problem for soem time now.
But my only solution is find another program to convert the OBJ into another format.
As seing as mayas importer has changed now the only other option is to either 

A: ask turfster nicely if he might be able to change the CONVERSION code for the .OBJ files so they are supported in maya

OR

B: find someone who knows maya programming language and can create a script or plugin to import the MGS2 .OBJ files correctly.

OR

C: learn the language yourself, this may sound like a doubting task but i dont imagine itd be THAT HARD, id go at it myself hell i most likely will, but thatl be in a years time when i need to know some maya script for university animation projects.
