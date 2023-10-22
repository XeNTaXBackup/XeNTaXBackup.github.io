## Post #1
- Username: Dekill93
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 27, 2019 6:28 pm
- Post datetime: 2019-07-09T20:23:34+00:00
- Post Title: Help me to translate this code

Can anyone help me to translate this code... I want to change 30fps to 60fps on asphalt 9
[GameOptions.json.zip](https://xentaxbackup.github.io/file/16450_GameOptions.json.zip)
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-07-17T07:36:42+00:00
- Post Title: Help me to translate this code

Starts at line 358: render_allowedFPS
Have you tried to change "60" to just 60 at next line?
By the suspicious formatting of that block, it looks like you've been there already, since all numeric values don't have quotes, and are right next to the var name.
However allowed FPS doesn't mean, that it will actually run said framerate, it's limited by hardware, setting itself will only raise fps cap.
## Post #3
- Username: Taxmonk44
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 07, 2019 4:00 pm
- Post datetime: 2019-08-07T08:09:17+00:00
- Post Title: Help me to translate this code

Hey pal does it work.did unlock fps.
They encrypt the config .how you decrypt the game option.js
## Post #4
- Username: Taxmonk44
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 07, 2019 4:00 pm
- Post datetime: 2019-08-07T08:19:08+00:00
- Post Title: Help me to translate this code

> Reply from PredatorCZ ↑Wed Jul 17, 2019 3:36 pm at Wed Jul 17, 2019 3:36 pm
>
> 
Starts at line 358: render_allowedFPS
Have you tried to change "60" to just 60 at next line?
By the suspicious formatting of that block, it looks like you've been there already, since all numeric values don't have quotes, and are right next to the var name.
However allowed FPS doesn't mean, that it will actually run said framerate, it's limited by hardware, setting itself will only raise fps cap.

Mine is encrypted like this.plz help
[pic.png](https://xentaxbackup.github.io/file/16575_pic.png)
## Post #5
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-08-07T15:15:50+00:00
- Post Title: Help me to translate this code

This looks like, it's base64 encoded.
There are plenty of base64 encoders/decoders online.
