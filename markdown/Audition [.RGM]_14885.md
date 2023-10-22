## Post #1
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2016-08-18T17:00:51+00:00
- Post Title: Audition ["*.RGM"]

Hello, i have already made few post on this forum to talk about the same file format but my topics weren't interesting and were useless... im writting a new one today because their is a lot of experienced people on this forums who have a lot of knowledge that i don't have... i never made any binary file format and i feel very useless here... btw im learning c/++ and java for 7 months now but i can't do anything related to 3D binary mesh and i don't know where to start... I already got an answer about this file format on this forum and they told me that it was not an hard format and writting a maxscript from it would not be that hard... but i still can't find how to do it...
My goal with this format is to understand how he is working and to be able to import some files to 3DS max or any other 3D software... im not here to hack the game or ruin it i just love the character from it and their styles, the thing is that i want to use them for a fan-made game based with audition / Super dancer online / dance dance revolution characters...
But before talking about the format i will just give you some info about audition :

Audition online is a 3D rythm and dancing game released in korea back in 2006, this game exist in many different country and is a free-to-play.
The game is very popular in asian countries and exist on Play Station Portable also...
The gameplay is similar to dance dance revolution (it also works with arrows) but here you don't dance with your feets but with your hand ! 
(Here is a gameplay : [https://www.youtube.com/watch?v=xa_MlO2rSYM](https://www.youtube.com/watch?v=xa_MlO2rSYM))
This game is also famous because a lot of people are making modifications (custom songs... interface... custom textures) but anyway...
let's talk about the 3D file format ! 

the game himself store his models and textures in the Data folder... in archive called "*.ACV" you can get them by extracting the archive...
And into acv file you will find "*.RGM" file...
The RGM file is a file format that stores 3D meshes and biped animations
When you open ANY rgm file from audition you will notice that each time the file start with : "Delight3D 3D DynamicObjectFile..ÞÞÞÿÿÿ...Scene Root..Bip01..Bip01 Footsteps..Bip01 Pelvis..Bip01 Spine..Bip01 Spine1..Bip01 Neck..Bip01 Head..Bip01 HeadNub..Bip01 L Clavicle..Bip01 L UpperArm..Bip01 L Forearm..Bip01 L Hand..Bip01 L Finger0..Bip01 L Finger0Nub..Bip01 R Clavicle..Bip01 R UpperArm..Bip01 R Forearm..Bip01 R Hand..Bip01 R Finger0..Bip01 R Finger0Nub..Bip01 L Thigh..Bip01 L Calf..Bip01 L Foot..Bip01 L Toe0..Bip01 L Toe0Nub..Bip01 R Thigh..Bip01 R Calf..Bip01 R Foot..Bip01 R Toe0..Bip01 R Toe0Nub..Object01"
And i made some research about "delight 3D 3D dynamicObjectFile" and i saw that it was a rendering tool for 3DS MAX... (also maybe RGM file header ?)
Another interesting thing is that the PSP version of the game store his models and animations into a simple file format "*.GMO" (like the PC version) and i noticed that every model (face / shoes / shirt / hair) were already skinned ! so i think they exactly did the same for the PC version ! 
It means that audition character is a mix of different meshes (already skinned with the same bones names) and that the animations that the characters uses are just biped with the same bones names as the ones from skinned meshes... i don't know if it's clear don't know how to explain...
But this is only what i know about the file from my knowledges !

Thank you for reading, any help is welcome and i will be very happy to answer !
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2016-09-09T03:00:35+00:00
- Post Title: Audition ["*.RGM"]

> Reply from Facebook.com
>
> Hi, i saw your videos in YouTube And i found Exactly what i always wanted to see ! Someone explaining how to write import script for 3DS Max And very interesting video about binary mesh file ! And i would like to know since Im really new in this world of modding If you could help me about an "easy" binary mesh format... I don't force You at all If you don't want or don't have Time i understand And it's normal ! The format come from audition online it's à very old format (12 years old) And It contain mesh And animation here is the link from xentax forum about It : viewtopic.php?f=16&t=14885
I just know that They made the game entirely with 3DS Max (from stages to avatars And a animations)

And that like the PSP version of the game all models are already skinned to match the animation file biped
Hello Loginoux

I've read your xentax forum post here and if you are learning C, C++, and Java then you need to keep your focus on those.
It does not make sense for you to spend extra months to now learn maxscript when you already have the 7 months experience with those other languages.

Now unfortunately I cannot provide that help for you, as I just don't have enough knowledge with those languages to guide you.

But as you probably know already I have a maxscript series on how to read a 3d binary file into 3dsmax: [MaxScript [Video Guide]](http://forum.xentax.com/viewtopic.php?f=16&t=5644)
I've just added a playlist to keep those youtube video's more organised: [[Maxscript] How to Read a Model from Binary](https://www.youtube.com/playlist?list=PLgeoiwC2u6R6NIX_-AIsd62eL4fBI1Z7k)

The point here is that from those videos you may be able to get an idea on how to understand the (*.RGM) binary file.

As for C, C++, and Java check the manuals because you should be able to read binary naively in those languages. 
Then ask around for specific help on how to output a 3D file to (.Obj)

-Goodluck!

EDIT
I've had a look at one of the file samples "000.rgm"

From what I found it does not contain model data, it is an animation file.
But because it is missing the idle pose or the skeleton data it's useless on it's own.

My process of figuring out the format was record and took around an hour, if you wish that can be seen here
[https://youtu.be/oqKQ9h2C8HA](https://youtu.be/oqKQ9h2C8HA)

Structures
* little endian
* all integers are unsigned unless noted
* byte=8bit int, short=16bit int, long=32bit int, float=32bit float, matrix3x4 = 32bit float x12

```
	string	filetype
	short		unk1
	long		unk2
	long		unk3
	table1[n]	bone_info		// see table1 struct, n = 32 (constant?)
	long		count1
	long		unk04

	table1
		string	name
		byte		unk1

// After header loop bone_anim struct until End of File/Stream is reached, no count was found

bone_anim
	byte		unk01
	short		unk02
	short		unk03
	float		unk05
	float		unk06
	float		unk07
	float		unk08
	float		unk09
	float		unk10
	float		unk11
	float		unk12
	float		unk13
	float		unk14
	float		unk15
	float		unk16
	float		unk17
	float		unk18
	matrix3x4[n]	transforms		// n = count1 from header


```
## Post #3
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2016-09-10T16:24:43+00:00
- Post Title: Audition ["*.RGM"]

Hi, thank you for your kind reply !
I saw your video and it was very interesting i really liked it, i will also watch your playlist and focus on c/c++ more than maxscript...
About that 000.rgm it seems like a blank file(im sorry for it), so i updated my post and now you have other files if you want to check them ! 
Now i have more information about the file structure and this is really awesome, i don't know how to make stuff from the code you wrote but it's sure very useful, but i have a question if you have information about the file header... and the format himself is it possible to make your own "*.rgm" ?
Thank you for everything you done btw
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2016-09-13T00:13:48+00:00
- Post Title: Audition ["*.RGM"]

I looked at the format that had a model and there is a value that was 0 before that is now a vertex count followed by model data

you can see the video here;
[https://youtu.be/Ax_ghwMjnNI](https://youtu.be/Ax_ghwMjnNI)

and I'll upload the maxscript that was used *It was only written and tested for one file*
[RGM_IMP.zip](https://xentaxbackup.github.io/file/11699_RGM_IMP.zip)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-13T02:54:46+00:00
- Post Title: Audition ["*.RGM"]

now that there are actual model samples i had to run one through Hex2obj for kicks  



a1404_rgm.png (39.33 KiB) Viewed 352 times
## Post #6
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2016-09-13T12:15:49+00:00
- Post Title: Audition ["*.RGM"]

Awesome ! i wish i could do it lol i don't know what exactly i should look for actually their is so much stuff xD im really happy to see your replies...
Have you tried to look at the RGM files for the stages ?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-13T16:49:30+00:00
- Post Title: Audition ["*.RGM"]

> Reply from Loginoux
>
> Have you tried to look at the RGM files for the stages ?
first submesh in x_mas.rgm  



x_mas_rgm.png (194.74 KiB) Viewed 332 times
## Post #8
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2016-09-13T17:58:42+00:00
- Post Title: Audition ["*.RGM"]

AceWell This is genius ! i updated my post and you will find 3 more stages if you want to check them
## Post #9
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2016-09-14T11:13:18+00:00
- Post Title: Audition ["*.RGM"]

> Reply from mariokart64n
>
> I looked at the format that had a model and there is a value that was 0 before that is now a vertex count followed by model data

you can see the video here;
https://youtu.be/Ax_ghwMjnNI

and I'll upload the maxscript that was used *It was only written and tested for one file*

Hi, i saw your video and tested your script with many RGM files, it works but sometimes some files don't appear in the scene even if the script work without error messages (i updated again my post so you have an entire folder if you want to improve your awesome script) and some models have problems with textures, if i try to take like a female shirt and texture it, the texture is reversed or mirrored... so maybe their is something in the file about it ?
 Thank you for your help again...
