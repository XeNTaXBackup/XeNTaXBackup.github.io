## Post #1
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-14T13:38:03+00:00
- Post Title: very needed script for .big files

I'm using old aluigi's dump script for extracting fifa  .big files, but I noticed that not all files are exported, some players are missing. Can someone make a newer script or take a look, I cut file with filecutter script:
[https://www.mediafire.com/file/saqhrd7f ... e.rar/file](https://www.mediafire.com/file/saqhrd7f37g4f9t/.big_file.rar/file)
aluigi's script: [https://www.mediafire.com/file/ri9tl054 ... 3.bms/file](https://www.mediafire.com/file/ri9tl054bf75ynr/raw_ea_10fb_dumper_FO3.bms/file)
[Capture.PNG](https://xentaxbackup.github.io/file/17187_Capture.PNG)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-19T09:15:40+00:00
- Post Title: very needed script for .big files

> Reply from greenlemonade1 ↑Sat Dec 14, 2019 9:38 pm at Sat Dec 14, 2019 9:38 pm
>
> 
I'm using old aluigi's dump script for extracting fifa  .big files
Which script? You'd better attach a link to it so that people can tell what went wrong.

> Reply from greenlemonade1 ↑Sat Dec 14, 2019 9:38 pm at Sat Dec 14, 2019 9:38 pm
>
> 
Can someone make a newer script or take a look, I cut file with filecutter script:
Base on the sample data there're no asset names nor info table in the big files. You sure you didn't miss some files else important?
## Post #3
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-19T09:42:16+00:00
- Post Title: very needed script for .big files

> Reply from Bigchillghost ↑Thu Dec 19, 2019 5:15 pm at Thu Dec 19, 2019 5:15 pm
>
> 
greenlemonade1 wrote: ↑Sat Dec 14, 2019 9:38 pm
I'm using old aluigi's dump script for extracting fifa  .big files
Which script? You'd better attach a link to it so that people can tell what went wrong.
greenlemonade1 wrote: ↑Sat Dec 14, 2019 9:38 pm
Can someone make a newer script or take a look, I cut file with filecutter script:

Base on the sample data there're no asset names nor info table in the big files. You sure you didn't miss some files else important?
No mate, maybe beacuse the big file is encrypted, but if I got dump files, I will be satisfied. The script that I upload work, but it's missing some files (players) 
script: [https://www.mediafire.com/file/ri9tl054 ... 3.bms/file](https://www.mediafire.com/file/ri9tl054bf75ynr/raw_ea_10fb_dumper_FO3.bms/file)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-19T10:32:08+00:00
- Post Title: very needed script for .big files

> Reply from greenlemonade1 ↑Thu Dec 19, 2019 5:42 pm at Thu Dec 19, 2019 5:42 pm
>
> 
The script that I upload work, but it's missing some files (players)
This script splits the data by the "chunk" identifier, which obviously is the only way to unpack the file since there's no elementary info contained. So nothing can be improved except to further decompress the data to an rx3 file.

> Reply from greenlemonade1 ↑Thu Dec 19, 2019 5:42 pm at Thu Dec 19, 2019 5:42 pm
>
> 
maybe beacuse the big file is encrypted
They're not. And as said above, it's highly possible that you're wrong. There must be some files containing the records of the data, otherwise the .big archive would be an extremely inefficient format.
## Post #5
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-19T11:04:48+00:00
- Post Title: very needed script for .big files

> Reply from Bigchillghost ↑Thu Dec 19, 2019 6:32 pm at Thu Dec 19, 2019 6:32 pm
>
> 
greenlemonade1 wrote: ↑Thu Dec 19, 2019 5:42 pm
The script that I upload work, but it's missing some files (players) 

This script splits the data by the "chunk" identifier, which obviously is the only way to unpack the file since there's no elementary info contained. So nothing can be improved except to further decompress the data to an rx3 file.
greenlemonade1 wrote: ↑Thu Dec 19, 2019 5:42 pm
maybe beacuse the big file is encrypted
They're not. And as said above, it's highly possible that you're wrong. There must be some files containing the records of the data, otherwise the .big archive would be an extremely inefficient format.
I used one program that my friend made, and I extracted 500 files more than with the script, the problem is that takes too long, 25 hrst, but when I tried to run one  other big.file nothing happens. I upload that program, also that other big file, that makes the problem.
[https://www.mediafire.com/file/jz8i22nr ... s.rar/file](https://www.mediafire.com/file/jz8i22nrarvmp38/Help_tools.rar/file)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-19T14:27:18+00:00
- Post Title: very needed script for .big files

> Reply from greenlemonade1 ↑Thu Dec 19, 2019 7:04 pm at Thu Dec 19, 2019 7:04 pm
>
> 
I upload that program
Well, I'm definitely not a VB fan. But base on what I can tell from the code, the .big archive seem to contain more than just "chunk*" blocks. However since your samples are incomplete, I can't verify the structure either.

> Reply from greenlemonade1 ↑Thu Dec 19, 2019 7:04 pm at Thu Dec 19, 2019 7:04 pm
>
> 
the problem is that takes too long, 25 hrst, but when I tried to run one  other big.file nothing happens. I upload ... also that other big file, that makes the problem.
25 hours you said?  
In the 1st dump of data_graphic2 there's a "chunk*" block at offset 0x40. Don't know why you had nothing with that tool.
## Post #7
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-21T08:44:06+00:00
- Post Title: very needed script for .big files

> Reply from Bigchillghost ↑Thu Dec 19, 2019 10:27 pm at Thu Dec 19, 2019 10:27 pm
>
> 
greenlemonade1 wrote: ↑Thu Dec 19, 2019 7:04 pm
I upload that program

Well, I'm definitely not a VB fan. But base on what I can tell from the code, the .big archive seem to contain more than just "chunk*" blocks. However since your samples are incomplete, I can't verify the structure either.
greenlemonade1 wrote: ↑Thu Dec 19, 2019 7:04 pm
the problem is that takes too long, 25 hrst, but when I tried to run one  other big.file nothing happens. I upload ... also that other big file, that makes the problem.

25 hours you said?  
In the 1st dump of data_graphic2 there's a "chunk*" block at offset 0x40. Don't know why you had nothing with that tool.

Master, I got all samples, thah might can be helpful. Also I extracted data big 3 with fo3 export, and I found more than 100 new files, but data 2, won't be exported, that's a crap... 
[https://www.mediafire.com/file/tfah4222 ... s.rar/file](https://www.mediafire.com/file/tfah4222r1wy5x6/all_samples.rar/file)
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-21T15:11:57+00:00
- Post Title: very needed script for .big files

> Reply from greenlemonade1 ↑Sat Dec 21, 2019 4:44 pm at Sat Dec 21, 2019 4:44 pm
>
> 
Master, I got all samples, thah might can be helpful.
None of these are helpful.

> Reply from greenlemonade1 ↑Sat Dec 21, 2019 4:44 pm at Sat Dec 21, 2019 4:44 pm
>
> 
Also I extracted data big 3 with fo3 export, and I found more than 100 new files, but data 2, won't be exported, that's a crap...
Without any info of accessing to the data, there's no way to extract everything since there could be tons of format in the package. And it's absolutely unnecessary to unpack everything inside if you need only the model and the texture data. Conventionally if you can get all the file types you ever need for a FIFA game with that BMS script, it'd be impossible to miss any files of the same types.
## Post #9
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-21T16:22:31+00:00
- Post Title: very needed script for .big files

> Reply from Bigchillghost ↑Sat Dec 21, 2019 11:11 pm at Sat Dec 21, 2019 11:11 pm
>
> 
greenlemonade1 wrote: ↑Sat Dec 21, 2019 4:44 pm
Master, I got all samples, thah might can be helpful. 

None of these are helpful.
greenlemonade1 wrote: ↑Sat Dec 21, 2019 4:44 pm
Also I extracted data big 3 with fo3 export, and I found more than 100 new files, but data 2, won't be exported, that's a crap... 

Without any info of accessing to the data, there's no way to extract everything since there could be tons of format in the package. And it's absolutely unnecessary to unpack everything inside if you need only the model and the texture data. Conventionally if you can get all the file types you ever need for a FIFA game with that BMS script, it'd be impossible to miss any files of the same types.

I appreciate your help master, I think fifa online 4 is one of the hardest game to be exported
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-21T18:35:09+00:00
- Post Title: very needed script for .big files

> Reply from greenlemonade1 ↑Sat Dec 14, 2019 9:38 pm at Sat Dec 14, 2019 9:38 pm
>
> I'm using old aluigi's dump script for extracting fifa  .big files,So you used a FO3 bms script to extract FO4 big files, right?

> but I noticed that not all files are exported, some players are missing.Which "players" are missing? How'd you know that?

> Reply from greenlemonade1 ↑Thu Dec 19, 2019 7:04 pm at Thu Dec 19, 2019 7:04 pm
>
> I used one program that my friend made, and I extracted 500 files more than with the script,Again, you're using a program for FO3 big files for FO4 ones, right?

> the problem is that takes too long, 25 hrst, but when I tried to run one  other big.file nothing happens. I upload that program, also that other big file, that makes the problem.Surprise.  Your proceeding is damned to fail, obviously.  

What I found so far:
(refering to data_first.big, from FO4 I assume?)

- FIFA Online 3 - File Export.exe  exports 427 files named File_1 to File_427
- raw_ea_10fb_dumper_FO3.bms creates 417 .chu files (ten files missing? Those player files you talked of above?)

File_12 (size: 193.553 bytes) is similar to 0000000b.chu (size: 193.600 bytes) which has 47 additional zero bytes at the end.

You can extract 2 valid compressed streams from it using offzip for example. Sadly they don't show decent point clouds so far using hex2obj (view link in my sig)

Once again:

> Reply from greenlemonade1 ↑Thu Dec 19, 2019 7:04 pm at Thu Dec 19, 2019 7:04 pm
>
> I used one program that my friend made,It worked for FO3 big files I assume? Then I'd strongly recommend a proper proceeding: upload a (small, if possible) FO3 big file where these headers are contained:
'list of headers to find 'head_ | hair_ | eyes_ | jerse | numbe | shoe_ | ball_

This way coders could understand how the extraction process works for FO3 files and maybe what's different with FO4 big files.
## Post #11
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-22T11:00:26+00:00
- Post Title: very needed script for .big files

1) I can't find Sergio Augero's face texture for example, in every big file, big 2,3,4 contains face textures, but in data4 are also hair, eye and head models, that's why I know that files are missing, mate   

2)  I exported data 3 and 4, using fo3 program, and gave me good results, just some minor problems in data, but I can fix it,  but data 2, I can export, nothing happened, as Bigchillghost said, maybe because it gives a block at 0x40 offset.

3)So as I realize, I can get from on chunk file two textures, or?

4) There can be found earlier fo3 big that can be easily exported, after the 2017 they made export a bit harder, I know one guy exported it, some Korean, but I can't find him over a years. [https://www.mediafire.com/file/x8gtz33q ... s.rar/file](https://www.mediafire.com/file/x8gtz33qrzeiced/Two_Bigs.rar/file)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-22T13:07:30+00:00
- Post Title: very needed script for .big files

> Reply from greenlemonade1 ↑Sun Dec 22, 2019 7:00 pm at Sun Dec 22, 2019 7:00 pm
>
> 
1) I can't find Sergio Augero's face texture for example, in every big file, big 2,3,4 contains face textures, but in data4 are also hair, eye and head models, that's why I know that files are missing, mate   

