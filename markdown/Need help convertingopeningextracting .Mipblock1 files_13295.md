## Post #1
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2015-09-08T09:05:24+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

Need help converting/opening .mipblock1 files. I've never seen them/heard of them before.
I know they are texture files, because they're accompanied with .tex files
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-09-16T20:38:25+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

Hi hhchunter!

Open ascolormap.pc_mipblock1 with a hex editor and delete the first 92 bytes (0x5C in hexadecimal notation)

Download Header.rar from here:
http://www.mksecrets.net/forums/eng/viewtopic.php?f=93&t=7853
extract it and insert the header before the body of the texture and save with .DDS extension.

Download the Texconv Tool from here:
https://directxtex.codeplex.com/releases/view/615824
and run it with the following arguments:
texconv.exe -f R8G8B8A8_UNORM -ft DDS -px ed_ -m 11 ascolormap.pc_mipblock1.dds

This will result in a DDS file with 11 mipmaps, here's mipmap #1 to show you that it works:



ascolormap.pc_mipblock1.png (146.99 KiB) Viewed 90 times



If you are really willing to pay, feel free to send a PM so we can discuss the details
## Post #3
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2015-09-20T09:32:02+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

YES! Thank you so much!
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-09-20T21:02:20+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

I'm glad I was able to help. Which program do you use to open the .DDS file? I use Gimp by the way. 

And I was joking about the payment, just help someone else out (either here at xentax, another forum or in real life) and we are even  
Or consider donating to an animal welfare group, maybe this one: [http://adoptionavsallar.com/donations-a ... aisers.php](http://adoptionavsallar.com/donations-and-fundraisers.php) (that's where I got my two cats from) Any amount is truly welcome, even a few bucks.
## Post #5
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2015-09-21T04:43:11+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

Donation sent, hopefully it goes to good use
## Post #6
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-09-22T18:07:58+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

It looks like the file uses a different compression.
You could try this header instead:


 header2.rar
(146 Bytes) Downloaded 21 times


As before, delete the first 92 bytes, insert the header and save it as .dds
You don't even have to run texconv.exe

It should be possible to write a tool for that but right now I don't have the time.
## Post #7
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2015-09-25T13:05:01+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

super thankful for all the work you've done
## Post #8
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-09-25T21:22:05+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

No problem!
Chances are high that the textures of any modern video game are in the dds format  

Using DXT1 and a resolution of 1024x512 got me this:



fashionshow_concept_b_diffuse.pc_mipblock1.jpg (88.12 KiB) Viewed 51 times


This is the DDS header (created by Gimp):

```
44 44 53 20 7C 00 00 00 07 10 0A 00 00 02 00 00 00 04 00 00 00 00 04 00 00 00 00 00 0B 00 00 00 47 49 4D 50 2D 44 44 53 01 00 03 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 20 00 00 00 04 00 00 00 44 58 54 31 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 08 10 40 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```

And if you open a mipblock1 file in a hex editor, you can see the width and height at position 0x10 and 0x12 (just figured that out)
## Post #9
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2015-09-26T03:13:58+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

Thank you so much!
## Post #10
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2015-09-26T05:53:41+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

Working on another one now, but I get a semi corrupted file.
## Post #11
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-09-26T19:33:21+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

Try DX10.
You could also use the header from my first post, adjust the resolution and run the texconv tool.
0x0C = height: 00 02 00 00
0x10 = width: 00 04 00 00
## Post #12
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2016-03-22T02:42:44+00:00
- Post Title: Need help converting/opening/extracting .Mipblock1 files

Back again. 

The format may have changed slightly perhaps?

I tried getting a few files to convert to dds, they mostly did. 
But it seems like there is some sort of distortion going on with it.
[https://i.imgur.com/OgfBrId.jpg](https://i.imgur.com/OgfBrId.jpg)

Any idea's?

Mipblock file.
[https://anonfiles.com/file/57484252c922 ... 5ee410eec6](https://anonfiles.com/file/57484252c922c0f735242b5ee410eec6)
