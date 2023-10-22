## Post #1
- Username: LALHW
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 10, 2016 8:37 am
- Post datetime: 2016-01-12T22:36:41+00:00
- Post Title: NFS Rivals - .itexture

Hello, I am trying to edit some Need for Speed Rivals textures and I need help.

After dumping the game, I have tried to extract/convert the .itexture files, in order to get readable dds files, but I fail. The extracted results are some useless, very strangely proportioned (2048x1 px e.t.c) but with right names, dds files. I have tried using the following tools:
-Bf4 texture converter (Batch_Itexture_Converter_BF4.exe) by Dainiuxxx
-Star Wars Battlefront texture converter (Batch_Itexture_Converter.exe) by Dainiuxxx

Using Ninja Ripper I'm able to get some textures, is there any other way?
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-13T21:40:22+00:00
- Post Title: NFS Rivals - .itexture

[out]
## Post #3
- Username: LALHW
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 10, 2016 8:37 am
- Post datetime: 2016-01-15T19:38:05+00:00
- Post Title: NFS Rivals - .itexture

Yes, I'm using Windows, please check these files, I hope there is everything you need.

NFS - Rivals: [https://mega.nz/#!GQ0hXCgZ!ZM5gaxkHbn8o ... oTRJjFsxaE](https://mega.nz/#!GQ0hXCgZ!ZM5gaxkHbn8o_pUJo9oJ-WBnU_qW-_nLjoTRJjFsxaE), .ebx reffering to file
[https://mega.nz/#!XY0wwCLJ!gKEs2HDs6Ug2 ... DlpWHaZo1U](https://mega.nz/#!XY0wwCLJ!gKEs2HDs6Ug2ABR9zBS4F7H3WjUg7x2NMDlpWHaZo1U), .itexture
[https://mega.nz/#!XJFTwLSa!7NlSWL2g1AdM ... TODuLAC3rg](https://mega.nz/#!XJFTwLSa!7NlSWL2g1AdMubNDOnHUAWoGks3cLRPD7TODuLAC3rg), .chunk file, referred by the .itexture
[https://mega.nz/#!yM90nR6D!xuRKEh_Aatu2 ... -aFvrWF8dU](https://mega.nz/#!yM90nR6D!xuRKEh_Aatu2CGp-sWY8JO6OMod6Pr6Sm-aFvrWF8dU), extracted .dds via Bf4 texture converter 
[https://mega.nz/#!DQUSXS7a!pOSEc2s7kQzB ... 1ZSdz00tB4](https://mega.nz/#!DQUSXS7a!pOSEc2s7kQzBarVKi2kql16pBZMP5JYNI1ZSdz00tB4), the resulted .png after the dds conversion
[https://mega.nz/#!3d1mHLiA!JDxJsv0UbG9m ... RsS4Y_h4C4](https://mega.nz/#!3d1mHLiA!JDxJsv0UbG9mlPBNiCQaCTI9yHIUSlNNBRsS4Y_h4C4), real .dds (converted to png), extracted via Ninja Ripper
[https://mega.nz/#!jRVAjTKR!kPYzQhtZYGse ... 3ME4nKdfyw](https://mega.nz/#!jRVAjTKR!kPYzQhtZYGseEVCbkkKNgvtXDkgOYdTcT3ME4nKdfyw), screenshot from Texture Finder v2.1, showcasing the .chunk file
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-16T01:08:42+00:00
- Post Title: NFS Rivals - .itexture

[out]
## Post #5
- Username: LALHW
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 10, 2016 8:37 am
- Post datetime: 2016-01-16T10:05:59+00:00
- Post Title: NFS Rivals - .itexture

I will try your suggestion. I have found 'DXT5' using a hex editor, but where are the dimensions located? Can I just change the image size using any image editor?
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-16T10:23:28+00:00
- Post Title: NFS Rivals - .itexture

Open car_ford_mustanggt_2014_livery_kenblock_d.dds with a hex editor
put your cursor on byte 0xC and type in 00 08 to overwrite the current values
then put your cursor on byte 0x57 and type in 31 to overwrite the current value
save the file and you are done
## Post #7
- Username: LALHW
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 10, 2016 8:37 am
- Post datetime: 2016-01-16T11:19:16+00:00
- Post Title: NFS Rivals - .itexture

Thank you all, it works for most of the files. But can you please check these files, too? [https://mega.nz/#!qQExlL6J!-f4pirGH0Fa5 ... QVDNu--h4x](https://mega.nz/#!qQExlL6J!-f4pirGH0Fa5gJwYoXqjVsOJb0Y-jy4TQVDNu--h4x)Y It seems it's not working because it's supposed to be a 512px file. Is there any 'map' I should follow for the different image sizes? For example, what should I change for 128px, 256px, 512px e.t.c.?
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-16T12:54:00+00:00
- Post Title: NFS Rivals - .itexture

put your cursor on byte 0xD and type 02 to overwrite 08

all you're doing is taking the image size and converting it to hexadecimal and inputting that value in the right place in little endian byte order.

64 - 40 - 40 00
128 - 80 - 80 00
256 - 100 - 00 01
512 - 200 - 00 02
1024 - 400 - 00 04
2048 - 800 - 00 08
4096 - 1000 - 00 10

height value starts at 0xC and width value starts at 0x10
## Post #9
- Username: LALHW
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 10, 2016 8:37 am
- Post datetime: 2016-01-16T18:57:44+00:00
- Post Title: NFS Rivals - .itexture

THank you, everything is OK now. Final question: is it possible to enable alpha channel this way?
## Post #10
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-16T20:12:56+00:00
- Post Title: NFS Rivals - .itexture

[out]
