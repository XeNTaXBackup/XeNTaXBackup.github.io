## Post #1
- Username: yakafan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 13, 2007 12:52 am
- Post datetime: 2007-12-18T19:31:03+00:00
- Post Title: Can anyone help work out file structure of Naruto shape file

Hey people, I'm interested in the Naruto:rise of ninja meshes because I'm working with xbox 360 content in XNA and they look good for references since they're damn near perfect.

I've found out the creators used silo3d for the cage meshes, then 3ds max and zbrush combined to 'sculpt' the models, and exported from max in a custom / propriety format where they wrote a plugin but I'm new to this and you guys are awesome lol  

ign dev blog page: [http://blogs.ign.com/Ubi_Naruto/2007/10/12/68798/](http://blogs.ign.com/Ubi_Naruto/2007/10/12/68798/)
silo3d forums: [http://www.silo3d.com/forum/showthread.php?t=12815](http://www.silo3d.com/forum/showthread.php?t=12815)
modeller's gallery: [http://www.khalys.net/BOOK_2007/Naruto.htm](http://www.khalys.net/BOOK_2007/Naruto.htm)

You can kind of guess the poly count if you look at that guy's other works on the same site  

So I got 3 shape files and I can see there is a good few lines the same on all the files (not sure how long exactly) and definitely lots of bone / joint names in there, and animations right from after the header (raged, neutral, hurt)...it's really confusing as they're different    also there might be some kind of texture name further down but I'm not bothered about textures  

[http://files-upload.com/files/684448/gaara_shape.txt](http://files-upload.com/files/684448/gaara_shape.txt)
[http://files-upload.com/files/684453/haku_shape.txt](http://files-upload.com/files/684453/haku_shape.txt)
[http://files-upload.com/files/684467/kiba_shape.txt](http://files-upload.com/files/684467/kiba_shape.txt)

[http://beta.freedrive.com/member/viewfolder/30808](http://beta.freedrive.com/member/viewfolder/30808)

hope this information helps, i just want to be able to import into any modeller to take a look =) 

there's bone / joint names going down to offset ~9300 / ~2454 hex
(Head, Crotch, Forearm, Finger, Armpit, Cloth ?, Ruban?...)

and 2/3 of the way down the file you got animation names (maybe?), ~270000
(Energy, Rage, Shield, ChakraControl, Haku's mask 'prop')
so they are actions / attacks I think.

I have no idea about offsets in the headers I can't seem to understand it yet, but it doesn't look too hard to figure out for people who know what's what, any help is appreciated and thanks for reading.
