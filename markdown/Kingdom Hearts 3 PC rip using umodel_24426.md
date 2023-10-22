## Post #1
- Username: Amal Kotay
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 11, 2011 11:04 pm
- Post datetime: 2021-08-29T14:25:27+00:00
- Post Title: Kingdom Hearts 3 PC rip using umodel

I used override game detection because it wasn't detecting my game files, and then I use tools -> save packages, but I see two problems with the files that it spits out:

1. UE4 doesn't show the files when I add the saved packages to a project I already had. I tried using 4.26 and 4.17.

2. When I select files, I use flat view and ctrl+A to get all the packages. Based on the tree structure shown in umodel, I should get 6 folders. But when I check the output, I only get two - Game and Plugins. 

What am I missing? I set the platform to PC because that's what I have. Is there more than one AES key maybe?

Thanks!
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-08-30T03:23:32+00:00
- Post Title: Kingdom Hearts 3 PC rip using umodel

> 1. UE4 doesn't show the files when I add the saved packages to a project I already had. I tried using 4.26 and 4.17.

Packaged and unpacked uasset files aren't the same thing, the data isn't structured the same way at all.

Unreal editor can only read/use uasset files that haven't been compiled, the file extension is the same but thats mostly it.
