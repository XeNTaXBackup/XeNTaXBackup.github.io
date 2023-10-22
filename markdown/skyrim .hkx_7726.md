## Post #1
- Username: Knet0348
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 08, 2011 10:35 am
- Post datetime: 2011-11-21T08:38:25+00:00
- Post Title: skyrim .hkx

After playing though skyrim twice, I thought already about modding it so I can get the best out of my game copy and so it'll never get boring. I'm trying to open up .hkx, somewhat, somehow, because I want to replace some standart two hander animations with new(self-made) ones. First of all google search indicates that this is some sort of havok file format which can be opened by these "content tools", but it won't, I tried opening defaultmale.hkx and following errors came up: 

```
Warning: Unable to version contents, check warning log
```

Now this is not my only problem, what I'm even more worried about is that these havok content tools won't save its files in a 3ds max or blender compatible format, so basically I'm asking that you ackowledge not redirecting me to havok content tools since it's not of any help to me. 
edit, oh and after some research it seems as though maybe I simply used a wrong file. I just thought this would be a main skeleton .hkx because it was in the character anims root folder.
I would appreciate if someone was/were (sorry for bad English I seriously don't know how it's written correctly) to write a maxscript or a plugin or something similar that can import .hkx files(the ones skyrim uses, not the ones that are exported by the content tools program) I'd be very thankful. Exporting should not be needed since havok provides a plugin for this particular matter. 
If anyone does not own skyrim and wants to take a look at those files I'd be happy to provide them.
## Post #2
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-11-22T11:05:25+00:00
- Post Title: skyrim .hkx

NifTools team are now trying to decode skyrim formats. Here [http://niftools.sourceforge.net/forum/v ... m.php?f=38](http://niftools.sourceforge.net/forum/viewforum.php?f=38)
## Post #3
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-11-24T06:37:24+00:00
- Post Title: skyrim .hkx

HKX is a binary packaging format used in just about any game that uses the Havok Physics engine. Usually contains animations, but can contain just about anything. Sonic Generations uses them specifically for animations. The reason they cannot be opened with the content tools would be the exact same reason Generations no longer can. Compression of the files. I've looked into the straight up data, because the animations work on a track based system and the data blocks (which are labeled in the files) are just bytes, but I can't decipher it. Somebody that's good with animation formats probably could though. And I honestly don't know what Skyrim uses them for. My guess would be animations and probably breakable objects and whatnot, but I don't know for sure.
## Post #4
- Username: Knet0348
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 08, 2011 10:35 am
- Post datetime: 2011-11-29T12:31:35+00:00
- Post Title: skyrim .hkx

I checked every day now to see if there was support from niftools for anymations yet, aside from that not so bad 3ds max mesh import plugin, there is not too much to mention.... they are still working on meshes and textures, no one seems to give a crap about animations right now. Though I don't need meshes for animations to replace. So I'd find it wonderful if someone independently works on his own little .hkx import-export script so that thousands of people may begin adding more custom animations to the game, not retextures which aren't always of the best quality anyhow. I think animating is easy and that's why I'm confident there will be more quality in custom animations.
