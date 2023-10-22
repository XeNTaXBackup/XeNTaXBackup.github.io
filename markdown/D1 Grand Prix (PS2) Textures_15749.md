## Post #1
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2017-01-16T15:05:12+00:00
- Post Title: D1 Grand Prix (PS2) Textures

Hello everyone. After a little research I've found out the car models of this game are openable in ZModeler 2 in apparently good shape.
The format is .BIN but if renamed as .DFF it becomes importable in ZModeler 2, here's a sample:
[http://www44.zippyshare.com/v/OkEwo71Z/file.html](http://www44.zippyshare.com/v/OkEwo71Z/file.html)

Now, the question is, where are the textures? 
The UV map seems perfect, so only textures are missing. I think these are included in the .BIN file, as a package along with the 3D model, but I'm not sure.
## Post #2
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2017-01-18T17:23:02+00:00
- Post Title: D1 Grand Prix (PS2) Textures

In case needed, here's another sample: it's an unpacked .BIN package:
[http://www110.zippyshare.com/v/R1vYtd4L/file.html](http://www110.zippyshare.com/v/R1vYtd4L/file.html)

I've unpacked it using this aluigi QuickBMS script:

```
get BIN_SIZE asize
for OFFSET = 0 < BIN_SIZE
    get TYPE long
    get SIZE long
    get DUMMY1 short    # 0xf or 0x37
    get DUMMY2 short    # 0x1c02
    if DUMMY2 != 0x1c02
        print "ERROR"
        cleanexit
    endif
    savepos OFFSET
    if TYPE == 0x2
        getdstring NAME SIZE
    elif TYPE >= 0x100
        getdstring DUMMY SIZE
    endif
    if TYPE == 1
        log NAME OFFSET SIZE
        set NAME string ""
        math OFFSET += SIZE
        goto OFFSET
    endif
    savepos OFFSET
next
```
## Post #3
- Username: mea
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 18, 2021 9:18 pm
- Post datetime: 2021-07-30T07:39:55+00:00
- Post Title: D1 Grand Prix (PS2) Textures

2017 sheesh i hope you will see this
anyway i think i found the texture files
they are also saved as .bin format and inside the PACK folder but if u rename them to .txd they will open inside magictxd
then u can just export the textures and you have a ripped model
im gonna take a look at some other models
maybe i can rip everything from this game and then upload it here


ok so .bin has the model and the txd inside of it at the same time
i was able to get the model using the same way mentioned above ( rename to .dff and then import into zmodeler 2 ) and it works
## Post #4
- Username: figureddd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 18, 2022 4:18 pm
- Post datetime: 2022-02-18T08:21:50+00:00
- Post Title: D1 Grand Prix (PS2) Textures

> Reply from mea ↑Fri Jul 30, 2021 3:39 pm at Fri Jul 30, 2021 3:39 pm
>
> 
2017 sheesh i hope you will see this
anyway i think i found the texture files
they are also saved as .bin format and inside the PACK folder but if u rename them to .txd they will open inside magictxd
then u can just export the textures and you have a ripped model
im gonna take a look at some other models
maybe i can rip everything from this game and then upload it here


ok so .bin has the model and the txd inside of it at the same time
i was able to get the model using the same way mentioned above ( rename to .dff and then import into zmodeler 2 ) and it works

Hi mate, did you ever make any progress on this? I'm going to be looking into ripping cars and tracks soon but wanted to know if it's worth doing or not. There's so much content on this game!
## Post #5
- Username: mea
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 18, 2021 9:18 pm
- Post datetime: 2022-04-22T01:58:43+00:00
- Post Title: D1 Grand Prix (PS2) Textures

sorry for late reply
i dont go online very often here

i never went any deeper with the models of this game
there's just too much stuff

but i can tell you how to extract the models:

 you first NEED TO DUPLICATE THE MODEL FILE AND THEN RENAME FROM .bin/.pac TO .DFF then you can import the car models into zmodeler and then export into .obj (sadly zmodeler is going to remove the dummies so the entire car model is going to be merged into one object)

once you import it into 3ds max or blender you first need to remove the blob surrounding the car (its probably for collisions)
then i suggest you start first by applying the textures (the model should be already uv mapped

first you need to open the car model file in magicTXD (duplicate the file and rename its format to .txd)
[https://www.gtagarage.com/mods/show.php?id=27862](https://www.gtagarage.com/mods/show.php?id=27862)
then go Export>Export All>
now just apply the correct texture file for every material (every materials has the texture file name as its material name so this is gonna be easy)

and then after that you can remove the duplicates (they are lod objects i think)
almost every part of the car's body has a 1 or 2 lod objects

oh also MAKE SURE YOU ONLY DELETE THE LOW DETAILED OBJECTS (you know if its lod mesh if you see that its using a low res texture or its lower polygon than other duplicates)

if you're using 3ds max please use the Element selection mode (number 5 on your keyboard) its gonna help you alot



here's an image of some model 



.
.
.




tire models are in the same folder as car models
and extracting them is the same way as extracting car models (the above)

i mean honestly this process isnt hard
but it just takes a lot of time (alot alot of time considering this game has soo much content)

idk how to extract track models and i never tried to
but i've seen someone send a picture of one this game's tracks imported inside of renderware game engine(?)


sorry if you could not understand what i said.  im bad at explaining
## Post #6
- Username: mea
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 18, 2021 9:18 pm
- Post datetime: 2022-10-22T11:45:20+00:00
- Post Title: D1 Grand Prix (PS2) Textures

i ripped the competition cars because some friends liked the liveries from this game and wanted to make livery replicas idk

exported them in obj format
textures in png
and i included renders from 5 sides for every car

some cars might be missed up   
also this only includes the high detailed objects and textures
no lod models

here if anyone needs it    
[https://drive.google.com/file/d/1oXtO4A ... sp=sharing](https://drive.google.com/file/d/1oXtO4Aqu2nB2YV_bvF9OH1lN1tAoVSdX/view?usp=sharing)




843w6768093246780934.jpg (63.61 KiB) Viewed 147 times
## Post #7
- Username: Translunary
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 22, 2022 11:28 am
- Post datetime: 2022-11-11T16:42:47+00:00
- Post Title: D1 Grand Prix (PS2) Textures

were you ever able to rip the tracks from this game? converting the tracks in the PACK folder from .d1 to .txd works for the textures, but converting to a .dff and importing into zmodeler reveals a dome with a handful of triangles, no track to be found.
## Post #8
- Username: mea
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 18, 2021 9:18 pm
- Post datetime: 2022-11-29T12:40:17+00:00
- Post Title: D1 Grand Prix (PS2) Textures

sorry i dont know how to rip track models
## Post #9
- Username: Quore
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 22, 2020 1:45 pm
- Post datetime: 2022-12-09T12:26:14+00:00
- Post Title: D1 Grand Prix (PS2) Textures

> Reply from mea ↑Sat Oct 22, 2022 7:45 pm at Sat Oct 22, 2022 7:45 pm
>
> 
i ripped the competition cars because some friends liked the liveries from this game and wanted to make livery replicas idk

exported them in obj format
textures in png
and i included renders from 5 sides for every car

some cars might be missed up   
also this only includes the high detailed objects and textures
no lod models

here if anyone needs it    
https://drive.google.com/file/d/1oXtO4A ... sp=sharing


843w6768093246780934.jpg
How did you do it? Please tell me? And you can do it only with this game or with any PS2?
## Post #10
- Username: entiteta
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 23, 2023 5:57 pm
- Post datetime: 2023-04-23T09:59:20+00:00
- Post Title: D1 Grand Prix (PS2) Textures

YO DO YOU STILL HAVE THESE I NEED EM BUT ZIPPY SHARE IS DEAD!!!!
