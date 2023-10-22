## Post #1
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-07-07T00:36:39+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

Hi, for a while now I've been observing some issues with normal .dds textures extracted from Resident Evil Operation Raccoon City specifically.
For some reason in Blender and Maya, the normals seem to be displaying information not needed, making many surfaces look pixelated or blocky.


I'd really appreciate some guide on why this is happening and how to approach to fix the issue in the .dds directly (they also need some channel adjusments to avoid the "green" or "pink" look, but the problem remains with or without retouching the channels). I assume this is a technical issue in the textures extracted, since I tried for many days to fix it in different 3d softwares and render engines with no success.
## Post #2
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-07-29T01:01:55+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

bumping to offer $$ by paypal to someone who can help
## Post #3
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-08-05T20:02:32+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

Can you provide one of the normal maps?
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-11T05:55:56+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

You can't just muck with colors, you usually need to swap red and alpha and occasionally derive blue. You can use the normal swizzle Noesis script to do that. It's on the Noesis plugins google code repo: [https://code.google.com/p/noesis-plugin ... malswiz.py](https://code.google.com/p/noesis-plugins-official/source/browse/trunk/Rich/tool_normalswiz.py)
## Post #5
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-09-04T02:04:11+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

> Reply from MrAdults
>
> You can't just muck with colors, you usually need to swap red and alpha and occasionally derive blue. You can use the normal swizzle Noesis script to do that. It's on the Noesis plugins google code repo: https://code.google.com/p/noesis-plugin ... malswiz.py

Thank you for the response, I tried it and the normals improved dramatically, and I thought they looked good already in level zones.

I'm not very familiar with Noesis, but I read that the rapi module is provided by Noesis natively, right? Is there a way I can read that module to try to port rapi.imageNormalSwizzle to my script for a blender importer? 

Regards

edit: I also couldn't find the debug log/console in the latest version, nor how to enable it, am I missing something?
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-05T14:15:25+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

The noesis and rapi modules are implemented natively in Noesis. So you can't directly import them in a blender script.

noesis.logPopup()
## Post #7
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-09-06T00:50:36+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

I see, what I was asking for is just to read those modules to learn from them if you allow it. Actually implementing your algorithms to python-blender compatible would require quite some work maybe, so far I learned a lot transfering quick bms scripts to blender and was fun. 

If you know any image swizzler algorithm/info I can look at it will be appreciated too.

Thanks and regards!
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-06T03:03:24+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

Just swap the red and alpha channels of the image, scale and bias into vector space (0-255 to -1.0-1.0), then determine blue's contribution by subtracting the length of r+g from 1. (since you know the end result is a unit vector) Sometimes games will also store r+g biased, such that when you set blue to 1.0 and normalize you will end up with the correct normal. (this is common because the normal is in tangent space which means it will always revolve around z and can easily be clamped)

It will be about 10 times slower when you do it in Python.
## Post #9
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-09-19T22:51:54+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

Hey, thanks a lot Rich, you make it sound as an easy task, so I'll start investigating image manipulation and the DTX5 format.
I assume that Noesis is not open suource then.

Probably it will take me some time to do my own image swizzler in python, so I tried to modify the plugin to modify all the files given in an array, but it always end up creating only one. I'll investigate more and post it here to see why is not working.

An image swizzler batch would be much more useful specially for level zones, where I have like 2000 wrong normal textures.

Regards!
## Post #10
- Username: Bastien
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-20T01:48:19+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

Parts of it are, there might be some public plugin code that does exactly what that function does floating around. You should be able to write some code based on what I just said, though. 

If you want to run a Noesis script on a bunch of files, you write a script to handle it specifically, and invoke it from a .bat file like:

Noesis.exe ?runtool "Unswizzle normals" "C:\textures\myswizzlednormal.dds"

In that case you'd just have a tool script named "Unswizzle normals" and you could save the unswizzled image right back out to the source name provided in the script itself. Then you can use one of the many programs in existence intended for batch processing to generate a .bat using that tool command for all files in a folder or whatever.

The ?runtool stuff is pretty untested, I just hacked it in not too long ago for batch jobs just like that one where I want to write a quick Noesis tool script to process something in bulk.
## Post #11
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-09-23T02:11:37+00:00
- Post Title: [SOLVED] Blocky normal textures in render/viewport (.dds)

1900 textures processed in 40 minutes, worked like a charm! thanks again.
The only tricky part was realizing that the file path in the .bat was feeding noesis.getSelectedFile() and not the function arguments (I first tried to remove toolIndex, then adding another argument, but didn't work)
So, I just modified image swizzler like this

```
srcName = noesis.getSelectedFile()

#dstName = noesis.userPrompt(noesis.NOEUSERVAL_SAVEFILEPATH, "Save Image", "Select destination path for the swizzled image.", dstDefault, None)
dstName = dstDefault

```


In case someone needs it, I got all the normal textures in the game folder to create the .bat by copying the console output from this python script (this game has all normal textures with the suffix "_n").

```
def readAllFiles(Folder,extension="",suffix=""):
    """
    Returns a list of absolute filepaths on the folder and subfolders specified, filtering by extension and suffix (optional).
    """
    import os
    filepaths = []
    
    for root, dirs, files in os.walk(Folder):
        for n in files:
            
            file= os.path.join(root,n)
            f_extension = os.path.splitext(os.path.basename(file))[1]
            f_suffix = os.path.splitext(os.path.basename(file))[0][-2:]
            
            
            if extension == "" and suffix =="":
                filepaths.append(file)
            
            elif extension !="" and suffix =="" and f_extension == extension:
                filepaths.append(file)
                
            elif extension =="" and suffix !="" and f_suffix == suffix:
                filepaths.append(file)
            
            elif extension !="" and suffix !="" and f_suffix == suffix and f_extension == extension:
                filepaths.append(file)
    

    return filepaths

        
files = readAllFiles(r"D:\Game_Folder",".dds","_n")

#Could also write the .bat directly, this is for copying the console output to a .bat
for n in files:
    print ('Noesis.exe ?runtool "&Normal swizzler Batch" "' + n + '"')

print (len(files))

```


Cheers
