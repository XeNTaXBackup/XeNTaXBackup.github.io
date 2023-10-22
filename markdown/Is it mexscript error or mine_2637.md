## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-27T22:46:07+00:00
- Post Title: Is it mexscript error or mine?

While I am writting a mexscript for Evil Dead : Regeneration. Everything seems fine and show up, but when I try to extract the files, some of them didn'r work. I got the error as below.

I checked all offset and length are correct, just seems MultiEx Commander refuse to extract the file!

Could anyone take a look at it please!
[ERROR.jpg](https://xentaxbackup.github.io/file/1193_ERROR.jpg)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-27T22:47:10+00:00
- Post Title: Is it mexscript error or mine?

Here is the mexscript
[Evil_Dead_Regeneration_mexscript.zip](https://xentaxbackup.github.io/file/1194_Evil_Dead_Regeneration_mexscript.zip)
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-27T22:52:14+00:00
- Post Title: Is it mexscript error or mine?

And this is some of the files to test.
You can get more files in [here](http://forum.xentax.com/viewtopic.php?t=2631)
[test_files.zip](https://xentaxbackup.github.io/file/1195_test_files.zip)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-05-29T05:33:19+00:00
- Post Title: Is it mexscript error or mine?

Thanks, will take a look. 

[EDIT]Ok, go to Options and deselect Extraction->Check for overlapping files, then it will work. If that option is set, MultiEx Commander will assume all files in the index are in sequential order. The first file in dw.pak for instance starts at 3728 and is 8794 in size ( up to the offset of 12522). The second file starts at 1280 according to the index. Thus, there's a discrepancy in offsets and MultiEx will report this. By deselecting this check, MultiEx Commander will assume that files can be randomly distributed in the index.

Excellent work on the script by the way! Are you sure of the format? Nice job!
