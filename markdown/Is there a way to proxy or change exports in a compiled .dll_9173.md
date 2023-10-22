## Post #1
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-06-30T01:41:51+00:00
- Post Title: Is there a way to proxy or change exports in a compiled .dll

Just wondering if anyone has experience with this. It would seem that I have a .dll that was written badly and I want to change the export lists which would in turn fix some of the problems with it. I heard that you could actually proxify the export list and change them but I don't know how to do it. Any help would be greatly appreciated.
Here is an example of what I want to do with it, supposedly they wrote the exports like this
??0CRxAudio@@QAE@XZ

it should be called this instead
CRxAudio::CRxAudio(void)

the way it is now is causing horrible cpu spikes.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T02:16:09+00:00
- Post Title: Is there a way to proxy or change exports in a compiled .dll

I have not understood the last statement, because:
"??0CRxAudio@@QAE@XZ" indeed is "CRxAudio::CRxAudio(void)"

you can hook or proxify the exported functions of the dll, I have had experience with both although I have preferred the dll proxy solution but it may be not accepted on the current operating systems.
in case it helps [http://aluigi.org/mytoolz.htm#dllproxyskel](http://aluigi.org/mytoolz.htm#dllproxyskel)

I don't have a public example of hooking written by me at the moment but you can find many things on google.
## Post #3
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-06-30T02:56:55+00:00
- Post Title: Is there a way to proxy or change exports in a compiled .dll

thanks I totally forgot about that program. The problem im having is that I don't remember how to hook the .def to a dll. I did google search and it doesn't seem to have what I need. The .dll is already compiled so the source isn't available to me. 

I have permission to modify the .dll
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T12:28:13+00:00
- Post Title: Is there a way to proxy or change exports in a compiled .dll

in this case you are lucky because you already have the full prototype of the function due to the mangled function name:
 __thiscall CRxAudio::CRxAudio(void)

you are less lucky for the fact that you don't have the structure (the H file) of the CRxAudio audio object, but most depends by what you want to do... I mean what's your target.

at the moment I don't remember if dllproxyskel is able to handle mangled function names, I mean that probably it's necessary additional "manual" work to correct the names inside the C generated file.
