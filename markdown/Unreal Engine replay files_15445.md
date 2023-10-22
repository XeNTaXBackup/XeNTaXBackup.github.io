## Post #1
- Username: kikki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 04, 2016 1:11 am
- Post datetime: 2016-11-03T17:18:48+00:00
- Post Title: Unreal Engine replay files

Hey. I'm looking to try and get some useful information from UE replay files. The server they are sent from sends them as "chunks" as the game progresses, and there are a few API endpoints that tell me things like how many chunks exist etc. - the files themselves however aren't all that useful in their state. I believe they're compressed server side for the network traffic and decompressed client side, but I don't quite have enough knowledge to figure out how. Here's an example of one of the stream chunks... I've also attached it to this post.

[http://pastebin.com/HYEMjDst](http://pastebin.com/HYEMjDst)

I also feel like from my own searching this is where the processing actually takes place within the Unreal client:
[https://github.com/EpicGames/UnrealEngi ... eaming.cpp](https://github.com/EpicGames/UnrealEngine/blob/release/Engine/Source/Runtime/NetworkReplayStreaming/InMemoryNetworkReplayStreaming/Private/InMemoryNetworkReplayStreaming.cpp)

but again, a lack of knowledge in the engine prevents me from seeing exactly how it happens. I'd love if anyone with some more knowledge on the subject of replay/demo & network transfer/processing would offer some advice. Also willing to pay for some further help if anyone's looking for some work!
[stream.0.zip](https://xentaxbackup.github.io/file/11867_stream.0.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-11-04T23:32:41+00:00
- Post Title: Unreal Engine replay files

unreal networking is done by replicating properties.

unpicking replay data makes more sense with the game data - which game was this captured from?
## Post #3
- Username: kikki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 04, 2016 1:11 am
- Post datetime: 2016-11-06T20:51:01+00:00
- Post Title: Unreal Engine replay files

Hi, thanks for the response. [this is the game](http://epicgames.com/paragon). I'll take a look at the useful links! I've never done anything like this but willing to learn, any other resources or ideas you might have would be greatly appreciated.
