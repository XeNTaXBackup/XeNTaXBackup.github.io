## Post #1
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2021-10-27T02:49:48+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

Hello there!

Some years ago was interested on get the models from the Game Rule of Rose from ps2 i was able to unpack all files with a bms from Aluigi and found that the character models are in i3d format while the textures are just TIM2 Textures but thats the far i could get since i dont have any idea on how to open the i3d files.

Here are a couple of samples from Diana and Clara.

[https://www.mediafire.com/file/iexmwb13 ... a.rar/file](https://www.mediafire.com/file/iexmwb13xjymikq/Diana.rar/file)
[https://www.mediafire.com/file/8pgcfyc5 ... a.rar/file](https://www.mediafire.com/file/8pgcfyc5it1ml6i/clara.rar/file)

Edit: Ok I found that there is already a tool that convert the i3d files into obj files but was wondering if there is a way to get them with their original rig and bones.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-27T13:21:57+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

Noesis script to load the bones in the sample file:


 fmt_RuleOfRose(PS2)_i3d.zip
(846 Bytes) Downloaded 64 times
## Post #3
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2021-10-28T15:48:50+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

Thank you!

The plugin load´s fine the skeleton but did mention to fail to load certain dummy file?

Reading 'E:\TEMP EXT\Rule of Rose\CHARA\Chara\ACTION\dia\dia.mdl\\dummy'...Failed.

By the way the plugin could also support mesh to ? I know i mention to found a tool that load convert the i3d files to obj but would be cool have the models with their original rig if that its not possible just that display the static mesh+skeleton. ^^
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-29T14:57:59+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

> Reply from The Chief ↑Thu Oct 28, 2021 11:48 pm at Thu Oct 28, 2021 11:48 pm
>
> 
Reading 'E:\TEMP EXT\Rule of Rose\CHARA\Chara\ACTION\dia\dia.mdl\\dummy'...Failed.
Don't have that sample.

> Reply from The Chief ↑Thu Oct 28, 2021 11:48 pm at Thu Oct 28, 2021 11:48 pm
>
> 
By the way the plugin could also support mesh to ? I know i mention to found a tool that load convert the i3d files to obj but would be cool have the models with their original rig if that its not possible just that display the static mesh+skeleton. ^^
In fact the meshes are the tedious part to deal with in this format, sorry, just no time for that.
## Post #5
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2021-11-05T16:14:12+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

for anyone wondering you can get the static models with this tool:

[https://github.com/Murugo/Misc-Game-Research](https://github.com/Murugo/Misc-Game-Research)

Im just confused about the instructions some one share:

"You need to install Python and install numpy within that. After you're done, you can simply drag and drop the rpk's into the extractor and drag and drop the mdl files into the mdl2obj.Vertex color and armatures are not yet to be extracted. For environments especially it's the lighting that seems to be baked into vertex color. So we're still missing out on some cool looking shading"

OK Python installed and Numpy but where I should drag and drop the mdl and the rppk files lol ?

There is no .exe file and on command file i get from empty files or errors.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-05T18:48:18+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

Open console window (by executing cmd.exe).

change dir to folder with python.exe and rpk sample, then type 
python rpkextract.py sample.rpk

(Don't have an rpk file (required header: 'RTPK') to test it but should do.)
## Post #7
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2021-11-05T23:39:50+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

Thank you!

But I have this message:

SyntaxError: invalid syntax
>>> python mdl2obj.py dia.mdl
  File "<stdin>", line 1
    python mdl2obj.py dia.mdl


Here I upload some more samples this time on mdl:

[https://www.mediafire.com/file/gb8iq5gf ... s.rar/file](https://www.mediafire.com/file/gb8iq5gf8u4wfih/Samples.rar/file)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-06T05:41:23+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

Use python 3.0 (or above):
.



dia.png (96.57 KiB) Viewed 299 times
## Post #9
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2021-11-07T17:25:44+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

Thanks soI update to 3.10 and was able to drag and drop the main chara file on rpkextract.py so i get all files and you can drag and drop the mdl files in to the rpkextract.py so after unpacking a couple of times you get the i3d files but if i trie to drag and drop the file on the mdl2obj.py i get nothing doing the command line give me an syntax error .

Its python "mdl2obj.py dia.i3d" or python mdl2obj.py dia.i3d ,python (mdl2obj.py dia.i3d) ?

One more I have installed version 3.10 but when i open on cmd python mention version "2.7.15"
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-07T18:53:30+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

In command line you need to change the directory to folder with python.exe, .py file and mdl sample, then type 
python mdl2obj.py dia.mdl
should create dia_out.obj and .mtl file. If you type python and press enter "Python 3.x" should be displayed (x >= 0).

btw: I used blender for displaying dia.obj only - it wasn't involved in that "python extraction process", just in case someone else gets confused
## Post #11
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-12-02T21:12:43+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

> Reply from Bigchillghost ↑Wed Oct 27, 2021 9:21 pm at Wed Oct 27, 2021 9:21 pm
>
> 
Noesis script to load the bones in the sample file:
fmt_RuleOfRose(PS2)_i3d.zip

This one also works with the models from Ape Escape 3 but I only tried two of them.

I am not sure if it works with all of the models from Ape Escape 3 and Ape Escape 2.
[pl_g_nrm.zip](https://xentaxbackup.github.io/file/21338_pl_g_nrm.zip)
## Post #12
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2023-02-12T12:45:11+00:00
- Post Title: Rule of Rose (PS2) i3d File Format

Where do I  put the  pl_g_nrm.zip in what  location  in noesis.
