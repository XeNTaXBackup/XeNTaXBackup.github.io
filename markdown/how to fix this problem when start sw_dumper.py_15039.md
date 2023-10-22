## Post #1
- Username: nightland18
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 09, 2016 3:59 pm
- Post datetime: 2016-09-13T09:43:02+00:00
- Post Title: how to fix this problem when start sw_dumper.py?

i try to extract .cas file ( encrypt archive ) in Mirror's Edge Catalyst game like this forum: [viewtopic.php?f=10&t=14269](http://forum.xentax.com/viewtopic.php?f=10&t=14269), use this tool in that thread forum, need to register to download the tool. So anyway, I upload the tool to this: [https://www.sendspace.com/file/zn23uv](https://www.sendspace.com/file/zn23uv) . Here is my python code in sw_dumper.py :

```
#Often the assets are actually stored in cascat archives (the sbtoc knows where to search in the cascat), which is taken care of too.
#The script does not overwrite existing files (mainly because 10 sbtocs pointing at the same asset in the cascat would make the extraction time unbearable).

#Adjust paths here.
bf4Directory= r"H:\mirror edge catalyst\Mirrors Edge Catalyst" 
targetDirectory = r"F:\mirror edge 2 unpacked"

###The following paths do not require adjustments (unless the devs decided to rename their folders). Note that they are relative to bf4Directory.

#As files are not overwritten, the patched files need to be extracted first.
#The script will dump all tocs it can find in these two folders+subfolders:
tocRoot  = r"patch\win32" #patched and xpack files FIRST
tocRoot2 = r"data\Win32"   #unpatched vanilla files SECOND

#Note: The "Update" tocRoot contains both patch (for vanilla AND xpack) and unpatched xpack files. The reason it still
#      works correctly is because it goes through the folders alphabetically, so the patch comes first.


#Feel free to comment out one or both cats if they don't exist (some Frostbite 2 games shipped without cats).
#Although in that case you could just as well use an invalid path, i.e. not change anything.
cat1Path       = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\anchorinstallpackage\cas.cat"
cat2Path       = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\backinthegameinstallpackage\cas.cat"
cat3Path       = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\cityglobalinstallpackage\cas.cat"
cat4Path       = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\cityrevealinstallpackage\cas.cat"
cat5Path       = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\defaultinstallpackage\cas.cat"
cat6Path       = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\downtownnorthinstallpackage\cas.cat"
cat7Path       = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\downtownsouthinstallpackage\cas.cat"
cat8Path       = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\initialinstallpackage\cas.cat"
cat9Path       = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\prisonexteriorinstallpackage\cas.cat"
cat10Path      = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\releaseinstallpackage\cas.cat"
cat11Path      = r"H:\mirror edge catalyst\Mirrors Edge Catalyst\Data\Win32\gameconfigurations\rezoninginstallpackage\cas.cat"
#updateCatPath = r"Update"


#About the names of the res files:
#   The first part after the actual name (but before the file extension) is the RID. I think it's used by ebx to import res files.
#   When it is not just nulls, the resMeta is added after the RID. Its purpose depends on the file type.
#   Finally, the res file extensions are just an invention of mine. See the resTypes dict right below.


#####################################
#####################################
import cas
import noncas
import os
from binascii import hexlify,unhexlify
from struct import pack,unpack
from cStringIO import StringIO
from ctypes import *
LZ77 = cdll.LoadLibrary("LZ77")

resTypes={ #not really updated for bf4 though
    0x5C4954A6:".itexture",
    0x2D47A5FF:".gfx",
    0x22FE8AC8:"",
    0x6BB6D7D2:".streamingstub",
    0x1CA38E06:"",
    0x15E1F32E:"",
    0x4864737B:".hkdestruction",
    0x91043F65:".hknondestruction",
    0x51A3C853:".ant",
    0xD070EED1:".animtrackdata",
    0x319D8CD0:".ragdoll",
    0x49B156D4:".mesh",
    0x30B4A553:".occludermesh",
    0x5BDFDEFE:".lightingsystem",
    0x70C5CB3E:".enlighten",
    0xE156AF73:".probeset",
    0x7AEFC446:".staticenlighten",
    0x59CEEB57:".shaderdatabase",
    0x36F3F2C0:".shaderdb",
    0x10F0E5A1:".shaderprogramdb",
    0xC6DBEE07:".mohwspecific",
    0xafecb022:".luac",
    0xC611F34A:".MeshEmitterResource",
    0x9D00966A:".UITtfFontFile",
    0x957C32B1:".AtlasTexture",
    0x6BDE20BA:".Texture",
    0xA23E75DB:".TerrainLayerCombinations",
    0xC6CD3286:".EnlightenStaticDatabase",
    0xE36F0D59:".HavokClothPhysicsData",
    0xf04f0c81:".Dx11ShaderProgramDatabase"
}
def hex2(num): return hexlify(pack(">I",num)) #e.g. 10 => '0000000a'
class Stub(): pass #generic struct for the cat entry

def readCat(catDict, catPath):
    """Take a dict and fill it using a cat file: sha1 vs (offset, size, cas path)"""
    cat=cas.unXor(catPath)
    cat.seek(0,2) #get eof
    catSize=cat.tell()
    cat.seek(24) #skip nyan
    casDirectory=os.path.dirname(catPath)+"\\" #get the full path so every entry knows whether it's from the patched or unpatched cat.
    while cat.tell()<catSize:
        entry=Stub()
        sha1=cat.read(20)
        entry.offset, entry.size, dummy, casNum = unpack("<IIII",cat.read(16))
        entry.path=casDirectory+"cas_"+("0"+str(casNum) if casNum<10 else str(casNum))+".cas"
        catDict[sha1]=entry


def dump(tocPath, targetFolder):
    """Take the filename of a toc and dump all files to the targetFolder."""

    #Depending on how you look at it, there can be up to 2*(3*3+1)=20 different cases:
    #    The toc has a cas flag which means all assets are stored in the cas archives. => 2 options
    #        Each bundle has either a delta or base flag, or no flag at all. => 3 options
    #            Each file in the bundle is one of three types: ebx/res/chunks => 3 options
    #        The toc itself contains chunks. => 1 option
    #
    #Simplify things by ignoring base bundles (they just state that the unpatched bundle is used),
    #which is alright, as the user needs to dump the unpatched files anyway.
    #
    #Additionally, add some common fields to the ebx/res/chunks entries so they can be treated the same.
    #=> 6 cases.

    toc=cas.readToc(tocPath)
    if not (toc.get("bundles") or toc.get("chunks")): return #there's nothing to extract (the sb might not even exist)
    sbPath=tocPath[:-3]+"sb"
    sb=open(sbPath,"rb") 

    for tocEntry in toc.bundles:
        if tocEntry.get("base"): continue
        sb.seek(tocEntry.offset)

        ###read the bundle depending on the four types (+cas+delta, +cas-delta, -cas+delta, -cas-delta) and choose the right function to write the payload
        if toc.get("cas"):
            bundle=cas.Entry(sb)
            #make empty lists for every type to make it behave the same way as noncas
            for listType in ("ebx","res","chunks"):
                if listType not in vars(bundle):
                    vars(bundle)[listType]=[]
                    
            #The noncas chunks already have originalSize calculated in Bundle.py (it was necessary to seek through the entries).
            #Calculate it for the cas chunks too. From here on, both cas and noncas ebx/res/chunks (within bundles) have size and originalSize.
            for chunk in bundle.chunks:
                chunk.originalSize=chunk.logicalOffset+chunk.logicalSize
                    
            #pick the right function
            if tocEntry.get("delta"):
                writePayload=casPatchedPayload
                sourcePath=None #the noncas writing function requires a third argument, while the cas one does not. Hence make a dummy variable.
            else:
                writePayload=casPayload
                sourcePath=None 
        else:
            if tocEntry.get("delta"):
                #The sb currently points at the delta file.
                #Read the unpatched toc of the same name to get the base bundle.
                #First of all though, get the correct path.

                #Does it work like this?
                #   Update\Patch\Data\Win32\XP1\Levels\XP1_003\XP1_003.toc
                #=> Update\Xpack1\Data\Win32\XP1\Levels\XP1_003\XP1_003.toc
                xpNum=os.path.basename(tocPath)[2] #"XP1_003.toc" => "1"
                split=tocPath.lower().rfind("patch")
                baseTocPath=tocPath[:split]+"xpack"+xpNum+tocPath[split+5:]
                if not os.path.exists(baseTocPath): #Nope? Then it must work like this:
                    #   Update\Patch\Data\Win32\XP1Weapons.toc
                    #=> Data\Win32\XP1Weapons.toc
                    baseTocPath=tocPath[:split-7]+tocPath[split+6:] #just cut out Update\Patch
                #now open the file and get the correct bundle (with the same name as the delta bundle)   
                baseToc=cas.readToc(baseTocPath)
                for baseTocEntry in baseToc.bundles:
                    if baseTocEntry.id.lower() == tocEntry.id.lower():
                        break
                else: #if no base bundle has with this name has been found:
                    pass #use the last base bundle. This is okay because it is actually not used at all (the delta has uses instructionType 3 only).
                    
                basePath=baseTocPath[:-3]+"sb"
                base=open(basePath,"rb")
                base.seek(baseTocEntry.offset)
                bundle = noncas.patchedBundle(base, sb) #create a patched bundle using base and delta
                base.close()
                writePayload=noncasPatchedPayload
                sourcePath=[basePath,sbPath] #base, delta
            else:
                bundle=noncas.unpatchedBundle(sb)
                writePayload=noncasPayload
                sourcePath=sbPath

        ###pick a good filename, make sure the file does not exist yet, create folders, call the right function to write the payload  
        for entry in bundle.ebx:
            targetPath=targetFolder+"/bundles/ebx/"+entry.name+".ebx"
            #if not "sound/" in entry.name: continue
            if prepareDir(targetPath): continue
            writePayload(entry, targetPath, sourcePath)

        for entry in bundle.res: #always add resRid to the filename. Add resMeta if it's not just nulls. resType becomes file extension.
            targetPath=targetFolder+"/bundles/res/"+entry.name+" "+hexlify(pack(">Q",entry.resRid))
            if entry.resMeta!="\0"*16: targetPath+=" "+hexlify(entry.resMeta)
            if entry.resType not in resTypes: targetPath+=".unknownres "+hex2(entry.resType)
            else: targetPath+=resTypes[entry.resType]
            if prepareDir(targetPath): continue
            writePayload(entry, targetPath, sourcePath)

        for i in xrange(len(bundle.chunks)): #id becomes the filename. If meta is not empty, add it to filename.
            entry=bundle.chunks[i]
            targetPath=targetFolder+"/chunks/"+hexlify(entry.id) +".chunk" #keep the .chunk extension for legacy reasons
            #if bundle.chunkMeta[i].meta!="\x00": targetPath+=" firstMip"+str(unpack("B",bundle.chunkMeta[i].meta[10])[0])
            #chunkMeta is useless. The same payload may have several values for firstMips so chunkMeta contains info specific to bundles, not the file itself.
            if prepareDir(targetPath): continue
            writePayload(entry, targetPath, sourcePath) 

    #Deal with the chunks which are defined directly in the toc.
    #These chunks do NOT know their originalSize.
    #Available fields: id, offset, size
    for entry in toc.chunks:
        targetPath=targetFolder+"/chunks/"+hexlify(entry.id)+".chunk"
        if prepareDir(targetPath): continue
        if toc.get("cas"):
            try:
                catEntry=cat[entry.sha1]
                if checkchunk(catEntry.path,catEntry.offset):
                    LZ77.decompressUnknownOriginalSize(catEntry.path,catEntry.offset,catEntry.size,targetPath)
            except:
                print "chunk not found", hexlify(entry.sha1)
        else:
            if checkchunk(sbPath,entry.offset):
                LZ77.decompressUnknownOriginalSize(sbPath,entry.offset,entry.size,targetPath)

    sb.close()

def checkchunk(filename, offset):
    try:
        f=open(filename,"rb")
    except:
        return False
    f.seek(offset+8)
    magic=f.read(4)
    f.close()
    #if magic=="\x48\x00\x00\x0c" or magic=="\x01\x10\x06\xC0" or magic=="\x01\x10\x00\x00":
    return True
    #return False

def prepareDir(targetPath):
    if os.path.exists(targetPath): return True
    dirName=os.path.dirname(targetPath)
    if not os.path.exists(dirName): os.makedirs(dirName) #make the directory for the dll
    print targetPath


#for each bundle, the dump script selects one of these four functions
def casPayload(bundleEntry, targetPath, sourcePath):
    try:
        catEntry=cat[bundleEntry.sha1]
        if checkchunk(catEntry.path,catEntry.offset):
            LZ77.decompress(catEntry.path,catEntry.offset,catEntry.size, bundleEntry.originalSize,targetPath)
    except:
        print "chunk not found", hexlify(bundleEntry.sha1)
def noncasPayload(entry, targetPath, sourcePath):
    if checkchunk(sourcePath,entry.offset):
        LZ77.decompress(sourcePath,entry.offset,entry.size, entry.originalSize,targetPath)
def casPatchedPayload(bundleEntry, targetPath, sourcePath):
    if bundleEntry.get("casPatchType")==2:
        catDelta=cat[bundleEntry.deltaSha1]
        catBase=cat[bundleEntry.baseSha1]
        LZ77.patchCas(catBase.path,catBase.offset,
                      catDelta.path,catDelta.offset,catDelta.size,
                      bundleEntry.originalSize,targetPath)
    else:
        casPayload(bundleEntry, targetPath, sourcePath) #if casPatchType is not 2, use the unpatched function.
def noncasPatchedPayload(entry, targetPath, sourcePath):
    LZ77.patchNoncas(sourcePath[0],entry.baseOffset,#entry.baseSize,
                     sourcePath[1], entry.deltaOffset, entry.deltaSize,
                     entry.originalSize,targetPath,
                     entry.midInstructionType, entry.midInstructionSize)




#make the paths absolute and normalize the slashes
for path in "cat1Path", "cat2Path", "cat3Path", "cat4Path", "cat5Path", "cat6Path", "cat7Path", "cat8Path", "cat9Path", "cat10Path", "cat11Path", "updateCatPath", "tocRoot", "tocRoot2":
    if path in locals():
        locals()[path]= os.path.normpath(bf4Directory+"\\"+locals()[path])

targetDirectory=os.path.normpath(targetDirectory) #it's an absolute path already


def dumpRoot(root):
    for dir0, dirs, ff in os.walk(root):
        for fname in ff:
            if fname[-4:]==".toc":
                print fname
                fname=dir0+"\\"+fname
                dump(fname,targetDirectory)


cat=dict()
try: readCat(cat, cat1Path)
except: print "cat1Path cat not found."
try: readCat(cat, cat2Path)
except: print "cat2Path cat not found."
try: readCat(cat, cat3Path)
except: print "cat3Path cat not found."
try: readCat(cat, cat4Path)
except: print "cat4Path cat not found."
try: readCat(cat, cat5Path)
except: print "cat5Path cat not found."
try: readCat(cat, cat6Path)
except: print "cat6Path cat not found."
try: readCat(cat, cat7Path)
except: print "cat7Path cat not found."
try: readCat(cat, cat8Path)
except: print "cat8Path cat not found."
try: readCat(cat, cat9Path)
except: print "cat9Path cat not found."
try: readCat(cat, cat10Path) 
except: print "cat10Path cat not found."
try: readCat(cat, cat11Path)
except: print "cat11Path cat not found."


if "tocRoot" in locals():  dumpRoot(tocRoot)
if "tocRoot2" in locals(): dumpRoot(tocRoot2)
```


And here is picture problem: 


all option need to replace is done successfully. but may be is python code or python program problem.
If somebody understand, please help.
## Post #2
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-09-29T01:36:01+00:00
- Post Title: how to fix this problem when start sw_dumper.py?

It's trying to load the LZ77.dll, and can't find it. put it where it's looking. (usually with the *.py file)
