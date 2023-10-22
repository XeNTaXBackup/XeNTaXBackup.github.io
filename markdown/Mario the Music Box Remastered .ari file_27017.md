## Post #1
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-07-24T20:13:03+00:00
- Post Title: Mario the Music Box Remastered .ari file

hello, theres a game called mario the music box remastered the uses a custom encrypted file format by the name of .ari i tried asking in the developers official discord server one person said that they and their friend made an exe that decrypts the file here's a quote on how they did it: "it uses some fiddling with the header and xor encryption" when i asked if could get access to it they said "no, thanks" here's the file: [https://mega.nz/file/lAhkjTKI#x4QFGcNQr ... IvkSyvxmYg](https://mega.nz/file/lAhkjTKI#x4QFGcNQrue-6MDAli_WRy5K9K_AxaY3lIvkSyvxmYg)

If anyone responds i'll be happy.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-25T21:48:43+00:00
- Post Title: Mario the Music Box Remastered .ari file

So I've done a little research for this game. It turns out it's free to download on itch.io 
[https://teamari.itch.io/mario-the-music-box-remastered](https://teamari.itch.io/mario-the-music-box-remastered)

In the readme file the authors revealed that they've used RPG MAKER XP Engine to create this game. 
And if you'll check online, you'll see that this engine usually uses RGSSAD archives. Even if you'll create a new project in rpg maker and you'll export game files, you'll get "Game.exe" executable and *.rgssad archive as a result.
[http://wiki.xentax.com/index.php/Enterb ... SAD_RGSS3A](http://wiki.xentax.com/index.php/Enterbrain_RPG_Maker_RGSSAD_RGSS3A)

You can even find a hint in the "Game.ini" file:



game_ini.PNG (10.22 KiB) Viewed 126 times



But "Team Ari" have used some custom tools as you can read in this twitter post
[https://twitter.com/Team_Ari_Games/stat ... 1025684480](https://twitter.com/Team_Ari_Games/status/1211626231025684480)
Here's the link to the encryptor they've probably used
[https://github.com/ogniK5377/RPGMakerXpEncryptor](https://github.com/ogniK5377/RPGMakerXpEncryptor)

Your ARI archive doesn't have "RGSSAD" signature at the beginning, so I think thay've added some additional layer of encryption before releasing final version to the public. So now you could start analyzing main game's executable and search for decryption method.  If it really uses XOR, then most of the code can be copied from github.
## Post #3
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-07-26T07:17:22+00:00
- Post Title: Mario the Music Box Remastered .ari file

How should an rgssad signature should look like? I just redownloaded the game. Also this probably what they used to encrypt it: [https://github.com/ogniK5377/RPGMakerXpCustomContainer](https://github.com/ogniK5377/RPGMakerXpCustomContainer)
## Post #4
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-07-26T08:38:08+00:00
- Post Title: Mario the Music Box Remastered .ari file

Couldn't find anything on how it uses it the thing, what i managed to find is the MZ string in the begging of the hex code i 
highly doubt this is related rpg maker MZ but who knows
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-26T18:33:10+00:00
- Post Title: Mario the Music Box Remastered .ari file

> How should an rgssad signature should look like?

Like this:



screenshot000508.png (12.43 KiB) Viewed 93 times



> what i managed to find is the MZ string in the begging of the hex code i
>
> highly this is related rpg maker MZ but who knows

No, it's standard signature for windows executable [http://wiki.xentax.com/index.php/Windows_Executable_EXE](http://wiki.xentax.com/index.php/Windows_Executable_EXE)
## Post #6
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-07-26T20:25:49+00:00
- Post Title: Mario the Music Box Remastered .ari file

Is it possible to overwrite the signature in the .ari file to a rgssad signature?
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-26T22:04:09+00:00
- Post Title: Mario the Music Box Remastered .ari file

Yes, by reverse engineering decryption function and writing custom script/program to do it.
## Post #8
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-07-27T08:08:16+00:00
- Post Title: Mario the Music Box Remastered .ari file

I don't even have a pc to do that.
