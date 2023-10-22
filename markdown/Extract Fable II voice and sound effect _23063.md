## Post #1
- Username: Prophetjuhh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 26, 2020 7:32 am
- Post datetime: 2020-11-26T09:31:59+00:00
- Post Title: Extract Fable II voice and sound effect ?

Hello everyone,

Fable II is one of my favorite game and I would like to extract the game sound (like the vocal, sound effect etc )
Is it possible ?

I have the .ISO and and a .dvd format of the game but I don't know how to extract the files from them. (I'm a big noob at this)
I have a Fable2BNKExtract but it doesn't work, same with quickbms (error in src\file.c line 557: fdnum_open()
Error: No such file or directory)

I hope you can help me   

Thanks.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-26T12:38:56+00:00
- Post Title: Extract Fable II voice and sound effect ?

> same with quickbms (error in src\file.c line 557: fdnum_open() Error: No such file or directory)
To know how to use quickbms, you should read documentation here [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)
From the error description, it seems that you haven't provided required archive (or index file etc.) for extraction

> I have a Fable2BNKExtract but it doesn't work
To use this tool, you need to provide BNK archive in command line like this:

```
Fable2BNKExtract -e <archivename.bnk>
```


But you need to extract this archive from ISO first.
Try to google it up [https://www.google.com/search?client=fi ... ox+360+iso](https://www.google.com/search?client=firefox-b-d&q=how+to+extract+xbox+360+iso)

You can use this for example [https://digiex.net/threads/xbox-360-xis ... -ftp.9711/](https://digiex.net/threads/xbox-360-xiso-extract-best-an-easiest-xdg3-extraction-tool-with-gui-ftp.9711/)
## Post #3
- Username: Prophetjuhh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 26, 2020 7:32 am
- Post datetime: 2020-11-26T13:47:12+00:00
- Post Title: Extract Fable II voice and sound effect ?

Hey ! 
Thanks a lot for your help ! 

I used the Fable2BNKExtract to extract some sound (wav) it works well  but I can't play the song...

So I used RExplorer to extract the XMA from the wav file, how can I make it works like a real wav now ?

I have tried to use XMA_transform script with quickbms it recognise the XMA file but give me an error at the end :

```
operable program or batch file.
Info:  algorithm   198
       offset      00000000
       input size  0x0008c800 575488
       output size 0x0008c800 575488
       result      0xffffffff -1
Error: the uncompressed data (-1) is bigger than the allocated buffer (575488)
       It usually means that data is not compressed or uses another algorithm
Last script line before the error or that produced the error:
  1312 clog MEMORY_FILE2 0 SIZE SIZE MEMORY_FILE # from mem [to temp] to mem2
```


What's wrong ? Should I use another alternative ?
I'm trying to convert the XMA file into wav with the RExplorer but nothing happens.

I thing i'm going wrong with quickbms I read the guide but I don't see where is my mistake, I'm sorry again as I said i'm a beginner 

Thanks for your answer.
## Post #4
- Username: Prophetjuhh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 26, 2020 7:32 am
- Post datetime: 2020-11-26T15:13:21+00:00
- Post Title: Extract Fable II voice and sound effect ?

Ok, I found a way to open it with vgmstream software !

For the moment I can only listen to it but can I extract the song in wav with vgmstream ?
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-26T20:09:22+00:00
- Post Title: Extract Fable II voice and sound effect ?

> can I extract the song in wav with vgmstream ?
Yes, you can use Foobar + vgmstream plugin for that
[https://www.foobar2000.org/download](https://www.foobar2000.org/download)
## Post #6
- Username: Prophetjuhh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 26, 2020 7:32 am
- Post datetime: 2020-11-26T21:24:33+00:00
- Post Title: Extract Fable II voice and sound effect ?

Thanks a lot, you are awesome
