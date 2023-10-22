## Post #1
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2012-11-21T02:17:48+00:00
- Post Title: Medal Of Honor Warfighter (Pc) cas.cat,sb,toc,initfs_Win32

Hello, I open this thread to understand little more about extracting files for MOHW.
A friend called Frankelstner Simthic Forum has given me   
Well, here's the script (python) that you created for cascat MOHW files:

Step by step:
1.-Install python 2.7
2.-copy the code into a text file by changing the extension to .py  
3.-adjust the file paths in the script

```
outputfolder="D:\\moh raw patch\\"
 
import string
import sys
import os
from binascii import hexlify
from struct import unpack
from cStringIO import StringIO
import zlib
 
 
class Entry:
    pass
 
 
def readcat(catname):
    if catname[-4:]!=".cat": return
    cat=open(catname,"rb")
    if cat.read(16)!="NyanNyanNyanNyan":
        cat.close()
        raise Exception("Wrong magic, no nyan found.")
       
    casfolder=os.path.dirname(catname)+"\\"
    #get file length
    catsize=os.path.getsize(catname)
 
    #create file handles for the vanilla files
    casfiles=[]
                       
    for i in xrange(1,50):
        s="0"+str(i) if i<10 else str(i)
        try:
            cas=open(casfolder+"cas_"+s+".cas","rb")
            casfiles.append(cas)
        except:
            break
                       
    if not os.path.isdir(outputfolder): os.makedirs(outputfolder)
   
    while cat.tell()<catsize:
        #do the cat
        catEntry=Entry()                        
        catEntry.sha1=cat.read(20)                        
        catEntry.offset, catEntry.size, catEntry.casnum = unpack("<III",cat.read(12))
                     
        #do the cas
        cas=casfiles[catEntry.casnum-1]
        cas.seek(catEntry.offset)
        magic=cas.read(4)
        magic2=cas.read(4)
        magic3=cas.read(4)
        cas.seek(catEntry.offset)
         
        if magic=="\xCE\xD1\xB2\x0F":
            out=open(outputfolder+hexlify(catEntry.sha1),"wb")
            out.write(cas.read(catEntry.size))
            out.close()
                       
        elif magic3[0:2]=="\x78\xda" or magic3=="\xCE\xD1\xB2\x0F":
            outStream=StringIO()
            while cas.tell()<catEntry.offset+catEntry.size:
                uncompressedSize,compressedSize=unpack(">II",cas.read(8)) #big endian
 
                if uncompressedSize==compressedSize: #non zlib
                    outStream.write(cas.read(compressedSize))
                else:
                    outStream.write(zlib.decompress(cas.read(compressedSize)))
 
            data=outStream.getvalue()
            outStream.close()
            if data[:4]=="\xCE\xD1\xB2\x0F":
                out=open(outputfolder+hexlify(catEntry.sha1),"wb")
                out.write(data)
                out.close()
               
 
    for cas in casfiles:
        cas.close()
    cat.close()
   
 
readcat(catname)

```


Then on disk D: will the folder named "moh raw patch" that contains the files extracted from cas.cat the folder "data" of the game.
Then this script can transform a text file for your understanding and editing.

step by step:
1. - Copy the code into a text file by changing the extension to .Py
2. - Drag and drop the folder "raw patch moh" in the script
3. - Default is created in the root directory C: a folder called "MOHW files"
4. - And you can edit the game files

