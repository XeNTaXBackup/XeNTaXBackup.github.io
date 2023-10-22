## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-26T18:03:11+00:00
- Post Title: Long 3D meshes

Hello, I were checking the files after extraction of this game and trying to get a relation between meshes and textures, there are around 5k-6K textures, so is a hard task, another thing is the meshes some that still seeying compressed, others seems like an objects, and others have skel info, so should be any kind of characters or monster, I'm gonna attach some samples hope someone can get any kind pattern to be able to make a script, because if I try to get every mesh with a hex2obj gonna take much more time, besides I need to find the right texture   . Thank you so much in advance!

[https://www.mediafire.com/file/xolpmlv9 ... S.zip/file](https://www.mediafire.com/file/xolpmlv9k48vj6r/SAMPLES.zip/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-26T21:06:51+00:00
- Post Title: Long 3D meshes

> Reply from moonpaladin ↑Thu Jan 27, 2022 2:03 am at Thu Jan 27, 2022 2:03 am
>
> hope someone can get any kind pattern to be able to make a script, because...mesh format appears to be simple, so why not try to create a script on your own?
.



0000019b-dat.png (69.14 KiB) Viewed 324 times


At 0x10960 sizeOfUvsBlock = 2206x8 +6
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-26T21:30:06+00:00
- Post Title: Long 3D meshes

> Reply from shakotay2 ↑Thu Jan 27, 2022 5:06 am at Thu Jan 27, 2022 5:06 am
>
> 

Thanks shakotay2! Gonna review the values, I were checking the 0000004d.dat and to be honest doesn't seems that it contain a mesh
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-26T23:06:22+00:00
- Post Title: Long 3D meshes

> Reply from moonpaladin ↑Thu Jan 27, 2022 2:03 am at Thu Jan 27, 2022 2:03 am
>
> 
Hello
Ogre?
files that have :"[MeshSerializer_v1.40]"

do you want to RIP all the games that exist? Why do you need this?
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-26T23:33:19+00:00
- Post Title: Long 3D meshes

> Reply from Durik256 ↑Thu Jan 27, 2022 7:06 am at Thu Jan 27, 2022 7:06 am
>
> 
do you want to RIP all the games that exist? Why do you need this?

Thanks Durik!not all the games! xD, is just that sometimes I see a very cool creature or so, and when I download the game  it have around 20k models, so like this case I'm gonna search that one in the ocean of models lol. Thanks again
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-26T23:59:04+00:00
- Post Title: Long 3D meshes

> Reply from Durik256 ↑Thu Jan 27, 2022 7:06 am at Thu Jan 27, 2022 7:06 am
>
> 
Durik! one question, how about the 0000005e.dat and 0000007b.dat, them doesn't have the '[MeshSerializer_v1.40]' but seems that are meshes too, or I'm wrong?   , Im attaching more files like those too, please take a look when you can. ty!   

edit*: btw how can I add another data.find value, in case I found meshes with the value of meshv2, or meshserializer_v3.0? 

[https://www.mediafire.com/file/kjy555od ... s.zip/file](https://www.mediafire.com/file/kjy555odmub4uhj/more_samples.zip/file)
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-27T00:10:11+00:00
- Post Title: Long 3D meshes

> Reply from moonpaladin ↑Thu Jan 27, 2022 7:59 am at Thu Jan 27, 2022 7:59 am
>
> 
meshserializer_v3.0
replace [MeshSerializer_v1.40] >> [meshserializer_v3.0].
functionality is not guaranteed. because the file structure may differ

> Reply from moonpaladin ↑Thu Jan 27, 2022 7:59 am at Thu Jan 27, 2022 7:59 am
>
> 
0000005e.dat and 0000007b.dat
i will check.

you can also use this script to rename all files that have a head "[MeshSerializer_v1.40]".
for example, in (.rip_mesh). 
in the plugin, change .dat >> .rip_mesh too.

```
#your path (subdirectories too)
path = "C:\\SAMPLES\\"

def find_header(file):
    with open(file, "rb") as f:
        data = f.read()
        header = data.find('[MeshSerializer_v1.40]'.encode())
        if header != -1:
            return 1
        else:
            return 0

for root, dirs, files in os.walk(path):
    for file in files:
        without_ext, ext = os.path.splitext(file)
        file_path = os.path.join(root,file)
        if ext == ".dat":
            if find_header(file_path):
                os.rename(file_path, os.path.join(root,without_ext+".rip_mesh"))#your ext
```
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-27T00:13:51+00:00
- Post Title: Long 3D meshes

> Reply from Durik256 ↑Thu Jan 27, 2022 8:10 am at Thu Jan 27, 2022 8:10 am
>
> 
That gonna be really useful!
## Post #9
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-27T00:39:38+00:00
- Post Title: Long 3D meshes

as if I was guessing, there is this type of meshes v1.30 , and they load incorrectly with the script    

[https://www.mediafire.com/file/go58bex8 ... 0.zip/file](https://www.mediafire.com/file/go58bex88zg1v1h/samples_v1.30.zip/file)
## Post #10
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-27T01:54:29+00:00
- Post Title: Long 3D meshes

> Reply from Durik256 ↑Thu Jan 27, 2022 8:10 am at Thu Jan 27, 2022 8:10 am
>
> 
Durik I checked around 2.3k models! sorry for the spam! but here are some models that doesn't load all the submeshes and others that load but doesn't look good   . Thanks for your time   

[https://www.mediafire.com/file/gl8xahrk ... 2.zip/file](https://www.mediafire.com/file/gl8xahrk5odlyjl/samples_2.zip/file)

edit*: still checking the models   

[https://www.mediafire.com/file/6o8l5yjt ... 3.zip/file](https://www.mediafire.com/file/6o8l5yjtoio48f8/samples_3.zip/file)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-27T06:58:55+00:00
- Post Title: Long 3D meshes

> Reply from moonpaladin ↑Thu Jan 27, 2022 7:33 am at Thu Jan 27, 2022 7:33 am
>
> xD, is just that sometimes I see a very cool creature or so, and when I download the game  it have around 20k models, so like this case I'm gonna search that one in the ocean of models lol.Understand.
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-27T07:26:44+00:00
- Post Title: Long 3D meshes

> Reply from moonpaladin ↑Thu Jan 27, 2022 9:54 am at Thu Jan 27, 2022 9:54 am
>
> 
Thanks for your time
replace ([MeshSerializer_v1.40] >>  [MeshSerializer) in script to open all versions

this code is scaring me 

 
edit: ...samples 3\looks blank (dont work)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-27T11:36:40+00:00
- Post Title: Long 3D meshes

Creating general scripts is harder (see "patch" below) than using hex2obj for individual models, that's why I prefer the later:
.



0000425c-rip_mesh.png (82.84 KiB) Viewed 247 times


btw: this is the line with the "suspicious" value (patched for above sample):
    bs.seek(62+16, NOESEEK_REL)
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-27T13:04:19+00:00
- Post Title: Long 3D meshes

> Reply from shakotay2 ↑Thu Jan 27, 2022 7:36 pm at Thu Jan 27, 2022 7:36 pm
>
> 
I didn't want to do this.    

ok, I took a closer look. completely new plugin.  
opens all your problematic models.  

Oops. Not the right archive.. now i think everything 
[fmt_unk.zip](https://xentaxbackup.github.io/file/21685_fmt_unk.zip)
## Post #15
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-27T14:22:37+00:00
- Post Title: Long 3D meshes

> Reply from Durik256 ↑Thu Jan 27, 2022 9:04 pm at Thu Jan 27, 2022 9:04 pm
>
> 
Thank you so much Durik!
## Post #16
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-27T14:23:06+00:00
- Post Title: Re: Long 3D meshes

> Reply from shakotay2 ↑Thu Jan 27, 2022 7:36 pm at Thu Jan 27, 2022 7:36 pm
>
> 
Thanks for the info shakotay!!
## Post #17
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2022-01-27T17:39:03+00:00
- Post Title: Re: Long 3D meshes

Please share game name and site . So that script and researches made by other users could be linked to an existing game.
## Post #18
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-27T18:19:51+00:00
- Post Title: Re: Long 3D meshes

> Reply from Drawing ↑Fri Jan 28, 2022 1:39 am at Fri Jan 28, 2022 1:39 am
>
> 
Please share game name and site . So that script and researches made by other users could be linked to an existing game.
Tân Thiên Long 3D is the name of the game! if you get the filenames please let me know!
## Post #19
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-30T05:45:34+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Thu Jan 27, 2022 9:04 pm at Thu Jan 27, 2022 9:04 pm
>
> 
Hello Durik! it's me again xD! sorry for the pin! but I have reviewed around 14k meshes, so hope this is the last samples*, some meshes crash noesis, others just throw error, and  around 200 + meshes that looks like rectangles, dunno if that is wrong or not, but is a bit suspicious that are many of them. Please take a look when you can /o/. thanks!   

[https://www.mediafire.com/file/6bmialmz ... 4.zip/file](https://www.mediafire.com/file/6bmialmz3k1d068/samples_4.zip/file)
## Post #20
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-30T09:13:54+00:00
- Post Title: Re: Long 3D meshes

> Reply from moonpaladin ↑Sun Jan 30, 2022 1:45 pm at Sun Jan 30, 2022 1:45 pm
>
> 
 and  around 200 + meshes that looks like rectangles
it's grass ????

> Reply from moonpaladin ↑Sun Jan 30, 2022 1:45 pm at Sun Jan 30, 2022 1:45 pm
>
> 
I have reviewed around 14k meshes 
[sss.png](https://xentaxbackup.github.io/file/21697_sss.png)
## Post #21
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-30T14:38:32+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Sun Jan 30, 2022 5:13 pm at Sun Jan 30, 2022 5:13 pm
>
> 
it's grass ???? 
Yep, seems like that, but are many meshes like it xd
## Post #22
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-31T14:04:07+00:00
- Post Title: Re: Long 3D meshes

new plugin, opens all your problematic models.(fmt_mesh.py)
The problem is incorrect unpacking. some models are broken.
The second problem is the Taiwanese language.

I don't know about archives.
but i made an unpacker. with correct file extension and cut trash(96 byte).(fmt_axp.py)
because of the language when unpacking, the names are strange. Noesis does not find the folder.
so I just give new name.

ogre viewer. throws an error due to strange names. if you rename the material or edit the script, then it opens not broken models, but does not find the skeleton due to the same problem.

You can still use the script to rename non-broken models:

> Reply from Durik256 ↑Thu Jan 27, 2022 8:10 am at Thu Jan 27, 2022 8:10 am
>
> 
you can also use this script to rename all files that have a head "[MeshSerializer_v1.40]".
replace ([MeshSerializer_v1.40]>>[MeshSerializer) and (".dat >> ".mesh")

or use the second plugin from the archive so that there is no error when opening broken models.(fmt_mesh2.py)
[long3D_plugin.zip](https://xentaxbackup.github.io/file/21711_long3D_plugin.zip)
## Post #23
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-31T14:53:57+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Mon Jan 31, 2022 10:04 pm at Mon Jan 31, 2022 10:04 pm
>
> 
new plugin, opens all your problematic models.(fmt_mesh.py)
Thanks a lot Durik! really thanks for take your time on doing this !
## Post #24
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-31T15:15:15+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Mon Jan 31, 2022 10:04 pm at Mon Jan 31, 2022 10:04 pm
>
> 

Durik one question! after using the unpacker I got around 7k .dat files, by chance do you know if them contain any kind of mesh file or what could be these files?. Because after checking the meshes I have not found some creatures, so could be that some meshes have not the "[MeshSerializer" header  .
## Post #25
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-31T15:29:46+00:00
- Post Title: Re: Long 3D meshes

> Reply from moonpaladin ↑Mon Jan 31, 2022 11:15 pm at Mon Jan 31, 2022 11:15 pm
>
> 
I got around 7k .dat files,

not all archives contain names at the end, and if the last file does not contain names, then I check the file headers manually (.dds, .png, .tga, .mesh, .skeleton, .xml) all other files will have a .dat extension,  and a file with names too, you can find it and parse and rename files. So .dat can be anything, check in hex editor,
## Post #26
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-31T15:59:17+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Mon Jan 31, 2022 11:29 pm at Mon Jan 31, 2022 11:29 pm
>
> 
Thanks! gonna check all these .dat files
## Post #27
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-31T16:36:22+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Mon Jan 31, 2022 11:29 pm at Mon Jan 31, 2022 11:29 pm
>
> 
Durik after review it, there is a way that these "[Serializer_" files that have skeleton info, have mesh data too? little suspicious that a skel file have a size around 300kb-500kb. As I have been reviewed all the files, there are like sections of characters, others creature, others  mixed, but well Im trying to give it a sequence. So I'm attaching some samples, if these files have any kind of mesh info should look like a creature.  sorry for so much spam   

[https://www.mediafire.com/file/3hvit3qr ... l.zip/file](https://www.mediafire.com/file/3hvit3qr573kms5/dat_files-_skel.zip/file)

edit I had unpacked the model3.axp that weighed 1.3 gigabytes, the strange thing was that there were few meshes, now I just used your script to unpack it, and it seems that it has extracted correctly because I have many .mesh, the problem is that these do not work with your script   (could be that are encrypted)

[https://www.mediafire.com/file/byur6yhe ... s.zip/file](https://www.mediafire.com/file/byur6yhece1re70/model3_samples.zip/file)

edit2Also at unpacked the model3.axp with aluigi script I found this file, seems that this one contains the filenames    

[https://www.mediafire.com/file/yca366vp ... 9.467/file](https://www.mediafire.com/file/yca366vpye22c11/00000b39.467/file)
## Post #28
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-31T18:54:09+00:00
- Post Title: Re: Long 3D meshes

> Reply from moonpaladin ↑Tue Feb 01, 2022 12:36 am at Tue Feb 01, 2022 12:36 am
>
> 
 "[Serializer_"
.skeleton files contain the skeleton and animation

> Reply from moonpaladin ↑Tue Feb 01, 2022 12:36 am at Tue Feb 01, 2022 12:36 am
>
> 
 do not work with your script
I wrote that these are so-called broken files.
specifically, these do not have trash(96 bytes) at the beginning
add in fmt_mesh2.py:

```
if bs.readShort() == 4096:
	return 1
else:
	bs.seek(-2, NOESEEK_REL)
```

after:

```
	bs = NoeBitStream(data)
```

so that when you open there is no message "Detected file type: Unknown"

> Reply from Durik256 ↑Mon Jan 31, 2022 10:04 pm at Mon Jan 31, 2022 10:04 pm
>
> 
or use the second plugin from the archive so that there is no error when opening broken models.(fmt_mesh2.py)

> Reply from moonpaladin ↑Tue Feb 01, 2022 12:36 am at Tue Feb 01, 2022 12:36 am
>
> 
Also at unpacked the model3.axp with aluigi script I found this file, seems that this one contains the filenames
the model3.axp archive contains the filenames at the end. my script unpacks it with the correct extensions using this file.
look inside the script

edit: curiously. after reinstalling the game, all archives had names at the end. before that it was not so. for example, in archive "Model5.axp" file with names was at position 1216
## Post #29
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-31T19:24:01+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Tue Feb 01, 2022 2:54 am at Tue Feb 01, 2022 2:54 am
>
> 
.skeleton files contain the skeleton and animation
Gotcha!

> Reply from Durik256 ↑Tue Feb 01, 2022 2:54 am at Tue Feb 01, 2022 2:54 am
>
> 
I wrote that these are so-called broken files.
so that when you open there is no message "Detected file type: Unknown"
I edited the script and it doesn't throw error, anyways it doesn't load any kind of mesh just look blank  

> Reply from Durik256 ↑Mon Jan 31, 2022 10:04 pm at Mon Jan 31, 2022 10:04 pm
>
> 
edit: curiously. after reinstalling the game, all archives had names at the end. before that it was not so. for example, in archive "Model5.axp" file with names was at position 1216
Did you just reinstall, still doesn't update the game? or click on launcher? maybe at doing that it removes the names
## Post #30
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-31T19:49:49+00:00
- Post Title: Re: Long 3D meshes

> Reply from moonpaladin ↑Tue Feb 01, 2022 3:24 am at Tue Feb 01, 2022 3:24 am
>
> 
Did you just reinstall, still doesn't update the game? or click on launcher? maybe at doing that it removes the names
Yes, I have not launched and never played this game.
Then why only in some archives there was such a problem?

> Reply from moonpaladin ↑Tue Feb 01, 2022 3:24 am at Tue Feb 01, 2022 3:24 am
>
> 
mesh just look blank
well, if you looked inside the script, you would see that it only checks the header and creates an empty model.
(broken files contain incorrect information about the number of triangles, etc.)
of all the files with models, only these open:

```
Model.axp 18878 >> 8480
Model2.axp 3451 >> 659
Model3.axp 2944 >> 15
Model4.axp 2387 >> 0
Model5.axp 1215 >> 508
```


Most likely the problem is in unpacking. you need to solve this problem.
## Post #31
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-31T20:10:07+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Tue Feb 01, 2022 3:49 am at Tue Feb 01, 2022 3:49 am
>
> 
Then why only in some archives there was such a problem?
Most likely the problem is in unpacking. you need to solve this problem.
ohh
## Post #32
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-31T20:49:58+00:00
- Post Title: Re: Long 3D meshes

> Reply from moonpaladin ↑Tue Feb 01, 2022 3:24 am at Tue Feb 01, 2022 3:24 am
>
> 
Did you just reinstall, still doesn't update the game? or click on launcher? maybe at doing that it removes the names
names remain in the same file and are not moved to the end.  

i download your :

> Reply from moonpaladin ↑Wed Jan 26, 2022 7:03 am at Wed Jan 26, 2022 7:03 am
>
> 
Model5.axp
yes files are written to the end of the archive.
befor 1215 files. (names in >> 1216) of which 508 are working
after 1233 files. (names in >> 1216) of which 525 are working

in your archive (Material3.axp)
name in file: 2144.dat
file 1.dat >> indicates which texture belongs to which model???


is this chinese???? only notepad ++ opened correctly / I thought Taiwan
地表草\地表草_05暗.mesh>>Surface Grass\Surface Grass_05 Dark.mesh
## Post #33
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-31T21:03:37+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Tue Feb 01, 2022 4:49 am at Tue Feb 01, 2022 4:49 am
>
> 
Seems that is vietnamese server, and is using the game files of a chinese game called 新天龙八部  

just to note I uploaded these samples after I updated the game and play for a while  


 the  2144.dat contain all the filenames, I'm checking if is ordered
## Post #34
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-31T21:51:32+00:00
- Post Title: Re: Long 3D meshes

> Reply from moonpaladin ↑Tue Feb 01, 2022 5:03 am at Tue Feb 01, 2022 5:03 am
>
> 
game 新天龙八部
you need to say all the information at once.  
[upacker .axp exists.](https://secufiles.com/eNhZ/AXP_Packer.7z)
it also unpacks with broken files. so the problem is not in the archive, but in the models. 

[TLBBMeshViewer](https://code.google.com/archive/p/ogrehavok/downloads) with Chinese language support opens non-broken models with skeleton.

in noesis with my plugin:



mesh_boss.png (17.34 KiB) Viewed 204 times


[ogre-meshviewer](https://github.com/OGRECave/ogre-meshviewer/releases) if replace line 51 in ogre_mesh_viewer.py:

```
lmgr.logWarning("could not find material")#("could not find material '{}'".format(mat.getName()))
```

due to encoding problems does not open the skeleton:

```
Error: Unable to load skeleton 'boss╨┬╠ь═т╕─╘ь╚ю╨б╬х.skeleton' for Mesh 'boss╨а╨Т╨Ь╨╝╨Э╨▓╤С╨Ф╨д╨╝╨Ш╨╛╨а╨О╨Ю╨╡.mesh'.
```
## Post #35
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-31T22:07:56+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Tue Feb 01, 2022 5:51 am at Tue Feb 01, 2022 5:51 am
>
> 
Sorry :'(.  I found the vietnamese  server first  .

> Reply from Durik256 ↑Tue Feb 01, 2022 5:51 am at Tue Feb 01, 2022 5:51 am
>
> 
it also unpacks with broken files. so the problem is not in the archive, but in the models.
oh, this is really weird
## Post #36
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-31T23:16:02+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Tue Feb 01, 2022 5:51 am at Tue Feb 01, 2022 5:51 am
>
> 
Thanks alot for all the info! I have seem that the newest clients have encrypted the new meshes   . Anyways! I'm gonna looking for more info-
## Post #37
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-01T06:19:30+00:00
- Post Title: Re: Long 3D meshes

there is [source code](https://forum.ragezone.com/f857/release-dragon-oath-tlbb-2-a-978841/).
..\TOOLS >> file tools.
maybe there is an encoder?
for example, in AxCryptoMath.cpp  has >> DeCryptoIniFile
## Post #38
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-01T14:18:58+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Tue Feb 01, 2022 2:19 pm at Tue Feb 01, 2022 2:19 pm
>
> 
for example, in AxCryptoMath.cpp  has >> DeCryptoIniFile
edit also the names of the textures and skeleton doesn't match at all, it's like trial and error
## Post #39
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-01T15:06:10+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Tue Feb 01, 2022 2:19 pm at Tue Feb 01, 2022 2:19 pm
>
> 
for example, in AxCryptoMath.cpp  has >> DeCryptoIniFile
Hello Durik! I have asked Ekey too, and he tells me this:

"The data in these files is weird, probably encrypted ~0x80 bytes in header with a static key or a simple algorithm like XOR, cuz data started always with next bytes 84CCFA759A9D3B6D5AE1E83A, except this file > ТЛ№L20090112·Р¦гу+2.mesh"
## Post #40
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-01T18:29:59+00:00
- Post Title: Re: Long 3D meshes

> Reply from moonpaladin ↑Tue Feb 01, 2022 11:06 pm at Tue Feb 01, 2022 11:06 pm
>
> 
data started always with next bytes 84CCFA759A9D3B6D5AE1E83A

some non-broken models too have these 96 bytes(84 CC FA 75...26 E5 1A CE), so this does not apply to encryption.

I think you need to look at the source code :

> Reply from Durik256 ↑Tue Feb 01, 2022 2:19 pm at Tue Feb 01, 2022 2:19 pm
>
> 
in AxCryptoMath.cpp
in this file:

```
/*
chuue: Undecoded Uue code
chasc: decoded binary code
*/
```


I have already deleted all files associated with this game.
here is the archive with the source code from the tools folder. there are references to keys, etc. :

```
	#define BASE_XOR_VALUE	(0x04020626)
	#define BASE_PLUS_VALUE	(0x00970702)
	#define DEF_ENCRYPT_KEY (0x03070201)
```


also i build this solution [PatchWorker.zip](https://drive.google.com/file/d/1MH7jvLjCL_hmr1-GAC_YcCMSvWVGV03g/view?usp=sharing). from attachments
[补丁包制作.zip](https://xentaxbackup.github.io/file/21706_补丁包制作.zip)
## Post #41
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-01T20:34:14+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Wed Feb 02, 2022 2:29 am at Wed Feb 02, 2022 2:29 am
>
> 
I have already deleted all files associated with this game.
oh no :'(

> Reply from Durik256 ↑Wed Feb 02, 2022 2:29 am at Wed Feb 02, 2022 2:29 am
>
> 
also i build this solution PatchWorker.zip. from
Sorry for not understanding, but what would this file be used for?   . Thanks alot for all your effor Durik256!
## Post #42
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-02T20:06:33+00:00
- Post Title: Re: Long 3D meshes

support (.skeleton)

animation structure in xml:

```
    <bones>
        <bone id="0" name="joint1">
            <position x="0" y="0" z="0" />
            <rotation angle="1.5708">
                <axis x="-1" y="0" z="0" />
            </rotation>
        </bone>
        <bone id="1" name="Bip001">
            <position x="-0" y="87.6374" z="-0.012061" />
            <rotation angle="2.09439">
                <axis x="-0.57735" y="-0.57735" z="-0.57735" />
            </rotation>
        </bone>
    </bones>
    <bonehierarchy>
        <boneparent bone="Bip001" parent="joint1" />
    </bonehierarchy>
    <animations>
        <animation name="my_animation" length="0.1">
            <tracks>
                <track bone="Bip001">
                    <keyframes>
                        <keyframe time="0">
                            <translate x="0" y="0" z="0" />
                            <rotate angle="0">
                                <axis x="1" y="0" z="0" />
                            </rotate>
                        </keyframe>
                        <keyframe time="0.033333">
                            <translate x="-0.301643" y="-0.027527" z="2e-006" />
                            <rotate angle="0.00796363">
                                <axis x="0.188198" y="0.0867897" z="0.978289" />
                            </rotate>
                        </keyframe>
                        <keyframe time="0.066667">
                            <translate x="-0.603287" y="-0.055031" z="4e-006" />
                            <rotate angle="0.0159273">
                                <axis x="0.188198" y="0.0867919" z="0.978289" />
                            </rotate>
                        </keyframe>
                        <keyframe time="0.1">
                            <translate x="-0.90493" y="-0.08255" z="6e-006" />
                            <rotate angle="0.023881">
                                <axis x="0.188196" y="0.086792" z="0.978289" />
                            </rotate>
                        </keyframe>
                    </keyframes>
                </track>
            </tracks>
        </animation>
    </animations>
</skeleton>

```

based on it you can add support for animations.
[fmt_skeleton.zip](https://xentaxbackup.github.io/file/21713_fmt_skeleton.zip)
## Post #43
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-03T01:09:56+00:00
- Post Title: Re: Long 3D meshes

weight, mesh and skeleton together  
First of all, it searches for a skeleton by the name specified in the file.
(but since there is a problem with Chinese names). 
If doesn't find skeleton, it searches in the same folder with the same name as the model.

*(if not found then rename model and skeleton using ASCII chars)
=update=
[fmt_mesh.zip](https://xentaxbackup.github.io/file/21723_fmt_mesh.zip)
## Post #44
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-03T02:05:21+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Thu Feb 03, 2022 9:09 am at Thu Feb 03, 2022 9:09 am
>
> 
weight, mesh and skeleton together
Thanks alot Durik256!
## Post #45
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-25T06:30:28+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Thu Feb 03, 2022 9:09 am at Thu Feb 03, 2022 9:09 am
>
> 
Hello Durik! what could be the problem with this .mesh samples? It throw this error, AttributeError: 'int' object has no attribute 'setName'.

What is weird is why in these meshes thrown this error, this part of code "loadMesh(bs)" is returning an int, and mesh with this int value is trying to using a function (setName) that doesn't support?

I think here is the problem  

```
        if bs.readShort() == 10:
            break
        else:
            bs.seek(-1, NOESEEK_REL)
```


samples: [https://www.mediafire.com/file/ve75gvz8 ... s.zip/file](https://www.mediafire.com/file/ve75gvz8v94j5jv/LONG_error_samples.zip/file)
## Post #46
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-05T16:29:02+00:00
- Post Title: Re: Long 3D meshes

> Reply from moonpaladin ↑Fri Feb 25, 2022 2:30 pm at Fri Feb 25, 2022 2:30 pm
>
> 
this error, AttributeError: 'int' object has no attribute 'setName'.
the last subgrid has no vertex. you need to change the plugin so that it checks for this.
a workaround would be to return an empty mesh. replace all 'return 0' >> 'return NoeMesh([],[],"")' in method ''loadMesh()"


(only one model of all did not open)
## Post #47
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-05T21:17:59+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Sun Mar 06, 2022 12:29 am at Sun Mar 06, 2022 12:29 am
>
> 
a workaround would be to return an empty mesh. replace all 'return 0' >> 'return NoeMesh([],[],"")' in method ''loadMesh()"

Hello Durik! thank you very much, this gonna save me a lot of time!
## Post #48
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-05T22:20:15+00:00
- Post Title: Re: Long 3D meshes

> Reply from Durik256 ↑Sun Mar 06, 2022 12:29 am at Sun Mar 06, 2022 12:29 am
>
> 
Durik what could be the problem with some files that throw this error:

sample: [https://www.mediafire.com/file/ic6147ag ... .mesh/file](https://www.mediafire.com/file/ic6147agxoo2qus/%25C2%25B4%25C3%25B3%25C3%2584%25C2%25AE%25C2%25B7%25C2%25BF%25C3%258E%25C3%259D2.mesh/file)

Of course the filename and directory are ok, error appears at the exact moment that read the file in binary mode. Thanks!
