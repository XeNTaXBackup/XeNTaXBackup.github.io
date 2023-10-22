## Post #1
- Username: ProjectDiva
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-02-22T04:41:14+00:00
- Post Title: Decrypt any vita game (no custom firmware needed)

All you need is to buy the game and download it onto your vita.
Now install CMA or QCMA on your PC.
Now just backup your vita game to your pc over usb.
in your folder  setup in the pc app you will see \PS Vita\APP\XXXXXXXXXXXXXXXX\GAMENAME\
now you can go into the app folder and you will see an .psvimg
grab [https://github.com/yifanlu/psvimgtools/ ... s/tag/v0.1](https://github.com/yifanlu/psvimgtools/releases/tag/v0.1) for your OS.
go to [http://cma.henkaku.xyz/](http://cma.henkaku.xyz/) and put in your PSN ID (the xx number in this) APP\XXXXXXXXXXXXXXXX\GAMENAME\
now just run from command prompt
usage: psvimg-extract -K key input.psvimg outputdir
and you will get nice decrypted game content
