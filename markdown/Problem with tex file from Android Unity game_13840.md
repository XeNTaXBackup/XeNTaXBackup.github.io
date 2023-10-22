## Post #1
- Username: codeGrit
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 18, 2016 6:20 am
- Post datetime: 2016-01-18T00:07:53+00:00
- Post Title: Problem with tex file from Android Unity game

Hey -

I have avoided posting this here, but my patience has run thin lol. I've been futzing with this for a few days now and have made zero progress. I am trying to get some character portraits out of a mobile game for use in a fan site (No modification to the game, at all). The problem is, I just cannot get the tex file to resemble anything even remotely "right". I've tried with TextureFinder, UnityStudio, Unit Asset Explorer, Gimp.. all without progress. Just all bright green, red, and black junk. 

From the unity3d package I can see it was packed with TexturePacker, but the tex file is not any format I ever remember seeing. It's possible I have, and I just forgot.. it's been an extremely long time since I've done this stuff. 

Either way, if anyone can provide me some guidance I'd greatly appreciate it! Here's some links ~

The *.tex file: [https://www.dropbox.com/s/xji9ofn9li61p ... 7.tex?dl=0](https://www.dropbox.com/s/xji9ofn9li61pcr/texture%20%2304_2048x2048.47.tex?dl=0)
Unity3d Package: [https://www.dropbox.com/s/9zbxyl8lta48s ... ity3d?dl=0](https://www.dropbox.com/s/9zbxyl8lta48s7q/Resources~Prefabs~HeroEmblems~.unity3d?dl=0)

Thanks in advance!

Edit - Forgot to include link to *.tex file.
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-01-18T19:57:10+00:00
- Post Title: Problem with tex file from Android Unity game

It's in KTX format.

Export it with [disUnity](https://github.com/ata4/disunity/releases).
Resulting texture.ktx open in [Mali Texture Compression Tool](http://malideveloper.arm.com/resources/tools/mali-gpu-texture-compression-tool/). Then you can save it as png, tga, psd, ...

[](http://www.fastimages.eu/?v=mali.jpg)
## Post #3
- Username: codeGrit
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 18, 2016 6:20 am
- Post datetime: 2016-01-18T20:11:09+00:00
- Post Title: Problem with tex file from Android Unity game

Thanks so much, this is super helpful!~

EDIT: I had to roll back to disUnity 3 and was able to get the ktx file.

Thanks again!
