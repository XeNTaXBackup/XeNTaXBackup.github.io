## Post #1
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2020-07-07T12:01:50+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

Hello there, 

i'd like to have some help figuring out the face format of these 2 games, the car models are kinda weird, first of all, the files use a buffer of vertex data, mostly 50 vertexes at a time, inside there are the vertexes in 3 Float(little endian) form, afterwards the uvs in 2Short, then there is something weird, that looks a bit like some normals, and lastly some kind of signature, but this is where it all gets kinda funky, because this part is the one that designates faces in the track geometry or even in other games, so if you guys might have a look and tell me about it...

(blue are ps2 render pipeline flags? maybe mips assembly to tell what is what, havent found much info on that regard besides having the vertcount on the 3rd byte)(both red are my hints to what could be normals/fis)


here the test files

[https://gofile.io/d/IDFoME](https://gofile.io/d/IDFoME)

000004b8.dat (Subaru wrx wagon; C1 test file)


000000a6.sdb(Honda civic; TXRD2 test file)


for now this is what i get using a simple count tristrip generator, but i guess there must be jumps to avoid the extra triangulation

although i know that both should use TIM2 textures, txrd2 seems to obfuscate the header of the textures, any hint on that regard would also be great...

also in case anyone needs some hints how i did it, here the code im using in mrp

```
import sys
f = mrp.get_bfile()

positions = []
contp = [0]
bytenum = []
mat = open('newoffs.txt', 'w')
crap = open('crap.txt', 'w')

f.seek(0xD170)
double = f.readDouble()
#-----------------------------------------------------------------
modelflag1 = 0x01000202
modelflag2 = 0x6c028000
containerflag = 0x60000000
endflag = 0x17000000

f.seek(0,2)
eof = f.tell()-8
#deviation
f.seek(0x8)
#eof = f.readInt()+32
#override
#eof = 0x48F0
f.seek(0)
#testing = f.readDouble()
pointer = f.tell()
#while testing != double:
maxn = 0

f.seek(0)
while pointer < eof:
    testing = f.readInt()
    nextint = f.readInt()
    pointer = f.tell()
    if testing == modelflag1 and nextint == modelflag2:
        curpos = f.tell()
        byte = f.readByte()
        f.seek(-1,1)
        #print(curpos,(curpos%16),byte,file = mat)
        positions.append(curpos)
    elif testing == containerflag:
        curpos = f.tell()
        contp.append(curpos)
    f.seek(8,1)


f.seek(0)
verts = []
faces = []
uvs = []
normals = []
meshes = []
curfi = 0
count = 0
end = 0
positions.append(0)
contp.append(0)
print(len(positions))  
while end == 0:
    #for i in range(1):
    for i in range(len(contp)):#len(contp)
        pos = f.tell()
        verts = []
        faces = []
        uvs = []
        normals = []
        #normalsflag = 0
        curnum = i+1
        curmesha = "mesh"+str(i)
        curfi = 0
        reps = 0
        if count > (len(positions)-2):
            nextpos = 0
            end = 1
            curnum = 99999
        else:
            #print(count + 1, len positions)
            nextpos = positions[count+1]
        #print("--------------" + str(count)+"\t" +str(contp[i+1])+"-------------"+str(f.tellHex())+"\t"+str(hex(positions[count])))
        #print(hex(pos), hex(contp[curnum]), hex(nextpos), hex(contp[curnum]))
        if end == 0:
            if nextpos > contp[curnum]:
                curnum = curnum + 1
                print(curnum, len(contp))
            while pos < contp[curnum] and nextpos < contp[curnum]and count < len(positions) and end == 0:
                verts = []
                faces = []
                uvs = []
                curfi = 0
                #normals = []
                curmesh = curmesha+"_"+str(reps)
                print(curmesh, file = crap)
                reps = reps + 1
                jump = positions[count]
                if curnum == 12:
                    print(f.tellHex())
                f.seek(jump)
                #print((jump -8)%16)
                count = count+1
                #print(count, f.tellHex(),vc)
                f.seek(38,1)
                vc = f.readByte()
                f.seek(1,1)
                for i in range(vc):
                    vert = f.read3Float()
                    verts.append(vert)
        
                f.seek(4,1)
                for i in range(vc):
                    uv = f.read2Short()
                    uvs.append(uv)
                f.seek(4,1)
                for i in range(vc):
                    a = f.readbyte()
                    b = f.readbyte()
                    c = f.readbyte()
                    normal = (a,b,c)
                    normalbin = (str(bin(a)),str(bin(b)),str(bin(c)))
                    print((normal,normalbin), file = crap)
                    normals.append(normal)
                #f.seek(4,1)
                pos = f.tell()
                rest = 16 -(f.tell() % 16)
                f.seek(rest+3,1)
                #print (rest,hex(pos))
                test = f.readbyte()
                print(f.tellHex(),count,curmesh)
                if test == 98:
                    ffcheck = 0
                    #curfi = 0
                    #print(f.tellHex(),count,curmesh)
                    for i in range(vc):
                        test2 = f.readbyte()
                        binar = str(bin(test2))
                        binary = int(binar[-1])
                        if binary == 1:
                            if ffcheck == 0:
                                #faces.append(65535)
                                ffcheck = 1
                            else:
                                ffcheck = 0
                        else:
                            ffcheck = 0
                        faces.append(curfi)
                        curfi = curfi + 1
                else:
                    for i in range(vc):
                        faces.append(curfi)
                        curfi = curfi + 1
                #faces.append(65535)
        
                #pos = f.tell()
                if count > (len(positions)-1):
                    end = 1
                    nextpos = 0
                else:
                    nextpos = positions[count]
                #print("normals "+str(normalsflag))
                #print (curmesh,curnum, reps)

                if len(verts) != 0 and len(faces) != 0:
                    mrp.create_mesh(curmesh)
                    mesh = mrp.get_mesh(curmesh)
                    #mesh = mrp.get_mesh()
                    meshes.append(curmesh)
                    #print(test)
                    mesh.set_vertices(verts)
                    mesh.set_faces(faces,fm="TStripFF")
                    mesh.set_uvs(uvs,tp="Short")
                    mesh.set_uvs_indices(faces,fm="TStripFF")
                    mesh.set_normals(normals)
                    #meshes.append(curmesh)


print(vc,len(verts))
print(curfi,len(faces))

mrp.render(meshes)
mrp.view_uvs()
mrp.print_mesh()



print("ok", f.tellHex(),count,hex(positions[count+1]),hex(nextpos))

print(len(contp),len(positions),hex(eof))

sys.exit("script halt")#--------------------------------------------

```
## Post #2
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2020-07-09T20:57:05+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

mmmm no repplies yet, ill post an update that could be helpfull, after some testing, i did find at least something interesting, what i though that are the uvs, might also have information regarding facing, it helps me clean the mesh a little bit, but not so much, im not quite sure if im missing some flags or something....

spikey boy here


as seen here, this kinda improves a bit the face generation, long story short(the last byte on the so called uvs, seem to have a sequence, when it jumps more than 1 up/down it seems to need a new element generation; though it isnt working 100%


the first mesh of the civic was the one where i did most of this testing


although there isnt as many faulty triangulation, there seems to be missing faces that should not be skipped



```
import sys
f = mrp.get_bfile()

positions = []
contp = [0]
bytenum = []
mat = open('newoffs.txt', 'w')
crap = open('crap.txt', 'w')

f.seek(0xD170)
double = f.readDouble()
#-----------------------------------------------------------------
modelflag1 = 0x01000202
modelflag2 = 0x6c028000
containerflag = 0x60000000
endflag = 0x17000000

f.seek(0,2)
eof = f.tell()-8
#deviation
f.seek(0x8)
#eof = f.readInt()+32
#override
#eof = 0x48F0
f.seek(0)
#testing = f.readDouble()
pointer = f.tell()
#while testing != double:
maxn = 0

f.seek(0)
while pointer < eof:
    testing = f.readInt()
    nextint = f.readInt()
    pointer = f.tell()
    if testing == modelflag1 and nextint == modelflag2:
        curpos = f.tell()
        byte = f.readByte()
        f.seek(-1,1)
        #print(curpos,(curpos%16),byte,file = mat)
        positions.append(curpos)
    elif testing == containerflag:
        curpos = f.tell()
        contp.append(curpos)
    f.seek(8,1)


f.seek(0)
verts = []
faces = []

uvs = []
normals = []
meshes = []
curfi = 0
count = 0
end = 0
positions.append(0)
contp.append(0)
print(len(positions))  
#while end == 0:
for i in range(1):
    for i in range(len(contp)):#len(contp)
        pos = f.tell()
        verts = []
        faces = []
        
        uvs = []
        normals = []
        #normalsflag = 0
        curnum = i+1
        curmesha = "mesh"+str(i)
        curfi = 0
        reps = 0
        if count > (len(positions)-2):
            nextpos = 0
            end = 1
            curnum = 99999
        else:
            #print(count + 1, len positions)
            nextpos = positions[count+1]
        #print("--------------" + str(count)+"\t" +str(contp[i+1])+"-------------"+str(f.tellHex())+"\t"+str(hex(positions[count])))
        #print(hex(pos), hex(contp[curnum]), hex(nextpos), hex(contp[curnum]))
        if end == 0:
            if nextpos > contp[curnum]:
                curnum = curnum + 1
                print(curnum, len(contp))
            while pos < contp[curnum] and nextpos < contp[curnum]and count < len(positions) and end == 0:
                #for i in range(20):
                verts = []
                faces = []
                newfaces = []
                uvs = []
                curfi = 0
                #normals = []
                curmesh = curmesha+"_"+str(reps)
                print(curmesh, file = crap)
                reps = reps + 1
                jump = positions[count]
                if curnum == 12:
                    print(f.tellHex())
                f.seek(jump)
                #print((jump -8)%16)
                count = count+1
                #print(count, f.tellHex(),vc)
                f.seek(38,1)
                vc = f.readByte()
                f.seek(1,1)
                for i in range(vc):
                    vert = f.read3Float()
                    verts.append(vert)
        
                f.seek(4,1)
                #for i in range(vc):
                #    uv = f.read2Short()
                #    uvs.append(uv)
                #f.seek(4,1)
                byte = 0
                for i in range(vc):
                    kek = f.readInt()
                    #f.seek(-1,1)
                    binar = f'{kek:032b}'
                    print(binar,str(hex(kek))[-8:].zfill(6),i, file = crap)
                    f.seek(-1,1)
                    if i == 0:
                        first = f.readByte()
                        newfaces.append(i)
                    else:
                        test = f.readByte()
                        vara = test+1
                        varb = test-1
                        #print(test)
                        if test == first or vara == first or varb == first:
                            newfaces.append(i)
                        else:
                            #print("here",i)
                            first = test
                            newfaces.append(65535)
                            newfaces.append(i)
                #    a = f.readbyte()
                #    b = f.readbyte()
                #    c = f.readbyte()
                #    normal = (a,b,c)
                #    normalbin = (str(bin(a)),str(bin(b)),str(bin(c)))
                #    print((normal,normalbin), file = crap)
                #    normals.append(normal)
                #f.seek(4,1)
                pos = f.tell()
                rest = 16 -(f.tell() % 16)
                f.seek(rest+3,1)
                #print (rest,hex(pos))
                test = f.readbyte()
                print(f.tellHex(),count,curmesh)
                #if test == 98:
                #    ffcheck = 0
                    #curfi = 0
                    #print(f.tellHex(),count,curmesh)
                #    for i in range(vc):
                #        test2 = f.readbyte()
                #        binar = str(bin(test2))
                #        binary = int(binar[-1])
                #        if binary == 1:
                #            if ffcheck == 0:
                                #faces.append(65535)
                #                ffcheck = 1
                #            else:
                #                ffcheck = 0
                #        else:
                #            ffcheck = 0
                #        faces.append(curfi)
                #        curfi = curfi + 1
                #else:
                #    for i in range(vc):
                #        faces.append(curfi)
                #        curfi = curfi + 1
                #faces.append(65535)
        
                #pos = f.tell()
                if count > (len(positions)-1):
                    end = 1
                    nextpos = 0
                else:
                    nextpos = positions[count]
                #print("normals "+str(normalsflag))
                #print (curmesh,curnum, reps,len(newfaces),len(verts))
                #print(newfaces)
                
                if len(verts) != 0 and len(newfaces) != 0:
                    #print("pasa")
                    mrp.create_mesh(curmesh)
                    mesh = mrp.get_mesh(curmesh)
                    #mesh = mrp.get_mesh()
                    meshes.append(curmesh)
                    #print(test)
                    mesh.set_vertices(verts)
                    mesh.set_faces(newfaces,fm="TStripFF")
                    #mesh.set_uvs(uvs,tp="Short")
                    #mesh.set_uvs_indices(faces,fm="TStripFF")
                    #mesh.set_normals(normals)
                    meshes.append(curmesh)


print(vc,len(verts))
print(curfi,len(faces))
print(len(meshes))

mrp.render(meshes)
mrp.view_uvs()
mrp.print_mesh()



print("ok", f.tellHex(),count,hex(positions[count+1]),hex(nextpos))

print(len(contp),len(positions),hex(eof))

sys.exit("script halt")#--------------------------------------------

```
## Post #3
- Username: djibsone2
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Dec 21, 2016 10:15 am
- Post datetime: 2020-07-11T16:27:34+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

great start I try to rip the models with pcsx2 dx9 plugin but the models are impossible to use because it comes out flattened deform .. there are some very rare models in GENKI games  GOOG LUCK
## Post #4
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2020-07-20T13:51:40+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

sooooo, no feedback regarding faces, after testing many things i really dont want to keep trying without any leads, and i dont seem to find a way to debug the actual assembly code when emulating, so for now ill just leave this to the side, the cars from txrd2 can be extracted through Kaido battle 2(kaido racer); maybe there are few models that are in one game or in the other, but its the previous revision of LDMX binaries, basically with a bit of editing the script for txr3 i already got the 3d data, plus the textures for kb2 are in tim2s, so extractable, maybe if i am in dire need to get any model from c1 i might try later to at least rework the models with faulty geometry
## Post #5
- Username: ZykoMizuki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 24, 2021 5:05 am
- Post datetime: 2021-04-23T21:14:10+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

I was wondering, is it possible to rip off the game maps of txr3 or txrd2? I tried the shift + F8 method while using PCSX2 v0.9.8, and then imported the .obj files in 3ds max, but the meshes were distorted and it's all stretched, even with the PCSX2modelconverter, it's still stretched and some of the meshes were gone, I'm still looking for a way on how to rip off the game maps.
## Post #6
- Username: djibsone2
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Dec 21, 2016 10:15 am
- Post datetime: 2021-04-23T22:02:36+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

shame that pcsx2 emulator does not give good result. I would very much like to have the rare tokyo drift 2 car.
## Post #7
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2021-04-24T17:59:56+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

> Reply from ZykoMizuki ↑Sat Apr 24, 2021 5:14 am at Sat Apr 24, 2021 5:14 am
>
> 
I was wondering, is it possible to rip off the game maps of txr3 or txrd2? I tried the shift + F8 method while using PCSX2 v0.9.8, and then imported the .obj files in 3ds max, but the meshes were distorted and it's all stretched, even with the PCSX2modelconverter, it's still stretched and some of the meshes were gone, I'm still looking for a way on how to rip off the game maps.

yes there is, well kind of, txr3 maps extracting its kinda doable, there are some broken normals and uvs, but most of the maps work in a nice way, in fact those have already been ripped in private, i can share the code of the extractor i used, but i dont think anyone will be interested in implementing it in a seamless way, i kinda had to play some tricks to make it doable so i didn't kill myself in the process, the sheer amount of files is a bit too extensive to do it one by one, so i did some concatenation and created TOC files for those compounds, someday if i am bored enough i might aswell just dump the code to a proper python only scrip but for now I'm busy and dont want to do it.

txrd2 has a different problem in comparison to txr3, which is mainly the UVs, it uses some scaling for the uvs for each subsection of the geometry in the buffers, i have never figured out but basically something like half of the meshes have distorted textures cause of the uvs being scaled down.

3d mesh and geometry is kinda okayish in txrd2 case, sure there are some ups and downs with the uvs, it could be reworked but it would be really painful to do.

example for nagoya code:

```
import sys
f = mrp.get_bfile()
#----------------------------------------------------------------------------------------------------------------
curlocal = 1
#----------------------------------------------------------------------------------------------------------------
meshlist = f.readInt()
#print(meshlist+2)
f.seek(16)
#toc
toc = []
for i in range(meshlist):
    toc.append(f.readInt())
    f.seek(12,1)    
#print(toc)
pos = f.tellHex()
#print(hex(toc[2]))

#sys.exit("script halt")#--------------------------------------------

meshes = []
for i in range(meshlist):
    lefile = i
    currentoffset = toc[i] #+16
    f.seek(currentoffset)
    #f.seek(16,1)
    print(f.tellHex())
    counter = 0
    #print ("***************"+quak)
    lodn = f.readInt()
    #lodn = 1
    lods = []
    #meshes = []
    for i in range(1):
        offsets = (f.readInt())# + start + 16)
        lods.append(offsets)
        print(f.tellHex())
        #lods.append(0)

    for i in range(1):
    	curlod = i
    	
    	f.seek(currentoffset)
    	#f.seek(16,1)
    	f.seek(lods[i],1)
    	#print(f.tellHex())
    	f.seek(36,1)
    	#print("headera" + str(f.tellHex()))
    	#print(f.tellHex())
    	meshn = f.readInt()
    	
    	f.seek(168,1)
    	modoru = f.tell()
    	#print("headerb" + str(f.tellHex()))
    	f.seek(32,1)
    	locatora = f.readFloat()
    	locatorb = f.readFloat()
    	locatorc = f.readFloat()
    	f.seek(modoru)
    	#print(f.tellHex(),meshn)
    	for i in range(meshn):#mesh 80
    		curms = i
    		f.seek(92,1)
    		elementn = f.readInt()
    		f.seek(32,1)
    		for i in range(elementn):#element a0
    			curelem = i
    			
    			verts = []
    			uvs = []
    			faces = []
    			normals = []
    			curfi = -1
    			#print(f.tellHex(),counter)
    			counter = counter + 1
    			f.seek(13,1)
    			container = f.readByte()
    			text = f.readByte()+1
    			if curlocal == 8 or curlocal == 3 or curlocal == 9 or curlocal == 10 or curlocal == 13:
                            if container == 3:
                                container = 2
    			if container == 0:
    				curmesh = "HUE" + str(curlocal)+"file" + str(lefile) + "_mesh" +str(curms)+"_element"+str(curelem)+"_common_tex"+str(text)
    				mat = "common_tex"+str(text)
    				matex = 'matt.set_texture(r\"E:\\Downloads\\ModelResearcherPro\\Nueva carpeta\\txr3\\nagoya\\global\\cont1_'+str(text)+'.png")'
    			elif container == 4:
    				curmesh = "HUE" + str(curlocal)+"file" + str(lefile) + "_mesh" +str(curms)+"_element"+str(curelem)+"_common_anim_tex"+str(text)
    				mat = "common_anim_tex"+str(text)
    				matex = 'matt.set_texture(r\"E:\\Downloads\\ModelResearcherPro\\Nueva carpeta\\txr3\\nagoya\\global\\cont2_'+str(text)+'.png")'
    			else:
    				curmesh = "HUE" + str(curlocal)+"_file" + str(lefile) + "_mesh" +str(curms)+"_element"+str(curelem)+"_local"+str(curlocal)+"_cont"+str(container)+"_tex"+str(text)
    				mat = "local"+str(curlocal)+"_cont"+str(container)+"_tex"+str(text)
    				matex = 'matt.set_texture(r\"E:\\Downloads\\ModelResearcherPro\\Nueva carpeta\\txr3\\nagoya\\local\\loca'+str(curlocal)+'_'+str(container)+'_'+str(text)+'.png")'
    			f.seek(101,1)
    			facen = f.readInt()
    			f.seek(40,1)
    			for i in range(facen):#face
    				start = f.tell()
    				leng = f.readShort()
    				faceleng = ((leng*16)+16)
    				end = start + faceleng
    				#print(hex(start),hex(end),hex(faceleng),hex(leng))
    				f.seek(10,1)
    				vc = f.readInt()
    				f.seek(80,1)
    				#print(f.tellHex(), hex(vc),i)
    				for i in range(vc):
                                    x = (locatora + f.readFloat())
                                    y = (locatorb + f.readFloat())
                                    z = (locatorc + f.readFloat())
                                    vert = (x, y, z)
                                    verts.append(vert)
    				f.seek(4,1)
    				for i in range(vc):
    					u = f.readFloat()
    					v = -f.readFloat()
    					uv = (u,v)
    					uvs.append(uv)
    				f.seek(4,1)
    				for i in range(vc):
    					curfi = curfi + 1
    					faces.append(curfi)
    				faces.append(65535)
    				for i in range(vc):
    					a = f.readByte()
    					b = f.readByte()
    					c = f.readByte()
    					normal = (a,b,c)
    					normals.append(normal)
    					f.seek(1,1)
    				#print(f.tellHex())
    				f.seek(end)
    			mrp.create_mesh(curmesh)
    			mesh = mrp.get_mesh(curmesh)
    			mesh.set_vertices(verts)
    			mesh.set_uvs(uvs)
    			mesh.set_faces(faces,fm="TStripFF")
    			mesh.set_uvs_indices(faces,fm="TStripFF")
    			matt = mrp.create_material(mat)
    			exec(matex)
    			mesh.set_material(matt)

    			#mesh.set_normals(normals)
    			#mrp.render(curmesh)
    			#mrp.view_uvs(curmesh)
    			#mrp.print_mesh(curmesh)
    			meshes.append(curmesh)
    			f.seek(16,1)
    		#f.seek(16,1)
    
    #f.seek(endoffile)



print(f.tellHex())







#mrp.create_mesh(curmesh)
#mesh = mrp.get_mesh()
#mesh.set_vertices(verts)
#mesh.set_uvs(uvs)
#mesh.set_faces(faces,fm="TStripFF")
#mesh.set_uvs_indices(faces,fm="TStripFF")
#mesh.set_normals(normals)
mrp.render(meshes)
#mrp.view_uvs(meshes)
#mrp.print_mesh(meshes)







sys.exit("script halt")#--------------------------------------------

```


here another example for the TOC generator:

```
import sys
import os
import glob
from struct import *
#f = mrp.get_bfile()

files = glob.glob(r"E:\Downloads\ModelResearcherPro\Nueva carpeta\txr3\osaka\1\nfc\*")
print(len(files))
toc = open('toc.bin', 'wb')


count = len(files)
dummy = (count+2)*16
with open('toc.bin', 'ab') as file:
    file.write((count).to_bytes(16, byteorder='little', signed=False))
with open('toc.bin', 'ab') as file:
    file.write((dummy).to_bytes(16, byteorder='little', signed=False))

for i in range(len(files)):
    size = (os.stat(files[i]).st_size)
    dummy = dummy + size
    with open('toc.bin', 'ab') as file:
        file.write((dummy).to_bytes(16, byteorder='little', signed=False))

print(files)
sys.exit("script halt")#--------------------------------------------

```


lastly the code i did for txrd2

```
import sys
f = mrp.get_bfile()

#verts = []
#uvs = []
#faces = []
#curfi = -1
#mat = open('mat.txt', 'w')
#facesfile = open('faces.txt', 'w')
#variables = []
meshes = []
for i in range(18):
    materials = []
    new = 0
    filecount = i
    print ("***************")
    meshnum = f.readInt()
    f.seek(12,1)
    for i in range(meshnum):
        a = f.readInt()
        b = f.readInt()
        mesh = str(filecount)+"mesh_"+ str(i)+"_mat_"+str(a)+"_"+str(b)
        materials.append(mesh)
        f.seek(8,1)
        #print(mesh)
    #print(f.tellHex())
    #jump = (meshnum*16)
    #f.seek(jump)
    f.seek(-16,1)
    #print ("start "+f.tellHex())
    for i in range(meshnum):
        #print("mesh "+ str(i)+"\n",file = mat)
        curmesh = materials[i]
        verts = []
        uvs = []
        faces = []
        facestri = []
        normals = []
        curfi = -1
        f.seek(20,1)
        repeat = f.readInt()
        f.seek(40,1)
        for i in range(repeat):
            #print("\nRepeat "+ str(i)+"\thex ="+str(f.tellHex())+"\n",file = mat)
            #currep="_rep_"+str(i)
            #curmesha =curmesh+currep
            #verts = []
            #uvs = []
            #faces = []
            #facestri = []
            #curfi = -1
            start = f.tell()
            leng = f.readShort()
            meshleng = ((leng*16)+16)
            if leng != 0:
                f.seek(10,1)
                count = f.readint()
                f.seek(48,1)
                for i in range(count):
                    verts.append(f.read3Float())
                f.seek(4,1)
                for i in range(count):
                    uv = f.read2short()
                    uvs.append(uv)
                f.seek(4,1)
                ffcheck = 0
                #print (curmesh+"\t"+currep+"\t"+str(f.tellHex()))
                for i in range(count):
                    curfi = curfi + 1
                    #f.seek(3,1)
                    reada = f.readByte()
                    readb = f.readByte()
                    readc = f.readByte()
                    normals.append((reada,readb,readc))
                    readd = f.readByte()
                    binar = str(bin(readd))
                    binary = int(binar[-1])
                    facea = curfi - 2
                    faceb = curfi - 1
                    facec = curfi
                    if binary == 1:
                        if ffcheck == 0:
                            #print("\n\t\t\t\t\tFFFF",file = mat)
                            faces.append(65535)
                            ffcheck = 1
                        #else:
                            #ffcheck = 0
                    else:
                        if (i % 2) == 0:
                            facestri.append((facea,faceb,facec))
                        else:
                            facestri.append((facea,facec,faceb))
                        ffcheck = 0
                    faces.append(curfi)
                    #new = read
                    #if (len(variables) == 0:
                    #    variables.append(new)
                
                    #print ("current face "+str(i)+"\treada = "+hex(reada)+"\treadb = "+hex(readb)+"\treadc = "+hex(readc)+"\treadd = "+hex(readd)+"\t\tbin = "+str(binary), file = mat)    
                faces.append(65535)
                f.seek(start)
                f.seek(meshleng,1)
            #if (curfi + 1) > count:
                #print ("----------------------------------------------------------------------------------------------------------------------",file =facesfile)
            #print(curmesh+"\t"+currep+"\t"+str(f.tellHex())+"\nvc = "+str(count)+"\tmaxface = "+str(curfi + 1),file = facesfile)
            #print(facestri,file = facesfile)
        
        
            #faces.append(65535)       
        mrp.create_mesh(curmesh)
        mesh = mrp.get_mesh(curmesh)
        mesh.set_vertices(verts)
        #mesh.set_faces(faces,fm="TStripFF")
        mesh.set_faces(facestri)
        mesh.set_uvs(uvs,tp="Short")
        #mesh.set_uvs_indices(faces,fm="TStripFF")
        mesh.set_uvs_indices(facestri)
        #mesh.set_normals(normals)
        meshes.append(curmesh)
        
        #mrp.print_mesh()
        #print("\n---------------------------------------------------------------------------\n",file = mat)
    f.seek(16,1)
mrp.render(meshes)
print ("end "+f.tellHex())
print ("------------------")

```


before you try to load the code somewhere and try to dump stuff, this doesn't work like that, first you will need to unpack the files, which can be unpacked using the txr script for BMS(you need to change the endian type to small!!!!!! big endian will only work for ITC)...

for the textures you need to locate TIM2 blocks; basically the file structure goes like this; a lot of stuff, then cars, then wheels, then the tracks(for tracks you have first a global container for textures, then local containers and batches of sections;sections repeat a few times inside each track; iirc osaka was like 20 sections) then you need to link those global textures container and the local containers with the materials i did write in the script, a track like osaka alone has between 3000-5000 textures, also to unpack tim2 files the easiest is using noesis...

well i guess after reading as much you might want not to do it though xD
## Post #8
- Username: djibsone2
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Dec 21, 2016 10:15 am
- Post datetime: 2021-04-24T19:58:58+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

thanks but i'm a real noob with code.
## Post #9
- Username: ZykoMizuki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 24, 2021 5:05 am
- Post datetime: 2021-04-25T20:21:22+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

well I reached this far after deep browsing just to get my hands on the maps of TXR3, especially Osaka, I'm also familiar with scripts and codes so it wouldn't be that hard for me to figure it out, and to what I see here it looks like it might take a while to process. but yeah I'm still interested and willing to do this, I still have other things to do so maybe when I have freed my time, I'm gonna work on this,

also I appreciate the help, you did good bro, keep it up.
## Post #10
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2021-04-26T11:08:15+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

> Reply from ZykoMizuki ↑Mon Apr 26, 2021 4:21 am at Mon Apr 26, 2021 4:21 am
>
> 
well I reached this far after deep browsing just to get my hands on the maps of TXR3, especially Osaka, I'm also familiar with scripts and codes so it wouldn't be that hard for me to figure it out, and to what I see here it looks like it might take a while to process. but yeah I'm still interested and willing to do this, I still have other things to do so maybe when I have freed my time, I'm gonna work on this,

also I appreciate the help, you did good bro, keep it up.

I mean I could explain the structure of the the files and how to understand the flags of the geometry stuff... ill hit you up with some stuff
## Post #11
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2021-05-01T16:12:54+00:00
- Post Title: C1 grand prix / tokyo xtreme racer drift 2

to be honest at some point i kinda wanted to release the stuff more or less, though I don't want to be in any spotlight, so for now ill do the following...
the link below will work only for 1 week, aka till 8 may 2021, there will be the tracks and the textures, it needs fixing so much fun fixing what you can;

[https://gofile.io/d/NzTJy2](https://gofile.io/d/NzTJy2)
