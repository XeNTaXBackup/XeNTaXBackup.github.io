## Post #1
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-17T10:36:09+00:00
- Post Title: Frostbite 2 sound extraction research

Wop mates,

I really don't know if I'm in the good place for that subject but I would ask you something. 

As you can know, it's impossible to extract Battlefield 3 sounds for the moment and two days ago, I found a little trick in Battlefield 3 which allowed me to record ( by StereoMix configuration ) some sounds without any ambient sounds or something ( just a little bit of reverb only ). Now, I would know if some of you guys are interest for that so I'll explain you the trick. I really want to share it with the community because, as a sound designer, I like to have many clear soundbanks.

I'll write the technique once somebody is interested ( post here, not PM ), to be sure that I don't do that for nothing.

Cordialy.

Vosvoy
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-04-17T20:02:58+00:00
- Post Title: Frostbite 2 sound extraction research

Of course, go ahead!
## Post #3
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-17T20:41:21+00:00
- Post Title: Frostbite 2 sound extraction research

[DEPRECATED] NOTE: This is a fallback solution if you can't extract Battlefield 3 sounds with the way explained in the links below ( from " durandal217 " ).

All right,

I uploaded a commented YouTube video for that technique, because it's kind of hard to explain by writing.

( I prefer to prevent you that I have a shitty accent but I'll do my best to ensure that you can understand me. Also, don't pay any attention to graphics in-game because I moved on my old notebook. )

EDIT: Okay, sorry for being late guys. Here's the video ( don't try to search it on YouTube, you will never find it. You cannot watch this video if you don't have this link )

[http://www.youtube.com/watch?v=G5M9eDVy-ws](http://www.youtube.com/watch?v=G5M9eDVy-ws) 

Update 04/19/2013: Custom close captions on the video and Question-Answer on the topic.

________________________________________________
Q: What is " Stereo Mix "?

A: This is an audio configuration which allows you to record ALL SOUNDS from your computer. If you don't have it, you have to download an external tool for that.  Search on google.
________________________________________________
Q: Why are you talking about the " Soundscape thing "?

A: Because I think that the soundscape is f*cked up in this area of the map. That's why you have to move slowly to be between the place A soundscape and place B soundscape to " crash " it.
________________________________________________
Q: Is it makes a big difference ?

A: Well, if you're a maniac, like me, yes. Because you can record weapons, foley, and voice sounds without any stereo background noise ( which is a pain to remove during post-production ). As I say in my video, all you will got is a very little reverberation but nothing else.
________________________________________________
Q: Any other place where that's doing this?

A:That's my question too. I don't know if this glitch is active on another maps ( with no reverberation at all, that will be awesome ). If you find that on another maps, please tell us!
________________________________________________

If you use this technique to record the sounds with the intention to spread them around, then you're not welcome here. Keep it for yourself!

By the way, sorry for my bad english.

Stay tuned.

Vosvoy
## Post #4
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-26T20:34:14+00:00
- Post Title: Frostbite 2 sound extraction research

You can extract the sounds from BF3. 

[http://www.bfeditor.org/forums/index.ph ... opic=15731](http://www.bfeditor.org/forums/index.php?showtopic=15731)
and 
[http://www.bfeditor.org/forums/index.ph ... opic=15780](http://www.bfeditor.org/forums/index.php?showtopic=15780)

I have no idea how to use Python though.... 

Too bad I lost my mind and went through all 10,000 files in sb/toc and converted all the sounds from the 360 version.
## Post #5
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-26T21:57:42+00:00
- Post Title: Frostbite 2 sound extraction research

Oh, I thought it was impossible to convert the sounds. Too bad for me I don't have XBOX360 version of this game for the moment to check it out.
## Post #6
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-26T22:23:16+00:00
- Post Title: Frostbite 2 sound extraction research

It wasn't really impossible to begin with. The game uses the same codec as BC2 for 360, the difference here is decoding the toc/sb archives. Aluigi posted his frostbite 2 script which helped me figure out what was sound and what wasn't, of course none of the files had any names so I had to play it by ear. By simply adding .res to the end of each file I used the tools for BC2 and got the sounds converted. 

The methods I linked does a lot better, the script will decode everything AND give proper file names (and I think convert it). I tried to use the python scripts but the tutorial doesn't do a great job of explaining step by step so I don't know what I'm suppose to do, I tried, but nothing I did worked. 

You guys are a lot more experienced than I, so I'm sure you'll have no problem. One thing I should mention for those going after gun sounds is this: Unlike BC & BC2, BF3 dynamically mixes multiple sounds together to create what you hear in the game. 

In terms of in game audio, the method they employ for BF3 is leaps and bounds better then what they did in BC, however if you're looking for a particular sound of a weapon you are going to have to track down what sound files are used for a particular weapon. It is simple enough, just look at the .EBX file in a text editor and locate what file is used for mixing.
## Post #7
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-26T22:40:29+00:00
- Post Title: Frostbite 2 sound extraction research

> Reply from durandal217
>
> You guys are a lot more experienced than I, so I'm sure you'll have no problem. One thing I should mention for those going after gun sounds is this: Unlike BC & BC2, BF3 dynamically mixes multiple sounds together to create what you hear in the game. 

In terms of in game audio, the method they employ for BF3 is leaps and bounds better then what they did in BC, however if you're looking for a particular sound of a weapon you are going to have to track down what sound files are used for a particular weapon. It is simple enough, just look at the .EBX file in a text editor and locate what file is used for mixing.

Yeah, because they use some " layers " ( reflections, echoes, SFX, etc... ), based on the environment, on a same base sound. And as you said, it seems to be more tidy than BFBC2 and .dbx files were pretty messed.

By the way, thank's again mate for the links ( is it for PC version? ). I will try that when I had completed convertions of Contract Wars sounds ( maybe make a tutorial for that too, I don't know for the moment ).
## Post #8
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-26T23:54:26+00:00
- Post Title: Frostbite 2 sound extraction research

Oh you're quite welcome. I can't say for certain which version of BF3 the script supports, I couldn't confirm because in the python script it wants the location of cas.cat which I don't know what that is and there is no file in the BF3 directory with that name and extension. That was the problem I kept having and no matter what I couldn't figure out what it was and as a result couldn't get anything to extract.
## Post #9
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-04-27T05:16:30+00:00
- Post Title: Frostbite 2 sound extraction research

> Reply from durandal217
>
> because in the python script it wants the location of cas.cat which I don't know what that is.
They are used in Medal of honor warfighter which has FB2 engine too.
## Post #10
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-27T15:56:49+00:00
- Post Title: Frostbite 2 sound extraction research

@durandal217: You're definitly my lil' hero   . It works on PC version an get more of 30Gb of sounds. It's not really hard dude ( about the Python scripts ) but the process is f*cking long ( it took me 9 hours on my old notebook and more of 80Gb HDD space ).

If some of you guys need help, I would do it gladly with a lil' video tutorial.

Many regards.

Vosvoy
## Post #11
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-27T17:59:09+00:00
- Post Title: Frostbite 2 sound extraction research

will the  python script works with other fb2 games?
## Post #12
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-27T18:27:54+00:00
- Post Title: Frostbite 2 sound extraction research

> Reply from OrangeC
>
> will the  python script works with other fb2 games?

Sorry but I don't know, for the moment. I own Medal Of Honor Warfighter, but Origin is f*cking with me right now and I can't redownload it. Plus, I don't have another FB2 games.
## Post #13
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-27T19:41:16+00:00
- Post Title: Frostbite 2 sound extraction research

> Reply from OrangeC
>
> will the  python script works with other fb2 games?

If it works with BF3 and MoH, it should in theory work on any FB2 powered game. 

> Reply from Vosvoy
>
> @durandal217: You're definitly my lil' hero   . It works on PC version an get more of 30Gb of sounds. It's not really hard dude ( about the Python scripts ) but the process is f*cking long ( it took me 9 hours on my old notebook and more of 80Gb HDD space ).

If some of you guys need help, I would do it gladly with a lil' video tutorial.

Many regards.

Vosvoy

Could you post a video tutorial for future reference? I might extract the sounds from warfighter, but unless I know exactly what to do with the python script, I'd have to use the 360 method which is long, tedious, and a pain in my rear end.
## Post #14
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-27T20:25:57+00:00
- Post Title: Frostbite 2 sound extraction research

> Reply from durandal217
>
> Could you post a video tutorial for future reference? I might extract the sounds from warfighter, but unless I know exactly what to do with the python script, I'd have to use the 360 method which is long, tedious, and a pain in my rear end.

Sure mate. I will test that when Origin will stop being a d*ck and when I'll finally get my game re-downloaded.
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-27T20:34:31+00:00
- Post Title: Frostbite 2 sound extraction research

Please male tutorial for the 360 version as well.
## Post #16
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-27T21:50:24+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> Please make tutorial for the 360 version as well.

I personnally don't own BF3 or MOHW XBox360 version. Maybe I'll can make a XBox360 tutorial with the help of durandal217 who found how to convert sounds from BF3 Xbox360 version.
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-27T22:07:19+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Problem with the xbox360 version it doesnt have the cat/cas files. Wonder how can i circumvent this?
## Post #18
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-27T23:00:27+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> Problem with the xbox360 version it doesnt have the cat/cas files. Wonder how can i circumvent this?

Same.

That's probably why I couldn't get the script to work the 360 version doesn't have those files. And the way I did it was inferior to the python method. It wouldn't be of any help.

I wish I had found the python method from the beginning, because that would have saved me so much time and gave me better results.
## Post #19
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-28T04:44:59+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

That's remind me that the BF3 Open Beta version ( PC ) didn't have the .cat/.cas file. In order to extract it, I took the actual BF3 version ( PC ) .cat/.cas file and it worked.
## Post #20
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-28T05:41:59+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Is this an example of an ebx file? how can i link this to the actual file in the chunk SB archive? It comes from army of two devils cartel bundle file with aluigis script.
[mus_theme_ol_02.rar](https://xentaxbackup.github.io/file/6361_mus_theme_ol_02.rar)
## Post #21
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-28T07:43:45+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Yeah it looks like a .ebx file. 

I don't really understand what you mean by " link this to the actual file in the chunk SB archive ".
## Post #22
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-28T17:24:33+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

how to find the right chunk ID to the actual data in the .sb/toc file.
## Post #23
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-28T18:47:00+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> how to find the right chunk ID to the actual data in the .sb/toc file.

I think that I have a lil' idea for BF3 Xbox360 users but don't know if it's prohibited by the website rules: Provide the correct ( by " correct ", I mean readable ) converted .ebx files ( .txt files ) that contains chunks ID informations. Therefore, you will be able to recognize the sounds extracted from .sb/.toc files ( with aluigi's script ), but it's just a supposition and it can be a very very very very long process...

Waiting for moderation before anything.
## Post #24
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-28T19:04:15+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Hmm seems medal of honor is giving me a key error when using the dumper script. Even have it on python 32bit but halfway it just stops with an error.

EDIT: okay seems aluigis script doesnt dump the ebx files correctly.
## Post #25
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-28T19:46:46+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> Hmm seems medal of honor is giving me a key error when using the dumper script. Even have it on python 32bit but halfway it just stops with an error.

Which version 360? 

I tried something dumb after Vosvoy mentioned it, I grabbed a cas.cat file from the PC version of BF3 and placed it into the 360 BF3 directory, I then tried the python script, It starts extracting than stops with KeyError: 2899910632L.

It was worth a try.
## Post #26
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-28T20:03:19+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

PC version actually. I just tried  commenting now the unpatched files. Maybe i was trying to extract patched cas files with unpatched root folder. Hope it works now.

EDIT:Still nothing. Pissing me off now.
## Post #27
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-29T05:37:43+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

@OrangeC: Yeah it gave me an error too. You have to remove ( temporarly ) " 010_YemenTraining " .sb + .toc and " 067_Darra " .sb + .toc from MOHW\Data\Win32\MOHW\Levels\SP and MOHW\Update\Patch\Data\Win32\MOHW\Levels\SP. Personnaly, I did that and it works.

@durandal217: What is the error that pops-up in IDLE ( Traceback )?
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-29T05:52:49+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Wil try that.

Heres my error.

Traceback (most recent call last):
  File "C:\Python27\dumper.py", line 279, in <module>
    main()
  File "C:\Python27\dumper.py", line 277, in main
    dump(fname,outputfolder)
  File "C:\Python27\dumper.py", line 157, in dump
    casHandlePayload(entry,resPath+entry.elems["name"].content+resTypes[entry.elems["resType"].content])
KeyError: 3336302087L

EDIT: After going through the whole dumping process of warfighter i can say that there is a a bunch of erors randomly occuring when dumping the file and when im using the bf3decoder script as well i get a strange length as well.
## Post #29
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-29T16:06:55+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> Traceback (most recent call last):
  File "C:\Python27\dumper.py", line 279, in <module>
    main()
  File "C:\Python27\dumper.py", line 277, in main
    dump(fname,outputfolder)
  File "C:\Python27\dumper.py", line 157, in dump
    casHandlePayload(entry,resPath+entry.elems["name"].content+resTypes[entry.elems["resType"].content])
KeyError: 3336302087L

Forgive me, I forgot to tell you something more: If you only interested by sounds, please skip .res dumping by removing specifics lines code because it's kind of bugy:

Copy/paste this code in dumper.py ON the old one ( don't forget to change the paths if necessary ):

```
import Bundle
import os
from binascii import hexlify,unhexlify
from struct import pack,unpack
from cStringIO import StringIO
import sys
import zlib

####Adjust paths here. The script doesn't overwrite existing files so set tocRoot to the patched files first, then run the script again with the unpatched ones to get all files at their most recent version.

catName=r":\MOHW\Data\cas.cat"
patchedCatName=r":\MOHW\Update\Patch\Data\cas.cat" #used only when tocRoot contains "Update"

tocRoot=r":\MOHW\Data\Win32"
##tocRoot=r"C:\Program Files (x86)\Origin Games\Battlefield 3\Data\Win32"

outputfolder=":\"


############
############


def zlibb(f, size):
    ###give back the data directly if it is not in zlib format
    v1,v2=unpack(">II",f.read(8))
    magic=f.read(2)
    f.seek(-10,1)
    if magic!="\x78\xda" and v1!=v2: return f.read(size)
    ###
    outStream=StringIO()
    pos0=f.tell()
    while f.tell()<pos0+size:
        uncompressedSize,compressedSize=unpack(">II",f.read(8)) #big endian
        if compressedSize!=uncompressedSize: outStream.write(zlib.decompress(f.read(compressedSize)))
        else:
            magic=f.read(2)
            f.seek(-2,1) #hope that no uncompressed part starts with 78da:
            if magic=="\x78\xda": outStream.write(zlib.decompress(f.read(compressedSize)))
            else:                 outStream.write(f.read(compressedSize))   
    data=outStream.getvalue()
    outStream.close()
    return data

def zlibIdata(bytestring):
    return zlibb(StringIO(bytestring),len(bytestring))


class Stub(): pass


class Cat:
    def __init__(self,catname):
        cat2=open(catname,"rb")
        cat=sbtoc.unXOR(cat2)

        self.casfolder=os.path.dirname(catname)+"\\"
        cat.seek(0,2)
        catsize=cat.tell()
        cat.seek(16)
        self.entries=dict()
        while cat.tell()<catsize:
            entry=Stub()
            sha1=cat.read(20)
            entry.offset, entry.size, entry.casnum = unpack("<III",cat.read(12))
            self.entries[sha1]=entry
        cat.close()
        cat2.close()
       
    def grabPayload(self,entry):
        cas=open(self.casfolder+"cas_"+("0"+str(entry.casnum) if entry.casnum<10 else str(entry.casnum))+".cas","rb")
        cas.seek(entry.offset)
        payload=cas.read(entry.size)
        cas.close()
        return payload
    def grabPayloadZ(self,entry):
        cas=open(self.casfolder+"cas_"+("0"+str(entry.casnum) if entry.casnum<10 else str(entry.casnum))+".cas","rb")
        cas.seek(entry.offset)
        payload=zlibb(cas,entry.size)
        cas.close()
        return payload
     
def open2(path,mode):
    #create folders if necessary and return the file handle
    folderPath=os.path.dirname(path)
    if not os.path.isdir(folderPath): os.makedirs(folderPath)
    return open(path,mode)


def dump(tocName,outpath):
    try:
        toc=sbtoc.Superbundle(tocName)
    except IOError:
        return
    
    sb=open(toc.fullpath+".sb","rb")

    chunkPathToc=os.path.join(outpath,"chunks")+"/"
    #
    bundlePath=os.path.join(outpath,"bundles")+"/"
    ebxPath=bundlePath+"ebx/"
    dbxPath=bundlePath+"dbx/"       
    chunkPath=bundlePath+"chunks/"

    
    if "cas" in toc.entry.elems and toc.entry.elems["cas"].content==True:
        #deal with cas bundles => ebx, dbx, res, chunks. 
        for tocEntry in toc.entry.elems["bundles"].content: #id offset size, size is redundant
            sb.seek(tocEntry.elems["offset"].content)
            bundle=sbtoc.Entry(sb)

            for listType in ["ebx","dbx","chunks"]: #make empty lists for every type to get rid of key errors(=> less indendation)
                if listType not in bundle.elems:
                    bundle.elems[listType]=Stub()
                    bundle.elems[listType].content=[]
            
            for entry in bundle.elems["ebx"].content: #name sha1 size originalSize
                casHandlePayload(entry,ebxPath+entry.elems["name"].content+".ebx")
           
            for entry in bundle.elems["dbx"].content: #name sha1 size originalSize
                if "idata" in entry.elems: #dbx appear only idata if at all, they are probably deprecated and were not meant to be shipped at all.
                    out=open2(dbxPath+entry.elems["name"].content+".dbx","wb")
                    if entry.elems["size"].content==entry.elems["originalSize"].content:
                        out.write(entry.elems["idata"].content)
                    else:          
                        out.write(zlibIdata(entry.elems["idata"].content))
                    out.close()    
                
            for entryNum in xrange(len(bundle.elems["chunks"].content)): #id sha1 size, chunkMeta::meta
                entry=bundle.elems["chunks"].content[entryNum]
                entryMeta=bundle.elems["chunkMeta"].content[entryNum]
                if entryMeta.elems["meta"].content=="\x00":
                    firstMip=""
                else:
                    firstMip=" firstMip"+str(unpack("B",entryMeta.elems["meta"].content[10])[0])

                casHandlePayload(entry,chunkPath+hexlify(entry.elems["id"].content)+firstMip+".chunk")


        #deal with cas chunks defined in the toc. 
        for entry in toc.entry.elems["chunks"].content: #id sha1
            casHandlePayload(entry,chunkPathToc+hexlify(entry.elems["id"].content)+".chunk")

    else:
        #deal with noncas bundles
        for tocEntry in toc.entry.elems["bundles"].content: #id offset size, size is redundant
            sb.seek(tocEntry.elems["offset"].content)
            try:
                bundle=Bundle.Bundle(sb)
            except:
                print "Ignoring patched noncas bundle file from: "+toc.fullpath
                continue #

            for entry in bundle.ebxEntries:
                noncasHandlePayload(sb,entry,ebxPath+entry.name+".ebx")


            for entry in bundle.chunkEntries:
                if entry.meta=="\x00":
                    firstMip=""
                else:
                    firstMip=" firstMip"+str(unpack("B",entry.meta[10])[0])
                noncasHandlePayload(sb,entry,chunkPath+hexlify(entry.id)+firstMip+".chunk")

        #deal with noncas chunks defined in the toc
        for entry in toc.entry.elems["chunks"].content: #id offset size
            entry.offset,entry.size = entry.elems["offset"].content,entry.elems["size"].content #to make the function work
            noncasHandlePayload(sb,entry,chunkPathToc+hexlify(entry.elems["id"].content)+".chunk")          

def noncasHandlePayload(sb,entry,outPath):
    if os.path.exists(outPath): return
    print outPath
    sb.seek(entry.offset)
    out=open2(outPath,"wb")
    if "originalSize" in vars(entry):
        if entry.size==entry.originalSize:
            out.write(sb.read(entry.size))
        else:
            out.write(zlibb(sb,entry.size))
    else:
        out.write(zlibb(sb,entry.size))
    out.close()



cat=Cat(catName)

if "Update" in tocRoot:
    cat2=Cat(patchedCatName)
    def casHandlePayload(entry,outPath): #this version searches the patched cat first
        if os.path.exists(outPath): return #don't overwrite existing files to speed up things
        print outPath
        if "originalSize" in entry.elems:
            compressed=False if entry.elems["size"].content==entry.elems["originalSize"].content else True #I cannot tell for certain if this is correct. I do not have any negative results though.
        else:
            compressed=True
        if "idata" in entry.elems:
            out=open2(outPath,"wb")
            if compressed: out.write(zlibIdata(entry.elems["idata"].content))
            else:          out.write(entry.elems["idata"].content)

        else:        
            try:
                catEntry=cat2.entries[entry.elems["sha1"].content]
                activeCat=cat2
            except:
                catEntry=cat.entries[entry.elems["sha1"].content]
                activeCat=cat
            out=open2(outPath,"wb") #don't want to create an empty file in case an error pops up
            if compressed: out.write(activeCat.grabPayloadZ(catEntry))
            else:          out.write(activeCat.grabPayload(catEntry))

        out.close()
        

else:
    def casHandlePayload(entry,outPath): #this version uses the unpatched cat only
        if os.path.exists(outPath): return #don't overwrite existing files to speed up things
        print outPath
        if "originalSize" in entry.elems:
            compressed=False if entry.elems["size"].content==entry.elems["originalSize"].content else True #I cannot tell for certain if this is correct. I do not have any negative results though.
        else:
            compressed=True
        if "idata" in entry.elems:
            out=open2(outPath,"wb")
            if compressed: out.write(zlibIdata(entry.elems["idata"].content))
            else:          out.write(entry.elems["idata"].content)
        else:        
            catEntry=cat.entries[entry.elems["sha1"].content]
            out=open2(outPath,"wb") #don't want to create an empty file in case an error pops up
            if compressed: out.write(cat.grabPayloadZ(catEntry))
            else:          out.write(cat.grabPayload(catEntry))
        out.close()

def main():
    for dir0, dirs, ff in os.walk(tocRoot):
        for fname in ff:
            if fname[-4:]==".toc":
                print fname
                fname=dir0+"\\"+fname
                dump(fname,outputfolder)        

main()
```


Now you'll be able to dump the .sb/.toc archives without any errors ( normally... ).

> I get a strange length as well.

Yes I know, it happened to me too. So I removed each .ebx files that " crashed " the script ( I don't know why it's doing that. I ask on the BFEditor forum but still no answer ). For the moment, I have firearms/explosions and foley sounds.

EDIT: Ok I managed how to automatically " ignore " the sounds that the script don't like and extract the others. Just replace the ligne 450 by this one in " bf3decoder.py ":

```
                    if length%76!=0: return #raise Exception("Strange length: "+str(length))
```

I just add " return " but for a noob in coding like me, it's a lil' victory  .

@durandal217: Don't forget to tell me what is the error text in red ( Traceback ) that poped-up in your Python IDLE Shell and I'll try to see what's going on ( I'll even try to get a BF3 Xbox360 version to do the same thing you did ).
## Post #30
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-29T17:18:43+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Here it is:

```
  File "C:\Users\Durandal-217\Desktop\dumper.py", line 279, in <module>
    main()
  File "C:\Users\Durandal-217\Desktop\dumper.py", line 277, in main
    dump(fname,outputfolder)
  File "C:\Users\Durandal-217\Desktop\dumper.py", line 191, in dump
    noncasHandlePayload(sb,entry,resPath+entry.name+resTypes[entry.resType])
KeyError: 2899910632L
>>> 
```


Hope it helps.
## Post #31
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-29T17:34:56+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from durandal217
>
> Here it is:
Code: Select allTraceback (most recent call last):
  File "C:\Users\Durandal-217\Desktop\dumper.py", line 279, in <module>
    main()
  File "C:\Users\Durandal-217\Desktop\dumper.py", line 277, in main
    dump(fname,outputfolder)
  File "C:\Users\Durandal-217\Desktop\dumper.py", line 191, in dump
    noncasHandlePayload(sb,entry,resPath+entry.name+resTypes[entry.resType])
KeyError: 2899910632L
>>> 

Hope it helps.

Yeah, do exactly the same thing as I said above about .res files and tell me if it worked  .
## Post #32
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-29T18:01:51+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Sure, as soon as I get back to my desktop, ill give it a try and let you know if it works.
## Post #33
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-29T18:55:14+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

How do i go about changing the endian in the ebx to txt script?

EDIT: I have extracted from army of two as well x360 version. seems to work as it reads from the sb/toc files. Can't get the ebx files to convert to txt with the ebx script.
[mus_00_prologue_cp100_interface.rar](https://xentaxbackup.github.io/file/6371_mus_00_prologue_cp100_interface.rar)
## Post #34
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-29T19:39:57+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

I'll take a look but I don't think that I would be of great benefit because I'm not a master in coding. All I can say for the moment: .ebx files from Army of Two seems to be " big-endian " ( the dice magic is " 0F B2 D1 CE " for Army of Two and " CE D1 B2 0F " for MOHW ).

Did you get an error during convertion in the IDLE Shell?
## Post #35
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-29T20:24:02+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Just wanted to confirm the script works for BF3 Xbox 360. 

Now I tried the same thing for MOH PC, and it all properly extracts but when I try to convert the sounds I get this error: 

```
  File "C:\test\bf3decoder.py", line 507, in <module>
    xaslib = cdll.LoadLibrary("xas")
  File "C:\Python27\lib\ctypes\__init__.py", line 443, in LoadLibrary
    return self._dlltype(name)
  File "C:\Python27\lib\ctypes\__init__.py", line 365, in __init__
    self._handle = _dlopen(self._name, mode)
WindowsError: [Error 126] The specified module could not be found
>>> 
```


What am I doing wrong?
## Post #36
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-30T00:11:25+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from Vosvoy
>
> I'll take a look but I don't think that I would be of great benefit because I'm not a master in coding. All I can say for the moment: .ebx files from Army of Two seems to be " big-endian " ( the dice magic is " 0F B2 D1 CE " for Army of Two and " CE D1 B2 0F " for MOHW ).

Did you get an error during convertion in the IDLE Shell?

I actually didn't get any prompt at all. just exited. I also tried changing the endian order of the bytes in these values here but  then it gives me an error. Unless if i needed to change something else in the script.

```
##############################################################
if useExplorerNames:
    def createGuidTable(): #guid vs filename
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                path=os.path.join(dir0,fname)
                f=open(path,"rb")
                if f.read(4)!="\xCE\xD1\xB2\x0F":
                    f.close()
                    continue
                #grab the file guid directly, absolute offset 48 bytes
                f.seek(48)
                fileguid=f.read(16)
                f.close()
                filename=path[len(inputFolder):-4].replace("\\","/")
                guidTable[fileguid]=filename
else:
    def createGuidTable():
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                f=open(dir0+"\\"+fname,"rb")
                if f.read(4)!="\xCE\xD1\xB2\x0F":
                    f.close()
                    continue
                dbx=Dbx(f)
                guidTable[dbx.fileGUID]=dbx.trueFilename
        f5=open(guidTableName,"wb") #write the table
        cPickle.dump(guidTable,f5)
        f5.close()

```
## Post #37
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-30T05:31:34+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from durandal217
>
> Just wanted to confirm the script works for BF3 Xbox 360. 

Now I tried the same thing for MOH PC, and it all properly extracts but when I try to convert the sounds I get this error: 
Code: Select allTraceback (most recent call last):
  File "C:\test\bf3decoder.py", line 507, in <module>
    xaslib = cdll.LoadLibrary("xas")
  File "C:\Python27\lib\ctypes\__init__.py", line 443, in LoadLibrary
    return self._dlltype(name)
  File "C:\Python27\lib\ctypes\__init__.py", line 365, in __init__
    self._handle = _dlopen(self._name, mode)
WindowsError: [Error 126] The specified module could not be found
>>> 

What am I doing wrong?

Is xas.dll is in the same folder as bf3decoder.py?
## Post #38
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-30T07:53:11+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

wanted to confirm NFS the run extracts flawlessly PC version.

however mohw still gives me errors with the modified dumper script.

I am also gonna test ao2 ps3 sound convertion since most likely its as.

will report back.

EDIT: Script is unable to read ebx files from console version. doesn't give any error just does nothing.
## Post #39
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-30T14:38:29+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from Vosvoy
>
> Is xas.dll is in the same folder as bf3decoder.py?

No it's not in any folder, just on my desktop same as BF3decoder.py.
## Post #40
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-30T16:03:47+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Fixed the endian problem. now this.

```
  File "C:\Python27\ebxtotxt.py", line 306, in <module>
    main()
  File "C:\Python27\ebxtotxt.py", line 38, in main
    dumpText()
  File "C:\Python27\ebxtotxt.py", line 83, in dumpText
    dbx=Dbx(f)
  File "C:\Python27\ebxtotxt.py", line 165, in __init__
    self.fieldDescriptors=[FieldDescriptor(unpack("IHHII",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
error: unpack requires a string argument of length 16
```
## Post #41
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-30T16:42:49+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

@durandal217: It's very strange because this error 127 appear when the requested library ( in that case: xas.dll ) is not in the same folder as the python script. I never get this error before. Try to move your script with xas.dll and floattostring.dll ( a copy of it ) in a specified folder ( don't forget to change the paths in the script ). Otherwise, if it still crashing, reboot your computer ( we never know ).

@OrangeC: Seems that .ebx files from Army of Two doesn't have the same string lenght as BF3 .ebx files. I think that it's "8" but I'm not sure. By the way, can you please tell me what did you changed in the line code? I would try too on your file.
## Post #42
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-30T17:17:53+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

I changed the byte order in the required feilds.

```
    for dir0, dirs, ff in os.walk(ebxFolder):
        for fname in ff:
            f=open(dir0+"\\"+fname,"rb")
            if f.read(4)!="\x0F\xB2\xD1\xCE":
                f.close()
                continue
            dbx=Dbx(f)
            dbx.decode()

def valid(fname):
    f=open(fname,"rb")
    if f.read(4)!="\x0F\xB2\xD1\xCE":
        f.close()
        raise Exception("nope")
    return f

class nullguid(Exception):
    def __init__(self, value):
        self.value = value
    def __str__(self):
        return repr(self.value)]/code]

i have already changed it to big endian.
```
## Post #43
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-30T18:00:47+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> I changed the byte order in the required feilds.
Code: Select alldef decodeAudio():
    for dir0, dirs, ff in os.walk(ebxFolder):
        for fname in ff:
            f=open(dir0+"\\"+fname,"rb")
            if f.read(4)!="\x0F\xB2\xD1\xCE":
                f.close()
                continue
            dbx=Dbx(f)
            dbx.decode()

def valid(fname):
    f=open(fname,"rb")
    if f.read(4)!="\x0F\xB2\xD1\xCE":
        f.close()
        raise Exception("nope")
    return f

class nullguid(Exception):
    def __init__(self, value):
        self.value = value
    def __str__(self):
        return repr(self.value)]/code]

