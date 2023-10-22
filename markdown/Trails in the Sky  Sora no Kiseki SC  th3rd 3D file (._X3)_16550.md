## Post #1
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2017-07-17T05:12:37+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

I'm not that familiar with 3D formats, so I need help to convert model files (._X3) from Sora the 3rd to .obj or .ply files.
Here's a ingame screenshot a scene that contains the model:

Another tool, called GameViewer, which is available at [https://github.com/prefetchnta/gameviewer](https://github.com/prefetchnta/gameviewer) can view, but not export as 3D model, these model files:


Here's a sample of the file + textures: [https://transfer.sh/CG9oD/sora_3rd_sample.zip](https://transfer.sh/CG9oD/sora_3rd_sample.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-17T19:32:07+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

> Reply from uyjulian
>
> Another tool, called GameViewer, [...] can view, but not export as 3D model, these model filesa viewer that doesn't have an export option?  Very funny.  

Anyways, the format appears to be simple, but there's about 721 assumed small submeshes (SMs) in the sample file.
So a script is required to gather them all.
You might try a 3D ripper on a scene loaded by that famous viewer, so that you can rip some meshes, hopefully.

I used hex2obj (view link in my sig) to get one of the bigger SMs displayed:



U7000_X3.jpg (160.43 KiB) Viewed 282 times
## Post #3
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2017-07-18T02:24:42+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

Thanks!




I think all I need to do is figure out the space between CD3DFile_Mesh and the start of the vertices data.
## Post #4
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2017-07-18T17:40:05+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

Here's my progress so far:

[https://gist.github.com/uyjulian/db43b5 ... 00bc78cfdc](https://gist.github.com/uyjulian/db43b5e19d8dde6af1f8e400bc78cfdc)

Anybody know how to map textures?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-18T19:05:55+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

well done, see you used python.

I wrote a short C program (not as short as your script  ), same result:



U7000_X3-all.jpg (179.58 KiB) Viewed 250 times


texturing, iirc goes like this: select object, create material, apply texture. (Or simply open an image in UV/Image editor.)

Since there's so many submeshes (SMs) it would make sense to create mtl files via code.
But there's 21 .png textures only which are listed at the beginning of the _X3 file. So some grouping of SMs is required, I guess.

I tried to apply U70i1104.png (books) manually but I couldn't find a fitting uv map.

U70i3804.png appears to fit nicely. So that's maybe a way to find the connection between texture and mesh(es) in the _X3 file.

```
   nValue[0]= 0; nValue[1]= 0; nValue[2]= 1; nValue[3]= 0; nValue[4]= 2; nValue[5]= 0;    // 0000 0100 0200
   do {
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 6) ;       // j is offset here
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ;
            FIaddr_arr[cnt]= j ; pFBuf -= 4 ; j -= 4 ;
            GetDW(pFBuf, j, FIcnt, false) ; FIcnt_arr[cnt]= FIcnt ;
                //fprintf( stream, "# %3d 0x%x: %d\n", cnt, FIaddr_arr[cnt], FIcnt) ;
            if (cnt<1998) cnt++ ; else { chMB("Too many submeshes!\nbreak") ; j= dwFileSize ;}
        }
        { pFBuf += 7 ; j += 7 ; }     // 
   } while ((offs2!=0)&&(j<dwFileSize)) ;
   FIaddr_arr[cnt]= dwFileSize ;        // wichtig für Endabfrage

   cntMax= cnt ; cnt= 0 ;   //
   do {
        log_FIs(stream, FIaddr_arr[cnt], minFaceInd, maxFaceInd, lastFaceInd, FIcnt_arr, cnt) ;
        addrV= FIaddr_arr[cnt] -4 - vCnt_arr[cnt] * 40 ; Vsum += vCnt_arr[cnt] ;
        fprintf( stream, "# vertex addr: 0x%x\n", addrV) ;
        log_Verts(addrV, vCnt_arr[cnt], 40) ; logUVs(addrV+32, vCnt_arr[cnt], 40) ;
        cnt++ ;
   } while (cnt<cntMax);
   fprintf( stream, "# vertex sum: %d\n", Vsum) ;
```
## Post #6
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2017-07-19T03:42:51+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

There appears to be multiple textures in a set of faces, and I have no idea which face goes with which texture.
Here's my progress so far:
[https://gist.github.com/uyjulian/db43b5 ... 00bc78cfdc](https://gist.github.com/uyjulian/db43b5e19d8dde6af1f8e400bc78cfdc)

Here's some areas of the mesh area that I can't figure out:
## Post #7
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2017-07-19T15:26:24+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

Okay, so here's another sample:
[https://transfer.sh/nu3jC/sora_3rd_2.zip](https://transfer.sh/nu3jC/sora_3rd_2.zip)


The new sample was formatted a bit differently so I adjusted my script.
[https://gist.github.com/uyjulian/db43b5 ... 00bc78cfdc](https://gist.github.com/uyjulian/db43b5e19d8dde6af1f8e400bc78cfdc)
## Post #8
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2017-07-27T04:52:34+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

Textures have been mapped!!!!

New script at [https://gist.github.com/uyjulian/db43b5 ... 00bc78cfdc](https://gist.github.com/uyjulian/db43b5e19d8dde6af1f8e400bc78cfdc)

I'll make a blender plugin later
## Post #9
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-11-04T09:34:59+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

Were you ever able to create a blender script at all?

I saw your script above but I'm a little unsure how to use it, it doesn't appear to be a python script, but a .moon script, which is a subset of LUA?

I'm a little out of my depth here though.
## Post #10
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-11-05T14:54:59+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

uyjulian,

Can you tell me which script did you use to extract the .dir/.dat files correctly?

I did try the following script on the
The Legend of Heroes Trails in the Sky SC       (2015)
The Legend of Heroes Trails in the Sky the 3rd (2017), but did not work correctly.

[http://zenhax.com/viewtopic.php?f=9&t=6 ... rails#p119](http://zenhax.com/viewtopic.php?f=9&t=60&hilit=trails#p119)


The ED6Unpacker.exe works fine.
## Post #11
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-11-06T03:03:26+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

> Reply from Karpati
>
> uyjulian,

Can you tell me which script did you use to extract the .dir/.dat files correctly?

I did try the following script on the
The Legend of Heroes Trails in the Sky SC       (2015)
The Legend of Heroes Trails in the Sky the 3rd (2017), but did not work correctly.

http://zenhax.com/viewtopic.php?f=9&t=6 ... rails#p119


The ED6Unpacker.exe works fine.

Use Falconvert from here:

[http://www.pokanchan.jp/dokuwiki/softwa ... nvrt/start](http://www.pokanchan.jp/dokuwiki/software/falcnvrt/start)

It'll also convert the textures, it just doesn't work for the stages unfortunatly.

Note: For stages the PSP and the vita version (especially vita) use .it3 files, there is a converter for those but it doesn't work correctly a lot of the time.
## Post #12
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-11-09T19:03:32+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

I got the same result also:
[X3_screen.jpg](https://xentaxbackup.github.io/file/13537_X3_screen.jpg)
## Post #13
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-11-10T01:42:40+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

> Reply from Karpati
>
> I got the same result also:

Are you using a special plugin to make that work?

Searching on the website I can't see support for the kiseki formats at all.
## Post #14
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-11-10T05:49:25+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

> Reply from lionheartuk
>
> Searching on the website I can't see support for the kiseki formats at all.

The answer is very simple: it is an unreleased v6.521. The latest released version is v6.520.
## Post #15
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-11-11T02:46:01+00:00
- Post Title: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (._X3)

> Reply from Karpati
>
> lionheartuk wrote:Searching on the website I can't see support for the kiseki formats at all.

The answer is very simple: it is an unreleased v6.521. The latest released version is v6.520.

I see.

Will the new update support the file formats for environments from Sora no Kiseki FC and SC because those aren't ._x3

The First is .X so perhaps second is ._X2, I haven't checked the second games file format just yet.
## Post #16
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-11-11T13:35:53+00:00
- Post Title: Re: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (.

> Reply from lionheartuk
>
> Will the new update support the file formats for environments from Sora no Kiseki FC and SC because those aren't ._x3

The First is .X so perhaps second is ._X2, I haven't checked the second games file format just yet.

I can't answer to your question, because I did not find any .x or .x2 files in these game's archive files.
## Post #17
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-11-12T07:38:48+00:00
- Post Title: Re: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (.

> Reply from Karpati
>
> lionheartuk wrote:Will the new update support the file formats for environments from Sora no Kiseki FC and SC because those aren't ._x3

The First is .X so perhaps second is ._X2, I haven't checked the second games file format just yet.

I can't answer to your question, because I did not find any .x or .x2 files in these game's archive files.
[https://drive.google.com/open?id=1wa6HN ... Oz7p93-7KR](https://drive.google.com/open?id=1wa6HN864pOW_wd0xW7um4VOz7p93-7KR)


Here I've uploaded them from SC and FC, i was wrong on the file extensions however, it seems like 3rd and SC use the same format, but FC uses a slightly different format.
## Post #18
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-11-12T20:22:37+00:00
- Post Title: Re: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (.

I have released the 3D Object Converter v6.521 as a web update.

How to get the 3D Object Converter v6.521:
Please download the 3D Object Converter from [http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it
or download the portable version and extract it into a folder.

Run the program and use the Help/check for updates function to get it.

I will release the updated i3DConverter for Mac and Linux versions later.
[http://www.i3dconverter.com](http://www.i3dconverter.com)
## Post #19
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2018-06-17T18:36:12+00:00
- Post Title: Re: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (.

Sorry for no response for a while. I forgot to enable email subscriptions.

The script I made is intended to extract ._X3 files from Sora SC and 3rd. You need moonscript from luarocks installed.

Due to the hacky nature of how I extract the files, not all files will be successful in extracting.


If you're lazy, look up "Falcom 3D Model and Texture Dumps".
## Post #20
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2019-10-18T22:54:16+00:00
- Post Title: Re: Trails in the Sky / Sora no Kiseki SC / th3rd 3D file (.

OpenSora.Viewer can view _X2 and _X3 files.

[https://github.com/rds1983/OpenSora/releases](https://github.com/rds1983/OpenSora/releases)
