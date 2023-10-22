## Post #1
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2007-04-10T13:36:05+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

Hey there, let's see if you can open this files:
[http://www.megaupload.com/es/?d=FV8WCIHZ](http://www.megaupload.com/es/?d=FV8WCIHZ)

And here's something for the Mods/Admin: Please give me my ñ back, or at least put an n on my username. Thank you.
## Post #2
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-04-10T18:57:00+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

I'll like to see the file but I can't donwload from megaupload, can you upload it somewhere else?
somewhere where there is no cap per country

> And here's something for the Mods/Admin: Please give me my ñ back, or at least put an n on my username. Thank you.
lol :D
## Post #3
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2007-04-10T19:58:06+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

I said that cos my nick was before McCuñao, and not what I have now. OK, I'll attach.

I had like an 1.35MB of examples, Here's what could got into this.
[Copia de Otros.rar](https://xentaxbackup.github.io/file/1117_Copia de Otros.rar)
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-04-10T22:01:57+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

PXR it's a ELf file,  the ELF it's like .exe in windows but in GNU/Linux, in minds a executable

Both files of the example are ELF

Inside the file loading.psp.prx 

```

```


English
[http://en.wikipedia.org/wiki/Executable ... ble_Format](http://en.wikipedia.org/wiki/Executable_and_Linkable_Format)

Non english
[http://es.wikipedia.org/wiki/Executable ... ble_Format](http://es.wikipedia.org/wiki/Executable_and_Linkable_Format)
## Post #5
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2007-04-11T13:20:51+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

Thanks for the info, but that doesn't tell me how to extract/insert files.

But at least now I know that I have to find again a PS2/PSP Tim2 Reader, for the texture part. (I wanna translate the game)
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-04-11T14:04:29+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

These arent archive files with lots of gfx and stuff, these are
the files that run the game and load files, so you cannot really
extract/edit these files.

(except that i found some GIM icons in the loader exe)

but thats about it
## Post #7
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-04-11T15:28:54+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

The files you attached are executables not archives

the pxr only tell the psp what to do with the files :P

there must be other files around, probably big files that will need to be
chopped, try to look for .dat or data. something
## Post #8
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2007-04-11T17:28:56+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

You see, maybe they are execs, but it's all the files there are in the game. All prx, of similar namings. The loading.prx has the textures for the loading screen as it looks, there are more stuff there, but the big one is a data.prx, 700MB of file. That's why I'm asking about these file formats.
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-04-11T20:20:36+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

The Data.prx file is probably the archive file 

however i doubt that one is an Executable PRX file.

anyways, if you could upload a cutted version of it somewhere
it would be lots easier.

Edit: 
can someone find me a PSP GIM image reader/plugin so
i can test the validity of the rips i made.

i cant find anything by googling on that :X
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-04-12T05:51:43+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

Okay, got hold of this big data file, which was data.img , not data.prx.
anyways, almost everything in this .img file is packed.
all TIM images, scripts, GIM images are packed with something i dont recognize.

i will post examples of these later today.
[packed.zip](https://xentaxbackup.github.io/file/1120_packed.zip)
## Post #11
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-04-12T17:34:16+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

I'm not an expert on this but it looks like the files are compressed with something that uses a sliding window


The first "block" of the file ends with 0xFF - offset 13 in the I3D and 9 in the tims

All files end with 0x00

More files would be of help :)
hopefully you can find a simple text file that is compressed

Edit: From what little I could gather, the I3d seem to be a model/level or part of it at least

Has references to Nodes(scene graph?) materials and "mesh" :P
Most likely the games uses the same format for both levels and models
## Post #12
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2007-04-21T08:15:26+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

Any new progress?
## Post #13
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-04-27T19:51:23+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

without more files from the main archive I don't think much can be done..
a list of the files would be interesting though

like Strobe said, the files are compressed
without knowing what the output data should look like there isn't much that can be done, a compressed text file however should be of some help, but I don't know if there are any
## Post #14
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2007-04-28T12:01:40+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

So I have to upload more chunks of the file? How can I do that?
## Post #15
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-04-29T18:54:36+00:00
- Post Title: Ghost in the Shell: Stand Alone Complex PSP .prx

I have no idea how strobe extracted the files from the main data file but if you can do that(ask strobe for the extractor?) and look for text files, that is files that one can almost read :P like subtitle files or scripts that are compressed then post them

you will know they are compressed when they start normal and then become garble eg:

Script 0001 blabla test ***tes*** 03****

I've used '*' to mark those squares one usually sees in binary files
## Post #16
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-03-09T13:01:32+00:00
- Post Title: Re: Ghost in the Shell: Stand Alone Complex PSP .prx

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-05-16T20:12:13+00:00
- Post Title: Re: Ghost in the Shell: Stand Alone Complex PSP .prx

data.img tool[http://www.pspripkits.com/download/file.php?id=1032](http://www.pspripkits.com/download/file.php?id=1032)
## Post #18
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2011-05-16T20:15:46+00:00
- Post Title: Re: Ghost in the Shell: Stand Alone Complex PSP .prx

Works for PAL? I heard that there was some tools NTSC-only.
## Post #19
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2011-05-19T06:27:07+00:00
- Post Title: Re: Ghost in the Shell: Stand Alone Complex PSP .prx

> Reply from alon
>
> data.img toolhttp://www.pspripkits.com/download/file.php?id=1032

Thanks for the link but i have problems with the tool

"Upex doesn't recognize internal or external command"
