## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-13T19:26:45+00:00
- Post Title: Cabal 2 [Crytek files]

[http://www.2shared.com/file/AZrHC7-2/char_40.html](http://www.2shared.com/file/AZrHC7-2/char_40.html)

So in another thread we are now able to get the models for this game and it's crytek files .chr,.caf etc

I tried with the aion importer for blender but it can only recognize .cgf files.

Any clue what to do? Inlcuded is .chr file, textures and animations
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-03-13T22:46:58+00:00
- Post Title: Cabal 2 [Crytek files]

KO in a minute!  

In Short, it a modified CryTek file. The resource table had a extra dword for the chunk size! That is!
struct Res_Table {
   dword          ChunkID
   dword          ChunkVer
   dword          ChunkOffset
   dword          ChunkIndex
   dword          ChunkSize
}
[Cabal2_test.jpg](https://xentaxbackup.github.io/file/5184_Cabal2_test.jpg)
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-14T11:01:16+00:00
- Post Title: Cabal 2 [Crytek files]

Cool, will you support this script in fatimporter soon? Looking forward to it
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-04-10T01:59:21+00:00
- Post Title: Cabal 2 [Crytek files]

Anyone can help with this model format please?

[http://www.2shared.com/file/AZrHC7-2/char_40.html](http://www.2shared.com/file/AZrHC7-2/char_40.html)

Its from Cabal 2, maybe can made Noesis script?.
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-04-10T17:30:21+00:00
- Post Title: Cabal 2 [Crytek files]

fat already made it but will not release it yet, but soon we will get our hands on this beauty
## Post #6
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-04-11T07:33:41+00:00
- Post Title: Cabal 2 [Crytek files]

> Reply from pixellegolas
>
> fat already made it but will not release it yet, but soon we will get our hands on this beauty

Mmmm well if u ask i see in fatimporter its already finished, i see the skeleton position its right and the model its in T position, also fat madde the window of preview from game in fatimporter, wath u think left?.

But maybe fat its bussy with other thinks, then it hink its bether of somebody can try extract with other system.
## Post #7
- Username: w3rnis
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 14, 2015 6:21 am
- Post datetime: 2015-11-14T13:59:49+00:00
- Post Title: Cabal 2 [Crytek files]

> Reply from fatduck
>
> KO in a minute!  

In Short, it a modified CryTek file. The resource table had a extra dword for the chunk size! That is!
struct Res_Table {
   dword          ChunkID
   dword          ChunkVer
   dword          ChunkOffset
   dword          ChunkIndex
   dword          ChunkSize
}

Maybe someone got script for cabal 2?
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-14T21:15:09+00:00
- Post Title: Cabal 2 [Crytek files]

Noesis with CryTek plugin doesn't work? I've had script for Cabal 2 model, maybe I can find it. Can you provide sample model?
## Post #9
- Username: w3rnis
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 14, 2015 6:21 am
- Post datetime: 2015-11-15T10:42:07+00:00
- Post Title: Cabal 2 [Crytek files]

Yep you are right Noesis with CryTek plugin workd  tnx next question...
in this video guy uses fatimporter with cabal script but i couldnt find it anywhere it wasn't public or something ? )
[https://www.youtube.com/watch?v=LVgMUs8ngfs](https://www.youtube.com/watch?v=LVgMUs8ngfs)
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-11-24T13:08:46+00:00
- Post Title: Cabal 2 [Crytek files]

> Reply from w3rnis
>
> Yep you are right Noesis with CryTek plugin workd  tnx next question...
in this video guy uses fatimporter with cabal script but i couldnt find it anywhere it wasn't public or something ? )
https://www.youtube.com/watch?v=LVgMUs8ngfs
lol first of all, the importer he got was not public, is private payed, and is for Cabal 1 no Cabal2, Cabal 1 than 2 format was change and engine too so useless.
## Post #11
- Username: w3rnis
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 14, 2015 6:21 am
- Post datetime: 2015-11-25T15:10:26+00:00
- Post Title: Cabal 2 [Crytek files]

> Reply from CriticalError
>
> w3rnis wrote:Yep you are right Noesis with CryTek plugin workd  tnx next question...
in this video guy uses fatimporter with cabal script but i couldnt find it anywhere it wasn't public or something ? )
https://www.youtube.com/watch?v=LVgMUs8ngfs
lol first of all, the importer he got was not public, is private payed, and is for Cabal 1 no Cabal2, Cabal 1 than 2 format was change and engine too so useless.

omg... ty for explanation..... i know what engines and what formats both games uses...MR Smartass. I was asking about that tool cuz i need it for cabal 1....
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-11-25T16:39:35+00:00
- Post Title: Cabal 2 [Crytek files]

> Reply from w3rnis
>
> CriticalError wrote:w3rnis wrote:Yep you are right Noesis with CryTek plugin workd  tnx next question...
in this video guy uses fatimporter with cabal script but i couldnt find it anywhere it wasn't public or something ? )
https://www.youtube.com/watch?v=LVgMUs8ngfs
lol first of all, the importer he got was not public, is private payed, and is for Cabal 1 no Cabal2, Cabal 1 than 2 format was change and engine too so useless.

omg... ty for explanation..... i know what engines and what formats both games uses...MR Smartass. I was asking about that tool cuz i need it for cabal 1....so if you know why ask in a topic don't have nothing related to cabal 1? this is a topic of Cabal 2 no Cabal 1, so in this case you need do a new topic related to this and make every question there, i'm not smart or whatever you call, know and others are more about but nobody is a genius or anything.