2)  I exported data 3 and 4, using fo3 program, and gave me good results, just some minor problems in data, but I can fix it,  but data 2, I can export, nothing happened, as Bigchillghost said, maybe because it gives a block at 0x40 offset.

3)So as I realize, I can get from on chunk file two textures, or?

4) There can be found earlier fo3 big that can be easily exported, after the 2017 they made export a bit harder, I know one guy exported it, some Korean, but I can't find him over a years. https://www.mediafire.com/file/x8gtz33q ... s.rar/fileWhich files are you talking about? I was talking about data_first.big which can be extracted by FIFA Online 3 - File Export.exe.

You are talking about "data 3 and 4". What is this?

I assume it's data_graphic4.big_0_1853850148 for example from your opening post?
Using FIFA Online 3 - File Export.exe results in three files File_1, File_2 and File_3.
All 3 of those start with "chunkzip" as a signature. Using offzip on them results in several files (.rx3 for example).

btw: FIFA Online 3 - File Export.exe has an option 2. inport/export with filemaster. Do you have this tool?

Using ea_big4.bms (from your "FO3 Big" folder) on data_2.big_0_228335040 (signature "BIg")
reveals this
Error: incomplete input file X: \FO3 Big\data_2.big_0
_228335040
       Can't read 2 bytes from offset 006d3c07.

