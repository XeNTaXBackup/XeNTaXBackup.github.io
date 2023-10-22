## Post #1
- Username: ttruva
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 15, 2016 12:27 am
- Post datetime: 2022-01-13T19:31:46+00:00
- Post Title: ADF Files (Custom Engine)

Hello,

I want to extract some models and I really need for some help. It's an old game developed with a custom engine. 
I've extracted the (.DAT) files with quickbms. So, the file format of the models are .ADF
I've been trying for a long time but I couldn't succeed.
Here are the some screenshots from my experiences with .ADF files and 3D Model Researcher.

[](https://ibb.co/zFnQJ5C)
[](https://ibb.co/th23VVj)
[](https://ibb.co/sQX5bG0)

And this is a screenshot of the model's inside view from the game:
[](https://ibb.co/JqkRcnL)

Btw, this is just a small experience model. I want to extract larger models if I can succeed in this.

If you want to help me about this, you can download the model from the link below:
[https://www113.zippyshare.com/v/T21GGQm3/file.html](https://www113.zippyshare.com/v/T21GGQm3/file.html)

Any help would be greatly appreciated.
All the best!
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-14T15:47:57+00:00
- Post Title: ADF Files (Custom Engine)

Data is compressed. 1st submesh after decompressing the data:



mesh.png (57.53 KiB) Viewed 121 times
## Post #3
- Username: ttruva
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 15, 2016 12:27 am
- Post datetime: 2022-01-14T21:28:24+00:00
- Post Title: ADF Files (Custom Engine)

> Reply from Bigchillghost ↑Fri Jan 14, 2022 11:47 pm at Fri Jan 14, 2022 11:47 pm
>
> 
Data is compressed. 1st submesh after decompressing the data:
mesh.png

Thank you so much.
Is there a resource you can recommend me in this case?
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-15T07:57:42+00:00
- Post Title: ADF Files (Custom Engine)

Use the following BMS script to decompress the file.
[ADF_Decompressor.zip](https://xentaxbackup.github.io/file/21609_ADF_Decompressor.zip)
## Post #5
- Username: ttruva
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 15, 2016 12:27 am
- Post datetime: 2022-01-16T21:17:07+00:00
- Post Title: ADF Files (Custom Engine)

Hello again,

@Bigchillghost thank you so much for your assistance. It was really helpful. I made a lot of progress, thanks to you.

I have a new problem. I can't visualize texture coordinates (UV) properly. I get the error message "Texture Index error!". I read the tutorial page many times, but I couldn't understand what I did wrong. So, I've uploaded some screenshots about my current progress. 
Do you have any ideas on what I'm doing wrong?

[](https://ibb.co/Kyk38PB)
[](https://ibb.co/g950BBs)
[](https://ibb.co/bWcJ2dk)
[](https://ibb.co/84f9bb7)
[](https://ibb.co/CP1GKn7)
[](https://ibb.co/qnjQ1d5)
[](https://ibb.co/Ltm8gQS)
[](https://ibb.co/1djFg6f)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-17T01:43:36+00:00
- Post Title: ADF Files (Custom Engine)

> Reply from ttruva ↑Mon Jan 17, 2022 5:17 am at Mon Jan 17, 2022 5:17 am
>
> 
I can't visualize texture coordinates (UV) properly ...
Do you have any ideas on what I'm doing wrong?
Those are per-face texcoords, meaning that there're (faceCount * 3) UV coordinates. Also there seems to be  2 UV channels so you might need to check the second one as well.
## Post #7
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2022-01-25T20:06:04+00:00
- Post Title: ADF Files (Custom Engine)

> Reply from ttruva ↑Mon Jan 17, 2022 5:17 am at Mon Jan 17, 2022 5:17 am
>
> 
Hello again,

@Bigchillghost thank you so much for your assistance. It was really helpful. I made a lot of progress, thanks to you.

I have a new problem. I can't visualize texture coordinates (UV) properly. I get the error message "Texture Index error!". I read the tutorial page many times, but I couldn't understand what I did wrong. So, I've uploaded some screenshots about my current progress. 
Do you have any ideas on what I'm doing wrong?

Lol. Errors in the program are very informative.
