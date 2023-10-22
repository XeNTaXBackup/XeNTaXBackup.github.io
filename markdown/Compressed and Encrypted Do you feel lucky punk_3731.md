## Post #1
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-09-22T21:51:24+00:00
- Post Title: Compressed and Encrypted: Do you feel lucky punk?

Hi all,

After several weeks wrangling with the new Fallen Earth MMO I've made some progress, but have finally hit a roadblock.  If anyone cares to look these two files over to see if they can decipher the compression/encryption, please do!

I've successfully extracted all the textures and targa files from the game, and although I've retrieved a lot of great content I'm still unable to get any of the other data reversed.

Attached is a zip file containing two files:

hmf_ragdoll.xml.obfuscated -> a file in compressed/encrypted form
hmf_ragdoll.xml.decoded -> the same file inflated and decrypted

Bugtest has been kind enough to assist me with a lot of questions, but it seems to be looking more and more like zlib compression with a dictionary file.  Anyways if someone would like to take a whack at these just to see if they have an, "AHA!" moment, any help would be greatly appreciated.

P.S. If you're wondering how I have a decoded version of the file, it's because some assets are not loaded into the game's proprietary archive and are instead extracted/decoded and written during the install process.
[sample.zip](https://xentaxbackup.github.io/file/2365_sample.zip)
## Post #2
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-13T06:38:53+00:00
- Post Title: Compressed and Encrypted: Do you feel lucky punk?

Developers are smartasses nowadays, they don't use popular algorithms to compress their data. I just reversed my first gamepack (yup, i'm still noob) and you know what? Compression algorithm is unique for the game i reversed. So i think you just have to get your game and reverse its exe file. It's pain in the arse, but this is the only way you can reverse some formats - first reverse the game and find out how it works with its files.