```
import string
import sys
from binascii import hexlify
from struct import unpack
import os
from cStringIO import StringIO

#adjust output folder here; you must specify a folder
outputFolder="C:/MOHW files"

try:
    #try to print a number as 0.95
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
    #the number will be printed as 0.949999988079
    def formatfloat(num):
        return str(num)


def hasher(keyword): #32bit FNV-1 hash with FNV_offset_basis = 5381 and FNV_prime = 33
    hash = 5381
    for byte in keyword:
        hash = (hash*33) ^ ord(byte)
    return hash & 0xffffffff # use & because Python promotes the num instead of intended overflow



class Header:
    def __init__(self,varList): ##all 4byte unsigned integers
        self.absStringOffset     = varList[0]  ## absolute offset for string section start
        self.lenStringToEOF      = varList[1]  ## length from string section start to EOF
        self.numGUID             = varList[2]  ## number of external GUIDs
        self.null                = varList[3]  ## 00000000
        self.numInstanceRepeater = varList[4]
        self.numComplex          = varList[5]  ## number of complex entries
        self.numField            = varList[6]  ## number of field entries
        self.lenName             = varList[7]  ## length of name section including padding
        self.lenString           = varList[8]  ## length of string section including padding
        self.numArrayRepeater    = varList[9]
        self.lenPayload          = varList[10] ## length of normal payload section; the start of the array payload section is absStringOffset+lenString+lenPayload


class FieldDescriptor:
    #field has 4byte hash, 2byte type, 2byte reference/pointer, 4byte offset , 4byte secondary offset
    #e.g. 4B1F9065  3500  0000  0C000000  1C000000
    #     hash      type  ref   offset    offset2
    # => 'VoiceOverType', 0x0035, 0, 12, 28
    def __init__(self,varList):
        self.name            = keywordDict[varList[0]]
        self.type            = varList[1]
        self.ref             = varList[2] #the field may contain another complex
        self.offset          = varList[3] #offset in payload section; relative to the complex containing it
        self.secondaryOffset = varList[4]

        
class ComplexDescriptor:
    #complex has 4byte hash, 4byte field index, 1byte number of fields, 1byte alignment size, 2byte type, 2byte payload size, 2byte size2
    #e.g. 39E97F28  52000000    04   04     3500  5000 0000
    #     hash      fieldIndex  num  align  type  size size2
    # => 'EntityVoiceOverInfo', 82, 4, 4, 0x0035, 80, 0
    def __init__(self,varList):
        self.name            = keywordDict[varList[0]]
        self.fieldStartIndex = varList[1] #the index of the first field belonging to the complex
        self.numField        = varList[2] #the total number of fields belonging to the complex
        self.alignment       = varList[3]
        self.type            = varList[4]
        self.size            = varList[5] #total length of the complex in the payload section
        self.secondarySize   = varList[6] #seems deprecated


class InstanceRepeater:
    def __init__(self,varList):
        self.null            = varList[0] #seems to be always null
        self.repetitions     = varList[1] #number of instance repetitions
        self.complexIndex    = varList[2] #index of complex used as the instance

class arrayRepeater:
    def __init__(self,varList):
        self.offset          = varList[0] #offset in array payload section
        self.repetitions     = varList[1] #number of array repetitions
        self.complexIndex    = varList[2] #not necessary for extraction



    
def read(filename):
    global f1, f2, externalGUIDList, internalGUIDList, fields, complexes, header, trueFilename, arrayRepeaters, isPrimaryInstance, keywordDict
    
    #check magic
    try: f1=open(filename,"rb")
    except: return
    if f1.read(4)!="\xCE\xD1\xB2\x0F":
        f1.close()
        return

    print filename
    
    header=Header(unpack("11I",f1.read(44)))
    trueFilename="" #the cas extractor only guesses a filename which may be incorrect; but I do know how to find out the correct one
    
    #grab the file GUID and its primary instance. Make the hex numbers to string, e.g. 0x4b => "4b"
    fileGUID, primaryInstanceGUID = hexlify(f1.read(16)), hexlify(f1.read(16))


    #add all GUID pairs to a list. These are external GUIDs so the first GUID is the GUID
    #of another file and the second belongs to an instance inside that file (may or may not be primary)
    externalGUIDList=[(hexlify(f1.read(16)),hexlify(f1.read(16))) for i in range(header.numGUID)]

    #make list of names and make a dictionary hash vs name
    keywords=str.split(f1.read(header.lenName),"\x00")
##    while len(keywords[-1])==0:
##        keywords.pop() #remove the last few empty entries which appeared due to null-padding; not necessary because keywordDict does not mind
    keywordDict=dict((hasher(keyword),keyword) for keyword in keywords)


    #read all fields and complexes into lists; replace hashes with names instantly
    fields=[FieldDescriptor(unpack("IHHII",f1.read(16))) for i in xrange(header.numField)]
    complexes=[ComplexDescriptor(unpack("IIBBHHH",f1.read(16))) for i in xrange(header.numComplex)]


    #read instanceRepeater and arrayRepeater, each entry consists of 3 unsigned ints
    instanceRepeaters=[InstanceRepeater(unpack("3I",f1.read(12))) for i in range(header.numInstanceRepeater)] 
    while f1.tell()%16!=0: f1.seek(1,1) #padding
    arrayRepeaters=[arrayRepeater(unpack("3I",f1.read(12))) for i in range(header.numArrayRepeater)]

    #ignore string section and read directly only when necessary. The elements are accessed directly via offset instead of index.
    f1.seek(header.absStringOffset+header.lenString)


    #START OF PAYLOAD SECTION
  

    ##make a list of all internal instance GUID, ignore the actual payload; this way I can instantly replace a payload Guid index with a string
    internalGUIDList=[]
    for instanceRepeater in instanceRepeaters:
        for repetition in xrange(instanceRepeater.repetitions):
            internalGUIDList.append(hexlify(f1.read(16)))
            f1.seek(complexes[instanceRepeater.complexIndex].size,1)

    f1.seek(header.absStringOffset+header.lenString) # go back to start of payload section



    ##do the same as above, but 1) don't make a list and 2) read the payload 
    f2=StringIO() #prepare stream to write the output into memory because filename is not known yet
    
    for instanceRepeater in instanceRepeaters:
        instance=complexes[instanceRepeater.complexIndex]
        
        for repetition in xrange(instanceRepeater.repetitions):
            tabLevel=1
            instanceGUID=hexlify(f1.read(16))
            startPos=f1.tell()
            if instanceGUID==primaryInstanceGUID:
                f2.write(instance.name+" "+instanceGUID+" #primary instance\r\n")
                isPrimaryInstance=True
            else:
                f2.write(instance.name+" "+instanceGUID+"\r\n")
                isPrimaryInstance=False
            readComplex(instance,tabLevel)
            f1.seek(startPos+instance.size)
  
    f1.close() # the source file is read and everything is in the f2 stream
    
    #create folder, file, etc.
    try:
        outFilename=os.path.join(outputFolder,trueFilename)+" "+fileGUID+".txt"
        if not os.path.isdir(os.path.dirname(outFilename)): os.makedirs(os.path.dirname(outFilename))
        f3=open(outFilename,"wb")
        f3.write(f2.getvalue())
        f3.close()
    except:
        print "Could not write file "+filename
        try: f3.close()
        except: pass
    f2.close()
    

##field types sorted by the value of their ref:
##ref==0 ("7d40","0dc1","3dc1","4dc1","5dc1","adc0","bdc0","ddc0","edc0","fdc0","3500"):
##        7d40: 4bytes; string, the value is the offset in the string section
##        0dc1: 4bytes; uint32
##        3dc1: 4bytes; single float
##        4dc1: 8bytes; double float
##        5dc1: 16bytes; GUID, referring to chunk files?
##        adc0: 1byte; bool, padded to 4 if no other adc0,bdc0, the same applies to the other <4 bytes values
##        bdc0: 1byte; int8
##        ddc0: 2bytes; uint16
##        edc0: 2bytes; int16
##        fdc0: 4bytes; int32
##        3500: 4bytes; GUID index, read as uint32 and the first bit is the isExternal flag. Do >>31 and afterwards use it as the index for the right GUID table
##                      
##
##ref!=0 ("4100","2900","29d0"):
##        4100: 4bytes; arrayRepeater index
##        2900: 0bytes; complex entry
##        29d0: 0bytes; complex entry
##
##
##ref sometimes 0, sometimes non 0 ("0000","8900"):
##        0000: 0bytes when field within an enum or 8bytes (all nulls) when element of "$" (which indicates inheritance)
##        8900: 4bytes; enum. Find the enum corresponding to the payload value


def readComplex(complex,tabLevel):
    #recursive function to read everything
    
    #get the fields for the complex
    fieldList=fields[complex.fieldStartIndex : complex.fieldStartIndex+complex.numField]
    
    startPos=f1.tell()
    if tabLevel!=1: f2.write("::"+complex.name+"\r\n")
        
    for field in fieldList:
        readField(field,startPos,tabLevel)

    f1.seek(startPos+complex.size)


def readField(field,startPos,tabLevel):
    f1.seek(startPos+field.offset)
##    f2.write("@"+str(f1.tell()))
    if field.type not in (0x0029,0xd029,0x0041,0x0000): #handle the simple stuff
        f2.write(tabLevel*"\t"+field.name+" "+unpackSimpleField(field)+"\r\n")
        
    elif field.type !=0x0041: #non arrays
        f2.write(tabLevel*"\t"+field.name)
        readComplex(complexes[field.ref],tabLevel+1) #recursion
        
    else: #arrays
        arrayIndex=unpack("I",f1.read(4))[0]
        if arrayIndex==0: #in contrast to the 0035 type, this time index 0 is reserved for these cases
            f2.write(tabLevel*"\t"+field.name+" *nullArray*"+"\r\n")
            return
        arrayRepeater=arrayRepeaters[arrayIndex] #no arrayIndex-1 necessary
        f1.seek(arrayRepeater.offset+header.absStringOffset+header.lenString+header.lenPayload)
        if arrayRepeater.repetitions==0: f2.write(tabLevel*"\t"+field.name+" *nullArray*"+"\r\n")
        else:
            arrayComplex=complexes[field.ref]
            memberField=fields[arrayComplex.fieldStartIndex]

            f2.write(tabLevel*"\t"+field.name)
            f2.write("::"+arrayComplex.name+"\r\n")
            for arrayRepetition in xrange(arrayRepeater.repetitions):
                position=f1.tell()
                readField(memberField,position,tabLevel+1) #recursion



#make a dictionary for the number/bool types. Mainly to save me from bloating the function below too much. Single floats not included either because I want to display them properly.
numDict={0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("b",1),0xc0ed:("h",2), 0xc0dd:("H",2)}

def unpackSimpleField(field):
    #read everything except 0x0029, 0xd029, 0x0041, 0x0000
    #i.e. all assignments that do not contain another complex (0x0089 being the exception because it is so different)
    global trueFilename
    try:
        #if the entry is number/bool, extract it with the dictionary; else go to except
        (typ,length)=numDict[field.type]
        num=unpack(typ,f1.read(length))[0]
        return str(num)
    
    except:
        if field.type==0xc13d: return formatfloat(unpack("f",f1.read(4))[0])
        if field.type==0xc15d: return hexlify(f1.read(16)) #GUID, neither external nor internal
        elif field.type==0xc0dd: return hexlify(f1.read(2)) #not sure about this type
            
        elif field.type==0x0089:                                                                                     
            if field.ref==0: return "*nullEnum*"
            else:
                #The field points at another complex. The fields in this complex then are the choices.
                #Basically I go through the fields one level deeper. These fields do not behave like actual fields, lots of nulls and offset is no offset at all.
                compareValue=unpack("I",f1.read(4))[0] #this value must match fakefield.offset
                fieldList=fields[complexes[field.ref].fieldStartIndex : complexes[field.ref].fieldStartIndex+complexes[field.ref].numField]
                for fakeField in fieldList:
                    if fakeField.offset==compareValue:
                        return fakeField.name

        elif field.type==0x407d: #the string section
            #The 4bytes payload are the offset, so we need to remember where we are, then jump and read
            #a null-terminated string and jump back
            originalPos=f1.tell() 
            f1.seek(header.absStringOffset+unpack("I",f1.read(4))[0])
            
            string=""
            while 1:
                a=f1.read(1)
                if a=="\x00": break
                else: string+=a
            f1.seek(originalPos+4)
            
            if len(string)==0: return "*nullString*" #actually the string is ""

            if isPrimaryInstance and trueFilename=="" and field.name=="Name": trueFilename=string
            return string

        elif field.type==0x0035:
            #Write the GUID of another instance. There are two different cases.
            #If the instance is found in another file use externalGUIDList (2*16 bytes).
            #If the instance is found in this file use internalGUIDList (1*16 bytes).
            #The first bit is the isExternal flag. => bitshift by 31 and bitmask
            GUIDIndex=unpack("I",f1.read(4))[0]
            
            if GUIDIndex>>31: return "-".join(externalGUIDList[GUIDIndex&0x7fffffff])
            elif GUIDIndex==0: return "*nullGuid*"   #this being handled differently by the engine is a bit annoying as internalGUIDList of course has an element at index 0
            else: return internalGUIDList[GUIDIndex-1] #as a result, minus 1 is necessary


def main():
    if not outputFolder:
        return
    for ff in sys.argv[1:]:
        if os.path.isfile(ff):
            read(ff)
        else:
            for dir0,dirs,files in os.walk(ff):
                for f in files:
                    read(dir0+"\\"+f)
                        
try:  
    main()
except Exception, e:
    raw_input(e)

main()

```


