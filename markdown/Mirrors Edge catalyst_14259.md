## Post #1
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2016-04-23T04:36:12+00:00
- Post Title: Mirrors Edge catalyst

Just wondering if anyone with a beta code was able to extract the music from the mirrors edge beta.
## Post #2
- Username: gottagofast420
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 23, 2016 5:15 pm
- Post datetime: 2016-04-23T09:40:07+00:00
- Post Title: Mirrors Edge catalyst

I've tried the numerous tools I've found here, but to no avail.

If anyone has any suggestions/tools I could try, don't be afraid to tell me.

Here's the file structure of the beta, if anyone was wondering:
[http://pastebin.com/CjFz2bnC](http://pastebin.com/CjFz2bnC)
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-25T15:43:51+00:00
- Post Title: Mirrors Edge catalyst

have you tried battlefield 4/hardline dumper / audio decoder ?

Note that resource dumping lines are commented in this version, so it only dumps audio chunks and sound ebx's
[bf4dumper.rar](https://xentaxbackup.github.io/file/10834_bf4dumper.rar)
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-04-25T16:27:47+00:00
- Post Title: Mirrors Edge catalyst

[I got an error attempting to use it.](http://i.imgur.com/xRO5M76.jpg)

Unless I'm doing something wrong?
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-25T16:57:24+00:00
- Post Title: Mirrors Edge catalyst

That means the format is not the same as in battlefield. Have you tried Star wars dumper? I think you did...

And in this case, I need game files, otherwise I can't help you.
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-04-25T17:04:20+00:00
- Post Title: Mirrors Edge catalyst

The Star Wars dumper did indeed work.

I got a whole heap of .chunk files and couldn't work out if any of them had audio as they didn't have proper filenames.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-25T17:16:00+00:00
- Post Title: Mirrors Edge catalyst

> Reply from brendan19
>
> The Star Wars dumper did indeed work.

Very good. Do you also have EBX folder dumped? Now run the audio decoder, its in separate script "fb3decoder.py".

> Reply from brendan19
>
> I got a whole heap of .chunk files and couldn't work out if any of them had audio as they didn't have proper filenames.

They don't have to have proper names. Names are in EBX files. That's OK
## Post #8
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-04-25T17:57:49+00:00
- Post Title: Mirrors Edge catalyst

Tested it with the initial package, managed to get decoded SFX with names. Now trying with all of the cat/cas pairs.

Successfully decoded audio  (can't say it's everything since it's still a beta)
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-25T21:00:11+00:00
- Post Title: Mirrors Edge catalyst

Congratulations
## Post #10
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-04-25T21:22:26+00:00
- Post Title: Mirrors Edge catalyst

which star wars dumper? the python one I used isn't working. Keeps telling me chunk isn't found.
## Post #11
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-04-26T04:08:43+00:00
- Post Title: Mirrors Edge catalyst

Use this edited version of the script for Mirror's Edge: Catalyst

I also included the ealayer3 tool.

Basically, all you need to change in these scripts is the following

sw_dumper.py:

```
targetDirectory = r"<THE DIRECTORY WHERE YOU WANT THE FILES TO EXTRACT TO>"
```


fb3decoder.py

```
targetDirectory = r"<THE DIRECTORY WHERE YOU WANT THE DECODED .WAV FILES PLACED>"

#Download Zench's tool so the script can handle EALayer3.
ealayer3Path=r"<THE DIRECTORY THAT HAS THE EALAYER3 TOOL>\ealayer3.exe" 
```


EDIT: Updated ealayer3 tool.
[swbf_me-c_edit tool](http://www85.zippyshare.com/v/YHk08MTQ/file.html)
## Post #12
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2016-04-26T04:34:32+00:00
- Post Title: Mirrors Edge catalyst

Great work! Look forward to trying it out
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-26T15:14:00+00:00
- Post Title: Mirrors Edge catalyst

> Reply from brendan19
>
> I also included the ealayer3 tool.

You included Zench's version of the tool. And I far as I remember, it will extract multi-file chunks wrong. For example, from the chunk with 5 sounds it will extract 15 files, 10 of which will be duplicates. Better use my updated version of his tool.
## Post #14
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-04-26T18:17:54+00:00
- Post Title: Mirrors Edge catalyst

Updated link with your version of ealayer3 included
## Post #15
- Username: Hello
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 11, 2016 4:19 pm
- Post datetime: 2016-06-11T10:42:10+00:00
- Post Title: Mirrors Edge catalyst

Hey, thanks a lot for making these tools.

I'm having a problem with the latest version of MEC. Extraction seems to work perfectly with brendan19's link. I'm able to get 28.5gb of files in /bundles and /chunks. However, when I run fb3decoder.py it runs through hundreds of .ebx files and ends with the output below.

```
lms_bauble_bitumen_static.ebx
lms_bauble_bitumen_static_mesh.ebx
lms_bauble_destrasset_merged.ebx
lms_bauble_roofcolor_static.ebx
lms_bauble_roofcolor_static_mesh.ebx
lms_bauble_roofflat_static.ebx
lms_bauble_roofflat_static_mesh.ebx
lms_bauble_voro_static.ebx
lms_bauble_voro_static_mesh.ebx
lms_bauble_walltiles_static.ebx
lms_bauble_walltiles_static_mesh.ebx
lms_bauble_windows_static.ebx
lms_bauble_windows_static_mesh.ebx
Traceback (most recent call last):
  File "F:\Extract\mec\fb3decoder\fb3decoder.py", line 576, in <module>
    main()
  File "F:\Extract\mec\fb3decoder\fb3decoder.py", line 566, in main
    dbx=Dbx(f,relPath)
  File "F:\Extract\mec\fb3decoder\fb3decoder.py", line 342, in __init__
    inst=self.readComplex(instanceRepeater.complexIndex,f,True)
  File "F:\Extract\mec\fb3decoder\fb3decoder.py", line 368, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "F:\Extract\mec\fb3decoder\fb3decoder.py", line 421, in readField
    (typ,length)=numDict[fieldDesc.type]
KeyError: 49437
```


I'm unfamiliar with python but I've traced the keyerror back to:
numDict={0xC12D:("Q",8),0xc0cd:("B",1) ,0x0035:("I",4),0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("b",1),0xc0ed:("h",2), 0xc0dd:("H",2), 0xc13d:("f",4)}

49437 in hexadecimals is 0xC11D, which isn't in that list. I assume I have to add it to the list but I'm not sure what to add it as.

Any help is appreciated. Thanks!
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-11T11:22:12+00:00
- Post Title: Re: Mirrors Edge catalyst

Probably they introduced some new type inside EBX structure. Since this is not related to audio, you can safely delete all folders with EBX files that are NOT audio, and it must work.
## Post #17
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2016-08-29T15:06:09+00:00
- Post Title: Re: Mirrors Edge catalyst

> Reply from Hello
>
> 49437 in hexadecimals is 0xC11D, which isn't in that list. I assume I have to add it to the list but I'm not sure what to add it as.
IMHO it is 8 bytes data, may be 
```
0xc11d:("q",8)
```
