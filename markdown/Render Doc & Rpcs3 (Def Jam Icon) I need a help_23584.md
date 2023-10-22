## Post #1
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2021-03-13T15:38:11+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

Hello guys!!

Since the new version of Rpcs3 is excellent
copes with PS3 games, I was tried
get models from the game Def Jam Icon. 

1) I have tested Render Doc (v1.12) & Rpcs3 compatibility
and got geometry, but the structure of the columns in
CSV table are different from PC games.
There are files with models in the Render Doc,
and exported to CSV, but in blender plugin
they dont opened, it gives an error. 

2) RenderDoc + FBX Exporter
it is based on the old version of RenderDoc and Rpcs3
got only 1 fps, without loading scenes, aint possibilities
get the data.

3) also tested csv2obj - no results. 

I attached examples of files: 
icon-jeezy-test.csv - example from Rpcs3
mafia3-simpleobj-test.csv - example from PC game

I really hope for your help, as I want to get it for a long time
all models from the game Def Jam Icon..
Thanks.

[https://www.mediafire.com/file/lgakq3yu ... s.zip/file](https://www.mediafire.com/file/lgakq3yuhsj3urh/samples.zip/file)
## Post #2
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2021-03-14T18:06:59+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

I have some progress, just changed values of CSV file in google doc, and delete strings with "Restart" words, make correct numbers in VTX, and after blender plugin is work. But in model has many holes, and wrong gluing polygons... Still waiting for experts opinion, just need to know what I doing wrong, cause I guess now it much closer to fix it
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-03-15T12:11:26+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

> Reply from JimmyJ ↑Mon Mar 15, 2021 2:06 am at Mon Mar 15, 2021 2:06 am
>
> 
delete strings with "Restart" words, make correct numbers in VTX, and after blender plugin is work. But in model has many holes, and wrong gluing polygons...
The "Restart" identifiers are used to mark the end of the triangle strip. Perhaps the plugin supports only normal triangles?



icon-jeezy-test.png (142.23 KiB) Viewed 279 times



But getting the model from the GPU like this is definitely not a good idea. Better start with the original game files instead.
## Post #4
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2021-03-16T09:09:03+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

> Reply from Bigchillghost ↑Mon Mar 15, 2021 8:11 pm at Mon Mar 15, 2021 8:11 pm
>
> 
JimmyJ wrote: ↑Mon Mar 15, 2021 2:06 am
delete strings with "Restart" words, make correct numbers in VTX, and after blender plugin is work. But in model has many holes, and wrong gluing polygons... 

The "Restart" identifiers are used to mark the end of the triangle strip. Perhaps the plugin supports only normal triangles?
icon-jeezy-test.png


But getting the model from the GPU like this is definitely not a good idea. Better start with the original game files instead.
Thanks you for attention.
1) I try to load only one section before "restart" line is coming, and that triangles isnt glues 
Here is what I got 
here is blender script maybe you can better found a problem
[https://github.com/sbobovyc/GameTools/b ... ort_pix.py](https://github.com/sbobovyc/GameTools/blob/master/Blender/import_pix.py)

2) some time ago we try to load models from game files
Beedy a lot help me, he was created Noesis script for rx2 models and textures, but main character dont load it, cause have morphs, and quantity of verticles did not match   
and shakotay2 help too, just loaded rx2 model in Hex2obj model have some bugs, but I fix it manually
here is samples of same character (from renderdoc) model
[https://www.sendspace.com/file/ozdhvx](https://www.sendspace.com/file/ozdhvx)

and also more information are here
[viewtopic.php?f=16&t=21785](https://forum.xentax.com/viewtopic.php?f=16&t=21785)
[https://zenhax.com/viewtopic.php?f=7&t= ... n&start=40](https://zenhax.com/viewtopic.php?f=7&t=9490&hilit=def+jam+icon&start=40)
## Post #5
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2021-03-18T16:25:38+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

Updating

1) Yesterday I was remember that Def Jam Icon came out and for Xbox360, and tested it on RenderDoc + Xenia
emulator, I was hope this format will be for the script for blender more understandable, Render Doc with task
did it, but the structure of the columns is very similar on those from the PS3 version, and the geometry is clear, but
the script doesnt recognize "Restart" lines.  Here is example of 2 same scenes for RenderDoc 1.12
one from PS3 and one from Xbox360:
[https://mega.nz/file/hxElGaQB#6vXm0f1qj ... 5VguDZRG98](https://mega.nz/file/hxElGaQB#6vXm0f1qjSuGUtSqSRiQtwzPIAjRPfpER5VguDZRG98)

2) I found an alternative FBX exporter (made on python) for Render Doc on one Chinese site, it works
with PC games, but with version models PS3 and Xbox360 - isn't. When I was try to export model, nothing happend
and have that warrings in log:

It only works with install extension in RenderDoc
[https://github.com/FXTD-ODYSSEY/RenderDoc2fbx](https://github.com/FXTD-ODYSSEY/RenderDoc2fbx)

I'm not the first who notice this bug, already several people wrote to the author of the script on github

here is tutorial how to make scripts for RenderDoc
[https://blog.l0v0.com/posts/c12b915c.html](https://blog.l0v0.com/posts/c12b915c.html)

3) What conclusion did I come to: Models from PC games are displayed in the tab "VS In", models from PS3 and Xbox360
in the "VS Out" tab, it can also affect for the absence of triangles when exporting, without the "Restart" lines as Bigchillghost
wrote may not properly close the build chain polygons. Also PC files has name of colums POSTION.x, POSTION.y, POSTION.z. in
Xbox360 scene it named SV_Position.x, SV_Position.y, SV_Position.z.


I spent for it test around 5 hours, Does anyone have the ability to own Python programming skills check this exporter or fix it for games PS3 and Xbox360 for RenderDoc?
## Post #6
- Username: YosefMarkuz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 18, 2021 1:13 am
- Post datetime: 2021-04-17T19:10:17+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

> Reply from JimmyJ ↑Sat Mar 13, 2021 11:38 pm at Sat Mar 13, 2021 11:38 pm
>
> 
Hello guys!!

Since the new version of Rpcs3 is excellent
copes with PS3 games, I was tried
get models from the game Def Jam Icon. 

1) I have tested Render Doc (v1.12) & Rpcs3 compatibility
and got geometry, but the structure of the columns in
CSV table are different from PC games.
There are files with models in the Render Doc,
and exported to CSV, but in blender plugin
they dont opened, it gives an error. 

2) RenderDoc + FBX Exporter
it is based on the old version of RenderDoc and Rpcs3
got only 1 fps, without loading scenes, aint possibilities
get the data.

3) also tested csv2obj - no results. 

