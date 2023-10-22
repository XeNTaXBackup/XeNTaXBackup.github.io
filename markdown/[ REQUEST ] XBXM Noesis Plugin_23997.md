## Post #1
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2021-06-04T09:12:18+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

I managed to extract the files from Spider-Man 2 on original Xbox and I am hoping that someone would be willing to take a look and see what they can do. I've uploaded sample files to my one drive account. I assume the .XBX files are the models, and the .DDS files extracted as such, so the textures are already figured out. I would love to be able to do this, as we all know the console version of Spider-Man 2: The Game is ONE OF the only times a console version is far superior then its PC counterpart 

[https://1drv.ms/u/s!AslhLaUopiodukQGpVn ... l?e=5CHB0n](https://1drv.ms/u/s!AslhLaUopiodukQGpVnajd5aa12l?e=5CHB0n)

Thanks in advance guys
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-05T08:22:48+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Ecelon ↑Fri Jun 04, 2021 5:12 pm at Fri Jun 04, 2021 5:12 pm
>
> I assume the .XBX files are the models
That's true.  

Using AXE:
(edit: corrected polygon vertex indices count & address for the 1st submesh)
[PRISONER_RUFUS_00000002.png](https://xentaxbackup.github.io/file/20254_PRISONER_RUFUS_00000002.png)
## Post #3
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2021-06-05T10:30:35+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Bigchillghost ↑Sat Jun 05, 2021 4:22 pm at Sat Jun 05, 2021 4:22 pm
>
> 
Ecelon wrote: ↑Fri Jun 04, 2021 5:12 pmI assume the .XBX files are the models

That's true.  

Using AXE:

Thanks for confirming that mate, you're a bloody legend. I've downloaded AXE and toyed around with it for about 10 minutes. I've noticed that both our copies are different. Mine doesn't have a little-endian selection so I can't select it. If I keep big-endian unselected, that should default to little-endian? Also I tried to do a model I didn't upload, to see if I could do it. I couldn't figure out how to find the "vertex attributes - count". How would I go about figuring that out?

Thanks again 

EDIT: nevermind, just realized I downloaded your normal version and not the Xtreme Edition
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-05T15:02:53+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

Whoops, there was a mistake for the polygon params of the 1st submesh. The count and address for polygon vertex indices should respectively be 502 and 0x888.

> Reply from Ecelon ↑Sat Jun 05, 2021 6:30 pm at Sat Jun 05, 2021 6:30 pm
>
> I couldn't figure out how to find the "vertex attributes - count". How would I go about figuring that out?
Good thing is that you can literally find everything you need from the header and use the values as is. Just set the number of columns to 96 in your hex editor, and look for the sequence 06 00 00 00 to locate the info table, as shown in the following image:



hdr.png (33.63 KiB) Viewed 216 times


The info of one submesh is now held on one row so by counting the amount of the 06 00 00 00 sequence you'll know how many submeshes there're in the file. The sequence is followed by the count and the address of the polygon vertex indices. Skip 12 bytes and there come the count, the address and the size of the vertex data. The vertex stride comes 4 bytes after that. 

There's also a mapping bone indices count at 0x38 bytes before the vertex count, followed by the address of the mapping bone indices. You'll need that if you're interested in getting the skinning info.
## Post #5
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2021-06-07T13:08:44+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Bigchillghost ↑Sat Jun 05, 2021 11:02 pm at Sat Jun 05, 2021 11:02 pm
>
> 
Whoops, there was a mistake for the polygon params of the 1st submesh. The count and address for polygon vertex indices should respectively be 502 and 0x888.
Ecelon wrote: ↑Sat Jun 05, 2021 6:30 pmI couldn't figure out how to find the "vertex attributes - count". How would I go about figuring that out?

Good thing is that you can literally find everything you need from the header and use the values as is. Just set the number of columns to 96 in your hex editor, and look for the sequence 06 00 00 00 to locate the info table, as shown in the following image:
hdr.png
The info of one submesh is now held on one row so by counting the amount of the 06 00 00 00 sequence you'll know how many submeshes there're in the file. The sequence is followed by the count and the address of the polygon vertex indices. Skip 12 bytes and there come the count, the address and the size of the vertex data. The vertex stride comes 4 bytes after that. 

There's also a mapping bone indices count at 0x38 bytes before the vertex count, followed by the address of the mapping bone indices. You'll need that if you're interested in getting the skinning info.

I wanna thank you first and foremost, but to be honest, I just ain't getting mate. I've been toying around with Axa and HxD for an hour and haven't come up with a win sadly
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-07T17:43:35+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Ecelon ↑Mon Jun 07, 2021 9:08 pm at Mon Jun 07, 2021 9:08 pm
>
> 
to be honest, I just ain't getting mate. I've been toying around with Axa and HxD for an hour and haven't come up with a win sadly
The program is called "AXE", not "Axa". You'll need a basic understanding of common data types, hex reading and related terms of geometry elements to understand what I was talking about. Check the tutorial from the 1st link in my signature as a start. You can also read the demonstration on using AXE through the link in the AXE release page for further info.

In the meanwhile, you may use the following Noesis script to do the work for you.
[fmt_SpiderMan2_xbx.zip](https://xentaxbackup.github.io/file/20260_fmt_SpiderMan2_xbx.zip)
## Post #7
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2021-06-09T13:23:28+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Bigchillghost ↑Tue Jun 08, 2021 1:43 am at Tue Jun 08, 2021 1:43 am
>
> 
Ecelon wrote: ↑Mon Jun 07, 2021 9:08 pm
to be honest, I just ain't getting mate. I've been toying around with Axa and HxD for an hour and haven't come up with a win sadly

The program is called "AXE", not "Axa". You'll need a basic understanding of common data types, hex reading and related terms of geometry elements to understand what I was talking about. Check the tutorial from the 1st link in my signature as a start. You can also read the demonstration on using AXE through the link in the AXE release page for further info.

In the meanwhile, you may use the following Noesis script to do the work for you.

Sorry about that, that was typo. My bad mate. So I looked at your tutorial, and I haven't gotten any headway. Guess I'm just not cut out to reverse engineer models. Thanks for pointing me in the that direction though, I'll keep trying over time and hopefully I get somewhere.

Thank you so much for the Noesis plugin, that's helped immensely. It works for about half of the models and I was hoping you could take a look at the plugin and fix it if you have the time mate. I've uploaded new examples to: [https://1drv.ms/u/s!AslhLaUopiodukQGpVn ... l?e=5CHB0n](https://1drv.ms/u/s!AslhLaUopiodukQGpVnajd5aa12l?e=5CHB0n)

Thanks again, this is so awesome. I already have Black Cat done, in her awesome low-poly amazingness
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-12T14:22:48+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Ecelon ↑Wed Jun 09, 2021 9:23 pm at Wed Jun 09, 2021 9:23 pm
>
> It works for about half of the models and I was hoping you could take a look at the plugin and fix it if you have the time mate.
Here's the lastest version of the script which works fine for the existing samples at least. Morph files are not supported.
[fmt_SpiderMan2_xbx.zip](https://xentaxbackup.github.io/file/20288_fmt_SpiderMan2_xbx.zip)
## Post #9
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-12T17:10:16+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Bigchillghost ↑Sat Jun 12, 2021 10:22 pm at Sat Jun 12, 2021 10:22 pm
>
> 
Ecelon wrote: ↑Wed Jun 09, 2021 9:23 pmIt works for about half of the models and I was hoping you could take a look at the plugin and fix it if you have the time mate.

Here's the lastest version of the script which works fine for the existing samples at least. Morph files are not supported.

Added bones and skinning info with the bone maps. Indices are bytes and weights normalized ubytes, 4 bones per vertex(at least in the 2 samples I checked, some may have more or less, if that's the case the info is probably located in the submeshInfo header with the other data, didn't check). Also adjusted the winding order of faces.
Parenting info is nowhere to be found though unless I missed something obvious but at least it's easy to fix manually. This info is probably located in the animation file, I saw a few formats doing this.


 fmt_SpiderMan2_xbx.zip
(1.73 KiB) Downloaded 24 times



All credits goes to Bigchillghost obviously, just took a look real quick and added a few lines to his research.
## Post #10
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T17:02:05+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

Can we all do Ben 10: Alien Force: Vilgax Attacks for XBox 360 next?
## Post #11
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2021-06-22T03:56:22+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Bigchillghost ↑Sat Jun 12, 2021 10:22 pm at Sat Jun 12, 2021 10:22 pm
>
> 
Ecelon wrote: ↑Wed Jun 09, 2021 9:23 pmIt works for about half of the models and I was hoping you could take a look at the plugin and fix it if you have the time mate.

Here's the lastest version of the script which works fine for the existing samples at least. Morph files are not supported.

Thank you so much for your help on this awesome plugin mate.

> Reply from Joschka ↑Sun Jun 13, 2021 1:10 am at Sun Jun 13, 2021 1:10 am
>
> 
Bigchillghost wrote: ↑Sat Jun 12, 2021 10:22 pm
Ecelon wrote: ↑Wed Jun 09, 2021 9:23 pmIt works for about half of the models and I was hoping you could take a look at the plugin and fix it if you have the time mate.

Here's the lastest version of the script which works fine for the existing samples at least. Morph files are not supported.


Added bones and skinning info with the bone maps. Indices are bytes and weights normalized ubytes, 4 bones per vertex(at least in the 2 samples I checked, some may have more or less, if that's the case the info is probably located in the submeshInfo header with the other data, didn't check). Also adjusted the winding order of faces.
Parenting info is nowhere to be found though unless I missed something obvious but at least it's easy to fix manually. This info is probably located in the animation file, I saw a few formats doing this.
fmt_SpiderMan2_xbx.zip

All credits goes to Bigchillghost obviously, just took a look real quick and added a few lines to his research.

Heck yeah mate, that's bloody awesomeness, thanks so much. Stupid question, but how would I go about fixing them manually? Import into my program of choice and parent them? Or do I have to do it externally?

Also, sorry for the uber late response, I haven't had access to my pc much over the past few weeks.
## Post #12
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-22T07:31:15+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Ecelon ↑Tue Jun 22, 2021 11:56 am at Tue Jun 22, 2021 11:56 am
>
> 

Heck yeah mate, that's bloody awesomeness, thanks so much. Stupid question, but how would I go about fixing them manually? Import into my program of choice and parent them? Or do I have to do it externally?

Yeah exactly, you just need to import the model in your 3d software and then parent them manually.
## Post #13
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2021-06-24T02:46:21+00:00
- Post Title: [ REQUEST ] XBXM Noesis Plugin:

> Reply from Joschka ↑Tue Jun 22, 2021 3:31 pm at Tue Jun 22, 2021 3:31 pm
>
> 
Ecelon wrote: ↑Tue Jun 22, 2021 11:56 am

Heck yeah mate, that's bloody awesomeness, thanks so much. Stupid question, but how would I go about fixing them manually? Import into my program of choice and parent them? Or do I have to do it externally?


Yeah exactly, you just need to import the model in your 3d software and then parent them manually.

You bloody legend, thank you so much
