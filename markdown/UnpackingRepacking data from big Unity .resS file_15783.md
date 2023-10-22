## Post #1
- Username: ffleader1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 25, 2017 12:19 am
- Post datetime: 2017-01-24T16:49:00+00:00
- Post Title: Unpacking/Repacking data from big Unity .resS file

I have spent a good few hours into this and I still cannot figure how to do this correctly.
I am trying to unpacking (and repacking later if I can unpack the data successfully) some data from a resourse.asset.resS file. I knew that the .resS file is a headerless file and is supposed to go along with the .asset file.
However, the .resS file itself is more than 2GB. I suppose that does not work with some exact tool. 
I have tried:
- Disunity: Giving out "Map fail" Error
- Unity assets explorer: Giving out "Tprogressbar property out of range"
- AssetBundleExtractor: It does read the asset file that goes with the .resS files, but it does not read, exact anything from the .resS file.
- Unity Studio: Does not even read the .asset file.
So as you guys can see, I am kinda out of option here.
I will post the files here:
- resources.asset: [https://drive.google.com/file/d/0B-RJhH ... sp=sharing](https://drive.google.com/file/d/0B-RJhHKhMtEeQ0ZPVzNWbVcwOUU/view?usp=sharing)
- resources.asset.resS: [https://drive.google.com/file/d/0B-RJhH ... sp=sharing](https://drive.google.com/file/d/0B-RJhHKhMtEeb0M4akUwVjEwdUE/view?usp=sharing)
- resources.resource: [https://drive.google.com/file/d/0B-RJhH ... sp=sharing](https://drive.google.com/file/d/0B-RJhHKhMtEeTWxnMDE5WTRsM3c/view?usp=sharing)

And the entire game folder:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/0B-RJhHKhMtEeVFVRa3ZiR1VtVE0?usp=sharing)
Please help.
Thank you in advance.
## Post #2
- Username: ffleader1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 25, 2017 12:19 am
- Post datetime: 2017-01-29T01:19:20+00:00
- Post Title: Unpacking/Repacking data from big Unity .resS file

Bump :<
## Post #3
- Username: ffleader1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 25, 2017 12:19 am
- Post datetime: 2017-01-29T03:24:54+00:00
- Post Title: Unpacking/Repacking data from big Unity .resS file

Solution: Updated version of Unity Assets Bundle Extractor works, with version 2.1_b
