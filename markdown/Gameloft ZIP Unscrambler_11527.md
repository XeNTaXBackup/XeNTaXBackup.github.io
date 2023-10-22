## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-05-20T21:48:20+00:00
- Post Title: Gameloft ZIP Unscrambler

It seems some newer Gameloft games, such as N.O.V.A. 3, use scrambled ZIP files instead of the traditional CustomPak. It took me forever banging my head against the CustomPak reader until I realized that it was probably not a CustomPak. Somehow it also escaped my attention until today that all files of this type starts with "SB". Well, anyway, here's a program to descramble the files. Have fun with it. Source code is included, as always. I haven't written my DRM wrapper yet, so I guess iOS app hacking noobs will be all over this soon.

Download at the blog: [blog/?p=1177](http://forum.xentax.com/blog/?p=1177)

Format notes
It's basically a ZIP file, but with different signatures and encrypted file headers. Instead of "PK\x03\x04" for each file header, you've got "SB" followed by a short of the header length. Not sure why they did it that way, but that's how it works. Oddly enough, the compressed data is not encrypted, so just copy that verbatim. Near the end you'll find the central ZIP directory, which starts with "SDIR", and goes on until the end of the file. Note this directory is a single block instead of the many repeating blocks you find in a normal .zip file. Everything after the "SDIR" is encrypted, so to get this block back just write "PK\x01\x02" to your output and dump the decrypted block to it. No need to differentiate between a central directory entry and the end-of-central-directory block. Regarding the encryption, it's just scrolling XOR, with the file name being the key.

Version History
[1.0.0.0 2014-05-20]
Initial release
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-21T00:40:52+00:00
- Post Title: Gameloft ZIP Unscrambler

Zing zing zing haha i knew it was xor ill take a look at the binary in IDA seems interesting once again good work man
yeah you're right lol
## Post #3
- Username: wasii2009
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 18, 2021 6:32 am
- Post datetime: 2021-04-19T16:38:03+00:00
- Post Title: Gameloft ZIP Unscrambler

> Reply from cra0 ↑Wed May 21, 2014 8:40 am at Wed May 21, 2014 8:40 am
>
> 
Zing zing zing haha i knew it was xor ill take a look at the binary in IDA seems interesting once again good work man
yeah you're right lol

Got anything to unzip the game files ? This link not working for me
