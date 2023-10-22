## Post #1
- Username: TheEmbracedOne
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 15, 2020 1:18 am
- Post datetime: 2020-04-16T14:49:25+00:00
- Post Title: For Honor Decryption (encryption keys inside)

Hi all, 
I've been trying to decrypt the latest For Honor game files for audio files but they've been encrypted since Oct 2018 with the coming of the Marching Fire expansion. I have managed to get my hands on the game files from before the encryption and I managed to extract all sounds from them, however I'd like to get some help figuring out how to get into the latest audio files (hopefully a method that'll work with later updates).

I talked to a couple of people in the FH community who used to datamine the game and I learned the following:
- the headers have been encrypted after mentioned expansion release
- I managed to get my hands on some AES encryption keys for the latest files but have no idea how to use them: [https://pastebin.com/St54pNgz](https://pastebin.com/St54pNgz)

I've uploaded the relevant files here, both the old, unencrypted files from Oct 2018 and the new, encrypted, latest files:
[https://mega.nz/folder/CltSiCgT#vGIwWjDtAjT5uDiOjOY39w](https://mega.nz/folder/CltSiCgT#vGIwWjDtAjT5uDiOjOY39w)

Note that the latest files do have a SoundPackages folder, but based on how many PCK files there were in the old, pre-encryption files, I would assume they've moved the sound files to the .forge files ending with "_sound.forge". If it helps, I can upload the rest of the files that dont have a "sound" suffix.

I'd really appreciate any help with this, so I could rip audio files from these latest files and from new updates in the future.
## Post #2
- Username: TheEmbracedOne
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 15, 2020 1:18 am
- Post datetime: 2020-04-27T18:33:55+00:00
- Post Title: For Honor Decryption (encryption keys inside)

I tried decrypting the files with AES Crypt since: [https://www.aescrypt.com/download/](https://www.aescrypt.com/download/)

Unfortunately I keep getting the "invalid signature" error, that according to some sources I found means that "the 'AES' header was not observed at the start of the file. It's a basic sanity check to ensure that the file format is known before attempting the decryption process. A better message would be "invalid AES file". I'll add that to the to-do list."

Somene also pointed out that it might be that the "header is somehow common data in the game, and they've chopped it off deliberately in the data files. Before decrypting in the game, the code just prepends the header back on to the file data stream.  Just my hypothesis, but I've seen it done with other file formats before."

Any ideas please?

For future reference, you can always reach me on Discord, my ID is The Embraced One#6059 and I'm also going to be on the Xentax Discord server.
## Post #3
- Username: exhaleme
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 10, 2017 10:59 am
- Post datetime: 2020-06-03T23:20:07+00:00
- Post Title: For Honor Decryption (encryption keys inside)

[https://wiki.modme.co/wiki/apps/Reforge.html](https://wiki.modme.co/wiki/apps/Reforge.html)

Not even close to AES... ("Custom Encryption")

Tool by DTZxPorter ^
## Post #4
- Username: TheEmbracedOne
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 15, 2020 1:18 am
- Post datetime: 2020-06-06T14:43:06+00:00
- Post Title: For Honor Decryption (encryption keys inside)

Wow, thank you so much for your reply! I'll try this tool. Thanks again!
## Post #5
- Username: karjalainen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 16, 2021 9:00 pm
- Post datetime: 2021-05-16T13:01:54+00:00
- Post Title: For Honor Decryption (encryption keys inside)

Necro, but did you ever figure this out? I've managed to use the supplied tool to get .dec file but unsure where to go from there. Did you get the sound files extracted in the end?
## Post #6
- Username: globe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 13, 2021 12:20 am
- Post datetime: 2021-08-12T16:23:46+00:00
- Post Title: For Honor Decryption (encryption keys inside)

Hey there. I'm in the exact same situation as you. I just wanted to ask if you could post a link to the unencrypted sound files in a .pck format. Thanks!
