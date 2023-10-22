## Post #1
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-04-15T22:18:17+00:00
- Post Title: A serious question regarding languages used

I'm currently in the process of making some modifying tools for a game. I have made substantial progress these past few weeks, but I have been using nothing but MaxScript. You know, that scripting language in 3DS Max (obviously). I've had this thought in the back of my head for awhile now, which goes something like this:

"What kind of 'programmer' uses MaxScript?"

I honestly feel that, by using MaxScript, I am not considered an actual programmer. I can script things pertaining to my modding tools with little to no issue in MaxScript. I've made other things as well, which are actually pretty advanced tools that may turn into something bigger down the line. But if I try moving production over to, say, C++; things go downhill. I'm conflicted by all of this and would like to hear from some of the others around here.

Basically, my long-term goal in life is to pursue a career based around programming. I enjoy it thoroughly. But I feel slightly discouraged because MaxScript seems so easy to use...is that just a misjudgment? Is MaxScript considered a programming language that is not considered some kind of "wannabe-language"? I don't know why I suddenly feel this way, but it sure is bugging the crap out of me. I almost feel like I should know C++ and all that other crap, haha.

Yeah, this is kind of stupid. But it's bothering me!
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-04-15T23:50:21+00:00
- Post Title: A serious question regarding languages used

The only times you should worry about the language you use are if you're applying for a position that requires knowledge of a particular language, or if you're working on a project that the language you're using doesn't lend itself to. That is, using the right tool for the job and meeting employment requirements. Any time where you're being judged for the language you're using, though, rather than what you're accomplishing with that language, you can ignore the person.

Keeping in mind that I'm not familiar with MaxScript and can't program in anything but TI-89 BASIC and a little Javascript, if you're looking for a language that others are likely to consider closer to "real" programming than MaxScript, without straying too far from the scripting language feel, I'd recommend Lua or Python for straightforward languages that are pretty easy to pick up, while being quite powerful (Lua is incredibly lightweight and, as such, is often used for scripting in games, so it's also got that going for it). If you're interested in learning more about web design/programming, you may want to look into Ruby (which is similar to Python in many ways, though (from what I've read) with somewhat weird syntax in some areas) or Javascript. If you insist on learning a "traditional" programming language, and you're looking at C++, according to what I've read at least, it would be easier to start with C and go from there, and you may also want to look at Java. If you're looking for something more "different", Erlang and Scala are popular choices for functional programming.

Now, let's have a "real" programmer come in here and tell me I'm full of crap.
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-04-16T01:53:41+00:00
- Post Title: A serious question regarding languages used

> Reply from Dinoguy1000
>
> The only times you should worry about the language you use are if you're applying for a position that requires knowledge of a particular language, or if you're working on a project that the language you're using doesn't lend itself to. That is, using the right tool for the job and meeting employment requirements. Any time where you're being judged for the language you're using, though, rather than what you're accomplishing with that language, you can ignore the person.

Keeping in mind that I'm not familiar with MaxScript and can't program in anything but TI-89 BASIC and a little Javascript, if you're looking for a language that others are likely to consider closer to "real" programming than MaxScript, without straying too far from the scripting language feel, I'd recommend Lua or Python for straightforward languages that are pretty easy to pick up, while being quite powerful (Lua is incredibly lightweight and, as such, is often used for scripting in games, so it's also got that going for it). If you're interested in learning more about web design/programming, you may want to look into Ruby (which is similar to Python in many ways, though (from what I've read) with somewhat weird syntax in some areas) or Javascript. If you insist on learning a "traditional" programming language, and you're looking at C++, according to what I've read at least, it would be easier to start with C and go from there, and you may also want to look at Java. If you're looking for something more "different", Erlang and Scala are popular choices for functional programming.

Now, let's have a "real" programmer come in here and tell me I'm full of crap.
You're full of crap.  LOL

No, but seriously, the best base to start with, is at least some kind of unmanaged language, like C/C++, or even better, if you can handle it, a really low level language like ASM.  Sure, you can get by with only high-level languages or managed languages, but you're only limiting yourself.  There are many things that can be accomplished with high-level programming, and I use C# a lot, but it can't do everything as well as C/C++, and scripting languages are even more restricted with what you can really do.  If you can get away with it, they're fine, but you are better off learning as much as you can, so there will never be any job you can't do.

For an example, using MaxScript, we could import Yukes models into 3DS Max, but because of the way MaxScript works, it emulating mouse clicks, it would take a LONG time, up to 45 seconds or longer, to load a complete arena.  I went ahead and used C++ and made an actual 3DS Max import plugin, and now a complete arena can be loaded in a split second.  Unmanaged programming will always out perform managed programming, always.
## Post #4
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-04-16T03:11:48+00:00
- Post Title: A serious question regarding languages used

I've found a liking to programming languages such as Pascal/Delphi, Python, LUA, and MaxScript. It must be the simplicity of the syntax yet sheer power of the language. Nobody has judged me about using MaxScript, I'm simply judging myself for some reason.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-04-16T06:01:31+00:00
- Post Title: A serious question regarding languages used

Aah, it would have helped some if you'd mentioned the breadth of your experience in your OP. Knowing that, I would move to back brienj completely in saying your next step should probably be C/C++/ASM, or *something* that offers you more complete control over the machine. I'd also again suggest a strongly functional language such as Erlang or Scala, simply for the fact that functional languages, when used as they're designed to be, are so radically different from other languages (if you like, think of it like this: C/ASM give you a really good understanding on how your computer works at a very low level, and functional languages force you to change your entire perspective). The general theme here, though, is broadening your skillset.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-04-16T17:09:47+00:00
- Post Title: A serious question regarding languages used

To me, if I can boss my computer around to get what I want done, then it is a fully qualified programming language.
Doesn't matter if it is not as fast, or requires more effort to get things done.

I prefer high-level languages because they are easier to write (for me anyways), but will turn to lower-level stuff if I really need power. Of course that requires me to learn a new language but it's the same thought process.
