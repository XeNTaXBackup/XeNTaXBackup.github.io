## Post #1
- Username: thugsoldierx
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 17, 2010 5:25 pm
- Post datetime: 2010-07-12T16:31:32+00:00
- Post Title: Needs help with MK Vs DC universe textures

Hey ,
anybody know how to get the textures out the game MK vs Dc universe here is a file and i think that the file where the textures are in .

[http://www.megaupload.com/?d=BPJXUY87](http://www.megaupload.com/?d=BPJXUY87) 

i hope someone can help me with this    its a .xxx File .
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-12T16:42:15+00:00
- Post Title: Needs help with MK Vs DC universe textures

umodel supports models and textures from this game.
## Post #3
- Username: thugsoldierx
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 17, 2010 5:25 pm
- Post datetime: 2010-07-12T16:44:47+00:00
- Post Title: Needs help with MK Vs DC universe textures

> Reply from chrrox
>
> umodel supports models and textures from this game.

yeah i know i hear about it but where can i find it and how must i use it to get those textures ?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-12T17:59:31+00:00
- Post Title: Needs help with MK Vs DC universe textures

did you even attempt to find umodel?
just Google umodel results in his website being the 3rd in the list
if i google umodel unreal his site is the first one.
## Post #5
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-07-12T18:36:26+00:00
- Post Title: Needs help with MK Vs DC universe textures

> Reply from chrrox
>
> did you even attempt to find umodel?
just Google umodel results in his website being the 3rd in the list
if i google umodel unreal his site is the first one.
It's amazing how low the GQ's (Google Quotient) of people can be.
## Post #6
- Username: thugsoldierx
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 17, 2010 5:25 pm
- Post datetime: 2010-07-12T19:42:14+00:00
- Post Title: Needs help with MK Vs DC universe textures

> Reply from brienj
>
> chrrox wrote:did you even attempt to find umodel?
just Google umodel results in his website being the 3rd in the list
if i google umodel unreal his site is the first one.
It's amazing how low the GQ's (Google Quotient) of people can be.

yeah i have found stuff i have the downloaded Umodel for Win32 and also fix the game unreal tournament 2004  but what must i do with it to get the textures from mk vs dc universe ? brienj can you please  help me out with this ?
## Post #7
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-07-12T21:17:04+00:00
- Post Title: Needs help with MK Vs DC universe textures

On Gildors website where you found Umodel there are 2 video tutorials on how to do stuff. There is also a whole forum on his site specifically designed to explain just the sorta things your asking.

just in case you can't figure out how to do it, ive provided the links you need   

[Video tutorials](http://www.gildor.org/projects/umodel/tutorials)
[The forum](http://www.gildor.org/smf/index.php?board=3.0)

And the advice you find on there does work, i started ripping UT3 based games a few weeks ago ( MK Vs DCU being one of them ) and ive had nothing but success.

Have fun now.

Nobby.
## Post #8
- Username: thugsoldierx
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 17, 2010 5:25 pm
- Post datetime: 2010-07-13T11:17:12+00:00
- Post Title: Needs help with MK Vs DC universe textures

yeah thanks but i already done that parts on the tutorials and still get this error message 


******** C:\TMP\Umodel\CHAR_LiuKang.xxx ********

WARNING: IntProperty "UAnimSequence::m_nVersion" was not found
ERROR: assertion failed: size >= 0 && size < (256<<20)

appMalloc:size=1041865114 <- TArray::SerializeSimple <- UAnimSequence::Serialize <- LoadObject:AnimSequence'CHAR_LiuKang.AnimSequence_0', pos=3FE99, ver=402/30, game=1803 <- UObject::EndLoad <- UnPackage::CreateExport:CHAR_LiuKang.xxx:155 <- LoadWholePackage <- Main

can some1 add me on messenger ([thugsoldierx@hotmail.com](mailto:thugsoldierx@hotmail.com)) and show me it on teamviewer how umodel works please ?
## Post #9
- Username: thugsoldierx
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-13T11:32:55+00:00
- Post Title: Needs help with MK Vs DC universe textures

animation is not supported iun this game use the -noanim flag in the command line

c:\umodel.exe -export -noanim c:\test.xxx
## Post #10
- Username: thugsoldierx
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 17, 2010 5:25 pm
- Post datetime: 2010-07-13T12:16:59+00:00
- Post Title: Needs help with MK Vs DC universe textures

thanks i got it now realy this was helpfull    but those mk vs dc textures looks awfull
## Post #11
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-07-13T18:03:06+00:00
- Post Title: Needs help with MK Vs DC universe textures

> Reply from thugsoldierx
>
> thanks i got it now realy this was helpfull    but those mk vs dc textures looks awfull

Try removing the transparency layer from the images.when you try viewing the textured model in almost any 3d app the transparency will make most of the model look screwed up.  To be honest im surprised you never ran into this before, this is a very common thing for games to do. All of the textures ( diffuse, specular and normal map ALL have transparency layers )


This is what the 3d apps see because of the transparency........................ And this is what they need to see....
[](http://img210.imageshack.us/i/61077875.jpg/) [](http://img541.imageshack.us/i/42266302.jpg/)
Both images are " Raiden_Diff.tga " just i removed the transparency from the second image so you can see what it supposed to look like.
Here is a pic of Raiden, in Wireframe mode so you can see all the data. And here is the same model textured. 
[](http://img687.imageshack.us/i/21302928.jpg/) [](http://img517.imageshack.us/i/63291235.jpg/)
As you can see the transparency effects what the model looks like in a big way. The models will look like this in 3ds max when you import the PSK, and will look pretty much the same in most 3d apps untill you do something about the transparency layer. 
Also... This might sound like a stupid question ( but you never know these days ) you do know how the textures work for these models , don't you?  like when it asks for a texture for "material1, material2" (in some cases up to material 50 ) you do know which textures maps should be used for those? And also the first ( sometimes 2 ) materials ( not material 1 and 2) usually called "character" and "accessories" usually don't get a texture applied to them, you have to do that manually most times ( and they are the two main textures) If you don't know how any of those work then no wonder your having problems with textures looking wrong.
## Post #12
- Username: thugsoldierx
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 17, 2010 5:25 pm
- Post datetime: 2010-07-13T19:55:09+00:00
- Post Title: Needs help with MK Vs DC universe textures

yeah they looks good haha i use the wrong program to open up the tga files but they are good now.  som1 know something about the textures off the game marvel ultimate aliance 2 ?
