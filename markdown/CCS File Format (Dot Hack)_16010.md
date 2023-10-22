## Post #1
- Username: namine207
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 16, 2017 11:04 am
- Post datetime: 2017-03-17T08:38:32+00:00
- Post Title: CCS File Format (Dot Hack)

Hello there!

I've been talking with a Reverse Engineer named WarrantyVoider who is trying to RE the CCS file format found in .hack//IMOQ, Fragment, G.U. and Link. So far, using HackPics, Guhck, and Forte's CCS2OBJ as references, he's been able to create three utilities to assist in viewing, dumping, and editing the data and texture contents of the CCS files contained within IMOQ/Fragment's Data.bin, G.U. and onward's compressed CCS files.

So far, he's come to understand certain type's of data and identifiers used in the code to show what filetype each data blob represents, and he's already begun some work into understanding the blobs that represent model data. However, there have definitely been a few roadblocks at this point and we both thought it'd be a good idea to post here and see if maybe he could get any input.

Here are the utilities wv has coded to look into these files:

CCS File Explorer (Allows for in depth exploration and dumping of IMOQF's Data.bin and resulting CCS) as well as Texture Export:
[https://github.com/zeroKilo/CCSFileExplorerWV](https://github.com/zeroKilo/CCSFileExplorerWV)

Data.bin Reader (Most functions are now implemented in the more comprehensive CCSFE above, but this one processes G.U./Link CCS files as well via the "Compressed" format option):
[http://www.mediafire.com/file/90tok58uz ... Reader.zip](http://www.mediafire.com/file/90tok58uzdxujne/DataBinReader.zip)

Area Server Explorer (For editing/extracting Fragment's Area Server program and its CCS files):
[https://github.com/zeroKilo/AreaServerExplorerWV](https://github.com/zeroKilo/AreaServerExplorerWV)

I also have an index of files (based on texture/naming info) contained within Fragment's Data.BIN in particular to help provide a means of quickly finding whichever file someone is looking for:
[https://docs.google.com/document/d/18FL ... sp=sharing](https://docs.google.com/document/d/18FLZUuAyTnPIJWWh_pHYJImAA48kyYN_XThnS6U3eeo/edit?usp=sharing)

Some other things that may help include Forte's CCS2OBJ tool, which allows one to take GU format CCSes and extract some, but not all, OBJ files from them (with the source included):
[http://www.mediafire.com/file/e9igf8f5i ... Source.zip](http://www.mediafire.com/file/e9igf8f5ikrgrnt/CS2OBJ_with_Source.zip)

And here are some examples of three different types of CCS files, one from G.U., one from IMOQ, and a third from the Area Server (Area Server files are very stripped down compared to their game counterparts):
[http://www.mediafire.com/file/iklox2uas ... amples.zip](http://www.mediafire.com/file/iklox2uasiqxczn/CCS_File_Examples.zip)

The last thing that's definitely worth sharing as far as resources go is this file containing 8k mesh blobs that wv exported yesterday. He's been working to run it through using some information included in Forte's previous Xentax threads, and despite some success, we haven't been able to quite crack the model files yet:
[http://www.mediafire.com/file/igymnx9b3nww50s/sub.rar](http://www.mediafire.com/file/igymnx9b3nww50s/sub.rar)

The file types are listed here:

case 0xcccc2400: // BIN
               break;
            case 0xcccc0100: // OBJECT
            case 0Xcccc0a00:
            case 0Xcccc2000:
               break;
            case 0xcccc0200: // MATERIAL
               break;
            case 0xcccc0700: // ANIMATION
               break;
            case 0xcccc0800: // MESH
               break;
            case 0xcccc0900: // CMP
               break;
            case 0xcccc0400: // PALETTE
               break;
        case 0xcccc0300: // IMAGE

If anyone is able to take a look into some of these files using any of the above utilities, or is able to shed some light onto this format, definitely let me know via a PM, and I can get you in touch with WV, so you guys can talk even more in depth and hopefully work together to find a solution!

I'm going to be editing this too if there's any additional information or resources that I should add, so keep an eye out within the next few hours as I may pop on a bit more. I'll also try to update this thread if any major breakthroughs should occur!


Update 1:

Ok, so WarrantyVoider has made an additional utility, called Stupidblocks, that allows anyone to analyze the model blocks. It provides either an error, or an 0xFFFFFFFF, which means that it read the file completely. If we can fix the blocks with errors so that it's read the entire file, we effectively have the format and can add it into the CCS Viewer! Here's that utility:

[http://www.mediafire.com/file/8x5y70itd ... Blocks.zip](http://www.mediafire.com/file/8x5y70itdraekvm/StupidBlocks.zip)

And here are the updated block definitions:

public static uint[] validBlockTypes = new uint[] { 
            0xCCCC0001, 0xCCCC0002, 0xCCCC0005, 0xCCCC0100,
            0xCCCC0102, 0xCCCC0108, 0xCCCC0200, 0xCCCC0300,
            0xCCCC0400, 0xCCCC0500, 0xCCCC0502, 0xCCCC0600,
            0xCCCC0601, 0xCCCC0603, 0xCCCC0609, 0xCCCC0700,
            0xCCCC0800, 0xCCCC0900, 0xCCCC0A00, 0xCCCC0B00,
            0xCCCC0C00, 0xCCCC0E00, 0xCCCC1100, 0xCCCC1200,
            0xCCCC1300, 0xCCCC1400, 0xCCCC1900, 0xCCCC1901,
            0xCCCC2000, 0xCCCCFF01
        };
0800 = "MDL" (models), 0400 = CLT (color table/palette), 0300 = TEX (texture,bitmap), 0700 = groups of subblocks, 0001 header, 0002 file/obj list
## Post #2
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2017-03-17T12:09:10+00:00
- Post Title: CCS File Format (Dot Hack)

yay, I wanted to register and realized I already have an account here, yay!

some screenshots to the stupidblock tool (sry for the name^^)

successfull read (reads till type FF01)


read with errors


the node name format is: index, type, offset (rel. to parent)
offset is for comparing in hexeditor^^

please let me know if you find an unknown type not convered yet

also [here the current structure definition for the models](http://pastebin.com/bpdBrmZA)
and [a list of possible values ive seen for unknown2 and 3](http://pastebin.com/Mw6bFY7W), from 35000+ test mesh blobs

greetz WV
## Post #3
- Username: namine207
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 16, 2017 11:04 am
- Post datetime: 2017-03-19T23:27:56+00:00
- Post Title: CCS File Format (Dot Hack)

Woah! Seriously cool update!  With some help from NCDyson, the CCS File Explorer now has a fully correct read on the data blocks inside the CCS files! WV has also coded in Raw Import and Saving capabilities, so you can actually change out the files inside of the CCSes, here's a cool example!

Original Texture Object with Pallette:


Texture Object with different Pallette:


This has really opened up the door for a lot of different possibilities, so it looks like this topic is going to be pretty active in the days to come!
## Post #4
- Username: Kharaxel
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 29, 2008 8:56 pm
- Post datetime: 2017-03-27T21:23:44+00:00
- Post Title: CCS File Format (Dot Hack)

This kind of progress is amazing! I hope you guys can pull through and we can get G.U. model exporting.
Thank you!
## Post #5
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2017-04-10T22:30:33+00:00
- Post Title: CCS File Format (Dot Hack)

I got your messages... albeit I'm not here very actively anymore but I show up on rare occasions... I'm hesitant to release this because honestly its kind of crap, and I don't remember how any of it works or even which of these is the correct file... but I do have a script that imports scene geometry and come character geometry, but without bone information.

The files are somewhat different in format between scene and character though, so there's something you have to un/comment out when trying to switch between one or the other.... I'm sorry I can't tell you which.

I apologize because the code is a wreck that even I can't explain, but it one of them does accomplish some things. I don't have time right now to clean it up for you, but if you're interested in working on the format, I figure more disclosure is better than less, even if you can't make sense of it, there's still a better chance than if I kept it to myself.
Does NOT work on GU as they are a newer CCS/CMP format.

You need to unzip the .CCS archives and run noesis on the T/CMP.
.CCS archives for GU and IMOQ and Fragment are simple GZip archives that 7zip should readily handle with the 'unpack archive' option.

I apologize for the size, but I can't find a way to spoiler this.

Newer Datestamp

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
    handle = noesis.register(".hack//IMOQ, .hack//FGMT", ".cmp")
    noesis.setHandlerTypeCheck(handle, imoqCheckType)
    noesis.setHandlerLoadModel(handle, imoqLoadModel) #see also noepyLoadModelRPG
        #noesis.setHandlerWriteModel(handle, noepyWriteModel)
        #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
    #noesis.logPopup()
        #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
    return 1

CCS_HEADER = 0xCCCC0001

#check if it's this type based on the data
def imoqCheckType(data):
    bs = NoeBitStream(data)
    if len(data) < 16:
        return 0
    if bs.readUInt() != CCS_HEADER:
        return 0
    #print("check pass")
    return 1         

#load the model
def imoqLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    
    
    successful_loads = 0
    
    mdl_loc = []
    file_paths = []
    file_comps = []
    comp_owner = []
    
    #read the main file name
    bs.seek(0x0C, NOESEEK_ABS)
    cmp_name = bs.readBytes(0x20).decode("ASCII").rstrip("\0")
    
    #read subfile path/names...
    #first reading how many files and components there will be...
    bs.seek(0x44, NOESEEK_ABS)
    num_files = bs.readUInt()
    num_comps = bs.readUInt()
    
    bs.seek(0x20, NOESEEK_REL)
    #Now grab the paths
    for i in range(0,num_files-1):
        file_paths.append(bs.readBytes(0x20).decode("ASCII").rstrip("\0"))
    #print("filepaths done"+hex(bs.tell()))
    #skip the empty path entry padding
    #bs.seek(0x20, NOESEEK_REL)
    
    #now we read the names of each component of the previously named files, and memorize to which file they belong
    for i in range(0,num_comps-0):
    #.decode("ASCII") is obvious, but .rstrip("\0") is less so. It cuts the 00 00 00 off the end of the string
        file_comps.append(bs.readBytes(0x1E).decode("Shift_JIS").rstrip("\0"))
        comp_owner.append(bs.readUShort())
    #print("comp names done"+hex(bs.tell()))
        #Don't print anything with shift_jis encoding... it crashes noesis

    #Find the MDL markers, 0x00 08 CC CC :: Old way. 
    '''while(bs.getOffset()<len(data)):
        if bs.readUInt() == 0xCCCC0800:
            mdl_loc.append(bs.getOffset())'''
    #Find MDLs and components, intelligently. :: New way
    bs.readBytes(0x08) #unknown
    #print(hex(bs.tell()))
    cmpLoc = []
    cmpType = []
    cmpLength = []
    cmpNameID = []
    matlist = []
    texlist = []
    cltlist = []
    mdlmat = []
    bonelist = []
    boneparentlist = []
    bonemdllist = [0]
    skeletonlist = []
    
    #for i in range(0,num_comps):
    while(bs.getOffset()<len(data)):    
        checking = bs.readUInt()
        if checking & 0xCCCC0000 == 0xCCCC0000 and checking <= 0xCCCCFFFF:
            cmpType.append(checking)
            #print(hex(checking))
        #cmpType.append(bs.readUInt())
        #if cmpType[i] & 0xCCCC0000 != 0xCCCC0000:
        #    noesis.logPopup
        #    print(hex(bs.tell()))
        #    return 0
            cmpLoc.append(bs.tell())
            cmpLength.append(bs.readUInt())
            cmpNameID.append(bs.readUInt())
        
        #bs.seek(cmpLength[i]*4,NOESEEK_REL)
        
    totalVerts = 0 #we will track how many verts have been iterated
    #print(1)
    #for every model marker found, attempt to load vertices...
    """
    for i in range(0,len(cmpType)):

    
    #if 1==1:
        bs.seek(cmpLoc[i], NOESEEK_ABS)
        if cmpType[i] == 0xCCCC0200:
            #if(len(matlist)==217):
                #print("This is the errorindex", hex(bs.tell()))
            print(""+hex(bs.tell())+" Mat")
            #t = loadTEX(texofs[i],bs)
            #texlist.append(NoeTexture(rapi.getExtensionlessName(rapi.getLocalFileName(rapi.getInputName()))+"_"+str(i), t[1], t[2], t[0], noesis.NOESISTEX_RGBA32))
            #loadTIM(texofs[i],bs,texlist)
            bs.readBytes(0x08) #skip some stuff
            texidx = bs.readUInt()
            tmpmat = 0
            textmp = 0
            paltmp = 0
            #print(hex(bs.tell()))
            somefloat = bs.readFloat()
            blendmode = bs.readUInt()
            #print("blend",hex(blendmode), hex(bs.tell()-4))
            for a in range(0,len(cmpType)):
                if cmpType[a] == 0xCCCC0300 and cmpNameID[a] == texidx:
                
                    #load texture
                    #textmp = getTex()
                    
                    
                    bs.seek(cmpLoc[a],NOESEEK_ABS)
                    #print(""+hex(bs.tell())+" Tex")
                    bs.readBytes(4) #ignore some things
                    texname = bs.readUInt()
                    #print(file_comps[texname])
                    cltidx = bs.readUInt()
                    bs.readBytes(8) #unknown
                    w = 2 ** bs.readByte()
                    h = 2 ** bs.readByte()
                    bs.readBytes(6) #unknown
                    l = bs.readUInt() * 4
                    #print(w,h,hex(l))
                    pix = bs.readBytes(l)
                    clut = 0
                    for b in range(0,len(cmpType)):
                        if cmpType[b] == 0xCCCC0400 and cmpNameID[b] == cltidx:
                            bs.seek(cmpLoc[b],NOESEEK_ABS)
                            #print(""+hex(bs.tell())+" Clut")
                            #continue
                    bs.readBytes(8)#ignore some stuff
                    bs.readBytes(0x0C)#unknown
                    cl = bs.readUInt()
                    clut = []
                    
                    for b in range(0,cl*4):
                        if(b>0):
                            if((b)%4==0):
                                clut.append(max(0,(bs.readUByte()*2)-1)&0xFF)
                                #print(clut[b-1])
                                #clut.append(bs.readUByte())
                            else:
                                clut.append(bs.readUByte())
                                #print(clut[b-1])
                    clut = struct.pack('B'*len(clut),*clut)
                    textmp = rapi.imageDecodeRawPal(pix,clut,w,h,8,"r8g8b8a8")
                    texlist.append(NoeTexture(file_comps[texname], w, h, textmp, noesis.NOESISTEX_RGBA32))
                    #print ("Material:", file_comps[cmpNameID[i]])
                    tmpmat = NoeMaterial(file_comps[cmpNameID[i]],file_comps[texidx])
                    #print(file_comps[cmpNameID[i]])
                    tmpmat.setTexture(file_comps[texname])
                    if(blendmode == 0x10000000):
                        tmpmat.setBlendMode(noesis.NOEBLEND_SRC_ALPHA,noesis.NOEBLEND_ONE)
                    #tmpmat.setFlags(0,1)
                    #______tmpmat.setTexture(texlist[i])
                    #rapi.rpgSetMaterial("mat_"+str(i))
                    
            #nameidx = bs.readUInt()
            matlist.append(tmpmat)
            """
    for i in range(0,len(cmpType)):
        bs.seek(cmpLoc[i], NOESEEK_ABS)  
        bs.readBytes(4)
        nameID = bs.readUInt()
        #if cmpType[i] != 0xCCCCFF01:
        #    if nameID <= len(file_comps):# and cmpType[i] == 0xCCCC0B00:
        #        #print(""+str(hex(nameID))+" "+file_comps[nameID]+" "+hex(bs.tell()-0x0C))
        #        continue
        
        
    for i in range(0,len(cmpType)):
            
        
        bs.seek(cmpLoc[i], NOESEEK_ABS)
        facedir = 0
        if cmpType[i] == 0xCCCC0100:
            #We are a bone!!!
            nameID = cmpNameID[i]
            boneID = skeletonlist.index(file_comps[nameID])
            b = bonelist[boneID]
            #b = NoeBone(len(bonelist),file_comps[nameID],NoeMat43(( NoeVec3((1.0, 0.0, 0.0)), NoeVec3((0.0, 1.0, 0.0)), NoeVec3((0.0, 0.0, 1.0)), NoeVec3((0.0, 1.0, 0.0 )) ) ))
            l = bs.readUInt()
            bs.readUInt() #name stuff we already read
            parentname = bs.readUInt()
            boneparentlist.append(parentname)
            meshname = bs.readUInt()
            bonemdllist.append(meshname)
            shadowname = bs.readUInt()
            #b.parentIndex = boneparentlist.index(parentname)
            b.parentName  = file_comps[parentname]
            #print(file_comps[nameID],file_comps[parentname],file_comps[meshname],hex(b.parentIndex),hex(bonenamelist[bonenamelist.index(parentname)]))
            
            #bonelist.append(b)
            #print(hex(len(bonelist)))
            #bonelist = rapi.multiplyBones(bonelist)
        elif cmpType[i] == 0xCCCC0800:
            trans = NoeMat43((NoeVec3((1, 0, 0)),
                             NoeVec3((0, 0, 1)),
                             NoeVec3((0, -1, 0)),
                             NoeVec3((0, 0, 0))))
            rapi.rpgSetTransform(trans)
            #For testing, we will continue here to dummy out this code
            #continue
            boneweight = []
            boneidx    = []
            
            nameID = cmpNameID[i]
            if bs.readInt() <= 5:
                #print("Bone Model")
                #print(file_comps[nameID],hex(bs.tell()), hex(nameID, ))
                bonemdllist.append(nameID)
                continue
            #print(file_comps[nameID],hex(bs.tell()))
            bs.readUInt()
            scale = bs.readFloat()
            #print(scale)
            rapi.rpgSetPosScaleBias((scale/1,scale/1,scale/1),(0,0,0))
            meshType = bs.readByte()
            meshtype2 = bs.readByte()
            mcount = bs.readUShort()
            #print(""+file_comps[nameID]+" "+hex(bs.tell()))
            if meshType == 0x05:
                #print("skipping, 0x05 type")
                #mdlmat.append(0)
                #continue   
                
                
                #
                bs.readUInt()
                bs.readBytes(0x04) #for now I don't know what this is.
                #bs.readBytes(4)
                #some_pointer_crap = bs.readUInt()
                #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
                #    continue
                
                #rapi.rpgSetName(file_comps[nameID])
                bone = []
                #print(hex(mcount))
                rapi.multiplyBones(bonelist)
                for mesh in range(0,mcount):
                    rapi.rpgSetName(file_comps[nameID])#+str(mesh))
                    if (meshtype2 == 0x06):
                        rapi.rpgSetName(file_comps[nameID]+"_Morph_"+str(mesh))
                    clut = bs.readUInt()
                    #rapi.rpgSetMaterial(file_comps[clut])
                    #
                    
                    verts2 = bytearray()
                    uvs2 = []
                    #if vcount <= totalVerts: #to prevent potential negative vcounts
                    #    totalVerts = 0
                    #if vcount > 0xFFFF:
                        
                        #print("skipping, too many verts")
                    #    continue
                    if(mesh==mcount-1):
                        #print("CCA count", hex(cmpType.count(0xCCCC0A00)))
                        print("Last!" , hex(bs.tell()))
                        #continue
                        rapi.rpgSetName(file_comps[nameID]+"_TEST")
                        uvcount = bs.readUInt()
                        vcount = bs.readUInt()
                        noUVflag = 0
                        half = []
                        if(vcount == 0):
                            vcount = uvcount
                            noUVflag = 1
                        #bs.readBytes(0x04)                        
                        print("Vertex",hex(bs.tell()), vcount)
                        for v in range(0,vcount):
                            verts2 += bs.readBytes(6) #positions
                            #uvs2 += bs.readBytes(2)
                            #half = bytearray()
                            #half+=struct.pack('B', 0)
                            #half+=struct.pack('B', 0)
                            #half+=bs.readBytes(2)
                            #print(float(half))
                            #half = struct.pack('s'*len(half), *half)
                            #print("\x00\x00"+bs.readBytes(2))
                            #half = struct.pack('s'*4, *half))
                            if(noUVflag == 0):
                                half.append(bs.readUShort())
                                #b1 = bs.readUByte()# * 0x10000
                                #b2 = bs.readUByte()
                                #print(hex(b1))
                                #print(file_comps[b2])
                            #half2 = struct.pack('>H', half)
                            #half = (struct.unpack('H', half2))[0]
                            #print(file_comps[half])
                        #print("H > UVs",max(half) > uvcount)
                        print("Mysterious",hex(bs.tell()))
                        if bs.tell() % 4 == 2:
                            bs.readBytes(2) #we MUST be 4byte aligned!
                        #mystery flags for triwinding
                        mystery = []
                        for f in range(0,vcount-3):
                            mystery.append(bs.readBytes(4))
                        #bs.readBytes(vcount*4) #colors
                        
                        print("UV",hex(bs.tell()))
                        print(hex(bs.readUInt()),hex(bs.readUInt()),hex(bs.readUInt()))
                        print("UV",uvcount*2)
                        if(noUVflag == 0):
                            for w in range(0, uvcount*2):
                                #uvs2 = bs.readBytes(uvcount*4) #UVs
                                uvs2.append(bs.readUShort()) #UVs
                                #print(uvs2[len(uvs2)-1])
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                        else:
                            for w in range(0, vcount*2):
                                #uvs2 = bs.readBytes(uvcount*4) #UVs
                                uvs2.append(bs.readUShort()) #UVs
                                #print(uvs2[len(uvs2)-1])
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                        if(vcount>uvcount):
                            for w in range(0, (vcount-uvcount)*2):
                                uvs2.append(0x0000)
                        print(hex(bs.tell()))
                        print(len(verts2))
                        #print(hex(bs.tell()))
                        normBuff = []#bytearray()
                        for nrm in range(0,len(mystery)):
                            #normBuff+=struct.pack('B'*3, mystery[nrm][0],mystery[nrm][1],mystery[nrm][2])
                            normBuff.append((mystery[nrm][0]*65535))
                            normBuff.append((mystery[nrm][1]*65535))
                            normBuff.append((mystery[nrm][2]*65535))
                        normBuff = struct.pack('I'*len(normBuff),*normBuff)
                        uvs2 = struct.pack('H'*len(uvs2), *uvs2)
                        rapi.rpgBindPositionBuffer(verts2, noesis.RPGEODATA_SHORT, 6)
                        rapi.rpgBindUV1Buffer(uvs2, noesis.RPGEODATA_USHORT, 4)
                        #rapi.rpgBindNormalBuffer(normBuff, noesis.RPGEODATA_UINT, 4)
                        
                        rapi.rpgSetUVScaleBias(NoeVec3((256,256,0)),NoeVec3((0,0,0)))
                        
                        tmp2 = []
                        prevflag = 0
                        #facedir = 0
                        for f in range(2, vcount-0-3):
                            # if(f==0):
                                # tmp2.append(f)
                                # tmp2.append(f)
                                
                            # tmp2.append(f)
                            #if(f<71 or f> 84):continue
                            flag = mystery[f][3]
                            #flag = 0
                            #print(mystery[f][3])
                            if(mystery[f-1][3]!=flag and mystery[f-2][3]==1):
                                facedir = 1 - facedir
                            if (flag == 0x00):
                                if (facedir) == 0:
                                    tmp2.append(f - 2)
                                    tmp2.append(f - 1)
                                    tmp2.append(f)
                                else:
                                    tmp2.append(f - 1)
                                    tmp2.append(f - 2)
                                    tmp2.append(f)
                                facedir = 1 - facedir
                            ###############################
                            # flag = mystery[f][3]
                            # #print(f,f-1,f-2)
                            # #flag = 0
                            # if (flag == 0x00):
                                # if (facedir) == 0:
                                    # tmp2.append(f - 2)
                                    # tmp2.append(f - 1)
                                    # tmp2.append(f)
                                # else:
                                    # tmp2.append(f - 1)
                                    # tmp2.append(f - 2)
                                    # tmp2.append(f)
                                # facedir = 1 - facedir
                            # elif(flag == 0x01):
                                # if(flag != mystery[f-1][3]):
                                    # facedir = 1 - facedir
                            # elif(flag == 0x02):
                                # facedir = 0
                            ###############################    
                                #facedir = 1 - facedir
                            #    if (facedir) == 0:
                            #        tmp2.append(i + 2)
                            #        tmp2.append(i + 1)
                            #        tmp2.append(i)
                            #    else:
                            #        tmp2.append(i + 1)
                            #        tmp2.append(i + 2)
                            #        tmp2.append(i)
                            #elif(flag == 0x02):
                            #    facedir = 0
                            #if i>0:
                            #    if mystery[i-1][3] == flag:
                            #        facedir = 1 - facedir
                            #print(len(tmp2))
                            '''
                            if i % 2 == 1:
                                tmp2.append(i)
                                tmp2.append(i+2)
                                tmp2.append(i+1)
                            else:
                                tmp2.append(i)
                                tmp2.append(i+1)
                                tmp2.append(i+2)
                            '''
                        #print(len(tmp2))
                        #print(*tmp2)
                        noesis.logPopup()
                        faceBuff = struct.pack('H'*len(tmp2), *tmp2)
                        rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                        rapi.rpgClearBufferBinds() 
                        #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
                        successful_loads+=1

                    else:
                        vcount = bs.readUInt()
                        bs.readBytes(0x04)
                        bone.append(bs.readUInt())
                        #print(bonenamelist)
                        #print("bone?", hex(bone[mesh]),file_comps[bone[mesh]])
                    #The order of vertex, UV, VColor, and Tridata may be wrong.
                        #print("Vertex",hex(bs.tell()), vcount)
                        verts = bs.readBytes(vcount*6) #positions
                        #print("Mysterious",hex(bs.tell()))
                        if bs.tell() % 4 == 2:
                            bs.readBytes(2) #we MUST be 4byte aligned!
                        #mystery flags for triwinding
                        mystery = []
                        for f in range(0,vcount):
                            mystery.append(bs.readBytes(4))
                            #print(bone[mesh])
                            boneidx.append(skeletonlist.index(file_comps[bone[mesh]]))
                            
                            #boneidx.append(mesh)
                            boneweight.append(1.0)
                        #bs.readBytes(vcount*4) #colors
                        normBuff = []#bytearray()
                        for nrm in range(0,len(mystery)):
                            #normBuff+=struct.pack('B'*3, mystery[nrm][0],mystery[nrm][1],mystery[nrm][2])
                            normBuff.append((mystery[nrm][1]/0x2))
                            normBuff.append((mystery[nrm][2]/0x2))
                            #normBuff.append((mystery[nrm][2]/255))
                        normBuff = struct.pack('f'*len(normBuff),*normBuff)
                        #print("UV",hex(bs.tell()))
                        uvs = bs.readBytes(vcount*4) #UVs
                        
                        #print("End of Mesh",hex(bs.tell()))
                        
                        #print(hex(bs.tell()))
                        rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
                        rapi.rpgBindUV1Buffer(uvs, noesis.RPGEODATA_USHORT, 4)
                        
                        #rapi.rpgBindNormalBuffer(normBuff, noesis.RPGEODATA_FLOAT, 4)
                        
                        rapi.rpgSetUVScaleBias(NoeVec3((256,256,0)),NoeVec3((0,0,0)))
                        
                        tmp2 = []
                        
                        #facedir = 0
                        for f in range(2, vcount):

                            
                            flag = mystery[f][3]
                            #flag = 0
                            if(mystery[f-1][3]!=flag and mystery[f-2][3]==1):
                                facedir = 1 - facedir
                            if (flag == 0x00):
                                if (facedir) == 0:
                                    tmp2.append(f - 2)
                                    tmp2.append(f - 1)
                                    tmp2.append(f)
                                else:
                                    tmp2.append(f - 1)
                                    tmp2.append(f - 2)
                                    tmp2.append(f)
                                facedir = 1 - facedir
                                #if(flag == mystery[f-1][3]):
                                #    facedir = 1 - facedir
                            #elif(flag == 0x01):
                            #    if(flag != mystery[f-1][3]):
                            #        facedir = 1 - facedir
                            #elif(flag == 0x02):
                            #    facedir = 0
                                #facedir = 1 - facedir
                            #    if (facedir) == 0:
                            #        tmp2.append(i + 2)
                            #        tmp2.append(i + 1)
                            #        tmp2.append(i)
                            #    else:
                            #        tmp2.append(i + 1)
                            #        tmp2.append(i + 2)
                            #        tmp2.append(i)
                            #elif(flag == 0x02):
                            #    facedir = 0
                            #if i>0:
                            #    if mystery[i-1][3] == flag:
                            #        facedir = 1 - facedir
                            #print(len(tmp2))
                            '''
                            if i % 2 == 1:
                                tmp2.append(i)
                                tmp2.append(i+2)
                                tmp2.append(i+1)
                            else:
                                tmp2.append(i)
                                tmp2.append(i+1)
                                tmp2.append(i+2)
                            '''
                        #print(len(tmp2))
                        noesis.logPopup()
                        faceBuff = struct.pack('H'*len(tmp2), *tmp2)
                        
                        weightbuff = struct.pack('f'*len(boneweight),*boneweight)
                        boneidxbuff = struct.pack('I'*len(boneidx),*boneidx)
                        
                        
                        rapi.rpgBindBoneIndexBuffer(boneidxbuff, noesis.RPGEODATA_UINT, 4, 1)
                        rapi.rpgBindBoneWeightBuffer(weightbuff, noesis.RPGEODATA_FLOAT, 4, 1)
                        
                        rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                        rapi.rpgClearBufferBinds() 
                        #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
                        successful_loads+=1
            elif meshType == 0x08:#We will deal with shadow meshes here.
                #Nulling this for testing
                continue
                
                bs.readBytes(0x08) #for now I don't know what this is.
                
                #some_pointer_crap = bs.readUInt()
                #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
                #    continue
                
                rapi.rpgSetName(file_comps[nameID])
                #bs.readBytes(4)
                vcount = bs.readUInt()
                tcount = bs.readUInt()
                if vcount <= totalVerts: #to prevent potential negative vcounts
                    totalVerts = 0
                if vcount > 0xFFFF:
                    
                    #print("skipping, too many verts")
                    continue
                verts = bs.readBytes(vcount*6) #positions
                #print(hex(bs.tell()))
                if bs.tell() % 4 == 2:
                    bs.readBytes(2) #we MUST be 4byte aligned!
                rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
                tmp = []
                tmp2 = []
                #print(hex(bs.tell()))
                for f in range(0,tcount):
                    tmp2.append(bs.readUInt())
                    
                
                #print(len(tmp2))
                noesis.logPopup()
                faceBuff = struct.pack('I'*len(tmp2), *tmp2)
                #faceBuff = bs.readBytes(tcount*4) #tris
                rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_UINT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                rapi.rpgClearBufferBinds() 
                #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
                successful_loads+=1
                    
            else:#if meshType == 0x01 or meshType == 0x00:#We will deal with static meshes here.
                #print(meshType)    
                #continue
                #mdlmat = bs.readUInt()
                bs.readUInt()
                #print("70",hex(bs.tell()))
                bs.readUInt()#0x70
                for mesh in range(0,mcount):
                    bs.readUInt() #for now I don't know what this is.
                    #some_pointer_crap = bs.readUInt()
                    #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
                    #    continue
                    
                    rapi.rpgSetName(file_comps[nameID])#+str(mesh))
                    if (meshtype2 == 0x06):
                        rapi.rpgSetName(file_comps[nameID]+"_Morph_"+str(mesh))
                    #print(file_comps[nameID]+str(mesh),hex(bs.tell()))
                    mdlmat = bs.readUInt()
                    #bs.readUInt()
                    vcount = bs.readUInt()
                    if vcount <= totalVerts: #to prevent potential negative vcounts
                        totalVerts = 0
                    if vcount > 0xFFFF:
                        
                        #print("skipping, too many verts")
                        continue
                    print(file_comps[mdlmat])
                    #rapi.rpgSetMaterial(file_comps[mdlmat])
                    #The order of vertex, UV, VColor, and Tridata may be wrong.
                    #print(hex(bs.tell()), vcount)
                    verts = bs.readBytes(vcount*6) #positions
                    #print(hex(bs.tell()))
                    if bs.tell() % 4 == 2:
                        bs.readBytes(2) #we MUST be 4byte aligned!
                    #mystery flags for triwinding
                    mystery = []
                    for f in range(0,vcount):
                        mystery.append(bs.readBytes(4))
                    colors = bs.readBytes(vcount*4) #colors
                    
                    #print(hex(bs.tell()))
                    uvs = bs.readBytes(vcount*4) #UVs
                    
                    
                    #print(hex(bs.tell()))
                    rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
                    
                    if (meshtype2 != 0x06):
                        rapi.rpgBindUV1Buffer(uvs, noesis.RPGEODATA_USHORT, 4)
                        rapi.rpgBindColorBuffer(colors, noesis.RPGEODATA_UBYTE, 4, 3)
                        rapi.rpgSetUVScaleBias(NoeVec3((256,256,0)),NoeVec3((0,0,0)))
                    
                    tmp2 = []
                    
                    #facedir = 0
                    # This section is good. ###############################
                    #print(file_comps[nameID])
                    for f in range(2, vcount):
                        
                        flag = mystery[f][3]
                        flag1 = mystery[f-1][3]
                        flag2 = mystery[f-2][3]
                        flag3 = mystery[f-3][3]
                        flag3 = mystery[f-4][3]
                        """
                        #print(flag2,flag1,flag)
                        #flag = 0
                        facedir = 1 - facedir
                        if( flag1==1):
                            facedir = 1# - facedir
                        #if(f<vcount-1):
                        #    if(flag3==1 and ):
                        #        facedir = 1-facedir
                        #el
                        #else:
                        #    facedir = 1-facedir
                        #if(flag2==1 and flag1==0):
                        #    facedir = 1 - facedir
                        
                        if (flag == 0x00):
                            
                            #print(flag3,flag2,flag1,flag)
                            #if(flag3==):
                                #facedir = 1 - facedir
                            if (facedir) == 1:
                                tmp2.append(f - 2)
                                tmp2.append(f - 1)
                                tmp2.append(f)
                            else:
                                tmp2.append(f - 1)
                                tmp2.append(f - 2)
                                tmp2.append(f)
                        # This section is good. ###############################
                        """
                    
                    rapi.rpgSetStripEnder(0xFFFF)
                    tmp2.append(0)
                    tmp2.append(1)
                    on=1
                    for f in range(2,vcount):
                        #tmp2.append(f)
                        if(f<vcount-2 and f>1):
                            if(mystery[f+1][3]==1 and mystery[f][3]==1 ):
                                tmp2.append(0xFFFF)
                                #on=1-on
                                #tmp2.append(f)
                                #rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD,on)
                        tmp2.append(f)
                    rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)
                    #print(len(tmp2))
                    noesis.logPopup()
                    faceBuff = struct.pack('H'*len(tmp2), *tmp2)
                    rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE_STRIP, 1)
                    #rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                    rapi.rpgClearBufferBinds() 
                    #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
                    successful_loads+=1
        elif cmpType[i] == 0xCCCC0900:
            #print("CC9 name",file_comps[bs.readUInt()])
            bs.readUInt()
            bs.readUInt()
            length = bs.readUInt()
            for l in range(0,length):
                #print(file_comps[bs.readUInt()])
                bnm = bs.readUInt()
                #print("BNM",hex(bnm),file_comps[bnm])
                b = NoeBone(l,file_comps[bnm],NoeMat43(( NoeVec3((1.0, 0.0, 0.0)), NoeVec3((0.0, 1.0, 0.0)), NoeVec3((0.0, 0.0, 1.0)), NoeVec3((0.0, 0.0, 0.0 )) ) ))
                
                skeletonlist.append(file_comps[bnm])
                
                bonelist.append(b)
            #print(skeletonlist)
        #elif cmpType[i] == 0xCCCC0A00:
            #bonenamelist.append(cmpNameID[i])
        
        elif cmpType[i] == 0xCCCC0B00:
            #continue
            #HIT type models consist of geometry stored in floats
            #this geometry is proven to be the floor and wall collision of maps
            #it may also contain some UV data and be a renderable object in the game
            #as MDL data does not seem to exist for certain parts of maps.
            rapi.rpgSetPosScaleBias((1/8,1/8,1/8),(0,0,0))
            bs.readBytes(4)
            nameID = bs.readUInt()
            #nameID = cmpNameID[i]
            print(file_comps[nameID],hex(bs.tell()))
            unknown_ref = bs.readUInt()
            #print(file_comps[unknown_ref])
            for a in range(0,len(cmpNameID)-1):
                if(cmpNameID[a] == unknown_ref):
                    print(hex(cmpLoc[a]))
            numHits = bs.readUInt()
            bs.readBytes(4) #??
            for a in range(0,numHits):
                
                vcount = bs.readUInt()
                bs.readBytes(0x04)
                print(vcount,hex(bs.tell()))
                rapi.rpgSetName(file_comps[nameID])
                
                verts = bs.readBytes(vcount*0x18)
                
                rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_FLOAT, 0x0C)
                tmp2 = []
                wind = 1
                '''for a in range(0,(2*vcount)-2):
                    tmp2.append(a)
                    tmp2.append(a+1+wind)
                    tmp2.append(a+2-wind)
                    wind = 1 - wind'''
                for a in range(0,vcount):
                    tmp2.append(a)
                faceBuff = struct.pack('H'*len(tmp2), *tmp2)
                rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                print(hex(bs.tell()))
                successful_loads+=1
        else:
            continue
        
    if successful_loads > 0:
        
        mdl = rapi.rpgConstructModel()
        mdl.setBones(bonelist)
        mdl.setModelMaterials(NoeModelMaterials(texlist,matlist))
        mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList
        #rapi.rpgReset()

        
        #VertBuff = []
        #vcount = 0

        
       
    return 1
    

    
```


Older datestamp.

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
    handle = noesis.register(".hack//IMOQ, .hack//FGMT", ".cmp")
    noesis.setHandlerTypeCheck(handle, imoqCheckType)
    noesis.setHandlerLoadModel(handle, imoqLoadModel) #see also noepyLoadModelRPG
        #noesis.setHandlerWriteModel(handle, noepyWriteModel)
        #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
    noesis.logPopup()
        #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
    return 1

CCS_HEADER = 0xCCCC0001

#check if it's this type based on the data
def imoqCheckType(data):
    bs = NoeBitStream(data)
    if len(data) < 16:
        return 0
    if bs.readUInt() != CCS_HEADER:
        return 0
    #print("check pass")
    return 1         

#load the model
def imoqLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    
    
    successful_loads = 0
    
    mdl_loc = []
    file_paths = []
    file_comps = []
    comp_owner = []
    
    #read the main file name
    bs.seek(0x0C, NOESEEK_ABS)
    cmp_name = bs.readBytes(0x20).decode("ASCII").rstrip("\0")
    
    #read subfile path/names...
    #first reading how many files and components there will be...
    bs.seek(0x44, NOESEEK_ABS)
    num_files = bs.readUInt()
    num_comps = bs.readUInt()
    
    bs.seek(0x20, NOESEEK_REL)
    #Now grab the paths
    for i in range(0,num_files-1):
        file_paths.append(bs.readBytes(0x20).decode("ASCII").rstrip("\0"))
    #print("filepaths done"+hex(bs.tell()))
    #skip the empty path entry padding
    #bs.seek(0x20, NOESEEK_REL)
    
    #now we read the names of each component of the previously named files, and memorize to which file they belong
    for i in range(0,num_comps-0):
    #.decode("ASCII") is obvious, but .rstrip("\0") is less so. It cuts the 00 00 00 off the end of the string
        file_comps.append(bs.readBytes(0x1E).decode("Shift_JIS").rstrip("\0"))
        comp_owner.append(bs.readUShort())
    #print("comp names done"+hex(bs.tell()))
        #Don't print anything with shift_jis encoding... it crashes noesis

    #Find the MDL markers, 0x00 08 CC CC :: Old way. 
    '''while(bs.getOffset()<len(data)):
        if bs.readUInt() == 0xCCCC0800:
            mdl_loc.append(bs.getOffset())'''
    #Find MDLs and components, intelligently. :: New way
    bs.readBytes(0x08) #unknown
    #print(hex(bs.tell()))
    cmpLoc = []
    cmpType = []
    cmpLength = []
    #for i in range(0,num_comps):
    while(bs.getOffset()<len(data)):    
        checking = bs.readUInt()
        if checking & 0xCCCC0000 == 0xCCCC0000:
            cmpType.append(checking)
        #cmpType.append(bs.readUInt())
        #if cmpType[i] & 0xCCCC0000 != 0xCCCC0000:
        #    noesis.logPopup
        #    print(hex(bs.tell()))
        #    return 0
            cmpLoc.append(bs.tell())
            cmpLength.append(bs.readUInt())
        
        #bs.seek(cmpLength[i]*4,NOESEEK_REL)
        
    totalVerts = 0 #we will track how many verts have been iterated
    print(1)
    #for every model marker found, attempt to load vertices...
    for i in range(0,len(cmpType)):
        
        trans = NoeMat43((NoeVec3((1, 0, 0)),
                         NoeVec3((0, 0, 1)),
                         NoeVec3((0, -1, 0)),
                         NoeVec3((0, 0, 0))))
        rapi.rpgSetTransform(trans)
    
    #if 1==1:
        bs.seek(cmpLoc[i], NOESEEK_ABS)
        if cmpType[i] != 0xCCCC0800:
            continue
        elif bs.readInt() <= 5:
            
            print("skipping, too short")
            continue
        print(2)
        nameID = bs.readUInt()
        bs.readBytes(4)
        meshType = bs.readUShort()
        might_be_parent_or_bone_count = bs.readUShort()
        if meshType == 0x05:
            #print("skipping, type")
            continue #right now we're ignoring shadow 0x08, and actor 0x05 types.
        elif meshType == 0x08:#We will deal with shadow meshes here.
        
            bs.readBytes(0x08) #for now I don't know what this is.
            
            #some_pointer_crap = bs.readUInt()
            #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
            #    continue
            
            rapi.rpgSetName(file_comps[nameID])
            #bs.readBytes(4)
            vcount = bs.readUInt()
            tcount = bs.readUInt()
            if vcount <= totalVerts: #to prevent potential negative vcounts
                totalVerts = 0
            if vcount > 0xFFFF:
                
                #print("skipping, too many verts")
                continue
            verts = bs.readBytes(vcount*6) #positions
            #print(hex(bs.tell()))
            if bs.tell() % 4 == 2:
                bs.readBytes(2) #we MUST be 4byte aligned!
            rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
            tmp = []
            tmp2 = []
            print(hex(bs.tell()))
            for i in range(0,tcount):
                tmp2.append(bs.readUInt())
                
            
            print(len(tmp2))
            noesis.logPopup()
            faceBuff = struct.pack('I'*len(tmp2), *tmp2)
            #faceBuff = bs.readBytes(tcount*4) #tris
            rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_UINT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
            rapi.rpgClearBufferBinds() 
            #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
            successful_loads+=1
                
        else:#if meshType == 0x01 or meshType == 0x00:#We will deal with static meshes here.
            #print(meshType)    
            
            
            bs.readBytes(0x0C) #for now I don't know what this is.
            
            #some_pointer_crap = bs.readUInt()
            #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
            #    continue
            
            rapi.rpgSetName(file_comps[nameID])
            bs.readBytes(4)
            vcount = bs.readUInt()
            if vcount <= totalVerts: #to prevent potential negative vcounts
                totalVerts = 0
            if vcount > 0xFFFF:
                
                #print("skipping, too many verts")
                continue
            #It is possible that vcount is cumulative for some meshes
            #Leading to the potential for vcounts larger than available vertices
            #vcount -= totalVerts
            
            #testing
            #if mdl_loc[i] == 0x4e3e4 or mdl_loc[i] == 0x4e3e0:
            #    continue
            #print(vcount)
            '''VertBuff = bs.readBytes(vcount*6)
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 6, 0)
            rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
            '''
            
            
            
            #for i in range(0,vcount):
                #rapi.immBegin(noesis.RPGEO_TRIANGLE)
                #rapi.immVertex3((bs.read("hhh")))
                #rapi.immEnd()
            #The order of vertex, UV, VColor, and Tridata may be wrong.
            #print(hex(bs.tell()))
            verts = bs.readBytes(vcount*6) #positions
            #print(hex(bs.tell()))
            if bs.tell() % 4 == 2:
                bs.readBytes(2) #we MUST be 4byte aligned!
            #mystery flags for triwinding
            mystery = []
            for i in range(0,vcount):
                mystery.append(bs.readBytes(4))
            bs.readBytes(vcount*4) #colors
            
            #print(hex(bs.tell()))
            uvs = bs.readBytes(vcount*4) #UVs
            
            
            #print(hex(bs.tell()))
            rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
            rapi.rpgBindUV1Buffer(uvs, noesis.RPGEODATA_USHORT, 4)
            
            rapi.rpgSetUVScaleBias(NoeVec3((256,256,0)),NoeVec3((0,0,0)))
            
            tmp2 = []
            
            facedir = 0
            for i in range(2, vcount):

                
                flag = mystery[i][3]
                #flag = 0
                if (flag == 0x00):
                    if (facedir) == 1:
                        tmp2.append(i - 2)
                        tmp2.append(i - 1)
                        tmp2.append(i)
                    else:
                        tmp2.append(i - 1)
                        tmp2.append(i - 2)
                        tmp2.append(i)
                    facedir = 1 - facedir
                #elif(flag == 0x01):
                #    facedir = 0
                    
                    #facedir = 1 - facedir
                #    if (facedir) == 0:
                #        tmp2.append(i + 2)
                #        tmp2.append(i + 1)
                #        tmp2.append(i)
                #    else:
                #        tmp2.append(i + 1)
                #        tmp2.append(i + 2)
                #        tmp2.append(i)
                #elif(flag == 0x02):
                #    facedir = 0
                #if i>0:
                #    if mystery[i-1][3] == flag:
                #        facedir = 1 - facedir
                #print(len(tmp2))
                '''
                if i % 2 == 1:
                    tmp2.append(i)
                    tmp2.append(i+2)
                    tmp2.append(i+1)
                else:
                    tmp2.append(i)
                    tmp2.append(i+1)
                    tmp2.append(i+2)
                '''
            print(len(tmp2))
            noesis.logPopup()
            faceBuff = struct.pack('H'*len(tmp2), *tmp2)
            rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
            rapi.rpgClearBufferBinds() 
            #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
            successful_loads+=1
    if successful_loads > 0:
        mdl = rapi.rpgConstructModel()
        mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList
        #rapi.rpgReset()
    
        
        #VertBuff = []
        #vcount = 0

        
       
    return 1
    

    
```


I had them both enabled in noesis because I was testing them... but I don't know what's what anymore. Sorry again.
## Post #6
- Username: namine207
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 16, 2017 11:04 am
- Post datetime: 2017-04-10T23:14:29+00:00
- Post Title: CCS File Format (Dot Hack)

> Reply from Satoh
>
> I got your messages... albeit I'm not here very actively anymore but I show up on rare occasions... I'm hesitant to release this because honestly its kind of crap, and I don't remember how any of it works or even which of these is the correct file... but I do have a script that imports scene geometry and come character geometry, but without bone information.

The files are somewhat different in format between scene and character though, so there's something you have to un/comment out when trying to switch between one or the other.... I'm sorry I can't tell you which.

I apologize because the code is a wreck that even I can't explain, but it one of them does accomplish some things. I don't have time right now to clean it up for you, but if you're interested in working on the format, I figure more disclosure is better than less, even if you can't make sense of it, there's still a better chance than if I kept it to myself.
Does NOT work on GU as they are a newer CCS/CMP format.

You need to unzip the .CCS archives and run noesis on the T/CMP.
.CCS archives for GU and IMOQ and Fragment are simple GZip archives that 7zip should readily handle with the 'unpack archive' option.

I apologize for the size, but I can't find a way to spoiler this.

Newer Datestamp
Code: Select all#CCS CMP model importer

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
    handle = noesis.register(".hack//IMOQ, .hack//FGMT", ".cmp")
    noesis.setHandlerTypeCheck(handle, imoqCheckType)
    noesis.setHandlerLoadModel(handle, imoqLoadModel) #see also noepyLoadModelRPG
        #noesis.setHandlerWriteModel(handle, noepyWriteModel)
        #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
    #noesis.logPopup()
        #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
    return 1

CCS_HEADER = 0xCCCC0001

#check if it's this type based on the data
def imoqCheckType(data):
    bs = NoeBitStream(data)
    if len(data) < 16:
        return 0
    if bs.readUInt() != CCS_HEADER:
        return 0
    #print("check pass")
    return 1         

#load the model
def imoqLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    
    
    successful_loads = 0
    
    mdl_loc = []
    file_paths = []
    file_comps = []
    comp_owner = []
    
    #read the main file name
    bs.seek(0x0C, NOESEEK_ABS)
    cmp_name = bs.readBytes(0x20).decode("ASCII").rstrip("\0")
    
    #read subfile path/names...
    #first reading how many files and components there will be...
    bs.seek(0x44, NOESEEK_ABS)
    num_files = bs.readUInt()
    num_comps = bs.readUInt()
    
    bs.seek(0x20, NOESEEK_REL)
    #Now grab the paths
    for i in range(0,num_files-1):
        file_paths.append(bs.readBytes(0x20).decode("ASCII").rstrip("\0"))
    #print("filepaths done"+hex(bs.tell()))
    #skip the empty path entry padding
    #bs.seek(0x20, NOESEEK_REL)
    
    #now we read the names of each component of the previously named files, and memorize to which file they belong
    for i in range(0,num_comps-0):
    #.decode("ASCII") is obvious, but .rstrip("\0") is less so. It cuts the 00 00 00 off the end of the string
        file_comps.append(bs.readBytes(0x1E).decode("Shift_JIS").rstrip("\0"))
        comp_owner.append(bs.readUShort())
    #print("comp names done"+hex(bs.tell()))
        #Don't print anything with shift_jis encoding... it crashes noesis

    #Find the MDL markers, 0x00 08 CC CC :: Old way. 
    '''while(bs.getOffset()<len(data)):
        if bs.readUInt() == 0xCCCC0800:
            mdl_loc.append(bs.getOffset())'''
    #Find MDLs and components, intelligently. :: New way
    bs.readBytes(0x08) #unknown
    #print(hex(bs.tell()))
    cmpLoc = []
    cmpType = []
    cmpLength = []
    cmpNameID = []
    matlist = []
    texlist = []
    cltlist = []
    mdlmat = []
    bonelist = []
    boneparentlist = []
    bonemdllist = [0]
    skeletonlist = []
    
    #for i in range(0,num_comps):
    while(bs.getOffset()<len(data)):    
        checking = bs.readUInt()
        if checking & 0xCCCC0000 == 0xCCCC0000 and checking <= 0xCCCCFFFF:
            cmpType.append(checking)
            #print(hex(checking))
        #cmpType.append(bs.readUInt())
        #if cmpType[i] & 0xCCCC0000 != 0xCCCC0000:
        #    noesis.logPopup
        #    print(hex(bs.tell()))
        #    return 0
            cmpLoc.append(bs.tell())
            cmpLength.append(bs.readUInt())
            cmpNameID.append(bs.readUInt())
        
        #bs.seek(cmpLength[i]*4,NOESEEK_REL)
        
    totalVerts = 0 #we will track how many verts have been iterated
    #print(1)
    #for every model marker found, attempt to load vertices...
    """
    for i in range(0,len(cmpType)):

    
    #if 1==1:
        bs.seek(cmpLoc[i], NOESEEK_ABS)
        if cmpType[i] == 0xCCCC0200:
            #if(len(matlist)==217):
                #print("This is the errorindex", hex(bs.tell()))
            print(""+hex(bs.tell())+" Mat")
            #t = loadTEX(texofs[i],bs)
            #texlist.append(NoeTexture(rapi.getExtensionlessName(rapi.getLocalFileName(rapi.getInputName()))+"_"+str(i), t[1], t[2], t[0], noesis.NOESISTEX_RGBA32))
            #loadTIM(texofs[i],bs,texlist)
            bs.readBytes(0x08) #skip some stuff
            texidx = bs.readUInt()
            tmpmat = 0
            textmp = 0
            paltmp = 0
            #print(hex(bs.tell()))
            somefloat = bs.readFloat()
            blendmode = bs.readUInt()
            #print("blend",hex(blendmode), hex(bs.tell()-4))
            for a in range(0,len(cmpType)):
                if cmpType[a] == 0xCCCC0300 and cmpNameID[a] == texidx:
                
                    #load texture
                    #textmp = getTex()
                    
                    
                    bs.seek(cmpLoc[a],NOESEEK_ABS)
                    #print(""+hex(bs.tell())+" Tex")
                    bs.readBytes(4) #ignore some things
                    texname = bs.readUInt()
                    #print(file_comps[texname])
                    cltidx = bs.readUInt()
                    bs.readBytes(8) #unknown
                    w = 2 ** bs.readByte()
                    h = 2 ** bs.readByte()
                    bs.readBytes(6) #unknown
                    l = bs.readUInt() * 4
                    #print(w,h,hex(l))
                    pix = bs.readBytes(l)
                    clut = 0
                    for b in range(0,len(cmpType)):
                        if cmpType[b] == 0xCCCC0400 and cmpNameID[b] == cltidx:
                            bs.seek(cmpLoc[b],NOESEEK_ABS)
                            #print(""+hex(bs.tell())+" Clut")
                            #continue
                    bs.readBytes(8)#ignore some stuff
                    bs.readBytes(0x0C)#unknown
                    cl = bs.readUInt()
                    clut = []
                    
                    for b in range(0,cl*4):
                        if(b>0):
                            if((b)%4==0):
                                clut.append(max(0,(bs.readUByte()*2)-1)&0xFF)
                                #print(clut[b-1])
                                #clut.append(bs.readUByte())
                            else:
                                clut.append(bs.readUByte())
                                #print(clut[b-1])
                    clut = struct.pack('B'*len(clut),*clut)
                    textmp = rapi.imageDecodeRawPal(pix,clut,w,h,8,"r8g8b8a8")
                    texlist.append(NoeTexture(file_comps[texname], w, h, textmp, noesis.NOESISTEX_RGBA32))
                    #print ("Material:", file_comps[cmpNameID[i]])
                    tmpmat = NoeMaterial(file_comps[cmpNameID[i]],file_comps[texidx])
                    #print(file_comps[cmpNameID[i]])
                    tmpmat.setTexture(file_comps[texname])
                    if(blendmode == 0x10000000):
                        tmpmat.setBlendMode(noesis.NOEBLEND_SRC_ALPHA,noesis.NOEBLEND_ONE)
                    #tmpmat.setFlags(0,1)
                    #______tmpmat.setTexture(texlist[i])
                    #rapi.rpgSetMaterial("mat_"+str(i))
                    
            #nameidx = bs.readUInt()
            matlist.append(tmpmat)
            """
    for i in range(0,len(cmpType)):
        bs.seek(cmpLoc[i], NOESEEK_ABS)  
        bs.readBytes(4)
        nameID = bs.readUInt()
        #if cmpType[i] != 0xCCCCFF01:
        #    if nameID <= len(file_comps):# and cmpType[i] == 0xCCCC0B00:
        #        #print(""+str(hex(nameID))+" "+file_comps[nameID]+" "+hex(bs.tell()-0x0C))
        #        continue
        
        
    for i in range(0,len(cmpType)):
            
        
        bs.seek(cmpLoc[i], NOESEEK_ABS)
        facedir = 0
        if cmpType[i] == 0xCCCC0100:
            #We are a bone!!!
            nameID = cmpNameID[i]
            boneID = skeletonlist.index(file_comps[nameID])
            b = bonelist[boneID]
            #b = NoeBone(len(bonelist),file_comps[nameID],NoeMat43(( NoeVec3((1.0, 0.0, 0.0)), NoeVec3((0.0, 1.0, 0.0)), NoeVec3((0.0, 0.0, 1.0)), NoeVec3((0.0, 1.0, 0.0 )) ) ))
            l = bs.readUInt()
            bs.readUInt() #name stuff we already read
            parentname = bs.readUInt()
            boneparentlist.append(parentname)
            meshname = bs.readUInt()
            bonemdllist.append(meshname)
            shadowname = bs.readUInt()
            #b.parentIndex = boneparentlist.index(parentname)
            b.parentName  = file_comps[parentname]
            #print(file_comps[nameID],file_comps[parentname],file_comps[meshname],hex(b.parentIndex),hex(bonenamelist[bonenamelist.index(parentname)]))
            
            #bonelist.append(b)
            #print(hex(len(bonelist)))
            #bonelist = rapi.multiplyBones(bonelist)
        elif cmpType[i] == 0xCCCC0800:
            trans = NoeMat43((NoeVec3((1, 0, 0)),
                             NoeVec3((0, 0, 1)),
                             NoeVec3((0, -1, 0)),
                             NoeVec3((0, 0, 0))))
            rapi.rpgSetTransform(trans)
            #For testing, we will continue here to dummy out this code
            #continue
            boneweight = []
            boneidx    = []
            
            nameID = cmpNameID[i]
            if bs.readInt() <= 5:
                #print("Bone Model")
                #print(file_comps[nameID],hex(bs.tell()), hex(nameID, ))
                bonemdllist.append(nameID)
                continue
            #print(file_comps[nameID],hex(bs.tell()))
            bs.readUInt()
            scale = bs.readFloat()
            #print(scale)
            rapi.rpgSetPosScaleBias((scale/1,scale/1,scale/1),(0,0,0))
            meshType = bs.readByte()
            meshtype2 = bs.readByte()
            mcount = bs.readUShort()
            #print(""+file_comps[nameID]+" "+hex(bs.tell()))
            if meshType == 0x05:
                #print("skipping, 0x05 type")
                #mdlmat.append(0)
                #continue   
                
                
                #
                bs.readUInt()
                bs.readBytes(0x04) #for now I don't know what this is.
                #bs.readBytes(4)
                #some_pointer_crap = bs.readUInt()
                #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
                #    continue
                
                #rapi.rpgSetName(file_comps[nameID])
                bone = []
                #print(hex(mcount))
                rapi.multiplyBones(bonelist)
                for mesh in range(0,mcount):
                    rapi.rpgSetName(file_comps[nameID])#+str(mesh))
                    if (meshtype2 == 0x06):
                        rapi.rpgSetName(file_comps[nameID]+"_Morph_"+str(mesh))
                    clut = bs.readUInt()
                    #rapi.rpgSetMaterial(file_comps[clut])
                    #
                    
                    verts2 = bytearray()
                    uvs2 = []
                    #if vcount <= totalVerts: #to prevent potential negative vcounts
                    #    totalVerts = 0
                    #if vcount > 0xFFFF:
                        
                        #print("skipping, too many verts")
                    #    continue
                    if(mesh==mcount-1):
                        #print("CCA count", hex(cmpType.count(0xCCCC0A00)))
                        print("Last!" , hex(bs.tell()))
                        #continue
                        rapi.rpgSetName(file_comps[nameID]+"_TEST")
                        uvcount = bs.readUInt()
                        vcount = bs.readUInt()
                        noUVflag = 0
                        half = []
                        if(vcount == 0):
                            vcount = uvcount
                            noUVflag = 1
                        #bs.readBytes(0x04)                        
                        print("Vertex",hex(bs.tell()), vcount)
                        for v in range(0,vcount):
                            verts2 += bs.readBytes(6) #positions
                            #uvs2 += bs.readBytes(2)
                            #half = bytearray()
                            #half+=struct.pack('B', 0)
                            #half+=struct.pack('B', 0)
                            #half+=bs.readBytes(2)
                            #print(float(half))
                            #half = struct.pack('s'*len(half), *half)
                            #print("\x00\x00"+bs.readBytes(2))
                            #half = struct.pack('s'*4, *half))
                            if(noUVflag == 0):
                                half.append(bs.readUShort())
                                #b1 = bs.readUByte()# * 0x10000
                                #b2 = bs.readUByte()
                                #print(hex(b1))
                                #print(file_comps[b2])
                            #half2 = struct.pack('>H', half)
                            #half = (struct.unpack('H', half2))[0]
                            #print(file_comps[half])
                        #print("H > UVs",max(half) > uvcount)
                        print("Mysterious",hex(bs.tell()))
                        if bs.tell() % 4 == 2:
                            bs.readBytes(2) #we MUST be 4byte aligned!
                        #mystery flags for triwinding
                        mystery = []
                        for f in range(0,vcount-3):
                            mystery.append(bs.readBytes(4))
                        #bs.readBytes(vcount*4) #colors
                        
                        print("UV",hex(bs.tell()))
                        print(hex(bs.readUInt()),hex(bs.readUInt()),hex(bs.readUInt()))
                        print("UV",uvcount*2)
                        if(noUVflag == 0):
                            for w in range(0, uvcount*2):
                                #uvs2 = bs.readBytes(uvcount*4) #UVs
                                uvs2.append(bs.readUShort()) #UVs
                                #print(uvs2[len(uvs2)-1])
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                        else:
                            for w in range(0, vcount*2):
                                #uvs2 = bs.readBytes(uvcount*4) #UVs
                                uvs2.append(bs.readUShort()) #UVs
                                #print(uvs2[len(uvs2)-1])
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                                # uvs2 += bytes(b" ")
                        if(vcount>uvcount):
                            for w in range(0, (vcount-uvcount)*2):
                                uvs2.append(0x0000)
                        print(hex(bs.tell()))
                        print(len(verts2))
                        #print(hex(bs.tell()))
                        normBuff = []#bytearray()
                        for nrm in range(0,len(mystery)):
                            #normBuff+=struct.pack('B'*3, mystery[nrm][0],mystery[nrm][1],mystery[nrm][2])
                            normBuff.append((mystery[nrm][0]*65535))
                            normBuff.append((mystery[nrm][1]*65535))
                            normBuff.append((mystery[nrm][2]*65535))
                        normBuff = struct.pack('I'*len(normBuff),*normBuff)
                        uvs2 = struct.pack('H'*len(uvs2), *uvs2)
                        rapi.rpgBindPositionBuffer(verts2, noesis.RPGEODATA_SHORT, 6)
                        rapi.rpgBindUV1Buffer(uvs2, noesis.RPGEODATA_USHORT, 4)
                        #rapi.rpgBindNormalBuffer(normBuff, noesis.RPGEODATA_UINT, 4)
                        
                        rapi.rpgSetUVScaleBias(NoeVec3((256,256,0)),NoeVec3((0,0,0)))
                        
                        tmp2 = []
                        prevflag = 0
                        #facedir = 0
                        for f in range(2, vcount-0-3):
                            # if(f==0):
                                # tmp2.append(f)
                                # tmp2.append(f)
                                
                            # tmp2.append(f)
                            #if(f<71 or f> 84):continue
                            flag = mystery[f][3]
                            #flag = 0
                            #print(mystery[f][3])
                            if(mystery[f-1][3]!=flag and mystery[f-2][3]==1):
                                facedir = 1 - facedir
                            if (flag == 0x00):
                                if (facedir) == 0:
                                    tmp2.append(f - 2)
                                    tmp2.append(f - 1)
                                    tmp2.append(f)
                                else:
                                    tmp2.append(f - 1)
                                    tmp2.append(f - 2)
                                    tmp2.append(f)
                                facedir = 1 - facedir
                            ###############################
                            # flag = mystery[f][3]
                            # #print(f,f-1,f-2)
                            # #flag = 0
                            # if (flag == 0x00):
                                # if (facedir) == 0:
                                    # tmp2.append(f - 2)
                                    # tmp2.append(f - 1)
                                    # tmp2.append(f)
                                # else:
                                    # tmp2.append(f - 1)
                                    # tmp2.append(f - 2)
                                    # tmp2.append(f)
                                # facedir = 1 - facedir
                            # elif(flag == 0x01):
                                # if(flag != mystery[f-1][3]):
                                    # facedir = 1 - facedir
                            # elif(flag == 0x02):
                                # facedir = 0
                            ###############################    
                                #facedir = 1 - facedir
                            #    if (facedir) == 0:
                            #        tmp2.append(i + 2)
                            #        tmp2.append(i + 1)
                            #        tmp2.append(i)
                            #    else:
                            #        tmp2.append(i + 1)
                            #        tmp2.append(i + 2)
                            #        tmp2.append(i)
                            #elif(flag == 0x02):
                            #    facedir = 0
                            #if i>0:
                            #    if mystery[i-1][3] == flag:
                            #        facedir = 1 - facedir
                            #print(len(tmp2))
                            '''
                            if i % 2 == 1:
                                tmp2.append(i)
                                tmp2.append(i+2)
                                tmp2.append(i+1)
                            else:
                                tmp2.append(i)
                                tmp2.append(i+1)
                                tmp2.append(i+2)
                            '''
                        #print(len(tmp2))
                        #print(*tmp2)
                        noesis.logPopup()
                        faceBuff = struct.pack('H'*len(tmp2), *tmp2)
                        rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                        rapi.rpgClearBufferBinds() 
                        #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
                        successful_loads+=1

                    else:
                        vcount = bs.readUInt()
                        bs.readBytes(0x04)
                        bone.append(bs.readUInt())
                        #print(bonenamelist)
                        #print("bone?", hex(bone[mesh]),file_comps[bone[mesh]])
                    #The order of vertex, UV, VColor, and Tridata may be wrong.
                        #print("Vertex",hex(bs.tell()), vcount)
                        verts = bs.readBytes(vcount*6) #positions
                        #print("Mysterious",hex(bs.tell()))
                        if bs.tell() % 4 == 2:
                            bs.readBytes(2) #we MUST be 4byte aligned!
                        #mystery flags for triwinding
                        mystery = []
                        for f in range(0,vcount):
                            mystery.append(bs.readBytes(4))
                            #print(bone[mesh])
                            boneidx.append(skeletonlist.index(file_comps[bone[mesh]]))
                            
                            #boneidx.append(mesh)
                            boneweight.append(1.0)
                        #bs.readBytes(vcount*4) #colors
                        normBuff = []#bytearray()
                        for nrm in range(0,len(mystery)):
                            #normBuff+=struct.pack('B'*3, mystery[nrm][0],mystery[nrm][1],mystery[nrm][2])
                            normBuff.append((mystery[nrm][1]/0x2))
                            normBuff.append((mystery[nrm][2]/0x2))
                            #normBuff.append((mystery[nrm][2]/255))
                        normBuff = struct.pack('f'*len(normBuff),*normBuff)
                        #print("UV",hex(bs.tell()))
                        uvs = bs.readBytes(vcount*4) #UVs
                        
                        #print("End of Mesh",hex(bs.tell()))
                        
                        #print(hex(bs.tell()))
                        rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
                        rapi.rpgBindUV1Buffer(uvs, noesis.RPGEODATA_USHORT, 4)
                        
                        #rapi.rpgBindNormalBuffer(normBuff, noesis.RPGEODATA_FLOAT, 4)
                        
                        rapi.rpgSetUVScaleBias(NoeVec3((256,256,0)),NoeVec3((0,0,0)))
                        
                        tmp2 = []
                        
                        #facedir = 0
                        for f in range(2, vcount):

                            
                            flag = mystery[f][3]
                            #flag = 0
                            if(mystery[f-1][3]!=flag and mystery[f-2][3]==1):
                                facedir = 1 - facedir
                            if (flag == 0x00):
                                if (facedir) == 0:
                                    tmp2.append(f - 2)
                                    tmp2.append(f - 1)
                                    tmp2.append(f)
                                else:
                                    tmp2.append(f - 1)
                                    tmp2.append(f - 2)
                                    tmp2.append(f)
                                facedir = 1 - facedir
                                #if(flag == mystery[f-1][3]):
                                #    facedir = 1 - facedir
                            #elif(flag == 0x01):
                            #    if(flag != mystery[f-1][3]):
                            #        facedir = 1 - facedir
                            #elif(flag == 0x02):
                            #    facedir = 0
                                #facedir = 1 - facedir
                            #    if (facedir) == 0:
                            #        tmp2.append(i + 2)
                            #        tmp2.append(i + 1)
                            #        tmp2.append(i)
                            #    else:
                            #        tmp2.append(i + 1)
                            #        tmp2.append(i + 2)
                            #        tmp2.append(i)
                            #elif(flag == 0x02):
                            #    facedir = 0
                            #if i>0:
                            #    if mystery[i-1][3] == flag:
                            #        facedir = 1 - facedir
                            #print(len(tmp2))
                            '''
                            if i % 2 == 1:
                                tmp2.append(i)
                                tmp2.append(i+2)
                                tmp2.append(i+1)
                            else:
                                tmp2.append(i)
                                tmp2.append(i+1)
                                tmp2.append(i+2)
                            '''
                        #print(len(tmp2))
                        noesis.logPopup()
                        faceBuff = struct.pack('H'*len(tmp2), *tmp2)
                        
                        weightbuff = struct.pack('f'*len(boneweight),*boneweight)
                        boneidxbuff = struct.pack('I'*len(boneidx),*boneidx)
                        
                        
                        rapi.rpgBindBoneIndexBuffer(boneidxbuff, noesis.RPGEODATA_UINT, 4, 1)
                        rapi.rpgBindBoneWeightBuffer(weightbuff, noesis.RPGEODATA_FLOAT, 4, 1)
                        
                        rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                        rapi.rpgClearBufferBinds() 
                        #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
                        successful_loads+=1
            elif meshType == 0x08:#We will deal with shadow meshes here.
                #Nulling this for testing
                continue
                
                bs.readBytes(0x08) #for now I don't know what this is.
                
                #some_pointer_crap = bs.readUInt()
                #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
                #    continue
                
                rapi.rpgSetName(file_comps[nameID])
                #bs.readBytes(4)
                vcount = bs.readUInt()
                tcount = bs.readUInt()
                if vcount <= totalVerts: #to prevent potential negative vcounts
                    totalVerts = 0
                if vcount > 0xFFFF:
                    
                    #print("skipping, too many verts")
                    continue
                verts = bs.readBytes(vcount*6) #positions
                #print(hex(bs.tell()))
                if bs.tell() % 4 == 2:
                    bs.readBytes(2) #we MUST be 4byte aligned!
                rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
                tmp = []
                tmp2 = []
                #print(hex(bs.tell()))
                for f in range(0,tcount):
                    tmp2.append(bs.readUInt())
                    
                
                #print(len(tmp2))
                noesis.logPopup()
                faceBuff = struct.pack('I'*len(tmp2), *tmp2)
                #faceBuff = bs.readBytes(tcount*4) #tris
                rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_UINT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                rapi.rpgClearBufferBinds() 
                #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
                successful_loads+=1
                    
            else:#if meshType == 0x01 or meshType == 0x00:#We will deal with static meshes here.
                #print(meshType)    
                #continue
                #mdlmat = bs.readUInt()
                bs.readUInt()
                #print("70",hex(bs.tell()))
                bs.readUInt()#0x70
                for mesh in range(0,mcount):
                    bs.readUInt() #for now I don't know what this is.
                    #some_pointer_crap = bs.readUInt()
                    #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
                    #    continue
                    
                    rapi.rpgSetName(file_comps[nameID])#+str(mesh))
                    if (meshtype2 == 0x06):
                        rapi.rpgSetName(file_comps[nameID]+"_Morph_"+str(mesh))
                    #print(file_comps[nameID]+str(mesh),hex(bs.tell()))
                    mdlmat = bs.readUInt()
                    #bs.readUInt()
                    vcount = bs.readUInt()
                    if vcount <= totalVerts: #to prevent potential negative vcounts
                        totalVerts = 0
                    if vcount > 0xFFFF:
                        
                        #print("skipping, too many verts")
                        continue
                    print(file_comps[mdlmat])
                    #rapi.rpgSetMaterial(file_comps[mdlmat])
                    #The order of vertex, UV, VColor, and Tridata may be wrong.
                    #print(hex(bs.tell()), vcount)
                    verts = bs.readBytes(vcount*6) #positions
                    #print(hex(bs.tell()))
                    if bs.tell() % 4 == 2:
                        bs.readBytes(2) #we MUST be 4byte aligned!
                    #mystery flags for triwinding
                    mystery = []
                    for f in range(0,vcount):
                        mystery.append(bs.readBytes(4))
                    colors = bs.readBytes(vcount*4) #colors
                    
                    #print(hex(bs.tell()))
                    uvs = bs.readBytes(vcount*4) #UVs
                    
                    
                    #print(hex(bs.tell()))
                    rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
                    
                    if (meshtype2 != 0x06):
                        rapi.rpgBindUV1Buffer(uvs, noesis.RPGEODATA_USHORT, 4)
                        rapi.rpgBindColorBuffer(colors, noesis.RPGEODATA_UBYTE, 4, 3)
                        rapi.rpgSetUVScaleBias(NoeVec3((256,256,0)),NoeVec3((0,0,0)))
                    
                    tmp2 = []
                    
                    #facedir = 0
                    # This section is good. ###############################
                    #print(file_comps[nameID])
                    for f in range(2, vcount):
                        
                        flag = mystery[f][3]
                        flag1 = mystery[f-1][3]
                        flag2 = mystery[f-2][3]
                        flag3 = mystery[f-3][3]
                        flag3 = mystery[f-4][3]
                        """
                        #print(flag2,flag1,flag)
                        #flag = 0
                        facedir = 1 - facedir
                        if( flag1==1):
                            facedir = 1# - facedir
                        #if(f<vcount-1):
                        #    if(flag3==1 and ):
                        #        facedir = 1-facedir
                        #el
                        #else:
                        #    facedir = 1-facedir
                        #if(flag2==1 and flag1==0):
                        #    facedir = 1 - facedir
                        
                        if (flag == 0x00):
                            
                            #print(flag3,flag2,flag1,flag)
                            #if(flag3==):
                                #facedir = 1 - facedir
                            if (facedir) == 1:
                                tmp2.append(f - 2)
                                tmp2.append(f - 1)
                                tmp2.append(f)
                            else:
                                tmp2.append(f - 1)
                                tmp2.append(f - 2)
                                tmp2.append(f)
                        # This section is good. ###############################
                        """
                    
                    rapi.rpgSetStripEnder(0xFFFF)
                    tmp2.append(0)
                    tmp2.append(1)
                    on=1
                    for f in range(2,vcount):
                        #tmp2.append(f)
                        if(f<vcount-2 and f>1):
                            if(mystery[f+1][3]==1 and mystery[f][3]==1 ):
                                tmp2.append(0xFFFF)
                                #on=1-on
                                #tmp2.append(f)
                                #rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD,on)
                        tmp2.append(f)
                    rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)
                    #print(len(tmp2))
                    noesis.logPopup()
                    faceBuff = struct.pack('H'*len(tmp2), *tmp2)
                    rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE_STRIP, 1)
                    #rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                    rapi.rpgClearBufferBinds() 
                    #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
                    successful_loads+=1
        elif cmpType[i] == 0xCCCC0900:
            #print("CC9 name",file_comps[bs.readUInt()])
            bs.readUInt()
            bs.readUInt()
            length = bs.readUInt()
            for l in range(0,length):
                #print(file_comps[bs.readUInt()])
                bnm = bs.readUInt()
                #print("BNM",hex(bnm),file_comps[bnm])
                b = NoeBone(l,file_comps[bnm],NoeMat43(( NoeVec3((1.0, 0.0, 0.0)), NoeVec3((0.0, 1.0, 0.0)), NoeVec3((0.0, 0.0, 1.0)), NoeVec3((0.0, 0.0, 0.0 )) ) ))
                
                skeletonlist.append(file_comps[bnm])
                
                bonelist.append(b)
            #print(skeletonlist)
        #elif cmpType[i] == 0xCCCC0A00:
            #bonenamelist.append(cmpNameID[i])
        
        elif cmpType[i] == 0xCCCC0B00:
            #continue
            #HIT type models consist of geometry stored in floats
            #this geometry is proven to be the floor and wall collision of maps
            #it may also contain some UV data and be a renderable object in the game
            #as MDL data does not seem to exist for certain parts of maps.
            rapi.rpgSetPosScaleBias((1/8,1/8,1/8),(0,0,0))
            bs.readBytes(4)
            nameID = bs.readUInt()
            #nameID = cmpNameID[i]
            print(file_comps[nameID],hex(bs.tell()))
            unknown_ref = bs.readUInt()
            #print(file_comps[unknown_ref])
            for a in range(0,len(cmpNameID)-1):
                if(cmpNameID[a] == unknown_ref):
                    print(hex(cmpLoc[a]))
            numHits = bs.readUInt()
            bs.readBytes(4) #??
            for a in range(0,numHits):
                
                vcount = bs.readUInt()
                bs.readBytes(0x04)
                print(vcount,hex(bs.tell()))
                rapi.rpgSetName(file_comps[nameID])
                
                verts = bs.readBytes(vcount*0x18)
                
                rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_FLOAT, 0x0C)
                tmp2 = []
                wind = 1
                '''for a in range(0,(2*vcount)-2):
                    tmp2.append(a)
                    tmp2.append(a+1+wind)
                    tmp2.append(a+2-wind)
                    wind = 1 - wind'''
                for a in range(0,vcount):
                    tmp2.append(a)
                faceBuff = struct.pack('H'*len(tmp2), *tmp2)
                rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
                print(hex(bs.tell()))
                successful_loads+=1
        else:
            continue
        
    if successful_loads > 0:
        
        mdl = rapi.rpgConstructModel()
        mdl.setBones(bonelist)
        mdl.setModelMaterials(NoeModelMaterials(texlist,matlist))
        mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList
        #rapi.rpgReset()

        
        #VertBuff = []
        #vcount = 0

        
       
    return 1
    

    

Older datestamp.
Code: Select all#CCS CMP model importer

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
    handle = noesis.register(".hack//IMOQ, .hack//FGMT", ".cmp")
    noesis.setHandlerTypeCheck(handle, imoqCheckType)
    noesis.setHandlerLoadModel(handle, imoqLoadModel) #see also noepyLoadModelRPG
        #noesis.setHandlerWriteModel(handle, noepyWriteModel)
        #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
    noesis.logPopup()
        #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
    return 1

CCS_HEADER = 0xCCCC0001

#check if it's this type based on the data
def imoqCheckType(data):
    bs = NoeBitStream(data)
    if len(data) < 16:
        return 0
    if bs.readUInt() != CCS_HEADER:
        return 0
    #print("check pass")
    return 1         

#load the model
def imoqLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    
    
    successful_loads = 0
    
    mdl_loc = []
    file_paths = []
    file_comps = []
    comp_owner = []
    
    #read the main file name
    bs.seek(0x0C, NOESEEK_ABS)
    cmp_name = bs.readBytes(0x20).decode("ASCII").rstrip("\0")
    
    #read subfile path/names...
    #first reading how many files and components there will be...
    bs.seek(0x44, NOESEEK_ABS)
    num_files = bs.readUInt()
    num_comps = bs.readUInt()
    
    bs.seek(0x20, NOESEEK_REL)
    #Now grab the paths
    for i in range(0,num_files-1):
        file_paths.append(bs.readBytes(0x20).decode("ASCII").rstrip("\0"))
    #print("filepaths done"+hex(bs.tell()))
    #skip the empty path entry padding
    #bs.seek(0x20, NOESEEK_REL)
    
    #now we read the names of each component of the previously named files, and memorize to which file they belong
    for i in range(0,num_comps-0):
    #.decode("ASCII") is obvious, but .rstrip("\0") is less so. It cuts the 00 00 00 off the end of the string
        file_comps.append(bs.readBytes(0x1E).decode("Shift_JIS").rstrip("\0"))
        comp_owner.append(bs.readUShort())
    #print("comp names done"+hex(bs.tell()))
        #Don't print anything with shift_jis encoding... it crashes noesis

    #Find the MDL markers, 0x00 08 CC CC :: Old way. 
    '''while(bs.getOffset()<len(data)):
        if bs.readUInt() == 0xCCCC0800:
            mdl_loc.append(bs.getOffset())'''
    #Find MDLs and components, intelligently. :: New way
    bs.readBytes(0x08) #unknown
    #print(hex(bs.tell()))
    cmpLoc = []
    cmpType = []
    cmpLength = []
    #for i in range(0,num_comps):
    while(bs.getOffset()<len(data)):    
        checking = bs.readUInt()
        if checking & 0xCCCC0000 == 0xCCCC0000:
            cmpType.append(checking)
        #cmpType.append(bs.readUInt())
        #if cmpType[i] & 0xCCCC0000 != 0xCCCC0000:
        #    noesis.logPopup
        #    print(hex(bs.tell()))
        #    return 0
            cmpLoc.append(bs.tell())
            cmpLength.append(bs.readUInt())
        
        #bs.seek(cmpLength[i]*4,NOESEEK_REL)
        
    totalVerts = 0 #we will track how many verts have been iterated
    print(1)
    #for every model marker found, attempt to load vertices...
    for i in range(0,len(cmpType)):
        
        trans = NoeMat43((NoeVec3((1, 0, 0)),
                         NoeVec3((0, 0, 1)),
                         NoeVec3((0, -1, 0)),
                         NoeVec3((0, 0, 0))))
        rapi.rpgSetTransform(trans)
    
    #if 1==1:
        bs.seek(cmpLoc[i], NOESEEK_ABS)
        if cmpType[i] != 0xCCCC0800:
            continue
        elif bs.readInt() <= 5:
            
            print("skipping, too short")
            continue
        print(2)
        nameID = bs.readUInt()
        bs.readBytes(4)
        meshType = bs.readUShort()
        might_be_parent_or_bone_count = bs.readUShort()
        if meshType == 0x05:
            #print("skipping, type")
            continue #right now we're ignoring shadow 0x08, and actor 0x05 types.
        elif meshType == 0x08:#We will deal with shadow meshes here.
        
            bs.readBytes(0x08) #for now I don't know what this is.
            
            #some_pointer_crap = bs.readUInt()
            #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
            #    continue
            
            rapi.rpgSetName(file_comps[nameID])
            #bs.readBytes(4)
            vcount = bs.readUInt()
            tcount = bs.readUInt()
            if vcount <= totalVerts: #to prevent potential negative vcounts
                totalVerts = 0
            if vcount > 0xFFFF:
                
                #print("skipping, too many verts")
                continue
            verts = bs.readBytes(vcount*6) #positions
            #print(hex(bs.tell()))
            if bs.tell() % 4 == 2:
                bs.readBytes(2) #we MUST be 4byte aligned!
            rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
            tmp = []
            tmp2 = []
            print(hex(bs.tell()))
            for i in range(0,tcount):
                tmp2.append(bs.readUInt())
                
            
            print(len(tmp2))
            noesis.logPopup()
            faceBuff = struct.pack('I'*len(tmp2), *tmp2)
            #faceBuff = bs.readBytes(tcount*4) #tris
            rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_UINT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
            rapi.rpgClearBufferBinds() 
            #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
            successful_loads+=1
                
        else:#if meshType == 0x01 or meshType == 0x00:#We will deal with static meshes here.
            #print(meshType)    
            
            
            bs.readBytes(0x0C) #for now I don't know what this is.
            
            #some_pointer_crap = bs.readUInt()
            #if some_pointer_crap & 0xCCCC0000 == 0xCCCC0000:
            #    continue
            
            rapi.rpgSetName(file_comps[nameID])
            bs.readBytes(4)
            vcount = bs.readUInt()
            if vcount <= totalVerts: #to prevent potential negative vcounts
                totalVerts = 0
            if vcount > 0xFFFF:
                
                #print("skipping, too many verts")
                continue
            #It is possible that vcount is cumulative for some meshes
            #Leading to the potential for vcounts larger than available vertices
            #vcount -= totalVerts
            
            #testing
            #if mdl_loc[i] == 0x4e3e4 or mdl_loc[i] == 0x4e3e0:
            #    continue
            #print(vcount)
            '''VertBuff = bs.readBytes(vcount*6)
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 6, 0)
            rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
            '''
            
            
            
            #for i in range(0,vcount):
                #rapi.immBegin(noesis.RPGEO_TRIANGLE)
                #rapi.immVertex3((bs.read("hhh")))
                #rapi.immEnd()
            #The order of vertex, UV, VColor, and Tridata may be wrong.
            #print(hex(bs.tell()))
            verts = bs.readBytes(vcount*6) #positions
            #print(hex(bs.tell()))
            if bs.tell() % 4 == 2:
                bs.readBytes(2) #we MUST be 4byte aligned!
            #mystery flags for triwinding
            mystery = []
            for i in range(0,vcount):
                mystery.append(bs.readBytes(4))
            bs.readBytes(vcount*4) #colors
            
            #print(hex(bs.tell()))
            uvs = bs.readBytes(vcount*4) #UVs
            
            
            #print(hex(bs.tell()))
            rapi.rpgBindPositionBuffer(verts, noesis.RPGEODATA_SHORT, 6)
            rapi.rpgBindUV1Buffer(uvs, noesis.RPGEODATA_USHORT, 4)
            
            rapi.rpgSetUVScaleBias(NoeVec3((256,256,0)),NoeVec3((0,0,0)))
            
            tmp2 = []
            
            facedir = 0
            for i in range(2, vcount):

                
                flag = mystery[i][3]
                #flag = 0
                if (flag == 0x00):
                    if (facedir) == 1:
                        tmp2.append(i - 2)
                        tmp2.append(i - 1)
                        tmp2.append(i)
                    else:
                        tmp2.append(i - 1)
                        tmp2.append(i - 2)
                        tmp2.append(i)
                    facedir = 1 - facedir
                #elif(flag == 0x01):
                #    facedir = 0
                    
                    #facedir = 1 - facedir
                #    if (facedir) == 0:
                #        tmp2.append(i + 2)
                #        tmp2.append(i + 1)
                #        tmp2.append(i)
                #    else:
                #        tmp2.append(i + 1)
                #        tmp2.append(i + 2)
                #        tmp2.append(i)
                #elif(flag == 0x02):
                #    facedir = 0
                #if i>0:
                #    if mystery[i-1][3] == flag:
                #        facedir = 1 - facedir
                #print(len(tmp2))
                '''
                if i % 2 == 1:
                    tmp2.append(i)
                    tmp2.append(i+2)
                    tmp2.append(i+1)
                else:
                    tmp2.append(i)
                    tmp2.append(i+1)
                    tmp2.append(i+2)
                '''
            print(len(tmp2))
            noesis.logPopup()
            faceBuff = struct.pack('H'*len(tmp2), *tmp2)
            rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, len(tmp2), noesis.RPGEO_TRIANGLE, 1)
            rapi.rpgClearBufferBinds() 
            #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vcount, noesis.RPGEO_POINTS, 1)
            successful_loads+=1
    if successful_loads > 0:
        mdl = rapi.rpgConstructModel()
        mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList
        #rapi.rpgReset()
    
        
        #VertBuff = []
        #vcount = 0

        
       
    return 1
    

    

I had them both enabled in noesis because I was testing them... but I don't know what's what anymore. Sorry again.

Woah, Satoh, this is freaking awesome!  Thank you so much for this post, it's going to help us a ton
## Post #7
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2017-04-11T01:35:10+00:00
- Post Title: CCS File Format (Dot Hack)

I hope so. I looked for my notes but this was unable to find most of them. What I did find is mostly just a documentation of the different CC tags like you already have. I apologize for all the random bits of code commented out in those files... it all does something, and I saved it for reference I think. even though it ended up not working correctly, I believe I kept it as a sort of documentation on what I was trying to read?

I regret that I never fully grasped the Noesis API 100%.

I have some code for GU models too, but I never had much success with that and I think it was hardcoded to exactly one model, so not really of a lot of use.

I guess I'll post my notes anyway, in case there's something useful you don't have.
At least they're somewhat shorter... I used to have pages of notes on the format but I just can't find them... which is frustrating.

```
CCCC0002 	Filename Header
CCCC0005 	EOF?
CCCC0100 	Bone?
CCCC0200 	MAT
CCCC0300 	TEX
CCCC0400 	CLT
CCCC0500 	LGT
CCCC0600 	MPH
CCCC0700 	ANM
CCCC0800 	MDL
CCCC0900 	CMP
CCCC0A00 	OBJ
CCCC0B00 	HIT
CCCC0C00 	BOX?
CCCC2000 	Dummy? 



CC1 headertag long (0xCCCC0001)
headersize long *4 exclusive
CCSF tag long
thisfilesname string 0x20bytes
archiveversion? long  (0x00000100 Quarantine,Fragment; 0x00000123 Redemption; 0x00000124 Link)
unk long
unk long (always 1?)
unk long (always 0?)

CC2 headertag long (0xCCCC0002)
namelength long *4 exclusive (counts both file names and chunk names)
countfiles long (first string is padding)
countchunks long (first string is padding)
padfname string 0x20bytes
filenames string[countfiles-1] 0x20bytes each 
padchunkname string 0x20bytes
chunknames string[countchunks-1] 0x20bytes each ( the last two bytes of each string are a {fileindex short indexed from 1})
unk long (always 3?)
unk long (always 0?)
Data begins.


Known header tags:
CC1 0xCCCC0001 Archive header
CC2 0xCCCC0002 
CCA 0xCCCC0A00 OBJ bone?
CC2000 0xCCCC2000 OBJ dummy?
CC700 0xCCCC0700 ANM
	CCF1 0xCCCCFF01 Frame? Index? Unchancged frame?
	CC102 0xCCCC0201 Frame? List of bones to change?
        CC202 0xCCCC0202 ??
CC200 0xCCCC0200 MAT Always contains a 0x3F800000 somewhere...? (1.0 as a float32?)
CC100 0xCCCC0100 ??? seems related to the very short models... is this a bone?
CC900 0xCCCC0900 CMP
CC800 0xCCCC0800 MDL
CC300 0xCCCC0300 TEX
CC400 0xCCCC0400 CLT

After a chunk header is always a SIZE long. After that, usually, there is a CHUNKINDEX long

Texture's have a modificed header. The size is a (long-32)*4
```


EDIT: I think to switch between Character and Map loading you have to set a flag to false... Probably the Texture loader, Vertex Colors, or HIT loader. I'm almost certain I put a boolean in there for it because I couldn't figure out how to get the code to recognize a character from a map automatically.

EDIT2:
I vaguely remember now, that one of the key points about the models is that they're broken up into different sections throughout the file but they all share the same vertex count. So section two won't start at index 0, it might start at index 50 or so, and then later on link to something like 2. You have to load all sections of vertices triangles and UVs before you commit any of it to rendering because of that.
Character models all have a very lowpoly shadow mesh, which is easy to read but misleading in that its usually the first set of mesh data. 

Maps and cutscene characters have a mesh format that is identical to normal character data, but has no UVS... this data is for morphs, as this is one of the few games that bothered to use them instead of simply using facial bones.

Sorry for all the random disorganized thoughts... I just want to make sure I disclose anything I remember. I may post more if anything else comes to me.
## Post #8
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2017-04-30T06:01:15+00:00
- Post Title: CCS File Format (Dot Hack)

So legit, I've been scouring the internet relentlessly for any information on the model and texture formats for this game, and this is the closest anyone has gotten that I've seen anywhere. The lack of bone information is fine for what I require. Basically all I need is an OBJ with proper UV's and a method to extract the matching textures. Any chance this could be revived?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-30T09:48:27+00:00
- Post Title: CCS File Format (Dot Hack)

> Reply from Satoh
>
> I apologize for the size, but I can't find a way to spoiler this.seriously.
Why don't you zip your python scripts and append them to your post?

This would also prevent some witty fellows from quoting the scripts and make this thread completely unreadable.
## Post #10
- Username: namine207
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 16, 2017 11:04 am
- Post datetime: 2017-05-22T00:58:28+00:00
- Post Title: CCS File Format (Dot Hack)

Final update on everything for now!

WV left the project a while back, and since then we've had a number of reverse engineers come on and help get this application where it needs to be, so we present to you CCS File Explorer Version 1.0.2!

[https://bitbucket.org/Casuallynoted/ccs-file-explorer](https://bitbucket.org/Casuallynoted/ccs-file-explorer)

It's capable of reading and exporting models/textures from both IMOQ and GU, with the following bugs/limitations:

-Cannot export animation, particle, bone, or material data.
-In a character model that is normally rigged, you are able to read and export most of the models without rigging, but the final model in the list isn't read correctly and comes out bizarre and corrupted looking (IMOQ Specific).
-In a character model that is normally rigged, none of the static models save from accessories like hats or glasses show up in the preview window and/or export. (GU Specific).
-Some specific models don't export UVs correctly. No identifiable cause has been found thus far.

Unfortunately these last three issues have left us all stumped and as a result the development of the tool has hit a dead end. However, full areas have been exported and pieced together to look exactly as they do in the game using this utility. If anyone does have any reverse engineering experience and would like to help finish the tool, definitely shoot me a PM and I'll send you as much info as I can on how to recreate the issues and what we know. Tremendous thanks to WV, Satoh, Dyson, and countless others who have made this all possible.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-22T18:51:48+00:00
- Post Title: CCS File Format (Dot Hack)

> , but the final model in the list isn't read correctlywhat does that mean "final model in the list"? Could you upload a sample file?

> -In a character model that is normally rigged, none of the static models save from accessories like hats or glasses show up in the preview window and/or export. (GU Specific).sample file?
I couldn't get the preview window working for the CSS files you uploaded. Only the texture preview works, for the model data I get raw view only (model view tab vanishes then). Maybe due to compiling it on Win7, 64 bit, where the exe fails, had to compile it for x86 and execute it on XP (don't have a suiting compiler there).
Anyways, the "Extract all Models" feature seems to work for static models:



CSS-explorer.JPG (149.84 KiB) Viewed 435 times



> -Some specific models don't export UVs correctly. No identifiable cause has been found thus far.sample file?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-05T11:09:24+00:00
- Post Title: CCS File Format (Dot Hack)

well, sometimes I feel like a real dumbo. In this case looking for the uvs of the treasure Box I was simply thinking too sophisticated, what a fault.  

First of all: this is a great project from Warranty Voider. Wish I had the patience to code such a viewer.

Nevertheless there were two caveats for me: a) it's written in C# (not really my preferred language),
b) it misses an absolute address for the file data, everything is "stream relative" (or I didn't get it).

After I introduced an absolute address things got clearer and I thought there was some data missing.
There were 270 <Vector2f> read but only 185 in the buffer.
But why turned all uvs out to be vt 0.0 0.0? What the heck.

Then, finally, after a week of relaxing I gave it a second try: the unknown bytes block!
How could I ignore it? How stupid!

Well, simply change the following line like so forcing the concerning if-block to be skipped:
if (FormatVariant == 10 || FormatVariant == 13)     // was 0 and 3
It's before // read texture block
UVBytes = new List<byte[]>(); in Block0800.cs, 17kb
(Be sure to get the correct Block0800.cs, there's a smaller one in the Blocks subdirectory.)

And, as always, it's a quick hack only, may fail with other CCS files.
Especially FormatVariant == 13 should be == 3 as before, didn't test it.



treasure_Box-GU-format.JPG (69.45 KiB) Viewed 384 times



Correction of an assumed typo in override public bool Equals(Object obj) / Vector2f.cs
return (this.U == other.U) && (this.V == other.V);

But Equals doesn't seem to be used in the code so far.
## Post #13
- Username: namine207
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 16, 2017 11:04 am
- Post datetime: 2017-06-05T11:19:44+00:00
- Post Title: CCS File Format (Dot Hack)

> Reply from shakotay2
>
> well, sometimes I feel like a real dumbo. In this case looking for the uvs of the treasure Box I was simply thinking too sophisticated, what a fault.  

First of all: this is a great project from Warranty Voider. Wish I had the patience to code such a viewer.

Nevertheless there were two caveats for me: a) it's written in C# (not really my preferred language),
b) it misses an absolute address for the file data, everything is "stream relative" (or I didn't get it).

After I introduced an absolute address things got clearer and I thought there was some data missing.
There were 270 <Vector2f> read but only 185 in the buffer.
But why turned all uvs out to be vt 0.0 0.0? What the heck.

Then, finally, after a week of relaxing I gave it a second try: the unknown bytes block!
How could I ignore it? How stupid!

Well, simply change the following line like so forcing the concerning if-block to be skipped:
if (FormatVariant == 10 || FormatVariant == 13)     // was 0 and 3
It's before // read texture block
UVBytes = new List<byte[]>(); in Block0800.cs, 17kb
(Be sure to get the correct Block0800.cs, there's a smaller one in the Blocks subdirectory.)

And, as always, it's a quick hack only, may fail with other CCS files.
treasure_Box-GU-format.JPG

Woaaaaaaaaaaaah, man that's amazing!! Yes, I do remember discussing the advantages of absolute address vs stream, this one does it all via stream if I'm correct 

But wow, this is really amazing! Would you mind if I recreated these changes over on my end and accredit you with a new branch on Bitbucket? :O (May wind up being a new build altogether if we test it and it all works out with no other issues!)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-05T11:30:21+00:00
- Post Title: CCS File Format (Dot Hack)

> Reply from namine207
>
> Would you mind if I recreated these changes over on my end and accredit you with a new branch on Bitbucket?do as you wish to do; no credits required.
But keep in mind that it's a quick hack only to get uvs work with the Treasure Box - GU Format.ccs. You'll have to think about a correct patch.
## Post #15
- Username: namine207
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 16, 2017 11:04 am
- Post datetime: 2017-06-05T11:33:47+00:00
- Post Title: CCS File Format (Dot Hack)

> Reply from shakotay2
>
> namine207 wrote:Would you mind if I recreated these changes over on my end and accredit you with a new branch on Bitbucket? do as you wish to do; no credits required.
But keep in mind that it's a quick hack only to get uvs work with the Treasure Box - GU Format.ccs. You'll have to think about a correct patch.

Oh absolutely! Tbh I'll try running it through some of the other stuff just to see if it works with say the chim stuff, which has the same problem, but tbh even an alternate build for a tricky file or two is absolutely a fantastic step in the right direction!
## Post #16
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2019-01-24T21:21:15+00:00
- Post Title: Re: CCS File Format (Dot Hack)

Fuck, how tha fuck i open this? there's no a .exe tool?
## Post #17
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2019-01-28T22:50:36+00:00
- Post Title: Re: CCS File Format (Dot Hack)

how i replace textures that have more than 1 file? it corrupt the others
