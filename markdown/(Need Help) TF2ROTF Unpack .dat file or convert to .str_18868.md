## Post #1
- Username: Metalado
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 28, 2018 6:36 am
- Post datetime: 2018-09-27T23:16:18+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

Hello Guys, I was visited by the thought of trying to adapt the dlc of console version game to the PC version of the game Transformers 2 revenge of the fallen. I took out all the files from the dlc that were packed in .pkg, but I was faced with one problem, all the files were in the .edat format which was suitable only for the console version of the game, as I understood it. I started looking for methods of decrypting this format, and converting it back to the familiar .str. For a very long time I wandered around the Internet in search of an answer, with help the program edat rebuilder I was convert .edat file into a .dat file format. On this I stopped, I was not able to convert this format into .str. However, I noticed that the file has magic strm (the code header) which is the reverse of the header of the .str - mrts format code. In general, I will be very grateful to people, or a person who will help me understand this, and I would not mind paying for assistance, thanks.
## Post #2
- Username: Metalado
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 28, 2018 6:36 am
- Post datetime: 2018-09-27T23:23:00+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

[https://drive.google.com/open?id=1DrrJ6 ... b3dUqIwxmf](https://drive.google.com/open?id=1DrrJ6eTRojciijwBb7FAQrb3dUqIwxmf) - decrypt files .edat - .dat
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-27T23:56:59+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

The console systems(PS3/Xbox360) use big-endian as byte order, while PC is in little-endian. But I doubt it'll be as simply as a matter of endianness. Most likely they'll modify the format slightly for different platforms.
## Post #4
- Username: Metalado
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 28, 2018 6:36 am
- Post datetime: 2018-09-28T02:17:23+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

> Reply from Bigchillghost
>
> The console systems(PS3/Xbox360) use big-endian as byte order, while PC is in little-endian. But I doubt it'll be as simply as a matter of endianness. Most likely they'll modify the format slightly for different platforms. Very interesting! Thanks for the answer, but I do not understand much about it, unlike you)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-28T03:44:54+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

You'll need to compare the differences between files of the same character from both PC & the console version so the files you uploaded doesn't help much actually. But to be honest, it's no picnic especially if there's no specification about the format.
## Post #6
- Username: Metalado
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 28, 2018 6:36 am
- Post datetime: 2018-09-28T04:58:52+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

> Reply from Bigchillghost
>
> You'll need to compare the differences between files of the same character from both PC & the console version so the files you uploaded doesn't help much actually. But to be honest, it's no picnic especially if there's no specification about the format. Okay, but I thought that these similarities of the  strm mrts code meant something, um, for me it's complicated, I'm far from the code, I can hardly understand it myself, my direction is 3D modeling.
## Post #7
- Username: Metalado
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 28, 2018 6:36 am
- Post datetime: 2018-09-29T00:47:22+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

> Reply from Bigchillghost
>
> You'll need to compare the differences between files of the same character from both PC & the console version so the files you uploaded doesn't help much actually. But to be honest, it's no picnic especially if there's no specification about the format. Can I ask you for help?
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-29T02:11:10+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

> Reply from Metalado
>
> Can I ask you for help?
I remember I tried to extract the character models from the PC version around two years ago, but I gave up eventually due to its messy format, and clearly you can get most of them from TF3. But anyway you'll have to upload the required samples first. I can have a check and see if there're merely changes about the endianness.
## Post #9
- Username: Metalado
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 28, 2018 6:36 am
- Post datetime: 2018-09-29T21:37:33+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

> Reply from Bigchillghost
>
> Metalado wrote:Can I ask you for help?  
I remember I tried to extract the character models from the PC version around two years ago, but I gave up eventually due to its messy format, and clearly you can get most of them from TF3. But anyway you'll have to upload the required samples first. I can have a check and see if there're merely changes about the endianness. Good, then I attach the character file of the PC version of the .str format and from the dlc for the sony format .edat: [https://drive.google.com/open?id=1X3Q7j ... aejNA4_IOn](https://drive.google.com/open?id=1X3Q7jZq1Njc6f4tzyanrvVaejNA4_IOn)
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-30T02:16:05+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

> Reply from Metalado
>
> Good, then I attach the character file of the PC version of the .str format and from the dlc for the sony format .edat
Well, I thought you knew what I was taking about. The files would be comparable only if they're of the SAME character, otherwise it's rather difficult without known the full structure of the file. And I need the decrypted str file of course, not the edat one.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-30T04:38:33+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

OK, I've just downloaded the PS3 version and compared the ratchet models. It seems there's mainly a difference of the endianness, except that the pc version has higher res of textures with slightly different headers.
But even so there're still a lot of work to do. You'll have to research the whole format and figure out all fields of variables, and/or at least their sizes. Working with both PC and PS3 version files can help you do it easier and faster, but it's still rather time consuming. And obviously I don't have the time and passion for it right now.
## Post #12
- Username: Metalado
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 28, 2018 6:36 am
- Post datetime: 2018-09-30T19:44:58+00:00
- Post Title: (Need Help) TF2ROTF: Unpack .dat file or convert to .str

> Reply from Bigchillghost
>
> OK, I've just downloaded the PS3 version and compared the ratchet models. It seems there's mainly a difference of the endianness, except that the pc version has higher res of textures with slightly different headers.
But even so there're still a lot of work to do. You'll have to research the whole format and figure out all fields of variables, and/or at least their sizes. Working with both PC and PS3 version files can help you do it easier and faster, but it's still rather time consuming. And obviously I don't have the time and passion for it right now. Thanks! As there will be time and desire, please write! In debt i will not stay
