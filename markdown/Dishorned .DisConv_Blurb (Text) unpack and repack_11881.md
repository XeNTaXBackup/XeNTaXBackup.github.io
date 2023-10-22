## Post #1
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-09-02T13:27:26+00:00
- Post Title: Dishorned *.DisConv_Blurb (Text) unpack and repack

Hi all! I have a problem with .DisConv_Blurb in this game! I unpack sucessfully upk file with that game and found .DisConv_Blurb file. This have text. Like this:



Can you help me unpack and repack text in this file? I try to change it in Hex and game crash! @@
Thanks in advance!
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-09-02T18:17:38+00:00
- Post Title: Dishorned *.DisConv_Blurb (Text) unpack and repack

Just compare that .texture2D and .dds files. You will notice that .texture2D has another "head" (probably 0x301 bytes long) and also "tail" (0x38 bytes long). Data between head and tail should be the same as in .DDS (after 0x80 bytes long DDS head).
## Post #3
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-09-03T16:31:30+00:00
- Post Title: Dishorned *.DisConv_Blurb (Text) unpack and repack

> Reply from merlinsvk
>
> Just compare that .texture2D and .dds files. You will notice that .texture2D has another "head" (probably 0x301 bytes long) and also "tail" (0x38 bytes long). Data between head and tail should be the same as in .DDS (after 0x80 bytes long DDS head).

Thanks! are they same while in a game? I unpacked *.upk and found .DisConv_Blurb file. This have text. Like this:



Can you help me unpack and repack text in this file? I try to change it in Hex and game crash! @@
Thanks in advance!
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-09-03T21:27:09+00:00
- Post Title: Dishorned *.DisConv_Blurb (Text) unpack and repack

Well, your original question was about textures. I can't help you with texts.
## Post #5
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-09-05T06:27:32+00:00
- Post Title: Dishorned *.DisConv_Blurb (Text) unpack and repack

> Reply from merlinsvk
>
> Well, your original question was about textures. I can't help you with texts.

Thanks! This game have about 20000 file *.DisConv_Blurb. That so sad! @@
