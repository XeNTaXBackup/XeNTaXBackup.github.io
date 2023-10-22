## Post #1
- Username: SLR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 30, 2013 3:07 pm
- Post datetime: 2013-06-02T07:49:57+00:00
- Post Title: Scarlet Blade character model extractions

Hi,

I'm new to posting in this forum, but have been a regular visitor to do research into character model extraction for Scarlet Blade.

Having read posts regarding Queen's Blade model extraction using Finale00's Noesis script, and implementing the same script to Scarlet Blade, I was very much relieved to see how effective the process was.

Coming from a computer forensic background, I was initially using IDA and X Ways to do memory analysis trying to find my character in the SB.EXE process. Unfortunately, the process is locked and is difficult to dump. The Belkinsoft forensic imaging program claims to be able to dump locked processes, though even after doing this I was unable to find any solid evidence of my character as it was displayed at the "Choose Character" menu.
It was soon after this that I found the Noesis script by Finale00 (thank you very much by the way . So now I can just recreate my character from the objects contained within the gfpk files, and of course apply all sorts of different costumes if I choose.

The new issue for me though is that as I am somewhat new to 3D modelling, I would like to know how I can import all character files necessary to display the character as it would appear in game. For example, the run animation, the various standing animations, and the textures. I have been able to import all the meshes for a character into 3D Studio Max, but when I apply any DDS texture associated with the mesh, it seems like it is skewed or off-centre. Is there a change I need to make during the import texture process to make it fit the mesh correctly?

In addition to this, can anyone tell me what is the preferred or most user friendly 3D modelling software (ie 3D Studio Max/Blender etc) to import all character files as well as their DDS textures and bones/animations? 

Here is a link to my initial posts in another forum in case you want to check out some history of my research: [http://forum.ragezone.com/f111/scarlet- ... on-934074/](http://forum.ragezone.com/f111/scarlet-blade-character-model-extraction-934074/)

Thank you in advance! I look forward to spending more time in this forum.
## Post #2
- Username: TinyGuy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 24, 2009 6:43 pm
- Post datetime: 2013-06-06T17:35:59+00:00
- Post Title: Scarlet Blade character model extractions

Hey mate. I've been working on SB recently. I wrote plugin for Cinema4D R12 which can import models with their bones directly from gfpk archives. You can try it if you like.



Download: [http://www.mediafire.com/download/iprll ... c4dr12.zip](http://www.mediafire.com/download/iprlly5ed38t666/sbimporter_c4dr12.zip)
## Post #3
- Username: SLR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 30, 2013 3:07 pm
- Post datetime: 2013-06-12T09:25:06+00:00
- Post Title: Scarlet Blade character model extractions

Thanks for replying to my post with an awesome solution  I'm in the process of acquiring Cinema 4D R13, do you think this will be ok for your plugin?
## Post #4
- Username: SLR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 30, 2013 3:07 pm
- Post datetime: 2013-06-13T10:41:51+00:00
- Post Title: Scarlet Blade character model extractions

Disregard previous reply.

The plugin does work, but with the 32bit version of R13 only. 

I'm currently trying to view the textures on the imported model but can't for some reason. Can you please provide a brief walk through for importing meshes and textures?

Thanks again
## Post #5
- Username: TinyGuy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 24, 2009 6:43 pm
- Post datetime: 2013-06-13T11:08:05+00:00
- Post Title: Scarlet Blade character model extractions

In plugin you must select two directories (under list box where you choose bone file). First one is path to some directory where textures will be extracted (It shouldn't be anywhere on your C: - because there may be access rights problem etc. But you can try Your Document directory). Second path is where the game is installed (where game launcher is located). This should help.
## Post #6
- Username: SLR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 30, 2013 3:07 pm
- Post datetime: 2013-06-13T11:59:43+00:00
- Post Title: Scarlet Blade character model extractions

Thanks again 

I've kind of worked it out, and the following is a simple guide to the extraction:

I've identified the issue. The texture file "sati.dds" needs to be extracted via QuickBMS from the "ScarletBlade\Data\Objects\NPC\tex\tex.gfpk" file in order to be applied to the mesh. The texture files are then selected beneath the "Select Bone File" section of the plugin.

Step by step process

When selecting a character mesh, having had the character's *.gfpk been extracted via the same QuickBMS method, each body and costume for a character is independent of the body type. For example, the file WH_BD_CS_30.mesh appears to be a schoolgirl costume or similar for the Whipper, and each file with the same WH_BD_CS precursor is a different costume. Having played WoW previously, I don't think that the character armor in WoW is structured the same way. I think that each piece of armor is it's own mesh which is applied to the main body. 
Anyway, once the body has been identified, import the character gfpk via the Cinema 4D 32 bit plugin kindly created by TinyGuy. 

Select the wh_bd_cs_13.bone file.

Under this in the first selection box, find the WH_BD_CS_30.dds file from ScarletBlade\Data\Objects\PC\tex\a\Objects\PC\tex
The second box I just leave as the same. Though given TinyGuy's explanation, it would make sense to make this whatever he said it should be.

You will see the Whipper schoolgirl body be imported with it's associated textures.

To add the desired face, go through the same process again but this time select the desired face file from \ScarletBlade\Data\Objects\PC\WH\a\Objects\PC\WH\FC, such as WH_FC_N_07.mesh.
I selected the same  wh_bd_cs_13.bone file from the drop down list, and then the same texture file directory.

The mesh will appear with the texture wh_fc_n_07_nr.dds but this can be changed on the right hand side in the attributes box under color/texture (...) to the desired face.

The same procedure has to be performed to import hair and any other objects you may want.

I use Noesis to quickly open dds files to determine which object I want to import.

Attached is the screenshot of the result of the above process. The hair is some kind of weird pirate hat associated with the WH HR files which was easy to fit in. I suspect that the other hair styles are generic so should fit each character model regardless of the specified WH/PU/DE/etc as a filename precursor.
[WH Schoolgirl pirate hat.jpg](https://xentaxbackup.github.io/file/6463_WH Schoolgirl pirate hat.jpg)
## Post #7
- Username: SLR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 30, 2013 3:07 pm
- Post datetime: 2013-06-13T12:50:32+00:00
- Post Title: Scarlet Blade character model extractions

Hair update:

File attached is WH_HR_N_08.mesh on previously specified body.
Hair piece: CO_HR_N_51.dds (CO = Common?)
Colour changed to blonde/yellow and mix strength reduced to 72%.
[WH_HR_N_08.jpg](https://xentaxbackup.github.io/file/6464_WH_HR_N_08.jpg)
## Post #8
- Username: SLR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 30, 2013 3:07 pm
- Post datetime: 2013-07-15T13:01:09+00:00
- Post Title: Scarlet Blade character model extractions

Same images pasted: This look familiar people?


The pirate hat that costs 5000 AP or whatever...

and



Going to see if it's possible to get the pink uniform happening. It may have been added in a patch as I didn't see it in the previous model lists.
## Post #9
- Username: SLR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 30, 2013 3:07 pm
- Post datetime: 2013-07-15T14:27:58+00:00
- Post Title: Scarlet Blade character model extractions

This is a Defender in a pilot outfit that has not been released yet (as far as I'm aware):



Files:
de_bd_cs_16.mesh
de_fc_n_04.mesh
de_hr_n_19.mesh
## Post #10
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2013-10-31T02:15:05+00:00
- Post Title: Scarlet Blade character model extractions

> Reply from SLR
>
> This is a Defender in a pilot outfit that has not been released yet (as far as I'm aware):

Files:
de_bd_cs_16.mesh
de_fc_n_04.mesh
de_hr_n_19.mesh

All its fine, but u forget post the BMD script to extract the textures, can u post please?.
## Post #11
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-11-01T04:54:38+00:00
- Post Title: Scarlet Blade character model extractions

> Reply from Rimbros
>
> SLR wrote:This is a Defender in a pilot outfit that has not been released yet (as far as I'm aware):

Files:
de_bd_cs_16.mesh
de_fc_n_04.mesh
de_hr_n_19.mesh

All its fine, but u forget post the BMD script to extract the textures, can u post please?.
 ¿¿?? 

Is that crap different from queen's blade format?? As far as I know it's the same game but "renamed" as Scarlet Blade.
## Post #12
- Username: SLR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 30, 2013 3:07 pm
- Post datetime: 2013-12-10T11:16:27+00:00
- Post Title: Scarlet Blade character model extractions

Hey,

It's been so long since I had a look at this stuff, I'm just going through all my old extractions to find what you're after.

Yes, Scarlet Blade is basically an adult version of Queen's Blade. This means that most of the Queen's Blade extraction methods will work with these files.

I found this post helpful: Queen's Blade MMO [viewtopic.php?t=8202&p=83118#p83118](http://forum.xentax.com/viewtopic.php?t=8202&p=83118#p83118)

Refer to finale000's Noesis code/plugins for the Queen's Blade and or Scarlet Blade BMS script. I am reluctant to repost anything that he (or she) has made.
## Post #13
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-18T16:48:26+00:00
- Post Title: Scarlet Blade character model extractions

> Reply from TinyGuy ↑Fri Jun 07, 2013 1:35 am at Fri Jun 07, 2013 1:35 am
>
> 
Hey mate. I've been working on SB recently. I wrote plugin for Cinema4D R12 which can import models with their bones directly from gfpk archives. You can try it if you like.
Hello TinyGuy! is any way of pack a .mesh .bone etc into a gfpk archive? or you could modify the script to can load a .mesh too please? I have some unpacked gfpk archives and .mesh cannot be loaded into cinema4d   . Thanks alot for you script!
