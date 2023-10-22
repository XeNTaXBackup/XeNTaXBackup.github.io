## Post #1
- Username: Shadowmael
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 28, 2022 11:00 pm
- Post datetime: 2022-12-02T00:05:22+00:00
- Post Title: how does the structure of a CPK work?

I was analyzing the files inside the psp Fate/extra game, then a question came to my mind 

How do CPK files work? In this case, its structure, pointers, etc... With that in mind, I wanted to make an extractor for Fate/extra, an extractor capable of working on different devices, like for example on android phones, Linux, etc...

But I don't know anything about this file... The most I know is that at the beginning of the file header there is a String "CPK" not all CPK files contain this header

First I tried parsing the quickbms script used to extract the CPK files

bms script link: [http://aluigi.altervista.org/papers/bms/cpk.bms](http://aluigi.altervista.org/papers/bms/cpk.bms)

Even so, I still couldn't understand very well how CPK files work, after looking at the first lines of the script I was able to come to a conclusion. 

```
// this endian big is "wrong" because the first values ​​are actually little endian
comtype cpk

idstring "CPK "
// here it checks if the header starts with "CPK"

set query->offset long 0
// here it takes 4 bytes and uses it as a pointer

set query->index long 0
set query->name string "TocOffset"
// these two lines above are used to get 4 bytes each but I don't know for which server

callfunction query_utf 1
// Here it seems to call a function 
set toc_offset long UTF_VALUE
```


There are many questions in my head about CPK files and I would like to understand more about how they work 

CPK: [https://drive.google.com/file/d/1Y2P4dF ... p=drivesdk](https://drive.google.com/file/d/1Y2P4dFoZMtiBISRGVr-2Ug4ONTatxp7W/view?usp=drivesdk)

Right above I left the CPK link that I mentioned at the beginning of the text 

I know it's a lot to ask for a detailed explanation of these CPK files since there are several formats and different structures but I still want to ask for help for you more experienced ones 

Yeah I tried parsing the codes from the CriPakTools But as I never used C# I couldn't understand much 

CriPakTools: [https://github.com/esperknight/CriPakTo ... kTools.exe](https://github.com/esperknight/CriPakTools/blob/master/Build/CriPakTools.exe)
## Post #2
- Username: Shadowmael
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-02T20:01:43+00:00
- Post Title: how does the structure of a CPK work?

You haven't posted any details. How do you expect people to help you if you didn't tell us anything useful like:
- What scripts are you talking about? Can you link them here?
- What game are those script for?
- Which CPK format do you try to analyze? (Yes, there are few formats with the same extension...)
- A CPK sample attached to the post or shared on some hosting server like mega.nz, google drive would be nice


Also using something like "!!!!!!??????" on the end of your post doesn't help with anything. 


You should also check out this link [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
There are a lot tutorials there explaining how to read and write this "code" you were talking about 

By the way, every command is explained in the quickbms documentation [http://aluigi.altervista.org/papers/quickbms.txt](http://aluigi.altervista.org/papers/quickbms.txt)
## Post #3
- Username: Shadowmael
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 28, 2022 11:00 pm
- Post datetime: 2022-12-02T20:18:35+00:00
- Post Title: how does the structure of a CPK work?

You're right, it was my mistake to ask for help without giving details about...

I'm already uploading the CPK file and I'll edit the post to correct my error, I'll also give more details
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-02T21:47:22+00:00
- Post Title: how does the structure of a CPK work?

For some reason we didn't have this format documented on our wiki.
Now it's there, I've just created this article [http://wiki.xentax.com/index.php/CRI_Middleware_CPK](http://wiki.xentax.com/index.php/CRI_Middleware_CPK)

You should be really interested in this gist as well
[https://gist.github.com/unknownbrackets ... ffb7f1bae4](https://gist.github.com/unknownbrackets/78c4631a4091044d381432ffb7f1bae4)
because file format is described in details on this page.
