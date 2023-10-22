## Post #1
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2019-06-01T14:39:41+00:00
- Post Title: The Learning Company *.bul files

Hi all,

Some games which were released by The Learning Company in the 2000's (following the disastrous Mattel ordeal) have their resources in files with the .bul extension. I've determined the format to be:

```
// for each file
   string   - name of file
   byte {x} - file data

```


The audio is not recognized properly by Audacity, no matter which encoding I choose, but the WAV files can be extracted using a program like Ravioli Game Tools, which can recognize when there's a known file type within an archive and extract that (albeit with a generic name).

Even though the file names are not in a table (and, from what I can tell, there's no information in the archive for file sizes or offsets), is there still an easy way to extract the files from these archives with their correct names?

Examples (from StarFlyers Royal Jewel Rescue): [https://www.dropbox.com/s/913joafpidewf ... es.7z?dl=0](https://www.dropbox.com/s/913joafpidewfvx/bul%20examples.7z?dl=0)

-Johnny
