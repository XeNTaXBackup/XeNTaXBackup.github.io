## Post #1
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-02-20T02:58:52+00:00
- Post Title: Final Fantasy XI .DAT (PC)

I researched the model file of FFXI for a month. And i found some information about this game.

The model file is very fantastic and beautiful. And i hope with these information, some genius like Chrox,finale00, chrrox, Szkaradek123, Mr Adult or great people can help me make the max script or blender python that supports bone + weight.

Here are some information:

1> The .DAT file contain all information about bone, weight, animation, mesh and texture in "Model ROM folder".And some .DAT file contain information of Effect in "Effect ROM folder". But we only talk about .DAT model file.

2> All animations have their name in .DAT file and they can be read by the hex editor.

3> The .DAT contain "address link" to the Sound effect place of the model, too.

4> This is some tools that can read the mesh + animation:

FFXI Model Viewer English version :  this tool was translated from a FFXI Model Viewer from Japan. It can display all mesh of model + full animation clips. It also has an option to convert .DAT file to .MQO format and we can import .MQO into 3DS Max by MQO Importer Plugin. But the limit is the MQO file (metasequoia) contains only mesh (like .obj file).It required FFXI must be installed but we can cheat it by create the fake path installation because it only reads the ".DAT" model file. 

Atlanta Viewer : this tool is a true viewer. It can view all model + animation + effect with sound + map + field + file folder. It required FFXI must be installed

Virtual Reality Studio : this tool was made by a Japanese company. This tool like a 3D Tool, it can import .DAT file with full bone, weight + animation and we can modify the animation, bone or the mesh and then export back to .DAT file. The limit is it has no option export to popular model file like .FBX or Collada.

