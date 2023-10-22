## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-27T15:54:06+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

1) Introduction
Advanced Mesh Reaper - Xtreme Edition, abbreviated AXE, is a complete reconstruction of the existing [Advanced Mesh Reaper](viewtopic.php?f=33&t=20995), abbreviated AMR, and comes with a lot of exclusive new features.

Unlike AMR, AXE is designed to support as many vertex attributes as possible. Apart from positions, normals and texcoords, AXE supports also tangents, binormals, vertex colors, blend indices and blend weights. It also introduced an "Auto Bone Generation" system in order to actually support skinning info, which might be the biggest highlight when compared with AMR.

AXE also attempts to become more flexible so as to deal with different data structures. A mesh object can now be described with multiple polygon and vertex parameter sets which provides a possibility to handle and validate variable-length data structure, or simply to merge a set of sub-meshes into a single object. When there's only one parameter set for polygon and vertex attributes, AXE will then degenerate itself into the exact same workflow as AMR. 

2) Change Log

```
				Added an option to the Tools for importing skeleton from external bone nodes dump;
				Added a bone index base parameter for adjusting the final blend indices;
				Fixed force noramlization of tangent & binormal not working for data interpretation;
				Fixed incorrectly saving of vertex params in PLC file;
				Fixed implict index encoding error;
				Fixed ineffectiveness of relative address sub-switches for TBN vectors;
				Fixed constraint for min value of All Same Stride in some scenarios.
2021.10.10 - v1.2.0 		Removed the global position divisor factor from Preference;
				Added a local "Positions Unit Factor" option to the vertex parameter section;
				Added an option to inverse TBN vectors;
				Added an option to force noramlization on TBN vectors;
				Added sub switches of Relative Address, All Same (of Stride) and All Same (of Data Type) for all vertex attributes;
				Adjustments on the UI and the PLF definitions due to the above changes.
2021.10.01 - v1.1.1 		Fixed an issue that the vertex parameter sets combo box might contain incorrect amount of items;
				Fixed an issue where memory was allocated insufficiently for stripped indices;
				Fixed an issue which prevented certain data type params from being loaded.
2021.07.17 - v1.1.0	 	Fixed an issue that prevents from generating implicit indices when material group params are not used;
				Added option to dump decoded polygon vertex indices to specified file;
				Added option to specify individual data source for reference indices in the Data Reorganizer;
				Support for passing a shared source data file path argument through command line;
				Added error identifiers for polygons if duplicate value detected upon interpretation;
				Added a global position divisor factor to Preference.
2021.06.05 - v1.0.2		Fixed a bug that crashed the program when adding a triangle strip mesh param to the list;
				Minor optimizations for Preference and PLC statistics calculation.
2021.05.27 - v1.0.1		Initial release.

```

3) User Interface


Refer to the [AXE Demo](viewtopic.php?f=29&t=23962) for a peek on its capabilities.
Get the version fit with the demonstration [here](viewtopic.php?f=16&t=23963&p=178524#p178524).

4) Main Features
1. Ability to specify individual data source files for polygon and vertex attributes, or to use a single source for all channels;
2. Support for material assignment and management;
3. Support for assigning multiple materials to different polygon sets of a single mesh;
4. Flexible mesh constructing workflows based on parameter set system;
5. Support for all kinds of vertex attributes including positions, texture coordinates, TBN vectors, vertex colors and skinning info;
6. Ability to handle position bounding box to retain the in-game scaling;
7. Support for multiple UV channels without limit on amount;
8. Support for applying textures on any specified UV channel;
9. Ability to merge sub-meshes into a single object or to split a mesh group into physically detached sub-meshes;
10. Support for mesh transformation including translation, rotation, scaling and axis inversion;
11. Ability to automatically generate a set of bone nodes from existing skinning info, and provides tools for editing and constructing a usable skeleton based on the result;
12. Data interpretation and statistics analysis for polygon and vertex attributes;
13. Support for saving/loading all params to/from the parameter list container format;
14. Helper tool to reorganize data referenced by indices;
15. Visualization for positions, texcoords, TBN vectors, vertex colors and skeleton.

5) Example Model Extracted by the Tool



6) Notes

There are some components used or required by AXE which are not likely to be changed frequently so they're detached from the release of the AXE executable.

The first component is an external mesh viewer called "ViewScene" which AXE uses to preview the model with different attributes.
It's similar to the one used by AMR but it has been extended for the needs of AXE.

The second component is required by AXE for its GUI is based on Qt technology thus it requires the Qt dependencies for execution.

These components can be downloaded through the links provided in the attachment.

