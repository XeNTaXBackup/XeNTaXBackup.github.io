## Post #1
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2011-09-17T19:27:22+00:00
- Post Title: Quickbms String Help

I need some help with modifying a string in quickbms.

Say I have a string "thisismysuperkey" that is 0x7468697369736D7973757065726B6579 in hex

I want to increment it in my loop by 1 so it becomes "uhisismysuperkey" 0x7568697369736D7973757065726B6579 in hex

next round it becomes 
0x7668697369736D7973757065726B6579 in hex, etc

Is this possible in Quickbms?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-17T20:53:26+00:00
- Post Title: Quickbms String Help

sure its possible but we need your script to help you.
## Post #3
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2011-09-17T21:24:46+00:00
- Post Title: Quickbms String Help

Ok Here's a simple example

```
#GetDString KEY 16

print "the variable KEY of the file has the value %KEY%"
print "the variable KEY of the file has the value %KEY|h%"

MATH KEY + 1  #this doesn't work 

print "the variable KEY of the file has the value %KEY%"
print "the variable KEY of the file has the value %KEY|h%"

```


I attached a file to run the script on, it's just my 16 byte key "thisismysuperkey".
[file2.zip](https://xentaxbackup.github.io/file/4717_file2.zip)
## Post #4
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2011-09-19T08:05:05+00:00
- Post Title: Quickbms String Help

I made a little progress, a easy question.

How would I get a variable into a temporary_file?

Say I wanted to write the variable KEY in the example to a temporary_file.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-09-20T17:23:44+00:00
- Post Title: Quickbms String Help

```
encryption rot "\x01"
string NAME E= NAME
encryption "" ""
print "%NAME%"
```
## Post #6
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2011-09-20T22:55:10+00:00
- Post Title: Quickbms String Help

Thanks for the help aluigi, I try that code out.

How would i get my variable into a temporary_file?
