## Post #1
- Username: coggy9
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 25, 2011 8:54 am
- Post datetime: 2012-03-27T03:23:14+00:00
- Post Title: BIT.TRIP RUNNER

I was going to work on a model/texture mod for BIT.TRIP RUNNER on the PC, but it looks like the developer stores files in a unknown format. The only piece of info that I could find on the .aescn files was someone stating that the PC version uses these files. They're are also .aetex, .aemenu, .aefs, and .aeefx files. Could anyone please look into these formats? Sorry if this isn't much help. I have no idea how to reverse engineer game archives(yet).
[BITTRIPRUNNER.zip](https://xentaxbackup.github.io/file/5234_BITTRIPRUNNER.zip)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-27T03:42:44+00:00
- Post Title: BIT.TRIP RUNNER

They're not archives. Or at least, most of them aren't anyways.
aetex are textures and aescn are models.

aescn references a bunch of other files which I'm not sure what they are.
So now you should be able to work on reversing the textures.

The header does not seem too difficult but I don't know the pixel format.
