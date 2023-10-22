## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-08-25T17:51:50+00:00
- Post Title: Blast Games Ltd. .geo file

Dug up some old games again and came upon this .geo file from little brittain PC
thought it was a very generic /common kind of .geo files from the 2000s
so i tried some converters online but failed :-/
could yall guys please have a look at this? i just hope its something simple.


 ball.zip
.geo File from the game (2.73 KiB) Downloaded 17 times
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-25T18:28:21+00:00
- Post Title: Blast Games Ltd. .geo file

> Reply from Henchman800 ↑Sat Aug 26, 2023 1:51 am at Sat Aug 26, 2023 1:51 am
>
> so i tried some converters online but failed :-/"Converters online" is different from "online converters", is it?

Anyways, the ball is simple enough:
.



ball-geo.png (47.94 KiB) Viewed 88 times
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2023-08-26T02:02:12+00:00
- Post Title: Blast Games Ltd. .geo file

Maxscript for 3dsmax

```
Maxscript to import ball.geo 3d file
written by mariokart64n
August 25 2023
*/

-- Release an file locks from windows
gc()

-- clear the console
clearListener()

-- set widget variable
try(destroyDialog impgeo)catch(impgeo)

-- creates a widget
rollout impgeo "impGeo" (
    
    -- read function / main function
    fn read file = (
        
        -- Checks input is valid
        if file != undefined and file != "" do (
            
            -- Attempt to open file
            local f = try(fopen file "rb")catch(undefined)
            if f != undefined then (
                
                -- Read Header
                fseek f 0x0C #seek_set
                fseek f (readLong f #unsigned) #seek_set
                fseek f (readLong f #unsigned) #seek_set
                fseek f 0x08 #seek_cur
                fseek f (readLong f #unsigned) #seek_set
                fseek f 0x08 #seek_cur
                
                -- Read Mesh Info
                local vert_addr = readLong f #unsigned
                local face_addr = readLong f #unsigned
                fseek f 0x1C #seek_cur
                local vert_count = readLong f #unsigned
                fseek f 0x24 #seek_cur
                local face_count = readLong f #unsigned
                
                -- Read Texture
                fseek f 0x0C #seek_set
                fseek f (readLong f #unsigned) #seek_set
                fseek f (readLong f #unsigned) #seek_set
                fseek f 0x0C #seek_cur
                fseek f (readLong f #unsigned) #seek_set
                fseek f (readLong f #unsigned) #seek_set
                local texture_file = readString f
                
                -- Read Geometry
                local v = 1
                local vertArray = #()
                local tvertArray = #()
                local normArray = #()
                local faceArray = #()
                
                fseek f vert_addr #seek_set
                for v = 1 to vert_count do (
                    append vertArray [readFloat f, readFloat f, readFloat f]
                    append normArray [readFloat f, readFloat f, readFloat f]
                    readLong f #unsigned -- Color
                    append tvertArray [readFloat f, 1.0 - (readFloat f), 0.0]
                    )
                
                fseek f face_addr #seek_set
                for v = 1 to (face_count / 3) do (
                    append faceArray ([readShort f #unsigned, readShort f #unsigned, readShort f #unsigned] + 1)
                    faceArray[faceArray.count] = [faceArray[faceArray.count][1], faceArray[faceArray.count][3], faceArray[faceArray.count][2]]
                    )
                
                -- Release File
                fclose f
                
                -- Build Mesh
                delete $*
                local msh = mesh vertices:vertArray faces:faceArray tverts:tvertArray
                msh.name = uniqueName (getFilenameFile texture_file)
                msh.material = StandardMaterial()
                msh.material.diffuseMap = Bitmaptexture fileName:((getFilenamePath file) + texture_file)
                showTextureMap msh.material on
                msh.wireColor = random white black
                select msh
                
                -- Apply UV's
                buildTVFaces msh
                for v = 1 to faceArray.count do (setTVFace msh v faceArray[v])
                
                -- Apply Normals
                local i = 1, ii = 1
                setCommandPanelTaskMode #modify
                for i = 1 to msh.numfaces do setFaceSmoothGroup msh i 1
                local normID = #{}
                local normMod = Edit_Normals()
                addmodifier msh normMod ui:off
                normMod.selectBy = 1
                normMod.displayLength = 1.0
                
                normID = #{}
                --apply normals
                for i = 1 to normArray.count do (
                    normID = #{} --free normID
                    normMod.ConvertVertexSelection #{i} &normID
                    for ii in normID do (
                        normMod.SetNormal ii (normalize normArray[i])
                        )
                    )
                collapseStack msh
                subobjectLevel = 0
                
                )
            
            -- Notify that File Failed to Open
            else (messageBox "Failed to open file.")
            )
        )
    
    )

-- Luanch Widget
--createDialog impgeo

-- Opens File
impgeo.read(
    --"C:\\Users\\Corey\\Downloads\\ball\\ball.geo" -- fixed path for testing
    GetOpenFileName types:"Geo files (*.geo)|*.geo|All files (*.*)|*.*|"
    )

```
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-08-26T08:40:24+00:00
- Post Title: Blast Games Ltd. .geo file

Damn!
You Guys are freaking fast!
Thanks so much for your Work on this.

Haha and no, i was referring to online converters and older converters i found online.

Thanks so much again!
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-26T10:02:45+00:00
- Post Title: Blast Games Ltd. .geo file

> Reply from Henchman800 ↑Sat Aug 26, 2023 4:40 pm at Sat Aug 26, 2023 4:40 pm
>
> Haha and no, i was referring to online convertersThere is no such thing as a .geo online converter, I guess.

What you're referring to is probably online converters for geographic coordinates.
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-08-26T12:53:24+00:00
- Post Title: Blast Games Ltd. .geo file

> Reply from shakotay2 ↑Sat Aug 26, 2023 6:02 pm at Sat Aug 26, 2023 6:02 pm
>
> 
What you're referring to is probably online converters for geographic coordinates.

hehe caught me i guess.
i was lucky like that before though with a .geo file from a different game.
when they are old enough and just dump .dds and .wav files in folders next to the .exe, then the 3d model usually is a very common type from that era, too.

However thanks again man for the quick response
## Post #7
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-08-26T16:18:41+00:00
- Post Title: Blast Games Ltd. .geo file

> Reply from mariokart64n ↑Sat Aug 26, 2023 10:02 am at Sat Aug 26, 2023 10:02 am
>
> 
Maxscript for 3dsmax

thank you agian man, could you also make it available as a blender script for me please?
cant get my 3ds max to run on my laptop no more -.-

EDIT:
nevermind, its working now
