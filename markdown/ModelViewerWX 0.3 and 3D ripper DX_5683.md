## Post #1
- Username: Giganova
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 31, 2010 5:01 am
- Post datetime: 2011-01-01T19:57:16+00:00
- Post Title: ModelViewerWX 0.3 and 3D ripper DX

So i found a way too Dump KH2 files with ModelViewer and 3D ripper DX.

Problem is, when i import them into 3DS max, the quality of the model (not texture) is realy low and not smoot at all.



Can sombody help me?
## Post #2
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2011-01-01T21:20:02+00:00
- Post Title: ModelViewerWX 0.3 and 3D ripper DX

You will probably find its the same quality, just the amount of smoothing has been turned down ( it looks like its in FLAT SHADED mode). DXripper always seems to drop the smoothing angle to a really low number, you will need to increase that.  If i remember correctly, DXripper sets it at around 35°, you need to raise the smoothing angle to about 65° - 89.5° it should be found in the materials panel somewhere ( sorry MAX isnt my chosen app of choice so i dont know it all that well ) that should remove all those sharp edges and smooth out the corners.
## Post #3
- Username: Giganova
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 31, 2010 5:01 am
- Post datetime: 2011-01-01T21:46:09+00:00
- Post Title: ModelViewerWX 0.3 and 3D ripper DX

> Reply from Nobby
>
> You will probably find its the same quality, just the amount of smoothing has been turned down ( it looks like its in FLAT SHADED mode). DXripper always seems to drop the smoothing angle to a really low number, you will need to increase that.  If i remember correctly, DXripper sets it at around 35°, you need to raise the smoothing angle to about 65° - 89.5° it should be found in the materials panel somewhere ( sorry MAX isnt my chosen app of choice so i dont know it all that well ) that should remove all those sharp edges and smooth out the corners.

Thank you, but i can't find anything about a smoothing angle in 3DS max or on Internet

EDIT: nvm, welding the Meshes together did the job

EDIT AGAIN: after exporting, it got low quality again
## Post #4
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2011-01-01T23:31:35+00:00
- Post Title: ModelViewerWX 0.3 and 3D ripper DX

Stick with it, the answer will come eventually. There HAS to be an option SOMEWHERE to allow you to adjust the amount of smoothing.
Other wise everything created in MAX would either be always smooth or always flat shaded. 
This sort of thing couldnt happen if you didint have smoothing values.
 two objects exactly the same but with different amounts of smoothing applied.
I actually created those in another app and imported them, but it was just to show that it has to be possible to have different smoothing amounts other wise what id done, couldnt be done     if you see what i mean..
So stick with it, the answer will be out there, just i don't know what it is    As i said MAX isnt my app of choice, i only use it for ripping and converting to other formats. i do all my 3d work in Lightwave.
## Post #5
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2011-01-02T03:47:07+00:00
- Post Title: ModelViewerWX 0.3 and 3D ripper DX

[SMOOTHING GROUPS](http://www.youtube.com/watch?v=-Iswm1xKtGs)
