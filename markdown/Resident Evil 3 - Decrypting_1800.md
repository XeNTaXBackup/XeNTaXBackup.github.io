## Post #1
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-23T02:26:17+00:00
- Post Title: Resident Evil 3 - Decrypting

Ive made a long way on this format.
The files are encrypted with XOR. thats simple. however,
they use 2 Different XORs per file. and all files have 2 headers.
one encryption header, and one file header.

the Encryption header itself is XOR by using the 16th byte value
in the header.

however I have not yet found out what is making out the second
XOR value for the rest of the file.

here is an example of a WAVE file found in rofs15.dat
, you see the here that i have the first header decrypted by XORing
it with 6. and the rest of the file with value of 152.

and it is for sure a WAVE file. however, the 152 value was almost
bruteforced from my side. anyone else has something to come with? :/
[encrypted.gif](https://xentaxbackup.github.io/file/659_encrypted.gif)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-23T02:26:54+00:00
- Post Title: Resident Evil 3 - Decrypting

Decrypted.
[decrypted.gif](https://xentaxbackup.github.io/file/660_decrypted.gif)
## Post #3
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-03-06T20:02:02+00:00
- Post Title: Resident Evil 3 - Decrypting

Hello,

Could you please write down a complete explanation of how to decrypt the files, in the wiki for example?
## Post #4
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-04-25T20:42:20+00:00
- Post Title: Resident Evil 3 - Decrypting

I figured now how you did it. In fact, rofs15.dat archive contains WAV file as you said, and all files starts with 'RIFF' string, so it's easy to xoring it against the crypted value to find the key (single byte).

Now we need to find how this key is selected.

I started writing a wiki page about it, will rewrite it for xentax once I got it:
[http://rewiki.regengedanken.de/wiki/.DA ... _Evil_3%29](http://rewiki.regengedanken.de/wiki/.DAT_%28Resident_Evil_3%29)

As you can see the 'NotComp' string you found may refer to the fact that the file is not compressed. Other files I found have 'Hi_Comp' as string, and are not like what they should be (for example TIM files), so it may mean they are compressed.
## Post #5
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-04-30T22:02:45+00:00
- Post Title: Resident Evil 3 - Decrypting

Hello,

I finally found how decryption is done. I will post an example routine later on rewiki. Here is one of the background images (640x480 JPEG image directly from a rofs.dat file).
[reevengi4.jpg](https://xentaxbackup.github.io/file/1139_reevengi4.jpg)
## Post #6
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-05-01T08:18:21+00:00
- Post Title: Resident Evil 3 - Decrypting

Hello,

For  people interested, an example decryption routine is available at:
[http://rewiki.regengedanken.de/wiki/.DA ... _Evil_3%29](http://rewiki.regengedanken.de/wiki/.DAT_%28Resident_Evil_3%29)

Now, I need to do the same with the optionnal decompression step.
## Post #7
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-05-19T21:37:13+00:00
- Post Title: Resident Evil 3 - Decrypting

I finished writing a base documentation for the rofs<n>.dat file archives.

However, I wonder if I should also add some pseudo-code for decryption and decompression steps, any hints?

[http://wiki.xentax.com/index.php/Resident_Evil_3_DAT](http://wiki.xentax.com/index.php/Resident_Evil_3_DAT)
## Post #8
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-05-25T22:09:00+00:00
- Post Title: Resident Evil 3 - Decrypting

Hello,

I did more tests, and now everything is working correctly. The last error I made was to decrypt a whole file, then depack it. It does not work as the depacker must work on blocks of the file, and must be resetted.

So now, I updated everything in both Xentax and Rewiki pages. I also started writing a patch for [PhysicsFS library](http://www.icculus.org/physfs/) so I can use it in my own programs.
[jill.jpg](https://xentaxbackup.github.io/file/1189_jill.jpg)
## Post #9
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2007-06-11T17:21:35+00:00
- Post Title: Resident Evil 3 - Decrypting

so is it possible to get the stage models and textures ?
## Post #10
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-06-11T18:52:20+00:00
- Post Title: Resident Evil 3 - Decrypting

What I've done is the equivalent of having documented the ZIP archive file format. It does not tell anything about the files stored in the archive.

The background images are stored as JPEG images (like the background above), some textures and other bitmapped images are stored as TIM images (like the Jill skin above).

From the various file extensions I see in the archive, it roughly use same file formats for models and the rest as previous RE games, which are still to be documented.
## Post #11
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2007-06-13T10:50:59+00:00
- Post Title: Resident Evil 3 - Decrypting

any chance you can upload some zombie, and /or nemesis skins ?
im a 3d modeler and with these skins its a little easier for me to get something textured
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-12-17T10:05:42+00:00
- Post Title: Resident Evil 3 - Decrypting

Good work dudes!!! i missed this!!

I gave up too quickly ;X, glad too see someone finally broke that damn
encryption. Very nice work.
