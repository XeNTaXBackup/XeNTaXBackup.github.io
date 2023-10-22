## Post #1
- Username: 0xdeadbeef
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 01, 2016 7:34 am
- Post datetime: 2018-07-01T02:10:26+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

Hi

I have been working on understanding the format of the models used in Lord of the Rings Online.  My work also applies to Dungeons and Dragons Online due to the common origin of the engines.  I have made considerable progress, but now I am at a stage where a lot more expertise is required to go forward.  I am looking for interested people to help out.

Here is a summary of what I can do:
- Load geometry for all models: vertices and element arrays / indices.
- Load bone indices and weights.
- Render all models that use a single UV in the basic T-pose.
- Basic material support: loading diffuse and normal maps; rendering with the diffuse map.
- Load all HLSL shader sources associated with each model.
- Export the geometry to OBJ (limited use as OBJ doesn't support all the data types present)
- Provide samples and C++ or Python code for loading everything.

Here is a summary of what I need help with:
- Meaning of the remaining data in the mesh files for each model.  The abstract structure of the data is fully understood but not its meaning.  I think the data needs to be visualized.
- Rendering the models that use multiple UVs (some use 2 some 3)
- Understanding more data in the small model setup files. These contain data about bones, holding locations, AABBs, and... what else?
- Applying more data in the materials.  The structure of the data is fully understood, and descriptive names available for most of it, but I don't "do" lighting yet.

The main qualification for helping out is being more than a total beginner (like me) at models and animation.  Maybe some of the unknown data would make immediate sense to someone with experience who knows what to expect.

Altogether, I have a lot of information on the client-side data for these games.  I'll certainly post everything on the models in this thread, but perhaps not until it's closer to completion?  What do the regulars here recommend, should I dump everything in this thread immediately, or organize help via PMs (please feel free to send one) and only put results here when things are closer to completion?
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-07-02T07:45:13+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

0xdeadbeef, thanks for your hard wokr! can you upload the tools here?
## Post #3
- Username: 0xdeadbeef
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 01, 2016 7:34 am
- Post datetime: 2018-07-03T03:09:14+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

> Reply from Tosyk
>
> 0xdeadbeef, thanks for your hard wokr! can you upload the tools here?

Thanks for the interest! I have uploaded a subset of the Python tools relating to models.  I will continue to upload more of my toolset as I get time.  The first upload includes about 20 files out of over 150.  It is enough for working with most of the models.  I look forward to any input on the unsolved challenges mentioned in the OP.
[xentax10.7z](https://xentaxbackup.github.io/file/14545_xentax10.7z)
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-07-04T06:55:32+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

> Reply from 0xdeadbeef
>
> Tosyk wrote:0xdeadbeef, thanks for your hard wokr! can you upload the tools here?

Thanks for the interest! I have uploaded a subset of the Python tools relating to models.  I will continue to upload more of my toolset as I get time.  The first upload includes about 20 files out of over 150.  It is enough for working with most of the models.  I look forward to any input on the unsolved challenges mentioned in the OP.thanks for the share, 0xdeadbeef, I'll take a look at the tools when I get home
## Post #5
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-06-27T11:26:57+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

Hi 0xdeadbeef,

First thanks for all your work!

i could use help getting this to work, i tried running your scripts but cant seem to get them to work.

i tried to follow your example in README file and tried running some of the scripts independently but they all got "not defined" error.



for example in dataid.py

no file or data is imported as far as i can see, but all arguments seem to be undefined  - is there any input i need to enter?

where do i chose which .dat file i want to open? or is that set by dataid?


sorry if the questions seem stupid i know some basic C code, never tried python before today.


any chance for the GUI 

Thanks in advance
## Post #6
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-07-04T21:00:51+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

So i manged to get the code working without any errors,

the last array "rm" is filed with byte data, but how do i get this data into a 3d model view?

or convert it to usable format like .obj?

if anyone is intrested this how i changed to code to work for me: (for some reason when following the example i kept getting errors)
[xentax1.PNG](https://xentaxbackup.github.io/file/16427_xentax1.PNG)
## Post #7
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-19T01:29:26+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

By editing the hkt of client_anim, it is now possible to load it with Havok Tools.
It's obviously valid for Animation, but I haven't found the file containing the Skeleton file (hkaSkeleton) yet, so I'm not sure if it can be played normally. 
By the way, is there a function to actually import and output the model?
I would like to combine them with anime and see if they can be loaded normally.

*EDIT
The file containing hkSkeleton exists in client_general.
It is difficult to find a skeleton and its corresponding animation because it does not have an identifiable file name.
However, with some edits, hkSkeleton could also be loaded with Havok Tools.



ddo.JPG (60.84 KiB) Viewed 278 times


However, since the bone indice param tag included in normal hka does not exist, even if you find the corresponding skeleton and animation, the animation may not be playable.

*MORE EDIT
I converted from hkt to xml and checked the information, but the information of hkaAnimationBinding is not set in all hka.
havok associates bones with anime through hkaAnimationBinding.
In DDO, the animation data itself may be Havok, but the method of reading it may be custom.
## Post #8
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-19T06:53:57+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

This thread got me into RE   

I actually managed to make a noesis script for DDO that works for 100% of meshes and skeletons.
But haven't been able to connect skeleton and animation, script also has many issues so i dont have any intention of releasing it at its current state.

> Reply from einherjar007 ↑Thu Nov 19, 2020 9:29 am at Thu Nov 19, 2020 9:29 am
>
> 
It is difficult to find a skeleton and its corresponding animation because it does not have an identifiable file name.
The secret to connecting skeleton files to mesh file is this: at the very end of the skeleton file all related mesh names are added.
For example: say slaad skeleton is used by blue and red slaad and file names of red is ABC and file name of blue is DFC, the very last bytes of the file will be ABCDFC if i remember correctly haven't touched it in over a year.

My main issue it traversing the .dat files and finding what i need, once i find skeleton/and texture data script loads them with no issues.

Could you show on example how to edit them so they can be viewed in Havok Tools please?



I wonder if someone is noticing a pattern with me and D&D games
## Post #9
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-19T07:43:39+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

funtastic work, jayn23!

To use a havok file with Havok Tools, first edit the header. Since there is unnecessary random data for each file,
remove the byte at the beginning so that 1E 0D B0 comes to the beginning.

*I dunno the exact version of Havok, but it can be loaded with the 2014 tools.
Then convert it to an xml file with AssetCc2.exe. AssetCc2.exe * .bin * .hkx

However, these files do not contain definition tags such as hkaAnimationContainer or hkRootLevelContainer and cannot be loaded by HavokTools.
You can define tags by adding them yourself or by using the data in other files.

I'm currently in a different location, so I can't access the hkx file to see the data. I will send you the minimum configuration hkx file, which is convenient for checking the data in PM later.
But sadly, animations are probably not available unless you find hkaAnimationBinding and transformTrackToBoneIndices somewhere on your client. It's probably impossible to manually define Havok's Bone Indicators.
## Post #10
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-19T09:02:23+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

> Reply from einherjar007 ↑Thu Nov 19, 2020 3:43 pm at Thu Nov 19, 2020 3:43 pm
>
> 
However, these files do not contain definition tags such as hkaAnimationContainer or hkRootLevelContainer and cannot be loaded by HavokTools.
You can define tags by adding them yourself or by using the data in other files.

I'm currently in a different location, so I can't access the hkx file to see the data. I will send you the minimum configuration hkx file, which is convenient for checking the data in PM later.
But sadly, animations are probably not available unless you find hkaAnimationBinding and transformTrackToBoneIndices somewhere on your client. It's probably impossible to manually define Havok's Bone Indicators.

I am embarrassed to say that i dont really know much about HAVOK format so all these tags like hkaAnimationBinding are going above my head   

What i did to RE skeleton format, i download .hkx files i could find on the web converted them to xml using HAVOK tools and RE all the transform data until i figured it all out, it was a long process of trial and error, but it was also my first go at skeleton data.

I never tried looking at the animation format because i could never attach a skeleton to corresponding animation to do some testing.
I believe if we can somehow find the connecting thread we can figure out the animation format as long as its not compressed - i dont work well with compressed data   

Edit:
I also when to give the Author of this thread credit for helping me while starting out, he sent me all his source code that was 150+ python files.
but for someone at the time who couldn't even print "hello world" in python it was a bit much so ya i took it slow and learned one step at a time.
## Post #11
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-19T16:42:22+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

Thank you PM, Unfortunately I can't seem to reply. but I understand the situation.
I attached havok_minimum.zip, The first three letters (H*,) of the PM you sent are the password.
*sorry, My country has recently become stricter in copyright, so I'm cautious about uploading.
This hkx file is just a minimal configuration file, so it's not rare.
It is faster to actually explain how to use this file using the bin file. Tomorrow, I will explain using the DDO file.

Thanks also for the information about mesh and skeleton filenames!
I have no knowledge of analysis. I just found out what the file formats have in common and what they can edit by trial and error. I'm glad it was useful.

And as for Indice, I can't get a 100% accurate animation, but I found a way to play it for the time being.
If the skeleton's "parentIndices num elements" and the animation's "numberOfTransformTracks" numbers match when converted to xml, 
create a pseudo-Indice (generally correct, but some rotations are corrupted I will explain this method tomorrow.

I'm a fan of the Dungeons & Dragons series, so I'm very happy that you're trying to create a script. really Thank you!
(Sorry for childish English. I am using translation)
## Post #12
- Username: Splasher9
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 04, 2013 10:57 pm
- Post datetime: 2022-05-10T08:53:25+00:00
- Post Title: Lord of the Rings Online and Dungeons and Dragons Online

Sorry to bumping the old topic..

Just wanted to know if there is an easy way to extract models from the .dat files than running .py scripts? (The script startup sequence is not entirely clear to me and im not good with programming)

At first tried to use DAT_UNPACKER for LOTR to unpack DDO .dat files and it didnt work out. Maybe someone could help me with model extraction?
