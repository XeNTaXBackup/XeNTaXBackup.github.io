## Post #1
- Username: TuneyTunes
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 29, 2022 8:47 am
- Post datetime: 2022-09-12T16:56:54+00:00
- Post Title: Deadly Premonition (X360) .XPC and .XMD files

Hello all!
I've recently gained a lot of interest in doing texture modding DPDC PC through dpfix. My idea is to port the 360 textures to the PC port as a nice alternative to the DC visuals (I personally don't like a lot of the new icons and HUD). I took a look through this [forum](https://forum.xentax.com/viewtopic.php?f=10&t=8524&p=91653#p91653) and I've downloaded chrrox's plugin for Noesis, sadly couldn't get Finale00's code before it was removed. The plugins worked well for DPDC however, after using offzip to extract the .pkg files from the 360 release, all .XPC files gives me this error (down below) and I've been stuck since. I would try posting on that specific thread however, that one is absolutely ancient and is now part of the Game Archive topic; meaning not many will see it. If anyone could help, that would be greatly appreciated!

Here is an [.XPC file](https://www.mediafire.com/file/udy5dgxxhrnuac5/0000fd58.xpc/file) from the 360 version so you can troubleshoot yourself if you'd like to.
[KQGw3O0gMC.png](https://xentaxbackup.github.io/file/22811_KQGw3O0gMC.png)
## Post #2
- Username: TuneyTunes
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-09-12T21:33:28+00:00
- Post Title: Deadly Premonition (X360) .XPC and .XMD files

It's hard to determine the file format with only one sample. Can you upload more samples?

However for the sample you posted there is only one DDS image inside.
If you'll delete first 224 bytes in hex editor (e.g. Hex Workshop), you will be able to
save data as DDS image.
## Post #3
- Username: TuneyTunes
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 29, 2022 8:47 am
- Post datetime: 2022-09-13T00:04:13+00:00
- Post Title: Deadly Premonition (X360) .XPC and .XMD files

> Reply from ikskoks ↑Tue Sep 13, 2022 5:33 am at Tue Sep 13, 2022 5:33 am
>
> 
It's hard to determine the file format with only one sample. Can you upload more samples?

However for the sample you posted there is only one DDS image inside.
If you'll delete first 224 bytes in hex editor (e.g. Hex Workshop), you will be able to
save data as DDS image.

Thanks, I'll try that out!

[ Here are some more samples for you to try. ](https://www.mediafire.com/file/aof1qsb01w2d1i6/XPCFiles2.zip/file) I hope it's enough! If you need more, let me know.
## Post #4
- Username: TuneyTunes
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 29, 2022 8:47 am
- Post datetime: 2022-09-13T17:11:02+00:00
- Post Title: Deadly Premonition (X360) .XPC and .XMD files

So I tried what you said last night and it worked very well! I got a lot of textures I was looking for but, I did notice a few of the ones I needed were part of a larger .XPC file archive. When I tried using your method, I got only one texture and it was always the same. I took a look at DPDC's hexes and noticed they don't have "DDS |" and "DXT1" (as shown below). Here are more [samples](https://www.mediafire.com/file/fd7fgirnnszpf87/XPC3.zip/file) if you want to take a look into this yourself and see if removing those bits or more is the key to having the Noesis plugins read the file correctly. Or if there is a method of getting a specific texture from that file using the hex editor.
[GDBD5nsuXe.png](https://xentaxbackup.github.io/file/22818_GDBD5nsuXe.png)
## Post #5
- Username: TuneyTunes
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-09-13T22:11:54+00:00
- Post Title: Deadly Premonition (X360) .XPC and .XMD files

I have created a script to extract all DDS files from XPC archive
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Deadly%20Premonition/Deadly_Premonition_XPC_script.bms)

You can use it with quickbms [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

And file format description is here [http://wiki.xentax.com/index.php/Deadly_Premonition_XPC](http://wiki.xentax.com/index.php/Deadly_Premonition_XPC)

If you want to mod the game, you can use "reimport mode" in quickbms, more info here [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)
## Post #6
- Username: TuneyTunes
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 29, 2022 8:47 am
- Post datetime: 2022-09-19T03:58:49+00:00
- Post Title: Deadly Premonition (X360) .XPC and .XMD files

I'll try this out, thanks so much for all your help!