i have already changed it to big endian.[/quote]

I meant the ebx script, sorry ;)

And another question, where did you find your ressources for coding. I mean you're pretty good no? And I would help people like you usually do in the forum.

PS: I would to know if some of you guys have BF3 Alpha here on Xentax! Please tell us!
## Post #44
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-30T20:12:01+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Hehe i wouldn't know how to code anything except recognize some really n00bish stuff in the script.


Find the bytes in brackets in the ebx script.


```
##############################################################
if useExplorerNames:
    def createGuidTable(): #guid vs filename
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                path=os.path.join(dir0,fname)
                f=open(path,"rb")
                if f.read(4)!="\[b]xCE\xD1\xB2\x0F[/b]":
                    f.close()
                    continue
                #grab the file guid directly, absolute offset 48 bytes
                f.seek(48)
                fileguid=f.read(16)
                f.close()
                filename=path[len(inputFolder):-4].replace("\\","/")
                guidTable[fileguid]=filename
else:
    def createGuidTable():
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                f=open(dir0+"\\"+fname,"rb")
                if f.read(4)!="\[b]xCE\xD1\xB2\x0F[/b]":
                    f.close()
                    continue
                dbx=Dbx(f)
                guidTable[dbx.fileGUID]=dbx.trueFilename
        f5=open(guidTableName,"wb") #write the table
        cPickle.dump(guidTable,f5)
        f5.close()

def dumpText():
    for dir0, dirs, ff in os.walk(inputFolder):
        for fname in ff:
            f=open(dir0+"\\"+fname,"rb")
            if f.read(4)!="\[b]xCE\xD1\xB2\x0F[/b]":
                f.close()
                continue
            dbx=Dbx(f)
            dbx.dump(outputFolder)
```


```
if f.read(4)!="\xCE\xD1\xB2\x0F":
```
 Should be reversed like so.

```
if f.read(4)!="\x0f\xB2\xD1\xCE":
```


changes to support Big endian.

However as you know im still getting the 16 string error argument. So if anyone else can figure out what line to change id really appreciate it.
## Post #45
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-30T20:55:08+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from Vosvoy
>
> @durandal217: It's very strange because this error 127 appear when the requested library ( in that case: xas.dll ) is not in the same folder as the python script. I never get this error before. Try to move your script with xas.dll and floattostring.dll ( a copy of it ) in a specified folder ( don't forget to change the paths in the script ). Otherwise, if it still crashing, reboot your computer ( we never know ).

I tried what you said and downloaded, floattostring.dll which I didn't have put everything in the same folder, tried it, still get error 126. Even tried rebooting, still get the same error.

EDIT: I keep reading about a dbx3.py, I never saw anything about that what is it? And where do I get it I keep searching and can't find anything on it.
## Post #46
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-30T21:17:49+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from durandal217
>
> floattostring.dll which I didn't have put everything in the same folder

Then, last solution: put floattostring.dll in the main python folder ( by default C:\Python27 ) if you didn't already did it.
## Post #47
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-30T21:18:39+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from Vosvoy
>
> durandal217 wrote:floattostring.dll which I didn't have put everything in the same folder

Then, last solution: put floattostring.dll in the main python folder ( by default C:\Python27 ) if you didn't already did it.

Ah OK let me try that.
## Post #48
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-30T21:22:29+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Tried it still get the same error.

EDIT: by the way what is dbx3.py that I keep reading about, I don't have that nor did I see any instructions for that anywhere besides "Run the script with F5. And read the short comment in the dbx3.py file to interpret the indices at the end of the filenames."
## Post #49
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-04-30T21:25:14+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

WOAH ACTUAL PROGRESS? ON BF3/MOHWF SOUND RIPPING ON PC? Color me impressed, I had to just use search for the hex values 480000C or something of the like in the sb/toc's on xbox360 files to rip the games. was a pain in the ass and gave 10k+ files no names.
## Post #50
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-30T21:29:34+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Yeah we are progressing, thanks to frankenstein dude or w/e his name is.

I tested it out on nfs run pc an works flawlessly. Only issue im having is converting MOHW pc sounds and the dumper.py still is giving me errors in dumping from mohw unless if im doing something wrong. BF3 decoder still cant convert mohw music all the way.

Tested dumper/ebx scripts on army of two the devils cartel and since its big endian and string count might be diferent it will not convert ebx to txt nor convert audio files since ebx's are not readable.
## Post #51
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-30T22:24:50+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from durandal217
>
> Tried it still get the same error.

EDIT: by the way what is dbx3.py that I keep reading about, I don't have that nor did I see any instructions for that anywhere besides "Run the script with F5. And read the short comment in the dbx3.py file to interpret the indices at the end of the filenames."

I don't know why he is talking about dbx3 neither. Hey, I just think about something: You got XBox360 version right? So, try to extract " *_wave " .ebx files with Battlefield bad company 2 technique ( maybe .xma files ? ).
## Post #52
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-30T22:29:17+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Whats the Bad company 2 technique and would it convert the ebx to txt?
## Post #53
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-30T22:40:58+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> Whats the Bad company 2 technique and would it convert the ebx to txt?

The Bad Company 2 technique of converting .res files to WAV.  In this case he is talking about extracting the data from the 360 version of the game and converting the ebx to txt, search for the ChunkId and then locate it, add a .res extension and covert it using ToWav.
## Post #54
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-30T22:48:55+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from durandal217
>
> OrangeC wrote:Whats the Bad company 2 technique and would it convert the ebx to txt?

The Bad Company 2 technique of converting .res files to WAV.  In this case he is talking about extracting the data from the 360 version of the game and converting the ebx to txt, search for the ChunkId and then locate it, add a .res extension and covert it using ToWav.

You'll be able to do that man? I mean NOW you've got the filenames ( .ebx files ).

> Reply from OrangeC
>
> Only issue im having is converting MOHW pc sounds and the dumper.py still is giving me errors in dumping from mohw

I really don't understand why it's still doing that for you mate. I removed " 010_YemenTraining " .sb + .toc and " 067_Darra " .sb + .toc from the main folder, I edited the script to ignore .res files and it let me go away.

Other error to inform?
## Post #55
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-30T22:59:02+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Well the problem is not converting 360 files (xma) since theres ea_multi_xma and the various header scripts. The problem is getting the chunkID out of the ebx files. I cannot convert console ebx files to txt to get the chunkID. The ebx converter script doesn't work on the ebx stuff from consoles.

EDIT: What part of the script did you edit?
## Post #56
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-04-30T23:07:54+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Back to square one then....
## Post #57
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-30T23:21:28+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

( Deleted content )
## Post #58
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-30T23:24:38+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> Well the problem is not converting 360 files (xma) since theres ea_multi_xma and the various header scripts. The problem is getting the chunkID out of the ebx files. I cannot convert console ebx files to txt to get the chunkID. The ebx converter script doesn't work on the ebx stuff from consoles.

EDIT: What part of the script did you edit?

The one that I told you there ( for correct MOHW dumping ): 

```
import Bundle
import os
from binascii import hexlify,unhexlify
from struct import pack,unpack
from cStringIO import StringIO
import sys
import zlib

####Adjust paths here. The script doesn't overwrite existing files so set tocRoot to the patched files first, then run the script again with the unpatched ones to get all files at their most recent version.

catName=r":\MOHW\Data\cas.cat"
patchedCatName=r":\MOHW\Update\Patch\Data\cas.cat" #used only when tocRoot contains "Update"

tocRoot=r":\MOHW\Data\Win32"
##tocRoot=r"C:\Program Files (x86)\Origin Games\Battlefield 3\Data\Win32"

outputfolder=":\"


############
############


def zlibb(f, size):
    ###give back the data directly if it is not in zlib format
    v1,v2=unpack(">II",f.read(8))
    magic=f.read(2)
    f.seek(-10,1)
    if magic!="\x78\xda" and v1!=v2: return f.read(size)
    ###
    outStream=StringIO()
    pos0=f.tell()
    while f.tell()<pos0+size:
        uncompressedSize,compressedSize=unpack(">II",f.read(8)) #big endian
        if compressedSize!=uncompressedSize: outStream.write(zlib.decompress(f.read(compressedSize)))
        else:
            magic=f.read(2)
            f.seek(-2,1) #hope that no uncompressed part starts with 78da:
            if magic=="\x78\xda": outStream.write(zlib.decompress(f.read(compressedSize)))
            else:                 outStream.write(f.read(compressedSize))   
    data=outStream.getvalue()
    outStream.close()
    return data

def zlibIdata(bytestring):
    return zlibb(StringIO(bytestring),len(bytestring))


class Stub(): pass


class Cat:
    def __init__(self,catname):
        cat2=open(catname,"rb")
        cat=sbtoc.unXOR(cat2)

        self.casfolder=os.path.dirname(catname)+"\\"
        cat.seek(0,2)
        catsize=cat.tell()
        cat.seek(16)
        self.entries=dict()
        while cat.tell()<catsize:
            entry=Stub()
            sha1=cat.read(20)
            entry.offset, entry.size, entry.casnum = unpack("<III",cat.read(12))
            self.entries[sha1]=entry
        cat.close()
        cat2.close()
       
    def grabPayload(self,entry):
        cas=open(self.casfolder+"cas_"+("0"+str(entry.casnum) if entry.casnum<10 else str(entry.casnum))+".cas","rb")
        cas.seek(entry.offset)
        payload=cas.read(entry.size)
        cas.close()
        return payload
    def grabPayloadZ(self,entry):
        cas=open(self.casfolder+"cas_"+("0"+str(entry.casnum) if entry.casnum<10 else str(entry.casnum))+".cas","rb")
        cas.seek(entry.offset)
        payload=zlibb(cas,entry.size)
        cas.close()
        return payload
     
def open2(path,mode):
    #create folders if necessary and return the file handle
    folderPath=os.path.dirname(path)
    if not os.path.isdir(folderPath): os.makedirs(folderPath)
    return open(path,mode)


def dump(tocName,outpath):
    try:
        toc=sbtoc.Superbundle(tocName)
    except IOError:
        return
   
    sb=open(toc.fullpath+".sb","rb")

    chunkPathToc=os.path.join(outpath,"chunks")+"/"
    #
    bundlePath=os.path.join(outpath,"bundles")+"/"
    ebxPath=bundlePath+"ebx/"
    dbxPath=bundlePath+"dbx/"       
    chunkPath=bundlePath+"chunks/"

   
    if "cas" in toc.entry.elems and toc.entry.elems["cas"].content==True:
        #deal with cas bundles => ebx, dbx, res, chunks.
        for tocEntry in toc.entry.elems["bundles"].content: #id offset size, size is redundant
            sb.seek(tocEntry.elems["offset"].content)
            bundle=sbtoc.Entry(sb)

            for listType in ["ebx","dbx","chunks"]: #make empty lists for every type to get rid of key errors(=> less indendation)
                if listType not in bundle.elems:
                    bundle.elems[listType]=Stub()
                    bundle.elems[listType].content=[]
           
            for entry in bundle.elems["ebx"].content: #name sha1 size originalSize
                casHandlePayload(entry,ebxPath+entry.elems["name"].content+".ebx")
           
            for entry in bundle.elems["dbx"].content: #name sha1 size originalSize
                if "idata" in entry.elems: #dbx appear only idata if at all, they are probably deprecated and were not meant to be shipped at all.
                    out=open2(dbxPath+entry.elems["name"].content+".dbx","wb")
                    if entry.elems["size"].content==entry.elems["originalSize"].content:
                        out.write(entry.elems["idata"].content)
                    else:         
                        out.write(zlibIdata(entry.elems["idata"].content))
                    out.close()   
               
            for entryNum in xrange(len(bundle.elems["chunks"].content)): #id sha1 size, chunkMeta::meta
                entry=bundle.elems["chunks"].content[entryNum]
                entryMeta=bundle.elems["chunkMeta"].content[entryNum]
                if entryMeta.elems["meta"].content=="\x00":
                    firstMip=""
                else:
                    firstMip=" firstMip"+str(unpack("B",entryMeta.elems["meta"].content[10])[0])

                casHandlePayload(entry,chunkPath+hexlify(entry.elems["id"].content)+firstMip+".chunk")


        #deal with cas chunks defined in the toc.
        for entry in toc.entry.elems["chunks"].content: #id sha1
            casHandlePayload(entry,chunkPathToc+hexlify(entry.elems["id"].content)+".chunk")

    else:
        #deal with noncas bundles
        for tocEntry in toc.entry.elems["bundles"].content: #id offset size, size is redundant
            sb.seek(tocEntry.elems["offset"].content)
            try:
                bundle=Bundle.Bundle(sb)
            except:
                print "Ignoring patched noncas bundle file from: "+toc.fullpath
                continue #

            for entry in bundle.ebxEntries:
                noncasHandlePayload(sb,entry,ebxPath+entry.name+".ebx")


            for entry in bundle.chunkEntries:
                if entry.meta=="\x00":
                    firstMip=""
                else:
                    firstMip=" firstMip"+str(unpack("B",entry.meta[10])[0])
                noncasHandlePayload(sb,entry,chunkPath+hexlify(entry.id)+firstMip+".chunk")

        #deal with noncas chunks defined in the toc
        for entry in toc.entry.elems["chunks"].content: #id offset size
            entry.offset,entry.size = entry.elems["offset"].content,entry.elems["size"].content #to make the function work
            noncasHandlePayload(sb,entry,chunkPathToc+hexlify(entry.elems["id"].content)+".chunk")         

def noncasHandlePayload(sb,entry,outPath):
    if os.path.exists(outPath): return
    print outPath
    sb.seek(entry.offset)
    out=open2(outPath,"wb")
    if "originalSize" in vars(entry):
        if entry.size==entry.originalSize:
            out.write(sb.read(entry.size))
        else:
            out.write(zlibb(sb,entry.size))
    else:
        out.write(zlibb(sb,entry.size))
    out.close()



cat=Cat(catName)

if "Update" in tocRoot:
    cat2=Cat(patchedCatName)
    def casHandlePayload(entry,outPath): #this version searches the patched cat first
        if os.path.exists(outPath): return #don't overwrite existing files to speed up things
        print outPath
        if "originalSize" in entry.elems:
            compressed=False if entry.elems["size"].content==entry.elems["originalSize"].content else True #I cannot tell for certain if this is correct. I do not have any negative results though.
        else:
            compressed=True
        if "idata" in entry.elems:
            out=open2(outPath,"wb")
            if compressed: out.write(zlibIdata(entry.elems["idata"].content))
            else:          out.write(entry.elems["idata"].content)

        else:       
            try:
                catEntry=cat2.entries[entry.elems["sha1"].content]
                activeCat=cat2
            except:
                catEntry=cat.entries[entry.elems["sha1"].content]
                activeCat=cat
            out=open2(outPath,"wb") #don't want to create an empty file in case an error pops up
            if compressed: out.write(activeCat.grabPayloadZ(catEntry))
            else:          out.write(activeCat.grabPayload(catEntry))

        out.close()
       

else:
    def casHandlePayload(entry,outPath): #this version uses the unpatched cat only
        if os.path.exists(outPath): return #don't overwrite existing files to speed up things
        print outPath
        if "originalSize" in entry.elems:
            compressed=False if entry.elems["size"].content==entry.elems["originalSize"].content else True #I cannot tell for certain if this is correct. I do not have any negative results though.
        else:
            compressed=True
        if "idata" in entry.elems:
            out=open2(outPath,"wb")
            if compressed: out.write(zlibIdata(entry.elems["idata"].content))
            else:          out.write(entry.elems["idata"].content)
        else:       
            catEntry=cat.entries[entry.elems["sha1"].content]
            out=open2(outPath,"wb") #don't want to create an empty file in case an error pops up
            if compressed: out.write(cat.grabPayloadZ(catEntry))
            else:          out.write(cat.grabPayload(catEntry))
        out.close()

def main():
    for dir0, dirs, ff in os.walk(tocRoot):
        for fname in ff:
            if fname[-4:]==".toc":
                print fname
                fname=dir0+"\\"+fname
                dump(fname,outputfolder)       

main()
```
## Post #59
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-30T23:46:48+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from Vosvoy
>
> Xbox360 version users, GO THERE ( no virus ):

