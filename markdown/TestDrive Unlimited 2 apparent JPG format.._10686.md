## Post #1
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2013-08-13T18:42:07+00:00
- Post Title: TestDrive Unlimited 2 apparent JPG format..

Hey guys 

I hope someone can help me with this. First i need to say, i am completely useless at this sort of thing, so any responses will have to be dumbed down a lot  

Ok onto the point of the post..  In Testdrive unlimited 2 you have the ability to take photos. Then if you want you can either view your photo album or you can use your photos to decorate your house ( the houses have a few picture frames you can put the photos in) 
The files that get saved have a .jpg extension but nobody has been able to view these pictures in anything other than the game. It is strongly believed they are in fact jpg's but have been encrypted somehow. But personally im not even sure they are jpg's. 

Ultimately what i would like is to be able to take photos, make them readable in photoshop or another art program, edit them, or insert a totally new image, then be able to save them, then if need be convert them back so i can put them back in the game.

So if someone could be kind enough to maybe take a look at the file, see if they can find anything out, or if there is a way to convert it to something useable, and then back again. It would be VERY much appreciated.

Heres the file... [Photo](http://www.mediafire.com/?uan6xiu3llfbbbj)

Many thanks in advance.. Nobby 

P.S. Also here is a snapshot of the photo being displayed in game.. So if you are able to read it somehow, you know what the image should look like..
## Post #2
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-08-19T10:30:45+00:00
- Post Title: TestDrive Unlimited 2 apparent JPG format..

It's definitely not a valid JPEG file. The first bytes should start with "FF D8 FF E0 00 10 4A 46 49 46", but instead, they start with "B3 1B 1A F7 44 18 0A A5 41 CF". There seems to be some plain text at the bottom of the file, though: "##Ý¬2“î¹XR00000B2X.JPG##". Maybe "Ý¬2“î¹" (DD AC 32 93 EE B9) is the key and "XR" is the method (XOR), but that's just a wild guess.

Edit: nah, I don't think it's simple XOR. Do you have some more photos for analysis?
## Post #3
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2013-09-04T23:45:33+00:00
- Post Title: TestDrive Unlimited 2 apparent JPG format..

i could certainly get some more. just takes a couple of mins.

[Photos](http://www.mediafire.com/?vyvdvo6f6032dqe)
OK heres a set of 3 photos. Hope this helps and i hope you can find something useful out..This is one thing that has baffled us for a while.
## Post #4
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-09-05T10:37:16+00:00
- Post Title: TestDrive Unlimited 2 apparent JPG format..

Well, okay. Apparently, the key is different for every file. Only the last 25 bytes are always(?) in the same format: ##[DD AC 32 93 EE B9]XR[filename]##[0C]

I wonder if there are similarities between two photos with the same file name. In that case, the key is probably based on the file name. But without reversing the executable, I would say it's very hard to figure out the encryption/decryption process.

Edit: new theory: the bytes between the two hashes is the key, including or excluding the hashes. Don't know the cipher, though. I tried AES and xtea (used in TDU1) without success.
