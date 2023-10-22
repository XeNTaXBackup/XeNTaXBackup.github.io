## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-05T18:04:19+00:00
- Post Title: Noesis tutorial Zlib

In this tutorial ill go over how to load a file format that uses zlib compression directly in noesis.
The game is a free to play mmo called Rise of Immortals [http://www.riseofimmortals.com/](http://www.riseofimmortals.com/)
This code also works on other Petroglyph games using the alo format.
Download the client for free for a sample of your own
Ok in this particular format the file contains one zlib chunk that needs to be decompressed to gain access to the model
They only give us the compressed size and a constant offset the data starts at.
So the format of these alo files is
Bytes 01 - 16 #Header Information
Bytes 17 - 20 #Compressed size
Offset 36 #Start of zlib data

So knowing this we can use this code here to get the raw file in memory to work with

```
def noepyLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    bs.seek(16, NOESEEK_ABS)
    compsize = bs.read("i")
    bs.seek(36, NOESEEK_ABS)
    decompData = bytearray()
    cmpData = bs.readBytes(compsize[0])
    decompSize = rapi.getInflatedSize(cmpData)
    decompData += rapi.decompInflate(cmpData, decompSize)
    bs.seek(0, NOESEEK_ABS)
    bs = NoeBitStream(decompData, NOE_LITTLEENDIAN)
```

So what are we doing here
We create a context with
ctx = rapi.rpgCreateContext()
Then we open our byte stream
bs = NoeBitStream(data)
Then We get the compressed size of the zlib chunk

```
compsize = bs.read("i")
```

Now we setup a place to hold our new byte stream pieces "you only need to do this if you want to add multiple streams together but it will also work for one stream "

```
decompData = bytearray()
```

Now we store our compressed chunk

```
cmpData = bs.readBytes(compsize[0])
```

Then we get the uncompressed size of that chunk with this command

```
decompSize = rapi.getInflatedSize(cmpData)
```

Now we add our uncompressed data to our container we did earlier

```
decompData += rapi.decompInflate(cmpData, decompSize)
```

We Now go back to the start of the file because we don't need any of the original header and we replace our bs with the new uncompressed model

```
bs = NoeBitStream(decompData, NOE_LITTLEENDIAN)
```

Now you can handle the model just as if it were uncompressed.
The end result

If anyone has any questions on anything done in this model format just ask.
[fmt_Rise_of_Immortals_alo.rar](https://xentaxbackup.github.io/file/4888_fmt_Rise_of_Immortals_alo.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-12-06T23:02:26+00:00
- Post Title: Noesis tutorial Zlib

thanks for the tutorial!   

> Reply from chrrox
>
> This code also works on other Petroglyph games using the alo format.
your import script doesn't seem to work with Petroglyph's "Star Wars: Empire at War" *.alo models.
here is the *.alo format spec if you're feeling up to modifying yours:
[http://modtools.petrolution.net/docs/AloFileFormat](http://modtools.petrolution.net/docs/AloFileFormat)
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-07T00:00:59+00:00
- Post Title: Noesis tutorial Zlib

sample files would be a lot better i tested it with this game and guardians of graxia.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-12-07T03:37:30+00:00
- Post Title: Noesis tutorial Zlib

here is some samples:
*samples provided on request*

thanks!
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-07T04:04:45+00:00
- Post Title: Noesis tutorial Zlib

there are already tools to import the models on that site why not use those?
[http://modtools.petrolution.net/tools/](http://modtools.petrolution.net/tools/)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-12-07T04:19:22+00:00
- Post Title: Noesis tutorial Zlib

nevermind i may write an alo import script for Noesis soon.   

edit
there is now a alo/ala import/export script for Blender 2.79 now.   
[https://focumentation.fandom.com/wiki/Blender](https://focumentation.fandom.com/wiki/Blender)