https://rapidshare.com/files/1987796284/BF3EBX.rar

Cordialy.

Interesting, how were you able to convert exb from bf3? can it be done for other 360 frostbite 2 games?
## Post #60
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-30T23:54:56+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> Vosvoy wrote:Xbox360 version users, GO THERE ( no virus ):

https://rapidshare.com/files/1987796284/BF3EBX.rar

Cordialy.

Interesting, how were you able to convert exb from bf3? can it be done for other 360 frostbite 2 games?

Just a test to see if Xbox360 users can handle .ebx BF3 PC files ( with .xma converter ).
## Post #61
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-05-01T00:11:00+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

shouldn't be too hard, match the ebx with the id. Although it would be cool to have a linker script as not to rename manually one by one but this will do for now. then we can add our own xma header. and convert.
## Post #62
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-05-01T00:17:39+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from OrangeC
>
> shouldn't be too hard, match the ebx with the id. Although it would be cool to have a linker script as not to rename manually one by one but this will do for now. then we can add our own xma header. and convert.

I don't know anything about .xma format. So, I can't help you for that...
## Post #63
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-05-01T01:46:18+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

OMG I'm so dumb....... The PC chunks are different from the console chunks. They don't match up. Why didn't I think of that.

As an example the AEK-71 long reload CHUNKID for BF3 X360 is 34ab8c16913d8e37e7c05f76457d83a4 for BF3 PC it is 191FBE10D72A6AE3333401D966E8CBAE

I'm so sorry I didn't look at it sooner.
## Post #64
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-05-01T05:23:10+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

That's unfortunate. All the more reason to implement console ebx conversion.
## Post #65
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-05-01T13:32:37+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Yeah, we need to find a solution for that. I'll investigate scrupulously the python script for my part. Otherwise, maybe the script creator could help us.

