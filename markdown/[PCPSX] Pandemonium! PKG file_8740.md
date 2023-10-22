## Post #1
- Username: StealthSpyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 10, 2012 6:56 pm
- Post datetime: 2012-04-10T11:41:04+00:00
- Post Title: [PC/PSX] Pandemonium! PKG file

Hi everyone!

I've been trying to open the PKG files belonging to the game Pandemonium! for a long time now, but to no avail. I have tried nearly every unpacker application with PKG support, but unfortunately to no avail. I myself do not have any knowledge on file compressions, headers and so forth, so I figured it would be best to have you guys take a look at it instead.

Here is a link to the free demo which contains PKG files with the same structure as the full version, it just doesn't contain all the assets.
Demo link - [http://download.cnet.com/Pandemonium-de ... 08126.html](http://download.cnet.com/Pandemonium-demo/3000-2095_4-10008126.html)

The full version version came with a command-line tool called "Charles", which allows the user to replace certain textures in the PKG files. This tool might contain some hints regarding the way these files can be unpacked. Unfortunately, I'm not allowed to link to this tool here but I can send it to you if you send me a PM.

I hope you can be of help and it would be much appreciated!

Thanks in advance for your effort.
## Post #2
- Username: StealthSpyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 10, 2012 6:56 pm
- Post datetime: 2012-04-15T14:28:35+00:00
- Post Title: [PC/PSX] Pandemonium! PKG file

Just wondering, is there anyone looking into this? No offense.
## Post #3
- Username: StealthSpyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 10, 2012 6:56 pm
- Post datetime: 2012-04-19T10:40:28+00:00
- Post Title: [PC/PSX] Pandemonium! PKG file

Any thoughts on this so far? I don't want to force or rush anyone, I'm just being curious whether or not someone is actually looking into this and if some new light can be shed on the way the files could be unpacked.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-20T06:09:01+00:00
- Post Title: [PC/PSX] Pandemonium! PKG file

I really appreciate you deleting the links to the game files. Good job! The link to the tool from the PC version was altered, as you stated it came from the original game. That means it may not be a public tool.
## Post #5
- Username: StealthSpyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 10, 2012 6:56 pm
- Post datetime: 2012-07-22T13:02:40+00:00
- Post Title: [PC/PSX] Pandemonium! PKG file

It's been over three months since I posted this request and I can't help but wonder if there is actually anyone willing to help me with this. I would be incredibly grateful if someone wrote small tool that allows me to unpack the files contained in these PKG files.

Thanks.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-07-22T23:13:51+00:00
- Post Title: [PC/PSX] Pandemonium! PKG file

i downloaded a version of pandemonium and the charles.exe program has the 'nikkiface' and 'goonking' pkg offsets and data sizes hardcoded into them.

edit

the bitmap data (24-bit at least) is converted to 16-bit:

```
^ unused
a = byte 1
b = byte 2
c = byte 3

```


a bit of bit-shifting can convert it back, but it obviously loses 3 bits of precision

also, the charles program is terrible. have you tried using your own bitmap image? the data the image converts is completely wrong!
[kinghead_2wayconv.bmp](https://xentaxbackup.github.io/file/5592_kinghead_2wayconv.bmp)
## Post #7
- Username: StealthSpyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 10, 2012 6:56 pm
- Post datetime: 2012-08-07T06:48:47+00:00
- Post Title: [PC/PSX] Pandemonium! PKG file

Not very helpful indeed. However, would it be possible to determine the offsets of other files using this knowledge?
