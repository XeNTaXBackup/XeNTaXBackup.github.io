## Post #1
- Username: amoebame
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 02, 2022 6:56 pm
- Post datetime: 2022-11-02T14:49:53+00:00
- Post Title: Lego Creator: Knights Kingdom - .LCA format

Hello,

I hope you all are well.

I had a bout of nostalgia and began playing the old Lego games. I came across LC:KK and after trial/error was able to run it on a Windows 7 VM. I have a side-passion for 3D and am hoping to get more into it, with AR/VR becoming the new defacto for technology in SV. Anyways, I wanted to try my hand at extracting/converting the models to a modern obj format, and found the LC.BMS to start this process by extracting the core-files. 

Initially I tried using the old Superscape VRT application (found on [https://archive.org/details/superscape-vrt-v560](https://archive.org/details/superscape-vrt-v560) ) to try and see if they would auto-import. But due to 1) .LCA being unique format and 2) the legocreator2000.VRT in the core files running on version 5.70 (which the "latest" on archive is 5.6) created more issues. It does render an empty scene in IE using Viscape ([https://archive.org/details/VISCAPESVR](https://archive.org/details/VISCAPESVR)), but that is only for visualization not asset creation/viewing. I then tried to utilize GL extractors such as RenderDoc, NinjaRipper, amongst others in hoping to have any success. But this did not work as the application uses DX7 and the game auto-crashes when trying to start (since it is quite old).

I viewed the files first in VSCode (absolutely love the IDE), then in a hexeditor and found that the formats for the .LCA are similar to that of the .VCA which Superscape engine uses. Each single file is three in one. It contains a .SHAP, .WRLD, and .PALT. What I am having trouble doing is figuring out what the exact values are for each model (vertices/UV/etc.). Upon doing this, I can easily extract the information and put it together using blender.

I then began researching further upon what tools may be helpful in completing this task and came across this forum in addition to the MeshExtractor tool that converts Hex to a 3d object. I have uploaded a zip file containing two files, one is a .VCA file from Superscape's VRT program, and the other is a .LCA file for comparing. The link is here: [https://drive.google.com/drive/folders/ ... IwZsaRhrSi](https://drive.google.com/drive/folders/1mDvrKtDWQ6EkbRxiwvJl4kIwZsaRhrSi)

If anyone could assist or point me in the right direction, I would greatly appreciate it.

Thank you

Added: I found this link from 2000 from another person, if it is of any use: [https://news.lugnet.com/games/lego/creator/?n=25](https://news.lugnet.com/games/lego/creator/?n=25)
Added 2: I uploaded just the .SHAP portion of the file and found the following lines [https://imgur.com/a/nudf8gB](https://imgur.com/a/nudf8gB)




Added 3: I was able to extract a 2D-plane mesh using other research methods and found that the texture being mapped to it, contains the LEGO models. I think it is how the game does the rendering. Instead of an actual world, it is all rendered on a 2D mesh and textures are mapped to the plane.





Added 4: Here is a comparison of the files in SuperScape Viscape versus LC:KK


Added 5: This is a SHP file which VRT uses, holding the data used for each point/line/facet/chunk size/etc.