where we can create several changes to the game such as health, movement speed, change weapons, infinite ammo, etc..

Now the problem is to package and create a new cas.cat with edited files, that's why I turn to their aid. I wanted to use the tool called bf3 tweaker and does not work"

I also said this...:
"The tweaker does not detect the cascat files because they are zlib-compressed (I haven't added the functionality for this because it was not necessary in bf3). The text files cannot be converted into binary again because I do not fully understand these files. I know enough about them to create text files from them, but making binary files out of text requires complete knowledge of the file format. That's why the file tweaker is limited in its options too, it's because I do not understand the files".

Someone with enough knowledge to repackage a file cas.cat could provide your help please.

Frankelstner also has given me a script to open the files .sb and .toc

```
outputpath=r"D:\mohw loc sbtoc"
 
import sys
import os
from struct import unpack
from binascii import hexlify
import zlib
from cStringIO import StringIO
 
def read128(File):
    """Reads the next few bytes in a file as LEB128 and returns an integer"""
    result=0
    i=0
    while 1:
        byte=ord(File.read(1))
        result|=(byte&127)<<i
        i+=7
        if byte>>7==0:
            break
    return result
 
def readNullTerminatedString(f):
    result=""
    while 1:
        char=f.read(1)
        if char=="\x00": return result
        result+=char
 
 
#########
def readBundle(f):
    header=Header(unpack(">9I",f.read(36)))
    sha1List=[f.read(20) for i in xrange(header.numSha1)]
 
    dbxEntries=[BundleEntry(unpack(">3I",f.read(12))) for i in xrange(header.numDbx)]
    otherEntries=[BundleEntry(unpack(">3I",f.read(12))) for i in xrange(header.numOther)]
 
    for entry in otherEntries:
        entry.magic=f.read(4)
    for entry in otherEntries:
        entry.null=f.read(16)
 
    chunkEntries=[Chunk(f) for i in xrange(header.numChunks)]
    ###chunkmeta section, uses this weird toc stuff, just ignore it
    ##for chunk in chunkEntries:
       
    for entry in dbxEntries + otherEntries:
        f.seek(header.offsetPath+entry.offsetPath)
        entry.path=readNullTerminatedString(f)
 
    #save the files
    folder=os.path.join(outputpath,"bundles")+"\\"
    f.seek(header.unknown+4)
    for entry in dbxEntries:
        while f.tell()%16!=0: f.seek(1,1)
        folder2 = folder+os.path.dirname(entry.path)
       
        if not os.path.isdir(folder2): os.makedirs(folder2)
        f2=open(folder+entry.path+".dbx","wb")
        f2.write(f.read(entry.size1))
        f2.close()
 
   
class Header: #9 uint32
    def __init__(self,values):
        self.unknown=values[0]
        self.magic=values[1]
        self.numSha1=values[2]
        self.numDbx=values[3]
        self.numOther=values[4]
        self.numChunks=values[5]
        self.offsetPath=values[6]+4 #still unsure what to do with the first 4 bytes
        self.offsetChunk=values[7]+4
        self.sizeChunk=values[8]
       
class BundleEntry: #3 uint32 + 1 string
    def __init__(self,values):
        self.offsetPath=values[0] #in the path strings section
        self.size1=values[1] #size1=size2 for dbx. size1 is uncompressed and size2 is compressed
        self.size2=values[2]
        self.path=""
##        self.magic
 
class Chunk:
    def __init__(self, f):
        self.guid=f.read(16)
        self.size=unpack(">Q",f.read(8))[0]
        self.null=unpack(">I",f.read(4))[0]
#######
 
 
 
 
class Entry:
    pass
 
def readEntry(f): #similar to the main read
    entry=Entry()
    entry.size=read128(f) #metadata size, still in toc
    pos0=f.tell()
    while f.tell()<pos0+entry.size:
        typ=f.read(1)
        if typ=="\x00": break
        name=readNullTerminatedString(f)
        content=readContent(f,typ)
        if name=="offset": entry.offset=content
        elif name=="size": entry.size=content
        elif name=="id": entry.id=content
        else: raise Exception("Unknown keyword: "+name)
    return entry
       
def readContent(f,typ):
    if typ=="\x0f": return f.read(16)
    if typ=="\x09": return unpack("Q",f.read(8))[0]
    if typ=="\x08": return unpack("I",f.read(4))[0]
    if typ=="\x06": return True if f.read(1)=="\x01" else False
    if typ=="\x07":
        s=f.read(read128(f)-1)
        f.seek(1,1) #null
        return s
    if typ=="\x01":
        listLength=read128(f)
        pos0=f.tell()
        entries=[]
        while f.tell()<pos0+listLength and f.read(1)=="\x82":
            entries.append(readEntry(f))
        return entries
    else: raise Exception("Unknown type: "+hexlify(typ))
 
   
def unXOR(f):
    if f.read(4)!="\x00\xD1\xCE\x00":
        f.close()
        raise Exception("Bad toc magic.")
    f.seek(296)
    magic=[ord(f.read(1)) for i in xrange(260)] #last three bytes are not used
    data=f.read()
    f.close()
    data2=[None]*len(data) #initalize the buffer
    for i in xrange(len(data)):
        data2[i]=chr(magic[i%257]^ord(data[i])^0x7b)
    return StringIO("".join(data2))
 
 
def read(fname): #main function, validate and go through bundles and chunks
    if fname[-4:]!=".toc": return
    fXOR=open(fname,"rb")
    f=unXOR(fXOR)
    if f.read(1)!="\x82": return #wrong file type
    print fname ###
   
    dataLength=read128(f)
    eof=dataLength+f.tell()
   
    bundles=Entry()
    chunks=Entry()
   
    while f.tell()<eof:
        typ=f.read(1)
        if typ=="\x00": break
        name=readNullTerminatedString(f)
        content=readContent(f,typ)
        if name=="bundles":
            bundles.type=typ
            bundles.entries=content
        elif name=="chunks":
            chunks.type=typ
            chunks.entries=content
    f.close()
 
    #dump the data
   
    filename=os.path.splitext(fname)[0] #without extension
    f2=open(filename+".sb","rb")
    for entry in bundles.entries:
        f2.seek(entry.offset)
        f3=StringIO(f2.read(entry.size)) #make a copy of everything to save myself the trouble of adjusting padding
        readBundle(f3)
        f3.close()
    chunkfolder=os.path.join(outputpath,"chunks")
   
    if not os.path.isdir(chunkfolder): os.makedirs(chunkfolder)
    for chunk in chunks.entries:
        f2.seek(chunk.offset)
        f3=open(chunkfolder+"\\"+hexlify(chunk.id),"wb")
        f3.write(f2.read(chunk.size))
        f3.close()
 
 
 
    f2.close()
 
 
 
 
def main():
    read(inputpath)
##    for ff in sys.argv[1:]:
##        if os.path.isfile(ff):
##            read(ff)
##        else:
##            for dir0,dirs,files in os.walk(ff):
##                for f in files:
##                    read(dir0+"\\"+f)
           
try:  
    main()
except Exception, e:
    raw_input(e)

```


