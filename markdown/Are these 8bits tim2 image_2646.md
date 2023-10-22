## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-06T17:57:57+00:00
- Post Title: Are these 8bits tim2 image?

I wonder are these 8bits tim2 image? They seems look OK ingame but not right after extract?

Also, is there any porgram can view tim2 images?

Thanks
[tim2.rar](https://xentaxbackup.github.io/file/1197_tim2.rar)
## Post #2
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-06-08T10:55:30+00:00
- Post Title: Are these 8bits tim2 image?

Hi, 
They are 8 bit images opening as RAW if you enter width size 256x256 for smaller and 512x512 for larger. There is header in each file probable containing palette information. Header for small pic 1280, for larger 1088.
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-08T12:54:51+00:00
- Post Title: Are these 8bits tim2 image?

Thanks for the answer! Xela

But I'm not familiar with 2D format! What do you mean by "Header for small pic 1280, for larger 1088". Are you saying address offset 0x500(1280) etc!? I can't get you!?

I want to get the large image out there. Is there any ready to use program to do this?
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-06-08T20:07:42+00:00
- Post Title: Are these 8bits tim2 image?

Header size means that the picture date starts ater 1280 bytes or 1088 (for larger picture). Begining of the file probable palette. Ypu can open the larger picture as a RAW in greyscale size 512x512 header 1088 . If you convert that to index format and apply extracted palette you should get original picture. I opened both of them , the larger shows some kind of medalion.
## Post #5
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-03-24T03:29:00+00:00
- Post Title: Are these 8bits tim2 image?

I know this is a pretty old topic, but I've been working on a TIM2 tool, so I've been searching for topics here about them and testing all the ones I can find.  Here are the two files decoded -





And here is a screenshot showing each of them in my tool I am working on -



I hope to have my tool released within a couple months.  It's actually made specifically for a certain PS2 game, KOC2, but one of the side benefits, is that it will have a TIM2 tool in it, which will work with any game.  I'll be posting the tool here when it's completed and working well.
