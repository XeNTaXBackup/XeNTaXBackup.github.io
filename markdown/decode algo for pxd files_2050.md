## Post #1
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2006-08-19T21:52:43+00:00
- Post Title: decode algo for pxd files

hi there 

im not sure if this is the right place to ask, but i give it a try anyway

i'm trying to make a decode algo for the ejay pxd file format that is compressed audio in some way, so far i found that its always 44100 hz 16 bit mono.

any help is appreciatet 

cheers FunteX!
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-19T22:04:41+00:00
- Post Title: decode algo for pxd files

can attach a example/sample?

thanks
## Post #3
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2006-08-20T11:31:10+00:00
- Post Title: decode algo for pxd files

sure  

here it is...
## Post #4
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2006-08-20T11:34:38+00:00
- Post Title: decode algo for pxd files

....
[DC.rar](https://xentaxbackup.github.io/file/811_DC.rar)
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-20T14:03:30+00:00
- Post Title: decode algo for pxd files

Well examining the file appears:

```
tPxD'suck bass  Rave eJay 
```


looking for the net i found this (maybe help, maybe not..) 
[http://www.01net.com/telecharger/window ... 26507.html](http://www.01net.com/telecharger/windows/Multimedia/edition_audio/fiches/26507.html)
[http://www.pearl.fr/article-H696.html](http://www.pearl.fr/article-H696.html)

Looks a sample of this program (Rave Ejay) , maybe you can try to see if can decode to wav pcm

Anyway still searching  

PS: Are you in reversing.be?
## Post #6
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2006-08-20T14:15:18+00:00
- Post Title: decode algo for pxd files

in a file called pxd32d5.dll is there a function to encode wav to pxd, and i just figured out the parametres - i can make a little wav to pxd converter, if this is to any help? 

yes, i'm in reversing.be forum too
## Post #7
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2006-08-20T18:01:38+00:00
- Post Title: decode algo for pxd files

heres the file i talked about...  source included (Delphi 7)
[pxd32d5 dll call test.part1.rar](https://xentaxbackup.github.io/file/814_pxd32d5 dll call test.part1.rar)
## Post #8
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2006-08-20T18:02:22+00:00
- Post Title: decode algo for pxd files

...
[pxd32d5 dll call test.part2.rar](https://xentaxbackup.github.io/file/815_pxd32d5 dll call test.part2.rar)
