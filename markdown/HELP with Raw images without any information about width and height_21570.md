## Post #1
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-01-04T22:57:41+00:00
- Post Title: HELP with Raw images without any information about width and height

Can someone make script to fix headers for the dump files, which are supposed to be images/textures. 
Here are the samples: [https://www.mediafire.com/file/b84bctpy ... p.rar/file](https://www.mediafire.com/file/b84bctpy1my3svm/raw_dump.rar/file)
[Capture.PNG](https://xentaxbackup.github.io/file/17297_Capture.PNG)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-01-06T19:08:13+00:00
- Post Title: HELP with Raw images without any information about width and height

what is the full game name and the platform from which the samples came?
i don't think these are images, the data looks compressed to me, don't know.
## Post #3
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2020-01-06T23:31:03+00:00
- Post Title: HELP with Raw images without any information about width and height

That looks compressed, if you wanna test out for inages use texturefinder, with rawtext you can convert them to dds if that is the case, but again, that looks compressed, try maybe offzip
## Post #4
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-01-07T11:38:38+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from Acewell ↑Tue Jan 07, 2020 3:08 am at Tue Jan 07, 2020 3:08 am
>
> 
what is the full game name and the platform from which the samples came?
i don't think these are images, the data looks compressed to me, don't know.

It's fbmod from FIFA 20. Here is the link of the file, I used aluigi's script, maybe Bigchillghost can make a script: 
[https://www.mediafire.com/file/0e3sy6aq ... fbmod/file](https://www.mediafire.com/file/0e3sy6aqschbzs1/FIFA_20_greenlemonade.fbmod/file)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-08T05:30:04+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from greenlemonade1 ↑Tue Jan 07, 2020 7:38 pm at Tue Jan 07, 2020 7:38 pm
>
> 
I used aluigi's script
Which script was it? The data from your screenshot is oodle-compressed, while data in 0000000a.dat is zstd-compressed. From a rough glance over the fbmod archive the assets have names but your samples didn't.
## Post #6
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-02-08T09:17:00+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from Bigchillghost ↑Sat Feb 08, 2020 1:30 pm at Sat Feb 08, 2020 1:30 pm
>
> 
greenlemonade1 wrote: ↑Tue Jan 07, 2020 7:38 pm
I used aluigi's script

Which script was it? The data from your screenshot is oodle-compressed, while data in 0000000a.dat is zstd-compressed. From a rough glance over the fbmod archive the assets have names but your samples didn't.
I used this updated aluigi's script: [https://www.mediafire.com/file/6bq4m4oi ... d.bms/file](https://www.mediafire.com/file/6bq4m4oihsovld4/fifa18_fbmod.bms/file)
What should I do to decompress raw data files, because one is zstd, thans for helping mate
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-08T14:48:38+00:00
- Post Title: HELP with Raw images without any information about width and height

Here's a BMS script to unpack your sample archive.


 FIFA20_fbmod.zip
(961 Bytes) Downloaded 43 times



Some files are sharing the same name so remember to auto-rename them when prompt for related option.
## Post #8
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-02-08T18:08:16+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from Bigchillghost ↑Sat Feb 08, 2020 10:48 pm at Sat Feb 08, 2020 10:48 pm
>
> 
Here's a BMS script to unpack your sample archive.
FIFA20_fbmod.zip


Some files are sharing the same name so remember to auto-rename them when prompt for related option.

Works like a charm, for the sample file. But this fbmod can't be exported: [http://www.mediafire.com/file/d38wmobhf ... fbmod/file](http://www.mediafire.com/file/d38wmobhfqzkpcx/%255BFIFA_20%255D_Ronaldo.fbmod/file)
Also master, how can I open face texture and identify it, should I use raw texture finder or? Thanks
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-09T07:55:04+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from greenlemonade1 ↑Sun Feb 09, 2020 2:08 am at Sun Feb 09, 2020 2:08 am
>
> 
But this fbmod can't be exported...
Also master, how can I open face texture and identify it, should I use raw texture finder or? Thanks
Script updated in the same post. The path of the filenames are removed and texture header files are given an extension as "f20t" so you can use the following Noesis script to load the textures.
[tex_FIFA20.zip](https://xentaxbackup.github.io/file/17476_tex_FIFA20.zip)
## Post #10
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-02-09T09:20:17+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from Bigchillghost ↑Sun Feb 09, 2020 3:55 pm at Sun Feb 09, 2020 3:55 pm
>
> 
greenlemonade1 wrote: ↑Sun Feb 09, 2020 2:08 am
But this fbmod can't be exported...
Also master, how can I open face texture and identify it, should I use raw texture finder or? Thanks
Script updated in the same post. The path of the filenames are removed and texture header files are given an extension as "f20t" so you can use the following Noesis script to load the textures.

Works perfect, thank you so much. God blessed you
## Post #11
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-07-11T22:09:49+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from Bigchillghost ↑Sun Feb 09, 2020 3:55 pm at Sun Feb 09, 2020 3:55 pm
>
> 
greenlemonade1 wrote: ↑Sun Feb 09, 2020 2:08 am
But this fbmod can't be exported...
Also master, how can I open face texture and identify it, should I use raw texture finder or? Thanks
Script updated in the same post. The path of the filenames are removed and texture header files are given an extension as "f20t" so you can use the following Noesis script to load the textures.

Hi master, I hope you keeping you safe during corona, and that you doing well. I was wondering is there a way to export models file from fbmod, here is a sample. stay safe! 
[https://mega.nz/file/alsUnArI#pNU5NioDN ... PvKtPVOGio](https://mega.nz/file/alsUnArI#pNU5NioDN2n8zVUllhdgnAav1YdqkQy9CPvKtPVOGio)
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-12T04:31:59+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from greenlemonade1 ↑Sun Jul 12, 2020 6:09 am at Sun Jul 12, 2020 6:09 am
>
> I was wondering is there a way to export models file from fbmod
Get the importer here.
[viewtopic.php?f=16&t=22387](viewtopic.php?f=16&t=22387)



head_202750_0_0_mesh.f20m.png (87.08 KiB) Viewed 225 times
## Post #13
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-07-12T09:23:02+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from Bigchillghost ↑Sun Jul 12, 2020 12:31 pm at Sun Jul 12, 2020 12:31 pm
>
> 
greenlemonade1 wrote: ↑Sun Jul 12, 2020 6:09 amI was wondering is there a way to export models file from fbmod

Get the importer here.
viewtopic.php?f=16&t=22387
head_202750_0_0_mesh.f20m.png

Awesome, thanks for the fast reply!!! I have just two questions: 1) all textures can't be seen with noesis on this fbmod [https://www.mediafire.com/file/fjcq45fp ... fbmod/file](https://www.mediafire.com/file/fjcq45fpeofi24z/%5BFIFA20_%5D.fbmod/file)
                                                                                                2) I tried to convert obj to rx3, but strange thing is that fifa20 obj have more vertices, but the facs and indices are the same, how should I convert it? All the best master.
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-13T08:37:08+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from greenlemonade1 ↑Sun Jul 12, 2020 5:23 pm at Sun Jul 12, 2020 5:23 pm
>
> all textures can't be seen with noesis on this fbmod https://www.mediafire.com/file/fjcq45fp ... fbmod/file
It's best that you keep using mega for hosting large archives rather than mediafile. Will check it later once it's done.

> Reply from greenlemonade1 ↑Sun Jul 12, 2020 5:23 pm at Sun Jul 12, 2020 5:23 pm
>
> I tried to convert obj to rx3, but strange thing is that fifa20 obj have more vertices, but the facs and indices are the same, how should I convert it?
That's not a problem produced by the script so can't help you with that.
## Post #15
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-07-13T10:10:54+00:00
- Post Title: HELP with Raw images without any information about width and height

> Reply from Bigchillghost ↑Mon Jul 13, 2020 4:37 pm at Mon Jul 13, 2020 4:37 pm
>
> 
greenlemonade1 wrote: ↑Sun Jul 12, 2020 5:23 pmall textures can't be seen with noesis on this fbmod https://www.mediafire.com/file/fjcq45fp ... fbmod/file

It's best that you keep using mega for hosting large archives rather than mediafile. Will check it later once it's done.
greenlemonade1 wrote: ↑Sun Jul 12, 2020 5:23 pmI tried to convert obj to rx3, but strange thing is that fifa20 obj have more vertices, but the facs and indices are the same, how should I convert it?

That's not a problem produced by the script so can't help you with that.
I'm sorry I will upload throw mega, the script works excellent with those two samples, just this file have error and all textures can't be seen, I've tried with raw cooker, but nothing... Okay mate, I will figure it, I'm sure
