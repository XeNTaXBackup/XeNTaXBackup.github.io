## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2013-07-01T13:25:27+00:00
- Post Title: [Release] Naughty Dog Texture Editor

Hello everyone. I made a little program that can view and replace textures in .pak files and I wanted to share it with you. Here is how to use it.
Download : [http://www.mediafire.com/download/1wayc ... Editor.rar](http://www.mediafire.com/download/1waycem6bs0tabh/NDTextureEditor.rar)

How To Use Tutorial:
First of all make sure you have all required files. "TextureEditor.exe" and "libsquish.dll" must be in the same folder. You also need to have a pak file to load. You can use PSARC Extractor tool to extract pak files from psarc archieves just google it and you will find it. Make sure you have a backup of your pak file in case you mess up. So for this tutorial I will use the pak file "ellie-jacket-cloth-snow.pak" which is extracted from actor34.psarc and it has the textures for Ellie's outfit in winter season. We open the TextureEditor.exe and we click "File" tab on top and we choose "Open.." and a window will pop up to choose our pak file. We choose our .pak file and click OK.


Now that our file is loaded we can see the texture names and compression types in the list and we can see the texture previews on the right side of the list.


To export the textures we click "Export Textures" button on top menu and click "PNG" from sub menu. (Png is the only export method anyway ) After that a message box should pop up saying that the textures are succesfully exported. A folder will be created in the directory of the program and the textures will be in that folder. In my case the folder is called "ellie-jacket-cloth-snowtextures", it depends on your .pak file name.


We go into our folder and select the texture that we want to edit. You can use any image editing software you desire but the software must be able to save textures as .dds. So I recommend using Paint.net which already has dds support or photoshop/gimp which have dds plugins.

I want to edit Ellie's jacket so I right click on the texture and click "Open with..." and I choose Paint.net.


I suck at texture editing so I wont do anything complicated and I will just paint part of the texture to green.


When you are done editing the texture click on "Save as..." from the File menu and choose "DirectDraw Surface (.dds)" as save type.


A configuration window will popup. Now this part really important. You have to save your dds file depending on the original texture. If the original texture in pak file is compressed as DXT1 you have to save your modified texture as DXT1 so that you can be able to insert it into the pak file again. The good thing is that my program tells you the compression types. When you look at the texture list you will see the compression types next to the texture names like "DXT1", "DXT5" or "Unsupported". In my situation the jacket texture is compressed as DXT1 so at configuration window in Paint.Net I choose DXT1 and click save. You can alter the other settings if you know what you are doing but leaving them at default should be fine. Edit : Make sure generate mipmap is checked.


Now we go back to our TextureEditor program and choose the texture that we want to replace from the list. After that we click the "Replace Texture" button on top menu and a window will pop up that wants us to select our new modified texture. I saved my modified texture as newjacket.dds I choose it and click OK.


The program will replace the old texture with the newone and the preview will be updated.


Only thing you have to do is to put this pak file back into actor34 folder. When you extracted actor34.psarc a folder called "actor34" must be created. Just put your modified pak file back into actor34 folder overwriting the old one. You don't have to compress actor34 folder back into actor34.psarc it will just work fine as a folder. So copy actor34 folder to a hdd or usb and transfer it to your game directory in ps3. You can delete the actor34.psarc in your ps3 because the game can load from actor34 folder.

That is all. You will see your new texture when you open the game. Here is the final product of this tutorial.


I only tested it with Last Of Us but it should also be able to replace textures in other Naughty Dog games like Uncharted. Try it and write what happens in the comments. Also make sure you are editing the right file. For example in Last of Us if you are in winter season and you edit "ellie-jacket-cloth.pak" you won't see your new texture because the jacket texture that is used in winter is "ellie-jacket-cloth-snow.pak". Always read the .pak names and find the right pak file.

I hope this tutorial was good enough for you to understand. I am releasing this software free and don't want any donations. Best thing you can do to support me is to release your own mods . Have fun!
## Post #2
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-07-01T16:56:09+00:00
- Post Title: [Release] Naughty Dog Texture Editor

Hey men this tool its amazing i thik alot of guys could made alot of texture mods.
## Post #3
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2013-07-01T18:21:21+00:00
- Post Title: [Release] Naughty Dog Texture Editor

That is really awesome, great job!
## Post #4
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2013-07-01T20:00:48+00:00
- Post Title: [Release] Naughty Dog Texture Editor

Very cool tool. We could be looking at the start of Naughty Dog games modding.
## Post #5
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2013-07-05T14:45:47+00:00
- Post Title: [Release] Naughty Dog Texture Editor

This tool is very useful, thanks!
## Post #6
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2013-07-16T13:21:31+00:00
- Post Title: [Release] Naughty Dog Texture Editor

This is fantastic! But I'm thinking i'll need to void my ps3 warranty in order to do this. Would be great if we get access to the low poly models. That way we can resculpt high poly meshes for reprojection of normal maps etc.
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-07-27T03:47:44+00:00
- Post Title: [Release] Naughty Dog Texture Editor

great work!
## Post #8
- Username: BigGeyAl76
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 10, 2020 2:36 pm
- Post datetime: 2020-05-10T06:58:19+00:00
- Post Title: [Release] Naughty Dog Texture Editor

This thing has so many fucking trojans
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-10T08:03:29+00:00
- Post Title: [Release] Naughty Dog Texture Editor

> Reply from BigGeyAl76 ↑Sun May 10, 2020 2:58 pm at Sun May 10, 2020 2:58 pm
>
> 
This thing has so many fucking trojans
You just joined the site and all you write is nonsense about viruses. Bad attitude.
## Post #10
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2020-06-11T14:29:25+00:00
- Post Title: [Release] Naughty Dog Texture Editor

Hello! So I want to replace the button textures. (X, Square etc.) So in the pak23.psarc I found the hud.pak. I exported all textures, but for some reason, the circle button is not in there, and that's the only one missing?   Its also not in the list. Does the program somehow stop reading all the texture files from the pak since there are a lot in there? Or are the button textures somewhere else and these are just dummies? I also found them and changed them in main/misc1, but that didn't do anything. Thanks in advance.
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-11T14:40:12+00:00
- Post Title: [Release] Naughty Dog Texture Editor

> Reply from kotn3l ↑Thu Jun 11, 2020 10:29 pm at Thu Jun 11, 2020 10:29 pm
>
> 
Does the program somehow stop reading all the texture files from the pak since there are a lot in there?
There shouldn't be a limitation like this. It should be reading all the textures, unless it is an unsupported format. But it is  probably using the same format as other button textures you found.

I don't know from what file the UI textures are read ingame. If you changed it and it doesn't effect anything, then the game must be loading it from somewhere else.
## Post #12
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2020-06-11T15:09:08+00:00
- Post Title: [Release] Naughty Dog Texture Editor

> Reply from akderebur ↑Thu Jun 11, 2020 10:40 pm at Thu Jun 11, 2020 10:40 pm
>
> 
kotn3l wrote: ↑Thu Jun 11, 2020 10:29 pm
Does the program somehow stop reading all the texture files from the pak since there are a lot in there? 

There shouldn't be a limitation like this. It should be reading all the textures, unless it is an unsupported format. But it is  probably using the same format as other button textures you found.
I don't know from what file the UI textures are read ingame. If you changed it and it doesn't effect anything, then the game must be loading it from somewhere else.

Alright thanks, I'll figure it out. One more question: I don't have to repack the psarc files right? Is it enough to move the modified pak file into its corresponding folder? (for example /main/build/pak23/)
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-11T15:11:18+00:00
- Post Title: [Release] Naughty Dog Texture Editor

Yes, repacking shouldn't be necessary. Make sure to get rid of the original psarc though. i don't know what the game prioritizes when loading assets.
## Post #14
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2020-06-11T15:43:19+00:00
- Post Title: [Release] Naughty Dog Texture Editor

> Reply from akderebur ↑Thu Jun 11, 2020 11:11 pm at Thu Jun 11, 2020 11:11 pm
>
> 
Yes, repacking shouldn't be necessary. Make sure to get rid of the original psarc though. i don't know what the game prioritizes when loading assets.

Thanks. I found out that I probably had to update the files in the patch1.psarc. I did, and moved the original psarc out, and copied in the extracted files with my modified hud.pak as well. The game boots, but it just freezes and never even gets to the game logo.  Should I try repacking it? Also the psarc compression type probably also matters right?

EDIT: repacking also results in the same thing. Maybe I messed up the pak somehow? I saved the textures in DDS and their DXT1 compression with mipmaps.

EDIT: after reopening the modified pak file in misc1, it looks all weird: 


Looks like a mipmap issue. Maybe UI textures don't need mipmaps? Or..?
EDIT once again: I tried with no mipmaps. It looks okay after that, but the game won't start still.

The game engine also returns:
“ERROR: Canceling load of package [~DATABRANCH/misc1/debugrenderingk] - File is closed but more VRAM data is needed - Corrupt pak file? - Clear cache!"

EDIT: with no mipmaps, and repacked properly, it works!


this is on RPCS3 with an Xbox One controller. Cheers!
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-12T07:53:12+00:00
- Post Title: [Release] Naughty Dog Texture Editor

> Reply from kotn3l ↑Thu Jun 11, 2020 11:43 pm at Thu Jun 11, 2020 11:43 pm
>
> 
EDIT: with no mipmaps, and repacked properly, it works!
Nice to see that you got it working. Weird that it required repacking. Might be related to that specific pak or maybe because you are running on emulator. I am pretty sure I haven't repacked anything for model textures at the time.
