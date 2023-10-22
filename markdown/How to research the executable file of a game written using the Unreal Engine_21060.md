## Post #1
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-09-01T13:03:23+00:00
- Post Title: How to research the executable file of a game written using the Unreal Engine?

I want to make changes to the gameplay of a game written using the Unreal Engine.

To do this, I need to find the function that interests me, embed my DLL in the game process, and change the pointers.

But the UE prefers static linking (or DLLs are embedded, idk). Therefore, I see only one executable file that weighs 109 mb.
 How to isolate a game code from a framework code?
Or how to recognize the code of the framework?
How to work effectively with files of this size?
What pitfalls await me?
[The same question at StackExchange](https://reverseengineering.stackexchange.com/questions/22014/how-to-research-the-executable-file-of-a-game-written-using-the-unreal-engine)
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-10-15T07:57:25+00:00
- Post Title: How to research the executable file of a game written using the Unreal Engine?

You gave us very little informations.
Like:
* Name of the game.
* Unreal Engine version.
* Might be DRM protected (Themida, Denuvo, VMProtect) if it's online or newer title (thus not possible to disassemble).
* Dll's might be embedded as resources (use resource hacker if this statement is true).

If, it's a full built game with statically linked libraries, it would be hard/impossible to find correct method (there can be hundreds of thousands of them)

I would suggest you that you first look for:
* ini settings, they store a lot of tweak variables.
* look inside packages, they might store some data tables.
* try to run the game in a editor mode (if it's an uncooked game), so you can explore/edit game's assets.
