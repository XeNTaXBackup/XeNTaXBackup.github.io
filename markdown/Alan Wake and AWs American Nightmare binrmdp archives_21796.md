## Post #1
- Username: Nostritius
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 11, 2019 6:18 pm
- Post datetime: 2020-02-23T18:11:55+00:00
- Post Title: Alan Wake and AWs American Nightmare bin/rmdp archives

Hi everyone,
I'm trying to understand the bin/rmdp file format completely to write my own packer for my personal Alan Wake Tools [https://github.com/Nostritius/AWTools](https://github.com/Nostritius/AWTools). Specifically I have three problems in understanding the archive format:

 The big blob in the beginning of the file with a size of 120 bytes, I'm not sure what it does exactly, but I suspect it being parts of the rmdp file from specific positions to verify the integrity of the corresponding files.
 The 4 byte value before the name offset in the folder table, i want to know what this value describes and what it is used for
 Alan Wakes American Nightmare has a 64 bit value appended on every file entry, i also want to know, how this value is calculated and used.

If someone can help me in this, I would be very thankful   .
Thanks in Advance
