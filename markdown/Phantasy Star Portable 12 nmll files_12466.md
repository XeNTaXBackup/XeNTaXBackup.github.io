## Post #1
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2015-01-04T01:02:45+00:00
- Post Title: Phantasy Star Portable 1/2 nmll files

[http://psumods.co.uk/archives/wiki/files%253Anbl.html](http://psumods.co.uk/archives/wiki/files%253Anbl.html)

For this format the developers used encryption as well as multiple types of compression
The Encryption for the format has been resolved as well as one type of nbl file which
has one form of compression for the general 'nmll' file data and prs compression for 
the 'tmll' texture data.

Source code for the tools can be found here I also attached a modified nbl extractor that will handle the prs texture data
[https://github.com/essen/gasetools](https://github.com/essen/gasetools)
[https://github.com/essen/prsutil](https://github.com/essen/prsutil)

But there is another type of nbl file where the types of compression used for both the general and texture
data is different.

I attached the compressed data chunks does anyone recognize this type of compression.
[nbl_Research.rar](https://xentaxbackup.github.io/file/8428_nbl_Research.rar)
## Post #2
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2015-01-07T13:41:32+00:00
- Post Title: Phantasy Star Portable 1/2 nmll files

Upon further investigation it seems that the tmll texture data in type 1 nbl are not encrypted just compressed
while in type 2 nbl tmll's are also encrypted like the nmll data and after comparing nmll decrypted data of the same file types from type 1 with type 2
it seems like the decryption method is different between as type 2 data still seems encrypted after using the decryption algorithm that worked with type 1.

I attached below what I believe to be an encrypted gim file.
[Compare.rar](https://xentaxbackup.github.io/file/8442_Compare.rar)
