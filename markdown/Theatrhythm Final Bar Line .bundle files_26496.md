## Post #1
- Username: Sora3087
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 03, 2011 2:28 pm
- Post datetime: 2023-02-21T19:09:55+00:00
- Post Title: Theatrhythm Final Bar Line .bundle files

So I want to extract the content of these bundle files and the bundle files are varied in size that seem to indicate they load more than just the audio streams and chart files.
Here's a few samples:
[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1idX5UzPA0mezDVA_bTbMHLzPQ6fbY4p8?usp=share_link)

The game is built in Unity and the bundle files are most likely encrypted since there is a JSON file that describes assets that are loaded and one class named is Game.File.AssetBundleCryptProvider in Assembly-CSharp.

Since this is a switch game I don't thing I can use ILSpy on the NSO binary to read the class.

Anyone have any idea what to do with these?

There are also curious amounts of string data in the JSON one labeled "m_KeyDataString" that are base64 encoded, I pulled those out and added them to the drive folder too.

I tried parsing the KeyDataString file and it looks like its mostly just a list of strings for most of the file and then some binary data at the bottom.

I realize just having the keys wont help much if you don't know the encryption method but worth a shot.
## Post #2
- Username: grojdg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 24, 2023 9:03 am
- Post datetime: 2023-02-24T01:07:27+00:00
- Post Title: Theatrhythm Final Bar Line .bundle files

Spent some time digging with Shadow and Whovian from the ReSwitched discord. Most of the asset bundles are encrypted (AES 128 CBC) and each have a unique key and IV. I dumped about 1k of them, but don't have an automated way of knowing which key goes to which bundle yet.

Here's a sample key/iv pair for 1d5e9336a6f271ddf2741d02729bd730.bundle
KEY = 1BD3736C94C41B759377FF7B4F72C938
IV = D1F7B9A0C066931486186C6F73F2930A

There's an extra hash at the top of the decrypted file, if you chop it off (first 0x20 bytes) then you can load it in AssetStudio or whichever you choose and see the file. This bundle has a moogle(?) voice clip.
## Post #3
- Username: Sora3087
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 03, 2011 2:28 pm
- Post datetime: 2023-03-15T18:59:31+00:00
- Post Title: Theatrhythm Final Bar Line .bundle files

Interesting...

> Reply from grojdg ↑Fri Feb 24, 2023 9:07 am at Fri Feb 24, 2023 9:07 am
>
> 
but don't have an automated way of knowing which key goes to which bundle yet.

How did you identify which key and IV went with this file?
## Post #4
- Username: grojdg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 24, 2023 9:03 am
- Post datetime: 2023-03-25T05:23:39+00:00
- Post Title: Theatrhythm Final Bar Line .bundle files

I dumped them and did not know originally then just decrypted every file until the output looked correct.

But I was wrong, the bytes at the top are not a hash they are the salt and IV, just with some of the bytes out of order.

The game has a base64 encoded key that they decode then do some things like an xor routine on them. I worked with Shadow and Whovian from the ReSwitched discord and Shadow managed to reverse engineer the base key decryption routine and recreate almost matching C# code. I'll upload that code somewhere when I can.
## Post #5
- Username: Cutebleeder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 02, 2023 10:46 pm
- Post datetime: 2023-04-02T22:56:09+00:00
- Post Title: Theatrhythm Final Bar Line .bundle files

I am also interested in accessing the bundle files. I got pretty close to this info myself, but was unable to find the Keys. I tried with the set mentioned and did get it to work, but was unable to get Asset Studio to open it. Please help and keep me updated!
## Post #6
- Username: grojdg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 24, 2023 9:03 am
- Post datetime: 2023-05-22T21:59:23+00:00
- Post Title: Theatrhythm Final Bar Line .bundle files

Sorry this took some time.

[https://github.com/xxk-i/TheatrhythmDec ... es/tag/0.1](https://github.com/xxk-i/TheatrhythmDecrypt/releases/tag/0.1)

CLI to decrypt a single bundle file. Worked with Shadow from the ReSwitched discord to figure out the decryption routine, they wrote this app.
## Post #7
- Username: Cutebleeder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 02, 2023 10:46 pm
- Post datetime: 2023-05-31T14:28:20+00:00
- Post Title: Theatrhythm Final Bar Line .bundle files

I tried a few files, from large to small bundles. Some worked, some did not, but I am unable to figure out which application can extract files from these bundles. What program are you using?
## Post #8
- Username: grojdg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 24, 2023 9:03 am
- Post datetime: 2023-06-02T07:33:30+00:00
- Post Title: Theatrhythm Final Bar Line .bundle files

I tried what I believe to be every asset extractor out there, but it seems the file format itself is changed. Tools would have to be updated to support them.
