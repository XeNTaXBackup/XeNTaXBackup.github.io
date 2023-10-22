## Post #1
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-06-19T08:49:05+00:00
- Post Title: Help me extract files with string in *.cut

Here is a package contain multi WMSF files

[0120.cut](https://www.dropbox.com/s/end7xea5k9jhln3/0120.cut?dl=0)


yeah, just as the image, there are 5 WMSF files in the package.
-----------------------------point
I just want to split the whole package 0120.cut to 5 files with WMSF headers...
Like: 0120.cut -> 1.WMSF & 2.WMSF & ....
-----------------------------point
notice: Please DO NOT TELL ME split by size 0x5538h, it's just coninsistance in this file,
           I have multiple *.cut file like this with different size.

So, i need a batch file or other method.
Woud anyone help me ?
Any help will be greatly appreciated!!!!!
## Post #2
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-06-19T08:49:56+00:00
- Post Title: Help me extract files with string in *.cut

@Acewell
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-19T16:08:41+00:00
- Post Title: Help me extract files with string in *.cut

Try this BMS script, it should do the job:


# .cut file extractor
# By Dave, 2019

set OFFSET 0
set COUNT 1
get FSIZE asize

DO 
	GOTO OFFSET
	GET MISC1 long
	GET SIZE long
	REVERSELONG SIZE
	SET FILENAME COUNT
	STRING FILENAME + ".WMSF"

	LOG  FILENAME OFFSET SIZE

	MATH OFFSET + SIZE
	MATH COUNT + 1

WHILE OFFSET < FSIZE
## Post #4
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-06-20T02:20:42+00:00
- Post Title: Help me extract files with string in *.cut

> Reply from DKDave ↑Thu Jun 20, 2019 12:08 am at Thu Jun 20, 2019 12:08 am
>
> 
Try this BMS script, it should do the job:


# .cut file extractor
# By Dave, 2019

set OFFSET 0
set COUNT 1
get FSIZE asize

DO 
	GOTO OFFSET
	GET MISC1 long
	GET SIZE long
	REVERSELONG SIZE
	SET FILENAME COUNT
	STRING FILENAME + ".WMSF"

	LOG  FILENAME OFFSET SIZE

	MATH OFFSET + SIZE
	MATH COUNT + 1

WHILE OFFSET < FSIZE

OMG, Thank u So much for your perfect job!!!
It did work for me, Thanks !! 
Maybe i need to learn more about quickbms!!
Thank you DKDave,  You have been a great help!!!
