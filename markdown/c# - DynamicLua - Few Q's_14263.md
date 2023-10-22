## Post #1
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2016-04-23T19:28:56+00:00
- Post Title: c# - DynamicLua - Few Q's

Hi !

Hoping to ask advice of anyone that has more experience working with DynamicLua or similar library in c# - i think more c# related though...

Persistence / referencing to or from other class/namespace:-

From what i Understand about dynamic types (which is zero) they do not persist, and only accessible locally, within the class, so ive been creating some methods, to perform whatevr queries.   

If i wanted to access the same Lua instance from other namespace/class without passing that class as a reference how would it work.  If i created new dynamic Lua instance in the same application, would it connect to the initial tables created from other instance, or is it completely seperate ?  what is best way ofdoing this, without explicitly creating a new instance of the class that contains that main instance -  when i make that class static, or the dynamic lua instance itself - it doesnt seem to work (seems to be only way i know that could make it accessible throughout app)

Seperately:- is there any preferred method,to get some manner of printout of the entire Lua DB, tables/funcs etc.  something like a json structure,or just list of tables/func names etc, (Iterate through, use GetDynamicMemberNames ?)

Finally:- why have i seen some cases of guys creating main tables through a new Object[] rather than just stringName of table, or in Queries, referencing the main Table/Root  Through testing isee that it can be used to create hierarchy, but is there any other reason im not aware of

Google failed, & not much activity on DynLua page, so any help appreciated

Cheers
## Post #2
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2016-04-23T20:33:33+00:00
- Post Title: c# - DynamicLua - Few Q's

Removed.
## Post #3
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2016-04-25T21:40:04+00:00
- Post Title: c# - DynamicLua - Few Q's

> Reply from atom0s
>
> In terms of an active Lua implementation for C#, I would recommend checking out MoonSharp:
http://www.moonsharp.org/

The developer is active and the most recent update was pushed 2016-02-09
a
In my opinion, it is one of the better implementations in terms of speed and optimization for Lua < > C#. However in a large scale project that heavily uses Lua you will notice some massive overhead and slow down. (If you need a true implementation of Lua in your project, go with a true Lua implementation in C/C++.)

Dynamic in C# is not restricted to classes only, you can use it anywhere. You can read up more on the dynamic keyword here:
https://msdn.microsoft.com/en-us/library/dd264736.aspx

This can lead to serious overhead and lag if you are constantly talking between the C# app and Lua.

Mate, thank you for such a detailed reply, wasnt expecting as much, so cheers 

I am definately going to give it a go - currently ive found some workarounds here there, but its all such a headache, and there is virtually no way of properly tracking, and handling exceptions with DynLua, just a craptonne of Unknown fatal this error that error spewing out, half the time, and cant even begin to tell where its coming from :/  have to literally test each tables existence and double check vars on setting to even be sure it worked,  mucho headache