FFXI Model Viewer + Atlanta Viewer can be found here: [http://killingifrit.com/forums/topic/14 ... te-291009/](http://killingifrit.com/forums/topic/148935-model-vieweraltana-viewerewh-viewerffxitool-update-291009/)

Virtual Reality Studio can be found here : [http://www.credes.com/us/product/80/download.html](http://www.credes.com/us/product/80/download.html). You can found some tut in this website.

Youtube clip that teach you how to mod the .DAT file by Virtual Studio (3 part) : [http://www.youtube.com/watch?v=YrY6knJB ... re=related](http://www.youtube.com/watch?v=YrY6knJBU-s&feature=related)

And finally, this is some example file. This rar contains Odin, Alexander, Shinryu model, include .dds texture, MQO model file and .DAT file. I also added .MQO plugin for 3DS Max 2010 32 bit

[https://docs.google.com/open?id=0BxmE9E ... EyYzkyMGJl](https://docs.google.com/open?id=0BxmE9EG7QMMRMGI2NjdlODYtNWQ3ZS00MDc5LWJmOTYtZWRjMWEyYzkyMGJl)

Mediafire hates me. Everytime i upload, everytime i fail.

Once again, i hope everyone can help me to create a max script or blender python to import the .DAT file that support bone+ weight . It will be great if it can read the animation, too 

Here are some screenshot to show the quality of FFXI model :







And thank for reading my topic
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T03:17:30+00:00
- Post Title: Final Fantasy XI .DAT (PC)

Oh, looks pretty nice.
I wonder if any of the tools came with source. Or at least, someone released specs.
## Post #3
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-02-20T03:23:30+00:00
- Post Title: Final Fantasy XI .DAT (PC)

@finale Can you check .DAT model format ? I think the .DAT file isn't encrypted.

I tried to contact with the owner of model viewer tool but i cant find any his clue ><
## Post #4
- Username: goder2910
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-20T03:31:46+00:00
- Post Title: Final Fantasy XI .DAT (PC)

they are written in .net so a program like .net reflector can get you the source code almost perfectly intact.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T03:35:07+00:00
- Post Title: Final Fantasy XI .DAT (PC)

Source code would be nice.
Then it would require minimal effort to get to where the author got.

Looked at it. This is that PS2/online game right?
I saw the DDS file and was like "lol 3TXD"

At least, assuming it's a DDS file based on the exported files.

No index buffer, so it's probably just stringing all those vertices together

But I'm not sure how to parse it at first glance. I don't see any offsets and it just looks all random at the top.
## Post #6
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-20T04:07:04+00:00
- Post Title: Final Fantasy XI .DAT (PC)

Looking at the alexander file, the first half contains mostly dds textures - 3TXD.
That narrows it down - LOL
## Post #7
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-02-20T04:18:40+00:00
- Post Title: Final Fantasy XI .DAT (PC)

This game was developed for PS2 first, but later, it was developed for PC. The .DAT file that i got from PC, i think it 's different with PS2. because PS2 encrypted these files.

We can choose the option to export the texture to both .JPG and .BMP instead of .DDS.

So we have a little problem, I will try to use the net reflector to get the source code, hoping i will help you to understand more, finale

And thank for your suggesstion, chrrox.

PS : I tried to use Net reflector but it warning these tools is not kind of .Net module ><. Sad new !
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T04:22:29+00:00
- Post Title: Final Fantasy XI .DAT (PC)

I'm still wondering how I should be parsing those DDS files.
I mean, it looks completely backwards.

> Reply from Ninja
>
> Looking at the alexander file, the first half contains mostly dds textures - 3TXD.
That narrows it down - LOL

The latter half contains a bunch of floats.
Like, huge sections of floats.

So now the only problem is the top lol
## Post #9
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-02-20T06:39:34+00:00
- Post Title: Final Fantasy XI .DAT (PC)

Here are some link that relate to FFXI model viewer and .DAT file

Tutorial Model Viewer : [http://www.ffxionline.com/forums/dat-im ... wbies.html](http://www.ffxionline.com/forums/dat-image-rendering/54670-amaduns-tutorials-updated-dat-editing-newbies.html)

And : [http://ffxidats.caarrie.com/index.php?topic=516.0](http://ffxidats.caarrie.com/index.php?topic=516.0)

And little more information:

> .DAT - The all encompassing Model File. This combines your Model and Textures into a readable file for FFXI. Regardless of formatting of other files, .DAT's are the only compatible file with FFXI and can only be directly changed by VRS. However, by using other programs .DAT files can be broken down into the file types below, making Modding a much more enjoyable experience.
>
> .BMP - A very common Graphic File. It's very easy to edit and save, but has to be converted to .DDS format after being changed to be made useable.
>
> .DDS - This is the Texture file of a Model. It can be changed directly, but lesser editting Apps won't be able to open it. It's usually better just to edit the .BMP and save the .DDS file for .DAT conversion.
>
> .MCD - I'm guessing with this one, since I've yet to see it come into play. I'm pretty sure the .MCD file is what holds the Models Movements, Sounds, and anything else not editable at this time. Just don't delete this file, cause it does something.
>
> .MQO - This is the Model file. It contains the 3D Model as well as Texture Mappings. This is the only thing you will change if you don't plan on recoloring your Model.

There is also a "Alikona's Hex Editing Made Easy guide", but the forum is dead and i cannot find the topic.

@finale Waiting for your good new
## Post #10
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-02-21T04:21:07+00:00
- Post Title: Final Fantasy XI .DAT (PC)

Playing around with Google and i found Model Viewer of Final Fantasy XIV source code.

Maybe someone will need it to compare with Model Viewer of Final Fantasy XI

[https://github.com/nohbdy/ffxivmodelviewer](https://github.com/nohbdy/ffxivmodelviewer)
## Post #11
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-22T22:50:16+00:00
- Post Title: Final Fantasy XI .DAT (PC)

For skipping the start:-

```
token = readbyte
numof = readbyte
addme = 0
if token = 0x87 then addme = 16
length = (numof * 32) + addme - 6

```


The token does look like a bit wise flag, the last section of data follows the same principle but uses 3D and BD.
The source code for XIV suggests it's a bit wise flag as well.
if (token & 0x80 = 1) then addme = 16
## Post #12
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-03-02T04:51:55+00:00
- Post Title: Final Fantasy XI .DAT (PC)

I do not really understand this struct. So hoping someone will get more information with it 

Note : I want to find a tutorial that will teach me how to research 3D Model and writing import script. Everyone can give me a link ?
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-02T05:49:26+00:00
- Post Title: Final Fantasy XI .DAT (PC)

I don't think there are many tutorials. I made an attempt to get some sort of guide to get people started: [http://wiki.xentax.com/index.php/3D_Model_Guide](http://wiki.xentax.com/index.php/3D_Model_Guide)

But I don't know how to "teach" someone how to read a binary file. It's like...how do you teach someone to read a book? Teach them the language? Sure, you pretty much just have to know the following:

-what hex is.
-what the data represents. This means you'll need to know a bunch of 3D concepts, or at least the basics.

If you know how datatypes are represented in hex, then you pretty much just have to go through it and figure out how the data is stored.

Like that struct up there. You read a string that's 4 bytes, then you read two more bytes. Depending on the values of token and numof, you will skip that many bytes.

I guess you can read these and see if you pick anything up

[viewtopic.php?f=29&t=3739](http://forum.xentax.com/viewtopic.php?f=29&t=3739) - figuring out basic 3D model format (shaiya online)
[viewtopic.php?f=29&t=8319](http://forum.xentax.com/viewtopic.php?f=29&t=8319) - exploring 9dragon file format
[viewtopic.php?f=29&t=7760](http://forum.xentax.com/viewtopic.php?f=29&t=7760) - basic import script for noesis (python. C++ is available but no tutorials written)

Obviously, you should be getting yourself a hex editor and some sample files to actually see if you can follow along.
## Post #14
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-03-02T06:03:21+00:00
- Post Title: Final Fantasy XI .DAT (PC)

I have a basic about Struct just a noob. Thank you for your link !

The link "python" is very necessary with me.

I will learn more about Hexing guide. 

Note : I learning Chroxx tutorial (shaiya online), hoping this is a good tutorial for me 

Thank you, finale00
## Post #15
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-03-03T01:37:42+00:00
- Post Title: Final Fantasy XI .DAT (PC)

I checked the plugin for importing FFXI model + animation (two plugins) of Virtual Reality Studio. They are ".dll" file.

I tried PE Explorer to disassembler to read the source code from these .dll, but i dont understand anything.

Someone can help me to read the source code from disassembler of PE Explorer ?
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-03T02:07:23+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

It looks like even if I tried to skip the start, I don't know how many chunks there are.

I would imagine I would have to determine what kind of data I'm going to read in, cause for sure the textures are all over the place.

But anyways I got a copy of the game so I can start with some of the smaller files...

EDIT: Ok, so everything is stored in DAT files. 

Anyways let's just suppose this is a chunk-based format, where it gives the tag along with 4 bytes that identify what kind of information is stored and maybe some counts

The first tag is always followed by 0x 01 01.
There will always be a corresponding "end" chunk somewhere later.

You can see that the texture chunks also some common bytes following it (0x20)

Having this parenthesis matching makes it easier since now you can just do a while loop and build a parse tree from it.

Everything appears to be 16-byte aligned (judging from the pixel data, unless those 00's at the end are common).

There appears to be a chunk size somewhere. For example if you look at shiryu, the "cse0" chunk has token 0x87.
If you look a little further, you'll see 0xD8 or 216. If you look at the size of the entire chunk, it is about that much.

Now look at the "mse0" chunk at offset 0x200. It also has token 0x87, but this time if you look at the chunk size, you see 0x144, or 324.

Again, if you highlight the rest of the bytes until you get to the next chunk ("mse1"), you'll see it is a little more than 324 bytes.
## Post #17
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-03-03T09:40:32+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Thank you, finale00 !

Ah i understand a littte on your words.

Like you said, The .Dat format is "chunk-base format", right ?

And every chunk have its size. The first chunk (cse0) has 216, and futher the next chunk (mse0) has 324.

From here, because all things was stored in .DAT file, so we can split these chunks into piece and some chunk will contain vertex or bones , right ? 

But the thing that i dont understand is all of .DAT file have same structure or just some of DAT file have same structure?
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-03T09:45:31+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

I would imagine all dat files have the same structure.
I looked at a couple that were dealing with things like UI, and they were stored in the same way.

Some dat files even have only 4 bytes: 00 00 00 00

The textures are pretty much the same things. You just have to see what pixel format it uses to calculate the size of the pixel data.
## Post #19
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-07T01:19:05+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

This one's on my todo list already, but it's super-low priority. (well below FF12) I haven't played FFXI in years and have been too lazy to install it again to get at the data as well. I only care for the sake of main-numbered FF series completion in Noesis, because I'm a weirdo like that. I had planned to do it in the form of a native plugin as well...but if you're already working on it in the form of a Python script, I can probably assist if you get really stuck.

On a semi-related note, FF14 should also work in Noesis already. Probably. They may have changed the format since the beta, I never bought the game to test it. I recall chrrox telling me that it does work still. But if they did change it anyway, it's probably a trivial change to make the files load, but I'd have to have some data to see.

Edit: I forgot to mention, also, I came across a PDF at some point which completely detailed this file format and even had animation info. I can't seem to find it now, though. But it's out there somewhere, and should save anyone interested in the format many hours of guessing games. If you do find it, please post it here as well.
## Post #20
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-03-07T04:29:57+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Final Fantasy its the father and mother of the RPG games, i play the first Final Fantasy in 1985 with the Nintendo, I remember Squaresoft made 2 games to nintendo, one its rad racer a very old game of cars and then made this RPG, because the company are broquen the developers put the name of Final Fantasy to the game like the Final Hope for Squaresoft, now its a big company SQUARE-ENIX, i dont like the fusión and i think the RPG of square lost Quality with the fusión, yest that one with 2 red butoms, and then i play all the final fantasy series, i stop in Online Final Fantasy series coz i really dont like the Online series of this.
If Mr. Adults Already can made Noesis the Official Tool to open the models of the FF series this made the NOESIS a epic tool.
## Post #21
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-03-07T10:32:50+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

@Mr.Adult It 's hard to find .DAT file structure like you said. I tried to search around the internet 2 month ago but all the link related to FFXI was died. Maybe someone know Japan Language can help us to find .DAT structure in Japanese forum.
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-10T06:18:00+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Unrelated, but I decided to continue with my MQO plugin for noesis and was testing it on the MQO exports provided.

And here's odin!



Don't tell me they only store half of the model?
Or maybe the export dev decided to store only half the vertices to make it easier for the 3D tool.

And here's half a shiryu...
## Post #23
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-10T15:05:07+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

I think I read somewhere that final fantasy, especially on game consoles where optimized in this way, just storing half models etc. I think I read it connected to ffx on ps2
## Post #24
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-11T00:53:19+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Nope, FFX didn't use any kind of mirroring. FFXII might, though.
## Post #25
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-11T04:41:36+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

The mirror flag is quite obvious in the Alexander model because there is one object in the model that isn't mirrored.
How the hell do you skin it?
## Post #26
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-11T17:00:27+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Oh, ya, the towers at the top aren't mirrored lol.

So you've found the flag?
## Post #27
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-11T17:36:18+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Yeah, sticks out like a sore thumb.
Headers for the objects in 47.dat (alexander)

```
00339044 00000200 61360000 1407753D 0000C82D 3D6B0000 00000000 00003D6B 00000000 00000000 .. .a6..  u=.. -=k........=k........
00339080 00000000 00000000 10808080 80800000 80450000 803F0000 00000000 803F0000 00000000 ........      .. E.. ?...... ?......
00339116 00000000 00008045 00000000 00430000 00000080 74696D20 20202020 616C7865 3031     ...... E.....C..... tim     alxe01  

00393936 68685F61 2A130400 00000000 00000000 01000000 01002000 0000D21F F21F0000 13000520 hh_a*  ......... ... . ...    .. .  
00393972 00000200 07200000 B404BB24 0000681C 23410000 00000000 00002341 00000000 00000000 .. .  ..   $..h #A........#A........
00394008 00000000 00000000 10808080 80800000 80450000 803F0000 00000000 803F0000 00000000 ........      .. E.. ?...... ?......
00394044 00000000 00008045 00000000 00430000 00000080 74696D20 20202020 616C7865 3031     ...... E.....C..... tim     alxe01  

00427312 68665F70 AAA40400 00000000 00000000 01008000 00002000 00004226 62260000 09006B26 hf_p   ......... . ... ...B&b&.. .k&
00427348 00000200 6D260000 1E058B2B 0000B41E 3F4A0000 00000000 00003F4A 00000000 00000000 .. .m&..   +..  ?J........?J........
00427384 00000000 00000000 10808080 80800000 80450000 803F0000 00000000 803F0000 00000000 ........      .. E.. ?...... ?......
00427420 00000000 00008045 00000000 00430000 00000080 74696D20 20202020 616C7865 3031     ...... E.....C..... tim     alxe01 

00465344 68685F68 AAD30100 00000000 00000000 01008000 01002000 0000F50F 15100000 02001710 hh_h   ......... . . . ...    .. .  
00465380 00000200 19100000 D001E911 0000400B 291D0000 00000000 0000291D 00000000 00000000 .. .  ..    ..@ ) ........) ........
00465416 00000000 00000000 10808080 80800000 80450000 803F0000 00000000 803F0000 00000000 ........      .. E.. ?...... ?......
00465452 00000000 00008045 00000000 00430000 00000080 74696D20 20202020 616C7865 3035     ...... E.....C..... tim     alxe05  

00480304 68685F74 2A1C0800 00000000 00000000 01000000 01002000 00007C43 9C430000 1100AD43 hh_t*  ......... ... . ...|C C.. . C
00480340 00000200 AF430000 DC088B4C 00002835 B3810000 00000000 0000B381 00000000 00000000 .. . C..   L..(5  ........  ........
00480376 00000000 00000000 10808080 80800000 80450000 803F0000 00000000 803F0000 00000000 ........      .. E.. ?...... ?......
00480412 00000000 00008045 00000000 00430000 00000080 74696D20 20202020 616C7865 3031     ...... E.....C..... tim     alxe01  
```


byte 21 in the object header, if you can't see it. (don't include the offsets in the count)
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-11T18:05:06+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Hmm, so we have a bunch of entries at the top (maybe stuff like bones?), followed by a bunch of textures, followed by vertices, and then followed by faces (which contains mat name as a string, vert indices as shorts, and the UV's as 6 floats)

Another per-face format great...I can see why converting this to MQO was a natural choice just because when I'm looking at it all that comes to mind is MQO MQO MQO MQO MQO MQO
## Post #29
- Username: paulgswanson
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 05, 2011 4:00 am
- Post datetime: 2014-04-08T20:37:22+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Sorry to necro this, but has anyone come up with a final solution for this? Sadly i can't read or do code, but using all the apps provided like FFXItools, Metasequia, and ModelViewer I can get the model and texture but none of the animations. And really all I wanted was the animations for retargeting.  anyone have a already coded solution for this?
## Post #30
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2014-04-09T05:51:56+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> Reply from paulgswanson
>
> Sorry to necro this, but has anyone come up with a final solution for this? Sadly i can't read or do code, but using all the apps provided like FFXItools, Metasequia, and ModelViewer I can get the model and texture but none of the animations. And really all I wanted was the animations for retargeting.  anyone have a already coded solution for this?

read this maybe help you.
[http://gameresearch.haotui.com/thread-343-1-3.html](http://gameresearch.haotui.com/thread-343-1-3.html)
My friends and I researched this game, but the animation is not complete.
## Post #31
- Username: paulgswanson
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 05, 2011 4:00 am
- Post datetime: 2014-04-09T14:11:22+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Thanks for the link. there was quite a bit of helpful info in there, Google translate makes my head hurt though. I'm assuming those scripts only worked on character models with skeletons? The translation chrome gave me was....difficult.
## Post #32
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-07-03T10:56:07+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> Reply from paulgswanson
>
> Thanks for the link. there was quite a bit of helpful info in there, Google translate makes my head hurt though. I'm assuming those scripts only worked on character models with skeletons? The translation chrome gave me was....difficult.
Lucky you, I can't even get the page to load.

Any chance you have the scripts and would be willing to upload them?
## Post #33
- Username: Humm08
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 24, 2014 3:23 pm
- Post datetime: 2014-10-17T18:10:33+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Was the source for Altana View ever posted anywhere?
## Post #34
- Username: alloy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 14, 2014 4:30 pm
- Post datetime: 2014-10-21T03:24:20+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Back like in 2007 ffxitool had its source code up somewhere on the japanese net. 
Maybe it still is if you know japanese google-fu

[http://cosmosa.jp/ffxitool/](http://cosmosa.jp/ffxitool/)

Just a bunch on tools that can play music load models, levels and all kinds of data for ffxi. 

The guy who wrote Altana had access to the ffxitool source. His prog is just a lot more polished.  

But this is were it all ffxi data ripping started. 

Also the ffxi tool page i posted up there has some links to what seems to be info on data structure and whatnot.

And you can find a link to dl the actual programs on the page i linked up there

[http://cosmosa.jp/ffxitool/kaimemo.html](http://cosmosa.jp/ffxitool/kaimemo.html)
[http://cosmosa.jp/ffxitool/generator.html](http://cosmosa.jp/ffxitool/generator.html)
[http://cosmosa.jp/ffxitool/note.html](http://cosmosa.jp/ffxitool/note.html)

Hope anyone here can make any sense or if its even useful to you guys. 

And also theres a page dedicated to what i guess is his tool version for ff14

[http://cosmosa.jp/ffxivtool/](http://cosmosa.jp/ffxivtool/)

I have no idea what it does because i don't have that game and i literally just found out about it lol.
## Post #35
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-10T20:15:20+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

I ended up re-reversing this damn thing. It'll be in the Noesis release I'm planning to put up in a few minutes.

 
 

Animation and maps and everything are supported. Still haven't totally figured out how blending is specified for certain map objects, so some stuff may or may not be blended when it shouldn't or should be. But I did figure out terrain blending, so that's nice. I came across a code snippet for MZB/MMB "decryption" after extensive Japanese Googling, which I'm pretty sure was written by the author of ffxitools, but am not sure. But, thanks to that guy for being able to load the encrypted maps, I guess.

Character sets are also supported, via a new format called "ff11datset". An example sample_hume01.ff11datset will be included in the Noesis scenes directory. It works like this:

```
;^ must be the first line of the file

;search for dats using a path retrieved from a registry key
setPathKey	"HKEY_LOCAL_MACHINE" "SOFTWARE\PlayOnlineUS\InstallFolder" "0001"

;search for dats on a path relative to this file 
;setPathRel	"./"

;search for dats on an absolute path
;setPathAbs	"c:/whatever/ff11/"

dat			"__skeleton"	"ROM/27/82.dat"
dat			"__animation"	"ROM/27/82.dat"
dat			"face"			"ROM/27/87.dat"
dat			"head"			"ROM/27/103.dat"
dat			"body"			"ROM/28/7.dat"
dat			"hands"			"ROM/28/52.dat"
dat			"waist"			"ROM/28/84.dat"
dat			"legs"			"ROM/28/116.dat"
dat			"weapon"		"ROM/29/20.dat"

```

I'll probably put together a little Python script at some point that just tosses up a GUI to let you scroll through body parts and just generates+loads these files as you scroll through.
## Post #36
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-10T22:40:16+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Here's the source:

[http://www.richwhitehouse.com/index.php ... t=Snippets](http://www.richwhitehouse.com/index.php?content=inc_res.php&rescat=Snippets)

Try not to pretend you wrote it. Unbelievable how many people I came across showing viewers they "wrote" and refusing to send them to people, when clearly all they did was find an old source distribution of ffxitools. Probably some interesting behavioral statistics to be collected there.
## Post #37
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-10-13T23:49:10+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Here is my maxscript to load hi-poly character model in charcter creation.
It still doen't support skeleton /animation.
I'm not good at matrix calculation.I've discussed it with fatduck in his dead forum before,still not finished yet.
MrAdult,hope you can add them into noesis too.Tyvm for doing this project.

```
--heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents"Runtime Error: Out of scripter memory"
fname = getOpenFileName \ 
caption:"FFXI Model File" \
types:" FFXI Character Model File(*.dat)|*.dat|All files (*.*)|*.*|" \

clearlistener()
f = fopen fname "rb"


------------------------------------------Function Define Start
-------------------------------------------------------------------------------------
fn ReadFixedString bstream fixedLen =
(
   local str = ""
   for i = 1 to fixedLen do
   (
      str += bit.intAsChar (ReadByte bstream #unsigned)
   )
   str
)

-------------------------------------------------------------------------------------
------------------------------------------Function Define End
global Meshpointer_array = #()
global Bonepointer_array = #()
global Skinpointer_array  = #()
f_size = getFileSize fname
print "File size"
print f_size
f_lines = (f_size / 16)  as integer
fseek f 0 #seek_set
for i = 1 to (f_lines-1) do (
	pointer_pos = (ftell f) as integer
	magic_string1 = readlong f #unsigned
	fseek f 6 #seek_cur
	magic_num = readshort f #unsigned
	fseek f 4 #seek_cur
	if  magic_string1 == 1162629459 do( ------check if "SQLE"
		
		if magic_num == 10 do( -----check if mesh
			append Meshpointer_array [pointer_pos,0]
		)	----if magic_num = 10
		
		if magic_num == 11 do( --------check if skeleton
			append Bonepointer_array [pointer_pos,0]
		)----	if magic_num == 11
		
		if magic_num == 21 do( ------check if skin
			append Skinpointer_array [pointer_pos,0]
		) -----	if magic_num == 21				
	)----if  magic_string1 == 1162629459
)----or i = 1 to f_lines 
fseek f 0 #seek_set


for i = 1 to (Meshpointer_array.count) do (
  global Vert_array = #()
  global Normal_array = #()
  global UV_array = #()
  global Face_array=#()  
  global facechunk_array =#()
    
  mesh_start = Meshpointer_array [i][1] as integer
	
  fseek f mesh_start #seek_set------------------offset to chunk starting position

  fseek f 96 #seek_cur----------------------------where start to read mesh

  vtcount = readlong f #unsigned
  fseek f 12 #seek_cur
  print "vertice count check"
  print vtcount

    for j=1 to vtcount do( ----read vert
        vx = readfloat f
        vy = readfloat f
        vz = readfloat f
       append Vert_array [vx,vy,vz]	   
	)	----for j=1 to vtcount
	
   fseek f 8 #seek_cur	

	
	 for j=1 to vtcount do( ----read normal
        nx = readfloat f
        ny = readfloat f
        nz = readfloat f
	   append Normal_array[nx,ny,nz]
	 )--for j=1 to vtcount
	 
  fseek f 8 #seek_cur	 
    for j = 1 to vtcount do ( ----readUV
	     Uvx= ( ( readfloat f ) * -1 ) + 1
	     Uvy= readfloat f
	     --Uvy -= 1
	     append UV_array[Uvx,Uvy,0]
	)----j = 1 to vtcount

   code_count = readlong f #unsigned--------------------------------------face index start
   section_count = readlong f #unsigned
	
    for j = 1 to section_count do(
	    fid_pos = ftell f
	    fid_count = readshort f #signed
			
	     if fid_count < 0 do  (   ---------------------------- tri-strip
	      fid_num = fid_count * -1
	      fseek f 2 #seek_cur----skip 3 bytes of 0xff
		  backface=1 
		  global fid_array =#()
			 
			 for k = 1 to fid_num do (
				 fid = ( readlong f #unsigned )+ 1
				 append fid_array[fid,0]				 
			 )----for k = 1 to fid_num
			 
			 for k = 1 to (fid_num - 2) do(
				 f1 = fid_array[k][1]
				 f2 = fid_array[k+1][1]
				 f3 = fid_array[k+2][1]
				 backface=backface*-1
				   				   
                   if f1!=f2 and f1!=f3 and f2!=f3 then(
					   
                        if (backface==1) then (   
                           append Face_array [f1,f2,f3]
                        )    
    
                        if (backface==-1) then (
                           append Face_array [f1,f3,f2]
                        )						
                    )	----if f1!=f2 and f1!=f3 and f2!=f3
			 )----	 for k = 1 to (fid_num - 2)
	     )----if fid_count < 0 
		
	if fid_count > 0 do ( ---------------------------------------------trilist array
	  fseek f fid_pos #seek_set
	  print "Trilist array found ! position check!"
	  print fid_pos
		
	  fid_count = readshort f #signed
	    if fid_count < 0 do(
			
	      fid_num = fid_count * -1	
	    )----if fid_count < 0
	  
       fseek f 2 #seek_cur----skip 2 bytes of 0xff	
	  fid_num = fid_count
		print fid_num
	   for k = 1 to (fid_num / 3) do (
		   f1 = (readlong f #unsigned ) + 1
		   f2 = (readlong f #unsigned )+ 1
		   f3 = (readlong f #unsigned )+ 1
		   append Face_array [f1,f2,f3]
		   		   
	   )---- for k = 1 to (fid_count / 3)
	   
	   ) ----if fid_count>0 
    )----	 for j = 1 to section_count

  -------------------------------------------------------------------------------------build mesh
  -----------------------------------------------------------------------------------
  msh = mesh vertices:Vert_array faces:Face_array
  msh.numTVerts = UV_array.count
  buildTVFaces msh
    for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
    for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
    for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
  --msh.name = chunk_name
  
)----for i = 1 to (Meshpointer_array.count)




gc()
fflush f
fclose f

```


And here is the data list you can find those hi-poly models/animations.
[Hi-mesh_list.7z](https://xentaxbackup.github.io/file/9853_Hi-mesh_list.7z)
## Post #38
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-14T00:59:46+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Huh? Noesis already supports all of the character parts, and piecing them together as mentioned above. And animations. And levels.
## Post #39
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-10-14T01:12:07+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> Reply from MrAdults
>
> Huh? Noesis already supports all of the character parts, and piecing them together as mentioned above. And animations. And levels.

The character creation has high poly models different with normal in game models.Check those files in the data list i added please:)
## Post #40
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-14T01:20:35+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Seems your list is wrong for the US/NA release (or maybe just wrong), then. For example 63/104 isn't mesh data. You should refer to them by file ID's from the tables instead of the .dat names to be consistent.
## Post #41
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-10-14T02:13:49+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> Reply from MrAdults
>
> Seems your list is wrong for the US/NA release (or maybe just wrong), then. For example 63/104 isn't mesh data. You should refer to them by file ID's from the tables instead of the .dat names to be consistent.

ya,,some of the data in the list is wrong,,but their number is close
63/104 is texture
try 63/103 with my script
## Post #42
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-14T02:45:41+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

I figured that other animation format out, but it's pretty awful and worse than the in-game one. Not sure why it exists.

I might add support to Noesis at some point, but I don't see much point, cause it's self-evident and has nothing in common with the main .dats. Maybe I'll just do it in an external script.
## Post #43
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-10-17T04:56:49+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> Reply from MrAdults
>
> I figured that other animation format out, but it's pretty awful and worse than the in-game one. Not sure why it exists.

I might add support to Noesis at some point, but I don't see much point, cause it's self-evident and has nothing in common with the main .dats. Maybe I'll just do it in an external script.

I'm guessing that's was done by 2 different teams.1st team design the high poly models,2nd team use those models to design in game low-poly count models with optimized animation format.Because this game was designed to be working on very old ps2 with very limited ram size 10 years ago.
I viewed some maps from rom1 folder and found some blending issue you mentioned.Some trees leaves still lacking of correct alpha channel.And lacking of water materials.
Here is the actual in game video of those map area.Hope it will help your coding,Regards:)
[https://www.youtube.com/watch?v=kzrmwcSizIY](https://www.youtube.com/watch?v=kzrmwcSizIY)
## Post #44
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-17T05:33:48+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

I meant, the format itself is worse. It's bigger and offers worse compression quality for pbchannel or limited functionality for framechannel. Considering the other format had to have existed prior to ship, there's no reason for this format to exist in tandem, even if the content pipeline was entirely different.
## Post #45
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2015-10-21T07:55:46+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Oh shit, did it finally happen? Can I finally get the models out with weights and animations?

Always wanted to do stuff with FFXI's models but my lack of rigging expertise limited me.
## Post #46
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-21T10:12:41+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

I've got the rest of the map format charted out as well, with collision and quadtree data, and I've been sitting on these finished "SQLE" models with both of their animation formats and materials supported. I'll probably put up a new build with all of that on the weekend.

Still no idea how blending is specified for the prop-level map objects, despite having accounted for damn near every bit in the map and map geo chunks. I'm thinking there's some external object material database somewhere at this point. Also, regarding the missing sky/moon/water/etc., those objects are generated and driven by the server. There's already an option called -ff11renderunref in the current build, it will shit them all out at identity. You have to figure out how to pull them apart and place them yourself if you want to do something with them. You'll want to use -ff11keepnames with that, unless you want a big terrible inseparable triangle mess. -ff11optimizegeo is probably a good idea too, it will collapse redundancies and remove strip degenerates.
## Post #47
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2015-10-22T08:56:27+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

So all the lootables, interactable objects and skybox stuff gets shat out into the map origin if you run those arguments I'm guessing?
## Post #48
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-22T17:02:20+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

I imagine there are plenty of objects that are totally precached and instanced via the server, but yeah, everything explicitly embedded in the file that doesn't have a static object reference will get placed at identity.
## Post #49
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-25T05:04:14+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> -4.168 - Added a new -ff11blendhack option. This uses the Noesis software renderer to render all FF11 map geometry triangles in UV space, and determine how many of each mesh's triangles are only touching zero-alpha pixels in the texture. -ff11blendhack 0.99 is typically a good value to use. This completely demented solution is not foolproof, but catches the vast majority of broken blending cases.
>
>  -4.168 - Added support for FF11 SQLE models, including both types of animation.
Don't hurt yourself spanking it, you sick furry bastards. I'm sticking a fork in this now, so if you want anything else fixed/added, you're on your own.

To piece the SQLE models together, you can put a .noesis file in your FFXI directory root (above the ROM directories), like the sample_elf01ff11.noesis file included in the latest build. It looks like this:

```
version 1
physicslib		""
defaultAxis		"0"

object
{
	name			"body"
	model			"ROM/63/1.dat"
	loadOptions		"-ff11sqleanim ../64/40.dat"
}
object
{
	name			"head"
	model			"ROM/63/5.dat"
	loadOptions		"-ff11sqleanim ../64/46.dat"
	;this uses the relative positions of the neck joints on each skeleton to place the head
	offsetWithBones	"bone0001" "body" "bone0004"
	;combine both objects into a single model
	mergeTo			"body"
}
```

Modifying for other body/head/animation combinations should be pretty obvious. The bones for the head snapping may change, so figure out which ones you should be using by looking at the models in the Noesis data viewer.
## Post #50
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2015-10-26T05:24:25+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Do you still plan on writing a small gui to make loading player model stuff into Noesis easier? Something like what AltanaView offers?
## Post #51
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-10-27T05:44:09+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

It's possible that will strike my fancy at some point, but if not, anyone can handle doing it. See tool_windowtest.txt included with Noesis for an example of how to do custom GUI popups. Just use that, write out a .ff11datset text file and have Noesis auto-load it with noesis.openFile whenever you receive a control-changed message. I'd probably just use a scrollbar for each part and reload on the scroll changed message.
## Post #52
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2015-12-01T19:34:23+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

I know its a tall order, and I am certainly appreciative of import as it stands, but would it be possible to get an export function?

I realize exporting is sort of a hairier beast.
And you probably don't care. But if I don't ask the answer is a definite no. If I do, there's a 1% chance of yes.
Well I guess that counts as 'added or changed' so that's out I guess.

I glanced at the source you posted, but it seems like its referencing some files that aren't listed on the resource page, like model_ff11_decrypt.h

I also noticed a number of noe and rapi functions in it... if I were to try porting it to blender's python, would I need to know how those functions work, or are they only required to send the data to noesis? (Not sure if that's a clear question)
## Post #53
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-12-03T01:39:18+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Probably won't do an exporter until the day comes that there's nothing left to do in life but write exporters for FF games, and I expect to die of cancer or heart failure before then. But, it's possible I'll get to that point, somehow. (but 7, 8, 9, 10, 12, and 13 would come first)

The decryption routines by the guy that wrote ffxitool are in that header, which I didn't reverse myself. I'm not going to provide them publicly, as he could do that himself if he wanted to. If he's still alive. I don't know what his motivation was in ceasing source distribution. Maybe it was because people are turds.

I would encourage you to point people toward Noesis instead of just porting all of the code into a blender importer if that is your aim. Having users is nice and helps bring in new and interesting reports for one-off issues/crashes/etc. Which are provided to me automatically in the case of detectable problems, which is how I know hundreds of thankless bastards are using Noesis on a daily basis despite the complete lack of meaningful feedback outside of when they want a new stupid feature/game. That said, yeah, you need to figure out the purpose of the RAPI functions if you want to port it. Lucky for you, the RAPI uses in that module are pretty obvious.
## Post #54
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2015-12-03T07:11:12+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> Reply from MrAdults
>
> Probably won't do an exporter until the day comes that there's nothing left to do in life but write exporters for FF games, and I expect to die of cancer or heart failure before then. But, it's possible I'll get to that point, somehow. (but 7, 8, 9, 10, 12, and 13 would come first)

The decryption routines by the guy that wrote ffxitool are in that header, which I didn't reverse myself. I'm not going to provide them publicly, as he could do that himself if he wanted to. If he's still alive. I don't know what his motivation was in ceasing source distribution. Maybe it was because people are turds.

I would encourage you to point people toward Noesis instead of just porting all of the code into a blender importer if that is your aim. Having users is nice and helps bring in new and interesting reports for one-off issues/crashes/etc. Which are provided to me automatically in the case of detectable problems, which is how I know hundreds of thankless bastards are using Noesis on a daily basis despite the complete lack of meaningful feedback outside of when they want a new stupid feature/game. That said, yeah, you need to figure out the purpose of the RAPI functions if you want to port it. Lucky for you, the RAPI uses in that module are pretty obvious.

I was only trying to port it so there wouldn't be any intermediary format swapping... I was also going to try handling the exporting. (It is still an active game and there are model mods...my main reasons)

Intermediary formats generally lead to lossy conversions. However, after spending several hours remembering I don't actually understand C++ despite it looking relatively simple on the surface, I've decided against trying to straight port the code.

I do regularly try to push people toward Noesis for model viewing though. I love Noesis. Its probably in my top 5 most used programs. 
...
I'm also somewhat guilty of sending useless crash reports... >.> Then again, I stopped doing that when I realized it was basically my own fault most of the time. My method of scripting involves a lot of hammers and screws.
## Post #55
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-12-03T08:02:57+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

I see. The character geo + anim data will be pretty much lossless in terms of data storage if you use FBX, but what your FBX importer does on the other side could change that. The mirroring data can be recalculated from the unmirrored data, which a good exporter would want to do anyway to support new geometry from targets that don't support mirroring. You could also just be lazy and not support mirroring and set everything unmirrored, although you would probably not want to do this under the assumption that most people will be wanting to just import new geometry while keeping the mirrored skeleton + anims intact. The animation keyframes can also be recalculated, as the keyframes themselves are preserved as FBX keyframes and we can eliminate all of the unnecessary ones again by checking the error for spherical/linear interpolation at a given point on the animation curve. In these cases, I also typically expose an optional error threshold, so that the export target can enjoy a greater level optimization if the user wants at typically no discernible visual penalty. There's an option for this already rolled into the FBX exporter. In this case, there could potentially be some FP32 precision loss from transforming between matrices with baked scale and T+Q+S, but it's likely to be imperceptible.

Levels on the other hand, it's baking all the instanced geo out and transforming the actual verts, so you wouldn't be able to restore that trivially. The importer could be modified to preserve instances and transforms, but I doubt you were aiming to make a level exporter, as you'd run into a whole lot more trouble there than just instance preservation.

Well, thanks for supporting Noesis. I don't look at any crash report as useless unless it's someone writing a native plugin and causing a crash by feeding bad data into the API or crashing in the plugin itself, or it's someone using an old version of Noesis and the crash is already fixed in newer versions. The Python implementation should, in pure idealism, always protect the user from crashes even when they're doing awful things. Although achieving this in practice is often not worth it, depending on the complexity and overhead of that validation phase. I like to see the instances where this happens either way, though, so I can evaluate what might be done to highlight the bad usage with Python exceptions. I'm typically working with nothing but some thread contexts in a crash report, though, so if you find a case where you find the issue and you think "it shouldn't have been a big deal for Noesis to catch that and tell me about it", you can help a lot and save me some time by sending me your broken script and some data to reproduce the crash.

I looked into the state of FF11 a little when I was doing this format, and was somewhat surprised to see so many people still playing or going back to it, and horrified by the associated furry community as usual. I played it for a few months not long after its release in 2002 or 2003. After getting to around level 50 as a dark knight, I deleted my account and character upon realizing how much of my life I'd just wasted playing what is objectively a pretty awful game. Yet despite knowing it's an objectively awful game and not finding anything about the story particularly engaging, I still felt some strange underlying desire to go back to it, kind of like an abused spouse. If I were jobless, had no family, and in a state of helpless depression, it might've gotten me. Not this time, though, FF11. Not this time.
## Post #56
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2015-12-05T04:05:43+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> Reply from MrAdults
>
>  If I were jobless, had no family, and in a state of helpless depression, it might've gotten me. Not this time, though, FF11. Not this time.

Ha! I tried, but just couldn't get into it.
## Post #57
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2016-01-11T01:07:08+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

hm... I just now noticed that the animation reading is bugged. Only half the body's animation actually gets loaded for most of the animations. I'm not sure where to start with trying to get around that problem.
For an example, anyone can take a look at ROM/51/89.dat and see that the legs move for most of them, while the torso stays stark still...

EDIT: oh I see... they're separated into different animations, upper and lower... and they don't all seem to have equal parts for both... but its a lot more obvious when viewing them one animation at a time through the data viewer.
## Post #58
- Username: Maphesdus
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 12, 2016 3:53 am
- Post datetime: 2016-01-11T20:01:04+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Hey, I'm having a bit of an issue here. Whenever I try to export an FFXI model using Noesis and then import that model into another program (such as 3Ds Max or Unity), the model imports upside down. Am I doing something wrong, or is this a bug in Noesis?

Also, how do I view the models of player characters, considering they're an amalgamation of multiple files?
## Post #59
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2016-01-11T20:29:27+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> Reply from MrAdults
>
> [...]

Character sets are also supported, via a new format called "ff11datset". An example sample_hume01.ff11datset will be included in the Noesis scenes directory. It works like this:
Code: Select allNOESIS_FF11_DAT_SET
;^ must be the first line of the file

;search for dats using a path retrieved from a registry key
setPathKey	"HKEY_LOCAL_MACHINE" "SOFTWARE\PlayOnlineUS\InstallFolder" "0001"

;search for dats on a path relative to this file 
;setPathRel	"./"

;search for dats on an absolute path
;setPathAbs	"c:/whatever/ff11/"

dat			"__skeleton"	"ROM/27/82.dat"
dat			"__animation"	"ROM/27/82.dat"
dat			"face"			"ROM/27/87.dat"
dat			"head"			"ROM/27/103.dat"
dat			"body"			"ROM/28/7.dat"
dat			"hands"			"ROM/28/52.dat"
dat			"waist"			"ROM/28/84.dat"
dat			"legs"			"ROM/28/116.dat"
dat			"weapon"		"ROM/29/20.dat"

That's how.
I find its helpful to have Model Viewer or Altanaview open to find the dat numbers (they're displayed at the bottom of either program when they're loaded from the drop list)

As for loading upside down.... no that's not a bug.
It's due to the fact that all 3D programs consider "up" to be a different direction chosen by whomever wrote said program. 
It would be nice if you could specify a global Noesis 'up' axis, butas of right now I don't think there is one. There may be an advanced option to export with a custom rotation in the export options... but I'm not sure.

In any case it shouldn't be that hard to fix it on import... most importers have an option to specify an Up axis simply because not all formats and programs use the same one.

And back on my previous post I did notice that one upper body animation is missing, when it should be present. I'll have to look through the source again to see if there's any loop -1 errors or such... god I hate debugging C++
## Post #60
- Username: Dufus
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-01-13T01:46:43+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

There is a way to specify "up" in Noesis, that's why the models appear oriented correctly in Noesis. Noesis doesn't rotate the geometry itself, it changes what's considered "up" in the scene. This is The Right Thing To Do.

Most formats on the other hand don't support arbitrary scene orientations. The FBX exporter supports z-up using -fbxzup if you happen to be exporting from a format that uses this convention, or you can rotate the actual geometry using -rotate # # # where # # # are pitch, yaw, and roll. Or you can take the raw unrotated data into your modeler of choice and specify a correct "up" axis, if your modeler of choice allows. Most programs suck in this regard or only allow y-up/z-up.
## Post #61
- Username: Maphesdus
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 12, 2016 3:53 am
- Post datetime: 2016-01-16T05:47:03+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

Okay, thanks. Sorry for my noobish questions, I'm just new to this whole thing.

Is there a way to export the animations for the spell effects? Cuz' as far as I can tell Noesis only loads the textures for spells, and not the actual spell animations.

By the way, MrAdults is Rich Whitehouse, I assume?
## Post #62
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-16T10:44:32+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

> Reply from Maphesdus
>
> By the way, MrAdults is Rich Whitehouse, I assume?yep. Aliases of the "god of 3D model format analysing".

He's the One who's giving us the rules:

> Reply from MrAdults
>
> There is a way to specify "up" in Noesis, that's why the models appear oriented correctly in Noesis. Noesis doesn't rotate the geometry itself, it changes what's considered "up" in the scene. This is The Right Thing To Do.
## Post #63
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-03-08T12:17:28+00:00
- Post Title: Re: Final Fantasy XI .DAT (PC)

hello,long time..not sure if anyone still digging this game.
About map/terrain data..it's encrypted.inside the mmb,mzb block.
Someone sent me the information how to decrypt it.
I only knew how to IO basic 3d models..so that information didn't help me much.
I decide to left the information here.
For some kind people wanna make blender/3dsmax script to import/export terrain/maps.

```
{
    0xE2, 0xE5, 0x06, 0xA9, 0xED, 0x26, 0xF4, 0x42, 0x15, 0xF4, 0x81, 0x7F, 0xDE, 0x9A, 0xDE, 0xD0,
    0x1A, 0x98, 0x20, 0x91, 0x39, 0x49, 0x48, 0xA4, 0x0A, 0x9F, 0x40, 0x69, 0xEC, 0xBD, 0x81, 0x81,
    0x8D, 0xAD, 0x10, 0xB8, 0xC1, 0x88, 0x15, 0x05, 0x11, 0xB1, 0xAA, 0xF0, 0x0F, 0x1E, 0x34, 0xE6,
    0x81, 0xAA, 0xCD, 0xAC, 0x02, 0x84, 0x33, 0x0A, 0x19, 0x38, 0x9E, 0xE6, 0x73, 0x4A, 0x11, 0x5D,
    0xBF, 0x85, 0x77, 0x08, 0xCD, 0xD9, 0x96, 0x0D, 0x79, 0x78, 0xCC, 0x35, 0x06, 0x8E, 0xF9, 0xFE,
    0x66, 0xB9, 0x21, 0x03, 0x20, 0x29, 0x1E, 0x27, 0xCA, 0x86, 0x82, 0xE6, 0x45, 0x07, 0xDD, 0xA9,
    0xB6, 0xD5, 0xA2, 0x03, 0xEC, 0xAD, 0x62, 0x45, 0x2D, 0xCE, 0x79, 0xBD, 0x8F, 0x2D, 0x10, 0x18,
    0xE6, 0x0A, 0x6F, 0xAA, 0x6F, 0x46, 0x84, 0x32, 0x9F, 0x29, 0x2C, 0xC2, 0xF0, 0xEB, 0x18, 0x6F,
    0xF2, 0x3A, 0xDC, 0xEA, 0x7B, 0x0C, 0x81, 0x2D, 0xCC, 0xEB, 0xA1, 0x51, 0x77, 0x2C, 0xFB, 0x49,
    0xE8, 0x90, 0xF7, 0x90, 0xCE, 0x5C, 0x01, 0xF3, 0x5C, 0xF4, 0x41, 0xAB, 0x04, 0xE7, 0x16, 0xCC,
    0x3A, 0x05, 0x54, 0x55, 0xDC, 0xED, 0xA4, 0xD6, 0xBF, 0x3F, 0x9E, 0x08, 0x93, 0xB5, 0x63, 0x38,
    0x90, 0xF7, 0x5A, 0xF0, 0xA2, 0x5F, 0x56, 0xC8, 0x08, 0x70, 0xCB, 0x24, 0x16, 0xDD, 0xD2, 0x74,
    0x95, 0x3A, 0x1A, 0x2A, 0x74, 0xC4, 0x9D, 0xEB, 0xAF, 0x69, 0xAA, 0x51, 0x39, 0x65, 0x94, 0xA2,
    0x4B, 0x1F, 0x1A, 0x60, 0x52, 0x39, 0xE8, 0x23, 0xEE, 0x58, 0x39, 0x06, 0x3D, 0x22, 0x6A, 0x2D,
    0xD2, 0x91, 0x25, 0xA5, 0x2E, 0x71, 0x62, 0xA5, 0x0B, 0xC1, 0xE5, 0x6E, 0x43, 0x49, 0x7C, 0x58,
    0x46, 0x19, 0x9F, 0x45, 0x49, 0xC6, 0x40, 0x09, 0xA2, 0x99, 0x5B, 0x7B, 0x98, 0x7F, 0xA0, 0xD0,
};

static BYTE key_table2[0x100] =
{
    0xB8, 0xC5, 0xF7, 0x84, 0xE4, 0x5A, 0x23, 0x7B, 0xC8, 0x90, 0x1D, 0xF6, 0x5D, 0x09, 0x51, 0xC1,
    0x07, 0x24, 0xEF, 0x5B, 0x1D, 0x73, 0x90, 0x08, 0xA5, 0x70, 0x1C, 0x22, 0x5F, 0x6B, 0xEB, 0xB0,
    0x06, 0xC7, 0x2A, 0x3A, 0xD2, 0x66, 0x81, 0xDB, 0x41, 0x62, 0xF2, 0x97, 0x17, 0xFE, 0x05, 0xEF,
    0xA3, 0xDC, 0x22, 0xB3, 0x45, 0x70, 0x3E, 0x18, 0x2D, 0xB4, 0xBA, 0x0A, 0x65, 0x1D, 0x87, 0xC3,
    0x12, 0xCE, 0x8F, 0x9D, 0xF7, 0x0D, 0x50, 0x24, 0x3A, 0xF3, 0xCA, 0x70, 0x6B, 0x67, 0x9C, 0xB2,
    0xC2, 0x4D, 0x6A, 0x0C, 0xA8, 0xFA, 0x81, 0xA6, 0x79, 0xEB, 0xBE, 0xFE, 0x89, 0xB7, 0xAC, 0x7F,
    0x65, 0x43, 0xEC, 0x56, 0x5B, 0x35, 0xDA, 0x81, 0x3C, 0xAB, 0x6D, 0x28, 0x60, 0x2C, 0x5F, 0x31,
    0xEB, 0xDF, 0x8E, 0x0F, 0x4F, 0xFA, 0xA3, 0xDA, 0x12, 0x7E, 0xF1, 0xA5, 0xD2, 0x22, 0xA0, 0x0C,
    0x86, 0x8C, 0x0A, 0x0C, 0x06, 0xC7, 0x65, 0x18, 0xCE, 0xF2, 0xA3, 0x68, 0xFE, 0x35, 0x96, 0x95,
    0xA6, 0xFA, 0x58, 0x63, 0x41, 0x59, 0xEA, 0xDD, 0x7F, 0xD3, 0x1B, 0xA8, 0x48, 0x44, 0xAB, 0x91,
    0xFD, 0x13, 0xB1, 0x68, 0x01, 0xAC, 0x3A, 0x11, 0x78, 0x30, 0x33, 0xD8, 0x4E, 0x6A, 0x89, 0x05,
    0x7B, 0x06, 0x8E, 0xB0, 0x86, 0xFD, 0x9F, 0xD7, 0x48, 0x54, 0x04, 0xAE, 0xF3, 0x06, 0x17, 0x36,
    0x53, 0x3F, 0xA8, 0x11, 0x53, 0xCA, 0xA1, 0x95, 0xC2, 0xCD, 0xE6, 0x1F, 0x57, 0xB4, 0x7F, 0xAA,
    0xF3, 0x6B, 0xF9, 0xA0, 0x27, 0xD0, 0x09, 0xEF, 0xF6, 0x68, 0x73, 0x60, 0xDC, 0x50, 0x2A, 0x25,
    0x0F, 0x77, 0xB9, 0xB0, 0x04, 0x0B, 0xE1, 0xCC, 0x35, 0x31, 0x84, 0xE6, 0x22, 0xF9, 0xC2, 0xAB,
    0x95, 0x91, 0x61, 0xD9, 0x2B, 0xB9, 0x72, 0x4E, 0x10, 0x76, 0x31, 0x66, 0x0A, 0x0B, 0x2E, 0x83,
};

int BitCount(BYTE x)
{
    int n = 0;
    n += ((x >> 7) & 1);
    n += ((x >> 6) & 1);
    n += ((x >> 5) & 1);
    n += ((x >> 4) & 1);
    n += ((x >> 3) & 1);
    n += ((x >> 2) & 1);
    n += ((x >> 1) & 1);
    n += ((x >> 0) & 1);
    return n;
}

void decode_mmb2(BYTE *p)
{
    if(p[6] == 0xFF && p[7] == 0xFF)    {
        int decode_length = (p[0] << 0) | (p[1] << 8) | (p[2] << 16);
        DWORD key1 = p[5] ^ 0xF0;
        DWORD key2 = key_table2[key1] ;
        int key_counter = 0;

        DWORD decode_count = ((decode_length - 8) & ~0xf) / 2;

        DWORD *data1 = (DWORD *)(p + 8 + 0);
        DWORD *data2 = (DWORD *)(p + 8 + decode_count);
        for(DWORD pos = 0; pos < decode_count; pos += 8)
        {
            if(key2 & 1)
            {
                DWORD tmp;

                tmp = data1[0];
                data1[0] = data2[0];
                data2[0] = tmp;

                tmp = data1[1];
                data1[1] = data2[1];
                data2[1] = tmp;
            }
            key1 += 9;
            key2 += key1;
            data1 += 2;
            data2 += 2;
        }
    }
}

void decode_mmb(BYTE*p)
{
    if(p[3] >= 5)
    {
        int decode_length = (p[0] << 0) | (p[1] << 8) | (p[2] << 16);
        DWORD key = key_table[p[5] ^ 0xF0];
        int key_counter = 0;

        for(int pos = 8; pos < decode_length; pos++)
        {
            DWORD x = ((key & 0xFF) << 8) | (key & 0xFF);
            key += ++key_counter;

            p[pos] ^= (x >> (key & 7));
            key += ++key_counter;
        }
    }
    decode_mmb2(p);
}

void decode_mzb(BYTE* p)
{
    if (p[3] >= 0x1B)
    {
        int decode_length = (p[0] << 0) | (p[1] << 8) | (p[2] << 16);
        DWORD key = key_table[p[7] ^ 0xFF];
        int key_counter = 0;

        for (int pos = 8; pos < decode_length; )
        {
            int xor_length = ((key >> 4) & 7) + 16;

            if ((key & 1) && (pos + xor_length < decode_length))
            {
                for (int i = 0; i < xor_length; i++)
                 {
                    p[pos+i] ^= 0xFF;
                }
            }
            key += ++key_counter;
            pos += xor_length;
        }
        int node_count = (p[4] << 0) | (p[5] << 8) | (p[6] << 16);
        OBJINFO *node = (OBJINFO *)(p+32);
        for(int i = 0; i < node_count; i++)
        {
            for(int i = 0; i < 16; i++)
            {
                node->id[i] ^= 0x55; // OBJINFO.id[16]; offset +0x00
            }
            node++;
        }
    }
}


```


Pray mr.adult can heal from the illness.
