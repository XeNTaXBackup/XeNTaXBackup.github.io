## Post #1
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-10-26T18:42:38+00:00
- Post Title: Kamen Rider City Wars - Android

I need help or suggestions to extract this new game from Bandai, Kamen Rider City Wars, I've never seen this type of format before. The templates are in this path "com.bandainamcoent.citywars \ files \ dl \ assets". Thanks.

[http://www.mediafire.com/file/cck70psan ... tywars.rar](http://www.mediafire.com/file/cck70psansbl7yt/com.bandainamcoent.citywars.rar)

Samples: [http://www.mediafire.com/file/av1se3oia ... 0009_9.rar](http://www.mediafire.com/file/av1se3oiap2z57e/g3d_chara_B00009_9.rar)
## Post #2
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-11-10T06:33:11+00:00
- Post Title: Kamen Rider City Wars - Android

After much research I discovered that this new system of Bandai, "Genki Engine" is impossible to extract. The only way to get the models right now is to use Ninja Ripper.
## Post #3
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2018-03-24T01:31:05+00:00
- Post Title: Kamen Rider City Wars - Android

What emulator program did you used? BlueStacks or nox? And did you download this Kamen rider game through qoo app or just download directly from the source? I couldn't get anything out from this game with ninja ripper through Nox emulator and I have to download game through qoo app. Thank you in advance. I am appreciate all the help from you.
## Post #4
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-03-28T12:52:11+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from sasimiv11
>
> What emulator program did you used? BlueStacks or nox? And did you download this Kamen rider game through qoo app or just download directly from the source? I couldn't get anything out from this game with ninja ripper through Nox emulator and I have to download game through qoo app. Thank you in advance. I am appreciate all the help from you.

I used this method: [https://www.youtube.com/watch?v=Dp90rbVntb0](https://www.youtube.com/watch?v=Dp90rbVntb0)
Some tips, disable your antivirus to do the procedure, do not use the intruder inject, this works for Bluestacks too.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T16:04:32+00:00
- Post Title: Kamen Rider City Wars - Android

Model format is simple:



kamen.jpg (90.28 KiB) Viewed 707 times



Bone indices and weights are also easy to located. Should not be difficult to extract bones.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-29T05:01:32+00:00
- Post Title: Kamen Rider City Wars - Android

And the texture is in 16 bit RGB(565) format, with raw pixel data starting from 0xA4.



APL01_CO.png (213.02 KiB) Viewed 701 times
## Post #7
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-03-29T17:02:29+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from Bigchillghost
>
> Model format is simple:
kamen.jpg

Bone indices and weights are also easy to located. Should not be difficult to extract bones.

Amazing!!! Would you explain how to do this procedure?
## Post #8
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-03-29T19:50:10+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from Bigchillghost
>
> And the texture is in 16 bit RGB(565) format, with raw pixel data starting from 0xA4.
APL01_CO.png

Is it possible to explain the procedure for extraction? A tutorial with description and pictures would help.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-30T02:52:33+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from dswd2015
>
> 
Amazing!!! Would you explain how to do this procedure?

So I guess you know little about using Hex2Obj, and lack for some basic knowledge.
If you're completely new to this area, I suggest you to learn from the basis. 
See the link at my signature.

If you have any questions on any parts of the tutorial, I'd be glad to explain.
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-30T03:18:39+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from dswd2015
>
> 
Is it possible to explain the procedure for extraction? A tutorial with description and pictures would help.
Sure. That would be easy. Basic structure for the texture file:

```

0x8B		Long		ImageWidth
0x8F		Long		ImageHeight
0x9C		Long		RawPixelDataSize
0xA0		Bytes		RawPixelData
```


The pixel data actually begins at 0xA0 (= 160), not 0xA4 I mentioned earlier.
You can wrap the data with PVRTexTool like this:



WrapRawData.png (255.66 KiB) Viewed 676 times


It's no a problem to write a script for conversion when you know the above info.
But with only one texture file the research might not be accurate.
## Post #11
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-03-30T03:21:51+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from Bigchillghost
>
> dswd2015 wrote:
Amazing!!! Would you explain how to do this procedure?

So I guess you know little about using Hex2Obj, and lack for some basic knowledge.
If you're completely new to this area, I suggest you to learn from the basis. 
See the link at my signature.

If you have any questions on any parts of the tutorial, I'd be glad to explain.

Thanks, I'll follow your advice and read the tutorial.
## Post #12
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-03-30T07:26:37+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from Bigchillghost
>
> dswd2015 wrote:
Amazing!!! Would you explain how to do this procedure?

So I guess you know little about using Hex2Obj, and lack for some basic knowledge.
If you're completely new to this area, I suggest you to learn from the basis. 
See the link at my signature.

If you have any questions on any parts of the tutorial, I'd be glad to explain.

I tried to understand the tutorial but it still seems very difficult, sorry for that but could you create an example based specifically on this template? My question is about the procedure in hex edit, I suppose you need to do calculations, could you help me? Thanks again.

Samples: [http://www.mediafire.com/file/kndzni07i ... 0007_7.rar](http://www.mediafire.com/file/kndzni07iktgh37/MDL__B00007_7.rar)
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-30T10:26:34+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from dswd2015
>
> 
I tried to understand the tutorial but it still seems very difficult
Have you read them in order? Or you skipped the background knowledge part? This is very important, without which you can't go much further.

> Reply from dswd2015
>
> 
could you create an example based specifically on this template?
Sorry, no time for that now.

> Reply from dswd2015
>
> My question is about the procedure in hex edit, I suppose you need to do calculations, could you help me?
Which step confused you? You only need to understand why you need to do such calculations as shown in the tutorial, and leave the rest to the calculator.
## Post #14
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-03-30T11:46:29+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from Bigchillghost
>
> dswd2015 wrote:
I tried to understand the tutorial but it still seems very difficult
Have you read them in order? Or you skipped the background knowledge part? This is very important, without which you can't go much further.
dswd2015 wrote:
could you create an example based specifically on this template? 

Sorry, no time for that now.
dswd2015 wrote:My question is about the procedure in hex edit, I suppose you need to do calculations, could you help me? 
Which step confused you? You only need to understand why you need to do such calculations as shown in the tutorial, and leave the rest to the calculator.

I read the tutorial, all the parts, until I got to the hex edit, I downloaded the sample files but I could not understand the final procedure. Sorry to take your time, do not worry, I will not ask any more questions.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-30T13:08:42+00:00
- Post Title: Kamen Rider City Wars - Android

> Reply from dswd2015
>
> 
I read the tutorial, all the parts
Then simple questions: do you understand the concepts of different data types? Do you realize what hexadecimal system is?

> Reply from dswd2015
>
> Sorry to take your time, do not worry, I will not ask any more questions.
Don't get me wrong, but I have no time writing another tutorial based on another example right now coz I'm occupied with a personal project at the moment. 
Actually questioning is not some annoying things, but the necessary access to learning, only if you know what to question.

> Reply from dswd2015
>
> until I got to the hex edit, I downloaded the sample files but I could not understand the final procedure.
As mentioned above, put forward specific questions so that people will know what you're actually confused about.
## Post #16
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-03-30T13:14:17+00:00
- Post Title: Re: Kamen Rider City Wars - Android

> Reply from Bigchillghost
>
> dswd2015 wrote:
I read the tutorial, all the parts
Then simple questions: do you understand the concepts of different data types? Do you realize what hexadecimal system is?
dswd2015 wrote:Sorry to take your time, do not worry, I will not ask any more questions.
Don't get me wrong, but I have no time writing another tutorial based on another example right now coz I'm occupied with a personal project at the moment. 
Actually questioning is not some annoying things, but the necessary access to learning, only if you know what to question.
dswd2015 wrote:until I got to the hex edit, I downloaded the sample files but I could not understand the final procedure. 
As mentioned above, put forward specific questions so that people will know what you're actually confused about.

No problem, I could not understand the hexadecimal concept, I thank you for your help.
## Post #17
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-03-31T23:59:12+00:00
- Post Title: Re: Kamen Rider City Wars - Android

> Reply from Bigchillghost
>
> dswd2015 wrote:
I read the tutorial, all the parts
Then simple questions: do you understand the concepts of different data types? Do you realize what hexadecimal system is?
dswd2015 wrote:Sorry to take your time, do not worry, I will not ask any more questions.
Don't get me wrong, but I have no time writing another tutorial based on another example right now coz I'm occupied with a personal project at the moment. 
Actually questioning is not some annoying things, but the necessary access to learning, only if you know what to question.
dswd2015 wrote:until I got to the hex edit, I downloaded the sample files but I could not understand the final procedure. 
As mentioned above, put forward specific questions so that people will know what you're actually confused about.

Hey dude, I figured out how to do it, thank you very much for your help, mainly for solving the texture problem, thank you very much.
## Post #18
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-04-01T03:21:57+00:00
- Post Title: Re: Kamen Rider City Wars - Android

> Reply from Bigchillghost
>
> dswd2015 wrote:
Is it possible to explain the procedure for extraction? A tutorial with description and pictures would help.
Sure. That would be easy. Basic structure for the texture file:
Code: Select allOffset		Type		Specification

0x8B		Long		ImageWidth
0x8F		Long		ImageHeight
0x9C		Long		RawPixelDataSize
0xA0		Bytes		RawPixelData

The pixel data actually begins at 0xA0 (= 160), not 0xA4 I mentioned earlier.
You can wrap the data with PVRTexTool like this:
WrapRawData.png
It's no a problem to write a script for conversion when you know the above info.
But with only one texture file the research might not be accurate.

I still have a question, do these values shown in the image need to be calculated to arrive at this result?
## Post #19
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-01T03:51:57+00:00
- Post Title: Re: Kamen Rider City Wars - Android

You can see that the pixel data can be aligned for every two bytes so it's 16 bits per pixel for sure.



16bit.jpg (27.14 KiB) Viewed 419 times


Then you just have to weigh how many bits should be assigned to each channel. Basically it's a test and verify process. But there should be some fields specifying the format in the header. 
Usually it would be some enum values mapping to different formats. But to figure it out, you'll need to work with more samples.
## Post #20
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2018-04-15T01:05:53+00:00
- Post Title: Re: Kamen Rider City Wars - Android

I got the models from this game now. Thank you very much for your help. BTW I used noesis to convert those texture from dds to png.
## Post #21
- Username: whs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 28, 2017 5:07 pm
- Post datetime: 2018-10-19T16:38:48+00:00
- Post Title: Re: Kamen Rider City Wars - Android

Do you have a build geniuses model?
## Post #22
- Username: whs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 28, 2017 5:07 pm
- Post datetime: 2018-10-19T16:51:43+00:00
- Post Title: Re: Kamen Rider City Wars - Android

How do I extract models?
## Post #23
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2019-07-20T09:39:43+00:00
- Post Title: Re: Kamen Rider City Wars - Android

So it's possible to rip models from this game. but what about voice files?
## Post #24
- Username: wpw610
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 29, 2019 4:26 pm
- Post datetime: 2019-12-29T08:35:23+00:00
- Post Title: Re: Kamen Rider City Wars - Android

voice can be read by audacity directly.
## Post #25
- Username: asdzx34
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 16, 2019 6:52 pm
- Post datetime: 2020-05-04T23:44:14+00:00
- Post Title: Re: Kamen Rider City Wars - Android

I used a ninjaripper.
I can't extract the model.
What should I do?
## Post #26
- Username: Misawa Hajime
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 23, 2014 3:23 pm
- Post datetime: 2021-03-13T04:53:11+00:00
- Post Title: Re: Kamen Rider City Wars - Android

> Reply from sasimiv11 ↑Sun Apr 15, 2018 9:05 am at Sun Apr 15, 2018 9:05 am
>
> 
I got the models from this game now. Thank you very much for your help. BTW I used noesis to convert those texture from dds to png.

hye do you still have the Bms script for the model extracting...
## Post #27
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2021-05-04T09:18:19+00:00
- Post Title: Re: Kamen Rider City Wars - Android

> Reply from Misawa Hajime ↑Sat Mar 13, 2021 12:53 pm at Sat Mar 13, 2021 12:53 pm
>
> 
sasimiv11 wrote: ↑Sun Apr 15, 2018 9:05 am
I got the models from this game now. Thank you very much for your help. BTW I used noesis to convert those texture from dds to png.


hye do you still have the Bms script for the model extracting...

I have script! Have you city wars's data file in 0/data/data/com.bandai~? I need it. If you can share this, I can share script!
## Post #28
- Username: wjj162446
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 10, 2019 7:01 pm
- Post datetime: 2023-10-19T09:17:45+00:00
- Post Title: Re: Kamen Rider City Wars - Android

Is there anybody know how to extract Kamen Rider Gotchard File game?
