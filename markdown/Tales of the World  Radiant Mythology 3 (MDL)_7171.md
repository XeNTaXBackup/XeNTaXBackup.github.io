## Post #1
- Username: DeltaBlade
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 12, 2011 1:17 pm
- Post datetime: 2011-08-13T01:39:00+00:00
- Post Title: Tales of the World : Radiant Mythology 3 (MDL?)

I have found some files inside the "namco.bdi" from the Tales game which I believe they are texture files (*.ppt) and model files (*.mdl). I am saying this because I can't seems to find any GMO files, and the MDL files contains texts such as Bip01 and blah.

Link to extracted samples: [http://dl.dropbox.com/u/22930686/files/temp.zip](http://dl.dropbox.com/u/22930686/files/temp.zip)

Anyone want to play with it feel free to try it out. I will try to understand them but I am still a complete noob at binary files.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-13T01:53:32+00:00
- Post Title: Tales of the World : Radiant Mythology 3 (MDL?)

How did you extract them? (so I can compare with more files)
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-13T02:34:42+00:00
- Post Title: Tales of the World : Radiant Mythology 3 (MDL?)

> Reply from finale00
>
> How did you extract them? (so I can compare with more files)well maybe this can help you.
[Namco BDI Tool by CriticalError.rar](https://xentaxbackup.github.io/file/4622_Namco BDI Tool by CriticalError.rar)
## Post #4
- Username: DeltaBlade
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 12, 2011 1:17 pm
- Post datetime: 2011-08-13T07:28:03+00:00
- Post Title: Tales of the World : Radiant Mythology 3 (MDL?)

Well I extract the files manually 

I looked at the bdi file and find some data with 'EZBIND'. I took the chunk out and run it with quickBMS with this script below written by someone in the XentaX forum.

```
idstring "EZBIND\0\0"
get FILES long
get DUMMY long
for i = 0 < FILES
    get NAME_OFF long
    get SIZE long
    get OFFSET long
    get CRC long

    savepos TMP
    goto NAME_OFF
    get FNAME string
    goto TMP

    get NAME basename
    string NAME += /
    string NAME += FNAME

    clog NAME OFFSET SIZE SIZE
next i

```


@CriticalError : The tool seems very promising. I'll give it a try
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-13T12:28:27+00:00
- Post Title: Tales of the World : Radiant Mythology 3 (MDL?)

Great script. I was wondering what to do with those EZBIND stuff
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-16T23:51:50+00:00
- Post Title: Tales of the World : Radiant Mythology 3 (MDL?)

The bdi tool only extracts sounds.
Anything that will dump all of the models..?
## Post #7
- Username: DeltaBlade
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 12, 2011 1:17 pm
- Post datetime: 2011-08-17T07:47:44+00:00
- Post Title: Tales of the World : Radiant Mythology 3 (MDL?)

I'm also hoping that someone can write a tool for it.

3 more samples : [http://dl.dropbox.com/u/22930686/files/sample.zip](http://dl.dropbox.com/u/22930686/files/sample.zip)

I notice that not all the files are extracted from the data as the ezbind data contains a mixture of compressed and decompressed data. But I think it shouldn't matter too much.

The ezbind archive contains: (I presume)
* .mdl : model files
* .ani : animations
* .ppt : PSP textures.
* .nod : node data? (already decompressed)
* .txl : texture list? (also already decompressed)

Sample of an ezbind archive I found inside the bdi ([http://dl.dropbox.com/u/22930686/files/ang000.dat](http://dl.dropbox.com/u/22930686/files/ang000.dat)). Please reply if the file is faulty.
