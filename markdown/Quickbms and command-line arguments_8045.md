## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-13T18:31:40+00:00
- Post Title: Quickbms and command-line arguments

Is there a way to pass in command-line arguments to the script?
So like if I'm using zip.bms, I can just pass in a password rather than hardcode it.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-14T21:39:43+00:00
- Post Title: Quickbms and command-line arguments

it's possible to use the -a command which creates some variables called quickbms_arg1 and so on.
for example:

quickbms -a "hello bye how_are_you" script.bms file

will create the variables:
quickbms_arg1 = "hello"
quickbms_arg2 = "bye"
quickbms_arg3 = "how_are_you"

so if you get zip.bms and replace:
set ZIP_PASSWORD string ""
with:
set ZIP_PASSWORD string quickbms_arg1

it should work correctly
