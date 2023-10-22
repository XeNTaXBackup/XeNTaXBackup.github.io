## Post #1
- Username: whogivesaskit
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Apr 19, 2006 10:57 pm
- Post datetime: 2006-04-19T15:01:16+00:00
- Post Title: Wwe Raw 2 question

well sorta

i wanted to know where all the names are stored such as finisher names and various other things i found some of them but can't find finisher names

i think it's in the caw.bin file but can't open it with any .bin extractor

any help?

thx in advance

also is there an fml editor out there?
[caw.rar](https://xentaxbackup.github.io/file/708_caw.rar)
## Post #2
- Username: whogivesaskit
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Apr 19, 2006 10:57 pm
- Post datetime: 2006-04-21T06:48:12+00:00
- Post Title: Wwe Raw 2 question

noone know?

i really need to know how to open the model/animation files called .fml files if u need any sample file i'd be glad to give

i can open everything cept those files
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-21T08:50:23+00:00
- Post Title: Wwe Raw 2 question

The names of characters are indeed stored in caw.bin,
i dont know any editor yet that might be able to edit them
except for using a Generic Hexeditor, then just scan the file
with your eyes and edit the parts you want =D

it should be pretty easy, if you are used to hexxing.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-21T09:59:50+00:00
- Post Title: Wwe Raw 2 question

The names are in there, use this script in MultiEx Commander

```
GoTo EOF 0 ;
SavePos ASI 0 ;
GoTo SOF 0 ;
Do ;
SavePos FO 0 ;
Set FN String .DCOM ;
Get F String 0 ;
String F += FN ;
Log F FO Size 0 0 ;
Math FO += Size ;
GoTo FO 0 ;
While FO < ASI ;

```


This will extract the DCOM files (I think that's what they are for each character). The filenames are a bit screwed, that's how they are saved in there. 

Get the ready-to-use BMS below. 

The TOC from MultiEx Commander:

```
-----------------------------------
D:\Downloads\caw\caw.bin
Number of resources: 64
TOC Created on: 21-4-2006 at 12:57:13
-----------------------------------
Filename	Type	Size	Offset
TheÂ
```

[bin.zip](https://xentaxbackup.github.io/file/715_bin.zip)
## Post #5
- Username: whogivesaskit
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Apr 19, 2006 10:57 pm
- Post datetime: 2006-04-22T00:42:19+00:00
- Post Title: Wwe Raw 2 question

Awsome it worked

 is that where the finisher names/move names are located also?

and any news on the fml files?
[OB_chair.rar](https://xentaxbackup.github.io/file/719_OB_chair.rar)
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-23T07:23:59+00:00
- Post Title: Wwe Raw 2 question

whats fml? =o

you have a sample file for that? (sounds like a variation of an XML file)
## Post #7
- Username: whogivesaskit
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Apr 19, 2006 10:57 pm
- Post datetime: 2006-04-23T23:24:25+00:00
- Post Title: Wwe Raw 2 question

yea here's the sample file it's an exclusive file style for wwe raw 2 for xbox it's the model files land object's such as chair superstar and animation such as entrance style walks blah blah blah

the file's up there OB-Chair just ask if u need more i ahve lots more
## Post #8
- Username: whogivesaskit
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Apr 19, 2006 10:57 pm
- Post datetime: 2006-05-29T23:40:28+00:00
- Post Title: Wwe Raw 2 question

been a long time since i posted any news yet on the fml files?