which is not surprising since that file seems to be cut of at offset 0x1FFFFF.

(Guess there's an (other) error with the full sized file, too?)
## Post #13
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-22T13:43:53+00:00
- Post Title: very needed script for .big files

> Reply from shakotay2 ↑Sun Dec 22, 2019 9:07 pm at Sun Dec 22, 2019 9:07 pm
>
> 
greenlemonade1 wrote: ↑Sun Dec 22, 2019 7:00 pm
1) I can't find Sergio Augero's face texture for example, in every big file, big 2,3,4 contains face textures, but in data4 are also hair, eye and head models, that's why I know that files are missing, mate   

2)  I exported data 3 and 4, using fo3 program, and gave me good results, just some minor problems in data, but I can fix it,  but data 2, I can export, nothing happened, as Bigchillghost said, maybe because it gives a block at 0x40 offset.

3)So as I realize, I can get from on chunk file two textures, or?

4) There can be found earlier fo3 big that can be easily exported, after the 2017 they made export a bit harder, I know one guy exported it, some Korean, but I can't find him over a years. https://www.mediafire.com/file/x8gtz33q ... s.rar/file
Which files are you talking about? I was talking about data_first.big which can be extracted by FIFA Online 3 - File Export.exe.

You are talking about "data 3 and 4". What is this?

