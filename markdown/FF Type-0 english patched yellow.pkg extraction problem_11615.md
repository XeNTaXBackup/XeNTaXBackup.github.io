## Post #1
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-06-20T21:05:56+00:00
- Post Title: FF Type-0 english patched yellow.pkg extraction problem

Hi,i have problem extracting *.pkg archive from this english patched game. i try noesis but it always give me an error like this

[](http://postimg.org/image/510040fsd/)

Well, since this is a  2 iso merged,the yellow.pkg size is 2,65 GB. I try many other pkg extractor program available in the net,but no luck, it said not supported,corrupt,etc. So does anyone can help me solve this problem? all help appreciated  
[yellow.rar](https://xentaxbackup.github.io/file/7497_yellow.rar)
## Post #2
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-06-20T21:35:46+00:00
- Post Title: FF Type-0 english patched yellow.pkg extraction problem

Okay, here's some sample cut from my merged yellow.pkg. Its 1mb each,i hope this might be useful   

[https://www.sendspace.com/file/pl8yw1](https://www.sendspace.com/file/pl8yw1)
## Post #3
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-06-22T21:27:17+00:00
- Post Title: FF Type-0 english patched yellow.pkg extraction problem

anyone?please,a bms script or anything  i'm just curious,what that make noesis cannot extract this archive,is there a filesize limitation reading on noesis for psp archive format?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-23T00:36:21+00:00
- Post Title: FF Type-0 english patched yellow.pkg extraction problem

could you upload another 1MB yellow.pkg_xxx which contains this hex pattern at the beginning of the file, plz?
00 00 00 00 21 27

btw, did you try FF7CC_Extractor on the 2.65 GB file?
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-06-23T17:16:22+00:00
- Post Title: FF Type-0 english patched yellow.pkg extraction problem

Unless you're intending to translate the game from English to another language, it'd make more sense to just get the original Japanese iso and extract that using noesis, as I can confirm that works perfectly.
## Post #6
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-06-24T17:44:17+00:00
- Post Title: FF Type-0 english patched yellow.pkg extraction problem

Sorry for late response Shakotay2, here's a file that you asked. Its not 1 MB exact,but it contain hex pattern that you asked for. I hope i hear a good news from you  

[https://www.sendspace.com/file/ynnpn9](https://www.sendspace.com/file/ynnpn9)

and i have tried that ff7cc_extractor, it extract massive size of raw file from the yellow.pkg (its eats up my 16 GB HDD even its still just only extract 40 raw file,and the extracting process is not finished) so i assume thats not working.

> Reply from lionheartuk
>
> Unless you're intending to translate the game from English to another language, it'd make more sense to just get the original Japanese iso and extract that using noesis, as I can confirm that works perfectly.

Well,yeah,i have a plan to translate it to my native language, thats why i didnt bother the original japanese iso which easier to extract if i just want the model from the game
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-24T23:37:24+00:00
- Post Title: FF Type-0 english patched yellow.pkg extraction problem

> Reply from aagems
>
> Sorry for late response Shakotay2, here's a file that you asked. Its not 1 MB exact,but it contain hex pattern that you asked for. I hope i hear a good news from youthx, but I don't see the requested pattern in it (4x 00 then 0x21 0x27)
Anyway it's a sequence indicating a model file. So since your goal is translating it won't help you.
## Post #8
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-06-26T18:25:39+00:00
- Post Title: FF Type-0 english patched yellow.pkg extraction problem

Ok,here's another sample,its 30MB each now.I  hope now this sample contain what you need. My main purpose is just want to extract these yellow.pkg and i think this would help people out there who just have the english patch game but want rip the models from this great game   

[https://www.sendspace.com/file/aitkwv](https://www.sendspace.com/file/aitkwv)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-28T20:50:31+00:00
- Post Title: FF Type-0 english patched yellow.pkg extraction problem

well, there are lots of 0000803F patterns in the yellow.pkg.036 sample
but I don't seem to find structures like these

```
 0x0cdc:  1.000000 vt 0.997276 0.789363 00 0C 82 00  v 0.000000 1.276001 3.897705 0.000000  00 00 80 3F 
 0x0cf8:  0.000000 vt 0.919307 0.885539 C0 14 95 00  v 3.882141 1.143311 3.890015 0.000000  00 00 00 00 
 0x0d14:  1.000000 vt 0.780825 0.790986 6E 03 3E 00  v 0.140381 1.271484 0.052856 0.000000  00 00 80 3F 
```


as it would be required for "00 00 00 00 21 27" models.