I attached examples of files: 
icon-jeezy-test.csv - example from Rpcs3
mafia3-simpleobj-test.csv - example from PC game

I really hope for your help, as I want to get it for a long time
all models from the game Def Jam Icon..
Thanks.

https://www.mediafire.com/file/lgakq3yu ... s.zip/file

How did you get RenderDoc working with RPCS3?
## Post #7
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2021-04-25T17:04:49+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

> Reply from YosefMarkuz ↑Sun Apr 18, 2021 3:10 am at Sun Apr 18, 2021 3:10 am
>
> 
JimmyJ wrote: ↑Sat Mar 13, 2021 11:38 pm
Hello guys!!

Since the new version of Rpcs3 is excellent
copes with PS3 games, I was tried
get models from the game Def Jam Icon. 

1) I have tested Render Doc (v1.12) & Rpcs3 compatibility
and got geometry, but the structure of the columns in
CSV table are different from PC games.
There are files with models in the Render Doc,
and exported to CSV, but in blender plugin
they dont opened, it gives an error. 

2) RenderDoc + FBX Exporter
it is based on the old version of RenderDoc and Rpcs3
got only 1 fps, without loading scenes, aint possibilities
get the data.

3) also tested csv2obj - no results. 

I attached examples of files: 
icon-jeezy-test.csv - example from Rpcs3
mafia3-simpleobj-test.csv - example from PC game

I really hope for your help, as I want to get it for a long time
all models from the game Def Jam Icon..
Thanks.

https://www.mediafire.com/file/lgakq3yu ... s.zip/file


How did you get RenderDoc working with RPCS3?
Hi, it was easy, just use a last version of RenderDoc and RPCS3. I guess someone help to found issue, cause Def Jam its one of thousend games which people wants to rip from PS3 or Xbox360, which was not possible earlier
## Post #8
- Username: YosefMarkuz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 18, 2021 1:13 am
- Post datetime: 2021-04-26T00:13:16+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

But how exactly did you rip from the game? I only receive and error with Vulkan
## Post #9
- Username: YosefMarkuz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 18, 2021 1:13 am
- Post datetime: 2021-04-26T12:52:47+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

> Reply from JimmyJ ↑Mon Apr 26, 2021 1:04 am at Mon Apr 26, 2021 1:04 am
>
> 
YosefMarkuz wrote: ↑Sun Apr 18, 2021 3:10 am
JimmyJ wrote: ↑Sat Mar 13, 2021 11:38 pm
Hello guys!!

Since the new version of Rpcs3 is excellent
copes with PS3 games, I was tried
get models from the game Def Jam Icon. 

1) I have tested Render Doc (v1.12) & Rpcs3 compatibility
and got geometry, but the structure of the columns in
CSV table are different from PC games.
There are files with models in the Render Doc,
and exported to CSV, but in blender plugin
they dont opened, it gives an error. 

2) RenderDoc + FBX Exporter
it is based on the old version of RenderDoc and Rpcs3
got only 1 fps, without loading scenes, aint possibilities
get the data.

3) also tested csv2obj - no results. 

I attached examples of files: 
icon-jeezy-test.csv - example from Rpcs3
mafia3-simpleobj-test.csv - example from PC game

I really hope for your help, as I want to get it for a long time
all models from the game Def Jam Icon..
Thanks.

https://www.mediafire.com/file/lgakq3yu ... s.zip/file


How did you get RenderDoc working with RPCS3?

Hi, it was easy, just use a last version of RenderDoc and RPCS3. I guess someone help to found issue, cause Def Jam its one of thousend games which people wants to rip from PS3 or Xbox360, which was not possible earlier

Also how did you get the model out of there?
## Post #10
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2021-04-26T14:27:28+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

> Reply from YosefMarkuz ↑Mon Apr 26, 2021 8:52 pm at Mon Apr 26, 2021 8:52 pm
>
> 
JimmyJ wrote: ↑Mon Apr 26, 2021 1:04 am
YosefMarkuz wrote: ↑Sun Apr 18, 2021 3:10 am


How did you get RenderDoc working with RPCS3?

Hi, it was easy, just use a last version of RenderDoc and RPCS3. I guess someone help to found issue, cause Def Jam its one of thousend games which people wants to rip from PS3 or Xbox360, which was not possible earlier


Also how did you get the model out of there?

I dont get models, cause script export wrong geometry without many triangles just use csv. Main problem in structure of columns that why script is not working

also your graphic card should be with vulcan for good fps
## Post #11
- Username: YosefMarkuz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 18, 2021 1:13 am
- Post datetime: 2021-04-29T00:25:06+00:00
- Post Title: Render Doc & Rpcs3 (Def Jam Icon) I need a help

I do have and AMD and if i remember correct then AMD cards mostly work better with vulkan then nvidia. So you do not get the models then?
