## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-24T16:45:12+00:00
- Post Title: quickbms string operations

Two things I want to get:

Length of some string NAME
some substrings of NAME (ie: first 5 characters, last 3 characters, etc)

Is this possible? How to accomplish?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-24T17:18:57+00:00
- Post Title: quickbms string operations

read the help file included in quickbms?
just look up 
String VAR OP VAR
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-24T18:07:05+00:00
- Post Title: quickbms string operations

How can I combine the operations to determine if a substring is part of a string?

ie: determining whether the "." character is in some string, and possibly the index.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-10T01:07:21+00:00
- Post Title: quickbms string operations

If it's only one character, you can just scan through the string:

```
set DETECT 0x2e # needs to be the hex representation
callfunction searchstring 1

startfunction searchstring 
   strlen NAMEL NAME
   set EXISTS 0
   for i = 0 < NAMEL
      getVarChr T NAME i
      if T == DETECT
         set EXISTS 1
         break
      endif
   next i
endfunction
```

You'll also get the position of the character with this (variable i). It's a bit tricky to work with strings with QuickBMS. 
Do you really need to check for a string of length more than one? What exactkly do you want to do? Your example with the "." reminds me of "splitting file name and extension if there is one".
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-10T01:15:45+00:00
- Post Title: quickbms string operations

in your example of the dot if you want to know directly the extension of a filename located in a variable (like set VAR string "myfile.txt") you can just use:
set EXT extension VARIABLE

the String command can be used to do search operations but sometimes it's a bit complex and in some cases I'm still undecided on the return value.
for example if you want something like strchr you can just use the '&' operator or just "strchr" (it's the same since it's an alias):

set NAME string "myfile.txt"
set TMP string NAME
string TMP &= "."

in this case TMP will be ".txt"
you can do all the tests you want just like I did simply writing these example scripts and then placing a print command at the end, like:
print "result: %TMP%"
