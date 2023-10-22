## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-07-04T13:06:07+00:00
- Post Title: Portal Stories: Mel (source engine) DAT files

Hey. Does somebody know a way to compile working DAT files in this game?
I found this tutorial [https://developer.valvesoftware.com/wik ... ortal_2%29](https://developer.valvesoftware.com/wiki/Subtitles_%28Portal_2%29)
But i think that is only for developers 

Samples in attachment.
If noone replies, i'll try to write my own script to do this, but maybe there is easier way.
[samples Portal stories mel.zip](https://xentaxbackup.github.io/file/9383_samples Portal stories mel.zip)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-07-04T13:38:03+00:00
- Post Title: Portal Stories: Mel (source engine) DAT files

[http://developer.valvesoftware.com/wiki/Closed_Captions](http://developer.valvesoftware.com/wiki/Closed_Captions)

"[game/SDK root]\bin\captioncompiler.exe" %1
pause
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-07-04T14:30:46+00:00
- Post Title: Portal Stories: Mel (source engine) DAT files

Thank you 
I'll check it soon.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-07-04T19:57:26+00:00
- Post Title: Portal Stories: Mel (source engine) DAT files

So, i installed source SDK [https://developer.valvesoftware.com/wik ... stallation](https://developer.valvesoftware.com/wiki/SDK_Installation)
and Authoring Tools for Portal 2 [https://developer.valvesoftware.com/wik ... ortal_2%29](https://developer.valvesoftware.com/wiki/Authoring_Tools/SDK_%28Portal_2%29)

And i have very important question :p
How can i run this command when i don't have "captioncompiler.exe" in ANY bin directory?
\Portal Stories Mel\bin\
\Portal Stories Mel\portal_stories\bin\
\Portal 2\bin\

In this article we can read "Make sure the SDK launcher is set to the mod you're working on, then simply drag your caption file onto it."  Drag where?

I tried also a few variations of commands. For example
C:\Users\ikskoks>E:\SteamLibrary\SteamApps\common\SourceSDK\bin\SDKLauncher.exe -game "E:\SteamLibrary\SteamApps\common\Portal Stories Mel\bin"

It also didn't work. Any ideas? :p
## Post #5
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-07-05T04:12:33+00:00
- Post Title: Portal Stories: Mel (source engine) DAT files

> Reply from ikskoks
>
> So, i installed source SDK https://developer.valvesoftware.com/wik ... stallation
and Authoring Tools for Portal 2 https://developer.valvesoftware.com/wik ... ortal_2%29

And i have very important question :p
How can i run this command when i don't have "captioncompiler.exe" in ANY bin directory?
\Portal Stories Mel\bin\
\Portal Stories Mel\portal_stories\bin\
\Portal 2\bin\

In this article we can read "Make sure the SDK launcher is set to the mod you're working on, then simply drag your caption file onto it."  Drag where?

I tried also a few variations of commands. For example
C:\Users\ikskoks>E:\SteamLibrary\SteamApps\common\SourceSDK\bin\SDKLauncher.exe -game "E:\SteamLibrary\SteamApps\common\Portal Stories Mel\bin"

It also didn't work. Any ideas? :p

If you installed the sdk correctly
common\SourceSDK\bin\orangebox\bin
should contain the cc executable
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-07-05T07:04:25+00:00
- Post Title: Portal Stories: Mel (source engine) DAT files

Oh, thanks man 
It worked.
Earlier i had error "Can't find steam app user info" and i fixed this with [https://developer.valvesoftware.com/wik ... _user_info](https://developer.valvesoftware.com/wiki/Can%27t_find_steam_app_user_info)
