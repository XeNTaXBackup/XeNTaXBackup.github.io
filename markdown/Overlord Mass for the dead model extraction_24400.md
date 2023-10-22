## Post #1
- Username: TheZoroark007
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 16, 2019 1:14 am
- Post datetime: 2021-08-26T10:20:11+00:00
- Post Title: Overlord "Mass for the dead" model extraction

Hello everyone.
I tried to dump some models from the Android version of the mobile Game "Mass for the dead". Since this game seems to be made with unity, I thought that extracting character models should be easy. Saddly, the unity files don´t seem to open in any extractor program. 

According to this topic ([https://zenhax.com/viewtopic.php?t=13304](https://zenhax.com/viewtopic.php?t=13304)), it seems that the files are somehow encrypted. However, running the script provided in that thread only results in a 0kb file.

Does anyone have an idea if it is possible to get the content of these files ? Two example files are provided in the  attatched file
[Archive.zip](https://xentaxbackup.github.io/file/20691_Archive.zip)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-26T12:48:39+00:00
- Post Title: Overlord "Mass for the dead" model extraction

The xor key is slightly different. Use this BMS script to decrypt it:


 dec.zip
(247 Bytes) Downloaded 72 times
## Post #3
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-08-26T13:05:37+00:00
- Post Title: Overlord "Mass for the dead" model extraction

If I remember correctly, each file has a different key. I think the length was also different for each file.
## Post #4
- Username: TheZoroark007
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 16, 2019 1:14 am
- Post datetime: 2021-08-26T14:16:11+00:00
- Post Title: Overlord "Mass for the dead" model extraction

> Reply from Bigchillghost ↑Thu Aug 26, 2021 8:48 pm at Thu Aug 26, 2021 8:48 pm
>
> 
The xor key is slightly different. Use this BMS script to decrypt it:
dec.zip
Thank you very much. This script seems to work for around half of all files. Would there be a way for me to adapt this script to work with the other files ?

If it helps, I uploaded all the files here: [https://drive.google.com/file/d/110EFGy ... sp=sharing](https://drive.google.com/file/d/110EFGyXLlQrQEU6PCFehZkXL_AB_1GjU/view?usp=sharing)

> Reply from einherjar007 ↑Thu Aug 26, 2021 9:05 pm at Thu Aug 26, 2021 9:05 pm
>
> 
If I remember correctly, each file has a different key. I think the length was also different for each file.
It seems that some files share the same key, but I´m afraid you are right. Saddly, I have no idea how one would figure out all the other keys.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-26T17:18:21+00:00
- Post Title: Overlord "Mass for the dead" model extraction

Here's the modified script which'll adjust the key dynamically:


 AdaptiveKeyDec.zip
(511 Bytes) Downloaded 93 times



Tested on a couple of files only.
## Post #6
- Username: TheZoroark007
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 16, 2019 1:14 am
- Post datetime: 2021-08-26T20:50:14+00:00
- Post Title: Overlord "Mass for the dead" model extraction

> Reply from Bigchillghost ↑Fri Aug 27, 2021 1:18 am at Fri Aug 27, 2021 1:18 am
>
> 
Here's the modified script which'll adjust the key dynamically:
AdaptiveKeyDec.zip


Tested on a couple of files only.

Thank you, that seems to work for some more files. But on other files, I get errors like this:
[https://imgur.com/a/kWfDcCH](https://imgur.com/a/kWfDcCH)
(The file I used for this was "0a203d5b0df03e15f59fa96bb3bc48a9cecff498" in the "u" folder (The one I think the character-models are located in))
If I now change that header accordingly in a hex editor, the file seems to be accepted by the script, but it isn´t decrypted properly and won´t open in any program
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-27T12:09:43+00:00
- Post Title: Overlord "Mass for the dead" model extraction

Script updated at the same post.
## Post #8
- Username: TheZoroark007
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 16, 2019 1:14 am
- Post datetime: 2021-08-28T09:08:37+00:00
- Post Title: Overlord "Mass for the dead" model extraction

> Reply from Bigchillghost ↑Fri Aug 27, 2021 8:09 pm at Fri Aug 27, 2021 8:09 pm
>
> 
Script updated at the same post.
That worked very well. I finally got my model. Thank you very much
## Post #9
- Username: TheEleh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 01, 2021 9:04 am
- Post datetime: 2021-11-01T02:29:17+00:00
- Post Title: Overlord "Mass for the dead" model extraction

> Reply from TheZoroark007 ↑Sat Aug 28, 2021 5:08 pm at Sat Aug 28, 2021 5:08 pm
>
> 
Bigchillghost wrote: ↑Fri Aug 27, 2021 8:09 pm
Script updated at the same post.

That worked very well. I finally got my model. Thank you very much

Hi,

I'm also interested in getting a hold of the models here and was able to use the script just fine and managed to convert everything to an ASSET file. For some reason, though, I can't get anything like AssetStudio to open them. How did you manage to get your model?

Thanks in advance.
## Post #10
- Username: josek610
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 05, 2021 12:58 am
- Post datetime: 2021-11-04T19:15:39+00:00
- Post Title: Overlord "Mass for the dead" model extraction

I have the same issue. Neither AssetStudio or Asset Bundle Extractor recognise the decrypted files. Did someone know why this happen?
I'm using the latest JP version files.
## Post #11
- Username: VVP
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 25, 2021 3:06 pm
- Post datetime: 2021-12-01T05:15:14+00:00
- Post Title: Overlord "Mass for the dead" model extraction

Hi, I have notice that they where only some files in your folder and some people have not been able to open the some archives.

In this topic [https://zenhax.com/viewtopic.php?f=5&t=16111](https://zenhax.com/viewtopic.php?f=5&t=16111) I comment about my dificult to get all the assets for the game, how I got them and where to find them. The person how iniciate the topic shared an altered file that can decrypt many files of the game (infortunetely not all, he used this script as well). I have tested the extrated models and and it work well when open with the AssetStudio.

I hope that it can help the people that are having problems.
## Post #12
- Username: Helionmatrix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 26, 2023 11:57 am
- Post datetime: 2023-07-14T01:46:18+00:00
- Post Title: Overlord "Mass for the dead" model extraction

Hello I just want to know if you still have the step by step guide on how to extract data from Mass for the dead cause Zenhax is having a problem now and I can't browse the site of that page. Thank you in advance.
## Post #13
- Username: DTower
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 06, 2021 3:45 pm
- Post datetime: 2023-07-23T06:06:03+00:00
- Post Title: Overlord "Mass for the dead" model extraction

yes, unable to open the page site as well, maybe it is closed by the author or what, also, the script seems fine, as least by checking hex, it worked with some files, not sure how many %, maybe around 35-50%. Also, asset deciphered is not easily opened by the AssetStudio, do not know what do to with it right, still finding, if anyone can share a way or reopen the site, or paste site to another place.
