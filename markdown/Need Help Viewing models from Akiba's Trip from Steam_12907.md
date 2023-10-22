## Post #1
- Username: Jarten
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 05, 2015 12:47 pm
- Post datetime: 2015-06-05T05:31:02+00:00
- Post Title: Need Help Viewing models from Akiba's Trip from Steam

I'm pretty new to exporting models from games and I was hoping to extract the character models from this game in order to see how they were done clothing and hairwise, and to find out if it was possible to create newer textures for them to put back in game. By any chance would anyone know how to view and possible convert .pepd model files for editing?

Also I just joined this site so if I posted this in the wrong area or something please let me know so I can fix it if I can.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-05T09:36:13+00:00
- Post Title: Need Help Viewing models from Akiba's Trip from Steam

welcome to the forum, Jarten.  
On a quick glance I found this:
[viewtopic.php?f=10&t=10941&p=102489&hil ... pd#p102489](http://forum.xentax.com/viewtopic.php?f=10&t=10941&p=102489&hilit=%2Cpepd#p102489)
but it's for PS3 and Akiba's Trip 2

Keep in mind: other than PC files (little endian) the ones from PS3 are big-endian.
So even if the model format didn't change from AT to AT2 the noesis script won't load them.
(But maybe help create a new script? A pepd model sample (PC) would be needed, though.)
## Post #3
- Username: Jarten
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 05, 2015 12:47 pm
- Post datetime: 2015-06-05T18:09:00+00:00
- Post Title: Need Help Viewing models from Akiba's Trip from Steam

Thank you for having me   

Well, from looking at the game I think its a port of Akiba's Trip 2.
I managed to find an extractor to get to the model files so I was able to copy the model files and other ones out of the main directory.
Then I did try the noesis script that was in the link you posted but it didn't seem to work when I tried to follow what was directed.

here is one of the model files altho I don't know if it will need anything else to go with it.


 Akiba 2 - .pepd Model File.rar
(173.58 KiB) Downloaded 76 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-05T21:40:37+00:00
- Post Title: Need Help Viewing models from Akiba's Trip from Steam

using hex2obj (view link in my sig):



chrmd_f_head_taka_e_001.JPG (83.77 KiB) Viewed 542 times

(two submeshes, 2 left?)
## Post #5
- Username: Bayuro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 05, 2016 11:31 pm
- Post datetime: 2016-04-05T16:59:12+00:00
- Post Title: Need Help Viewing models from Akiba's Trip from Steam

Hello, I'm Bayuro. I'm kinda new here on Xentax. I just want to know if there's possible to extract/rip the models which also includes the textures of the city from Akiba's Trip 2 PC? If there's any please share some download links of the shareware used. The truth is I only need the texture of the city. I'm trying to make a city via mapster32 for Duke Nukem 3D. Reply will be appreciated. T.Y.
## Post #6
- Username: Bayuro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 05, 2016 11:31 pm
- Post datetime: 2016-04-05T17:21:25+00:00
- Post Title: Need Help Viewing models from Akiba's Trip from Steam

> Reply from Jarten
>
> Thank you for having me   

Well, from looking at the game I think its a port of Akiba's Trip 2.
I managed to find an extractor to get to the model files so I was able to copy the model files and other ones out of the main directory.
Then I did try the noesis script that was in the link you posted but it didn't seem to work when I tried to follow what was directed.

here is one of the model files altho I don't know if it will need anything else to go with it.
Akiba 2 - .pepd Model File.rar

Hello Jarten, I'm Bayuro. I just want to know what kind of extractor are you talking about? Please reply. Your answer will be appreciated. T.Y.
## Post #7
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-01-18T22:58:07+00:00
- Post Title: Need Help Viewing models from Akiba's Trip from Steam

the quick bms script works for Unpacking the volume.dat the PC version of Akiba's Trip Undead & Undressed

Unfortunately the Noesis Plugin fmt_pepd.py 
(in Akiba's Archive post uploaded by prototypesky) [viewtopic.php?p=89927](http://forum.xentax.com/viewtopic.php?p=89927)
It doesnt work for the PC version and says
version: 692977664
version not supported: 692977664

I tried an older version of Noesis but I'm sure its referring to the version of the Pepd (phyre)

The textures are also in a .phyre format
Its odd because the models contain the words DAE and DDS, soooo how far off can they be?
acctx_glasses_a_001_ps3.dds.D3D11.phyre
chrmd_f_head_goth_n_001_lod0.dae.D3D11.pepd

What I'd really like to do is change the textures and then repack the volume.dat 
(changing 3D models would be a fun bonus but tex mods seem more common)
[akiba_strip2_noesis_scripts.rar](https://xentaxbackup.github.io/file/12247_akiba_strip2_noesis_scripts.rar)
## Post #8
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-12-21T18:42:00+00:00
- Post Title: Need Help Viewing models from Akiba's Trip from Steam

this is doable, though i got to confess that the whole maps are rather wonky at times, did a mrp script to get the files, the worst one to get is chuo_s, the last meshes do seem to do all sort of wonky shit and the textures for it i still have to find them....

exactly as stated before, the textures are inside phyre texture, those are simple DXT1 textures with a phyre header, using RawTex by adjusting the start offset to A68 or A64 you should be able to extract them easy, the models are a bit more complex, this is my code, might be able to help with some of the struct of the game files...

```
f = mrp.get_bfile()

list1 = []
list2 = []
#listtype = []
listvc = []
listoff = []

f.seek(4,1)
headerstart = f.readInt()
materialnamesoff = f.readInt()
filesize = f.readInt()
f.seek(32)
paddingfactor = f.readInt()
afterpadding = 20112 + (paddingfactor * 36)

f.seek(materialnamesoff)
matnames = []
curpos = f.tell()
char = f.readbyte()
name = ""
while curpos < filesize:
    name = name + chr(char)
    char = f.readbyte()
    if char == 0:
        matnames.append(name)
        name = ""
    curpos = f.tell()

mat = open('mat.txt', 'w')
for i in range (len(matnames)):
    print (str(i)+"\t"+matnames[i],file = mat)
    #print(matnames,file = mat)
f.seek(0x5c)
testpadd = f.readInt()
expectedentry = materialnamesoff - testpadd - 10
print("expected entry point for vertexes = "+hex(expectedentry))

f.seek(0x4E91)
secondpaddingfactor = f.readInt()
f.seek(afterpadding)
byte = f.readByte()
while byte == 0:
    byte = f.readByte()
for i in range(secondpaddingfactor):
    name = ""
    while byte != 0:
        name = name + chr(byte)
        byte = f.readByte()
    while byte == 0:
        byte = f.readByte()
    list1.append(name)
while byte == 0:
    byte = f.readByte()
name = ""
while byte != 0:
    name = name + chr(byte)
    byte = f.readByte()
    if byte == 0:
        list2.append(name)
        name = ""
        byte = f.readByte()
        if byte == 0:
            byte = f.readByte()
f.seek(-4,1)
byte = f.readByte()
while byte == 0:
    byte = f.readByte()
f.seek(-1,1)
print ("current possition for list = "+f.tellHex())
#-----------------------------------------------------------------------------
curposlist1 = 0xCC0D
currentfilist = 0x1A871
currentfis = 0x484B8
#-----------------------------------------------------------------------------
f.seek(curposlist1)
firstint = f.readInt()
checkpattern = 0
while firstint != 0:
    for i in range(11):
        vc = f.readInt()
        numero1 = f.readInt()
        f.seek(12,1)
        numero2 = f.readInt()
        f.seek(20,1)
        currentoffsetpad = f.readInt()
        f.seek(4,1)
        currentsize = f.readInt()
        f.seek(4,1)
        listvc.append(vc)
        listoff.append(currentoffsetpad)
        firstint = f.readInt()
        if firstint == 16:
            if checkpattern == 1:
                f.seek(64,1)
                checkpattern = 0
            else:
                checkpattern = 1
    checkpattern = 0
meshcount = int((len(listoff))/11)
#meshcount = 45
print ("current mesh count = "+str(meshcount))
vcs = []
for i in range(meshcount):
    curvc = i * 11
    curvcoff = listvc[curvc]
    vcs.append(curvcoff)
    curuv1 = 5 + i*11
    curuv2 = 8 + i*11 
    print ("Mesh_" + str(i)+ "_uv1  \t\tvc = "+ str(listvc[curvc])+"("+str(curvc)+")\t\t\tvs = "+str(hex(listoff[curvc]+expectedentry))+"("+str(curvc)+")\t\t\tuvs1 = "+str(hex(listoff[curuv1]+expectedentry))+"("+str(curuv1)+")")
    print ("Mesh_" + str(i)+ "_uv2  \t\tvc = "+ str(listvc[curvc])+"("+str(curvc)+")\t\t\tvs = "+str(hex(listoff[curvc]+expectedentry))+"("+str(curvc)+")\t\t\tuvs2 = "+str(hex(listoff[curuv2]+expectedentry))+"("+str(curuv2)+")")
#print(hex(afterpadding))

fisizes = []
fiscounts = []
acummulatives = []
#-----------------------------------------------------------------------------
#currentfilist = 0x61C1
#-----------------------------------------------------------------------------
print ("current FI list offset = "+ hex(currentfilist))
f.seek(currentfilist)
for i in range(meshcount):
    f.seek(32,1)
    currenttesting = f.tellHex()
    fiscount = (int(f.readInt()))
    fiscounts.append(fiscount)
    f.seek(32,1)
    acummulative = f.readInt()
    acummulatives.append(acummulative)
    f.seek(4,1)
    fisize = f.readInt()
    fisizes.append(fisize)
    f.seek(8,1)
print(str(currenttesting),fiscount,str(fisize))
#-----------------------------------------------------------------------------
#currentfis = 0x8D4A
#-----------------------------------------------------------------------------

print("current FIS = "+str(hex(currentfis)))
print(fiscounts, fisizes)
print(vcs)

vertstart = (currentfis + acummulative + fisizes[-1])
#print (hex(vertstart))
#vertstart = 0x7CCCA

for i in range(meshcount-1):
    fis = []
    verts = []
    uv1 = []
    uv2 = []
    curvc = i * 11
    curuv1 = 5 + i*11
    curuv2 = 8 + i*11
    curmesha =("mesh"+str(i)+"_uv1")
    curmeshb =("uv2_mesh"+str(i))
    f.seek(currentfis + acummulatives[i])
    for i in range(fiscounts[i]):
        fi = f.readShort()
        fis.append(fi)
    f.seek(vertstart + listoff[curvc])
    for i in range(listvc[curvc]):
        vert = f.read3Float()
        verts.append(vert)
    f.seek(vertstart + listoff[curuv1-1])
    for i in range (listvc[curvc]):
        u = f.readFloat()
        v = -f.readFloat()
        uv1.append((u,v))
    f.seek(vertstart + listoff[curuv2-1])
    for i in range (listvc[curvc]):
        u = f.readFloat()
        v = -f.readFloat()
        uv2.append((u,v))
    #print(curmesha,curmeshb)
    mrp.create_mesh(curmesha)
    mesh = mrp.get_mesh(curmesha)
    mesh.set_vertices(verts)
    mesh.set_faces(fis)
    mesh.set_uvs(uv1)
    mesh.set_uvs_indices(fis)
    mrp.create_mesh(curmeshb)
    mesh = mrp.get_mesh(curmeshb)
    mesh.set_vertices(verts)
    mesh.set_faces(fis)
    mesh.set_uvs(uv2)
    mesh.set_uvs_indices(fis)


#mrp.render()
#mrp.view_uvs()
print("check no problems")

```

[yodobashi.JPG](https://xentaxbackup.github.io/file/17214_yodobashi.JPG)
