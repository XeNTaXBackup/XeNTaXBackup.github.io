## Post #1
- Username: joyingwol
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 27, 2022 9:43 pm
- Post datetime: 2022-12-27T15:00:17+00:00
- Post Title: Archeland (Unity) - encrypted files

Archeland is a Korean mobile game (with PC version) which have opened korean server recently.

Official website：[http://archeland.zlongame.co.kr/](http://archeland.zlongame.co.kr/)

I have downloaded the PC version at: [https://kru2update.zlongame.co.kr/KRU2/ ... _Setup.exe](https://kru2update.zlongame.co.kr/KRU2/Clientdown/Archeland_Setup.exe)

You may also download Apk from apkpure.

I have tried to use tools like Assetstudio to open the file but it seems to go wrong.

After check the hex I find that they are using an unique Unity version: 2017.4.42c1



Well it seems to be a Unity version for China only and have been encrypted. (unity-china-editor)

I have searched about 'decrypt' in dumped DLL as following and I dont know if I find a correct one...



I upload a few files and dlls that I dump from original apk for reference.

[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1UYMgyWAZR4lAinQK8MKK_djZslC981Nu?usp=share_link)

I hope someone to make a program to decrypt the assetbundle file to be a right one which can be opened by Assetstudio.

Thank you very much.

P.S. Another game named "天地劫：幽城再临" (Tiandijie) from Zilong also use this Unity version.

And the Official website of it: [http://tdj.zlongame.com/](http://tdj.zlongame.com/)

PC version at: [http://tdjdownload.zlongame.com/TDJ/Cli ... ficial.zip](http://tdjdownload.zlongame.com/TDJ/Clientdown/tdj_ob_official.zip)

Maybe they share the same way to encrypt the assetbundle?
## Post #2
- Username: hunshimowangzhy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 04, 2019 4:53 am
- Post datetime: 2023-01-09T04:12:42+00:00
- Post Title: Archeland (Unity) - encrypted files

The game is made by a Chinese company and uses the chinese version of Unity (that's why you see the suffix c1). There are asset encryption functions in the Chinese version. You can use AssetBundle.SetAssetBundleDecryptKey and AssetBundle.RecompressAssetBundleAsync to decrypt the asset files. There decryption key I found is "BlackJackProject". You can take a look at my reply in the Punish Gray Raven thread.
## Post #3
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-01-11T18:53:49+00:00
- Post Title: Archeland (Unity) - encrypted files

Actually if you know the key, you can simply hex edit Razmoth's PGR Studio and replace one of existing keys, it will work with any game with default implementation of that encryption. As proof-of-concept, here is modified build of the studio ([link](https://drive.google.com/file/d/1xuKFvVKT7f3zazi-ecBpIZm4-nld0Daj/view?usp=sharing), choose respective game in options), tested on latest versions of Archeland and Kalpa of Universe / Heaven and Earth Tribulation (that's english title for the second game).

Alternatively you can grab latest Razmoth's MH Studio with the support for that encryption and mentioned games [here](https://gitlab.com/RazTools/Studio/-/releases).

Update: Just checked the second game, the key provided by hunshimowangzhy above was from it.
Update 2: Builds are now merged into single one with support for 4 games, including Archeland, Kalpa of Universe, Doula Continent and Mecharashi.
Update 3: Support for Bless Global is added.
## Post #4
- Username: xiyuan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 03, 2023 10:18 am
- Post datetime: 2023-03-03T12:16:12+00:00
- Post Title: Archeland (Unity) - encrypted files

HI Spiritovod,
I put the TDJ PC file into modified build of the studio, prompt "No Unity file can be loaded"
## Post #5
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-04-16T18:48:51+00:00
- Post Title: Archeland (Unity) - encrypted files

> Reply from Spiritovod ↑Thu Jan 12, 2023 2:53 am at Thu Jan 12, 2023 2:53 am
>
> 
Update: Just checked the second game, the key provided by hunshimowangzhy above was from it.
Update 2: Builds are now merged into single one with support for 4 games, including Archeland, Kalpa of Universe, Doula Continent and Mecharashi.
Update 3: Support for Bless Global is added.
Nice, thanks for this, used the build to poke around in the 2.1.1 Mecharashi beta build to see if there was any Front Mission content still in there. There was, so, score!
