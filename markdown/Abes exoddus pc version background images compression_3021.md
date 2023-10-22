## Post #1
- Username: Paul
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 21, 2008 6:38 am
- Post datetime: 2008-04-21T18:21:02+00:00
- Post Title: Abes exoddus pc version background images compression?

Hey guys,

I started trying to reverse the static background images in each screen of abes exoddus for the pc a while ago, I've pretty much gave up with it but maybe someone here can figure it out 

Every file is made of some kind of chunks/segments, each segment can be anything but has an id string such as "Font" "Anim" or "Bits", "Bits" is the background images.

The background images are sliced into 16x240 segments to make a big 640x240 image. This is how the cam files are done in abes oddysee, as 16bit pixel data...

But the problem is that in exoddus they've added some sort of compression? Or at least I *think* its compression. It could be jpeg or RLE/packbits or something, who knows.. maybe some one who knows those formats well can easily see what it is.

Remeber this game is from 1998/9 so it can't be anything too hard to crack right? 

I've attached some sample .cam files and the source for some app that will load up the segments into buffers, but then what to do with the buffers to get the raw pixels is beyond me..

thanks++ to anyone that can figure this monster out 
[AE Cam.zip](https://xentaxbackup.github.io/file/1496_AE Cam.zip)
