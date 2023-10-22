## Post #1
- Username: emperorcool233
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 03, 2017 12:09 am
- Post datetime: 2018-06-10T05:31:21+00:00
- Post Title: Battlefield 1 fb3decoder strange issue

Hi

I am having a strange issue when running fb3decoder (the version in this video's description: [https://www.youtube.com/watch?v=mU5tuuwVKaY](https://www.youtube.com/watch?v=mU5tuuwVKaY))

It runs like normal, detects everything, then only extracts Core/Destruction audio files. These seem to work fine. Problem is, the script auto-closes afterwards and when re-run refuses to do more. It stops at Destruction.

I already have an audio dump but I would like the expansion guns like the Chauchat and their audio files, which is why I'm going through all the trouble. Any idea what could cause fb3decoder to stop there, and so neatly too? If it's supposed to give an error can I stop it from auto-closing so I can see it?

Thanks.

EDIT: I would also like to know how to read the .ebx files to get exact mixing info. Like, what Add files, what HiFi files, etc, to make the gunshot of a particular gun. I saw a thread about Battlefield 4 and how the .ebx there just straight up told you what files, but I can't seem to find it here. They're all unreadable strings. BF1 also speeds files up and down to create different gunshots and I really wanna know what those values are so I can replicate them.

EDIT 2: The script I use automatically labels everything if it finds the relevant .ebxs in the same operation. Bless the writer.

EDIT 3: I managed to get an error to stay put. Here is the traceback.

Traceback (most recent call last):
  File "D:\dump\fb3decoder\fb3decoder.py", line 561, in <module>
    main()
  File "D:\dump\fb3decoder\fb3decoder.py", line 558, in main
    dbx.decode()
  File "D:\dump\fb3decoder\fb3decoder.py", line 511, in decode
    decodeXas(currentChunkName, target, Segment.SamplesOffset)
  File "D:\dump\fb3decoder\fb3decoder.py", line 62, in decodeXas
    xas.decode(chunkPath, target, samplesOffset)
WindowsError: [Error -529697949] Windows Error 0xE06D7363

It seems to be something with Visual C++ Compiler which I haven't had issues with in the past.
## Post #2
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2018-06-15T15:32:27+00:00
- Post Title: Battlefield 1 fb3decoder strange issue

Hi,

Could you please copy/paste the Dump script there? I would check something.

By the way, try this script to convert .ebx files to .txt (don't forget to adjust file paths for you):

```
#The floattostring.dll requires 32bit Python to write floating point numbers in a succinct manner,
#but the dll is not required to run this script.
import string
import sys
from binascii import hexlify
import struct
import os
from cStringIO import StringIO
import cProfile
import cPickle
import copy

#Adjust input and output folders here F:\Server\Symthic\hexing\bf4 dump\update
inputFolder=r"D:\BF1Extract\DUMP\bundles\ebx"
outputFolder=r"D:\BF1Extract\DUMPEBX"

guidTableName="bf1up" #Name of the guid table file; keeping separate names
#for separate games is highly recommended. The table is created at the location of the script.

EXTENSION=".txt" #Use a different file extension if you like.
SEP="    "       #Adjust the amount of whitespace on the left of the converted file.

#Show offsets to the left
printOffsets=False #True/False

#Ignore all instances and fields with these names when converting to text:
IGNOREINSTANCES=["RawFileDataAsset"] #used in WebBrowser\Fonts, crashes the script otherwise
IGNOREFIELDS=[]
##IGNOREINSTANCES=["ShaderAdjustmentData","SocketData","WeaponSkinnedSocketObjectData","WeaponRegularSocketObjectData"]
##IGNOREFIELDS=["Mesh3pTransforms","Mesh3pRigidMeshSocketObjectTransforms"]

#I recommend ignoring a few fields/instances which are related to meshes,
#take up lots of space, and contain no useful information as the mesh format is not even known.
#As an example, Mesh3pTransforms contains nothing but xyz vectors and is found in most weapon
#files. This field takes up 715 lines in the 870 shotgun (the entire file is 3829 lines).
#If you enjoy having to scroll past these 700 lines all the time, then ignore nothing.
#Note however that the lists above applied to bf3. In bf4 I can only find Mesh3pTransforms in the files but not the other strings.
#Nevertheless, use this as a guide to ignore fields/instances on your own.



#First run through all files to create a guid table to resolve external file references.
#Then run through all files once more, but this time convert them using the guid table.
def main():
    createGuidTable()
    dumpText()


##############################################################
##############################################################
unpackLE = struct.unpack
def unpackBE(typ,data): return struct.unpack(">"+typ,data) 

def createGuidTable():
    for dir0, dirs, ff in os.walk(inputFolder):
        for fname in ff:
            if fname[-4:]!=".ebx": continue
            f=open(lp(dir0+"\\"+fname),"rb")
            relPath=(dir0+"\\"+fname)[len(inputFolder):-4]
            if relPath[0]=="\\": relPath=relPath[1:]
            try:
                dbx=Dbx(f,relPath)
                f.close()
            except ValueError as msg:
                f.close()
                if str(msg).startswith("The file is not ebx: "):
                    continue
                else: asdf
            guidTable[dbx.fileGUID]=dbx.trueFilename
    f5=open(guidTableName,"wb") #write the table
    cPickle.dump(guidTable,f5)
    f5.close()

def dumpText():
    for dir0, dirs, ff in os.walk(inputFolder):
        for fname in ff:
            if fname[-4:]!=".ebx": continue
            print fname
            f=open(lp(dir0+"\\"+fname),"rb")
            relPath=(dir0+"\\"+fname)[len(inputFolder):-4]
            if relPath[0]=="\\": relPath=relPath[1:]
            try:
                dbx=Dbx(f,relPath)
                f.close()
            except ValueError as msg:
                f.close()
                if str(msg).startswith("The file is not ebx: "):
                    continue
                else: asdf
            dbx.dump(outputFolder)

def open2(path,mode="rb"):
    if mode=="wb":    
        #create folders if necessary and return the file handle

        #first of all, create one folder level manully because makedirs might fail
        pathParts=path.split("\\")
        manualPart="\\".join(pathParts[:2])
        if not os.path.isdir(manualPart):
            os.makedirs(manualPart)

        #now handle the rest, including extra long path names
        folderPath=lp(os.path.dirname(path))
        if not os.path.isdir(folderPath): os.makedirs(folderPath)
    return open(lp(path),mode)

def lp(path): #long, normalized pathnames
    if len(path)<=247 or path=="" or path[:4]=='\\\\?\\': return os.path.normpath(path)
    return unicode('\\\\?\\' + os.path.normpath(path))


try:
    from ctypes import *
    floatlib = cdll.LoadLibrary("floattostring")
    def formatfloat(num):
        bufType = c_char * 100
        buf = bufType()
        bufpointer = pointer(buf)
        floatlib.convertNum(c_double(num), bufpointer, 100)
        rawstring=(buf.raw)[:buf.raw.find("\x00")]
        if rawstring[:2]=="-.": return "-0."+rawstring[2:]
        elif rawstring[0]==".": return "0."+rawstring[1:]
        elif "e" not in rawstring and "." not in rawstring: return rawstring+".0"
        return rawstring
except:
    def formatfloat(num):
        return str(num)
def hasher(keyword): #32bit FNV-1 hash with FNV_offset_basis = 5381 and FNV_prime = 33
    hash = 5381
    for byte in keyword:
        hash = (hash*33) ^ ord(byte)
    return hash & 0xffffffff # use & because Python promotes the num instead of intended overflow
class Header:
    def __init__(self,varList):
        self.absStringOffset     = varList[0]  ## absolute offset for string section start
        self.lenStringToEOF      = varList[1]  ## length from string section start to EOF
        self.numGUID             = varList[2]  ## number of external GUIDs
        self.numInstanceRepeater = varList[3]  ## total number of instance repeaters
        self.numGUIDRepeater     = varList[4]  ## instance repeaters with GUID
        self.unknown             = varList[5]
        self.numComplex          = varList[6]  ## number of complex entries
        self.numField            = varList[7]  ## number of field entries
        self.lenName             = varList[8]  ## length of name section including padding
        self.lenString           = varList[9]  ## length of string section including padding
        self.numArrayRepeater    = varList[10]
        self.lenPayload          = varList[11] ## length of normal payload section; the start of the array payload section is absStringOffset+lenString+lenPayload
class FieldDescriptor:
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.type            = varList[1]
        self.ref             = varList[2] #the field may contain another complex
        self.offset          = varList[3] #offset in payload section; relative to the complex containing it
        self.secondaryOffset = varList[4]
        if self.name=="$": self.offset-=8
class ComplexDescriptor:
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.fieldStartIndex = varList[1] #the index of the first field belonging to the complex
        self.numField        = varList[2] #the total number of fields belonging to the complex
        self.alignment       = varList[3]
        self.type            = varList[4]
        self.size            = varList[5] #total length of the complex in the payload section
        self.secondarySize   = varList[6] #seems deprecated
class InstanceRepeater:
    def __init__(self,varList):
        self.complexIndex    = varList[0] #index of complex used as the instance
        self.repetitions     = varList[1] #number of instance repetitions
class arrayRepeater:
    def __init__(self,varList):
        self.offset          = varList[0] #offset in array payload section
        self.repetitions     = varList[1] #number of array repetitions
        self.complexIndex    = varList[2] #not necessary for extraction
class Complex:
    def __init__(self,desc):
        self.desc=desc
class Field:
    def __init__(self,desc,offset):
        self.desc=desc
        self.offset=offset #track absolute offset of each field in the ebx

numDict={0xC12D:("Q",8),0xc0cd:("B",1) ,0x0035:("I",4),0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("b",1),0xc0ed:("h",2), 0xc0dd:("H",2), 0xc13d:("f",4)}

class Dbx:
    def __init__(self, f, relPath):
        #metadata
        magic=f.read(4)
        if    magic=="\xCE\xD1\xB2\x0F": self.unpack=unpackLE
        elif  magic=="\x0F\xB2\xD1\xCE": self.unpack=unpackBE
        else: raise ValueError("The file is not ebx: "+relPath)

        self.relPath=relPath #to give more feedback for unknown field types
        self.trueFilename=""
        self.header=Header(self.unpack("3I6H3I",f.read(36)))
        self.arraySectionstart=self.header.absStringOffset+self.header.lenString+self.header.lenPayload
        self.fileGUID=f.read(16)
        while f.tell()%16!=0: f.seek(1,1) #padding
        self.externalGUIDs=[(f.read(16),f.read(16)) for i in xrange(self.header.numGUID)]
        self.keywords=str.split(f.read(self.header.lenName),"\x00")
        self.keywordDict=dict((hasher(keyword),keyword) for keyword in self.keywords)
        self.fieldDescriptors=[FieldDescriptor(self.unpack("IHHii",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
        self.complexDescriptors=[ComplexDescriptor(self.unpack("IIBBHHH",f.read(16)), self.keywordDict) for i in xrange(self.header.numComplex)]
        self.instanceRepeaters=[InstanceRepeater(self.unpack("2H",f.read(4))) for i in xrange(self.header.numInstanceRepeater)] 
        while f.tell()%16!=0: f.seek(1,1) #padding
        self.arrayRepeaters=[arrayRepeater(self.unpack("3I",f.read(12))) for i in xrange(self.header.numArrayRepeater)]

        #payload
        f.seek(self.header.absStringOffset+self.header.lenString)
        self.internalGUIDs=[]
        self.instances=[] # (guid, complex)
        nonGUIDindex=0
        self.isPrimaryInstance=True #first instance is primary
        for i, instanceRepeater in enumerate(self.instanceRepeaters):
            for repetition in xrange(instanceRepeater.repetitions):
                #obey alignment of the instance; peek into the complex for that
                while f.tell()%self.complexDescriptors[instanceRepeater.complexIndex].alignment!=0: f.seek(1,1)

                #all instances after numGUIDRepeater have no guid
                if i<self.header.numGUIDRepeater:
                    instanceGUID=f.read(16)
                else:
                    #just numerate those instances without guid and assign a big endian int to them.
                    instanceGUID=struct.pack(">I",nonGUIDindex)
                    nonGUIDindex+=1
                self.internalGUIDs.append(instanceGUID)

                self.instances.append( (instanceGUID,self.readComplex(instanceRepeater.complexIndex,f,True)) )
                self.isPrimaryInstance=False #the readComplex function has used isPrimaryInstance by now
        f.close()

        #if no filename found, use the relative input path instead
        #it's just as good though without capitalization
        if self.trueFilename=="":
            self.trueFilename=relPath
        
        
        

    def readComplex(self, complexIndex, f, isInstance=False):
        complexDesc=self.complexDescriptors[complexIndex]
        cmplx=Complex(complexDesc)
        cmplx.offset=f.tell()
                     
        cmplx.fields=[]
        #alignment 4 instances require subtracting 8 for all field offsets and the complex size
        obfuscationShift=8 if (isInstance and cmplx.desc.alignment==4) else 0
        
        for fieldIndex in xrange(complexDesc.fieldStartIndex,complexDesc.fieldStartIndex+complexDesc.numField):
            f.seek(cmplx.offset+self.fieldDescriptors[fieldIndex].offset-obfuscationShift)
            cmplx.fields.append(self.readField(fieldIndex,f))
        
        f.seek(cmplx.offset+complexDesc.size-obfuscationShift)
        return cmplx

    def readField(self,fieldIndex,f):
        fieldDesc = self.fieldDescriptors[fieldIndex]
        field=Field(fieldDesc,f.tell())
##            f1.seek(startPos+field.offset)
####                f2.write("@"+str(f1.tell()))
        
        if fieldDesc.type in (0x0029, 0xd029,0x0000,0x8029):
            field.value=self.readComplex(fieldDesc.ref,f)
        elif fieldDesc.type==0x0041:
            arrayRepeater=self.arrayRepeaters[self.unpack("I",f.read(4))[0]]
            arrayComplexDesc=self.complexDescriptors[fieldDesc.ref]

            f.seek(self.arraySectionstart+arrayRepeater.offset)
            arrayComplex=Complex(arrayComplexDesc)
            arrayComplex.fields=[self.readField(arrayComplexDesc.fieldStartIndex,f) for repetition in xrange(arrayRepeater.repetitions)]
            field.value=arrayComplex
            
        elif fieldDesc.type in (0x407d, 0x409d):
            startPos=f.tell()
            stringOffset=self.unpack("i",f.read(4))[0]
            if stringOffset==-1:
                field.value="*nullString*"
            else:
                f.seek(self.header.absStringOffset+stringOffset)
                field.value=""
                while 1:
                    a=f.read(1)
                    if a=="\x00": break
                    else: field.value+=a
                f.seek(startPos+4)
                
                if self.isPrimaryInstance and fieldDesc.name=="Name" and self.trueFilename=="": self.trueFilename=field.value
            
                   
        elif fieldDesc.type in (0x0089,0xc089): #incomplete implementation, only gives back the selected string
            compareValue=self.unpack("i",f.read(4))[0] 
            enumComplex=self.complexDescriptors[fieldDesc.ref]

            if enumComplex.numField==0:
                field.value="*nullEnum*"
            for fieldIndex in xrange(enumComplex.fieldStartIndex,enumComplex.fieldStartIndex+enumComplex.numField):
                if self.fieldDescriptors[fieldIndex].offset==compareValue:
                    field.value=self.fieldDescriptors[fieldIndex].name
                    break

        elif fieldDesc.type==0xc15d:
            field.value=f.read(16)
        elif fieldDesc.type==0x417d:
            field.value=f.read(8)
        else:
            try:
                (typ,length)=numDict[fieldDesc.type]
                num=self.unpack(typ,f.read(length))[0]
                field.value=num
            except:
                print "Unknown field type: "+str(fieldDesc.type)+" File name: "+self.relPath
                field.value="*unknown field type*"
        
        return field
        

    def dump(self,outputFolder):
##        if not self.trueFilename: self.trueFilename=hexlify(self.fileGUID)
        
        outName=outputFolder+self.trueFilename+EXTENSION
#        outName=outputFolder+self.relPath+EXTENSION###temp for ebx ALL bundle dump
        
##        dirName=os.path.dirname(outputFolder+self.trueFilename)
##        if not os.path.isdir(dirName): os.makedirs(dirName)
##        if not self.trueFilename: self.trueFilename=hexlify(self.fileGUID)
##        f2=open(outputFolder+self.trueFilename+EXTENSION,"wb")
        f2=open2(outName,"wb")
        
        for (guid,instance) in self.instances:
            if instance.desc.name not in IGNOREINSTANCES: #############instances to ignore here
                writeInstance(f2,instance,hexlify(guid))
                self.recurse(instance.fields,f2,0)
        f2.close()

    def recurse(self, fields, f2, lvl): #over fields
        lvl+=1
        for field in fields:
            if field.desc.type in (0x0029,0xd029,0x0000,0x8029):
                if field.desc.name not in IGNOREFIELDS: ############# look for fields here
                    writeField(f2,field,lvl,"::"+field.value.desc.name)
                    self.recurse(field.value.fields,f2,lvl)
            elif field.desc.type == 0xc13d:
                writeField(f2,field,lvl," "+formatfloat(field.value))
            elif field.desc.type == 0xc15d:
                writeField(f2,field,lvl," "+hexlify(field.value).upper()) #upper case=> chunk guid
            elif field.desc.type==0x417d:
                val=hexlify(field.value)
##                val=val[:16]+"/"+val[16:]
                writeField(f2,field,lvl," "+val)
            elif field.desc.type == 0x0035:
                towrite=""
                if field.value>>31:
                    extguid=self.externalGUIDs[field.value&0x7fffffff]
                    try: towrite=guidTable[extguid[0]]+"/"+hexlify(extguid[1])
                    except: towrite=hexlify(extguid[0])+"/"+hexlify(extguid[1])
                elif field.value==0: towrite="*nullGuid*"
                else:
                    intGuid=self.internalGUIDs[field.value-1]
                    towrite=hexlify(intGuid)
                writeField(f2,field,lvl," "+towrite) 
            elif field.desc.type==0x0041:
                if len(field.value.fields)==0:
                    writeField(f2,field,lvl," *nullArray*")
                else:
                    writeField(f2,field,lvl,"::"+field.value.desc.name)

                    #quick hack so I can add indices to array members while using the same recurse function
                    for index in xrange(len(field.value.fields)):
                        member=field.value.fields[index]
                        if member.desc.name=="member":
                            desc=copy.deepcopy(member.desc)
                            desc.name="member("+str(index)+")"
                            member.desc=desc
                    self.recurse(field.value.fields,f2,lvl)
            else:
                try:
                    writeField(f2,field,lvl," "+str(field.value))
                except AttributeError:
                    print f2 #+ "zzzzzzzzzzzzzzzzzzzzzzzz"
                    continue

def hex2(num):
    #take int, return 8byte string
    a=hex(num)
    if a[:2]=="0x": a=a[2:]
    if a[-1]=="L": a=a[:-1]
    while len(a)<8:
        a="0"+a
    return a

if printOffsets:
    def writeField(f,field,lvl,text):
        f.write(hex2(field.offset)+SEP+lvl*SEP+field.desc.name+text+"\r\n")
    def writeInstance(f,cmplx,text):
        f.write(hex2(cmplx.offset)+SEP+cmplx.desc.name+" "+text+"\r\n")     
else:
    def writeField(f,field,lvl,text):
        f.write(lvl*SEP+field.desc.name+text+"\r\n")
    def writeInstance(f,cmplx,text):
        f.write(cmplx.desc.name+" "+text+"\r\n")


if outputFolder[-1] not in ("/","\\"): outputFolder+="\\"
if inputFolder[-1] not in ("/","\\"): inputFolder+="\\"


#if there's a guid table already, use it
try:
    f5=open(guidTableName,"rb")
    guidTable=cPickle.load(f5)
    f5.close()
except:
    guidTable=dict()

main()
```


Keep us updated.