You must place both the ViewScene folder and the Qt dependencies into the same path of the AXE executable.
The overall folder layout of AXE should be:

```
AXE/ViewScene/*
AXE/platforms/*
AXE/Qt5**.dll

```


Microsoft Visual C++ 2015 Redistributable (x86) or above is required for runtime.

7) Download
[AXE.7z](https://xentaxbackup.github.io/file/21460_AXE.7z)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-07-17T15:27:55+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

Updated v1.1.0:
- Fixed an issue that prevents from generating implicit indices when material group params are not used;
- Added option to dump decoded polygon vertex indices to specified file;
- Added option to specify individual data source for reference indices in the Data Reorganizer;
- Support for passing a shared source data file path argument through command line;
- Added error identifiers for polygons if duplicate value detected upon interpretation;
- Added a global position divisor factor to Preference.

I'm considering dropping support for WinXP coz up to now for release I still have to compile the application within a VM where the required version of Qt was installed. So I've created a poll. Anyone, especially XP users, feel free to show your opinion. Thank you for your attention!
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-01T10:08:26+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

Updated v1.1.1:
- Fixed an issue that the vertex parameter sets combo box might contain incorrect amount of items;
- Fixed an issue where memory was allocated insufficiently for stripped indices;
- Fixed an issue which prevented certain data type params from being loaded.



 AXE_v1.1.1.7z
(235.93 KiB) Downloaded 118 times



Well, since the poll has ended and still there're 6 voted "Yes", guess I'll have to keep the WinXP support for future release.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-10T10:32:25+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

Updated v1.2.0:
- Removed the global position divisor factor from Preference;
- Added a local "Positions Unit Factor" option to the vertex parameter section;
- Added an option to inverse TBN vectors;
- Added an option to force noramlization on TBN vectors;
- Added sub switches of Relative Address, All Same (of Stride) and All Same (of Data Type) for all vertex attributes;
- Adjustments on the UI and the PLF definitions due to the above changes.

Note that v1.1.1 will still be available for a while in order to comply with the AXE demonstration until there's urgent need for updating the article. Also I've extended the end time of the vote to make it run in the long term.
## Post #5
- Username: AdventureT
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jun 22, 2019 2:46 pm
- Post datetime: 2021-10-19T06:48:42+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

Will there be animation support in the future?
## Post #6
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-10-31T11:04:12+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

Hey, I wanted to ask two questions, sorry if I won't understand you from your first reply since English isn't my first language and this definitely isn't my area of expertise, but:

a) What's the point of parameter sets, can you use them for models of the same format and sort of make extracting models of the same format easier? From your post I can understand that yes, you can use them to combine multiple meshes into one but as per to how I can do that is how I'm a little lost - although I will definitely go over the AXE demo again to try and understand it better because I want to learn how to use AXE a lot more. I can do simple stuff like faces and UVs but I haven't dabbled in like the material groups, bones etc.

b) Is there any way to automate extracting models in terms of vert/face count or finding the start offset (like for example how noesis seeks the header)? Cause as of now I simply load the .plc I had made for and manually find the offset again and vert count and faces count.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-31T12:40:22+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

> Reply from dimis9138 ↑Sun Oct 31, 2021 7:04 pm at Sun Oct 31, 2021 7:04 pm
>
> 
What's the point of parameter sets
Parameter sets of what? Mesh? Polygon? Or Vertex attributes?

> Reply from dimis9138 ↑Sun Oct 31, 2021 7:04 pm at Sun Oct 31, 2021 7:04 pm
>
> 
can you use them for models of the same format and sort of make extracting models of the same format easier? ... you can use them to combine multiple meshes into one
What do you mean by "same format"? Judging by file extensions? Or geometry data layouts? Anyway there's no connection between each mesh recorded in the Parameter List. They're just a set of mesh objects that can be exported as a single FBX. But for Polygon and Vertex param sets, the only rule is that every param set must be consistent to each other. That is, you can't attempt to remove the material groups info of a new polygon param set when such info is specified in previous param sets, or vise versa. And you can't create a set of vertex params where some of them contain certain vertex attributes while others don't. Such operations are all forbidden and AXE will prompt you with the corresponding error message if you did, unless there's any unknown bugs, so if you encounter any, please let me know.  

> Reply from dimis9138 ↑Sun Oct 31, 2021 7:04 pm at Sun Oct 31, 2021 7:04 pm
>
> 
Is there any way to automate extracting models in terms of vert/face count or finding the start offset (like for example how noesis seeks the header)? Cause as of now I simply load the .plc I had made for and manually find the offset again and vert count and faces count.
AXE is mostly a helper tool so yeah you basically find everything manually and validate your guesses with it. After you've finished your analysis of the format you're dealing with, you can write an specialized tool for automatic handling. That is, either you re-implement everything you need from AXE, or to use tools like Noesis which provides such APIs.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-31T15:05:12+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