I assume it's data_graphic4.big_0_1853850148 for example from your opening post?
Using FIFA Online 3 - File Export.exe results in three files File_1, File_2 and File_3.
All 3 of those start with "chunkzip" as a signature. Using offzip on them results in several files (.rx3 for example).

btw: FIFA Online 3 - File Export.exe has an option 2. inport/export with filemaster. Do you have this tool?

Using ea_big4.bms (from your "FO3 Big" folder) on data_2.big_0_228335040 (signature "BIg")
reveals this
Error: incomplete input file X: \FO3 Big\data_2.big_0
_228335040
       Can't read 2 bytes from offset 006d3c07.

which is not surprising since that file seems to be cut of at offset 0x1FFFFF.

(Guess there's an (other) error with the full sized file, too?)
I understand mate, I was talking about data big 2, I already uploaded link, and it's strange it's starts also with chunkzip as a signature, but I can't export it, it gave me no error etc. [https://www.mediafire.com/file/jz8i22nr ... s.rar/file](https://www.mediafire.com/file/jz8i22nrarvmp38/Help_tools.rar/file)
I exported two days ago data big 4, with more than 12 000 files, for 25 or more hrs, but you export it so quickly. I appreciate your help very much.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-22T14:54:50+00:00
- Post Title: very needed script for .big files

> Reply from greenlemonade1 ↑Sun Dec 22, 2019 9:43 pm at Sun Dec 22, 2019 9:43 pm
>
> I exported two days ago data big 4, with more than 12 000 files, for 25 or more hrs, but you export it so quickly.It's because you used the full sized archive file (>12000 files contained) while I had the cut file only (2 MB of size, 3 files contained).
## Post #15
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-22T16:16:01+00:00
- Post Title: very needed script for .big files

> Reply from shakotay2 ↑Sun Dec 22, 2019 10:54 pm at Sun Dec 22, 2019 10:54 pm
>
> 
greenlemonade1 wrote: ↑Sun Dec 22, 2019 9:43 pmI exported two days ago data big 4, with more than 12 000 files, for 25 or more hrs, but you export it so quickly.It's because you used the full sized archive file (>12000 files contained) while I had the cut file only (2 MB of size, 3 files contained).

Oh that's a trick. Did you have sucess with data big 2?
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-22T16:59:09+00:00
- Post Title: Re: very needed script for .big files

nope. Re-read my post as of 2:07 o'clock:

> Using ea_big4.bms (from your "FO3 Big" folder) on data_2.big_0_228335040 (signature "BIg")
>
> reveals this
>
> Error...But that data_2.big... file was shortened to 2 MB. What is the error message when you use ea_big4.bms on the full sized data_2.big_0_228335040?
## Post #17
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-22T17:35:58+00:00
- Post Title: Re: very needed script for .big files

> Reply from shakotay2 ↑Mon Dec 23, 2019 12:59 am at Mon Dec 23, 2019 12:59 am
>
> 
nope. Re-read my post as of 2:07 o'clock:
Using ea_big4.bms (from your "FO3 Big" folder) on data_2.big_0_228335040 (signature "BIg")
reveals this
Error...But that data_2.big... file was shortened to 2 MB. What is the error message when you use ea_big4.bms on the full sized data_2.big_0_228335040?
I got little confused. I meant data big from fo4 with fo3 export program:[https://www.mediafire.com/file/xk3kx5yh ... 2.rar/file](https://www.mediafire.com/file/xk3kx5yhtv66ado/FO4_data_big_2.rar/file)
I used file cutter to shrink it, to be faster do download 
As for ea_big4.bms script I wanna tell that the script won't work with fo3 data big 2, although  in signature is the same "Big".
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-22T18:29:24+00:00
- Post Title: Re: very needed script for .big files

> Reply from greenlemonade1 ↑Mon Dec 23, 2019 1:35 am at Mon Dec 23, 2019 1:35 am
>
> As for ea_big4.bms script I wanna tell that the script won't work with fo3 data big 2, although  in signature is the same "Big".yeah, I know, mate. What is the error message in the quickbms console window then? (screenshot?)
And which size has  data_2.big_0_228335040?
## Post #19
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-22T19:03:42+00:00
- Post Title: Re: very needed script for .big files

> Reply from shakotay2 ↑Mon Dec 23, 2019 2:29 am at Mon Dec 23, 2019 2:29 am
>
> 
greenlemonade1 wrote: ↑Mon Dec 23, 2019 1:35 amAs for ea_big4.bms script I wanna tell that the script won't work with fo3 data big 2, although  in signature is the same "Big".yeah, I know, mate. What is the error message in the quickbms console window then? (screenshot?)
And which size has  data_2.big_0_228335040?

Well, actually there isn't any error, what is strange. In the first, I was taught, that I needs more time, because the export takes to damn slow, but I waited 5 hours, and not single file was exported xd 
The size of the big is: 1,728,760 kb.
Ignore file master, it's not relevant so
[Capture.PNG](https://xentaxbackup.github.io/file/17220_Capture.PNG)
## Post #20
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-23T22:05:23+00:00
- Post Title: Re: very needed script for .big files

> Reply from shakotay2 ↑Mon Dec 23, 2019 2:29 am at Mon Dec 23, 2019 2:29 am
>
> 
greenlemonade1 wrote: ↑Mon Dec 23, 2019 1:35 amAs for ea_big4.bms script I wanna tell that the script won't work with fo3 data big 2, although  in signature is the same "Big".yeah, I know, mate. What is the error message in the quickbms console window then? (screenshot?)
And which size has  data_2.big_0_228335040?

any news mate?
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-24T06:44:56+00:00
- Post Title: Re: very needed script for .big files

> Reply from greenlemonade1 ↑Sun Dec 22, 2019 7:00 pm at Sun Dec 22, 2019 7:00 pm
>
> 
but data 2, I can export, nothing happened, as Bigchillghost said, maybe because it gives a block at 0x40 offset.
Please distinguish the difference between "can" and "can't" next time. What I meant was that the file has a "chunkzip" block at offset 0x40 which was supposed to be extracted by any tool that has successfully extracted files of the same signature before.

> Reply from greenlemonade1 ↑Mon Dec 23, 2019 1:35 am at Mon Dec 23, 2019 1:35 am
>
> 
As for ea_big4.bms script I wanna tell that the script won't work with fo3 data big 2, although  in signature is the same "Big".
That's because the data_2.big is xored with a 4-byte key (6D 7C XX XX?). Even if it wasn't, the script won't work properly without some midifications. But of course it's irrelevant to this topic, isn't it?  

Also please refer to the full name of the files next time, i.e. "data_2.big" instead of "data big 2", to avoid confusion.

Since only files whose signature include a "chunk" wildcard -- like "chunkzip" -- can be extracted with raw_ea_10fb_dumper_FO3.bms, you won't get any further if you can't provide a sample that contains data other than "chunkzip" blocks.
Anyway there's another signature type ("EASF") in files like data_fo4.big and data_second.big, which use a different structure. So I suggest to focus only on the files with the signature you need, to avoid unnecessary works.
## Post #22
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-24T09:43:23+00:00
- Post Title: Re: very needed script for .big files

> Reply from Bigchillghost ↑Tue Dec 24, 2019 2:44 pm at Tue Dec 24, 2019 2:44 pm
>
> 
greenlemonade1 wrote: ↑Sun Dec 22, 2019 7:00 pm
but data 2, I can export, nothing happened, as Bigchillghost said, maybe because it gives a block at 0x40 offset.

Please distinguish the difference between "can" and "can't" next time. What I meant was that the file has a "chunkzip" block at offset 0x40 which was supposed to be extracted by any tool that has successfully extracted files of the same signature before.
greenlemonade1 wrote: ↑Mon Dec 23, 2019 1:35 am

Of course I know the difference, there is no need to saying that, probably some words are missing. Okay, I understand now. 
As for ea_big4.bms script I wanna tell that the script won't work with fo3 data big 2, although  in signature is the same "Big".That's because the data_2.big is xored with a 4-byte key (6D 7C XX XX?). Even if it wasn't, the script won't work properly without some midifications. But of course it's irrelevant to this topic, isn't it?  
> I didn't saay it's irellevant or etc, I was said in the moment is not crucial, because fo3 lost it's purpose, because there's no any update, but if you or someone can modify the script it will be great, of course.

Also please refer to the full name of the files next time, i.e. "data_2.big" instead of "data big 2", to avoid confusion.
> okay

Since only files whose signature include a "chunk" wildcard -- like "chunkzip" -- can be extracted with raw_ea_10fb_dumper_FO3.bms, you won't get any further if you can't provide a sample that contains data other than "chunkzip" blocks.
Anyway there's another signature type ("EASF") in files like data_fo4.big and data_second.big, which use a different structure. So I suggest to focus only on the files with the signature you need, to avoid unnecessary works.
> I will try to upload what is neccessary
## Post #23
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-24T10:32:34+00:00
- Post Title: Re: very needed script for .big files

> Reply from greenlemonade1 ↑Tue Dec 24, 2019 5:43 pm at Tue Dec 24, 2019 5:43 pm
>
> 
Of course I know the difference, there is no need to saying that, probably some words are missing. Okay, I understand now.
Don't take it wrong. If it wasn't for the additional explanation, it'd be the opposite meaning, which is really confusing and people would have to look over what you had written before to sort things out. 

Another thing that needs to point out, please, PREVIEW and CHECK what you have written before posting the whole thing. I'm talking about your BAD quoting style. It's a real horrible mess. I won't say a third time.
## Post #24
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-24T11:00:32+00:00
- Post Title: Re: very needed script for .big files

> Another thing that needs to point out, please, PREVIEW and CHECK what you have written before posting the whole thing. I'm talking about your BAD quoting style. It's a real horrible mess. I won't say a third time.
Okay, I'm doing my best, but I don't realize the procedure, I'm stupid...
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-24T17:27:46+00:00
- Post Title: Re: very needed script for .big files

It's just a matter of the starting quote and the stop /quote (which may be nested, of course).
.



quotation.png (46.32 KiB) Viewed 54 times



Use the Preview (as Bigchillghost pointed out) before posting and you should be safe.
