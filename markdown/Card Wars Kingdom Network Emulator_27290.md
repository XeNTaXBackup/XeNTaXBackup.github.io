## Post #1
- Username: caret
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 03, 2021 4:48 am
- Post datetime: 2023-10-11T17:22:49+00:00
- Post Title: Card Wars Kingdom Network Emulator

I've been spending the last few weeks deep-diving into an old mobile game called Card Wars Kingdom. It's an Adventure Time Card Wars game. It currently doesn't function due to the lack of servers (the servers are shutdown).

I'm trying to build a server emulator for it, but I don't fully understand the requirements to get it online. It is a unity game that makes decompilation easy but theres a ton of telemetry and facebook traffic I see when using adb logcat. I'm not too sure how to ensure the traffic I see is required or secondary to the game's function. 

Things like Kontagent and Kochava (facebook) are some of the many things I'm trying to understand more of. If anyone is interested in helping me, please PM me, it's my first time starting something like this, despite working in groups that have done this kind of thing before!

Things I've tried:
- JADX -> Found the facebook and kontagent stuff, not sure if its possible to remove it...
- dnspy -> Found some of the login functions to the non exsistant server, but it's still vague to me.
- Began server emulator writing using my pihole to redirect all traffic to my internal system (using actix-web at the moment)
