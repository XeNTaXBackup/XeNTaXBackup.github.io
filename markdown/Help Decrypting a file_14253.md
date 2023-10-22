## Post #1
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-04-21T16:02:35+00:00
- Post Title: Help Decrypting a file

Greetings!

I'm trying to access the 3D models of Saint Seiya APK, however the file is encrypted and their HEX code just shows __crypto__

I've searched through the DLLs and found the function that seems do Decrypt those files, but I don't know what the next step is. 
Since I'm not a programmer, so I really don't know how to use that information to extract the models.

Can you guys help me out?

Encrypted file sample: [http://www.mediafire.com/download/x66rc ... 491fc7.rar](http://www.mediafire.com/download/x66rc259u59v9w0/f0004c8e3154e3c539a69956b9fc6bcff2491fc7.rar)

Here's the decryption function:


And here are the DLLs in case you want to take a deeper look: [http://www.mediafire.com/download/kmteg ... x/DLLs.rar](http://www.mediafire.com/download/kmteght31grxq8x/DLLs.rar)

Thanks in advance!
## Post #2
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2016-04-22T03:37:11+00:00
- Post Title: Help Decrypting a file

Removed.
## Post #3
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-04-22T11:38:55+00:00
- Post Title: Help Decrypting a file

@atom0s you are absolutely right!

I've found _nativeDecrypto function inside libarrow.so. I managed to disassemble it with IDA [https://www.hex-rays.com/products/ida/](https://www.hex-rays.com/products/ida/)
I believe the language IDA uses is called ARM ([http://simplemachines.it/doc/arm_inst.pdf](http://simplemachines.it/doc/arm_inst.pdf))

Just to be sure, I'm uploading all the .SO files here: [http://www.mediafire.com/download/nr1q8 ... +files.rar](http://www.mediafire.com/download/nr1q8qrqcprklf6/SO+files.rar)

Here's the _nativeDecryptoToAssetBundle funcion:
