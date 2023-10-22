## Post #1
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2021-07-19T02:23:18+00:00
- Post Title: jubeat .VA3 extract??

i tried to extract any jubeat games (.VA3), & get this error [https://imgur.com/omylmus](https://imgur.com/omylmus), with what do I extract?, with another program? or this: [https://github.com/fisyher/gitadora-customs](https://github.com/fisyher/gitadora-customs) (it is very hard to compile with python)

here the link: [https://mega.nz/file/bIgT2aAK#FN8TgPyjD ... m0ZXZBHNBk](https://mega.nz/file/bIgT2aAK#FN8TgPyjDXNGHKNuzYvw5DeeyxCYMyv8am0ZXZBHNBk)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-19T21:26:10+00:00
- Post Title: jubeat .VA3 extract??

vas3tool.py from "gitadora-customs" toolkit works well with your samples.
It's not very hard to compile in Python, because you don't need to compile at all.   

First you need to install Python 3, then get all required libs with this command:

```
python -m pip install -r requirements.txt
```


And then you can use tool like this:

```
python vas3tool.py --extract -g guitar -i l44ff_entry.va3 -o entry_out
```
## Post #3
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2021-07-20T02:29:38+00:00
- Post Title: jubeat .VA3 extract??

with cmd or Python 3?? (i have python 3)
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-20T07:23:13+00:00
- Post Title: jubeat .VA3 extract??

Both commands with cmd.