Anyway, we now know that .ebx files from PC are not compliant with Xbox360 version. It's a small step forward.
## Post #66
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-05-05T22:39:57+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Just wanted to give you guys a heads up and let you know Frankelstner updated his sb/toc dumper for MOH warfighter. 
[http://www.bfeditor.org/forums/index.ph ... opic=15731](http://www.bfeditor.org/forums/index.php?showtopic=15731)

No update yet on audio conversion though.
## Post #67
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-05-07T15:58:30+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

We've got some useful details from the script creator:

> From Frankelstner:
>
> 
>
> The dll does exactly one thing: It converts a encoded block of 76 bytes into a decoded block of 128 floats. So the dll already does everything audio specific already. The task of the Python script is to feed the right bytes to the dll and eventually create a wav file from the floats it receives. It's not about audio at anymore, the problem is to have the script ensure that the file in question is actually XAS encoded, and to jump to the right places while reading an encoded file. The jumping part is already taken care of. And ensuring the file is actually XAS is just looking at the file with the strange length error and comparing it with other files that work correctly. Somewhere in the beginning there must be a byte different to tell the engine how to decode the format.
## Post #68
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-05-07T21:28:29+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

hmm strange it seems that the console chunks are weird when trying to match them up. Whats the difference here?

had to find the file by using the size because the chunk ID is not mall the same except the last numbers.

```
000008d0        $::SoundDataAsset
000008d0            $::Asset
000008d0                $::DataContainer
000008d8                Name AO4_Assets/Sound/Music/02_Outskirts/Action/Mus_Loop_OS02_Action_MMG1_134_Multi
000008dc                BudgetCategory Bc_Unknown
000008e0            NameHash 2538223577
000008e4            Chunks::array
00000944                member(0)::SoundDataChunk
00000944                    ChunkId B17600B855D3AC5D4D9090FF8B2B17BE
00000954                    ChunkSize 2083084
000008e8        Variations::array

Now the actual file is:b80076b1d3555dac4d9090ff8b2b17be.chunk
```


Some numbers are similiar but others not.
## Post #69
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-05-08T23:06:31+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Hey mates! Some news here:

> From Frankelstner:
>
> 
>
> Alright, here's a version that can deal with mohw (and hopefully big-endian files too, though I haven't tested that). For some reason the codec sometimes uses very strange values for the number of channels. E.g. the byte usually is 00 for 1 channel and 04 for 2 channels. However, some files use 01 and 05. I have played around with one sample file of each type, and think that 01 is 1 channel too and 05 is 2 channels. However, there's a chance some files are messed up, so give feedback if you find garbled audio.
>
> Code: Select all#needs python 2.7
>
> import string
>
> import sys
>
> from binascii import hexlify
>
> from struct import unpack,pack
>
> import os
>
> from cStringIO import StringIO
>
> import cProfile
>
> import cPickle
>
> 
>
> ebxFolder=   r"D:\hexing\mohw dump\bundles\ebx" #audio is found in several places
>
> chunkFolder= r"D:\hexing\mohw dump\chunks" #grab audio from here
>
> chunkFolder2=r"D:\hexing\mohw dump\bundles\chunks" #if the chunk is not found in the first folder, use this one
>
> outputFolder=r"D:\decoded mohw123123"
>
> 
>
> 
>
> #Run through the sound ebx files, find fields with chunk Guids and fieldName = ChunkId.
>
> #The script will overwrite existing files.
>
> 
>
> #The filename of the ebx file importing an audio chunk becomes the name of the wav file.
>
> #As for the indices, there are three of them in the following order.
>
> #1: Variation.ChunkIndex: Some ebx files import several completely independent audio chunk files. This index differentiates between them. 
>
> #2: Variation.Index: An ebx may use the same audio chunk for several sound variations, this index keeps them apart.
>
> #3: Segment.Index: A variation may contain several segments, so there is another index.
>
> 
>
> 
>
> ##############################################################
>
> ##############################################################
>
> def unpackBE(typ,data): return unpack(">"+typ,data)
>
> 
>
> def open2(path,mode="rb"):
>
>     if mode=="wb":
>
>         #create folders if necessary and return the file handle
>
>         #first of all, create one folder level manully because makedirs might fail
>
>         path=os.path.normpath(path)
>
>         pathParts=path.split("\\")
>
>         manualPart="\\".join(pathParts[:2])
>
>         if not os.path.isdir(manualPart): os.makedirs(manualPart)
>
> 
>
>         #now handle the rest, including extra long path names
>
>         folderPath=lp(os.path.dirname(path))
>
>         if not os.path.isdir(folderPath): os.makedirs(folderPath)
>
>     return open(lp(path),mode)
>
> 
>
> def lp(path): #long pathnames
>
>     if len(path)<=247 or path=="" or path[:4]=='\\\\?\\': return path
>
>     return unicode('\\\\?\\' + os.path.normpath(path))
>
> 
>
> def decodeAudio():
>
>     for dir0, dirs, ff in os.walk(ebxFolder):
>
>         for fname in ff:
>
>             f=open2(dir0+"\\"+fname)
>
>             magic=f.read(4)
>
>             if magic=="\xCE\xD1\xB2\x0F":
>
>                 dbx=Dbx(f,unpack)
>
>             elif magic=="\x0F\xB2\xD1\xCE":
>
>                 dbx=Dbx(f,unpackBE)
>
>             else:
>
>                 f.close()
>
>                 continue
>
>             dbx.decode()
>
>             
>
> try:
>
>     from ctypes import *
>
>     floatlib = cdll.LoadLibrary("floattostring")
>
>     def formatfloat(num):
>
>         bufType = c_char * 100
>
>         buf = bufType()
>
>         bufpointer = pointer(buf)
>
>         floatlib.convertNum(c_double(num), bufpointer, 100)
>
>         rawstring=(buf.raw)[:buf.raw.find("\x00")]
>
>         if rawstring[:2]=="-.": return "-0."+rawstring[2:]
>
>         elif rawstring[0]==".": return "0."+rawstring[1:]
>
>         elif "e" not in rawstring and "." not in rawstring: return rawstring+".0"
>
>         return rawstring
>
> except:
>
>     def formatfloat(num):
>
>         return str(num)
>
> def hasher(keyword): #32bit FNV-1 hash with FNV_offset_basis = 5381 and FNV_prime = 33
>
>     hash = 5381
>
>     for byte in keyword:
>
>         hash = (hash*33) ^ ord(byte)
>
>     return hash & 0xffffffff # use & because Python promotes the num instead of intended overflow
>
> class Header:
>
>     def __init__(self,varList): ##all 4byte unsigned integers
>
>         self.absStringOffset     = varList[0]  ## absolute offset for string section start
>
>         self.lenStringToEOF      = varList[1]  ## length from string section start to EOF
>
>         self.numGUID             = varList[2]  ## number of external GUIDs
>
>         self.null                = varList[3]  ## 00000000
>
>         self.numInstanceRepeater = varList[4]
>
>         self.numComplex          = varList[5]  ## number of complex entries
>
>         self.numField            = varList[6]  ## number of field entries
>
>         self.lenName             = varList[7]  ## length of name section including padding
>
>         self.lenString           = varList[8]  ## length of string section including padding
>
>         self.numArrayRepeater    = varList[9]
>
>         self.lenPayload          = varList[10] ## length of normal payload section; the start of the array payload section is absStringOffset+lenString+lenPayload
>
> class FieldDescriptor:
>
>     def __init__(self,varList,keywordDict):
>
>         self.name            = keywordDict[varList[0]]
>
>         self.type            = varList[1]
>
>         self.ref             = varList[2] #the field may contain another complex
>
>         self.offset          = varList[3] #offset in payload section; relative to the complex containing it
>
>         self.secondaryOffset = varList[4]
>
> class ComplexDescriptor:
>
>     def __init__(self,varList,keywordDict):
>
>         self.name            = keywordDict[varList[0]]
>
>         self.fieldStartIndex = varList[1] #the index of the first field belonging to the complex
>
>         self.numField        = varList[2] #the total number of fields belonging to the complex
>
>         self.alignment       = varList[3]
>
>         self.type            = varList[4]
>
>         self.size            = varList[5] #total length of the complex in the payload section
>
>         self.secondarySize   = varList[6] #seems deprecated
>
> class InstanceRepeater:
>
>     def __init__(self,varList):
>
>         self.null            = varList[0] #called "internalCount", seems to be always null
>
>         self.repetitions     = varList[1] #number of instance repetitions
>
>         self.complexIndex    = varList[2] #index of complex used as the instance
>
> class arrayRepeater:
>
>     def __init__(self,varList):
>
>         self.offset          = varList[0] #offset in array payload section
>
>         self.repetitions     = varList[1] #number of array repetitions
>
>         self.complexIndex    = varList[2] #not necessary for extraction
>
> class Complex:
>
>     def __init__(self,desc,dbxhandle):
>
>         self.desc=desc
>
>         self.dbx=dbxhandle #lazy
>
>     def get(self,name):
>
>         pathElems=name.split("/")
>
>         curPos=self
>
>         if pathElems[-1].find("::")!=-1: #grab a complex
>
>             for elem in pathElems:
>
>                 try:
>
>                     curPos=curPos.go1(elem)
>
>                 except Exception,e:
>
>                     raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
>
>             return curPos
>
>         #grab a field instead
>
>         for elem in pathElems[:-1]:
>
>             try:
>
>                 curPos=curPos.go1(elem)
>
>             except Exception,e:
>
>                 raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
>
>         for field in curPos.fields:
>
>             if field.desc.name==pathElems[-1]:
>
>                 return field
>
>             
>
>         raise Exception("Could not find field with name: "+name+"\nFilename: "+self.dbx.trueFilename)
>
> 
>
>     def go1(self,name): #go once
>
>         for field in self.fields:
>
>             if field.desc.type in (0x0029, 0xd029,0x0000,0x0041):
>
>                 if field.desc.name+"::"+field.value.desc.name == name:
>
>                     return field.value
>
>         raise Exception(name)
>
> 
>
> 
>
> class Field:
>
>     def __init__(self,desc,dbx):
>
>         self.desc=desc
>
>         self.dbx=dbx
>
>     def link(self):
>
>         if self.desc.type!=0x0035: raise Exception("Invalid link, wrong field type\nField name: "+self.desc.name+"\nField type: "+hex(self.desc.type)+"\nFile name: "+self.dbx.trueFilename)
>
>         
>
>         if self.value>>31:
>
>             extguid=self.dbx.externalGUIDs[self.value&0x7fffffff]
>
>             
>
>             for existingDbx in dbxArray:
>
>                 if existingDbx.fileGUID==extguid[0]:
>
>                     for guid, instance in existingDbx.instances:
>
>                         if guid==extguid[1]:
>
>                             return instance
>
>                     
>
> 
>
>             f=valid(inputFolder+guidTable[extguid[0]]+".ebx")
>
> ##            print guidTable[extguid[0]]
>
>             dbx=Dbx(f)
>
>             dbxArray.append(dbx)
>
>             for guid, instance in dbx.instances:
>
>                 if guid==extguid[1]:
>
>                     return instance
>
>             raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
>
>         elif self.value!=0:
>
>             for guid, instance in self.dbx.instances:
>
>                 if guid==self.dbx.internalGUIDs[self.value-1]:
>
>                     return instance
>
>         else:
>
>             raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
>
> 
>
>         raise Exception("Invalid link, could not find target.")
>
> 
>
>     def getlinkguid(self):
>
>         if self.desc.type!=0x0035: raise Exception("Invalid link, wrong field type\nField name: "+self.desc.name+"\nField type: "+hex(self.desc.type)+"\nFile name: "+self.dbx.trueFilename)
>
> 
>
>         if self.value>>31:
>
>             return "".join(self.dbx.externalGUIDs[self.value&0x7fffffff])
>
>         elif self.value!=0:
>
>             return self.dbx.fileGUID+self.dbx.internalGUIDs[self.value-1]
>
>         else:
>
>             raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
>
>     def getlinkname(self):
>
>         if self.desc.type!=0x0035: raise Exception("Invalid link, wrong field type\nField name: "+self.desc.name+"\nField type: "+hex(self.desc.type)+"\nFile name: "+self.dbx.trueFilename)
>
> 
>
>         if self.value>>31:
>
>             return guidTable[self.dbx.externalGUIDs[self.value&0x7fffffff][0]]+"/"+self.dbx.externalGUIDs[self.value&0x7fffffff][1]
>
>         elif self.value!=0:
>
>             return self.dbx.trueFilename+"/"+self.dbx.internalGUIDs[self.value-1]
>
>         else:
>
>             raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
>
>     
>
> 
>
>          
>
> def valid(fname):
>
>     f=open2(fname,"rb")
>
>     if f.read(4) not in ("\xCE\xD1\xB2\x0F","\x0F\xB2\xD1\xCE"):
>
>         f.close()
>
>         raise Exception("nope")
>
>     return f
>
> 
>
> class nullguid(Exception):
>
>     def __init__(self, value):
>
>         self.value = value
>
>     def __str__(self):
>
>         return repr(self.value)
>
> 
>
> 
>
> numDict={0x0035:("I",4),0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("B",1),0xc0ed:("h",2), 0xc0dd:("H",2), 0xc13d:("f",4)}
>
> 
>
> 
>
> class Stub:
>
>     pass
>
> 
>
> 
>
> 
>
> class Dbx:
>
>     def __init__(self, f,unpacker):
>
>         self.unpack=unpacker
>
>         self.trueFilename=""
>
>         self.header=Header(self.unpack("11I",f.read(44)))
>
>         self.arraySectionstart=self.header.absStringOffset+self.header.lenString+self.header.lenPayload
>
>         self.fileGUID, self.primaryInstanceGUID = f.read(16), f.read(16)    
>
>         self.externalGUIDs=[(f.read(16),f.read(16)) for i in xrange(self.header.numGUID)]
>
>         self.keywords=str.split(f.read(self.header.lenName),"\x00")
>
>         self.keywordDict=dict((hasher(keyword),keyword) for keyword in self.keywords)
>
>         self.fieldDescriptors=[FieldDescriptor(self.unpack("IHHII",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
>
>         self.complexDescriptors=[ComplexDescriptor(self.unpack("IIBBHHH",f.read(16)), self.keywordDict) for i in xrange(self.header.numComplex)]
>
>         self.instanceRepeaters=[InstanceRepeater(self.unpack("3I",f.read(12))) for i in xrange(self.header.numInstanceRepeater)] 
>
>         while f.tell()%16!=0: f.seek(1,1) #padding
>
>         self.arrayRepeaters=[arrayRepeater(self.unpack("3I",f.read(12))) for i in xrange(self.header.numArrayRepeater)]
>
> 
>
>         #payload
>
>         f.seek(self.header.absStringOffset+self.header.lenString)
>
>         self.internalGUIDs=[]
>
>         self.instances=[] # (guid, complex)
>
>         for instanceRepeater in self.instanceRepeaters:
>
>             for repetition in xrange(instanceRepeater.repetitions):
>
>                 instanceGUID=f.read(16)
>
>                 self.internalGUIDs.append(instanceGUID)
>
>                 if instanceGUID==self.primaryInstanceGUID:
>
>                     self.isPrimaryInstance=True
>
>                 else:
>
>                     self.isPrimaryInstance=False
>
>                 inst=self.readComplex(instanceRepeater.complexIndex,f)
>
>                 inst.guid=instanceGUID
>
>                 
>
>                 if self.isPrimaryInstance: self.prim=inst
>
>                 self.instances.append((instanceGUID,inst))
>
>     
>
>         f.close()
>
>         
>
> 
>
>     def readComplex(self, complexIndex,f):
>
>         complexDesc=self.complexDescriptors[complexIndex]
>
>         cmplx=Complex(complexDesc,self)
>
>         
>
>         startPos=f.tell()                 
>
>         cmplx.fields=[]
>
>         for fieldIndex in xrange(complexDesc.fieldStartIndex,complexDesc.fieldStartIndex+complexDesc.numField):
>
>             f.seek(startPos+self.fieldDescriptors[fieldIndex].offset)
>
>             cmplx.fields.append(self.readField(fieldIndex,f))
>
>         
>
>         f.seek(startPos+complexDesc.size)
>
>         return cmplx
>
> 
>
> 
>
>     def readField(self,fieldIndex,f):
>
>         fieldDesc = self.fieldDescriptors[fieldIndex]
>
>         field=Field(fieldDesc,self)
>
>         
>
>         if fieldDesc.type in (0x0029, 0xd029,0x0000):
>
>             field.value=self.readComplex(fieldDesc.ref,f)
>
>         elif fieldDesc.type==0x0041:
>
>             arrayRepeater=self.arrayRepeaters[self.unpack("I",f.read(4))[0]]
>
>             arrayComplexDesc=self.complexDescriptors[fieldDesc.ref]
>
> 
>
> ##            if arrayRepeater.repetitions==0: field.value = "*nullArray*"
>
>             f.seek(self.arraySectionstart+arrayRepeater.offset)
>
>             arrayComplex=Complex(arrayComplexDesc,self)
>
>             arrayComplex.fields=[self.readField(arrayComplexDesc.fieldStartIndex,f) for repetition in xrange(arrayRepeater.repetitions)]
>
>             field.value=arrayComplex
>
>             
>
>         elif fieldDesc.type in (0x407d, 0x409d):
>
>             startPos=f.tell()
>
>             f.seek(self.header.absStringOffset+self.unpack("I",f.read(4))[0])
>
>             string=""
>
>             while 1:
>
>                 a=f.read(1)
>
>                 if a=="\x00": break
>
>                 else: string+=a
>
>             f.seek(startPos+4)
>
>             
>
>             if len(string)==0: field.value="*nullString*" #actually the string is ""
>
>             else: field.value=string
>
>             
>
>             if self.isPrimaryInstance and self.trueFilename=="" and fieldDesc.name=="Name": self.trueFilename=string
>
>             
>
>                    
>
>         elif fieldDesc.type==0x0089: #incomplete implementation, only gives back the selected string
>
>             compareValue=self.unpack("I",f.read(4))[0] 
>
>             enumComplex=self.complexDescriptors[fieldDesc.ref]
>
> 
>
>             if enumComplex.numField==0:
>
>                 field.value="*nullEnum*"
>
>             for fieldIndex in xrange(enumComplex.fieldStartIndex,enumComplex.fieldStartIndex+enumComplex.numField):
>
>                 if self.fieldDescriptors[fieldIndex].offset==compareValue:
>
>                     field.value=self.fieldDescriptors[fieldIndex].name
>
>                     break
>
>         elif fieldDesc.type==0xc15d:
>
>             field.value=f.read(16)
>
>         elif fieldDesc.type == 0xc13d: ################################
>
>             field.value=formatfloat(self.unpack("f",f.read(4))[0])
>
>         else:
>
>             (typ,length)=numDict[fieldDesc.type]
>
>             num=self.unpack(typ,f.read(length))[0]
>
>             field.value=num
>
>         
>
>         return field
>
>         
>
> 
>
>     def dump(self,outputFolder):
>
>         dirName=os.path.dirname(outputFolder+self.trueFilename)
>
>         if not os.path.isdir(dirName): os.makedirs(dirName)
>
>         f2=open2(outputFolder+self.trueFilename+EXTENSION,"wb")
>
>         print self.trueFilename
>
>         
>
>         for (guid,instance) in self.instances:
>
>             if guid==self.primaryInstanceGUID: f2.write(instance.desc.name+" "+hexlify(guid)+ " #primary instance\r\n")
>
>             else: f2.write(instance.desc.name+" "+hexlify(guid)+ "\r\n")
>
>             self.recurse(instance.fields,f2,0)
>
>         f2.close()
>
> 
>
>     def recurse(self, fields,f2, lvl): #over fields
>
>         lvl+=1
>
>         for field in fields:
>
>             if field.desc.type in (0xc14d, 0xc0fd, 0xc10d, 0xc0ed, 0xc0dd, 0xc0bd, 0xc0ad, 0x407d, 0x409d, 0x0089):
>
>                 f2.write(lvl*SEP+field.desc.name+" "+str(field.value)+"\r\n")
>
>             elif field.desc.type == 0xc13d:
>
>                 f2.write(lvl*SEP+field.desc.name+" "+formatfloat(field.value)+"\r\n")
>
>             elif field.desc.type == 0xc15d:
>
>                 f2.write(lvl*SEP+field.desc.name+" "+hexlify(field.value)+"\r\n")
>
>             elif field.desc.type == 0x0035:
>
>                 towrite=""
>
>                 if field.value>>31:
>
>                     extguid=self.externalGUIDs[field.value&0x7fffffff]
>
>                     try: towrite=guidTable[extguid[0]]+"/"+hexlify(extguid[1])
>
>                     except: towrite=hexlify(extguid[0])+"/"+hexlify(extguid[1])
>
>                 elif field.value==0: towrite="*nullGuid*"
>
>                 else: towrite=hexlify(self.internalGUIDs[field.value-1])
>
>                 f2.write(lvl*SEP+field.desc.name+" "+towrite+"\r\n") 
>
>             elif field.desc.type==0x0041 and len(field.value.fields)==0:
>
>                 f2.write(lvl*SEP+field.desc.name+" "+"*nullArray*"+"\r\n")
>
>             else:
>
>                 f2.write(lvl*SEP+field.desc.name+"::"+field.value.desc.name+"\r\n")
>
>                 self.recurse(field.value.fields,f2,lvl)
>
> 
>
> 
>
>     def decode(self):
>
>         if not self.prim.desc.name=="SoundWaveAsset": return
>
> 
>
>         histogram=dict() #count the number of times each chunk is used by a variation to obtain the right index
>
> 
>
>         Chunks=[]
>
>         for i in self.prim.get("$::SoundDataAsset/Chunks::array").fields:
>
>             chnk=Stub()
>
>             Chunks.append(chnk)
>
>             chnk.ChunkId=i.value.get("ChunkId").value
>
>             chnk.ChunkSize=i.value.get("ChunkSize").value
>
> 
>
>             
>
>         variations=[i.link() for i in self.prim.get("Variations::array").fields]
>
> 
>
>         Variations=[]
>
>         
>
>         for var in variations:
>
>             Variation=Stub()
>
>             Variations.append(Variation)
>
>             Variation.ChunkIndex=var.get("ChunkIndex").value
>
>             Variation.SeekTablesSize=var.get("SeekTablesSize").value
>
>             Variation.FirstLoopSegmentIndex=var.get("FirstLoopSegmentIndex").value
>
>             Variation.LastLoopSegmentIndex=var.get("LastLoopSegmentIndex").value
>
> 
>
> 
>
>             Variation.Segments=[]
>
>             segs=var.get("Segments::array").fields
>
>             for seg in segs:
>
>                 Segment=Stub()
>
>                 Variation.Segments.append(Segment)
>
>                 Segment.SamplesOffset = seg.value.get("SamplesOffset").value
>
>                 Segment.SeekTableOffset = seg.value.get("SeekTableOffset").value
>
>                 Segment.SegmentLength = seg.value.get("SegmentLength").value
>
> 
>
>             Variation.ChunkId=hexlify(Chunks[Variation.ChunkIndex].ChunkId)
>
>             Variation.ChunkSize=Chunks[Variation.ChunkIndex].ChunkSize
>
>         
>
> 
>
>             #find the appropriate index
>
>             if Variation.ChunkIndex in histogram: #has been used previously already
>
>                 Variation.Index=histogram[Variation.ChunkIndex]
>
>                 histogram[Variation.ChunkIndex]+=1
>
>             else:
>
>                 Variation.Index=0
>
>                 histogram[Variation.ChunkIndex]=1
>
> 
>
>                 
>
>         #everything is laid out neatly now
>
>         #ChunkId, ChunkSize, Index, ChunkIndex, SeekTablesSize, FirstLoopSegmentIndex, LastLoopSegmentIndex
>
>         #Segments with SamplesOffset, SeekTableOffset, SegmentLength
>
> 
>
>         ChunkHandles=dict() #should speed things up
>
> 
>
>         for Variation in Variations:
>
>             try:
>
>                 f=ChunkHandles[Variation.ChunkId]
>
>             except:
>
>                 try:
>
>                     f=open2(chunkFolder+Variation.ChunkId+".chunk")
>
>                 except IOError:
>
>                     try:
>
>                         f=open2(chunkFolder2+Variation.ChunkId+".chunk")
>
>                     except:
>
>                         print "Chunk does not exist: "+Variation.ChunkId+" "+self.trueFilename
>
>                         return
>
>                 ChunkHandles[Variation.ChunkId]=f
>
> 
>
> 
>
>             for ijk in xrange(len(Variation.Segments)):
>
>                 Segment=Variation.Segments[ijk]
>
>                 f.seek(Segment.SamplesOffset)
>
>                 magic=f.read(4)
>
>                 
>
>                 if magic!="\x48\x00\x00\x0c":
>
>                     raise Exception("Wrong XAS magic.")
>
> 
>
>                 audioType=f.read(1) #0x14 is DICE XAS
>
>                 if audioType!="\x14":
>
>                     print "Non XAS audio segment (type "+hexlify(audioType)+"): "+Variation.ChunkId+" "+self.trueFilename
>
>                     continue
>
>                 channelRaw=f.read(1)
>
>                 if channelRaw not in channelDict:
>
>                     print self.trueFilename
>
>                 
>
>                     
>
>                 numChannels=channelDict[channelRaw]
>
>                 samplingRate=unpack(">H",f.read(2))[0] #[48000, 11025, 16000, 44100, 24000]
>
>                 f.read(4) #the first byte is always 0x40, the second takes one of 82 values, third and fourth can each take any value (i.e. 00 to ff)
>
>                 #82 values: ['\x01', '\x00', '\x03', '\x02', '\x05', '\x04', '\x07', '\x06', '\t', '\x08', '\x0b', '\n', '\r', '\x0c', '\x0f', '\x0e', '\x11', '\x10', '\x13', '\x12', '\x15', '\x14', '\x17', '\x16', '\x19', '\x18', '\x1b', '\x1a', '\x1d', '\x1c', '\x9f', '\x1e', '!', ' ', '#', '"', '%', '$', "'", '&', ')', '(', '+', '*', '-', ',', '/', '.', '1', '0', '3', '2', '5', '\x1f', '7', '6', '9', ';', '<', '?', '>', '\xc1', 'a', 'C', 'E', 'D', '\xa0', 'I', 'H', 'K', 'J', 'L', 'Y', 'X', '\x8e', '\x87', '4', 'A', 'd', 'F', '\x95', '\x7f']
>
>                 
>
>                 payload=""
>
>                 target= os.path.join(outputFolder,self.trueFilename)+" "+str(Variation.ChunkIndex)+" "+str(Variation.Index)+" "+str(ijk)+".wav"
>
>                 targetFolder=os.path.dirname(target)
>
>                 if not os.path.isdir(targetFolder): os.makedirs(targetFolder)
>
> 
>
>                 f2=StringIO()
>
>                 
>
>                 write_header(f2, samplingRate, numChannels)
>
>                 
>
>                 while 1:
>
>                     v1,length=unpack(">HH",f.read(4))
>
> 
>
>                     if length<=4: break
>
>                     length-=8
>
>                     
>
>                     v2,v3=unpack(">HH",f.read(4))
>
> 
>
>                     if length%76!=0:
>
>                         raise Exception("Strange length: "+str(length))
>
>                         
>
>                     atoms=length/76
>
> 
>
>                     blocks=[None]*numChannels
>
>                     
>
>                     for atom in xrange(0,atoms,numChannels):
>
>                         for i in xrange(numChannels):
>
>                             blocks[i]=decode(f.read(76))
>
>                             
>
>                         atomData=""
>
>                         for i in xrange(128):
>
>                             for j in xrange(numChannels):
>
>                                 atomData+=pack("f",blocks[j][i])
>
>                
>
>                         f2.write(atomData)
>
> 
>
>                 finalPos=f2.tell()
>
>                 f2.seek(4)    
>
>                 f2.write(pack("I",finalPos-8))
>
>                 f2.seek(76)
>
>                 f2.write(pack("I",finalPos-76))
>
> 
>
>                 f3=open2(target,"wb")
>
>                 f3.write(f2.getvalue())
>
>                 
>
>                 f2.close()
>
> 
>
>         for key in ChunkHandles:
>
>             ChunkHandles[key].close()
>
> 
>
> 
>
> 
>
> def write_header(fp, samplingRate, nchannels):
>
>     out = pack('4sl4s','RIFF',0,'WAVE')
>
>     floatSize = 4
>
>     fmt_size = 40
>
>     tag = 0xFFFE
>
>     etag = 3
>
> 
>
>     out += pack('4slHHllHH', 'fmt ', fmt_size, tag, nchannels, samplingRate,
>
>                 nchannels * samplingRate * floatSize, nchannels * floatSize, floatSize * 8)
>
> 
>
>     out += pack('HHlH14s', 22, floatSize * 8, (1 << nchannels) - 1, etag,
>
>                 '\x00\x00\x00\x00\x10\x00\x80\x00\x00\xaa\x008\x9b\x71')
>
> 
>
>     out += pack("<4sll","fact",4,floatSize)
>
>     out += pack("4sl","data",0)
>
> 
>
>     fp.seek(0)
>
>     fp.write(out)
>
> 
>
>     
>
> xaslib = cdll.LoadLibrary("xas")
>
> def decode(inputChars):
>
>     charType = c_char * 76
>
>     charBuf = charType(*inputChars)
>
>     charbufpointer = pointer(charBuf)
>
>     
>
>     floatType = c_float * 128
>
>     floatBuf = floatType()
>
>     floatbufpointer = pointer(floatBuf)
>
>     
>
>     xaslib.decode(charbufpointer, floatbufpointer)
>
>     
>
>     return floatBuf
>
> 
>
> 
>
> channelDict={"\x00":1,"\x04":2,"\x0c":4,"\x14":6,"\x1c":8,"\x05":2,"\x01":1}
>
> 
>
> 
>
> if outputFolder[-1] not in ("/","\\"): outputFolder+="/"
>
> if ebxFolder[-1] not in ("/","\\"): ebxFolder+="/"
>
> if chunkFolder[-1] not in ("/","\\"): chunkFolder+="/"
>
> if chunkFolder2[-1] not in ("/","\\"): chunkFolder2+="/"
>
> 
>
> 
>
>     
>
> decodeAudio()
Remember one thing guys: The script only  works on BF3 PC version ( 100% ) and MOHW PC version ( 90% > Have to use Zench EALayer3 tool for some sounds ), for the moment. There's some troubles with console version as durandal217 and OrangeC said.
## Post #70
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-05-09T06:17:00+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

To Convert the non-xas use the ealayer3 tool from zench.
## Post #71
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-05-09T19:25:53+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Frankelstner has updated the XAS script again to properly handle EALayer3 files for MOHW. Music now properly extracts.

```
import string
import sys
from binascii import hexlify
from struct import unpack,pack
import os
from cStringIO import StringIO
import cProfile
import cPickle
import subprocess



ebxFolder=   r"D:\hexing\mohw dump\bundles\ebx" #audio is found in several places
chunkFolder= r"D:\hexing\mohw dump\chunks" #grab audio from here
chunkFolder2=r"D:\hexing\mohw dump\bundles\chunks" #if the chunk is not found in the first folder, use this one
outputFolder=r"D:\decoded mohw123123123"
ealayer3Path=r"D:\ealayer3-0.7.0-win32\ealayer3.exe" #https://bitbucket.org/Zenchreal/ealayer3/downloads


#Run through the sound ebx files, find fields with chunk Guids and fieldName = ChunkId.
#The script will overwrite existing files.

#The filename of the ebx file importing an audio chunk becomes the name of the wav file.
#As for the indices, there are three of them in the following order.
#1: Variation.ChunkIndex: Some ebx files import several completely independent audio chunk files. This index differentiates between them. 
#2: Variation.Index: An ebx may use the same audio chunk for several sound variations, this index keeps them apart.
#3: Segment.Index: A variation may contain several segments, so there is another index.


##############################################################
##############################################################
def unpackBE(typ,data): return unpack(">"+typ,data)

def makeLongDirs(path):
    #create folders if necessary and return the file handle
    #first of all, create one folder level manully because makedirs might fail
    path=os.path.normpath(path)
    pathParts=path.split("\\")
    manualPart="\\".join(pathParts[:2])
    if not os.path.isdir(manualPart): os.makedirs(manualPart)
    
    #now handle the rest, including extra long path names
    folderPath=lp(os.path.dirname(path))
    if not os.path.isdir(folderPath): os.makedirs(folderPath)
    

def open2(path,mode="rb"):
    if mode=="wb": makeLongDirs(path)
    return open(lp(path),mode)

def lp(path): #long pathnames
    if len(path)<=247 or path=="" or path[:4]=='\\\\?\\': return path
    return unicode('\\\\?\\' + os.path.normpath(path))

def decodeAudio():
    for dir0, dirs, ff in os.walk(ebxFolder):
        for fname in ff:
            f=open2(dir0+"\\"+fname)
            magic=f.read(4)
            if magic=="\xCE\xD1\xB2\x0F":
                dbx=Dbx(f,unpack)
            elif magic=="\x0F\xB2\xD1\xCE":
                dbx=Dbx(f,unpackBE)
            else:
                f.close()
                continue
            dbx.decode()
            
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
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.type            = varList[1]
        self.ref             = varList[2] #the field may contain another complex
        self.offset          = varList[3] #offset in payload section; relative to the complex containing it
        self.secondaryOffset = varList[4]
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
        self.null            = varList[0] #called "internalCount", seems to be always null
        self.repetitions     = varList[1] #number of instance repetitions
        self.complexIndex    = varList[2] #index of complex used as the instance
class arrayRepeater:
    def __init__(self,varList):
        self.offset          = varList[0] #offset in array payload section
        self.repetitions     = varList[1] #number of array repetitions
        self.complexIndex    = varList[2] #not necessary for extraction
class Complex:
    def __init__(self,desc,dbxhandle):
        self.desc=desc
        self.dbx=dbxhandle #lazy
    def get(self,name):
        pathElems=name.split("/")
        curPos=self
        if pathElems[-1].find("::")!=-1: #grab a complex
            for elem in pathElems:
                try:
                    curPos=curPos.go1(elem)
                except Exception,e:
                    raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
            return curPos
        #grab a field instead
        for elem in pathElems[:-1]:
            try:
                curPos=curPos.go1(elem)
            except Exception,e:
                raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
        for field in curPos.fields:
            if field.desc.name==pathElems[-1]:
                return field
            
        raise Exception("Could not find field with name: "+name+"\nFilename: "+self.dbx.trueFilename)

    def go1(self,name): #go once
        for field in self.fields:
            if field.desc.type in (0x0029, 0xd029,0x0000,0x0041):
                if field.desc.name+"::"+field.value.desc.name == name:
                    return field.value
        raise Exception(name)


class Field:
    def __init__(self,desc,dbx):
        self.desc=desc
        self.dbx=dbx
    def link(self):
        if self.desc.type!=0x0035: raise Exception("Invalid link, wrong field type\nField name: "+self.desc.name+"\nField type: "+hex(self.desc.type)+"\nFile name: "+self.dbx.trueFilename)
        
        if self.value>>31:
            extguid=self.dbx.externalGUIDs[self.value&0x7fffffff]
            
            for existingDbx in dbxArray:
                if existingDbx.fileGUID==extguid[0]:
                    for guid, instance in existingDbx.instances:
                        if guid==extguid[1]:
                            return instance
                    

            f=valid(inputFolder+guidTable[extguid[0]]+".ebx")
##            print guidTable[extguid[0]]
            dbx=Dbx(f)
            dbxArray.append(dbx)
            for guid, instance in dbx.instances:
                if guid==extguid[1]:
                    return instance
            raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
        elif self.value!=0:
            for guid, instance in self.dbx.instances:
                if guid==self.dbx.internalGUIDs[self.value-1]:
                    return instance
        else:
            raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)

        raise Exception("Invalid link, could not find target.")

    def getlinkguid(self):
        if self.desc.type!=0x0035: raise Exception("Invalid link, wrong field type\nField name: "+self.desc.name+"\nField type: "+hex(self.desc.type)+"\nFile name: "+self.dbx.trueFilename)

        if self.value>>31:
            return "".join(self.dbx.externalGUIDs[self.value&0x7fffffff])
        elif self.value!=0:
            return self.dbx.fileGUID+self.dbx.internalGUIDs[self.value-1]
        else:
            raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
    def getlinkname(self):
        if self.desc.type!=0x0035: raise Exception("Invalid link, wrong field type\nField name: "+self.desc.name+"\nField type: "+hex(self.desc.type)+"\nFile name: "+self.dbx.trueFilename)

        if self.value>>31:
            return guidTable[self.dbx.externalGUIDs[self.value&0x7fffffff][0]]+"/"+self.dbx.externalGUIDs[self.value&0x7fffffff][1]
        elif self.value!=0:
            return self.dbx.trueFilename+"/"+self.dbx.internalGUIDs[self.value-1]
        else:
            raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
    

         
def valid(fname):
    f=open2(fname,"rb")
    if f.read(4) not in ("\xCE\xD1\xB2\x0F","\x0F\xB2\xD1\xCE"):
        f.close()
        raise Exception("nope")
    return f

class nullguid(Exception):
    def __init__(self, value):
        self.value = value
    def __str__(self):
        return repr(self.value)


numDict={0x0035:("I",4),0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("B",1),0xc0ed:("h",2), 0xc0dd:("H",2), 0xc13d:("f",4)}


class Stub:
    pass



class Dbx:
    def __init__(self, f,unpacker):
        self.unpack=unpacker
        self.trueFilename=""
        self.header=Header(self.unpack("11I",f.read(44)))
        self.arraySectionstart=self.header.absStringOffset+self.header.lenString+self.header.lenPayload
        self.fileGUID, self.primaryInstanceGUID = f.read(16), f.read(16)    
        self.externalGUIDs=[(f.read(16),f.read(16)) for i in xrange(self.header.numGUID)]
        self.keywords=str.split(f.read(self.header.lenName),"\x00")
        self.keywordDict=dict((hasher(keyword),keyword) for keyword in self.keywords)
        self.fieldDescriptors=[FieldDescriptor(self.unpack("IHHII",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
        self.complexDescriptors=[ComplexDescriptor(self.unpack("IIBBHHH",f.read(16)), self.keywordDict) for i in xrange(self.header.numComplex)]
        self.instanceRepeaters=[InstanceRepeater(self.unpack("3I",f.read(12))) for i in xrange(self.header.numInstanceRepeater)] 
        while f.tell()%16!=0: f.seek(1,1) #padding
        self.arrayRepeaters=[arrayRepeater(self.unpack("3I",f.read(12))) for i in xrange(self.header.numArrayRepeater)]

        #payload
        f.seek(self.header.absStringOffset+self.header.lenString)
        self.internalGUIDs=[]
        self.instances=[] # (guid, complex)
        for instanceRepeater in self.instanceRepeaters:
            for repetition in xrange(instanceRepeater.repetitions):
                instanceGUID=f.read(16)
                self.internalGUIDs.append(instanceGUID)
                if instanceGUID==self.primaryInstanceGUID:
                    self.isPrimaryInstance=True
                else:
                    self.isPrimaryInstance=False
                inst=self.readComplex(instanceRepeater.complexIndex,f)
                inst.guid=instanceGUID
                
                if self.isPrimaryInstance: self.prim=inst
                self.instances.append((instanceGUID,inst))
    
        f.close()
        

    def readComplex(self, complexIndex,f):
        complexDesc=self.complexDescriptors[complexIndex]
        cmplx=Complex(complexDesc,self)
        
        startPos=f.tell()                 
        cmplx.fields=[]
        for fieldIndex in xrange(complexDesc.fieldStartIndex,complexDesc.fieldStartIndex+complexDesc.numField):
            f.seek(startPos+self.fieldDescriptors[fieldIndex].offset)
            cmplx.fields.append(self.readField(fieldIndex,f))
        
        f.seek(startPos+complexDesc.size)
        return cmplx


    def readField(self,fieldIndex,f):
        fieldDesc = self.fieldDescriptors[fieldIndex]
        field=Field(fieldDesc,self)
        
        if fieldDesc.type in (0x0029, 0xd029,0x0000):
            field.value=self.readComplex(fieldDesc.ref,f)
        elif fieldDesc.type==0x0041:
            arrayRepeater=self.arrayRepeaters[self.unpack("I",f.read(4))[0]]
            arrayComplexDesc=self.complexDescriptors[fieldDesc.ref]

##            if arrayRepeater.repetitions==0: field.value = "*nullArray*"
            f.seek(self.arraySectionstart+arrayRepeater.offset)
            arrayComplex=Complex(arrayComplexDesc,self)
            arrayComplex.fields=[self.readField(arrayComplexDesc.fieldStartIndex,f) for repetition in xrange(arrayRepeater.repetitions)]
            field.value=arrayComplex
            
        elif fieldDesc.type in (0x407d, 0x409d):
            startPos=f.tell()
            f.seek(self.header.absStringOffset+self.unpack("I",f.read(4))[0])
            string=""
            while 1:
                a=f.read(1)
                if a=="\x00": break
                else: string+=a
            f.seek(startPos+4)
            
            if len(string)==0: field.value="*nullString*" #actually the string is ""
            else: field.value=string
            
            if self.isPrimaryInstance and self.trueFilename=="" and fieldDesc.name=="Name": self.trueFilename=string
            
                   
        elif fieldDesc.type==0x0089: #incomplete implementation, only gives back the selected string
            compareValue=self.unpack("I",f.read(4))[0] 
            enumComplex=self.complexDescriptors[fieldDesc.ref]

            if enumComplex.numField==0:
                field.value="*nullEnum*"
            for fieldIndex in xrange(enumComplex.fieldStartIndex,enumComplex.fieldStartIndex+enumComplex.numField):
                if self.fieldDescriptors[fieldIndex].offset==compareValue:
                    field.value=self.fieldDescriptors[fieldIndex].name
                    break
        elif fieldDesc.type==0xc15d:
            field.value=f.read(16)
        elif fieldDesc.type == 0xc13d: ################################
            field.value=formatfloat(self.unpack("f",f.read(4))[0])
        else:
            (typ,length)=numDict[fieldDesc.type]
            num=self.unpack(typ,f.read(length))[0]
            field.value=num
        
        return field
        

    def dump(self,outputFolder):
        dirName=os.path.dirname(outputFolder+self.trueFilename)
        if not os.path.isdir(dirName): os.makedirs(dirName)
        f2=open2(outputFolder+self.trueFilename+EXTENSION,"wb")
        print self.trueFilename
        
        for (guid,instance) in self.instances:
            if guid==self.primaryInstanceGUID: f2.write(instance.desc.name+" "+hexlify(guid)+ " #primary instance\r\n")
            else: f2.write(instance.desc.name+" "+hexlify(guid)+ "\r\n")
            self.recurse(instance.fields,f2,0)
        f2.close()

    def recurse(self, fields,f2, lvl): #over fields
        lvl+=1
        for field in fields:
            if field.desc.type in (0xc14d, 0xc0fd, 0xc10d, 0xc0ed, 0xc0dd, 0xc0bd, 0xc0ad, 0x407d, 0x409d, 0x0089):
                f2.write(lvl*SEP+field.desc.name+" "+str(field.value)+"\r\n")
            elif field.desc.type == 0xc13d:
                f2.write(lvl*SEP+field.desc.name+" "+formatfloat(field.value)+"\r\n")
            elif field.desc.type == 0xc15d:
                f2.write(lvl*SEP+field.desc.name+" "+hexlify(field.value)+"\r\n")
            elif field.desc.type == 0x0035:
                towrite=""
                if field.value>>31:
                    extguid=self.externalGUIDs[field.value&0x7fffffff]
                    try: towrite=guidTable[extguid[0]]+"/"+hexlify(extguid[1])
                    except: towrite=hexlify(extguid[0])+"/"+hexlify(extguid[1])
                elif field.value==0: towrite="*nullGuid*"
                else: towrite=hexlify(self.internalGUIDs[field.value-1])
                f2.write(lvl*SEP+field.desc.name+" "+towrite+"\r\n") 
            elif field.desc.type==0x0041 and len(field.value.fields)==0:
                f2.write(lvl*SEP+field.desc.name+" "+"*nullArray*"+"\r\n")
            else:
                f2.write(lvl*SEP+field.desc.name+"::"+field.value.desc.name+"\r\n")
                self.recurse(field.value.fields,f2,lvl)


    def decode(self):
        if not self.prim.desc.name=="SoundWaveAsset": return

        histogram=dict() #count the number of times each chunk is used by a variation to obtain the right index

        Chunks=[]
        for i in self.prim.get("$::SoundDataAsset/Chunks::array").fields:
            chnk=Stub()
            Chunks.append(chnk)
            chnk.ChunkId=i.value.get("ChunkId").value
            chnk.ChunkSize=i.value.get("ChunkSize").value

            
        variations=[i.link() for i in self.prim.get("Variations::array").fields]

        Variations=[]
        
        for var in variations:
            Variation=Stub()
            Variations.append(Variation)
            Variation.ChunkIndex=var.get("ChunkIndex").value
            Variation.SeekTablesSize=var.get("SeekTablesSize").value
            Variation.FirstLoopSegmentIndex=var.get("FirstLoopSegmentIndex").value
            Variation.LastLoopSegmentIndex=var.get("LastLoopSegmentIndex").value


            Variation.Segments=[]
            segs=var.get("Segments::array").fields
            for seg in segs:
                Segment=Stub()
                Variation.Segments.append(Segment)
                Segment.SamplesOffset = seg.value.get("SamplesOffset").value
                Segment.SeekTableOffset = seg.value.get("SeekTableOffset").value
                Segment.SegmentLength = seg.value.get("SegmentLength").value

            Variation.ChunkId=hexlify(Chunks[Variation.ChunkIndex].ChunkId)
            Variation.ChunkSize=Chunks[Variation.ChunkIndex].ChunkSize
        

            #find the appropriate index
            if Variation.ChunkIndex in histogram: #has been used previously already
                Variation.Index=histogram[Variation.ChunkIndex]
                histogram[Variation.ChunkIndex]+=1
            else:
                Variation.Index=0
                histogram[Variation.ChunkIndex]=1

                
        #everything is laid out neatly now
        #ChunkId, ChunkSize, Index, ChunkIndex, SeekTablesSize, FirstLoopSegmentIndex, LastLoopSegmentIndex
        #Segments with SamplesOffset, SeekTableOffset, SegmentLength

        ChunkHandles=dict() #for each ebx, keep track of all file handles

        for Variation in Variations:
            try:
                f=ChunkHandles[Variation.ChunkId]
            except:
                try:
                    f=open2(chunkFolder+Variation.ChunkId+".chunk")
                    currentChunkName=chunkFolder+Variation.ChunkId+".chunk"
                except IOError:
                    try:
                        f=open2(chunkFolder2+Variation.ChunkId+".chunk")
                        currentChunkName=chunkFolder2+Variation.ChunkId+".chunk"
                    except:
                        print "Chunk does not exist: "+Variation.ChunkId+" "+self.trueFilename
                        return
                ChunkHandles[Variation.ChunkId]=f


            for ijk in xrange(len(Variation.Segments)):
                Segment=Variation.Segments[ijk]
                f.seek(Segment.SamplesOffset)
                magic=f.read(4)
                
                if magic!="\x48\x00\x00\x0c":
                    raise Exception("Wrong XAS magic.")

                audioType=f.read(1) #0x14 is DICE XAS, 0x16 is ealayer3, 0x12 is unknown
                if audioType=="\x16":
                    if not ealayerSupport:
                        print "EALayer3 segment not converted as the tool is missing: "+Variation.ChunkId+" "+self.trueFilename
                        continue
                    target=os.path.join(outputFolder,self.trueFilename)+" "+str(Variation.ChunkIndex)+" "+str(Variation.Index)+" "+str(ijk)+".mp3"
                    makeLongDirs(target) #prepare the folder structure

                    process = subprocess.Popen([ealayer3Path,currentChunkName,"-i",str(Segment.SamplesOffset),"-o",target], stderr=subprocess.PIPE,startupinfo=startupinfo)
                    
                    process.communicate() #this should set the returncode
                    if process.returncode:
                        print process.stderr.readlines()

                    continue
                elif audioType!="\x14":
                    print "Unknown audio segment (type "+hexlify(audioType)+"): "+Variation.ChunkId+" "+self.trueFilename
                    continue

                

                channelRaw=f.read(1)
                if channelRaw not in channelDict:
                    print self.trueFilename
                
                    
                numChannels=channelDict[channelRaw]
                samplingRate=unpack(">H",f.read(2))[0] #[48000, 11025, 16000, 44100, 24000]
                f.read(4) #the first byte is always 0x40, the second takes one of 82 values, third and fourth can each take any value (i.e. 00 to ff)
                #82 values: ['\x01', '\x00', '\x03', '\x02', '\x05', '\x04', '\x07', '\x06', '\t', '\x08', '\x0b', '\n', '\r', '\x0c', '\x0f', '\x0e', '\x11', '\x10', '\x13', '\x12', '\x15', '\x14', '\x17', '\x16', '\x19', '\x18', '\x1b', '\x1a', '\x1d', '\x1c', '\x9f', '\x1e', '!', ' ', '#', '"', '%', '$', "'", '&', ')', '(', '+', '*', '-', ',', '/', '.', '1', '0', '3', '2', '5', '\x1f', '7', '6', '9', ';', '<', '?', '>', '\xc1', 'a', 'C', 'E', 'D', '\xa0', 'I', 'H', 'K', 'J', 'L', 'Y', 'X', '\x8e', '\x87', '4', 'A', 'd', 'F', '\x95', '\x7f']
                
                payload=""
                target= os.path.join(outputFolder,self.trueFilename)+" "+str(Variation.ChunkIndex)+" "+str(Variation.Index)+" "+str(ijk)+".wav"
                targetFolder=os.path.dirname(target)
                if not os.path.isdir(targetFolder): os.makedirs(targetFolder)

                f2=StringIO()
                
                write_header(f2, samplingRate, numChannels)
                
                while 1:
                    v1,length=unpack(">HH",f.read(4))

                    if length<=4: break
                    length-=8
                    
                    v2,v3=unpack(">HH",f.read(4))

                    if length%76!=0:
                        raise Exception("Strange length: "+str(length))
                        
                    atoms=length/76

                    blocks=[None]*numChannels
                    
                    for atom in xrange(0,atoms,numChannels):
                        for i in xrange(numChannels):
                            blocks[i]=decode(f.read(76))
                            
                        atomData=""
                        for i in xrange(128):
                            for j in xrange(numChannels):
                                atomData+=pack("f",blocks[j][i])
               
                        f2.write(atomData)

                finalPos=f2.tell()
                f2.seek(4)    
                f2.write(pack("I",finalPos-8))
                f2.seek(76)
                f2.write(pack("I",finalPos-76))

                f3=open2(target,"wb")
                f3.write(f2.getvalue())
                
                f2.close()

        for key in ChunkHandles:
            ChunkHandles[key].close()



def write_header(fp, samplingRate, nchannels):
    out = pack('4sl4s','RIFF',0,'WAVE')
    floatSize = 4
    fmt_size = 40
    tag = 0xFFFE
    etag = 3

    out += pack('4slHHllHH', 'fmt ', fmt_size, tag, nchannels, samplingRate,
                nchannels * samplingRate * floatSize, nchannels * floatSize, floatSize * 8)

    out += pack('HHlH14s', 22, floatSize * 8, (1 << nchannels) - 1, etag,
                '\x00\x00\x00\x00\x10\x00\x80\x00\x00\xaa\x008\x9b\x71')

    out += pack("<4sll","fact",4,floatSize)
    out += pack("4sl","data",0)

    fp.seek(0)
    fp.write(out)

    
xaslib = cdll.LoadLibrary("xas")
def decode(inputChars):
    charType = c_char * 76
    charBuf = charType(*inputChars)
    charbufpointer = pointer(charBuf)
    
    floatType = c_float * 128
    floatBuf = floatType()
    floatbufpointer = pointer(floatBuf)
    
    xaslib.decode(charbufpointer, floatbufpointer)
    
    return floatBuf


channelDict={"\x00":1,"\x04":2,"\x0c":4,"\x14":6,"\x1c":8,"\x05":2,"\x01":1}


if outputFolder[-1] not in ("/","\\"): outputFolder+="/"
if ebxFolder[-1] not in ("/","\\"): ebxFolder+="/"
if chunkFolder[-1] not in ("/","\\"): chunkFolder+="/"
if chunkFolder2[-1] not in ("/","\\"): chunkFolder2+="/"


#for ealayer. By default Python opens a new window for a split second and puts focus on it. This info makes no window show up at all.
startupinfo = subprocess.STARTUPINFO()
startupinfo.dwFlags |= subprocess.STARTF_USESHOWWINDOW
startupinfo.wShowWindow = subprocess.SW_HIDE


try:
    subprocess.Popen([ealayer3Path],startupinfo=startupinfo)
    ealayerSupport=True
    print "EALayer3 tool detected."
except WindowsError:
    ealayerSupport=False
    print "EALayer3 tool not detected."

    
decodeAudio()
```
## Post #72
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-05-09T20:01:18+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

That's god damn good.

Still have issues with Xbox360 version by the way?
## Post #73
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-05-09T23:03:15+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

> Reply from Vosvoy
>
> That's god damn good.

Still have issues with Xbox360 version by the way?

I decided to skip the 360 version, nothing was matching up. I just asked a friend if I could copy his files from the pc version and use that, he was cool with it, if not perplexed as to why I wanted just the files for a game we didn't even play anymore.

But he was cool with it, and I got what I needed.
## Post #74
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-05-09T23:31:19+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

Update

Testing now Army of two devils cartel the PS3 version as it uses EAlayer3. Works for the most part but has problems handling multichannel files.

EDIT: Okay seems i was using wrong arguments. The proper argument from ealayer3 to use is -S all" but i have no way of putting that properly into the python script in this line.

```
[ealayer3Path,currentChunkName,"-i",str(Segment.SamplesOffset),"-o",target], stderr=subprocess.PIPE,startupinfo=startupinfo)
```


any help?
## Post #75
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-05-10T01:57:59+00:00
- Post Title: Re: Battlefield 3: Sounds recording technique

All right. I believe that this time is the right one for console users. As OrangeC said: Frankelstner updated his script that can handle console FB2 games ( Army of Two: Devil's Cartel at least ) and seems to be functional. Here is the last script:

```
import string
import sys
from binascii import hexlify
from struct import unpack,pack
import os
from cStringIO import StringIO
import cProfile
import cPickle
import subprocess



ebxFolder=   r"D:\MOHWDUMP\bundles\ebx\mohw\audio" #audio is found in several places
chunkFolder= r"D:\MOHWDUMP\chunks" #grab audio from here
chunkFolder2=r"D:\MOHWDUMP\bundles\chunks" #if the chunk is not found in the first folder, use this one
outputFolder=r"D:\MOHWSOUNDS"
ealayer3Path=r"D:\ealayer3-0.7.0-win32\ealayer3.exe" #https://bitbucket.org/Zenchreal/ealayer3/downloads

ChunkIdObfuscation=False #set to True for some console games when the script does not find any chunks at all
obfuscationPermutation=[3,2,1,0,5,4,7,6,8,9,10,11,12,13,14,15]

#Run through the sound ebx files, find fields with chunk Guids and fieldName = ChunkId.
#The script will overwrite existing files.

#The filename of the ebx file importing an audio chunk becomes the name of the wav file.
#As for the indices, there are three of them in the following order.
#1: Variation.ChunkIndex: Some ebx files import several completely independent audio chunk files. This index differentiates between them. 
#2: Variation.Index: An ebx may use the same audio chunk for several sound variations, this index keeps them apart.
#3: Segment.Index: A variation may contain several segments, so there is another index.


##############################################################
##############################################################
def unpackBE(typ,data): return unpack(">"+typ,data)

def makeLongDirs(path):
    #create folders if necessary and return the file handle
    #first of all, create one folder level manully because makedirs might fail
    path=os.path.normpath(path)
    pathParts=path.split("\\")
    manualPart="\\".join(pathParts[:2])
    if not os.path.isdir(manualPart): os.makedirs(manualPart)
    
    #now handle the rest, including extra long path names
    folderPath=lp(os.path.dirname(path))
    if not os.path.isdir(folderPath): os.makedirs(folderPath)
    

def open2(path,mode="rb"):
    if mode=="wb": makeLongDirs(path)
    return open(lp(path),mode)

def lp(path): #long pathnames
    if len(path)<=247 or path=="" or path[:4]=='\\\\?\\': return path
    return unicode('\\\\?\\' + os.path.normpath(path))

def decodeAudio():
    for dir0, dirs, ff in os.walk(ebxFolder):
        for fname in ff:
            f=open2(dir0+"\\"+fname)
            magic=f.read(4)
            if magic=="\xCE\xD1\xB2\x0F":
                dbx=Dbx(f,unpack)
            elif magic=="\x0F\xB2\xD1\xCE":
                dbx=Dbx(f,unpackBE)
            else:
                f.close()
                continue
            dbx.decode()
            
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
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.type            = varList[1]
        self.ref             = varList[2] #the field may contain another complex
        self.offset          = varList[3] #offset in payload section; relative to the complex containing it
        self.secondaryOffset = varList[4]
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
        self.null            = varList[0] #called "internalCount", seems to be always null
        self.repetitions     = varList[1] #number of instance repetitions
        self.complexIndex    = varList[2] #index of complex used as the instance
class arrayRepeater:
    def __init__(self,varList):
        self.offset          = varList[0] #offset in array payload section
        self.repetitions     = varList[1] #number of array repetitions
        self.complexIndex    = varList[2] #not necessary for extraction
class Complex:
    def __init__(self,desc,dbxhandle):
        self.desc=desc
        self.dbx=dbxhandle #lazy
    def get(self,name):
        pathElems=name.split("/")
        curPos=self
        if pathElems[-1].find("::")!=-1: #grab a complex
            for elem in pathElems:
                try:
                    curPos=curPos.go1(elem)
                except Exception,e:
                    raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
            return curPos
        #grab a field instead
        for elem in pathElems[:-1]:
            try:
                curPos=curPos.go1(elem)
            except Exception,e:
                raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
        for field in curPos.fields:
            if field.desc.name==pathElems[-1]:
                return field
            
        raise Exception("Could not find field with name: "+name+"\nFilename: "+self.dbx.trueFilename)

    def go1(self,name): #go once
        for field in self.fields:
            if field.desc.type in (0x0029, 0xd029,0x0000,0x0041):
                if field.desc.name+"::"+field.value.desc.name == name:
                    return field.value
        raise Exception(name)


class Field:
    def __init__(self,desc,dbx):
        self.desc=desc
        self.dbx=dbx
    def link(self):
        if self.desc.type!=0x0035: raise Exception("Invalid link, wrong field type\nField name: "+self.desc.name+"\nField type: "+hex(self.desc.type)+"\nFile name: "+self.dbx.trueFilename)
        
        if self.value>>31:
            extguid=self.dbx.externalGUIDs[self.value&0x7fffffff]
            
            for existingDbx in dbxArray:
                if existingDbx.fileGUID==extguid[0]:
                    for guid, instance in existingDbx.instances:
                        if guid==extguid[1]:
                            return instance
                    

            f=valid(inputFolder+guidTable[extguid[0]]+".ebx")
##            print guidTable[extguid[0]]
            dbx=Dbx(f)
            dbxArray.append(dbx)
            for guid, instance in dbx.instances:
                if guid==extguid[1]:
                    return instance
            raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
        elif self.value!=0:
            for guid, instance in self.dbx.instances:
                if guid==self.dbx.internalGUIDs[self.value-1]:
                    return instance
        else:
            raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)

        raise Exception("Invalid link, could not find target.")

    def getlinkguid(self):
        if self.desc.type!=0x0035: raise Exception("Invalid link, wrong field type\nField name: "+self.desc.name+"\nField type: "+hex(self.desc.type)+"\nFile name: "+self.dbx.trueFilename)

        if self.value>>31:
            return "".join(self.dbx.externalGUIDs[self.value&0x7fffffff])
        elif self.value!=0:
            return self.dbx.fileGUID+self.dbx.internalGUIDs[self.value-1]
        else:
            raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
    def getlinkname(self):
        if self.desc.type!=0x0035: raise Exception("Invalid link, wrong field type\nField name: "+self.desc.name+"\nField type: "+hex(self.desc.type)+"\nFile name: "+self.dbx.trueFilename)

        if self.value>>31:
            return guidTable[self.dbx.externalGUIDs[self.value&0x7fffffff][0]]+"/"+self.dbx.externalGUIDs[self.value&0x7fffffff][1]
        elif self.value!=0:
            return self.dbx.trueFilename+"/"+self.dbx.internalGUIDs[self.value-1]
        else:
            raise nullguid("Nullguid link.\nFilename: "+self.dbx.trueFilename)
    

         
def valid(fname):
    f=open2(fname,"rb")
    if f.read(4) not in ("\xCE\xD1\xB2\x0F","\x0F\xB2\xD1\xCE"):
        f.close()
        raise Exception("nope")
    return f

class nullguid(Exception):
    def __init__(self, value):
        self.value = value
    def __str__(self):
        return repr(self.value)


numDict={0x0035:("I",4),0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("B",1),0xc0ed:("h",2), 0xc0dd:("H",2), 0xc13d:("f",4)}


class Stub:
    pass



class Dbx:
    def __init__(self, f,unpacker):
        self.unpack=unpacker
        self.trueFilename=""
        self.header=Header(self.unpack("11I",f.read(44)))
        self.arraySectionstart=self.header.absStringOffset+self.header.lenString+self.header.lenPayload
        self.fileGUID, self.primaryInstanceGUID = f.read(16), f.read(16)    
        self.externalGUIDs=[(f.read(16),f.read(16)) for i in xrange(self.header.numGUID)]
        self.keywords=str.split(f.read(self.header.lenName),"\x00")
        self.keywordDict=dict((hasher(keyword),keyword) for keyword in self.keywords)
        self.fieldDescriptors=[FieldDescriptor(self.unpack("IHHII",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
        self.complexDescriptors=[ComplexDescriptor(self.unpack("IIBBHHH",f.read(16)), self.keywordDict) for i in xrange(self.header.numComplex)]
        self.instanceRepeaters=[InstanceRepeater(self.unpack("3I",f.read(12))) for i in xrange(self.header.numInstanceRepeater)] 
        while f.tell()%16!=0: f.seek(1,1) #padding
        self.arrayRepeaters=[arrayRepeater(self.unpack("3I",f.read(12))) for i in xrange(self.header.numArrayRepeater)]

        #payload
        f.seek(self.header.absStringOffset+self.header.lenString)
        self.internalGUIDs=[]
        self.instances=[] # (guid, complex)
        for instanceRepeater in self.instanceRepeaters:
            for repetition in xrange(instanceRepeater.repetitions):
                instanceGUID=f.read(16)
                self.internalGUIDs.append(instanceGUID)
                if instanceGUID==self.primaryInstanceGUID:
                    self.isPrimaryInstance=True
                else:
                    self.isPrimaryInstance=False
                inst=self.readComplex(instanceRepeater.complexIndex,f)
                inst.guid=instanceGUID
                
                if self.isPrimaryInstance: self.prim=inst
                self.instances.append((instanceGUID,inst))
    
        f.close()
        

    def readComplex(self, complexIndex,f):
        complexDesc=self.complexDescriptors[complexIndex]
        cmplx=Complex(complexDesc,self)
        
        startPos=f.tell()                 
        cmplx.fields=[]
        for fieldIndex in xrange(complexDesc.fieldStartIndex,complexDesc.fieldStartIndex+complexDesc.numField):
            f.seek(startPos+self.fieldDescriptors[fieldIndex].offset)
            cmplx.fields.append(self.readField(fieldIndex,f))
        
        f.seek(startPos+complexDesc.size)
        return cmplx


    def readField(self,fieldIndex,f):
        fieldDesc = self.fieldDescriptors[fieldIndex]
        field=Field(fieldDesc,self)
        
        if fieldDesc.type in (0x0029, 0xd029,0x0000):
            field.value=self.readComplex(fieldDesc.ref,f)
        elif fieldDesc.type==0x0041:
            arrayRepeater=self.arrayRepeaters[self.unpack("I",f.read(4))[0]]
            arrayComplexDesc=self.complexDescriptors[fieldDesc.ref]

##            if arrayRepeater.repetitions==0: field.value = "*nullArray*"
            f.seek(self.arraySectionstart+arrayRepeater.offset)
            arrayComplex=Complex(arrayComplexDesc,self)
            arrayComplex.fields=[self.readField(arrayComplexDesc.fieldStartIndex,f) for repetition in xrange(arrayRepeater.repetitions)]
            field.value=arrayComplex
            
        elif fieldDesc.type in (0x407d, 0x409d):
            startPos=f.tell()
            f.seek(self.header.absStringOffset+self.unpack("I",f.read(4))[0])
            string=""
            while 1:
                a=f.read(1)
                if a=="\x00": break
                else: string+=a
            f.seek(startPos+4)
            
            if len(string)==0: field.value="*nullString*" #actually the string is ""
            else: field.value=string
            
            if self.isPrimaryInstance and self.trueFilename=="" and fieldDesc.name=="Name": self.trueFilename=string
            
                   
        elif fieldDesc.type==0x0089: #incomplete implementation, only gives back the selected string
            compareValue=self.unpack("I",f.read(4))[0] 
            enumComplex=self.complexDescriptors[fieldDesc.ref]

            if enumComplex.numField==0:
                field.value="*nullEnum*"
            for fieldIndex in xrange(enumComplex.fieldStartIndex,enumComplex.fieldStartIndex+enumComplex.numField):
                if self.fieldDescriptors[fieldIndex].offset==compareValue:
                    field.value=self.fieldDescriptors[fieldIndex].name
                    break
        elif fieldDesc.type==0xc15d:
            field.value=f.read(16)
        elif fieldDesc.type == 0xc13d: ################################
            field.value=formatfloat(self.unpack("f",f.read(4))[0])
        else:
            (typ,length)=numDict[fieldDesc.type]
            num=self.unpack(typ,f.read(length))[0]
            field.value=num
        
        return field
        

    def dump(self,outputFolder):
        dirName=os.path.dirname(outputFolder+self.trueFilename)
        if not os.path.isdir(dirName): os.makedirs(dirName)
        f2=open2(outputFolder+self.trueFilename+EXTENSION,"wb")
        print self.trueFilename
        
        for (guid,instance) in self.instances:
            if guid==self.primaryInstanceGUID: f2.write(instance.desc.name+" "+hexlify(guid)+ " #primary instance\r\n")
            else: f2.write(instance.desc.name+" "+hexlify(guid)+ "\r\n")
            self.recurse(instance.fields,f2,0)
        f2.close()

    def recurse(self, fields,f2, lvl): #over fields
        lvl+=1
        for field in fields:
            if field.desc.type in (0xc14d, 0xc0fd, 0xc10d, 0xc0ed, 0xc0dd, 0xc0bd, 0xc0ad, 0x407d, 0x409d, 0x0089):
                f2.write(lvl*SEP+field.desc.name+" "+str(field.value)+"\r\n")
            elif field.desc.type == 0xc13d:
                f2.write(lvl*SEP+field.desc.name+" "+formatfloat(field.value)+"\r\n")
            elif field.desc.type == 0xc15d:
                f2.write(lvl*SEP+field.desc.name+" "+hexlify(field.value)+"\r\n")
            elif field.desc.type == 0x0035:
                towrite=""
                if field.value>>31:
                    extguid=self.externalGUIDs[field.value&0x7fffffff]
                    try: towrite=guidTable[extguid[0]]+"/"+hexlify(extguid[1])
                    except: towrite=hexlify(extguid[0])+"/"+hexlify(extguid[1])
                elif field.value==0: towrite="*nullGuid*"
                else: towrite=hexlify(self.internalGUIDs[field.value-1])
                f2.write(lvl*SEP+field.desc.name+" "+towrite+"\r\n") 
            elif field.desc.type==0x0041 and len(field.value.fields)==0:
                f2.write(lvl*SEP+field.desc.name+" "+"*nullArray*"+"\r\n")
            else:
                f2.write(lvl*SEP+field.desc.name+"::"+field.value.desc.name+"\r\n")
                self.recurse(field.value.fields,f2,lvl)


    def decode(self):
        if not self.prim.desc.name=="SoundWaveAsset": return

        histogram=dict() #count the number of times each chunk is used by a variation to obtain the right index

        Chunks=[]
        for i in self.prim.get("$::SoundDataAsset/Chunks::array").fields:
            chnk=Stub()
            Chunks.append(chnk)
            chnk.ChunkId=i.value.get("ChunkId").value
            chnk.ChunkSize=i.value.get("ChunkSize").value

            
        variations=[i.link() for i in self.prim.get("Variations::array").fields]

        Variations=[]
        
        for var in variations:
            Variation=Stub()
            Variations.append(Variation)
            Variation.ChunkIndex=var.get("ChunkIndex").value
            Variation.SeekTablesSize=var.get("SeekTablesSize").value
            Variation.FirstLoopSegmentIndex=var.get("FirstLoopSegmentIndex").value
            Variation.LastLoopSegmentIndex=var.get("LastLoopSegmentIndex").value


            Variation.Segments=[]
            segs=var.get("Segments::array").fields
            for seg in segs:
                Segment=Stub()
                Variation.Segments.append(Segment)
                Segment.SamplesOffset = seg.value.get("SamplesOffset").value
                Segment.SeekTableOffset = seg.value.get("SeekTableOffset").value
                Segment.SegmentLength = seg.value.get("SegmentLength").value

            Variation.ChunkId=hexlify(Chunks[Variation.ChunkIndex].ChunkId)
            Variation.ChunkSize=Chunks[Variation.ChunkIndex].ChunkSize
        

            #find the appropriate index
            if Variation.ChunkIndex in histogram: #has been used previously already
                Variation.Index=histogram[Variation.ChunkIndex]
                histogram[Variation.ChunkIndex]+=1
            else:
                Variation.Index=0
                histogram[Variation.ChunkIndex]=1

                
        #everything is laid out neatly now
        #ChunkId, ChunkSize, Index, ChunkIndex, SeekTablesSize, FirstLoopSegmentIndex, LastLoopSegmentIndex
        #Segments with SamplesOffset, SeekTableOffset, SegmentLength

        ChunkHandles=dict() #for each ebx, keep track of all file handles

        for Variation in Variations:
            try:
                f=ChunkHandles[Variation.ChunkId]
            except:
                try:
                    f=open2(chunkFolder+Variation.ChunkId+".chunk")
                    currentChunkName=chunkFolder+Variation.ChunkId+".chunk"
                except IOError:
                    try:
                        f=open2(chunkFolder2+Variation.ChunkId+".chunk")
                        currentChunkName=chunkFolder2+Variation.ChunkId+".chunk"
                    except:
                        print "Chunk does not exist: "+Variation.ChunkId+" "+self.trueFilename
                        return
                ChunkHandles[Variation.ChunkId]=f


            for ijk in xrange(len(Variation.Segments)):
                Segment=Variation.Segments[ijk]
                f.seek(Segment.SamplesOffset)
                magic=f.read(4)
                
                if magic!="\x48\x00\x00\x0c":
                    raise Exception("Wrong XAS magic.")

                audioType=f.read(1) #0x14 is DICE XAS, 0x16 is ealayer3, 0x12 is unknown
                if audioType=="\x16":
                    if not ealayerSupport:
                        print "EALayer3 segment not converted as the tool is missing: "+Variation.ChunkId+" "+self.trueFilename
                        continue
                    target=os.path.join(outputFolder,self.trueFilename)+" "+str(Variation.ChunkIndex)+" "+str(Variation.Index)+" "+str(ijk)+".wav"
                    makeLongDirs(target) #prepare the folder structure

                    process = subprocess.Popen([ealayer3Path,currentChunkName,"-i",str(Segment.SamplesOffset),"-o",target,"-s","-w"], stderr=subprocess.PIPE,startupinfo=startupinfo)
                    
                    process.communicate() #this should set the returncode
                    if process.returncode:
                        print process.stderr.readlines()

                    continue
                elif audioType!="\x14":
                    print "Unknown audio segment (type "+hexlify(audioType)+"): "+Variation.ChunkId+" "+self.trueFilename
                    continue

                

                channelRaw=f.read(1)
                if channelRaw not in channelDict:
                    print self.trueFilename
                
                    
                numChannels=channelDict[channelRaw]
                samplingRate=unpack(">H",f.read(2))[0] #[48000, 11025, 16000, 44100, 24000]
                f.read(4) #the first byte is always 0x40, the second takes one of 82 values, third and fourth can each take any value (i.e. 00 to ff)
                #82 values: ['\x01', '\x00', '\x03', '\x02', '\x05', '\x04', '\x07', '\x06', '\t', '\x08', '\x0b', '\n', '\r', '\x0c', '\x0f', '\x0e', '\x11', '\x10', '\x13', '\x12', '\x15', '\x14', '\x17', '\x16', '\x19', '\x18', '\x1b', '\x1a', '\x1d', '\x1c', '\x9f', '\x1e', '!', ' ', '#', '"', '%', '$', "'", '&', ')', '(', '+', '*', '-', ',', '/', '.', '1', '0', '3', '2', '5', '\x1f', '7', '6', '9', ';', '<', '?', '>', '\xc1', 'a', 'C', 'E', 'D', '\xa0', 'I', 'H', 'K', 'J', 'L', 'Y', 'X', '\x8e', '\x87', '4', 'A', 'd', 'F', '\x95', '\x7f']
                
                payload=""
                target= os.path.join(outputFolder,self.trueFilename)+" "+str(Variation.ChunkIndex)+" "+str(Variation.Index)+" "+str(ijk)+".wav"
                targetFolder=os.path.dirname(target)
                if not os.path.isdir(targetFolder): os.makedirs(targetFolder)

                f2=StringIO()
                
                write_header(f2, samplingRate, numChannels)
                
                while 1:
                    v1,length=unpack(">HH",f.read(4))

                    if length<=4: break
                    length-=8
                    
                    v2,v3=unpack(">HH",f.read(4))

                    if length%76!=0:
                        raise Exception("Strange length: "+str(length))
                        
                    atoms=length/76

                    blocks=[None]*numChannels
                    
                    for atom in xrange(0,atoms,numChannels):
                        for i in xrange(numChannels):
                            blocks[i]=decode(f.read(76))
                            
                        atomData=""
                        for i in xrange(128):
                            for j in xrange(numChannels):
                                atomData+=pack("f",blocks[j][i])
               
                        f2.write(atomData)

                finalPos=f2.tell()
                f2.seek(4)    
                f2.write(pack("I",finalPos-8))
                f2.seek(76)
                f2.write(pack("I",finalPos-76))

                f3=open2(target,"wb")
                f3.write(f2.getvalue())
                
                f2.close()

        for key in ChunkHandles:
            ChunkHandles[key].close()



def write_header(fp, samplingRate, nchannels):
    out = pack('4sl4s','RIFF',0,'WAVE')
    floatSize = 4
    fmt_size = 40
    tag = 0xFFFE
    etag = 3

    out += pack('4slHHllHH', 'fmt ', fmt_size, tag, nchannels, samplingRate,
                nchannels * samplingRate * floatSize, nchannels * floatSize, floatSize * 8)

    out += pack('HHlH14s', 22, floatSize * 8, (1 << nchannels) - 1, etag,
                '\x00\x00\x00\x00\x10\x00\x80\x00\x00\xaa\x008\x9b\x71')

    out += pack("<4sll","fact",4,floatSize)
    out += pack("4sl","data",0)

    fp.seek(0)
    fp.write(out)

    
xaslib = cdll.LoadLibrary("xas")
def decode(inputChars):
    charType = c_char * 76
    charBuf = charType(*inputChars)
    charbufpointer = pointer(charBuf)
    
    floatType = c_float * 128
    floatBuf = floatType()
    floatbufpointer = pointer(floatBuf)
    
    xaslib.decode(charbufpointer, floatbufpointer)
    
    return floatBuf


channelDict={"\x00":1,"\x04":2,"\x0c":4,"\x14":6,"\x1c":8,"\x05":2,"\x01":1}


if outputFolder[-1] not in ("/","\\"): outputFolder+="/"
if ebxFolder[-1] not in ("/","\\"): ebxFolder+="/"
if chunkFolder[-1] not in ("/","\\"): chunkFolder+="/"
if chunkFolder2[-1] not in ("/","\\"): chunkFolder2+="/"


#for ealayer. By default Python opens a new window for a split second and puts focus on it. This info makes no window show up at all.
startupinfo = subprocess.STARTUPINFO()
startupinfo.dwFlags |= subprocess.STARTF_USESHOWWINDOW
startupinfo.wShowWindow = subprocess.SW_HIDE


try:
    subprocess.Popen([ealayer3Path,"-s","-w"],startupinfo=startupinfo)
    ealayerSupport=True
    print "EALayer3 tool detected."
except WindowsError:
    ealayerSupport=False
    print "EALayer3 tool not detected."

    
decodeAudio()
```


For PS3 users:

> From Frankelstner:
>
> 
>
> ChunkId FECAAFC2309C055D7E7D61C4C669F9C0 in EBX
>
> 
>
> Chunk ID In the filechunk name: c2afcafe9c305d057e7d61c4c669f9c0
>
> 
>
> lol
>
> 
>
> It's simple as pie.
>
> 
>
> FE CA AF C2 30 9C 05 5D 7E7D61C4C669F9C0
>
> C2 CA AF FE 30 9C 05 5D 7E7D61C4C669F9C0 #0 with 3
>
> C2 AF CA FE 30 9C 05 5D 7E7D61C4C669F9C0 #1 with 2
>
> C2 AF CA FE 9C 30 05 5D 7E7D61C4C669F9C0 #4 with 5
>
> C2 AF CA FE 9C 30 5D 05 7E7D61C4C669F9C0 #7 with 6
>
> 
>
> Ergo: 3 2 1 0 5 4 7 6 8 9 10 11 12 13 14 15
So, look at line 20 in the script and change False to True to allow the obfuscation permutation.

This one:

```
obfuscationPermutation=[3,2,1,0,5,4,7,6,8,9,10,11,12,13,14,15]
```

As OrangeC mentionned, it works for PS3 version as they are EALayer3 encoded.
## Post #76
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-05-10T03:27:23+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Its not going to convert X360 sounds because.

1. its EA XMA format.

2. Needs third party tools to be implemented into the script such as: "ea-Multi_xma to parse the XMA streams" "QuickBMS and XMA header Script to Add the Proper XMA header and Towav to convert the XMA files to wav.

It can be done but the process of adding it is beyond my skills.
## Post #77
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-05-10T15:35:30+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from OrangeC
>
> Its not going to convert X360 sounds because.

1. its EA XMA format.

2. Needs third party tools to be implemented into the script such as: "ea-Multi_xma to parse the XMA streams" "QuickBMS and XMA header Script to Add the Proper XMA header and Towav to convert the XMA files to wav.

Oh yeah I completly forgot that it's XMA for Xbox360.
## Post #78
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-07-26T00:50:20+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Ok so, even though I got it to work before, now everytime I try to decode bf3 or warfighter, it tells me how ealayer3 needs a specified input filename.. Can anyone help? it happens as soon as it trys to decode an ealayer3 file, and then i cant do anything but close it. (which shutsdown the whole conversion of all files) I think somethings different, because it used to just pop up a seperate window for each one. but i've updated to the latest fb2 decoder pack and still nothing.
## Post #79
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-07-26T15:46:19+00:00
- Post Title: Re: Frostbite 2 sound extraction research

when I get back home I can send you mine see if it works.
## Post #80
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-07-29T16:48:24+00:00
- Post Title: Re: Frostbite 2 sound extraction research

No need, I used the earlier script without the ealayer3 integration and it works.
## Post #81
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-09-29T22:47:36+00:00
- Post Title: Re: Frostbite 2 sound extraction research

good news: bf4 beta preload's cas/cat files appear unencrypted!

bad news: I still can't get this damn thing to work with ea layer 3 on it ;-;
## Post #82
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-09-30T18:23:13+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Sound extraction doesn't work for BF4 Beta. Gotta wait and hope Frank updates his script.
## Post #83
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-10-01T01:50:13+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Ah, hadn't tested myself, guess they changed the filesystem somehow. I just looked in cas.cat and was suprised to see nyannyannyan since steam always encrypts all data on preloads. I guess origin is fine with giving everything out besides the executables.
## Post #84
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-29T16:32:06+00:00
- Post Title: Re: Frostbite 2 sound extraction research

I've just read the long and cool story about extracting sounds from BF3/BF4 with all those .ebx/.cat/.cas things.

Can anyone tell me, in the end, is it possible to properly extract BF4 sounds with names or not? Because it seems it has some very different format and .ebx were compressed with custom compression. Did Frankelstner finally had time to finish it or not?
## Post #85
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2015-04-03T15:16:12+00:00
- Post Title: Re: Frostbite 2 sound extraction research

He did but has been MIA for a year now and bfeditor.org appears to be down where his scripts were at. :/ 

Would need someone continue his work to update it.
## Post #86
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-03T21:19:05+00:00
- Post Title: Re: Frostbite 2 sound extraction research

I still have is scripts. I also included the bf script and the frostbite audio extractor as well.

Also works for Battlefield hardlines PC version.

[https://mega.co.nz/#!UNUT3ZyL!esLEiI-NE ... fp_adBZ6JI](https://mega.co.nz/#!UNUT3ZyL!esLEiI-NEvMa66MgxDj8zjpt6_ELiF0MBfp_adBZ6JI)
## Post #87
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-04T13:41:46+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from Apollo
>
> He did but has been MIA for a year now and bfeditor.org appears to be down where his scripts were at. :/ 

Would need someone continue his work to update it.

What's need to be updated? As of now, I've changed his script a little to extract just the audio files. It doesn't take as much time and space as full extraction.

A week ago bfeditor was working... Who hosted the site? The same man?
## Post #88
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-04T13:47:28+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from OrangeC
>
> I still have is scripts. I also included the bf script and the frostbite audio extractor as well.

Also works for Battlefield hardlines PC version.

Thank you. Can you give me a link to the forum thread where it was posted? Was there anything interesting? I will read it in google cache.
## Post #89
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-04T20:25:29+00:00
- Post Title: Re: Frostbite 2 sound extraction research

[http://www.bfeditor.org/forums/index.ph ... opic=15844](http://www.bfeditor.org/forums/index.php?showtopic=15844)

Managed to scrounge up this.
## Post #90
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-05T14:55:20+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from OrangeC
>
> Managed to scrounge up this.

Unfortunately, google somehow doesn't have this page saved  Anyway, thank you for saving his latest version, i looked through it, he cleared up the code and now it looks really better.

This is what I was able to figure out for now:

- We have BF3 script, with ZLIB decompression code. I can't check this, but fortunately it worked for BF3, at least for most files.

- We have BF4 script, with custom LZ77 decompressor by Frankelstner as a separate dll (with no source code). It works for BF4 & BFH. I checked it on BFH beta, the script produced 4337 audio chunks, and successfully unpacked them into wavs. The data of ALL those 4337 chunks were used in unpacking, so I'm almost sure it really extracts ALL audio. Good work. The only problem i see is that XAS is really integer codec, not float. Of course you can extract it to floats, you can even make your cat float, but it doesn't mean it's a floating animal. This results in 2x times bigger files.

- When trying to apply this to Dragon Age Inquisition, I can't unpack anything, because of format changes. Files packed with ZLIB, but BF3 script doesn't work. BF4 doesn't work either, because it assumes it must be LZ77. The only thing people can do (and it is in video tutorial) is to remove all .cas and unpack only EN.VOC file which has about 3000 audio files. I was able to comment lines in BF4 script to extract only chunks, so now i have all 10587 audio files from the game. They are convertible, but have no proper names. DAI tools can find proper names, but can't extract audio (thus conversion errors). Also it is not suitable for mass extraction, but only as explorer.
## Post #91
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-05T18:45:47+00:00
- Post Title: Re: Frostbite 2 sound extraction research

All right, I have changed BF3 script so now it unpacks full DAI archives. It gave me 12000+ audio .ebx files, now proceeding with them.

fb3decoder.py script now extracts 23000 files (340 XAS, others Ealayer3) that used 9100 chunks as the source. Definitely it doesn't recognize music chunks. Proceeding.

It seems music .ebx have something different in them. Current scripts included. Can't guarantee it will work, try it. It must produce a lot of chunks.
[dai_dumper.rar](https://xentaxbackup.github.io/file/8955_dai_dumper.rar)
## Post #92
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-06T04:05:00+00:00
- Post Title: Re: Frostbite 2 sound extraction research

The scripts required a certain version of Python I don't remember which one. Someone have it?
## Post #93
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-06T04:25:37+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from Vosvoy
>
> The scripts required a certain version of Python I don't remember which one. Someone have it?

It must be 2.7 or later
## Post #94
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-06T04:42:11+00:00
- Post Title: Re: Frostbite 2 sound extraction research

All right. 

I just noticed that the ebx script is missing from OrangeC archive. Someone have it?

EDIT: Never mind, you can have it [here](http://pastebin.com/V7wuHpcV) but I think we need the floattostring.dll as well but I can't find it anywhere.

It gives me this error:

```
  File "H:\BF3SNDS\Script\final\ebx.py", line 407, in <module>
    main()
  File "H:\BF3SNDS\Script\final\ebx.py", line 45, in main
    createGuidTable()
  File "H:\BF3SNDS\Script\final\ebx.py", line 62, in createGuidTable
    dbx=Dbx(f,relPath)
  File "H:\BF3SNDS\Script\final\ebx.py", line 200, in __init__
    self.fieldDescriptors=[FieldDescriptor(self.unpack("IHHii",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
  File "H:\BF3SNDS\Script\final\ebx.py", line 149, in __init__
    self.name            = keywordDict[varList[0]]
KeyError: 291404853
>>> 
```


In the other hand I can read "#The floattostring.dll requires 32bit Python to write floating point numbers in a succinct manner, but the dll is not required to run this script." so I don't know what to think.

EDIT2: Ok so, I tried again but with the Battlefield 3 Open Beta files and it worked but not with the provided ebx script above but with this one:

```
import string
import sys
from binascii import hexlify
from struct import unpack
import os
from cStringIO import StringIO
import cProfile
import cPickle

#adjust input and output folders here
inputFolder=r"H:\BF3SNDS\DUMP\bundles\ebx\sound"
outputFolder=r"H:\BF3SNDS\EBX"
guidTableName="guidTable bf" #name of the guid table file

EXTENSION=".txt"
SEP="    "

#the script can use the actual filenames in the explorer for the guid table (fast)
#or it can parse almost the entire file to retrieve the filename (slow, but necessary when the explorer names are just hashes)
#in case #2, create a separate guidTable file, in case#1 do not create that file. 
#True/False
useExplorerNames=True


#ignore all instances and fields with these names when converting to text:
IGNOREINSTANCES=[]
IGNOREFIELDS=[]
##IGNOREINSTANCES=["ShaderAdjustmentData","SocketData","WeaponSkinnedSocketObjectData","WeaponRegularSocketObjectData"]
##IGNOREFIELDS=["Mesh3pTransforms","Mesh3pRigidMeshSocketObjectTransforms"]


#run createGuidTable or dumpText, or both (preferably in the right order)
#When using explorer names, do not change anything below.
#When not using explorer names you might want to make the guid table first, then restart the script to dump text only,
#though it should work fine without change too.
def main():
    createGuidTable()
    dumpText()




##############################################################
##############################################################
if useExplorerNames:
    def createGuidTable(): #guid vs filename
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                path=os.path.join(dir0,fname)
                f=open(path,"rb")
                if f.read(4)!="\xCE\xD1\xB2\x0F":
                    f.close()
                    continue
                #grab the file guid directly, absolute offset 48 bytes
                f.seek(48)
                fileguid=f.read(16)
                f.close()
                filename=path[len(inputFolder):-4].replace("\\","/")
                guidTable[fileguid]=filename
else:
    def createGuidTable():
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                f=open(dir0+"\\"+fname,"rb")
                if f.read(4)!="\xCE\xD1\xB2\x0F":
                    f.close()
                    continue
                dbx=Dbx(f)
                guidTable[dbx.fileGUID]=dbx.trueFilename
        f5=open(guidTableName,"wb") #write the table
        cPickle.dump(guidTable,f5)
        f5.close()

def dumpText():
    for dir0, dirs, ff in os.walk(inputFolder):
        for fname in ff:
            f=open(dir0+"\\"+fname,"rb")
            if f.read(4)!="\xCE\xD1\xB2\x0F":
                f.close()
                continue
            dbx=Dbx(f)
            dbx.dump(outputFolder)
            
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
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.type            = varList[1]
        self.ref             = varList[2] #the field may contain another complex
        self.offset          = varList[3] #offset in payload section; relative to the complex containing it
        self.secondaryOffset = varList[4]
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
        self.null            = varList[0] #called "internalCount", seems to be always null
        self.repetitions     = varList[1] #number of instance repetitions
        self.complexIndex    = varList[2] #index of complex used as the instance
class arrayRepeater:
    def __init__(self,varList):
        self.offset          = varList[0] #offset in array payload section
        self.repetitions     = varList[1] #number of array repetitions
        self.complexIndex    = varList[2] #not necessary for extraction
class Complex:
    def __init__(self,desc):
        self.desc=desc
class Field:
    def __init__(self,desc):
        self.desc=desc

numDict={0x0035:("I",4),0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("B",1),0xc0ed:("h",2), 0xc0dd:("H",2), 0xc13d:("f",4)}

class Dbx:
    def __init__(self, f):
        #metadata
        self.trueFilename=""
        self.header=Header(unpack("11I",f.read(44)))
        self.arraySectionstart=self.header.absStringOffset+self.header.lenString+self.header.lenPayload
        self.fileGUID, self.primaryInstanceGUID = f.read(16), f.read(16)    
        self.externalGUIDs=[(f.read(16),f.read(16)) for i in xrange(self.header.numGUID)]
        self.keywords=str.split(f.read(self.header.lenName),"\x00")
        self.keywordDict=dict((hasher(keyword),keyword) for keyword in self.keywords)
        self.fieldDescriptors=[FieldDescriptor(unpack("IHHII",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
        self.complexDescriptors=[ComplexDescriptor(unpack("IIBBHHH",f.read(16)), self.keywordDict) for i in xrange(self.header.numComplex)]
        self.instanceRepeaters=[InstanceRepeater(unpack("3I",f.read(12))) for i in xrange(self.header.numInstanceRepeater)] 
        while f.tell()%16!=0: f.seek(1,1) #padding
        self.arrayRepeaters=[arrayRepeater(unpack("3I",f.read(12))) for i in xrange(self.header.numArrayRepeater)]

        #payload
        f.seek(self.header.absStringOffset+self.header.lenString)
        self.internalGUIDs=[]
        self.instances=[] # (guid, complex)
        for instanceRepeater in self.instanceRepeaters:
            for repetition in xrange(instanceRepeater.repetitions):
                instanceGUID=f.read(16)
                self.internalGUIDs.append(instanceGUID)
                if instanceGUID==self.primaryInstanceGUID: self.isPrimaryInstance=True
                else: self.isPrimaryInstance=False
                
                self.instances.append( (instanceGUID,self.readComplex(instanceRepeater.complexIndex,f)) )
        f.close()
        
        

    def readComplex(self, complexIndex,f):
        complexDesc=self.complexDescriptors[complexIndex]
        cmplx=Complex(complexDesc)
        
        startPos=f.tell()                 
        cmplx.fields=[]
        for fieldIndex in xrange(complexDesc.fieldStartIndex,complexDesc.fieldStartIndex+complexDesc.numField):
            f.seek(startPos+self.fieldDescriptors[fieldIndex].offset)
            cmplx.fields.append(self.readField(fieldIndex,f))
        
        f.seek(startPos+complexDesc.size)
        return cmplx


    def readField(self,fieldIndex,f):
        fieldDesc = self.fieldDescriptors[fieldIndex]
        field=Field(fieldDesc)
        
        if fieldDesc.type in (0x0029, 0xd029,0x0000):
            field.value=self.readComplex(fieldDesc.ref,f)
        elif fieldDesc.type==0x0041:
            arrayRepeater=self.arrayRepeaters[unpack("I",f.read(4))[0]]
            arrayComplexDesc=self.complexDescriptors[fieldDesc.ref]

##            if arrayRepeater.repetitions==0: field.value = "*nullArray*"
            f.seek(self.arraySectionstart+arrayRepeater.offset)
            arrayComplex=Complex(arrayComplexDesc)
            arrayComplex.fields=[self.readField(arrayComplexDesc.fieldStartIndex,f) for repetition in xrange(arrayRepeater.repetitions)]
            field.value=arrayComplex
            
        elif fieldDesc.type in (0x407d, 0x409d):
            startPos=f.tell()
            f.seek(self.header.absStringOffset+unpack("I",f.read(4))[0])
            string=""
            while 1:
                a=f.read(1)
                if a=="\x00": break
                else: string+=a
            f.seek(startPos+4)
            
            if len(string)==0: field.value="*nullString*" #actually the string is ""
            else: field.value=string
            
            if self.isPrimaryInstance and self.trueFilename=="" and fieldDesc.name=="Name": self.trueFilename=string
            
                   
        elif fieldDesc.type==0x0089: #incomplete implementation, only gives back the selected string
            compareValue=unpack("I",f.read(4))[0] 
            enumComplex=self.complexDescriptors[fieldDesc.ref]

            if enumComplex.numField==0:
                field.value="*nullEnum*"
            for fieldIndex in xrange(enumComplex.fieldStartIndex,enumComplex.fieldStartIndex+enumComplex.numField):
                if self.fieldDescriptors[fieldIndex].offset==compareValue:
                    field.value=self.fieldDescriptors[fieldIndex].name
                    break
        elif fieldDesc.type==0xc15d:
            field.value=f.read(16)
        else:
            (typ,length)=numDict[fieldDesc.type]
            num=unpack(typ,f.read(length))[0]
            field.value=num
        
        return field
        

    def dump(self,outputFolder):
        dirName=os.path.dirname(outputFolder+self.trueFilename)
        if not os.path.isdir(dirName): os.makedirs(dirName)
        if not self.trueFilename: self.trueFilename=hexlify(self.fileGUID)
        f2=open(outputFolder+self.trueFilename+EXTENSION,"wb")
        print self.trueFilename
        
        for (guid,instance) in self.instances:
            if instance.desc.name not in IGNOREINSTANCES: #############
                if guid==self.primaryInstanceGUID: f2.write(instance.desc.name+" "+hexlify(guid)+ " #primary instance\r\n")
                else: f2.write(instance.desc.name+" "+hexlify(guid)+ "\r\n")
                self.recurse(instance.fields,f2,0)
        f2.close()

    def recurse(self, fields, f2, lvl): #over fields
        lvl+=1
        for field in fields:
            if field.desc.type in (0xc14d, 0xc0fd, 0xc10d, 0xc0ed, 0xc0dd, 0xc0bd, 0xc0ad, 0x407d, 0x409d, 0x0089):
                f2.write(lvl*SEP+field.desc.name+" "+str(field.value)+"\r\n")
            elif field.desc.type == 0xc13d:
                f2.write(lvl*SEP+field.desc.name+" "+formatfloat(field.value)+"\r\n")
            elif field.desc.type == 0xc15d:
                f2.write(lvl*SEP+field.desc.name+" "+hexlify(field.value).upper()+"\r\n") #upper case=> chunk guid
            elif field.desc.type == 0x0035:
                towrite=""
                if field.value>>31:
                    extguid=self.externalGUIDs[field.value&0x7fffffff]
                    try: towrite=guidTable[extguid[0]]+"/"+hexlify(extguid[1])
                    except: towrite=hexlify(extguid[0])+"/"+hexlify(extguid[1])
                elif field.value==0: towrite="*nullGuid*"
                else: towrite=hexlify(self.internalGUIDs[field.value-1])
                f2.write(lvl*SEP+field.desc.name+" "+towrite+"\r\n") 
            elif field.desc.type==0x0041 and len(field.value.fields)==0:
                f2.write(lvl*SEP+field.desc.name+" "+"*nullArray*"+"\r\n")
            else:
                if field.desc.name not in IGNOREFIELDS: #############
                    f2.write(lvl*SEP+field.desc.name+"::"+field.value.desc.name+"\r\n")
                    self.recurse(field.value.fields,f2,lvl)


if outputFolder[-1] not in ("/","\\"): outputFolder+="/"
if inputFolder[-1] not in ("/","\\"): inputFolder+="/"


#if there's a guid table already, use it
try:
    f5=open(guidTableName,"rb")
    guidTable=cPickle.load(f5)
    f5.close()
except:
    guidTable=dict()


main()
```


No chances about the sound decoder though (almost the same error as above). Doesn't work on BF3 anymore I presume.
## Post #95
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-06T16:51:25+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from Vosvoy
>
> All right. 

I just noticed that the ebx script is missing from OrangeC archive. Someone have it?

It IS in OrangeC archive and its called fb3decoder. It works for DAI.

p.s. I was wrong. The script recognizes all music chunks. I just didn't count the conversations.
So in total there are:

- 9101 chunks for /sound/
- 1465 chunks for /designcontent/conversations/
- 1 chunk for /vo/ss_inquisitor_vostream
= 10567 chunks. And this is exactly the total number of audio chunks found by dumper.
Win! We have extracted ALL audio chunks from DAI with proper names and all segments. This gives us about 100.000 audio files.

p.p.s. Ealayer3 needed to be corrected again to support this. It seems even with this version it fails somewhere after 90.000 files. I will correct it later.
## Post #96
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-08T18:37:11+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Ok. It seems Ealayer3 can't decode only 2 small files from the whole game. It is interesting and I will investigave that later, but for now here's the current version of audio extraction script (all .dlls and my version of ealayer3 included) It will skip those 2 small files (1 ironbull roar and 1 claws scratching)

It converts all 10567 audio chunks into 101600 mp3 and wav files. Enjoy.

Later I will also make an extractor version to extract audio only, and put it all in one new thread.
[dai_audio_decoder.rar](https://xentaxbackup.github.io/file/8985_dai_audio_decoder.rar)
## Post #97
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-12T12:02:12+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Anybody have the old script to unpack the audio from BF3? It must be called fb2decoder.py or fb2audio and now I can't find it anywhere. We have all the other scripts now: both dumpers for BF3 & BF4, both ebxtotxt for old and new .ebx format, and audio extractor for BF4.
## Post #98
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-12T13:30:17+00:00
- Post Title: Re: Frostbite 2 sound extraction research

That's what I told you. The new script doesn't work at all on BF3 anymore. I don't think that the current .ebx script works on BF3 either. I've lost all my data lately so I don't have the scripts anymore (my HDD is beeping. It must be the head stucked/blocked inside the HDD. So, I consider I've a 50/50 chance of recovering my stuff).
## Post #99
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-12T14:15:28+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from Vosvoy
>
> That's what I told you. The new script doesn't work at all on BF3 anymore. I don't think that the current .ebx script works on BF3 either.

Yes I know that. BF3 has different .ebx format, so the new script can't work with them.

I just thought you were talking about Dragon Age, and this is a different story. It has new .ebx format, but files packed with old packer, that's why I was able to change "dump" script to unpack it, and then use new audio script to decode the audio.

I think I can write a script to unpack BF3 again, but first let's see maybe someone has it saved.
## Post #100
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-12T14:37:29+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from daemon1
>
> I think I can write a script to unpack BF3 again, but first let's see maybe someone has it saved.

Sure. Maybe I could recover my stuff on the HDD that keeps beepin' (where all my extraction tools are). But I'll need some extra tools for that. Maybe the next week.
## Post #101
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-12T17:25:55+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Nevermind. I've already made a new script and it works. I've compiled different parts of all his scripts, redone a part where .ebx is analysed and it seems it gives proper audio files. Just need to check it now if everything was extracted.

p.s. checked. As in DAI, all files extracted OK, except one, i don't know why
## Post #102
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-12T19:26:54+00:00
- Post Title: Re: Frostbite 2 sound extraction research

So? You did it? Don't need the old scripts?
## Post #103
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-12T19:32:50+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from Vosvoy
>
> So? You did it? Don't need the old scripts?

Yes, I did it. Only checked it on one game, but i think it will work for all of frostbite 2 games. I also want to replace that XAS.dll so it will produce 16-bit sounds. It will save a lot of space. There's no need to make 32-bit waves, when the quality is long gone and said goodbye. It was packed into 4-bit adpcm xas.
## Post #104
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-12T21:04:49+00:00
- Post Title: Re: Frostbite 2 sound extraction research

The "new" scripts to dump and decode frostbite 2 games:

dumper, ebxtotxt, fb2audio

All .dlls and ealayer3 included
[bf3extractor.rar](https://xentaxbackup.github.io/file/9010_bf3extractor.rar)
## Post #105
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-13T14:00:15+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Oh man, you know your shit. Multitask guy heh?

Jokes apart, script works with BF3OpenBeta. Thanks mate.
## Post #106
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-13T16:18:58+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from Vosvoy
>
> script works with BF3OpenBeta. Thanks mate.

Good. Was it extracted before?

Also note that i forgot about this line in the script:

```

```

So it only extracts .ebx files that have "sound" in its name. If you need to extract all, just remove it.
## Post #107
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-14T10:07:25+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from daemon1
>
> Good. Was it extracted before?

Yes, the old script worked with the BF3OpenBeta. The one provided by OrangeC didn't work I think because it was specially made for BF4 and BFH. 

I also noticed that you added the mpeg library to the process. Why is that?
## Post #108
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-12T03:21:22+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Sorry to bump but I'm having a hard time getting the dumper script to dump the chunk data from the Battlefront alpha can somebody have a look and see if the script can extract the data from the alpha? 

I keep getting 

```
Patched cat not found.
>>> 
```
## Post #109
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-13T14:45:27+00:00
- Post Title: Re: Frostbite 2 sound extraction research

you should change folder names in the script
## Post #110
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-13T17:19:07+00:00
- Post Title: Re: Frostbite 2 sound extraction research

I hate doing this to you but i'm not following. Can you give me an example? by changing folder names in the script are we talking throughout the script or only the directories?
## Post #111
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-13T17:43:59+00:00
- Post Title: Re: Frostbite 2 sound extraction research

yes i mean directories in the beginning. It's also possible that this script just doesn't work with this alpha.
## Post #112
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-14T12:04:08+00:00
- Post Title: Re: Frostbite 2 sound extraction research

I changed the directories and am still getting the same message.
## Post #113
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-14T12:10:32+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Are there any .toc files in game? The script work is all based on these TOC files. It seems they changed something in this new engine version. But i've heard some people already working with it, so maybe soon they can extract sounds too. At least I checked CAS files and they contain the same old good XAS sounds.
## Post #114
- Username: wantafanta
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 10, 2015 4:08 am
- Post datetime: 2015-08-09T20:41:37+00:00
- Post Title: Re: Frostbite 2 sound extraction research

thanks to the creator of the new bf3 dumper! this needs to be shared in its own thread or something because i spent a very long time looking for this (started looking right after the bfeditor forums went down, never grabbed it while i had the chance) and im sure it'd save others alot of time searching.
## Post #115
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-12T17:47:07+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from wantafanta
>
> thanks to the creator of the new bf3 dumper! this needs to be shared in its own thread or something because i spent a very long time looking for this (started looking right after the bfeditor forums went down, never grabbed it while i had the chance) and im sure it'd save others alot of time searching.

yeah, i was going to put that all together and publish. Too many scripts, too many options.
## Post #116
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2015-08-16T17:56:59+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Someone get tuts please i'am little lost 
look easy just bad path directory 
or somethink's like that's looking
for only sound
## Post #117
- Username: wantafanta
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 10, 2015 4:08 am
- Post datetime: 2015-08-18T16:08:14+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from daemon1
>
> wantafanta wrote:thanks to the creator of the new bf3 dumper! this needs to be shared in its own thread or something because i spent a very long time looking for this (started looking right after the bfeditor forums went down, never grabbed it while i had the chance) and im sure it'd save others alot of time searching.

yeah, i was going to put that all together and publish. Too many scripts, too many options.

hmm do you have the BC2 scripts? i cant seem to be able to get the MG3 normal maps no matter what i do... i dont even know where the files are at inside the game directory i assume the async/weapons/ folder but there is more than one MG3 and they dont have textures stored there(im using the BC2Mod tools v3 so i dont know if its actually working or if i have some other issue but this has been a huge issue i havent been able to solve
## Post #118
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-18T17:01:49+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from wantafanta
>
> hmm do you have the BC2 scripts?

I don't know what is BC2, but on my experience textures sometimes can have rather unexpected names or locations.
## Post #119
- Username: oliie23
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 23, 2015 4:57 am
- Post datetime: 2015-08-21T09:24:41+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from wantafanta
>
> daemon1 wrote:wantafanta wrote:thanks to the creator of the new bf3 dumper! this needs to be shared in its own thread or something because i spent a very long time looking for this (started looking right after the bfeditor forums went down, never grabbed it while i had the chance) and im sure it'd save others alot of time searching.

yeah, i was going to put that all together and publish. Too many scripts, too many options.

hmm do you have the BC2 scripts? i cant seem to be able to get the MG3 normal maps no matter what i do... i dont even know where the files are at inside the game directory i assume the async/weapons/ folder but there is more than one MG3 and they dont have textures stored there(im using the BC2Mod tools v3 so i dont know if its actually working or if i have some other issue but this has been a huge issue i havent been able to solve

Hey, for what it's worth, if you're still looking, I have the BC1 script, which should work for BC2. I can't really provide you with a lot of instructions because I used it a long time ago, but you'll have to use the .bat files and probably slightly edit them (directories, which header to add and maybe some other stuff). From what I remember, you'll have to run it at least twice to get both mono and stereo files. Also, note that files like the gunshots actually have 3 audio files inside them - the start, the loop, the end (that's how gunshots worked in BC) so you will have to extract those at least three times, each time adding a header in a different place. The tools I attached have a few different addheaders you might try but I'm not too sure which ones of them will work so there'll be a lot of trial and error.

Also, very important, for some reason this script will only work with the XBOX360 version of the game and, at least back in the day, there was no single script that'd work with the PC version.
The BC1 script is on GDrive since it's too big for the forum [https://drive.google.com/open?id=0B-q_S ... UpJUzVQSVk](https://drive.google.com/open?id=0B-q_SbN8FN2GUXVOeUpJUzVQSVk)

And if anyone's still interested, this is the BF3 script [https://drive.google.com/open?id=0B-q_S ... FdWZXJ0LXM](https://drive.google.com/open?id=0B-q_SbN8FN2GS3F5OFdWZXJ0LXM) - it'll work with PC version btw.
[bf3.zip](https://xentaxbackup.github.io/file/9602_bf3.zip)
## Post #120
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2015-08-21T19:40:02+00:00
- Post Title: Re: Frostbite 2 sound extraction research

got this message someone can help please 

Traceback (most recent call last):
  File "H:\bt\bf3_extractor\dumper.py", line 354, in <module>
    cat=Cat(catName)
  File "H:\bt\bf3_extractor\dumper.py", line 119, in __init__
    cat2=open(catname,"rb")
IOError: [Errno 2] No such file or directory: 'H:\\install\\DaI\\Data\\Data\\cas.cat'
## Post #121
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2015-08-25T11:46:37+00:00
- Post Title: Re: Frostbite 2 sound extraction research

bumper finaly work 
and audioextract say 
You must specify an input filename.

i have extract only .sb and look need ebx for do it
## Post #122
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2016-09-26T18:46:56+00:00
- Post Title: Re: Frostbite 2 sound extraction research

I post this question here as I don't want to flood the forum with new topics:

BF1 Open Beta has been available one or two weeks ago. I tried the usual tool and, as I expected, it doesn't work:

```
  File "D:\test\bf4dumper.py", line 258, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "D:\test\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "D:\test\bf4dumper.py", line 102, in dump
    toc=cas.readToc(tocPath)
  File "D:\test\cas.py", line 95, in readToc
    return Entry(unXor(tocPath))
  File "D:\test\cas.py", line 37, in __init__
    raise Exception("Entry does not start with \\x82 or (rare) \\x87 byte. Position: "+str(f.tell()))
Exception: Entry does not start with \x82 or (rare) \x87 byte. Position: 1
>>> 
```

Is my savior 'round here?
## Post #123
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-26T19:38:56+00:00
- Post Title: Re: Frostbite 2 sound extraction research

tried star wars extractor?
## Post #124
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2016-09-26T19:44:19+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from daemon1
>
> tried star wars extractor?

Heh? Same engine?
## Post #125
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-26T19:45:17+00:00
- Post Title: Re: Frostbite 2 sound extraction research

yes, all the latest frostbite games usually work with that extractor
## Post #126
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2016-09-26T20:05:18+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from daemon1
>
> yes, all the latest frostbite games usually work with that extractor

Well, I only found the old Frankelstner script (bf4dumper from xentax) and got this in the process:

```
  File "D:\test\Python_Scripts\dumper.py", line 282, in <module>
    cat=Cat(catName)
  File "D:\test\Python_Scripts\dumper.py", line 58, in __init__
    entry.offset, entry.size, entry.casnum = unpack("<III",cat.read(12))
error: unpack requires a string argument of length 12
```


So, either I'm dumb either the tool is not working (I've attached the tool we used on old BF3Beta and BF4Updated before).
[fb3tools.rar](https://xentaxbackup.github.io/file/11735_fb3tools.rar)
## Post #127
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-26T20:20:23+00:00
- Post Title: Re: Frostbite 2 sound extraction research

i mean this one: [viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584)
## Post #128
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2016-09-26T20:28:28+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from daemon1
>
> i mean this one: viewtopic.php?f=10&t=13584

Okay I'm gonna give it a go! 

I'm not sleepin until it's done. Seeya until further edition...

EDIT1: [10:43PM (GMT+01:00) Bruxelles, Copenhague, Madrid, Paris] Dumper runnin' (Insert french enthusiasm here: "Fantastique!").

EDIT2: [11:04PM (GMT+01:00) Bruxelles, Copenhague, Madrid, Paris] EBX and sounds correctly converted (with names and folders, nothin' to worry about).

EDIT3: [11:17PM (GMT+01:00) Bruxelles, Copenhague, Madrid, Paris] ealayer3.exe had some problems during VO sounds extraction: loops of "ealayer3.exe has stopped working" - (Python -> "Error executing EALayer3"). If you came for complete soldier voice assets, you're f*cked (for now).

EDIT4: [00:02AM (GMT+01:00) Bruxelles, Copenhague, Madrid, Paris] DONE. I managed to skip the previous error by erasing the "vo" folder. The tool is workin' (5,60Gb sound files on the disk) except the ealayer3.exe for voices.

Many thanks mate.
## Post #129
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-27T04:24:17+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from Vosvoy
>
> If you came for complete soldier voice assets...

If I'm not mistaking, you can convert them with my updated version of ealayer3, it was here somewhere... I'll find the link later.

p.s. send me examples of files that dont work
## Post #130
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2016-09-28T14:53:53+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from daemon1
>
> Vosvoy wrote:If you came for complete soldier voice assets...

If I'm not mistaking, you can convert them with my updated version of ealayer3, it was here somewhere... I'll find the link later.

p.s. send me examples of files that dont work

Alright, gotta dump the files again though. I'll brb.

EDIT: So, I tried to use the old EbxToTxt script (for BF4) to give you an exact chunk name but it doesn't work. Anyway, this is where the troubles start:

```
vo_mp_alert_gas.ebx
Error executing EALayer3.
Sound/VO/MP/DE/Autotriggers/Alert/vo_mp_alert_gas
vo_mp_alert_grenade.ebx
Sound/VO/MP/DE/Autotriggers/Alert/vo_mp_alert_grenade
vo_mp_alert_headsup.ebx
Error executing EALayer3.
Sound/VO/MP/DE/Autotriggers/Alert/vo_mp_alert_headsup
vo_mp_alert_machinegunner.ebx
Sound/VO/MP/DE/Autotriggers/Alert/vo_mp_alert_machinegunner
vo_mp_alert_playerhit.ebx
Sound/VO/MP/DE/Autotriggers/Alert/vo_mp_alert_playerhit
vo_mp_alert_sniper.ebx
Sound/VO/MP/DE/Autotriggers/Alert/vo_mp_alert_sniper
vo_mp_alert_tank.ebx
Error executing EALayer3.
Error executing EALayer3.
```


I've attached the EbxToTxt from our "common friend" Frankelstner, if you want or if you don't have it anymore.
[ebx.zip](https://xentaxbackup.github.io/file/11746_ebx.zip)
## Post #131
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2016-10-18T19:27:10+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Anyone tried to extract the BF1 trial, using the sw dumper, but its hardly finding any chunks. Maybe because each level folder has cas/cat files in their folders?
## Post #132
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2016-10-20T05:17:01+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from OrangeC
>
> Anyone tried to extract the BF1 trial, using the sw dumper, but its hardly finding any chunks. Maybe because each level folder has cas/cat files in their folders?
I tried, but failed. Specifies the path to each file. And each time the program received an error.

```
This application has requested the Runtime to terminate it in an unusual way. Please contact the application's support team for more information. 
```
## Post #133
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2016-10-23T19:59:48+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from OrangeC
>
> Anyone tried to extract the BF1 trial, using the sw dumper, but its hardly finding any chunks. Maybe because each level folder has cas/cat files in their folders?
Doesn't work for me either. I just tried another method:
I opened the .SB file for the prologue and renamed all sounds that end with "_wave" in "_waxe" except for the music tracks. Nothing changed, so I did the same with the .SB file in the Patch folder. But then the game crashes.
## Post #134
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-24T17:42:28+00:00
- Post Title: Re: Frostbite 2 sound extraction research

If nothing else helps, you can always get audio without names with a simple chunk extractor I posted my in Star Wars thread. And then decode them with Xas_decode or ealayer3, whatever they're using.
## Post #135
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2016-11-06T18:51:53+00:00
- Post Title: Re: Frostbite 2 sound extraction research

It took me a bit to get everything done, but I finally made it.
I guess without one of the main threads on bfeditor.org being down, it would have worked a hell of a lot faster... 

Anyways, just wanna say thank you to daemon1 for uploading every filed needed to extract the audio of bf3 and for sure to Frankelstner (although he seems to be dead or sth) and to anybody else here, doing a great job! 

However, if sb after me wants to have all the bf3 sounds and doesn't know how to...

> Reply from [url=http://forum.xentax.com/viewtopic.php?f=17&t=10347&start=103]Get to post[/url] daemon1
>
> The "new" scripts to dump and decode frostbite 2 games:

dumper, ebxtotxt, fb2audio

All .dlls and ealayer3 included
1. Download and Install Python 2.7
2. Download bf3extractor.rar (Uploaded by daemon1)
3. Adjust paths
4. Run dumper.py
5. Run fb2audio.py
Have a nice one! ^^
## Post #136
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2016-11-16T00:16:28+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Yeah, daemon1 and Frankelstner did a really really great job.

Thanks again guys for your work and patience. Useless post for most of readers, maybe, but kind of important for those who did help us (I guess). 

FatalBulletHit: are you talking about extracting BF1 sounds? Because the oldest tools didn't work.
## Post #137
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2016-12-14T09:30:54+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from Vosvoy
>
> FatalBulletHit: are you talking about extracting BF1 sounds? Because the oldest tools didn't work.
Nope, sry:

> Reply from FatalBulletHit
>
> However, if sb after me wants to have all the bf3 sounds and doesn't know how to...
## Post #138
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2017-06-17T09:30:14+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Hi,
I am interested in grabbing handheld weapons sounds from bf3. I extracted everything and I noticed that gunshot ebx files are significantly bigger and different than reloads ebx files. They also doesn't convert to wave using fb2audio.py. The script reads them, but doesnt convert to wave just as it does with reloads ebx. Does anyone know how to convert gunshots ebxes ?
## Post #139
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2017-06-21T20:33:36+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from rpopulik
>
> Does anyone know how to convert gunshots ebxes ?

I don't, but as far as I know, every single gun shot is made with the sounds in the "shared_content" folder and not with the files you are talking about. No guarantee, tho, and I don't have a clue why there are additional bigger files in each of these sub folders.
However, if you are trying to get a clean gun shot you will get the job done quite well with the sounds in "shared_content". It also gives you all the sounds you need for an immersive gun shot, e.g. a M82 shot in a forest with deploying the bipod, handling the safety, a case dropping on dirt, reflection of the shot, bolt action, etc.

Hope I was able to help, feel free to report back if you have more questions!
## Post #140
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-06-26T07:59:44+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from FatalBulletHit
>
> rpopulik wrote:Does anyone know how to convert gunshots ebxes ?

I don't, but as far as I know, every single gun shot is made with the sounds in the "shared_content" folder and not with the files you are talking about. No guarantee, tho, and I don't have a clue why there are additional bigger files in each of these sub folders.
However, if you are trying to get a clean gun shot you will get the job done quite well with the sounds in "shared_content". It also gives you all the sounds you need for an immersive gun shot, e.g. a M82 shot in a forest with deploying the bipod, handling the safety, a case dropping on dirt, reflection of the shot, bolt action, etc.

Hope I was able to help, feel free to report back if you have more questions!

You can convert those .ebx files to .txt files via a python script made by Frankelstner. Those files doesn't contain any sounds but informations about them.

Imagine that the wave samples are culinary ingredients, the ebx files are the recipes and the engine is the cook.

For example, I'm gonna make a REX MP412 gunfire sound. Thanks to the ebx file, I know what I need:
- " CoreBassClose_OneShot_DoublePunch_Wave " for the punch/power (Shared_Content\CoreBassClose_OneShot\...).
- " HiFi_Revolver_Wave " for the mechanical effect (Shared_Content\HiFi_OneShot\...) and put the speed of this sample at -60 in Audacity.
- " Noise_Close_Rifle_Wave " to make the main stereo layer (Shared_Content\Noise_Layers\...).

Mix the whole thing with an additional impulse response sound of your choice (Shared_Content\Reflections\... or Shared_Content\Noise_Layers\...) and "Voilà, bon appétit".

It worked for BF3 and BF4 but I don't know if it works for BF1.

If you don't have it already, try this script:

```
import string
import sys
from binascii import hexlify
from struct import unpack
import os
from cStringIO import StringIO
import cProfile
import cPickle

#adjust input and output folders here
inputFolder=r"H:\BF3SNDS\DUMP\bundles\ebx\sound"
outputFolder=r"H:\BF3SNDS\EBX"
guidTableName="guidTable bf" #name of the guid table file

EXTENSION=".txt"
SEP="    "

#the script can use the actual filenames in the explorer for the guid table (fast)
#or it can parse almost the entire file to retrieve the filename (slow, but necessary when the explorer names are just hashes)
#in case #2, create a separate guidTable file, in case#1 do not create that file. 
#True/False
useExplorerNames=True


#ignore all instances and fields with these names when converting to text:
IGNOREINSTANCES=[]
IGNOREFIELDS=[]
##IGNOREINSTANCES=["ShaderAdjustmentData","SocketData","WeaponSkinnedSocketObjectData","WeaponRegularSocketObjectData"]
##IGNOREFIELDS=["Mesh3pTransforms","Mesh3pRigidMeshSocketObjectTransforms"]


#run createGuidTable or dumpText, or both (preferably in the right order)
#When using explorer names, do not change anything below.
#When not using explorer names you might want to make the guid table first, then restart the script to dump text only,
#though it should work fine without change too.
def main():
    createGuidTable()
    dumpText()




##############################################################
##############################################################
if useExplorerNames:
    def createGuidTable(): #guid vs filename
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                path=os.path.join(dir0,fname)
                f=open(path,"rb")
                if f.read(4)!="\xCE\xD1\xB2\x0F":
                    f.close()
                    continue
                #grab the file guid directly, absolute offset 48 bytes
                f.seek(48)
                fileguid=f.read(16)
                f.close()
                filename=path[len(inputFolder):-4].replace("\\","/")
                guidTable[fileguid]=filename
else:
    def createGuidTable():
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                f=open(dir0+"\\"+fname,"rb")
                if f.read(4)!="\xCE\xD1\xB2\x0F":
                    f.close()
                    continue
                dbx=Dbx(f)
                guidTable[dbx.fileGUID]=dbx.trueFilename
        f5=open(guidTableName,"wb") #write the table
        cPickle.dump(guidTable,f5)
        f5.close()

def dumpText():
    for dir0, dirs, ff in os.walk(inputFolder):
        for fname in ff:
            f=open(dir0+"\\"+fname,"rb")
            if f.read(4)!="\xCE\xD1\xB2\x0F":
                f.close()
                continue
            dbx=Dbx(f)
            dbx.dump(outputFolder)
            
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
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.type            = varList[1]
        self.ref             = varList[2] #the field may contain another complex
        self.offset          = varList[3] #offset in payload section; relative to the complex containing it
        self.secondaryOffset = varList[4]
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
        self.null            = varList[0] #called "internalCount", seems to be always null
        self.repetitions     = varList[1] #number of instance repetitions
        self.complexIndex    = varList[2] #index of complex used as the instance
class arrayRepeater:
    def __init__(self,varList):
        self.offset          = varList[0] #offset in array payload section
        self.repetitions     = varList[1] #number of array repetitions
        self.complexIndex    = varList[2] #not necessary for extraction
class Complex:
    def __init__(self,desc):
        self.desc=desc
class Field:
    def __init__(self,desc):
        self.desc=desc

numDict={0x0035:("I",4),0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("B",1),0xc0ed:("h",2), 0xc0dd:("H",2), 0xc13d:("f",4)}

class Dbx:
    def __init__(self, f):
        #metadata
        self.trueFilename=""
        self.header=Header(unpack("11I",f.read(44)))
        self.arraySectionstart=self.header.absStringOffset+self.header.lenString+self.header.lenPayload
        self.fileGUID, self.primaryInstanceGUID = f.read(16), f.read(16)    
        self.externalGUIDs=[(f.read(16),f.read(16)) for i in xrange(self.header.numGUID)]
        self.keywords=str.split(f.read(self.header.lenName),"\x00")
        self.keywordDict=dict((hasher(keyword),keyword) for keyword in self.keywords)
        self.fieldDescriptors=[FieldDescriptor(unpack("IHHII",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
        self.complexDescriptors=[ComplexDescriptor(unpack("IIBBHHH",f.read(16)), self.keywordDict) for i in xrange(self.header.numComplex)]
        self.instanceRepeaters=[InstanceRepeater(unpack("3I",f.read(12))) for i in xrange(self.header.numInstanceRepeater)] 
        while f.tell()%16!=0: f.seek(1,1) #padding
        self.arrayRepeaters=[arrayRepeater(unpack("3I",f.read(12))) for i in xrange(self.header.numArrayRepeater)]

        #payload
        f.seek(self.header.absStringOffset+self.header.lenString)
        self.internalGUIDs=[]
        self.instances=[] # (guid, complex)
        for instanceRepeater in self.instanceRepeaters:
            for repetition in xrange(instanceRepeater.repetitions):
                instanceGUID=f.read(16)
                self.internalGUIDs.append(instanceGUID)
                if instanceGUID==self.primaryInstanceGUID: self.isPrimaryInstance=True
                else: self.isPrimaryInstance=False
                
                self.instances.append( (instanceGUID,self.readComplex(instanceRepeater.complexIndex,f)) )
        f.close()
        
        

    def readComplex(self, complexIndex,f):
        complexDesc=self.complexDescriptors[complexIndex]
        cmplx=Complex(complexDesc)
        
        startPos=f.tell()                 
        cmplx.fields=[]
        for fieldIndex in xrange(complexDesc.fieldStartIndex,complexDesc.fieldStartIndex+complexDesc.numField):
            f.seek(startPos+self.fieldDescriptors[fieldIndex].offset)
            cmplx.fields.append(self.readField(fieldIndex,f))
        
        f.seek(startPos+complexDesc.size)
        return cmplx


    def readField(self,fieldIndex,f):
        fieldDesc = self.fieldDescriptors[fieldIndex]
        field=Field(fieldDesc)
        
        if fieldDesc.type in (0x0029, 0xd029,0x0000):
            field.value=self.readComplex(fieldDesc.ref,f)
        elif fieldDesc.type==0x0041:
            arrayRepeater=self.arrayRepeaters[unpack("I",f.read(4))[0]]
            arrayComplexDesc=self.complexDescriptors[fieldDesc.ref]

##            if arrayRepeater.repetitions==0: field.value = "*nullArray*"
            f.seek(self.arraySectionstart+arrayRepeater.offset)
            arrayComplex=Complex(arrayComplexDesc)
            arrayComplex.fields=[self.readField(arrayComplexDesc.fieldStartIndex,f) for repetition in xrange(arrayRepeater.repetitions)]
            field.value=arrayComplex
            
        elif fieldDesc.type in (0x407d, 0x409d):
            startPos=f.tell()
            f.seek(self.header.absStringOffset+unpack("I",f.read(4))[0])
            string=""
            while 1:
                a=f.read(1)
                if a=="\x00": break
                else: string+=a
            f.seek(startPos+4)
            
            if len(string)==0: field.value="*nullString*" #actually the string is ""
            else: field.value=string
            
            if self.isPrimaryInstance and self.trueFilename=="" and fieldDesc.name=="Name": self.trueFilename=string
            
                   
        elif fieldDesc.type==0x0089: #incomplete implementation, only gives back the selected string
            compareValue=unpack("I",f.read(4))[0] 
            enumComplex=self.complexDescriptors[fieldDesc.ref]

            if enumComplex.numField==0:
                field.value="*nullEnum*"
            for fieldIndex in xrange(enumComplex.fieldStartIndex,enumComplex.fieldStartIndex+enumComplex.numField):
                if self.fieldDescriptors[fieldIndex].offset==compareValue:
                    field.value=self.fieldDescriptors[fieldIndex].name
                    break
        elif fieldDesc.type==0xc15d:
            field.value=f.read(16)
        else:
            (typ,length)=numDict[fieldDesc.type]
            num=unpack(typ,f.read(length))[0]
            field.value=num
        
        return field
        

    def dump(self,outputFolder):
        dirName=os.path.dirname(outputFolder+self.trueFilename)
        if not os.path.isdir(dirName): os.makedirs(dirName)
        if not self.trueFilename: self.trueFilename=hexlify(self.fileGUID)
        f2=open(outputFolder+self.trueFilename+EXTENSION,"wb")
        print self.trueFilename
        
        for (guid,instance) in self.instances:
            if instance.desc.name not in IGNOREINSTANCES: #############
                if guid==self.primaryInstanceGUID: f2.write(instance.desc.name+" "+hexlify(guid)+ " #primary instance\r\n")
                else: f2.write(instance.desc.name+" "+hexlify(guid)+ "\r\n")
                self.recurse(instance.fields,f2,0)
        f2.close()

    def recurse(self, fields, f2, lvl): #over fields
        lvl+=1
        for field in fields:
            if field.desc.type in (0xc14d, 0xc0fd, 0xc10d, 0xc0ed, 0xc0dd, 0xc0bd, 0xc0ad, 0x407d, 0x409d, 0x0089):
                f2.write(lvl*SEP+field.desc.name+" "+str(field.value)+"\r\n")
            elif field.desc.type == 0xc13d:
                f2.write(lvl*SEP+field.desc.name+" "+formatfloat(field.value)+"\r\n")
            elif field.desc.type == 0xc15d:
                f2.write(lvl*SEP+field.desc.name+" "+hexlify(field.value).upper()+"\r\n") #upper case=> chunk guid
            elif field.desc.type == 0x0035:
                towrite=""
                if field.value>>31:
                    extguid=self.externalGUIDs[field.value&0x7fffffff]
                    try: towrite=guidTable[extguid[0]]+"/"+hexlify(extguid[1])
                    except: towrite=hexlify(extguid[0])+"/"+hexlify(extguid[1])
                elif field.value==0: towrite="*nullGuid*"
                else: towrite=hexlify(self.internalGUIDs[field.value-1])
                f2.write(lvl*SEP+field.desc.name+" "+towrite+"\r\n") 
            elif field.desc.type==0x0041 and len(field.value.fields)==0:
                f2.write(lvl*SEP+field.desc.name+" "+"*nullArray*"+"\r\n")
            else:
                if field.desc.name not in IGNOREFIELDS: #############
                    f2.write(lvl*SEP+field.desc.name+"::"+field.value.desc.name+"\r\n")
                    self.recurse(field.value.fields,f2,lvl)


if outputFolder[-1] not in ("/","\\"): outputFolder+="/"
if inputFolder[-1] not in ("/","\\"): inputFolder+="/"


#if there's a guid table already, use it
try:
    f5=open(guidTableName,"rb")
    guidTable=cPickle.load(f5)
    f5.close()
except:
    guidTable=dict()


main()
```


(I'm not at home now so I just copy/pasted this script from an ancient post on this thread so tell me if this script doesn't work)

Cordialy.
## Post #141
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2017-07-04T12:38:46+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from Vosvoy
>
> (I'm not at home now so I just copy/pasted this script from an ancient post on this thread so tell me if this script doesn't work)
Works totally fine, had the exact same script already on my HDD but apparently never used it.

Just one question:
"Weapon_SMG_UMP45_Silenced_02.txt" has 5498 lines of code... I understand the 56 paths, but what are the other 5442 lines about?   
I mean, what is important and how do you know stuff like this:

> Reply from Vosvoy
>
>  [...] put the speed of this sample at -60 in Audacity.
?
## Post #142
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-07-06T02:29:55+00:00
- Post Title: Re: Frostbite 2 sound extraction research

Any change someone could look at the audio stuff from battlefront 2 not sure if it's the sounds that's changed or the ebx format has changed but if anyone needs anything else like a chunk file to go along with that ebx file tell me the names...ect and i'll send it
[dc15.rar](https://xentaxbackup.github.io/file/13078_dc15.rar)
## Post #143
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-07-11T03:19:40+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from FatalBulletHit
>
> Vosvoy wrote:
Just one question:
"Weapon_SMG_UMP45_Silenced_02.txt" has 5498 lines of code... I understand the 56 paths, but what are the other 5442 lines about?   
I mean, what is important and how do you know stuff like this:
Vosvoy wrote: [...] put the speed of this sample at -60 in Audacity.

Here:

Wave ebx/sound/weapons/shared_content/hifi_oneshot/hifi_revolver_wave/8cac79083715480ad77264b7c25229c8
BasePitch 0.600000023842
    Loop LtNone
    ShuffleSegments False
    Plugins::array*

I decided a long time ago to mess around with BF3 sounds and I found this conclusion:

+/- 0.10 Ebx BasePitch points = +/- 10 speed points in Audacity

E.g:
> BasePitch: 1.00 = default.
> BasePitch: 0.60 = -40 speed points in Audacity [0.60 (ebx base pitch) - 1.00 (default base pitch) = -0.40]. 
> BasePitch: 2.00 = +200 speed points in Audacity.
> BasePitch: 1.10 = +10 speed points in Audacity. 
> BasePitch: 0.80 = -20 speed points in Audacity.
Etc...                     

I don't speak english so I don't even know how to explain all this thing, but I have one last advice for you.

Don't even try to understand the whole ebx mumbo jumbo. The most important things are "BasePitch" points and "Wave ebx/sound/..." directories. That's all.

EDIT: I corrected a few things.
## Post #144
- Username: manavortex
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 26, 2019 6:36 am
- Post datetime: 2019-12-13T11:06:01+00:00
- Post Title: Re: Frostbite 2 sound extraction research

I've tweaked the python script a little. It will ask for game and extraction paths, if those have not been set, and check if the directories are valid.

[https://1drv.ms/u/s!Ahb8fw3iR21phWlB2iI ... n?e=Y9qbT6](https://1drv.ms/u/s!Ahb8fw3iR21phWlB2iI22-dZBVRn?e=Y9qbT6)
## Post #145
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-12-13T17:28:49+00:00
- Post Title: Re: Frostbite 2 sound extraction research

> Reply from manavortex ↑Fri Dec 13, 2019 7:06 pm at Fri Dec 13, 2019 7:06 pm
>
> 
I've tweaked the python script a little.
Just out of curiosity, was modified to do what exactly? Anything more specific?
Also, what is wrong with the following, because it is more complete than anything else there is out there, above included, which have become fully obsolete.
[https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)
Will save you lots of headache.
