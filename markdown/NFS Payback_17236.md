## Post #1
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-04T00:28:14+00:00
- Post Title: NFS Payback

Greetings.

Got it today pre-ordered and after more than 4h of extraction process, I got all extracted yaay
Actual game files are:

```
21.8 GB (23,422,025,728 bytes)
351 Files, 35 Folders
```
[/i]
And after extraction:

```
35.0 GB (37,661,401,088 bytes)
365,233 Files, 22,414 Folders
```
[/i]

It can be extracted in same manner as any frostbite engine game that uses cat/cas file format.

Now, it does not extract using same bf4 python script as it worked for the NFS16, it has similar file/folder format arrangement as SWBF2, there for more information you can get it already posted here thank you daemon1 for all your hard work.

Keep in mind that it has already a Patch folder with files in it so make sure to enable it in the script.

UPDATE 01 *****************************************************************************************************
After a bit of more investigation seems meshes/textures can not be extracted/converted with the usual tools that are out there and that worked for other NFS frostbite games, there for samples sent out to be tested and also attached in here.

Maybe if daemon1 has some time can take a look and, who knows hehe, magic happens.

[NFSP_sample](https://mega.nz/#!H9VEHa7I!wQs-29hKuUHxxSoeJwQbLBFU5jI8Ks47ZWx8KgE8DuU) / [EBX_sample](https://mega.nz/#!W1FRAB7I!NYqyJccdffMsNVAQ1tDsYiIiStEx8NXMcapHoiaLRuY)

Also, if I try to use the fb3decoder I get the following result after few audio conversions occur:

```
  File "E:\3D Assets Game Geometry\fb3decoder.py", line 576, in <module>
    main()
  File "E:\3D Assets Game Geometry\fb3decoder.py", line 566, in main
    dbx=Dbx(f,relPath)
  File "E:\3D Assets Game Geometry\fb3decoder.py", line 343, in __init__
    inst=self.readComplex(instanceRepeater.complexIndex,f,True)
  File "E:\3D Assets Game Geometry\fb3decoder.py", line 369, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "E:\3D Assets Game Geometry\fb3decoder.py", line 422, in readField
    (typ,length)=numDict[fieldDesc.type]
KeyError: 49709
```


UPDATE 02 *****************************************************************************************************
Well, now we have access to the game assets, for research or what not.




cheers
## Post #2
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-02T10:49:35+00:00
- Post Title: NFS Payback

how did you find out that this chunk file is of this particular Meshset??
I get error while using Fb_SWBF2_mesh.exe, Fb_SWBF_mesh.exe or Fb_BF1_mesh.exe...
i tried these tools on your included sample file..
## Post #3
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-03T00:27:30+00:00
- Post Title: NFS Payback

> Reply from 8thwond3r
>
> how did you find out that this chunk file is of this particular Meshset??
I get error while using Fb_SWBF2_mesh.exe, Fb_SWBF_mesh.exe or Fb_BF1_mesh.exe...
i tried these tools on your included sample file..
And you will continue to have errors because daemon1 never updated them to work with NFSPayback or any other NFS in the series, usually car racing games do not get same love as the hyped games out there such as BF series and now SWBF series.

And for example, NFS Payback .MeshSet files have the following 6 hex sequences in the beginning of the file,

```
FF FF FF FF
```

Once you find them all you will find in front of them the chunks name, for example:
Model: car_acura_nsx_2017_mesh.MeshSet

LODs: 6
LOD: 0, 26BF241C1B3675FCA09D52557B4ADB9D.chunk
LOD: 1, D50CD9C613E5C2B1704CF740B6F3AC87.chunk
LOD: 2, 4E6453E7221C4BA6BA83D411E21DD497.chunk
LOD: 3, 86E2EFE746988101A727C36D28ACD967.chunk
LOD: 4, 51D0F79A71007BCB31211C7FDBA09657.chunk
LOD: 5, F30D41C77C939C74EEFF5904A4762603.chunk
## Post #4
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-03T01:05:24+00:00
- Post Title: NFS Payback

> Reply from mono24
>
> 8thwond3r wrote:how did you find out that this chunk file is of this particular Meshset??
I get error while using Fb_SWBF2_mesh.exe, Fb_SWBF_mesh.exe or Fb_BF1_mesh.exe...
i tried these tools on your included sample file..
And you will continue to have errors because daemon1 never updated them to work with NFSPayback or any other NFS in the series, usually car racing games do not get same love as the hyped games out there such as BF series and now SWBF series.

he said he will take a look, lets see what happens.
BTW, is unwrap 3d working for all meshset files ?
i am not paying 60$ just to convert the meshes..
## Post #5
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-03T01:23:50+00:00
- Post Title: NFS Payback

> Reply from mono24
>
> 8thwond3r wrote:how did you find out that this chunk file is of this particular Meshset??
I get error while using Fb_SWBF2_mesh.exe, Fb_SWBF_mesh.exe or Fb_BF1_mesh.exe...
i tried these tools on your included sample file..
And you will continue to have errors because daemon1 never updated them to work with NFSPayback or any other NFS in the series, usually car racing games do not get same love as the hyped games out there such as BF series and now SWBF series.

And for example, NFS Payback .MeshSet files have the following 6 hex sequences in the beginning of the file,
Code: Select allFF FF FF FF
Once you find them all you will find in front of them the chunks name, for example:
Model: car_acura_nsx_2017_mesh.MeshSet

LODs: 6
LOD: 0, 26BF241C1B3675FCA09D52557B4ADB9D.chunk
LOD: 1, D50CD9C613E5C2B1704CF740B6F3AC87.chunk
LOD: 2, 4E6453E7221C4BA6BA83D411E21DD497.chunk
LOD: 3, 86E2EFE746988101A727C36D28ACD967.chunk
LOD: 4, 51D0F79A71007BCB31211C7FDBA09657.chunk
LOD: 5, F30D41C77C939C74EEFF5904A4762603.chunk

thanks for the info, didn't know low lods' hex are also included in the same meshset file ...
I extracted only from the vehicles0,1,2,3 toc files (2 hours)...which was a bad idea coz i can't find any LOD0 chunks. Looks like I have to dump all the toc files in the directory...Well, this is going to take a minute
## Post #6
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-03T01:56:03+00:00
- Post Title: NFS Payback

> Reply from 8thwond3r
>
> he said he will take a look, lets see what happens.
BTW, is unwrap 3d working for all meshset files ?
i am not paying 60$ just to convert the meshes..
UPDATE/CORRECTION: Now the plugin also has an option to import externally a .ebx skeleton file for the characters in NFSPayback or some cars that have them. also supports every mesh asset from the NFS frostbite games such as:
Need For Speed The Run (2011)
Need For Speed Rivals (2013)
Need For Speed 2016
Need For Speed Payback (2017)

> Reply from mono24
>
> Meshes ONLY, and it will never be updated to support anything else for that matter, textures need to be placed manually one by one and that ONLY if you can find the right tool to get them to .dds, and it supports any .dds you throw at it, so far I found none to support NFSP.
Also, if daemon1 or anyone else who knows what to change,  can make or update an ebx2txt converter so we can use the proper information with in ebx to place the wheels tires brakes and such in the right 3d space, it could be awesome, until then, we just look and stare at the mesh/chunks lol.

BTW, the plugin for Unwrap3D has a feature where you can import a .xml file with required info from the EBX file and all wheels tires brakes and such get imported in to place, I bought it because its stable, multitude of formats including Frostbite3 games.
posted EBX sample in first post as well to convert for those that can help
Also for those who are curious if theyre extraction process went as correct as possible (I have doubts every asset gets extracted but anyway), after second patch of the game the sizes are as follows:
after patch #2

```
25.0 GB (26,928,377,856 bytes)
344 Files, 35 Folders
```

after extraction

```
37.0 GB (39,777,431,552 bytes)
371,287 Files, 22,595 Folders
```
[/i]
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-03T07:15:11+00:00
- Post Title: NFS Payback

heres you car and cop. As I said, all games are different, but only a little.
If you tell me default human skeleton name, i'll change it, now its walrus_humanmale.ebx as in SWBF2.
For car, use car's skeleton name parameter (if you even need the skeleton)



i posted ebx2txt and also sound convertor somewhere in my frostbyte thread
[Fb_NFSPB_mesh.rar](https://xentaxbackup.github.io/file/13635_Fb_NFSPB_mesh.rar)
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-03T08:39:06+00:00
- Post Title: NFS Payback

as for textures, try texture converters from SWBF
let me know if they dont work, i'll support them

beware, models here have 4 UV pairs
## Post #9
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-07T04:27:13+00:00
- Post Title: NFS Payback

> Reply from daemon1
>
> i posted ebx2txt and also sound convertor somewhere in my frostbyte thread
Those never worked for NFSP.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-07T15:51:56+00:00
- Post Title: NFS Payback

> Reply from mono24
>
> daemon1 wrote:i posted ebx2txt and also sound convertor somewhere in my frostbyte thread
Those never worked for NFSP.

i posted specific convertor for NFSP audio.
also i know for sure ebx2txt worked with it, because i converted some NFSP EBX files myself
## Post #11
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-08T00:19:01+00:00
- Post Title: NFS Payback

> Reply from daemon1
>
> mono24 wrote:daemon1 wrote:i posted ebx2txt and also sound convertor somewhere in my frostbyte thread
Those never worked for NFSP.

i posted specific convertor for NFSP audio.
also i know for sure ebx2txt worked with it, because i converted some NFSP EBX files myself
OK, I will search for them again and try them once more.

By the way, you managed to look at the samples I sent in PM, it seems they also have messed up heads, sent full sample few days ago, let me know if you could get them if not I will resend it, there is no rush of course only when ever you can, just wanted to know if you got them.

UPDATE:
Tried them again as last time, for the audio still gives error, unless you do a folder at a time and avoid what ever the errors are
But ebx2text still nothing as ive mentioned in the other thread nothing but 615 lines of the following:

```
Unknown field type: 49709 File name: 
```

then followed by this error

```
  File "D:\NFSP_dump\ebxtotext.py", line 422, in <module>
    main()
  File "D:\NFSP_dump\ebxtotext.py", line 45, in main
    createGuidTable()
  File "D:\NFSP_dump\ebxtotext.py", line 62, in createGuidTable
    dbx=Dbx(f,relPath)
  File "D:\NFSP_dump\ebxtotext.py", line 241, in __init__
    self.instances.append( (instanceGUID,self.readComplex(instanceRepeater.complexIndex,f,True)) )
  File "D:\NFSP_dump\ebxtotext.py", line 264, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "D:\NFSP_dump\ebxtotext.py", line 274, in readField
    field.value=self.readComplex(fieldDesc.ref,f)
  File "D:\NFSP_dump\ebxtotext.py", line 264, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "D:\NFSP_dump\ebxtotext.py", line 274, in readField
    field.value=self.readComplex(fieldDesc.ref,f)
  File "D:\NFSP_dump\ebxtotext.py", line 264, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "D:\NFSP_dump\ebxtotext.py", line 271, in readField
    field=Field(fieldDesc,f.tell())
MemoryError
```
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-08T15:51:53+00:00
- Post Title: NFS Payback

> Reply from mono24
>
> By the way, you managed to look at the samples I sent in PM
yes i got them

about EBX, ok, i only tried that on a few audio EBX sent to me by someone. So if it fails on others, i need to look at that later.
## Post #13
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-08T16:05:02+00:00
- Post Title: NFS Payback

> Reply from daemon1
>
> yes i got them
Does that mean included samples have all the required info to have same facefix tool for the characters as well?
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-08T16:23:28+00:00
- Post Title: NFS Payback

> Reply from mono24
>
> daemon1 wrote:yes i got them
Does that mean included samples have all the required info to have same facefix tool for the characters as well?
no i didnt check whats inside
## Post #15
- Username: enter
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 06, 2018 4:28 pm
- Post datetime: 2018-01-06T08:46:01+00:00
- Post Title: NFS Payback

hi guys i have a big problem i'm new with ripping games stuff and i like to ask about the NFS PayBack mesh tool, so i dumped the full game with this tool ( UFBE_0_2.exe ) and everything ok, but when i try to use the mesh tool ( Fb_NFSPB_mesh.exe ) it make 2 files one .ascii and one .smd but the problem is the 2 files have 0KB and when i try to import them with this 2 tools for blender like you suggest in the tutorial ( XNALaraMesh(1.7.3).zip / blender_source_tools_2.9.1.zip ) nothing happens with SMD file and gives me error with Ascii file.

so what i'm doing wrong can someone help please.
## Post #16
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-06T23:39:09+00:00
- Post Title: Re: NFS Payback

> Reply from enter
>
> so what i'm doing wrong can someone help please.
First of all, the UFBE_0_2 does NOT support the game or any other games from frostbite list for that matter except SWBF 1 / 2 and Battlefield 1, that is why you get errors, the extraction messes things up, also the tool only supports DATA folder of the games NOT the Update/Patch folders.

The only way for now to extract the game fully is by using the python script of SWBF2beta that I posted in first post of this thread.
After you delete your extraction and try the script to dump it all again use the mesh_tool again by daemon1 and should work.
## Post #17
- Username: enter
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 06, 2018 4:28 pm
- Post datetime: 2018-01-07T03:46:52+00:00
- Post Title: Re: NFS Payback

> Reply from mono24
>
> First of all, the UFBE_0_2 does NOT support the game or any other games from frostbite list for that matter except SWBF 1 / 2 and Battlefield 1, that is why you get errors, the extraction messes things up, also the tool only supports DATA folder of the games NOT the Update/Patch folders.

The only way for now to extract the game fully is by using the python script of SWBF2beta that I posted in first post of this thread.
After you delete your extraction and try the script to dump it all again use the mesh_tool again by daemon1 and should work.

i can't find the SWBF2beta script in first post of this thread, i'm really new to this i hope you can help me, and i will promise not bothering you again because i know the beginner are pain in the ass.
## Post #18
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-07T06:10:44+00:00
- Post Title: Re: NFS Payback

> Reply from enter
>
> i can't find the SWBF2beta script in first post of this thread, i'm really new to this i hope you can help me, and i will promise not bothering you again because i know the beginner are pain in the ass.
Do not worry, your not bothering me, I am as a beginner as you are, I simply had lots of trial and error and I remember what it works and what to try, no one taught me, yet had to diligently read and re-read and researched and gather all possible information I could find out there.

Let's begin:

-if you already have python installed version 32bit 2.7.3 and up, then disregard step 1:

Step1: download the latest 2.7 32bit python [https://www.python.org/ftp/python/2.7.1 ... 2.7.14.msi](https://www.python.org/ftp/python/2.7.14/python-2.7.14.msi)
NOTE-if you have installed version 3.x.x you MUST uninstall it because it wont work, only works with python 32bit 2.7.3 and up, not 3.x.x.
Step2: now that your python is nicely installed download the following:


 NFS_P_dump.zip
I attached my script I used and i edited after I tested it thoroughly and it work with out errors (of course its the beta one created by daemon1 (24.25 KiB) Downloaded 215 times


Step3: extract NFS_P_dump.zip anywhere you like:
-right click on NFSP_dump.py and click on Edit with IDLE
-a python IDLE window will pop up
Step4: in that opened window edit ONLY the following lines, in the beginning of the file (as I mentioned I already edited so you wont have to edit other than the correct paths)

```
targetDirectory     = r"X:\YOUR PATH\NFSP_dump"
```

make sure that 

```
targetDirectory
```

is NOT same drive/HDD where the game is installed to avoid other errors like read/write erros and other potential errors, and also to speed up process, you can extract the game like that in one hour or less depending on your PC specs of course in some cases it can take hours, anyway.
-so make sure X on bf4Directory is where your game is installed and correct path to it
-while X on targetDirectory is the other drive/HDD where you want to extract the game with the correct path of your choosing
NOTE:-for instance mine looked like this;

```
targetDirectory     = r"E:\3D Assets Game Geometry\NFSP_dump"
```

there for yours needs to look different once you edit it with correct paths
Step5:-now after correcting the paths, while still on that window opened hit F5 on your keyboard if a pop up shows up to save click OK then another window will open and extraction should begin, just sit back and let it run you will know when its done when nothing else happens and at the end of the window extraction you will see

```
>>>
```

remember it takes a loooong time, hours

have fun, cheers
## Post #19
- Username: enter
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 06, 2018 4:28 pm
- Post datetime: 2018-01-07T06:50:58+00:00
- Post Title: Re: NFS Payback

mono24 i really can't thank you enough for your kindness, i will try it but i'm sure it will work perfectly.
## Post #20
- Username: enter
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 06, 2018 4:28 pm
- Post datetime: 2018-01-07T12:48:34+00:00
- Post Title: Re: NFS Payback

Hello i need to ask you one more time, did i have done something wrong? i did exactly like you said but i still get this problems
photo: [https://ibb.co/kq7Wgb](https://ibb.co/kq7Wgb)

maybe i don't know how to use the mesh tool, can you explain how can i use it the right way, if that not to much to ask for, and thank you again.

EDIT: Nevermind bro i figured out, thank you so much for your help. ( the problem was the car needs skeleton and without it will never make the mesh file )
## Post #21
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-07T23:59:59+00:00
- Post Title: Re: NFS Payback

> Reply from enter
>
> EDIT: Nevermind bro i figured out, thank you so much for your help. ( the problem was the car needs skeleton and without it will never make the mesh file )
Glad it worked out, but what are you using for the mesh extraction? in your posted picture it sais "frostbite_faceposer".
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-08T06:26:31+00:00
- Post Title: Re: NFS Payback

> Reply from mono24
>
> enter wrote:EDIT: Nevermind bro i figured out, thank you so much for your help. ( the problem was the car needs skeleton and without it will never make the mesh file )
Glad it worked out, but what are you using for the mesh extraction? in your posted picture it sais "frostbite_faceposer".
its an internal name for same program i used to make all mesh and face tools for frostbite
## Post #23
- Username: enter
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 06, 2018 4:28 pm
- Post datetime: 2018-01-08T08:46:02+00:00
- Post Title: Re: NFS Payback

mono24 it's like what daemon1 said.

So guys i have a big problem with the quality of the model and the textures:

1. the quality:
I know why the model doesn't have a good quality, because when you export the model with a very small scale then when you try to import the models on any program you will find that the model mesh it's kinda messy and bubbly, so can you guys edit the mesh tool to generate the car with bigger scale so we can fix this messy bubbly mesh problem.
The following picture explain the problem more


2. The Textures:
a. When i convert the textures with this tool ( Batch_Itexture_Converter_SWBF2.exe ) i have a problem which is the tool doesn't convert all textures correctly some textures get damaged
The following picture explain the problem more


b. The model does not have the same textures names, i think the mesh tool generating a new names for the textures.
The following picture explain the problem more


so i have a question after all that i use 3dsimEd to convert Forza cars, so i'm asking if it possible to you guys to make a plugin for that program so we can open the .meshset files on it, like i do with .carbin and .modelbin files.

Thanks guys for your help, cheers.
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-08T12:13:41+00:00
- Post Title: Re: NFS Payback

1. i have no idea whats your problem with mesh, it must be loaded in any program correctly. If your program loads it incorrect, this is a problem of that program.

2. black textures are not damaged, they are probably DX10.

3. its not easy to get texture names from frostbite engine, you need to use a lot of files and links between them to get texture names, so this is not supported in my tool. There are not so many textures, you should be able to apply them manually.

4. i'm not going to make any plugins for 3rd party programs
## Post #25
- Username: enter
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 06, 2018 4:28 pm
- Post datetime: 2018-01-08T12:26:32+00:00
- Post Title: Re: NFS Payback

> Reply from daemon1
>
> 1. i have no idea whats your problem with mesh, it must be loaded in any program correctly. If your program loads it incorrect, this is a problem of that program.

For the mesh i use this tool ( XPS .mesh.ascii importer for Blender ) from this tutorial [https://sta.sh/04jxcv9d9o0](https://sta.sh/04jxcv9d9o0)
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-08T12:33:22+00:00
- Post Title: Re: NFS Payback

> Reply from enter
>
> daemon1 wrote:1. i have no idea whats your problem with mesh, it must be loaded in any program correctly. If your program loads it incorrect, this is a problem of that program.

For the mesh i use this tool ( XPS .mesh.ascii importer for Blender ) from this tutorial https://sta.sh/04jxcv9d9o0

it works for SWBF1/2 and all other games because they use standard frostbite normals for smoothing. NFS is using something else.
## Post #27
- Username: enter
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 06, 2018 4:28 pm
- Post datetime: 2018-01-08T12:39:59+00:00
- Post Title: Re: NFS Payback

> it works for SWBF1/2 and all other games because they use standard frostbite normals for smoothing. NFS is using something else

Then no hope of fixing this issue, WOW that will take so much time to fix, i think i will wait the gamemodels guys to upload there cars, but thank you so much man for your help.
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-08T13:23:56+00:00
- Post Title: Re: NFS Payback

> Reply from enter
>
> Then no hope of fixing this issue, WOW that will take so much time to fix,

I dont know how long it will take, i'll deal with it someday.
Because now EA decided to do ALL their games on frostbite, so you can expect all new NFS games to have this. And those DX10 textures. Be ready.
## Post #29
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-08T17:38:54+00:00
- Post Title: Re: NFS Payback

> Reply from enter
>
> 1. the quality:
I know why the model doesn't have a good quality, because when you export the model with a very small scale then when you try to import the models on any program you will find that the model mesh it's kinda messy and bubbly, so can you guys edit the mesh tool to generate the car with bigger scale so we can fix this messy bubbly mesh problem.
Did you perform that in 3DSmax just as to apply a smooth option?

> Reply from enter
>
> 2. The Textures:
a. When i convert the textures with this tool ( Batch_Itexture_Converter_SWBF2.exe ) i have a problem which is the tool doesn't convert all textures correctly some textures get damaged
You have a couple of options out of the many out there that are simple to use:


 DDS_Converter.rar
Option 1, a simple conversion,where you can change in what format by editing the ctex_c.bat with desired extension, default is PNG,you can use JPG, TIF, etc (139.59 KiB) Downloaded 93 times


Option 2 a bit more fancy one that can be used on many games:
[DDS_Converter-6712-3-0](https://mega.nz/#!PxNyQD5J!OngfpsdFs6ykN5i1qol4Qlkm5t8w5YtJD_SNp1LG_90)
## Post #30
- Username: enter
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 06, 2018 4:28 pm
- Post datetime: 2018-01-08T20:31:13+00:00
- Post Title: Re: NFS Payback

> Did you perform that in 3DSmax just as to apply a smooth option?
yes

And about the textures tools you provide they are just for dds textures, i need a tool can convert from .Texture to .DDS and it must be have a chunks option too, because if the tool does not have the chunks option it will not work anyway.
## Post #31
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-08T21:28:43+00:00
- Post Title: Re: NFS Payback

> Reply from enter
>
> Did you perform that in 3DSmax just as to apply a smooth option?
yes
Interesting, I performed same thing, convert it in to poly, then apply the smooth option, the result does not change one bit, while your result is crisp, unless I am missing something

> Reply from enter
>
> And about the textures tools you provide they are just for dds textures, i need a tool can convert from .Texture to .DDS and it must be have a chunks option too, because if the tool does not have the chunks option it will not work anyway.
Well, I figured that's the only issue your having, because those batch texture converters get the DDSs out of the chunks with the correct header, doesn't mean they all can be previewed/opened by known tools/soft, that's where those tools come in, they get those damaged DDS textures and converts them to readable formats.
## Post #32
- Username: enter
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 06, 2018 4:28 pm
- Post datetime: 2018-01-08T22:03:07+00:00
- Post Title: Re: NFS Payback

> Reply from mono24
>
> Interesting, I performed same thing, convert it in to poly, then apply the smooth option, the result does not change one bit, while your result is crisp, unless I am missing something
you need to apply edit poly modifier on top of the editable mesh, because the smoothing modifier does not work with editable mesh but the problem is that not all the car parts have the same amount of smoothing and you will lose all your UV maps too.

and i tried the textures tools but still no luck, just black color nothing else.
## Post #33
- Username: othanb7
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 09, 2018 7:23 am
- Post datetime: 2018-02-10T08:56:26+00:00
- Post Title: Re: NFS Payback

How to FIX Like this ? went i click F5 and then like this   

NB > I use WIndows 7 64 Bit

Please Help Me for Ripped NFS Payback Models  
[Untitled.png](https://xentaxbackup.github.io/file/13894_Untitled.png)
## Post #34
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-11T00:22:10+00:00
- Post Title: Re: NFS Payback

> Reply from othanb7
>
> How to FIX Like this ? went i click F5 and then like this
Make sure you uninstall first your 64bit of Python and install 32bit version 2.7.3 and up,
because LZ77.dll is 32 built and there for does not support 64bit,
you can definitely use latest version, I use it all the time and it works well.
https://www.python.org/ftp/python/2.7.1 ... 2.7.14.msi

NOTE:
Try to avoid long names for your directories because you can encounter other errors.
try to at least shorten the location for the extraction in something like this:

```
targetDirectory     = r"D:\NFSP_dump"
```

And use another HDD, NOT same HDD where the game is installed, to avoid other errors.
## Post #35
- Username: othanb7
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 09, 2018 7:23 am
- Post datetime: 2018-02-11T08:08:01+00:00
- Post Title: Re: NFS Payback

Ok Bro its Done and Work  but the file format is .ebx how to change format .ebx to 3d models ?
[Untitled.png](https://xentaxbackup.github.io/file/13899_Untitled.png)
## Post #36
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-11T21:24:33+00:00
- Post Title: Re: NFS Payback

> Reply from othanb7
>
> Ok Bro its Done and Work  but the file format is .ebx how to change format .ebx to 3d models ?
Damn, does anyone know how to read now a days? All info is available already, just requires for you or anyone else, you know, to actually read it, not trying to be mean here, just saying.

You can not "change" .ebx to models, those are binary text files that are meant for other things like converting audios or extracting transforms for some game assets, bone/skeleton information, etc etc etc.

Go in to res folder and over there you'll find the file formats that will need the .chunk files from the chunks folder.
more available info is here [viewtopic.php?f=16&t=17114](http://forum.xentax.com/viewtopic.php?f=16&t=17114)
including tutorials and tools, all you gotta do so pay attention and inform yourself, even if examples are for another game they all work the same.

I will be away for few days so I wont be able to help much.
## Post #37
- Username: streetracer23
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 28, 2014 8:51 pm
- Post datetime: 2018-02-25T12:16:55+00:00
- Post Title: Re: NFS Payback

Hi all ! I unpacked game and have 2 folders bundles and chunks , what next ? i read tread at battlefront and dont understend what next / / /
## Post #38
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-25T22:48:03+00:00
- Post Title: Re: NFS Payback

> Reply from streetracer23
>
> Hi all ! I unpacked game and have 2 folders bundles and chunks , what next ? i read tread at battlefront and dont understend what next / / /
If you go back and pay close attention you'll see its all there.
In the attachment for the Battlefront game you'll also find Fb_NFSPB_mesh.exe and you do same procedure as explained, to convert the meshes, and its also attached here on first page by daemon1.
## Post #39
- Username: streetracer23
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 28, 2014 8:51 pm
- Post datetime: 2018-02-27T09:50:57+00:00
- Post Title: Re: NFS Payback

Fb_NFSPB_mesh.exe crashed conwertion car_audi_r8v10_2016_headlights_seta_mesh . How fix it ? i convert meshes car from RES folder only
## Post #40
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-27T14:26:35+00:00
- Post Title: Re: NFS Payback

> Reply from streetracer23
>
> Fb_NFSPB_mesh.exe crashed conwertion car_audi_r8v10_2016_headlights_seta_mesh . How fix it ? i convert meshes car from RES folder only
As daemon1 already stated, you need to grab any skeleton.ebx file that the game has and rename it walrus_humanmale.ebx from the EBX folder, and the conversion will start, because its hardcoded to support hat name only.
if you'd look on first page where he posted you'd see.
## Post #41
- Username: streetracer23
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 28, 2014 8:51 pm
- Post datetime: 2018-03-17T10:07:59+00:00
- Post Title: Re: NFS Payback

Hi ! please take screenshot UFBE at nfs pb before unpacking, i dont understend where add ticks at program
## Post #42
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-03-18T01:32:27+00:00
- Post Title: Re: NFS Payback

> Reply from streetracer23
>
> Hi ! please take screenshot UFBE at nfs pb before unpacking, i dont understend where add ticks at program
You said you already have the game extracted and files are in two folders, bundles and chunks so all you need to do is use daemon1's tool to convert meshes.
For ease of use make a batch file like this in a text editor like Notepad or Notepad++:

```
for %%a IN (*.MeshSet) do Fb_NFSPB_mesh.exe "%%a"
```

save it as example: Fb_NFSPB_meshCONV.bat
now copy it inside a car folder you want to convert, with Fb_NFSPB_mesh.exe
and also  make sure you have a skeleton.ebx renamed to walrus_humanmale.ebx
for example I used:
car_beck_kustomsf132_1932_suspensionf_skeleton.ebx and renamed it to walrus_humanmale.ebx.
Any skeleton will work.
so once you have in your car folder all these three files:
Fb_NFSPB_meshCONV.bat
Fb_NFSPB_mesh.exe
walrus_humanmale.ebx
all you have to do is double click on Fb_NFSPB_meshCONV.bat and conversion will begin.
## Post #43
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2018-06-13T21:13:46+00:00
- Post Title: Re: NFS Payback

When i try to use the fb3decoder.py I get the following result after few audio conversions occur:

```
veh_gear_shift_classic_down.ebx
veh_gear_shift_classic_up.ebx
veh_gear_shift_performance_down.ebx
veh_gear_shift_performance_up.ebx
veh_gear_shift_race_down.ebx
veh_gear_shift_race_up.ebx
veh_gear_shift_sport_down.ebx
veh_gear_shift_sport_up.ebx
veh_gear_shift_stock_down.ebx
veh_gear_shift_stock_up.ebx
nfs18_carhorn.ebx
playerhorn_baseconfig.ebx
veh_horn_audi_a4_0_dualtone_420hz-480hz.ebx

Traceback (most recent call last):
  File "C:\Users\Utente\Desktop\ebx\fb3audio_nfs.py", line 550, in <module>
    main()
  File "C:\Users\Utente\Desktop\ebx\fb3audio_nfs.py", line 548, in main
    dbx.decode()
  File "C:\Users\Utente\Desktop\ebx\fb3audio_nfs.py", line 500, in decode
    decodePcm(currentChunkName, target, 0)
  File "C:\Users\Utente\Desktop\ebx\fb3audio_nfs.py", line 75, in decodePcm
    xas.swapEndianPcm(chunkPath, target, samplesOffset)
NameError: global name 'xas' is not defined
```


Anyone can help me please?
## Post #44
- Username: raven154
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 10, 2018 4:25 am
- Post datetime: 2018-08-10T20:46:52+00:00
- Post Title: Re: NFS Payback

> Reply from mono24
>
> streetracer23 wrote:Hi ! please take screenshot UFBE at nfs pb before unpacking, i dont understend where add ticks at program
You said you already have the game extracted and files are in two folders, bundles and chunks so all you need to do is use daemon1's tool to convert meshes.
For ease of use make a batch file like this in a text editor like Notepad or Notepad++:
Code: Select allfor %%a IN (*.MeshSet) do Fb_NFSPB_mesh.exe "%%a"
save it as example: Fb_NFSPB_meshCONV.bat
now copy it inside a car folder you want to convert, with Fb_NFSPB_mesh.exe
and also  make sure you have a skeleton.ebx renamed to walrus_humanmale.ebx
for example I used:
car_beck_kustomsf132_1932_suspensionf_skeleton.ebx and renamed it to walrus_humanmale.ebx.
Any skeleton will work.
so once you have in your car folder all these three files:
Fb_NFSPB_meshCONV.bat
Fb_NFSPB_mesh.exe
walrus_humanmale.ebx
all you have to do is double click on Fb_NFSPB_meshCONV.bat and conversion will begin.

car_beck_kustomsf132_1932_suspensionf_skeleton.ebx... in what folder is, detailed...
## Post #45
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-08-10T21:40:59+00:00
- Post Title: Re: NFS Payback

> Reply from raven154
>
> car_beck_kustomsf132_1932_suspensionf_skeleton.ebx... in what folder is, detailed...
That was just an example I used, there are many others you can use, simply go at the root of "ebx" folder and search for "skel" and see what it comes up, then you pick any of them and you rename it accordingly and that's it.
## Post #46
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-01-22T17:42:53+00:00
- Post Title: Re: NFS Payback

Hello;

The textures problem is resolved; but I've got a problem with Fb_NFSPB_mesh.exe i.e., this:

[https://www.dropbox.com/s/t13z5v96rjjmn ... e.jpg?dl=0](https://www.dropbox.com/s/t13z5v96rjjmniz/Immagine.jpg?dl=0)

I'm trying to extract the 2017 Acusa NSX (just fro try), and, the files .ascii and .smd are 0Kb, obv.

Help!
## Post #47
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-23T02:13:59+00:00
- Post Title: Re: NFS Payback

> Reply from Fiammanera628
>
> but I've got a problem with Fb_NFSPB_mesh.exe
[viewtopic.php?p=138712#p138712](http://forum.xentax.com/viewtopic.php?p=138712#p138712)
## Post #48
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-01-23T06:25:28+00:00
- Post Title: Re: NFS Payback

> Reply from mono24
>
> Fiammanera628 wrote:but I've got a problem with Fb_NFSPB_mesh.exe
viewtopic.php?p=138712#p138712

Ok, but wich of these .ebx I have to rename 

[https://www.dropbox.com/s/ootnd82rabau0 ... 1.jpg?dl=0](https://www.dropbox.com/s/ootnd82rabau0in/Immagine1.jpg?dl=0)
[https://www.dropbox.com/s/tyfe5rkgyjlli ... 2.jpg?dl=0](https://www.dropbox.com/s/tyfe5rkgyjlli8x/Immagine2.jpg?dl=0)
[https://www.dropbox.com/s/7l8uj7v4qvh0p ... 3.jpg?dl=0](https://www.dropbox.com/s/7l8uj7v4qvh0pjq/Immagine3.jpg?dl=0)

I try to rename "car_acura_nsx_2017_mesh.ebx" with "walrus_humanmale.ebx" and run the Fb_NFSPB_meshCONV.bat; but nothing changed (I have 0Kb .ascii and 0Kb .smd yet).
## Post #49
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-24T00:00:59+00:00
- Post Title: Re: NFS Payback

> Reply from Fiammanera628
>
> I try to rename "car_acura_nsx_2017_mesh.ebx" with "walrus_humanmale.ebx" and run the Fb_NFSPB_meshCONV.bat; but nothing changed (I have 0Kb .ascii and 0Kb .smd yet).
It clearly states, it works ONLY with SKELETON ebx not just any random ebx, read one more time, SKELETON, ONLY SKELETONS work!!!
It doesn't matter if its the main skeleton from the SWBFII game, if you have the game that is, it doesn't matter if its a skeleton from the actual game NFSP of a character/car/bird/tree or what ever, as long as its a SKELETON renamed to walrus_humanmale.ebx



sample.png (229.58 KiB) Viewed 186 times


And after your done converting then importing your mesh in your desired software, just delete the generated skeleton and that's it.
## Post #50
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-01-24T09:49:07+00:00
- Post Title: Re: NFS Payback

ok, calm down...   I try with "car_astonmartin_db5_1964_suspensionf_setdgxa_skeleton.ebx", and renamed "walrus_humanmale.ebx"; it seems to work (I haven't got the 0Kb .ascii and 0Kb .smd, now).

Ok, it works!

So, I resolved also a little problem with textures.

thank you for help
## Post #51
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-25T03:49:30+00:00
- Post Title: Re: NFS Payback

> Reply from Fiammanera628
>
> ok, calm down...
No need for me to be calm, when I already am calm, I marked it clearly so others will see it too, don't worry your NOT the only one not seeing it. 

> Reply from Fiammanera628
>
> So, I resolved also a little problem with textures.
What kind of a problem?
## Post #52
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-01-25T09:10:28+00:00
- Post Title: Re: NFS Payback

> Reply from mono24
>
> No need for me to be calm, when I already am calm, I marked it clearly so others will see it too, don't worry your NOT the only one not seeing it.

Ah ok!   

> Reply from mono24
>
> What kind of a problem?

(the problem was understand how to see the DX12 textures)

BUT

I don't resolved it completely, indeed. I've got a little problem with UV mapping:
[https://www.dropbox.com/s/5rhqd4uk539m7 ... 4.jpg?dl=0](https://www.dropbox.com/s/5rhqd4uk539m7i5/Immagine4.jpg?dl=0)

I open the .ascii file of this Lamborghini Diablo; do you think the .smd file is better for the UV mapping?
## Post #53
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-26T00:37:07+00:00
- Post Title: Re: NFS Payback

> Reply from Fiammanera628
>
> I open the .ascii file of this Lamborghini Diablo; do you think the .smd file is better for the UV mapping?
Lot of them are screwed up, it is what it is.
You'll have to work around it, there are far too many issues everywhere on so many games we use what we have.
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-26T06:15:00+00:00
- Post Title: Re: NFS Payback

> Reply from Fiammanera628
>
> I've got a little problem with UV mapping:
this is not an issue
this file is for another car, not for this one
## Post #55
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-01-26T08:14:47+00:00
- Post Title: Re: NFS Payback

> Reply from daemon1
>
> Fiammanera628 wrote:I've got a little problem with UV mapping:
this is not an issue
this file is for another car, not for this one

Really?   But I'me sure I've open the Diablo files... is the ebx of the skeleton the problem  Because I used the "car_astonmartin_db5_1964_suspensionr_setorxa_skeleton.ebx" then renamed to "walrus_humanmale.ebx".

Or is something else?
## Post #56
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-26T10:25:42+00:00
- Post Title: Re: NFS Payback

no, the problem is texture file
this texture is NOT for this car
## Post #57
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-01-26T15:35:44+00:00
- Post Title: Re: NFS Payback

> Reply from daemon1
>
> no, the problem is texture file
this texture is NOT for this car

Wait I give you the files that I found on the "Texture" foldier...

[https://www.dropbox.com/sh/7uu9qwlcsxfa ... IcWQa?dl=0](https://www.dropbox.com/sh/7uu9qwlcsxfax5s/AAAz5lfwwefQbqQS3mnKIcWQa?dl=0)
## Post #58
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-03-10T17:39:41+00:00
- Post Title: Re: NFS Payback

Hello, after a lot of time, I'm re-trying to extract 3d models from NFS Payback... but this time, I've ripped the VW Golf premium from Deluxe version of Payback (with Ninja Ripper).

No problem with the model (i think), but it is sill with the textures: on .obj files are like this:
[https://www.dropbox.com/s/kumnwxssp2lgi ... e.jpg?dl=0](https://www.dropbox.com/s/kumnwxssp2lgiud/Immagine.jpg?dl=0)
while with original Ninja Ripper .rip files are like this:
[https://www.dropbox.com/s/1l4kh2d9ows7k ... 2.jpg?dl=0](https://www.dropbox.com/s/1l4kh2d9ows7krs/Immagine2.jpg?dl=0) (like this only with the back of car, because I tried to correct the UV mapping)
and I don't know how to correct this.

I'm trying to correct the wrap of the car right now.

And the UV map coincides with the model.

Help pls
## Post #59
- Username: Kenzisto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 05, 2019 5:45 am
- Post datetime: 2019-04-05T11:02:37+00:00
- Post Title: Re: NFS Payback

> Reply from Fiammanera628 ↑Thu Jan 24, 2019 5:49 pm at Thu Jan 24, 2019 5:49 pm
>
> 
ok, calm down...   I try with "car_astonmartin_db5_1964_suspensionf_setdgxa_skeleton.ebx", and renamed "walrus_humanmale.ebx"; it seems to work (I haven't got the 0Kb .ascii and 0Kb .smd, now).

Ok, it works!

So, I resolved also a little problem with textures.

thank you for help

High guys I'm new here. 
I'm ripping VW golf gti clubsport but some how can't find any skeleton File for it. Just to be sure can I use any cars skeleton eg Aston Martin to get ASCII and smd files for the GTi ? I keep getting 0kb files and fb_nfspb_mesh.exe crashes. Meshset ebx and tool are in same folder. Help
## Post #60
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-05T14:13:43+00:00
- Post Title: Re: NFS Payback

> Reply from Kenzisto ↑Fri Apr 05, 2019 7:02 pm at Fri Apr 05, 2019 7:02 pm
>
> Just to be sure can I use any cars skeleton
Yes, any, literally any skeleton will work regardless what its for, character/car/birdy you name it, as long as its renamed accordingly.
## Post #61
- Username: Kenzisto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 05, 2019 5:45 am
- Post datetime: 2019-04-06T09:15:46+00:00
- Post Title: Re: NFS Payback

> Reply from mono24 ↑Fri Apr 05, 2019 10:13 pm at Fri Apr 05, 2019 10:13 pm
>
> 
Kenzisto wrote: ↑Fri Apr 05, 2019 7:02 pmJust to be sure can I use any cars skeleton
Yes, any, literally any skeleton will work regardless what its for, character/car/birdy you name it, as long as its renamed accordingly.

alright i managed to get that ASCII and SMD files ectracted properly thanks   

however i ran into this problem when getting the DDS textures. the tool crashes when attempting to convert the first texture.

sorry for the long error message on attachment
[Capture.PNG](https://xentaxbackup.github.io/file/15999_Capture.PNG)
## Post #62
- Username: Kenzisto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 05, 2019 5:45 am
- Post datetime: 2019-04-11T11:29:19+00:00
- Post Title: Re: NFS Payback

I've imported the GOLF but some parts are missing E.g: bumpers boots lights wheel exhaust basically every custormizable part is missing. how can i fix this
[Capture.PNG](https://xentaxbackup.github.io/file/16020_Capture.PNG)
## Post #63
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-16T16:51:48+00:00
- Post Title: Re: NFS Payback

> Reply from Kenzisto ↑Sat Apr 06, 2019 5:15 pm at Sat Apr 06, 2019 5:15 pm
>
> i ran into this problem when getting the DDS textures. the tool crashes when attempting to convert the first texture.
That tool was never updated to work for the NFSP game, your out of luck regarding textures for the game. Or you can try Frosty Tool Suite.

> Reply from Kenzisto ↑Thu Apr 11, 2019 7:29 pm at Thu Apr 11, 2019 7:29 pm
>
> 
I've imported the GOLF but some parts are missing E.g: bumpers boots lights wheel exhaust basically every custormizable part is missing. how can i fix this
The file is correct, that's what's exported from that file alone, the rest of the parts are in the main folder for each vehicle in the customization subfolder and need to be converted one by one, they are multiple for al customizations possible for that specific vehicle.
## Post #64
- Username: Ezekiel
- Rank: beginner
- Number of posts: 37
- Joined date: Mon Jan 25, 2016 4:18 am
- Post datetime: 2019-06-15T21:05:18+00:00
- Post Title: Re: NFS Payback

I want to thank again daemon1 and mono24 for hard work,
## Post #65
- Username: DHR
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2019-06-16T05:56:09+00:00
- Post Title: Re: NFS Payback

> Reply from Ezekiel ↑Sun Jun 16, 2019 5:05 am at Sun Jun 16, 2019 5:05 am
>
> 
I want to thank again daemon1 and mono24 for hard work,

That's fine, but we prefer you to click the "thanks" button on posts that you want to thank the author for. It's the little thumbs-up icon next to the quote button.
## Post #66
- Username: Ezekiel
- Rank: beginner
- Number of posts: 37
- Joined date: Mon Jan 25, 2016 4:18 am
- Post datetime: 2019-06-16T09:39:14+00:00
- Post Title: Re: NFS Payback

sorry, My post was about to ask for some help, but it turned out like a bump...


So I have problem again with few objects, 

Fb_NFSPB_mesh keep crashing and giving me ASCI 0 KB files sometimes.
You guys said that we need to change skeleton to walrus, but the mesh I want to convert does not contain skeleton.ebx


 joshua_tree.rar
(78.62 KiB) Downloaded 19 times


Can anyone take a look at this, maybe it's there but I can't identify

Thanks.
## Post #67
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-06-16T22:46:19+00:00
- Post Title: Re: NFS Payback

> Reply from Ezekiel ↑Sun Jun 16, 2019 5:39 pm at Sun Jun 16, 2019 5:39 pm
>
> 
You guys said that we need to change skeleton to walrus, but the mesh I want to convert does not contain skeleton.ebx
Go back and trace your steps closely, and pay attention, as I've mentioned ANY skeleton will do, only few items with in each Frostbite games have actual skeleton, some skeletons are used across multiple assets, now your sample doesn't have a specific skeleton in order to be converted, just use same skeleton renamed that you used before on files that worked.

I currently do not have any of the files extracted to test stuff myself.
## Post #68
- Username: Ezekiel
- Rank: beginner
- Number of posts: 37
- Joined date: Mon Jan 25, 2016 4:18 am
- Post datetime: 2019-06-17T09:02:23+00:00
- Post Title: Re: NFS Payback

yeah, you were right chief, any of them skeletons are fine..
so glad I resolved this quick, thought no one gone reply since it's old theme..
Big Thanks
## Post #69
- Username: DHR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jul 01, 2019 6:10 am
- Post datetime: 2019-06-30T22:46:21+00:00
- Post Title: Re: NFS Payback

I am extracting my game, but could someone please assist me to obtain sound files? I only need 180sx and s15 sound files please.
## Post #70
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-01T04:46:15+00:00
- Post Title: Re: NFS Payback

> Reply from DHR ↑Mon Jul 01, 2019 6:46 am at Mon Jul 01, 2019 6:46 am
>
> ...but could someone please assist me to obtain sound files?
[https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)
## Post #71
- Username: DHR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jul 01, 2019 6:10 am
- Post datetime: 2019-07-01T14:16:27+00:00
- Post Title: Re: NFS Payback

> Reply from mono24 ↑Mon Jul 01, 2019 12:46 pm at Mon Jul 01, 2019 12:46 pm
>
> 
DHR wrote: ↑Mon Jul 01, 2019 6:46 am...but could someone please assist me to obtain sound files?
https://github.com/NicknineTheEagle/Frostbite-Scripts

I somehow got the fbdecoder to work, but it only extracts a few audio files and it ends like this
## Post #72
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-01T16:14:42+00:00
- Post Title: Re: NFS Payback

> Reply from DHR ↑Mon Jul 01, 2019 10:16 pm at Mon Jul 01, 2019 10:16 pm
>
> I somehow got the fbdecoder to work, but it only extracts a few audio files...
Use link I posted for the recent and better support of the scripts, it has full audio and car sounds support in their native format with out decoding them to wav/mp3.
The script your using is deprecated and no full audio support among other things.
Delete everything and start from scratch using the new scripts.

good luck
## Post #73
- Username: DHR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jul 01, 2019 6:10 am
- Post datetime: 2019-07-02T00:30:13+00:00
- Post Title: Re: NFS Payback

> Reply from mono24 ↑Tue Jul 02, 2019 12:14 am at Tue Jul 02, 2019 12:14 am
>
> 
DHR wrote: ↑Mon Jul 01, 2019 10:16 pmI somehow got the fbdecoder to work, but it only extracts a few audio files...
Use link I posted for the recent and better support of the scripts, it has full audio and car sounds support in their native format with out decoding them to wav/mp3.
The script your using is deprecated and no full audio support among other things.
Delete everything and start from scratch using the new scripts.

good luck

I keep getting this

"Python 2.7.14 (v2.7.14:84471935ed, Sep 16 2017, 20:19:30) [MSC v.1500 32 bit (Intel)] on win32
Type "copyright", "credits" or "license()" for more information.
>>> 
======== RESTART: E:\Games\NFS Payback\AUdio\frostbite3\ebxtoasset.py ========
Loading GUID table...

Traceback (most recent call last):
  File "E:\Games\NFS Payback\AUdio\frostbite3\ebxtoasset.py", line 31, in <module>
    ebx.loadGuidTable(dumpDirectory)
  File "E:\Games\NFS Payback\AUdio\frostbite3\ebx.py", line 34, in loadGuidTable
    f=open(os.path.join(dumpFolder,"guidTable.bin"),"rb")
IOError: [Errno 2] No such file or directory: 'E:\\Games\\NFS Payback\\AUdio\\frostbite3\\New\\guidTable.bin'
>>> "
## Post #74
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-02T04:42:52+00:00
- Post Title: Re: NFS Payback

> Reply from DHR ↑Tue Jul 02, 2019 8:30 am at Tue Jul 02, 2019 8:30 am
>
> I keep getting this

"Python 2.7.14 (v2.7.14:84471935ed, Sep 16 2017, 20:19:30) [MSC v.1500 32 bit (Intel)] on win32
...



Check again, start over! Capture.JPG (116.68 KiB) Viewed 71 times
## Post #75
- Username: DHR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jul 01, 2019 6:10 am
- Post datetime: 2019-07-02T12:13:08+00:00
- Post Title: Re: NFS Payback

> Reply from mono24 ↑Tue Jul 02, 2019 12:42 pm at Tue Jul 02, 2019 12:42 pm
>
> 
DHR wrote: ↑Tue Jul 02, 2019 8:30 amI keep getting this

"Python 2.7.14 (v2.7.14:84471935ed, Sep 16 2017, 20:19:30) [MSC v.1500 32 bit (Intel)] on win32
...
Capture.JPG

Still the same, even on newest python as well as this
## Post #76
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-02T15:34:06+00:00
- Post Title: Re: NFS Payback

You didn't pay attention, start over means erase everything and dump again with the new scripts, otherwise it cant find the needed files, the new scripts are handling the game assets the correct way while the old ones didn't, that is why you'll end up getting a bunch of errors,  start over.
And to avoid other errors use last version of Python 3.
## Post #77
- Username: DHR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jul 01, 2019 6:10 am
- Post datetime: 2019-07-03T00:00:31+00:00
- Post Title: Re: NFS Payback

> Reply from mono24 ↑Tue Jul 02, 2019 11:34 pm at Tue Jul 02, 2019 11:34 pm
>
> 
You didn't pay attention, start over means erase everything and dump again with the new scripts, otherwise it cant find the needed files, the new scripts are handling the game assets the correct way while the old ones didn't, that is why you'll end up getting a bunch of errors,  start over.
And to avoid other errors use last version of Python 3.

It ended with this error.


When I use ebxtoasset it extacts them but not correcrty, they don't end in .wav but rather in .gin or .sps

I can extact the .gin using nfs_snd_decoders, which are old, but some of the sounds are messed up with it. Tried using ealayer3 for .sps but unssucessful. Any advice?
## Post #78
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-03T03:26:59+00:00
- Post Title: Re: NFS Payback

> Reply from DHR ↑Wed Jul 03, 2019 8:00 am at Wed Jul 03, 2019 8:00 am
>
> When I use ebxtoasset it extacts them but not correcrty, they don't end in .wav but rather in .gin or .sps
As I've mentioned already in a prior message, the new scripts extract ACTUAL audio in their native encoded form by the developers, with out being decoded, GIN are car sounds, SPS are rest of the game sounds/audio/music etc, they are NOT decoded to mp3/wav which is what we want in first place because of old decoders do a not so great job in playing/converting them, but since now are better supported, researched and reversed, you need to use foobar2000/vgmstream in order to play them accordingly.

What the script does is, goes through the EBXs that have AUDIO in them, and they point to required RESs, and they contain needed headers and duration and other info for the actual CHUNK data, and the script stiches them correctly while also giving them the correct names located in the EBXs.
This is an example of how EBXs for AUDIO look inside, for example this one is  GIN car sound.

```
	$::SoundDataAsset
		$::Asset
			$::DataContainer
			Name Audio/Cars/CarEngine/Mazda_RX7/OctaneData/Mazda_RX7_Decel2_Reversed_EXH_Noise_RX
		PrimePriority 0
		RequestPriority 0
		Chunks::SoundDataChunk-Array
			member(0)::SoundDataChunk
				ChunkId 162e088c-0db3-d397-0750-5e2d24e7d9b0
				ChunkSize 106188
		Policy Audio/System/AudioSystem_NFS16/cf108490-62d0-45d2-9237-5b072337417d
	MinRpm 0
	MaxRpm 0
	SampleRate 0
	LengthS 0.0

```

OctaneAsset tells us its a GIN sound, and we know that because it has a SoundDataAsset, that has a actual name, and it goes to a ChunkId with its accurate size, and if you look that ChunkId up in the CHUNKS folder, assuming you dumped the game correctly, you can grab that CHUNK and add a GIN extension and play it just fine in mentioned software/plugin

And also, how do you guys come up with al these errors it baffles me, literally, if you own the legit game, update and everything and use current script the way its mentioned, NO errors occur, AT ALL, just saying.
Did you dump the game from scratch as I've mentioned?
## Post #79
- Username: DHR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jul 01, 2019 6:10 am
- Post datetime: 2019-07-03T11:13:27+00:00
- Post Title: Re: NFS Payback

> Reply from mono24 ↑Wed Jul 03, 2019 11:26 am at Wed Jul 03, 2019 11:26 am
>
> 
DHR wrote: ↑Wed Jul 03, 2019 8:00 amWhen I use ebxtoasset it extacts them but not correcrty, they don't end in .wav but rather in .gin or .sps
As I've mentioned already in a prior message, the new scripts extract ACTUAL audio in their native encoded form by the developers, with out being decoded, GIN are car sounds, SPS are rest of the game sounds/audio/music etc, they are NOT decoded to mp3/wav which is what we want in first place because of old decoders do a not so great job in playing/converting them, but since now are better supported, researched and reversed, you need to use foobar2000/vgmstream in order to play them accordingly.

What the script does is, goes through the EBXs that have AUDIO in them, and they point to required RESs, and they contain needed headers and duration and other info for the actual CHUNK data, and the script stiches them correctly while also giving them the correct names located in the EBXs.
This is an example of how EBXs for AUDIO look inside, for example this one is  GIN car sound.
Code: Select allOctaneAsset 9130dd40-5457-e75b-5f09-81c9ae5dfa30
	$::SoundDataAsset
		$::Asset
			$::DataContainer
			Name Audio/Cars/CarEngine/Mazda_RX7/OctaneData/Mazda_RX7_Decel2_Reversed_EXH_Noise_RX
		PrimePriority 0
		RequestPriority 0
		Chunks::SoundDataChunk-Array
			member(0)::SoundDataChunk
				ChunkId 162e088c-0db3-d397-0750-5e2d24e7d9b0
				ChunkSize 106188
		Policy Audio/System/AudioSystem_NFS16/cf108490-62d0-45d2-9237-5b072337417d
	MinRpm 0
	MaxRpm 0
	SampleRate 0
	LengthS 0.0

OctaneAsset tells us its a GIN sound, and we know that because it has a SoundDataAsset, that has a actual name, and it goes to a ChunkId with its accurate size, and if you look that ChunkId up in the CHUNKS folder, assuming you dumped the game correctly, you can grab that CHUNK and add a GIN extension and play it just fine in mentioned software/plugin

And also, how do you guys come up with al these errors it baffles me, literally, if you own the legit game, update and everything and use current script the way its mentioned, NO errors occur, AT ALL, just saying.
Did you dump the game from scratch as I've mentioned?

I get this with foobar
## Post #80
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-03T21:55:07+00:00
- Post Title: Re: NFS Payback

> Reply from DHR ↑Wed Jul 03, 2019 7:13 pm at Wed Jul 03, 2019 7:13 pm
>
> I get this with foobar

> Reply from DHR ↑Wed Jul 03, 2019 7:13 pm at Wed Jul 03, 2019 7:13 pm
>
> 
mono24 wrote: ↑Wed Jul 03, 2019 11:26 am...you need to use foobar2000/vgmstream in order to play them accordingly.
DHR wrote: ↑Wed Jul 03, 2019 7:13 pm
mono24 wrote: ↑Wed Jul 03, 2019 11:26 am...in mentioned software/plugin...
## Post #81
- Username: DHR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jul 01, 2019 6:10 am
- Post datetime: 2019-07-06T15:37:51+00:00
- Post Title: Re: NFS Payback

Man I am sorry but I literally understand none of this? Do I even have the right program, could you please just give me a link to it? Where is this software/plugin even.

Also, if it's not secret what happened to the sk3tch f4b thread?
## Post #82
- Username: wahxd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 18, 2019 10:39 pm
- Post datetime: 2019-08-18T17:40:41+00:00
- Post Title: Re: NFS Payback

Hey guys, I'm new to this stuff, but i saw that you guys didn't post a fix for the textures, which i might have just gotten a solution, which the way i did it was i used UFBE_0_2.exe, and i had extracted NFSP through that, which gives you the normal .Texture files, however with the python extraction (Page 3), i had gotten .DX12Texture files, which I'm not sure of how to open and or use, but you can just replace the .DX12Texture
with the .Texture files obtained from UFBE.exe, and use those as a texture replacement for the .DX12Texture. Hope it helps someone! 
[UFBE_0_2.rar](https://xentaxbackup.github.io/file/16615_UFBE_0_2.rar)
## Post #83
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-19T00:00:03+00:00
- Post Title: Re: NFS Payback

> Reply from wahxd ↑Mon Aug 19, 2019 1:40 am at Mon Aug 19, 2019 1:40 am
>
> ...you guys didn't post a fix for the textures, which I might have just gotten a solution...
It is just a type error as it is found in many python scripts, all you had to do is rename/edit yourself the python script in any txt editor or inside the IDLE python window, from this:

```
0x6BDE20BA = Dx12Texture
```

to this

```
0x6BDE20BA = Texture
```

Assuming that's the correct hash in front of it, otherwise maybe it was a wrong named extension for the wrong hash.
But even so, to date DX12Texture does not exist in any Frostbite game.
You should have posted direct link to where UFBE was initially posted not attach it.
## Post #84
- Username: wahxd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 18, 2019 10:39 pm
- Post datetime: 2019-08-20T21:37:09+00:00
- Post Title: Re: NFS Payback

> Reply from mono24 ↑Mon Aug 19, 2019 8:00 am at Mon Aug 19, 2019 8:00 am
>
> 
...It is just a type error as it is found in many python scripts, all you had to do is rename/edit yourself the python script...Oh alright, thanks for that, is there any possible way to extract ONLY the texture files then? without all the Meshsets and others included?
## Post #85
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-21T04:18:03+00:00
- Post Title: Re: NFS Payback

> Reply from wahxd ↑Wed Aug 21, 2019 5:37 am at Wed Aug 21, 2019 5:37 am
>
> ...is there any possible way to extract ONLY the texture files...
No, it is NOT possible to extract textures only since its dependent on both EBXs and CHUNKs, I'm sure a proficient dev can modify a python script to make it happen, but with what exists currently is impossible.
Your best bet though, to get only required/needed textures and no other unnecessary data is to use Frosty Tool Suite: [https://frostytoolsuitedev.gitlab.io/](https://frostytoolsuitedev.gitlab.io/)

good luck
## Post #86
- Username: wahxd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 18, 2019 10:39 pm
- Post datetime: 2019-08-24T12:39:16+00:00
- Post Title: Re: NFS Payback

> Reply from mono24 ↑Wed Aug 21, 2019 12:18 pm at Wed Aug 21, 2019 12:18 pm
>
> 
...your best bet though, to get only required/needed textures and no other unnecessary data is to use Frosty Tool Suite...
Sucks that the tool only exports one at a time, but could you not also just use the normal .texture files from the UFBE extraction tool too?
## Post #87
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-25T02:22:03+00:00
- Post Title: Re: NFS Payback

> Reply from wahxd ↑Sat Aug 24, 2019 8:39 pm at Sat Aug 24, 2019 8:39 pm
>
> Sucks that the tool only exports one at a time...
As the Frosty dev specified, numerous and numerous times, the Frosty Tool Suite is designed for modding NOT for mass extraction, and will NEVER support mass extraction not even multiple files at once, its main purpose is to edit one file at a time for modding creation only.

> Reply from wahxd ↑Sat Aug 24, 2019 8:39 pm at Sat Aug 24, 2019 8:39 pm
>
> but could you not also just use the normal .texture files from the UFBE extraction tool too?
I have no clue as to what your exact question is?
With UFBE you can only dump the entire game to use any proper files, be it textures/meshes/sounds etc.
## Post #88
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-10-15T17:36:54+00:00
- Post Title: Re: NFS Payback

Hello,

I've got a little issue with NFS Payback with Ninjaripper: because when I want to rip the game of a car without damage, is perfect, but when i want to rip a car WITH DAMAGES, it rip the car like it hasn't got any damages

With car damages I mean like this:
[https://www.dropbox.com/s/09toxly0j9q24fm/0243.jpg?dl=0](https://www.dropbox.com/s/09toxly0j9q24fm/0243.jpg?dl=0)

Someone can hepl me, please?
## Post #89
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2020-11-18T21:21:37+00:00
- Post Title: Re: NFS Payback

I don't suppose anyone has found the Lina Navarro mesh and textures in there?
As in Dominique Tipper from The Expanse?
## Post #90
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-11-18T22:44:06+00:00
- Post Title: Re: NFS Payback

I looked as well for that character when i had game unpacked, and i found that there isn't one in the assets, only in the cinematic videos.
## Post #91
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2020-11-19T00:26:16+00:00
- Post Title: Re: NFS Payback

> Reply from mono24 ↑Thu Nov 19, 2020 6:44 am at Thu Nov 19, 2020 6:44 am
>
> 
I looked as well for that character when i had game unpacked, and i found that there isn't one in the assets, only in the cinematic videos.

Bugger! How typical! 
Thanks though. You've saved me buying the game just for her model.
## Post #92
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-11-21T02:10:35+00:00
- Post Title: Re: NFS Payback

> Reply from Spartan019 ↑Thu Nov 19, 2020 8:26 am at Thu Nov 19, 2020 8:26 am
>
> Bugger! How typical!
Actually all characters in-game are there, i got confused about the names since i haven't dealt with Frostbite games in a very long time, sorry about that, so yeah you can definitely get a copy and gain access to the characters, except if your familiar with the engine, all faces are messed up and this particular game doesn't have a tool for it to fix them.
## Post #93
- Username: AreanLee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 06, 2021 10:26 am
- Post datetime: 2021-03-16T01:53:06+00:00
- Post Title: Re: NFS Payback

> Reply from enter ↑Mon Jan 08, 2018 4:46 pm at Mon Jan 08, 2018 4:46 pm
>
> 
a. When i convert the textures with this tool ( Batch_Itexture_Converter_SWBF2.exe ) i have a problem which is the tool doesn't convert all textures correctly some textures get damaged
The following picture explain the problem more

Hey how you doing,

             So I was trying to extract the texture with "Batch_Itexture_Converter_SWBF2" but I dont think it support DX12TEXTURE, what should I do?
## Post #94
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-03-17T00:35:01+00:00
- Post Title: Re: NFS Payback

> Reply from AreanLee ↑Tue Mar 16, 2021 9:53 am at Tue Mar 16, 2021 9:53 am
>
> So I was trying to extract the texture with "Batch_Itexture_Converter_SWBF2" but I dont think it support DX12TEXTURE, what should I do?
That tool does NOT extract anything, it merely converts between one format to another, and there is no such thing as "DX12TEXTURE", currently there's no proper tool that can convert new frostbite games and their textures entirely and/or correctly, there for not much or anything you can do at the moment.
