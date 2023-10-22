## Post #1
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2017-01-04T14:25:08+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

Hello...
I wanted to convert models from PC game "Toybox Turbos".





I found that it had one .nfs file so I started finding any of script or extractor and finally found a BMS script...
but after the extraction of .nfs file I was disclosed to two new files ".ego" and ".BUNDLE".

I would like to ask if anyone knows how I can extract textures and models from these files....It looks like the textures are in the .ego files but I am not sure whether the models are in .BUNDLE files or not.

How can I extract the models and textures from these files??

Here is the link to the files... 
Thanks in advance...

[https://app.box.com/s/h5s6hliva211fj2gxbh3qyunf7pwnv0u](https://app.box.com/s/h5s6hliva211fj2gxbh3qyunf7pwnv0u)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-05T03:33:54+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

here is a Noesis python script to open your texture samples  


 tex_ToyboxTurbos_ego.zip
(626 Bytes) Downloaded 32 times



only supports dxt5 because all of the samples were dxt5
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-05T13:38:21+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

first submesh, some extra faces, dunno:



vrambundle.JPG (90.29 KiB) Viewed 126 times
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-01-06T13:16:24+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

taruncreation,

I used the toyboxturbos.bms on the win_000.nfs file.
After it I used the codemasters_nefs.bms on the win_000_new.nfs file, it extracted some files from the system and audio folders. After it crashed:


QuickBMS generic files extractor and reimporter 0.7.7 (64bit test)

Error: the compressed LZMA input is wrong or incomplete (0)
Info:  algorithm   445
       offset      000000000551a0c0
       input size  0x000000000000f9e5 63973
       output size 0x0000000000010000 65536
       result      0xffffffffffffff9c -100

Error: the uncompressed data (-100) is bigger than the allocated buffer (65536)

Last script line before the error or that produced the error:
  178 clog MEMORY_FILE TMP_OFF TMP CHUNK_SIZE
## Post #5
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2017-01-06T16:15:55+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

@Karpati

I was able to extract the new nfs file....



I have attached the script which extract it..
@shakotay2
How did you got the models out ?

@AceWell
I have extracted the textures...thanks for the script   
Is there any way to extract the models ?


[script.rar](https://xentaxbackup.github.io/file/12166_script.rar)
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-01-06T16:35:02+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

@taruncreation,

I compared the scripts and they were identical.

(The size of win_000.nfs is 321.126.400 bytes)
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-01-06T17:40:30+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

@taruncreation,

I used the attached script to decode the win_000.nfs file.
Can you compare it with your ones?
[toyboxturbos.zip](https://xentaxbackup.github.io/file/12167_toyboxturbos.zip)
## Post #8
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2017-01-07T02:56:42+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

@Karpati,

I checked the script and it worked nicely...a new .nfs file was formed...now you can easily extract it by using the script I attached with my last post..
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-01-07T07:20:27+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

@taruncreation

I did try your script on my file, but it crashed also.
## Post #10
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-01-07T10:11:09+00:00
- Post Title: Toybox Turbos's .ego and .BUNDLE files.

@taruncreation

I reinstalled the game again, and I compared the installed (new and old) win_000.nfs using Total Commander.
It found 1 byte difference!

After it the codemasters_nefs.bms extracted all files from the win_000_new.nfs file.
