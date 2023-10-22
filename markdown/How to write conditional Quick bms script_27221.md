## Post #1
- Username: SubZer0
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 23, 2021 3:57 am
- Post datetime: 2023-09-20T19:51:12+00:00
- Post Title: How to write conditional Quick bms script

I am writing script but I failed to understand how to use condition in quick bms script.

Say at start of file which I unpack have xx xx xx xx (4bytes)
Then script 'callfunction_1' 

And if it dont have those matching 4bytes then it callfunction_2

Appreciate any help on this noob query
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-09-21T19:49:24+00:00
- Post Title: How to write conditional Quick bms script

Try this:

```

if SIGN == 0x58504854
 	callfunction PRINT_AAA
else
 	callfunction PRINT_BBB
endif	



startfunction PRINT_AAA
 	print "AAA"
endfunction


startfunction PRINT_BBB
 	print "BBB"
endfunction
```
## Post #3
- Username: SubZer0
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 23, 2021 3:57 am
- Post datetime: 2023-09-23T07:48:14+00:00
- Post Title: How to write conditional Quick bms script

Thank you I will try and let you know