The subfolder "chunks" will contain various resource files which the other version of my sbtoc script does not create. Note however, that some files may still be missing because I do not understand the sbtoc archives enough to fully extract all files. It does however extract 100% of the files from en.toc/en.sb. Err and change the inputpath to the MOHW files, I have played around with the bf3 files a bit.
if anyone can help reading dump files in the folder you have extracted chunks 

You have created a python script to decrypt the file initfs_Win32:
Folder : Medal of Honor Warfighter\Update\Patch\Data\initfs_Win32

```

filename = sys.argv[1]

f1=open(filename,"rb")
header=f1.read(296)
magic=[]
for i in range(257):
    magic.append(ord(f1.read(1)))
f1.seek(3,1)
data=f1.read()
f1.close()
f2=open(filename+".txt","wb")
f2.write(header)
f2.write("{"*257)
f2.write("\0"*3)
buff=""
for i in xrange(len(data)):
    buff+=chr(magic[i%257]^ord(data[i])^0x7b)
    if i%128==0:
        f2.write(buff)
        buff=""
f2.write(buff)
f2.close()

```
 

The decrypted file can only be changed with a hex editor leaving the original size of the file after editing it, or causes it not to start the game. Besides the file does not require rekey and can hit in the installation folder as a text file without the extension "txt"

