## Post #1
- Username: MadMaxx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 15, 2021 7:00 pm
- Post datetime: 2021-11-15T11:12:08+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

Hello everyone    

I'm trying to extract the 3D models (character, object, map) of dragon quest 5 (PS2 version ).
So far, I have managed to get the game (patched English version) and extract all the files (after having unpacked the .BAT file containing the whole).
FILE FOR UNPACKING .DAT FILE : [https://drive.google.com/file/d/1CxhTQ1 ... sp=sharing](https://drive.google.com/file/d/1CxhTQ1sXDgRJuFTA_8MdMdXKX9xqRyN9/view?usp=sharing)

Now i find some .LZ (LZSS) files but i don't know what to do with them.   

LZ extracted file : 
[https://drive.google.com/file/d/1VSpcNE ... sp=sharing](https://drive.google.com/file/d/1VSpcNE7-uNHlz9sL0PG2C8ntrxRHRvNh/view?usp=sharing)
[https://drive.google.com/file/d/1pTsFSa ... sp=sharing](https://drive.google.com/file/d/1pTsFSa4BHR4jvjeykyOXc24-Y9wS0tGu/view?usp=sharing)


To my knowledge, there is no software allowing to open them or to convert them into an other format.
I am therefore stuck there.
It is very frustrating because all the files are there and only ask to be exploited ...  
So I wanted to know if any of you, would have an idea ( Noesis script ? ) in advance or if you thought that it will not be possible to exploit and convert the 3D models.
I can send you any file so that you can possibly see by yourself. 

[https://imgbb.com/VYQtyzr](https://imgbb.com/VYQtyzr)
[https://ibb.co/51kdy34](https://ibb.co/51kdy34)
[https://imgbb.com/MM2Pp14](https://imgbb.com/MM2Pp14)

I searched a lot on the internet and I did not find anything allowing to recover the 3D models (and texture) from a .LZ file.   

Unfortunately, I have the impression that there is no solution to recover and convert the 3D models as for the 3DS version of Dragon quest (using Ohana3DS Rebirth) for this ps2 version 

Thank you in advance for your help and have a good day !!

EDIT : 

Some screenshot of the game xD 

[https://gamefaqs.gamespot.com/a/screen/ ... 421661.jpg](https://gamefaqs.gamespot.com/a/screen/full/6/6/1/421661.jpg)
[https://gamefaqs.gamespot.com/a/screen/ ... 422212.jpg](https://gamefaqs.gamespot.com/a/screen/full/2/1/2/422212.jpg)
[https://gamefaqs.gamespot.com/a/screen/ ... 422247.jpg](https://gamefaqs.gamespot.com/a/screen/full/2/4/7/422247.jpg)
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-11-17T00:48:44+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

Use the script posted [here](https://zenhax.com/viewtopic.php?t=15242#p63813) with quickbms to decompressed the .lz files.
The 3d models use vif tags search for "20 01 03 00 XX 68" in a Hex editor to find vertices addresses, where "XX" stands for vertices count, which makes the task of extracting 3d models boring.
Example of first mesh, faces were generated automatically and uvs appear to be short type.



bianca.chaindata.png (34.5 KiB) Viewed 177 times
## Post #3
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-11-17T00:49:13+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

Textures are easier to extract, there is more than one texture in the bianca.chainadata.lz file:



bianca.chaindataimagem1.png (53.89 KiB) Viewed 176 times
## Post #4
- Username: MadMaxx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 15, 2021 7:00 pm
- Post datetime: 2021-11-17T11:22:23+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

Hello Reh,    


First of all, many thanks for your help, I was not expecting such a precise and clear answer.    
Unfortunately, after all my research, I expected to have to go through Hex2obj, which I dreaded.
To put it simply, I'm not that good at it, and I usually use out-of-the-box tools for the rips I make.
Now, with the explanations you gave me, I still understand that you did a lot of the work by identifying some crucial information and for that thank you again.


I'm not going to give up and will try the experiment with Hex2obj ( i never used hex2obj or manipulated HEX file/database , so i'm more than a noob ), but it's not off to a good start.  
To learn and start from a good base, I set myself the goal of doing the same thing as you, with the same models (and the images you posted).
And already it starts badly xD


I unzipped the same Bianka file that you used with BMS (I had used this script before, but the file that was checked out had no extension so I thought it didn't work).
I open Hex2obj and I enter the same information as on your image (following the procedure Go1> Go2> Go3) but I do not get absolutely the same result (no model to display and errors).  

 Here, I replicated the information available in your image:
 picture below:


[](https://ibb.co/4mCfSmx)



Then, I tried by modifying it ( change the max face index )  and I get a result: 3 fucking vertex displayed, no model yet..xD
 picture below:

[](https://ibb.co/m8ysvsd)






So I think I'm going to have a lot of work to get "results" and above all, if I understood correctly what you are explaining to me, the search for "vertices addresses" is long and boring for each model.  
I can't even imagine the difficulties that I will encounter for the UV part, animation etc ... (even if in reality the animations do not really interest me)
I still have a long way to go so ...






Anyway, thanks for your help with textures, I'll try to get the console texture explorer software.     


You still brought light to me in this tunnel and I will try not to let go!





EDIT1 : 

[](https://ibb.co/gzm6HxX)

And voila, the same thing with Console Texture Explorer, I entered the same data as you but I get a different result ...
Also, how did you get the exact code to put for offset graphic and offset pallet?

EDIT2 : 

Is the model that you managed to generate complete?
Because on the image you posted (in the obj viewer) it does not look like the model that we might expect (Bianka character)?
## Post #5
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-11-17T14:28:52+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

Sorry, it was my fault, I forgot that I removed some bytes from the beginning of the file when extracting, I updated the images with the correct addresses now.

> Reply from MadMaxx ↑Wed Nov 17, 2021 7:22 pm at Wed Nov 17, 2021 7:22 pm
>
> 
(I had used this script before, but the file that was checked out had no extension so I thought it didn't work).
Actually when you extract it will have no extension, i added an extension for it.
Regarding you not having the FAKE option, maybe your Hex2obj is an old version, I use 0.24e.

> Reply from MadMaxx ↑Wed Nov 17, 2021 7:22 pm at Wed Nov 17, 2021 7:22 pm
>
> 
Is the model that you managed to generate complete?

No, as I said before this type of file uses Vif tags, the model is split into several parts, for Bianka's file for example it's split into 37 parts, that's the boring part I mentioned before.

Here is a better result after a few hours of removing extra triangles and scaling UVs.



bianca.png (152.93 KiB) Viewed 175 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-17T19:25:51+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

> Reply from reh ↑Wed Nov 17, 2021 10:28 pm at Wed Nov 17, 2021 10:28 pm
>
> No, as I said before this type of file uses Vif tags, the model is split into several parts, for Bianka's file for example it's split into 37 parts, that's the boring part I mentioned before.I've updated the rws Make_H2O tool for Bianca:
.



Bianca.png (105.02 KiB) Viewed 162 times



@reh: could you confirm the uv address 0x2B18 in your updated image? Aah, should be WordUV?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-17T19:51:18+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

Here's a quick'n dirty hacked exe  tested with Bianca only! (UVs have some superfluous faces and may need to be scaled up.)
(Uses the "rws" tool for DragonQuestV.)
.


 Make_H2ODragonQuestV.zip
(31.13 KiB) Downloaded 18 times

 (fixed uv addresses)

.exe needs other files to work! Use .zip from here, 

> Reply from shakotay2 ↑Wed Apr 29, 2020 6:10 am at Wed Apr 29, 2020 6:10 am
>
> 
copy above exe into the extracted folder.

Use hex2obj version from here to create obj files from H2O files (use "Strip" "Fake"):

> Reply from shakotay2 ↑Wed Apr 29, 2020 8:32 pm at Wed Apr 29, 2020 8:32 pm
>
>
## Post #8
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-11-17T20:16:07+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

> Reply from shakotay2 ↑Thu Nov 18, 2021 3:25 am at Thu Nov 18, 2021 3:25 am
>
> 
@reh: could you confirm the uv address 0x2B18 in your updated image? Aah, should be WordUV?
Yes, i used WordUV.
This was quick, thanks to your tool it will certainly speed up the process of extracting the models, thank you!
When extracting it I also had problems with the UVs, some points out of place.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-17T20:23:27+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

@reh: I will never understand how people like you get a proper uv map from such a mess.  
Great!  

btw: don't miss to "remove doubles" from the mesh in blender if you haven't done so.

Just as a hint: the tool expects 'S' (0x53) at offset 0x80 of chaindata files ('SKMD')

----------------

> Reply from MadMaxx ↑Wed Nov 17, 2021 7:22 pm at Wed Nov 17, 2021 7:22 pm
>
> So I think I'm going to have a lot of work to get "results" and above all, if I understood correctly what you are explaining to me, the search for "vertices addresses" is long and boring for each model.Well, there's simpler 3D model formats for beginners, but this is the way you chose.
## Post #10
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-11-17T21:49:42+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

> Reply from shakotay2 ↑Thu Nov 18, 2021 4:23 am at Thu Nov 18, 2021 4:23 am
>
> 
@reh: I will never understand how people like you get a proper uv map from such a mess.  
Great!  

btw: don't miss to "remove doubles" from the mesh in blender if you haven't done so.

Just as a hint: the tool expects 'S' (0x53) at offset 0x80 of chaindata files ('SKMD')
I've already dedicated a few hours of my life editing uvs.   
Yes, I did that and remove doubles is a good tip to have a cleaner model.
I believe uvs don't work very well due to the way the file is unzipped, some bytes that should be x00 in the file are x20, but I could be wrong.
## Post #11
- Username: MadMaxx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 15, 2021 7:00 pm
- Post datetime: 2021-11-18T10:24:55+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

> Sorry, it was my fault, I forgot that I removed some bytes from the beginning of the file when extracting, I updated the images with the correct addresses now.
This is not a problem, thanks to you for the update of the information, I was able to obtain a Vertex Cloud (like yours).
This allowed me to better understand how it all works (even if I remain convinced that it is not at my level).

> Actually when you extract it will have no extension, i added an extension for it.
>
> Regarding you not having the FAKE option, maybe your Hex2obj is an old version, I use 0.24e.
I understood correctly, so I now add extensions to this type of file.
I got the version with "FAKE option", thank you!

> No, as I said before this type of file uses Vif tags, the model is split into several parts, for Bianka's file for example it's split into 37 parts, that's the boring part I mentioned before.
Alright, I understand, I think God sent shakotay2 to save us from this torment.

> Here is a better result after a few hours of removing extra triangles and scaling UVs.
Omg, wow, Great JOB !!!! You have totally passed the RIP, Really congratulations !!

> few hours of removing extra triangles and scaling UVs.
FEW HOURS !! Omg hahahaha few hours per model, there are 217 just in the "Charactere" folder XD XD XD

Again Thank you for your help Reh, you really took the subject to heart and achieved tremendous results.
## Post #12
- Username: MadMaxx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 15, 2021 7:00 pm
- Post datetime: 2021-11-18T11:19:22+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

> Well, there's simpler 3D model formats for beginners, but this is the way you chose.
No, not really , I got into the project a bit impulsively and I absolutely did not achieve the level required in this area to obtain good results (I understood better by consulting the Hex2obj Tuto and your comments.)   .
I think that without you and by continuing on this path, it would not have gotten me anywhere.   


> Here's a quick'n dirty hacked exe tested with Bianca only! UVs are a mess, need hard work to be restored.
>
> (Uses the "rws" tool for DragonQuestV.)

Thank you very much shakotay2, your hack works perfectly !!!!!!!!!!!         
I can't even imagine how you could have developed something so useful and effective, so quickly! (I don't code at all).

 I also confirm that it works with some other models, I tested it with another one taken at random and everything is going as expected:   

1> Extraction of the model with QBSM and Dragon Quest 5 PS2 script
2> Extraction of the different parts of the model (in h2o) with the shakotay2 Hack (and I imagine thanks to the information that Reh found).
3> Conversion of h2o to obj with the hex2obj version provided by shakotay2 (version capable of processing rws files, addition of the rws extension to the file extracted with QBSM)
4> Import of OBJ files (e.g With blender , used a script for multiple OBJ file import).
5> Clean The mesh (remove crazy and double face, clean normal, merge vertice etc.).
6> Next: Repair UV's, extract textures, apply everything (Reh level xD).

Now the point is this:
It is a shame that the models are cut into several parts (choice of game developers, I imagine in relation to their needs).  
It is also a pity that in the process of recovering the model, there are so many "double sided face " and "crazy faces" that appear.  
The model is completely polluted and requires painstaking work to be able to clean it (moreover, cleaning is a destructive process and it is possible to make mistakes (overprime the real face of the model ...) and have something suitable .
Too bad the UV is not preserved correctly.

> I've already dedicated a few hours of my life editing uvs.

 ̶P̶e̶r̶s̶o̶n̶a̶l̶l̶y̶,̶ ̶i̶f̶ ̶I̶ ̶h̶a̶d̶ ̶t̶h̶e̶ ̶t̶e̶x̶t̶u̶r̶e̶s̶,̶ ̶I̶ ̶w̶o̶u̶l̶d̶n̶'̶t̶ ̶t̶r̶y̶ ̶t̶o̶ ̶a̶r̶r̶a̶n̶g̶e̶ ̶t̶h̶e̶ ̶U̶V̶s̶ ̶o̶f̶ ̶t̶h̶e̶ ̶m̶o̶d̶e̶l̶s̶ ̶(̶t̶o̶o̶ ̶m̶e̶s̶s̶y̶)̶ ̶b̶u̶t̶ ̶I̶ ̶w̶o̶u̶l̶d̶ ̶r̶e̶d̶o̶ ̶t̶h̶e̶m̶ ̶c̶o̶m̶p̶l̶e̶t̶e̶l̶y̶ ̶(̶m̶a̶n̶u̶a̶l̶ ̶u̶n̶w̶r̶a̶p̶)̶.̶
̶I̶t̶'̶s̶ ̶a̶l̶r̶e̶a̶d̶y̶ ̶m̶o̶r̶e̶ ̶i̶n̶ ̶m̶y̶ ̶s̶k̶i̶l̶l̶s̶.
Forgot that, very difficult, I don't think I can for all models xD
shakotay2 is right, really impressive work Reh.


Despite everything, with this face and UV problem, the treatment for each model remains relatively long (I recommend blender because the cleaning tools are really good, eg vertex merge, interior face select etc ...), but incomparable with what it was initially, thank you again Reh and shakotay2, you saved us a lot of time !!!!!!!     

Here are some examples of what I have achieved:

BASEHERO MDL EXTRACTED AND CONVERTED 
:[](https://ibb.co/6w6S0Jv)
BASEHERO CLEANED MDL : 
[](https://ibb.co/J3kwmcs)
Destructive cleaning process and accidental loss of a face of the model : 
[](https://ibb.co/M7DB2DL)
Fucking Crazy Uv's : 
[](https://ibb.co/zSQs9YX)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-18T11:40:29+00:00
- Post Title: [PS2] NEED HELP ! DRAGON QUEST 5 LZSS 3D MODELS

> Reply from MadMaxx ↑Thu Nov 18, 2021 7:19 pm at Thu Nov 18, 2021 7:19 pm
>
> I can't even imagine how you could have developed something so useful and effective, so quickly!Well, because I didn't it thus quickly!  As I wrote it's from the rws tool (from 18 months ago, that wasn't a quick hack).

> Reply from shakotay2 ↑Wed Apr 29, 2020 6:10 am at Wed Apr 29, 2020 6:10 am
>
> 

The quick hack was to patch the rws tool for DragonQuestV.

And yes, there seems to be a bug in calculating the uv addresses, half of them were 2 bytes too big, wrong alignment, whatever.

edit: fixed uv addresses, see zip here:

> Reply from shakotay2 ↑Thu Nov 18, 2021 3:51 am at Thu Nov 18, 2021 3:51 am
>
> 
Still some superfluous faces in uv map but not a mess as before.
