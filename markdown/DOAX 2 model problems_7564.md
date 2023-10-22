## Post #1
- Username: fubartactyx2011
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 16, 2011 11:33 pm
- Post datetime: 2011-10-25T03:15:57+00:00
- Post Title: DOAX 2 model problems

Hi.  I'm new to modding and this forum as well, but I aspire to be a contributor some day.

Anyway, I have a few issues about the DOAX 2 models.  I sent a message to mariokart64n on his Youtube channel regarding all my problems at the time and despite being quite lengthy he still generously replied.  However, there are few things I still can't figure out and instead of pestering mariokart64n exclusively, I think it's much more fair to address these items in the forum:

-Fixing the flat hair on the models (I know there was a thread that mentioned the same issue, but that wasn't the topic in focus and it was never resolved)
-Importing in to 3D Studio Max 2010 using a md5mesh importer script 
-Rigging the face

I used Noesis to export the models as SMD, Wunderboy's SMD importer: [http://www.wunderboy.org/3dapps.php](http://www.wunderboy.org/3dapps.php) to import the body models and Cannonfodder's SMD importer: [http://www.chaosincarnate.net/cannonfodder/3dsmax.php](http://www.chaosincarnate.net/cannonfodder/3dsmax.php) to import the head models.  Body is fine and I figured out how to resolve the "double feet" effect.  The head however, has flat hair.  Here's an example of Hitomi's head model:



Anyone know how to fix this to look like proper strands?  Do I actually have to edit the vertices manually or is there a simpler approach (i.e.: an option in a modifier?)

In terms of the md5mesh, I tried importing them using the one mariokart64n suggested: [http://www.gildor.org/downloads](http://www.gildor.org/downloads) but when I run it I receive the following error:  "--Unknown property: name in undefined"



I used the debugger to highlight the suspect code, but I don't know how to resolve it. I've seen this error mentioned on other forums, but no one seems to have a solution.

Lastly, does anyone know a good tutorial on how to rig a face?  I think I have a couple of ideas, or theories for streamlining it, but I'm not too confident at this point.

That's all for now.  Thanks to everyone on the forum.  I admire all your skills!
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-10-25T03:52:51+00:00
- Post Title: DOAX 2 model problems

what do you mean by flat?

I'm going to take a wild guess and forgive me if I'm wrong

but do you mean how do you enable the texture transparency?

three primary colours are used to makeup a single. Red, Green, Blue.

in 2D formats they also added a 4th. this was called the texture mask.
now more commonly used for texture transparency, but has an inf number of uses...

to enable this 4th channel as we call it you need to go into the max material editor.
open the hair material and copy the diffuse texture to the opacity map slot. open the properties of the texture on the opacity slot.
and enable texture alphas
## Post #3
- Username: fubartactyx2011
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 16, 2011 11:33 pm
- Post datetime: 2011-10-26T04:03:40+00:00
- Post Title: DOAX 2 model problems

Hi mariokart64n.  Thanks again for taking the time to help me out.

Wanted to reply earlier, but I was doing overtime at my work (ironically enough, I'm in the managed IT field ).  Anyway, I experimented with some interpretations of your advice (to be honest, some terms just went over my head    ), at the end here's what I did:

-Opened material editor, copied one the dds texture files on to both the Diffuse Maps and the Opacity Maps:



-Then I went into the Opacity Maps Parameters, went down into Mono Channel Output and selected Alpha and applied the texture:



Rinse and repeat.

I know the textures are all inappropriately assigned--and maybe I'll have to figure that out myself, but in terms of the process is this what you meant?

If it is...woohoo!  Progress!  Now all I have to do is figure out how to (and I bet you hear this often  ) bone her face.

Thanks again mariokart64n!
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-10-28T02:30:17+00:00
- Post Title: DOAX 2 model problems

I was wodnering why I had never created a script for this, since its such a tedious action in 3dsmax :/

here I wrote this:

```
button btn1 "BIG BUTTON" pos:[23,18] width:252 height:57
label lbl1 "Script Will Copy the DiffuseMap over to the OpacityMap on Selected Objects. Beware that OpacityMaps Impact \
Performance! So becareful Only to Run this On objects that \"Need\" Alphas/Opacity On!" pos:[6,88] width:288 height:75
fn EnableAlpha mat =(mat.twoSided = on;mat.diffuseMap.monoOutput = 0;mat.diffuseMap.alphaSource = 2
mat.diffuseMap.preMultAlpha = on;mat.opacityMap = Bitmaptexture fileName:mat.diffuseMap.filename
mat.opacityMap.monoOutput = 1;mat.opacityMap.alphaSource = 0
mat.opacityMap.preMultAlpha = off;mat.FilterColor = color 128 128 128)
on btn1 pressed do(obj=selection;for i = 1 to obj.count do(if obj[i].material!=undefined do(
case of((classof obj[i].material==StandardMaterial): (EnableAlpha obj[i].material)
(classof obj[i].material==MultiMaterial): (for x = 1 to obj[i].material.numsubs do(EnableAlpha obj[i].material.materialList[x])));messageBox "Done!")))
) createDialog enaOpa
```


pop that into a text file rename to whatever.ms and just drag and drop it into 3dsmax (win7 UAC may disable drag and drop?) if thats the case go into max, goto maxscript > Run, open it there.
the result is a float box with a button, select objects you wish to preform the texture operation on and press the Big Button.

some people have a messed up viewer port(mis-configured?), so changes may not be visible. so its best to press F9 to perform a render to see if the changes have occurred.

-mariokart64n