Bye!
## Post #2
- Username: abdullayev007
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Aug 02, 2012 7:02 am
- Post datetime: 2012-12-06T12:40:06+00:00
- Post Title: Medal Of Honor Warfighter (Pc) cas.cat,sb,toc,initfs_Win32

It can extract game subtitles?
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-12-06T21:09:06+00:00
- Post Title: Medal Of Honor Warfighter (Pc) cas.cat,sb,toc,initfs_Win32

Hey great work on the python scripts!!

Also does the bottom script work on the other chunk files that are not en/toc/sb?
## Post #4
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2012-12-08T02:13:03+00:00
- Post Title: Medal Of Honor Warfighter (Pc) cas.cat,sb,toc,initfs_Win32

> Reply from abdullayev007
>
> It can extract game subtitles?

If you can, I again mention that one can extract the files. Toc lozalization the folder, but it has not succeeded in turning the extracted data
The problem is that someone with sufficient knowledge about the file structure could repackage
## Post #5
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2012-12-08T02:14:08+00:00
- Post Title: Medal Of Honor Warfighter (Pc) cas.cat,sb,toc,initfs_Win32

> Reply from OrangeC
>
> Hey great work on the python scripts!!

Also does the bottom script work on the other chunk files that are not en/toc/sb?

Only in the localization files
## Post #6
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-12-08T09:44:49+00:00
- Post Title: Medal Of Honor Warfighter (Pc) cas.cat,sb,toc,initfs_Win32

Is it Only for Binary Texts?
Did you find anyway to extract other stuff?
## Post #7
- Username: abdullayev007
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Aug 02, 2012 7:02 am
- Post datetime: 2012-12-08T10:06:40+00:00
- Post Title: Medal Of Honor Warfighter (Pc) cas.cat,sb,toc,initfs_Win32

> Reply from vitoci
>
> abdullayev007 wrote:It can extract game subtitles?

If you can, I again mention that one can extract the files. Toc lozalization the folder, but it has not succeeded in turning the extracted data
The problem is that someone with sufficient knowledge about the file structure could repackage

do you want to say This script can extract language files? but can't import? right??
