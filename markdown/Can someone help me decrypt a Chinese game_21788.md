## Post #1
- Username: Maren
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 18, 2017 11:36 pm
- Post datetime: 2020-02-22T09:36:59+00:00
- Post Title: Can someone help me decrypt a Chinese game?

I downloaded the apk and unpack it, all the assets are encrypted in someway. There's a bunch of so file in \lib\x86 but the one I think that is most likely to contain decryption method is libtpnsSecurity.so. I opened it in IDA and found these functions: 


Capture.PNG (47.15 KiB) Viewed 84 times

 This is as far as I can go 

The game may use TEA or XXTEA
I have no experience in the matter so I hope someone can help me. I attached a zip file which contains the so files, some lua files and pngs

Note: The game server actually leaked its Directory Listing and I was able to grab on some php files, one of them is xxtea.php which is just the source code for the algorithm, others are just functions with no clues, they are also added in zip files.

Thank you

files.zip [https://www.dropbox.com/s/ohbrsbp2j7obr ... s.zip?dl=0](https://www.dropbox.com/s/ohbrsbp2j7obrq0/files.zip?dl=0)
