## Post #1
- Username: Scorpion2k7
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 18, 2013 12:39 am
- Post datetime: 2017-12-13T22:51:11+00:00
- Post Title: Okami HD - PC File Encrypted

I need help to decrypt Okami HD PC files.
I uploaded an example of an encrypted and decrypted file
[example.rar](https://xentaxbackup.github.io/file/13681_example.rar)
## Post #2
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2017-12-15T16:35:27+00:00
- Post Title: Okami HD - PC File Encrypted

It's blowfish with 256bit key. The key had to be (obviously) in the game. I wrote yesterday a tool to decrypt/encrypt it (I'm porting our Polish translation project from PS2 to PC). Don't mind "compress/decompress" in usage, I've copied that part from my another tool ^^. Have fun.

[http://ff12.pl/down/okami-encdec.zip](http://ff12.pl/down/okami-encdec.zip)

PS. Your encrypted file doesn't match your decrypted file. I guess you either used a memory dump, where pointers might've been overwritten or you've used a files from another system (PS2/WII/PS3).
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-15T23:00:13+00:00
- Post Title: Okami HD - PC File Encrypted

> Reply from ffgriever
>
> It's blowfish with 256bit key. The key had to be (obviously) in the game.
nice work!    what was the key, if you don't mind me asking?
## Post #4
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2017-12-16T00:09:32+00:00
- Post Title: Okami HD - PC File Encrypted

> Reply from AceWell
>
> nice work!    what was the key, if you don't mind me asking?

```
YaKiNiKuM2rrVrPJpGMkfe3EK4RbpbHw
```

I guess someone was hungry...
## Post #5
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2017-12-18T17:00:59+00:00
- Post Title: Okami HD - PC File Encrypted

Quick observation: the actual key is read from the file data_pc/config/flower.cip. It's encrypted with master key

```
M2m2sukiYAKIx3pcWgj4Mue3Nh7gapQe
```


Messing about with some other stuff...
You can run the game with decrypted files by changing the constructor for m2::ResourceReadConfig in hx::SingletonObject<class m2::ResourceReadConfig>::getSingletonInstance(void) (it's the instruction assigning a 1 to a static location near the end of the function, change that to assign 0). The decrypted files need to be in the "data" folder instead of "data_pc". There are also two places you need to patch because apparently someone forgot to turn off a thread when encryption isn't used and it would crash. Search references to m2::ResourceReadConfig::GetUseCipherResource(void) and nop the conditional jump in the last two references. Note you'll need to retain flower.cip even though you don't need to do so usually if they didn't leave that thread running.
## Post #6
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2017-12-19T09:57:08+00:00
- Post Title: Okami HD - PC File Encrypted

Thanks. Nice finds. It will be helpful for quick changes and testing. To be honest, though, I've never understood this kind of forced and useless code. What was the point? The implementation was simple and didn't take much time, but has certainly cost a measurable amount of money to develop and test. I've got a feeling that it has more to do with board of directors wishes than developers' actual plans.

> "- You need to add some protection, you know, that flashy, sparky, magic thing or code or whatever it's called to protect something, wait, assets right, that's what you call it? But make it fast and don't generate any more costs."
>
> (a day has passed)
>
> "- It's protected, see?! This encryption cannot be bruteforced within billions of years!" (then whispering to himself "...but the keys are under the doormat").
>
> "- Jolly good! Now our shareholders will be relieved!"

Just a random rant  . Even though I enjoy challenge, I'm actually glad it's that obvious this time, as I don't have as much free time to spare as I had 10 or 15 years ago.
## Post #7
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2017-12-21T17:26:41+00:00
- Post Title: Okami HD - PC File Encrypted

It also helps that it literally tells you it's Blowfish.
## Post #8
- Username: neuokami
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 02, 2019 12:00 am
- Post datetime: 2019-10-02T02:21:57+00:00
- Post Title: Okami HD - PC File Encrypted

> Reply from ffgriever ↑Sat Dec 16, 2017 12:35 am at Sat Dec 16, 2017 12:35 am
>
> 
It's blowfish with 256bit key. The key had to be (obviously) in the game. I wrote yesterday a tool to decrypt/encrypt it (I'm porting our Polish translation project from PS2 to PC). Don't mind "compress/decompress" in usage, I've copied that part from my another tool ^^. Have fun.

http://ff12.pl/down/okami-encdec.zip

PS. Your encrypted file doesn't match your decrypted file. I guess you either used a memory dump, where pointers might've been overwritten or you've used a files from another system (PS2/WII/PS3).

HI, I am a member of the team who have made Chinese localization version of Okami PS2 PS3 and PC. What I have been doing is helping translation, modifying the illustrations. Although the localization process has already been completed and all the texture in the game has been translated as well, I still have some regrets, I want to make Clover logo back in the game, the tech support who provide me the unpacked dds files in my team wouldn't help me with that.

Here is the file name of logo in the opening scene
8A74C5148C436C429FD631EF67ED0EF7:Capcom
171D331CF51A649D37CA2C4C15A3F8B8:Criware
E30ED897FD16CC6607B04DEBCB2D103C:hexa drive

I was wonder if you could tell me where to find these files or how to find .dds in .dat.
Best regards.
[an00.rar](https://xentaxbackup.github.io/file/16842_an00.rar)
## Post #9
- Username: neuokami
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 02, 2019 12:00 am
- Post datetime: 2019-10-02T07:56:28+00:00
- Post Title: Okami HD - PC File Encrypted

I was foolish, problem solved.