> Reply from Bigchillghost ↑Sun Oct 31, 2021 8:40 pm at Sun Oct 31, 2021 8:40 pm
>
> AXE is mostly a helper tool so yeahOne of the best I know of so far.  

btw, I had the idea of an extra feature for hex2obj, (additional) creation of an AMR-plf file.
But I met too many unknowns (01 000000 and many zeroes  ) in the binary file:
.



AMR plf file.png (24.66 KiB) Viewed 1412 times
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-31T15:28:20+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

> Reply from shakotay2 ↑Sun Oct 31, 2021 11:05 pm at Sun Oct 31, 2021 11:05 pm
>
> 
btw, I had the idea of an extra feature for hex2obj, (additional) creation of an AMR-plf file.
But I met too many unknowns (01 000000 and many zeroes  ) in the binary file:
Ah, reminded me of the old days and all the pain of porting existing PLFs to a new version every time there're new fields adding in. That's why I chose json instead for AXE. But AMR is an abandoned project now (meaning that any known/unknown bugs will not be fixed) so it just don't worth the efforts for such attempts.
## Post #10
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-05T12:31:02+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

Quick question as I'm trying to turn some of my AXE stuff into Noesis plugins for fun and to learn, what's the char/word (word is ushort I think?) option for normals and tangents etc? Wasn't able to find it in Noesis documentation for normals for the AOE4 plugin I'm trying to work on and I was basically wondering what the Noesis equivalent would be.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-05T15:10:38+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

> Reply from dimis9138 ↑Fri Nov 05, 2021 8:31 pm at Fri Nov 05, 2021 8:31 pm
>
> 
what's the char/word (word is ushort I think?) option for normals and tangents etc?
"char" means signed byte. And yes, "word" is a alias of unsigned short. More info here:
[viewtopic.php?p=138999#p138999](viewtopic.php?p=138999#p138999)

Or just google for the terms.
## Post #12
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-04T11:29:10+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

> Reply from Bigchillghost ↑Thu May 27, 2021 11:54 pm at Thu May 27, 2021 11:54 pm
>
> 

      thank you for your sharing!
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-04T12:45:41+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

> Reply from ptg1121 ↑Sat Dec 04, 2021 7:29 pm at Sat Dec 04, 2021 7:29 pm
>
> 
I think it's best NOT to quote anything directly from the main post, for the sake of future management and simplicity of this topic. You can re-edit your post and replace it with an empty quote like this one above.
## Post #14
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-04T12:53:19+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

> Reply from Bigchillghost ↑Sat Dec 04, 2021 8:45 pm at Sat Dec 04, 2021 8:45 pm
>
> 


Hello, your software is too strong, but I can't play it. I see that PDF is different from the new version in many places。



Can I record a demo video with the new version of AXE?
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-04T14:33:14+00:00
- Post Title: Advanced Mesh Reaper - Xtreme Edition

> Reply from ptg1121 ↑Sat Dec 04, 2021 8:53 pm at Sat Dec 04, 2021 8:53 pm
>
> I see that PDF is different from the new version in many places
Use v1.1.1 to couple with the demonstration as a start. There should be no difficulties for transition to a newer version once you're familiar with it.

> Reply from ptg1121 ↑Sat Dec 04, 2021 8:53 pm at Sat Dec 04, 2021 8:53 pm
>
> Can you spare time for the latest version of the video?
What video?

FYI the closing tag of your quote is missing. Make sure to place the text within the BBCode tag pair.

```
...
[/quote]

```

For more info, read here:
[app.php/help/bbcode](app.php/help/bbcode)
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T13:33:17+00:00
- Post Title: Re: Advanced Mesh Reaper - Xtreme Edition

Updated v1.3.0:
- Added an option to the Tools for batch generating materials of different base colors;
- Added an option to the Tools for importing skeleton from external bone nodes dump;
- Added a bone index base parameter for adjusting the final blend indices;
- Fixed force noramlization of tangent & binormal not working for data interpretation;
- Fixed incorrectly saving of vertex params in PLC file;
- Fixed implict index encoding error;
- Fixed ineffectiveness of relative address sub-switches for TBN vectors;
- Fixed constraint for min value of All Same Stride in some scenarios.
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-24T11:41:40+00:00
- Post Title: Re: Advanced Mesh Reaper - Xtreme Edition

Update:
Recompiled v1.1.1 and v1.3.0 executables for WinXP.
