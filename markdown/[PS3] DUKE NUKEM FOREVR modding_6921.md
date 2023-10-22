## Post #1
- Username: Snake Plissken
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 6:35 am
- Post datetime: 2011-07-06T00:55:27+00:00
- Post Title: [PS3] DUKE NUKEM FOREVR modding

first a few things off topic befor i begin. no matter what i try to do i can not get xentax to send me emails when ever some one replys to something of mine. now... also... my bad if this has been posted in the wrong spot....

Greetings. I am new so allow me to briefly to introduce myself. My name is Snake Plissken. I am currently the leader dogged “Chief Commander” of a social game networking community  known as the PMW NATION. This group has made me able to work on a verity of projects since I obtained my position as the up most ranking with in this Klan. My position currently makes me the director of there PMW NATION Development Department  to where we have been working for some time now on Duke Nukem Forever modifications.   

I’m currently working with the PS3 version of the game duke nukem forever. By using PS3 with CFW, one can present packages to there consol by ways of commercial and homebrew    pkg.         There is currently a SDK for the PS3 that can be used to make .pkgs for use of the cfw.         One such .pkg  developed with these tools was used to obtain read/Wright access to the PS3s file structure in form of FTP access via  server and client application.   At this point. We were able to back up DUKE NUKEM FOREVER in the ps3 versions entirety.


Giving us read Wright access to DUKE NUKEM FOREVER; for the ps3. 


At this point the file structure is present and I am able to back up a copy of megapackge.dat 

With the use of a application developed by a man name gorge Whitehouse  known as Noesis. I was able to extract not only the contents of meatpackge.dat but several other .dat extensions such as texturesdirectory.dat     mesh.dat,ect.


Once I have used Noesis to export the contents of meatpackge.dat I am presented with  364 items

What we are pert curly interested in at the moment is achieving a first person perspective view in both the RC monster truck, RC race car, and monster truck sequences found in game,

So with this we take look at the .u files found in our exported megapackge.dat content.   


Some files open with a batch file made with notepad++      


By opening notepad++ and typing 


"C:\Users\mchlkeeling\Games\Unreal Tournament 3\Binaries\UT3.exe" batch export %1 class .uc "C:\Users\mchlkeeling\desktop\testo\u\decompiled\classes"

"(C:where ever ut3 is located)" batchexport %1 class .uc "C:where ever you want it outputted to"

And then saving as .bat file. 


This application can be used to extract only certain .u files


We are currently under the impression that these .u files are standard UE2.5 .u files

unreal script as its called.   I have once been told that unreal script can not be recompiled but this was only once and once upon a time ago, and I have not seen this as of yet…. As of yet……

The batch application will export certain .u files such as engine.u    


Engine.u has been successfully exported into a series of  1,071    .uc files   




Now on behalf of achieving the effect of first person view on the ps3 we feel that this may be obtained by using a application known as wotgreal to view the .u file to some extent.    

So these our the achievements I have made and   at the moment my team and I have no clue on how to re-pack the extracted megapackge.dat .bat   or how to re pack or to recompile .uc files back into the .u file

Also…. Unreal editor crashes for me and I have searched the internet for why this may be but it seems that every one that uses vista gets the very same issue and I wonder if there was ever a solution to this. I would of tried a lot more development on the matter if I had a functional non crashing upon starting up version of unrealED.         

On another note I wouldn’t know where to post this next sets of questions but it seems the engine.u contains more extensions of classes for use in some type of editor then any content one would see in game. I here once on how to dump .u .uc files onto a version of UDK and it would then the UDK would see to it that it would mold to that games specific environment.   Almost like one would have to load up the game editors elements as found in the game in order to have that UDK functioning in any manner for that game…. The amount of editor content I have found inside Duke nukem forever is out of this world crazy, and I truly believe that a DUKE NUKEM FOREVER editor and all of its proper elements in order to exist and run infact do exist 100%  in its full, concealed inside each and every copy of the game…. Or at least what im seeing here. Now this is a whole another story.  And perhaps im posing this all in the wrong place.. To where if I am please just let me know and let me off with a warning for being my first time.   

But the question remains. How to re-pack the once exported content of megapakge.dat
