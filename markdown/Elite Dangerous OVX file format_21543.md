## Post #1
- Username: SunBro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 18, 2017 4:58 am
- Post datetime: 2019-12-29T00:11:38+00:00
- Post Title: Elite Dangerous OVX file format

Hello!

It seems that in the past year Frontier Developments has changed the root filesystem for Elite Dangerous yet again, effectively voiding most of the research data we have on it.

Currently, the files are packed in directory names 00 to 0f and 09 which seemingly have encrypted files within with no extensions whatsoever.

The only file which seemingly is the key to opening those files is a 5 megabyte data.ovx file.

I'm sending a sample of the data.ovx file as of today and some of the seemingly encrypted content files so that hopefully someone who's more knowledgeable on the matter can help shed some light here.

[https://mega.nz/#F!dtQBRSSR!C5CIqPc7MAXytDkmagv8pg](https://mega.nz/#F!dtQBRSSR!C5CIqPc7MAXytDkmagv8pg)

My intent currently is to extract the updated sound files with their names if possible.

Thanks!
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-29T14:36:34+00:00
- Post Title: Elite Dangerous OVX file format

The file 00cb9a90e6eaf7b7f6bd40816a8f56845dca3ce2 is compressed by zlib compression. This data.ovx contains hex bytes in ASCII style. The first 40 characters of each line should match to one of the file with that name. Then there're 128 characters, aka 64 hex bytes left. It might have some info about the compressed & decompressed size or something, and probably been encrypted. But obviously they can't store all asset names of a file within merely 64 bytes of data.
