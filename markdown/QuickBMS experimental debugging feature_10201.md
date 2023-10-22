## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-06T10:47:05+00:00
- Post Title: QuickBMS experimental debugging feature

I have just released a new version of QuickBMS (0.5.17) with an experimental feature added to get the key from the Simraceway game process.

It's just a simple debugger that breaks when there is a breakpoint or an exception and automatically creates variables containing the x86 registers (so yes you can use print "%EAX%").

It's really very basic and implemented on the fly to help the people who were contacting me about Simraceway but currently the idea works and I can improve it in the next months.

Example script:

```
savepos OFFSET

# relative offset of the function in the module
math OFFSET += 0x00001122

# or we can just search the instructions of the function
findloc OFFSET string "\x55\x8B\xEC\x8B\x55\x0C\x0F\xB6\x0A"

# set breakpoint
goto OFFSET
put 0xcc byte

# yeah the following cycle takes some cpu, there is no sleep/wait in quickbms
# wait till breakpoint
for EIP = 0 == 0
    # do nothing
next

# debug purpose
print "EAX %eax|x%\nEBX %ebx|x%\nECX %ecx|x%\nEDX %edx|x%\nESI %esi|x%\nEDI %edi|x%\nEBP %ebp|x%\nESP %esp|x%\nEIP %eip|x%"

# get the stack arguments
goto ESP
get RET_ADDR long
get ARG1 long
get ARG2 long
get ARG3 long

# read the content of the second argument, maybe a string or data
goto ARG2
getdstring KEY 32
```


How to use it:
when the game is running or maybe just after it has been launched just execute the following command:

```
quickbms.exe -p simraceway_getkey.bms process://PROCESS_NAME/debug
```
where PROCESS_NAME is replaced with name of the game.
QuickBMS allows also to specify the exact module if the function you want to monitor is not in the executable: process://PROCESS_NAME:MODULE_NAME/debug

I hope you like the idea but at the moment if you insert a breakpoint then you can't change it back and re-executing the code... oh well maybe in the next version :)
## Post #2
- Username: mschreiner
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 24, 2013 1:26 am
- Post datetime: 2013-07-09T02:17:08+00:00
- Post Title: QuickBMS experimental debugging feature

I tried this and it did not seem to do anything.

Also the zip files you can download from there will not open.
They are really trying to make it harder....LOL
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-07-13T08:27:17+00:00
- Post Title: QuickBMS experimental debugging feature

it works perfectly as described here:
[http://aluigi.altervista.org/misc/simra ... wfiles.txt](http://aluigi.altervista.org/misc/simraceway_newfiles.txt)
