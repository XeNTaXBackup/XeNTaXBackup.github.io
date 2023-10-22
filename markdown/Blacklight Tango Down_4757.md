## Post #1
- Username: s6xy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 16, 2010 1:50 am
- Post datetime: 2010-07-15T18:26:01+00:00
- Post Title: Blacklight: Tango Down

I did check and attempt to do the following;

[viewtopic.php?f=17&t=3477](http://forum.xentax.com/viewtopic.php?f=17&t=3477)
[viewtopic.php?f=10&t=4284](http://forum.xentax.com/viewtopic.php?f=10&t=4284)

And another thread, neither solutions worked on this game's files.

The errors I was given on my attempt to use the quickBMS file:

Common.bnk

> offset   filesize   filename
>
> ------------------------------
>
>   00001240 3559915520 Common_-1667559168.wav
>
> 
>
> Error: the requested amount of bytes to allocate is negative (-735051776)
And more relevant to the file linked below;

> offset   filesize   filename
>
> ------------------------------
>
>   00000080 540934400  Nade_EMP_-1168890365.wav
>
> 
>
> Error: incomplete input file number 0, can't read 540406920 bytes.
>
>        anyway don't worry, it's possible that the BMS script has been written
>
>        to exit in this way if it's reached the end of the archive so check it
>
>        or contact its author or verify that all the files have been extracted

They are using Wwise audio streaming, and the CookedPCConsole folder contains .bnk files, linked a few files that might be able to help you guys find me a solution!

[http://lslcabi.net/bl/SoundbanksInfo.xml](http://lslcabi.net/bl/SoundbanksInfo.xml)
[http://lslcabi.net/bl/Init.bnk](http://lslcabi.net/bl/Init.bnk)
[http://lslcabi.net/bl/WwiseTest.bnk](http://lslcabi.net/bl/WwiseTest.bnk)
[http://lslcabi.net/bl/Nade_EMP.bnk](http://lslcabi.net/bl/Nade_EMP.bnk)
