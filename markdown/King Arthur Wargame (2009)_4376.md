## Post #1
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-04-23T16:52:00+00:00
- Post Title: King Arthur Wargame (2009)

i've successfully extracted the pak files using sir aluigi's king arthur bms script found on [http://aluigi.org/papers.htm](http://aluigi.org/papers.htm), the files inside where dds texture files and nmf model files, from what i've researched nmf file where ati normalmapping files, so i tried ATI's normal mapper to view or convert the files but to no avail it failed, it had an error which it can't read the header of the nmf file.

could you guys help me out? thank you so much! have a nice day
[BALAN_HORSE.rar](https://xentaxbackup.github.io/file/2966_BALAN_HORSE.rar)
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-04-26T10:31:02+00:00
- Post Title: King Arthur Wargame (2009)

> Reply from omfgpota
>
> i've successfully extracted the pak files using sir aluigi's king arthur bms script found on http://aluigi.org/papers.htm, the files inside where dds texture files and nmf model files, from what i've researched nmf file where ati normalmapping files, so i tried ATI's normal mapper to view or convert the files but to no avail it failed, it had an error which it can't read the header of the nmf file.

could you guys help me out? thank you so much! have a nice day

Okay, I was able to get the model using a hex editor, and pasting the vertexes and face list data.
This is not an ATI normal Mapping file though there are normal maps on the vertexes.
There are 3 meshes in this file, the horse's front and back and a rider

I giving you the links to the model and uploading a picture.


[http://ps23dformat.wikispaces.com/file/ ... orse.blend](http://ps23dformat.wikispaces.com/file/view/kahorse.blend)

I put the model in Blenders .blend format but you will need to convert it to a different format for the texture to work
(None of my hexed meshes show textures properly in blender unless I convert it again)
## Post #3
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-04-28T01:37:56+00:00
- Post Title: King Arthur Wargame (2009)

thank you so much for the reply furryfan! ok sir, i've checked it out with a hex editor, hex workshop to be exact. yes you're right. the models codes are there.  could you teach me on the procedure you used to extract the models? did you just copied the hex code pasted on a notepad and save it as another format like .obj? can you help me please, you can reply here or via pm.

thank you sir furryfan!
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-04-28T17:33:59+00:00
- Post Title: King Arthur Wargame (2009)

> Reply from omfgpota
>
> thank you so much for the reply furryfan! ok sir, i've checked it out with a hex editor, hex workshop to be exact. yes you're right. the models codes are there.  could you teach me on the procedure you used to extract the models? did you just copied the hex code pasted on a notepad and save it as another format like .obj? can you help me please, you can reply here or via pm.

thank you sir furryfan!

I did sort of copy the hex.
The first step I did was look in the file using a hex editor, and try to see If their were any vertexes, a rule a thumb is that they are usally right before the normal mappings and most normal mappings have squares that sum up to 1 (and maybe some that do not in the same game), so I can do the math on every 3 sets of floats in the file. Recognizing the texture coordinates, is more tricky, but they tend to be fractions so .4375001290 really stands out as probably being a texture map, also texture maps are usally found after the normal maps. Note some games have more than one normal map.

In this game each vertex has the following information:

VertexX, VertexY, VertexZ, NormalMap1X, NormalMap1Y, NormalMap1Z, 4byte Bone Information, NormalMap2X, NormalMap2Y, NormalMap2Z, TextureMapU, TextureMapV

I copy the vertexes from the hex editor (I use Cheat Engine, which is mainly used for memory hacking, but can open static files) into Microsoft Word, then I remove put parenthesis around every 48 byte array by using the find and replace function with the following Wildcard replace all search
Find any 2 character followed by a space (repeated 48 times)
and replace it with 
("Find what text")
Then I do a find/replace non-wildcard search to find the 13th-28th bytes and delete them.
I then remove the line break, and paste the vertex/normal/texture mapping into a blank Ogre3d binary .MESH file that is set to vertex/normal/texture.
Similary I use find/replace to take the two 00's off of the 4byte face list array, because Ogre3d uses 2byte face indexes and paste them into the file.
Then I convert .MESH into .MESH.XML and import it into blender, and delete the 1000's of null vertexes at point 0,0,0 and save the mesh as .BLEND
This sounds like a lot of steps, but it takes less than 40 seconds for me to do it. Also once I learn how to use macros in word It would be less than a few seconds.
see my website for more information because I have to study for finals and it saves time not typing everything out in full, I can have a proper King Arthur guide in a few days, if you want.
## Post #5
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-04-28T22:59:59+00:00
- Post Title: King Arthur Wargame (2009)

wow thank you for the procedures sir furryfan, ill take a look on that and try to do it on my own. 

but yes, the proper guide should really help out (me and others who's interested on this game). 

thank you so much sir, I appreciate your help and the effort you've done to help me out.
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-04-29T18:15:06+00:00
- Post Title: King Arthur Wargame (2009)

> Reply from omfgpota
>
> wow thank you for the procedures sir furryfan, ill take a look on that and try to do it on my own. 

but yes, the proper guide should really help out (me and others who's interested on this game). 

thank you so much sir, I appreciate your help and the effort you've done to help me out.

Here is the full procedure ask me if you have any questions!

Finding where the meshes begin is not easy (The headers might be contained in separte file) however in all of the sample meshes structures begin with the following properties

The vertexes begin right after "30 00 00 00 1C 11 00 00" STRUC#1
The vertexes end at "02 00 00 00 (00 00)" and the Face List begins at (00 00) STRUC#2
The Face list ends 2bytes before "00 00 00 4D 6F 64 65" STRUC#3

1. Use cheat engine to open the NMF file
2. Use the Array search function to search for "30 00 00 00 1C 11 00 00" and put all the search results in the list at the bottom of the screen
3. Use the Array search function to search for "02 00 00 00 00 00" and put all the search results in the list at the bottom of the screen
4. Use the Array search function to search for "00 00 00 4D 6F 64 65" and put all the search results in the list at the bottom of the screen
5.Sort the list by offset location, then each mesh has to have STRUC #s #1,#2,#3 in exact order, with none in between, and other results are extraneous
6. Begin right after a valid STRUC#1 by right clicking  the address list and picking "browse location in memory"
7. Hold the left mouse button down and using the pagedown button highlight the hex addresses until you reach the begining of STRUC #2
8. Right click the highlighted red hex and select copy
9. Open up Microsoft word and paste the hex in a blank document and add one space at the end and save it has VertexArray.
10. Go back in cheatengine and go 2 bytes before the end of STRUC2.
11. Select the hex untill you reach 1 byte before the beginning of STRUC3
12 Right click the red hex and press copy
13 Paste the hex in a blank Microsoft word document and add one space at the end and save it has FaceArray
14. Go back to your saved file called VertexArray and use the following "Find and Replace All" operands on the document allways starting at the beginning of the file
revome the quotes from the text strands and remember some have a single space at the end of the operand:
Find (WildCard search) "?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? "
Replace All With  "^&^l"

Find (WildCard search) "?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ?? ^l"
Replace All with "(^&"

Find (Normal search) "(^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? ^?^? "
Replace All with nothing ""


Steps 15-20 Not Applicable for this game
21. Save the file. This is the vertexes
22. Open Cheat Engine, but instead of opening the CS_ file open a new file I will put up on the "Everquest 2" [http://ps23dformat.wikispaces.com/Everquest+2](http://ps23dformat.wikispaces.com/Everquest+2) section of the website called "blankmodel1.mesh" (there are random unsorted files there) remember use the button on the left in Cheat engine and not the middle button
23. Click the middle left button that says "Memory view"
24. In this new window go to the "Tools" menu and click "Fill Memory" and put in without the quotes "2f195" in the From field and put without quotes "f1254" in the To field. And put without quotes "0" in the Fill with field. Press OK.
25. Right click the the number column in the left hand part of the screen and click "Goto Address" and type in "2f195" without the quotes. Press OK
26. Then keep cheatengine open and go back to the document you saved and select all of it and right click copy.
27. Paste everything into the first hex byte on the screen in cheat engine. It should paste after a few moments.
27B. do the same with the face array but first clear the memory from "2d" to "2f140" and then paste the faces into offset "2d"
28. Close Cheat engine
29. Download the ogreXMLconverter from [http://sourceforge.net/projects/ogre/fi ... i/download](http://sourceforge.net/projects/ogre/files/ogre-tools/1.6.0/OgreCommandLineTools_1.6.0.msi/download)
30. Then press the "Windows Start Button" and find the "Command Prompt" (In windows Vista it is under Programs->Accessories-> Command Prompt
31. Type in the path to the ogrexmlconverter.exe (Hint just the whole converter folder in the default path for me it is C:\users\mike to avoid typing the full path) then type \ogrecommandlinetools\ogrexmlconverter blankmodel1.mesh
this will only work if before you have pasted blankmodel1.mesh in the Users\yourname directory.
32. Press enter and you should see a long list of text on the screen and hopefully when it is done there will be a new file called blankmodel1.mesh.xml in the same place.
33. Next assuming you have already installed blender, download the .mesh.xml importer for blender found at [http://ogreaddons.svn.sourceforge.net/v ... _import.py](http://ogreaddons.svn.sourceforge.net/viewvc/ogreaddons/trunk/blenderimport/ogre_import.py)
34. Put that python script into the .blender\scripts folder
35. Open blender and go to the file-> import menu and select ogre. find the blankmesh1.xml file and hilight it and press import.
36. The mesh should appear but you have to before doing anything delight the 1000s of null vertexes located at 0,0,0 otherwise they will be extra vertexes and faces and the mesh will not look like anything. Hint go to edit mode and be in wire frame mode and zoom in on the default location.
Zoom in deep enough to the "Middle of chaos" and hold down control and circle around the point 0,0,0 press delete on the key board and press the option delete vertexes.
37. Zoom back out and change the mode to object mode and the display mode to filled mode.
38. Congratulations you have your mesh.
Note that these steps may take long at first, but I can do the entire list in less than 2 minutes. Also many steps like downloading you only do once.
If you have any questions please feel free to contact me or email me.
