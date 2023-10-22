## Post #1
- Username: Wolyafa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 04, 2018 1:33 am
- Post datetime: 2020-04-28T14:49:45+00:00
- Post Title: Trails of Mana Sound Effect files .uexp .uasset

Hello Everyone!

I was wondering if there's a way to convert the music and sound files from the game into mp3 or similar...

The game uses Unreal engine 4.22 and file extensions are .uasset and .uexp

see the zip package ~

[https://drive.google.com/file/d/1fX0WXV ... cs5fN/view](https://drive.google.com/file/d/1fX0WXVxlj9_3QdYN6PyF04cTcFecs5fN/view)

Thanks in advance for any help / tools that work!
## Post #2
- Username: HijackTheRipper
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Aug 29, 2014 9:28 pm
- Post datetime: 2020-05-04T17:14:10+00:00
- Post Title: Trails of Mana Sound Effect files .uexp .uasset

There are lot simply ways to get the music without extraction specially if you could avoid unity files  :wink:
## Post #3
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-05-05T17:13:51+00:00
- Post Title: Trails of Mana Sound Effect files .uexp .uasset

> Reply from Wolyafa ↑Tue Apr 28, 2020 10:49 pm at Tue Apr 28, 2020 10:49 pm
>
> I was wondering if there's a way to convert the music and sound files from the game into mp3 or similar...
If its BGM just delete everything in hex until you reach its header 6D616266 (mabf) and rename extension to MAB.
If its VO/FX delete everything till you reach its header 73616266 (sabf) and rename extension to SAB.
And after that, for both formats, make sure you delete its last 4 trailing bytes C1832A9E to play/convert them in foobar2000/vgmstream combo.

have fun
## Post #4
- Username: HijackTheRipper
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Aug 29, 2014 9:28 pm
- Post datetime: 2020-05-12T08:01:54+00:00
- Post Title: Trails of Mana Sound Effect files .uexp .uasset

@mono24

Did this method works for all .uasset files or only for files from the game above?
