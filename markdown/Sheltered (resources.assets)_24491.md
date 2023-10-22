## Post #1
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2021-09-13T18:58:47+00:00
- Post Title: Sheltered (resources.assets)

Hello

I think the text file of the game Sheltered is in the "resources.assets" file. I checked on the internet if there is a translation for my local language, it is, but it is compatible for the STEAM version. Work on the EPIC version hasn't even started yet.
I want to translate it myself, but my programming knowledge is almost zero. I need your help for this. I could not open "resources.assets" file with "Assest Explorer". I am sharing the file below.

[https://drive.google.com/file/d/1s-yDNh ... 3BMoH/view](https://drive.google.com/file/d/1s-yDNhT476mf4wt3lxypWmREH963BMoH/view)
## Post #2
- Username: UtkuGARIP
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-13T20:56:34+00:00
- Post Title: Sheltered (resources.assets)

Hi, it seems that it is standard Unity 5 assets archive (version 17) [http://wiki.xentax.com/index.php/Unity_Assets](http://wiki.xentax.com/index.php/Unity_Assets)

You can edit it with UnityEx or with Unity Assets Explorer [https://i.imgur.com/1OUEt7D.png](https://i.imgur.com/1OUEt7D.png)
## Post #3
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2021-09-14T10:31:04+00:00
- Post Title: Sheltered (resources.assets)

> Reply from ikskoks ↑Tue Sep 14, 2021 4:56 am at Tue Sep 14, 2021 4:56 am
>
> 
Hi, it seems that it is standard Unity 5 assets archive (version 17) http://wiki.xentax.com/index.php/Unity_Assets

You can edit it with UnityEx or with Unity Assets Explorer https://i.imgur.com/1OUEt7D.png

Thank you bro
## Post #4
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2021-09-14T13:48:43+00:00
- Post Title: Sheltered (resources.assets)

With UnityEX 1.8.9.4 I opened the "resources.assets" file and was able to extract the "Localization.txt" file, but the "Localization.txt" file looks like an "Excel" table, it looks complicated when opened with Notepad. I thought I should convert and edit an Excel file (.xlsx) but failed.
Do you know how to edit the "Localization.txt" file tidily?



[https://drive.google.com/file/d/1uD-Qhf ... ifPdy/view](https://drive.google.com/file/d/1uD-Qhfnfw_olzXOpIYojNpBeyFGifPdy/view)

Also, there are many text files of the same complexity.
## Post #5
- Username: UtkuGARIP
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-14T20:22:41+00:00
- Post Title: Sheltered (resources.assets)

Well, you can do what you want in few steps:
1. Change file extension from TXT to CSV
2. Open CSV in Notepad++ and raplace all tabs with semicolons    "\t" --> ";"  (or just select tab as delimeter in the next step)
3. Load data in excel as it is in this tutorial [https://www.unisender.com/en/support/co ... set-utf-8/](https://www.unisender.com/en/support/contact-lists/import-contact/charset-utf-8/)
4. Save your file as XLSX file. Your  output file will be formatted like this [https://i.imgur.com/6DByNw0.png](https://i.imgur.com/6DByNw0.png)


But I think that it may not be the best solution. 
The better one would be load TXT file in OmegaT [https://omegat.org/download](https://omegat.org/download)
and set proper segmentation options (break segment after tab etc.).
Then you'll translate the text in OmegaT directly and export it to TXT with the same encoding.
## Post #6
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2021-09-14T22:44:29+00:00
- Post Title: Sheltered (resources.assets)

> Reply from ikskoks ↑Wed Sep 15, 2021 4:22 am at Wed Sep 15, 2021 4:22 am
>
> 
Well, you can do what you want in few steps:
1. Change file extension from TXT to CSV
2. Open CSV in Notepad++ and raplace all tabs with semicolons    "\t" --> ";"  (or just select tab as delimeter in the next step)
3. Load data in excel as it is in this tutorial https://www.unisender.com/en/support/co ... set-utf-8/
4. Save your file as XLSX file. Your  output file will be formatted like this https://i.imgur.com/6DByNw0.png


But I think that it may not be the best solution. 
The better one would be load TXT file in OmegaT https://omegat.org/download
and set proper segmentation options (break segment after tab etc.).
Then you'll translate the text in OmegaT directly and export it to TXT with the same encoding.

If you don't mind, can you explain with pictures in your spare time? The OmegaT method seems simpler.
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-15T08:50:53+00:00
- Post Title: Sheltered (resources.assets)

> If you don't mind, can you explain with pictures in your spare time?
Sure, here you go:

1. Download OmegaT [https://omegat.org/download](https://omegat.org/download)
2. Go to Project > New [https://i.imgur.com/fNQl1mr.png](https://i.imgur.com/fNQl1mr.png)
3. Copy "Localization.txt" to "source" folder in your project location.
4. Go to Project > Properties > Segmentation settings and do it like this [https://i.imgur.com/caMR2mi.png](https://i.imgur.com/caMR2mi.png)
5. And you'll get this result [https://i.imgur.com/qEFGLcG.png](https://i.imgur.com/qEFGLcG.png)

Also few notes about above:
- You may want to split your TXT files to avoid parsing errors from OmegaT (if the file is too big)
- You can do some tricks to get only english text to translate, but that would require some programming knowledge or using excel as was already mentioned. 
- Of course you can set segmentation as you wish. Above is only example.
## Post #8
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2021-09-15T10:22:16+00:00
- Post Title: Sheltered (resources.assets)

I made it! Thank you very much for your help. I'll start the translation right away.
