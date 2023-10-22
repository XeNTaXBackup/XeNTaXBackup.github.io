## Post #1
- Username: gazitron
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 12, 2012 8:33 am
- Post datetime: 2012-01-12T00:52:33+00:00
- Post Title: Please help to create a patch for CoJ: BiB

Hello everyone.
I am Gazitron from Call of Juarez: Bound in Blood forum.
We all like this game but a publisher stopped to support this game right after its release. 
The MP mode is amazing but still needs fixes. 
I work on it 2 years but finally stuck at the point of modifying the dll file as well as modifying the rpack files.

Rpack files: I noticed that one guy finally created such a tool to extract the content from rpack files for Dead Island game (same engine) but that program doesn't work for CoJ: BiB or set wrong. 

Dll file: the developers hide there all the useful functions such as server settings and all other essential information. We can't ban players, no voice commands, no dedicated server management, no anticheat etc. But I checked and all those functions are hidden in the dll. I just surprised why developers disabled all those features in CoJ: 2 if they added everything successfully in CoJ: 1. 

Please, we beg for help for 2-3 years since that game was released. I do what I can to enjoy it but still need help. 

Please. if some coder is interested or somebody wants to help you are welcome!

If some coder will be able to join us we will try to create a donations.
## Post #2
- Username: gazitron
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 12, 2012 8:33 am
- Post datetime: 2012-01-12T19:36:35+00:00
- Post Title: Please help to create a patch for CoJ: BiB

Or I have started to integrate the LUA code into the game. Can you please tell me is this a good idea or I will waste my time?

Thank you.
## Post #3
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-01-17T10:16:52+00:00
- Post Title: Please help to create a patch for CoJ: BiB

If you want us to help you with the rpack files please post some (upload them to e.g. [Mediafire](http://www.mediafire.com))
if they are too big to upload (>50 MB) cut them with a file cutter and post the first and last 10 MB.

LUA is great if it has access to all ingame variables, else it makes little sense to use it.

Please post more details what you did work on, maybe we can help you with that.
I personally have no idea how to edit DLL files.
Have you checked all the available functions with something like [DLL export viewer](http://www.nirsoft.net/utils/dll_export_viewer.html)
## Post #4
- Username: gazitron
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 12, 2012 8:33 am
- Post datetime: 2012-01-17T22:54:21+00:00
- Post Title: Please help to create a patch for CoJ: BiB

> Reply from 0xFAIL
>
> If you want us to help you with the rpack files please post some (upload them to e.g. Mediafire)
if they are too big to upload (>50 MB) cut them with a file cutter and post the first and last 10 MB.

LUA is great if it has access to all ingame variables, else it makes little sense to use it.

Please post more details what you did work on, maybe we can help you with that.
I personally have no idea how to edit DLL files.
Have you checked all the available functions with something like DLL export viewer

Hello, thank you for help!
The .rpack files are useless but at the current stage are not so important as the rest modding of the dedicated server which we try to implement.... 

We try to change the address of master server which is used for connection of dedicated server (its address is in the code) so that it will connect to our own master server because the old one has very low speed and bad stability. Or at least remove the connection to master server at all so that connections between server and clients will be straight. 

Then there is no BAN command activated (but in the code), the other guy wrote the script to activate it but we are looking for the way how to run this script in game. 

Also can't open the console to modify the game.

But everything is in the code, just need to activate it probably by useing console commands but they are hidden in the code + can't open the console menu.
