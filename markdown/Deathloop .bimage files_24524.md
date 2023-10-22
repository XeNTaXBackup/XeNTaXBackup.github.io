## Post #1
- Username: mariachiscalpi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 20, 2021 3:53 am
- Post datetime: 2021-09-23T16:28:29+00:00
- Post Title: Deathloop .bimage files

Hey!

I spent some time snooping around the forum looking for means of converting the .bimage files I extracted from Deathloop using QuickBMS, and while I have managed to find scripts meant to aid in the conversion of the aforementioned file type in [RAGE,](https://forum.xentax.com/viewtopic.php?f=18&t=17736) [The Old Blood](https://forum.xentax.com/viewtopic.php?f=18&t=12853) or [The Evil Within 2,](https://forum.xentax.com/viewtopic.php?f=35&t=17407) none of them seem to work for the .bimage files specific to Deathloop. Needless to say, I'd greatly appreciate any and all help in streamlining the process for converting these texture files to a more palatable extension.

[Here's](https://drive.google.com/drive/folders/1fEK7MS_5ZmdckRqByvIQ8Esn7bEesBag?usp=sharing) a Google Drive link to a few of them. Do let me know should you need me to upload anything else to figure it out. Cheers!
## Post #2
- Username: wully
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 30, 2021 7:23 am
- Post datetime: 2021-09-30T17:10:28+00:00
- Post Title: Deathloop .bimage files

Looking for help with this also. I've pulled out the 3d models, but I just need the slab textures

I tried running the Dishonored2_tex.exe directly. It wouldn't pick up the bimage files. Renaming them to bimage7 got the converter to read them but it says they are in an unknown format. Are Deathloops files bimage 6 or 7?

```
Dishonored 2: Texture Converter v1.03 by Volfin

Converting ./\slab_curves_01_d.bimage7 ( 1 / 3 )
  - Unknown Format 6 - 1
Converting ./\slab_curves_01_n.bimage7 ( 2 / 3 )
  - Unknown Format 4 - 1
Converting ./\slab_curves_01_p.bimage7 ( 3 / 3 )
  - Unknown Format 5 - 1
```
## Post #3
- Username: cidqu
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 29, 2021 11:36 pm
- Post datetime: 2021-10-01T11:31:02+00:00
- Post Title: Deathloop .bimage files

Hi, I was translating Deathloop. Thanks to 'ikskoks' I managed to paste data from .decl files. But I got something different, Turkish Language has some different characters than the normal Latin Alphabet (ışöçüğ) and Deathloop Fonts don't support this. I want to change the font but couldn't manage to extract .bimage files. Can anyone help, please? I left an example.
[64_df.zip](https://xentaxbackup.github.io/file/20928_64_df.zip)
## Post #4
- Username: CrazyHairGuy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 11, 2020 2:24 pm
- Post datetime: 2021-10-02T04:07:33+00:00
- Post Title: Deathloop .bimage files

> Reply from wully ↑Fri Oct 01, 2021 1:10 am at Fri Oct 01, 2021 1:10 am
>
> 
Looking for help with this also. I've pulled out the 3d models, but I just need the slab textures

I tried running the Dishonored2_tex.exe directly. It wouldn't pick up the bimage files. Renaming them to bimage7 got the converter to read them but it says they are in an unknown format. Are Deathloops files bimage 6 or 7?
Code: Select allPS F:\Development\Games\Deathloop\generated\model\models\equipment\slabs\texture> .\Dishonored2_tex.exe ./ .\output\
Dishonored 2: Texture Converter v1.03 by Volfin

Converting ./\slab_curves_01_d.bimage7 ( 1 / 3 )
  - Unknown Format 6 - 1
Converting ./\slab_curves_01_n.bimage7 ( 2 / 3 )
  - Unknown Format 4 - 1
Converting ./\slab_curves_01_p.bimage7 ( 3 / 3 )
  - Unknown Format 5 - 1

As far as I can gather, the Deathloop .bimages are a new version/revision that have only been used in Deathloop so far, so someone would have to do some poking around in the files themselves and figure out the differences between them and the older versions, and then update the .bimage converter.
## Post #5
- Username: kidaXV
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 26, 2019 12:26 pm
- Post datetime: 2021-10-17T10:24:46+00:00
- Post Title: Deathloop .bimage files

I'm new to this but I managed to create a rough python script that can convert a handful of compression types from .bimage to .dds. It seems to work for UI and model skins now, although there might be some compression types it doesn't handle.

I was able to figure out the addresses of the image size via 010 editor (using the [template from here](https://zenhax.com/viewtopic.php?f=9&t=15900) as a guideline), and knew from Dishonored 2 images that they used DXT5. I also used [rawtexcmd](https://zenhax.com/viewtopic.php?t=7099) to test this out and figure out what kind of "magic header" to add to these files to make them readable as DDS.

```
import binascii
import os
import struct

"""
Scuffed python script to convert Deathloop .bimage files to .dds

Usage: 
`python bimage.py <file.bimage>` - Makes a best attempt at generating file.bimage.dds

`python bimage.py <directory>` - Will attempt to convert images in directory, and act recursively on all subdirectories
"""

parser = argparse.ArgumentParser()
parser.add_argument('file', help='.bimage file or directory to convert. Works recursively for directories.')

ext = '.bimage'
ext_mip0 = '_mip0'

size_int_bytes = 4
size_long_bytes = 8
heighttomipmapstart = 47
dds_header_height_offset = 12

compchar_to_header = {
    # BC1 (DXT1)
    14: 'RERTIHwAAAAHEAAAAAQAAAAEAAAAAAgAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFhUMQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=',
    # BC3 (DXT5)
    16: 'RERTIHwAAAAHEAAAAAEAAAABAAAAAAEAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFhUNQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==',
    # BC4 (ATI1)
    17: 'RERTIHwAAAAHEAAAAAEAAAABAAAAgAAAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAAQVRJMQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=',
    # (DX10)
    18: 'RERTIHwAAAAHEAAAAAQAAAAEAAAAABAAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFgxMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABUAAAAAwAAAAAAAAABAAAAAAAAAA==',
    # (DX10)
    19: 'RERTIHwAAAAHEAAAAAEAAAABAAAAAAEAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFgxMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABfAAAAAwAAAAAAAAABAAAAAAAAAA==',
    # BC7 (DX10)
    20: 'RERTIHwAAAAHEAAAcAgAAAAPAAAAkH4AAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFgxMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABiAAAAAwAAAAAAAAABAAAAAAAAAA=='
}

buffersize = 2048

def bytesToInt(b):
    return struct.unpack('<I', b)[0]

def getDdsHeader(compchar, height, width, area):
    if compchar in compchar_to_header:
        header = bytearray(binascii.a2b_base64(compchar_to_header[compchar]))
        struct.pack_into('<III', header, dds_header_height_offset, height, width, area)
        return header
    else:
        print('unknown compression format! ', compchar)
        return None

def processFile(file):
    outputFileName = file[:-len(ext)] + '.dds'
    with open(file, 'rb') as bimageFile:
        bimageFile.read(size_long_bytes) # id
        compcharBytes = bimageFile.read(size_int_bytes) # determine dxt format
        compchar = struct.unpack('<I', compcharBytes)[0]
        bimageFile.read(size_int_bytes) # unknown
        bimageFile.read(size_int_bytes) # unknown
        bimageFile.read(size_int_bytes) # width
        bimageFile.read(size_int_bytes) # height

        width = bytesToInt(bimageFile.read(size_int_bytes))
        height = bytesToInt(bimageFile.read(size_int_bytes))
        area = width * height

        header = getDdsHeader(compchar, height, width, area)
        if header == None:
            print('{}: unable to generate header'.format(file))
            return False

        with open(outputFileName, 'wb') as outFile:
            outFile.write(header)
            # Determine whether to read from here or a separate mipmap file
            mipFile = file + ext_mip0
            if not os.path.exists(mipFile):
                bimageFile.read(heighttomipmapstart) # skip to beginning of first mipmap
                buffer = bimageFile.read(buffersize)
                while buffer:
                    outFile.write(buffer)
                    buffer = bimageFile.read(buffersize)
            else:
                # Copy from mipmap file
                with open(mipFile, 'rb') as mip:
                    buffer = mip.read(buffersize)
                    while buffer:
                        outFile.write(buffer)
                        buffer = mip.read(buffersize)
    return True

def processDir(dir):
    numProcessed = 0
    numSuccess = 0
    for root, _, files in os.walk(dir):
        for file in files:
            if file.endswith(ext):
                numProcessed += 1
                if processFile(os.path.join(root, file)):
                    numSuccess += 1
    print('{}/{} bimage files converted to dds.'.format(numSuccess, numProcessed))

def main():
    args = parser.parse_args()
    if os.path.isdir(args.file):
        processDir(args.file)
    elif os.path.isfile(args.file):
        if args.file.endswith(ext):
            if processFile(args.file):
                print('1 bimage file converted to dds.')
            else:
                print('unable to convert.')
        else:
            print('please use a .bimage file.')
    else:
        print('no eligible file or directory found')

if __name__ == "__main__":
    main()
```


Edit: Updated to handle dx10 images
Edit 2: Updated to handle more images
Edit 3: Updated to handle more images
[Google Drive link](https://drive.google.com/drive/folders/1H1-kaDPgnF7xCvuBy_RTXJSNKGPtvuF9) with some of the interesting textures
[outfits_j_a01_01_is.bimage.png](https://xentaxbackup.github.io/file/21035_outfits_j_a01_01_is.bimage.png)
## Post #6
- Username: coffeeastronaut
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 19, 2021 1:06 pm
- Post datetime: 2021-12-19T20:59:48+00:00
- Post Title: Deathloop .bimage files

Pardon me for a dumb question, this is my first time doing anything like this- for the python code, how do you input the location of the files to use? I’ve tried everything I can figure out on my own, but I can’t seem to get anything beyond the same error message over and over (the following arguments are required: file) which I assume has something to do with what I’m doing. Help!
## Post #7
- Username: kidaXV
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 26, 2019 12:26 pm
- Post datetime: 2021-12-20T04:23:48+00:00
- Post Title: Deathloop .bimage files

> Reply from coffeeastronaut ↑Mon Dec 20, 2021 4:59 am at Mon Dec 20, 2021 4:59 am
>
> 
Pardon me for a dumb question, this is my first time doing anything like this- for the python code, how do you input the location of the files to use? I’ve tried everything I can figure out on my own, but I can’t seem to get anything beyond the same error message over and over (the following arguments are required: file) which I assume has something to do with what I’m doing. Help!

Hi! It sounds like you just need to provide the script with the path to the file or directory you'd like to convert. Assuming you're using windows, this article explains a bit about how file paths work: [https://docs.microsoft.com/en-us/dotnet ... th-formats](https://docs.microsoft.com/en-us/dotnet/standard/io/file-path-formats)

For instance, if you saved the script as "bimage.py", and that script is at the top level of the directory where you extracted the deathloop files, you could invoke it in the command line with 
```
python bimage.py generated\image\models\guis\loading_screens
```
 where "generated\image\models\guis\loading_screens" is the relative path from the script to a directory that contains all the loading screens.

An absolute path would also work, such as 
```
python bimage.py C:\Users\kida\Documents\deathloopfiles\generated\image\models\guis\knowledge_images\mem_know_antenna_wakeup_game_is.bimage
```

(to invoke on a single file) or 
```
python bimage.py C:\Users\kida\Documents\deathloopfiles\generated\image\models\guis\knowledge_images\
```
 (to invoke on a directory)
## Post #8
- Username: coffeeastronaut
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 19, 2021 1:06 pm
- Post datetime: 2021-12-20T16:25:45+00:00
- Post Title: Deathloop .bimage files

Oh, that’s exactly it! Thank you so much!
## Post #9
- Username: DV9 x Drillz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 08, 2020 11:10 pm
- Post datetime: 2021-12-25T16:07:41+00:00
- Post Title: Deathloop .bimage files

> Reply from kidaXV ↑Sun Oct 17, 2021 6:24 pm at Sun Oct 17, 2021 6:24 pm
>
> 
I'm new to this but I managed to create a rough python script that can convert a handful of compression types from .bimage to .dds. It seems to work for UI and model skins now, although there might be some compression types it doesn't handle.

I was able to figure out the addresses of the image size via 010 editor (using the template from here as a guideline), and knew from Dishonored 2 images that they used DXT5. I also used rawtexcmd to test this out and figure out what kind of "magic header" to add to these files to make them readable as DDS.
Code: Select allimport argparse
import binascii
import os
import struct

"""
Scuffed python script to convert Deathloop .bimage files to .dds

Usage: 
`python bimage.py <file.bimage>` - Makes a best attempt at generating file.bimage.dds

`python bimage.py <directory>` - Will attempt to convert images in directory, and act recursively on all subdirectories
"""

parser = argparse.ArgumentParser()
parser.add_argument('file', help='.bimage file or directory to convert. Works recursively for directories.')

ext = '.bimage'
ext_mip0 = '_mip0'

size_int_bytes = 4
size_long_bytes = 8
heighttomipmapstart = 47
dds_header_height_offset = 12

compchar_to_header = {
    # BC1 (DXT1)
    14: 'RERTIHwAAAAHEAAAAAQAAAAEAAAAAAgAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFhUMQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=',
    # BC3 (DXT5)
    16: 'RERTIHwAAAAHEAAAAAEAAAABAAAAAAEAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFhUNQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==',
    # BC4 (ATI1)
    17: 'RERTIHwAAAAHEAAAAAEAAAABAAAAgAAAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAAQVRJMQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=',
    # (DX10)
    18: 'RERTIHwAAAAHEAAAAAQAAAAEAAAAABAAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFgxMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABUAAAAAwAAAAAAAAABAAAAAAAAAA==',
    # (DX10)
    19: 'RERTIHwAAAAHEAAAAAEAAAABAAAAAAEAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFgxMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABfAAAAAwAAAAAAAAABAAAAAAAAAA==',
    # BC7 (DX10)
    20: 'RERTIHwAAAAHEAAAcAgAAAAPAAAAkH4AAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAEAAAARFgxMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABiAAAAAwAAAAAAAAABAAAAAAAAAA=='
}

buffersize = 2048

def bytesToInt(b):
    return struct.unpack('<I', b)[0]

def getDdsHeader(compchar, height, width, area):
    if compchar in compchar_to_header:
        header = bytearray(binascii.a2b_base64(compchar_to_header[compchar]))
        struct.pack_into('<III', header, dds_header_height_offset, height, width, area)
        return header
    else:
        print('unknown compression format! ', compchar)
        return None

def processFile(file):
    outputFileName = file[:-len(ext)] + '.dds'
    with open(file, 'rb') as bimageFile:
        bimageFile.read(size_long_bytes) # id
        compcharBytes = bimageFile.read(size_int_bytes) # determine dxt format
        compchar = struct.unpack('<I', compcharBytes)[0]
        bimageFile.read(size_int_bytes) # unknown
        bimageFile.read(size_int_bytes) # unknown
        bimageFile.read(size_int_bytes) # width
        bimageFile.read(size_int_bytes) # height

        width = bytesToInt(bimageFile.read(size_int_bytes))
        height = bytesToInt(bimageFile.read(size_int_bytes))
        area = width * height

        header = getDdsHeader(compchar, height, width, area)
        if header == None:
            print('{}: unable to generate header'.format(file))
            return False

        with open(outputFileName, 'wb') as outFile:
            outFile.write(header)
            # Determine whether to read from here or a separate mipmap file
            mipFile = file + ext_mip0
            if not os.path.exists(mipFile):
                bimageFile.read(heighttomipmapstart) # skip to beginning of first mipmap
                buffer = bimageFile.read(buffersize)
                while buffer:
                    outFile.write(buffer)
                    buffer = bimageFile.read(buffersize)
            else:
                # Copy from mipmap file
                with open(mipFile, 'rb') as mip:
                    buffer = mip.read(buffersize)
                    while buffer:
                        outFile.write(buffer)
                        buffer = mip.read(buffersize)
    return True

def processDir(dir):
    numProcessed = 0
    numSuccess = 0
    for root, _, files in os.walk(dir):
        for file in files:
            if file.endswith(ext):
                numProcessed += 1
                if processFile(os.path.join(root, file)):
                    numSuccess += 1
    print('{}/{} bimage files converted to dds.'.format(numSuccess, numProcessed))

def main():
    args = parser.parse_args()
    if os.path.isdir(args.file):
        processDir(args.file)
    elif os.path.isfile(args.file):
        if args.file.endswith(ext):
            if processFile(args.file):
                print('1 bimage file converted to dds.')
            else:
                print('unable to convert.')
        else:
            print('please use a .bimage file.')
    else:
        print('no eligible file or directory found')

if __name__ == "__main__":
    main()

Edit: Updated to handle dx10 images
Edit 2: Updated to handle more images
Edit 3: Updated to handle more images
Google Drive link with some of the interesting textures

Hey Kida, I used this script and sucessfully converted some .bimage files to .dds. But when I open a file in gimp and I get an error message saying "DDS image message: Unsupported DXGI Format (98)". When I try open it in paint.net the I get an error message saying "There was an error reading media from file". Do you have any idea what could be causing this?

Update: I've solved my issue, if you are having the same issue as me, this is how i solved it. 

Currently, the bms script for Deatloop crashes when it tries to extract a few files, so does not finish extracting everything else. This meant I did not have all the .bimage files (.bimage_MIP) necessary to generate a full DDS Image. Luckily, or Unluckily if the files that cause the crash are the files you want, if you separate the .resource file you want with the master_resource.index file and run the bms it will fully unpack the .resource file. I did this and I now had all the files necessary to generate the DDS image. Now, all you have to do is run the bimage.py script and you have your DDS.

If you do not do this and try to generate a DDS using the only bimage that extracts then you will not be able to open it in GIMP, Paint.NET or whatever it is you're using. I spent days trying to see if my image editing programs had the right DDS plugin and editing the files using a hex editor to try and make it work
