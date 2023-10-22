## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-14T13:24:07+00:00
- Post Title: good tutorials for anything relates to resource reversal

"Go learn it yourself"

While the advice is useful, it is not useful if there are no useful leads.
While ideally people should understand something from scratch, that is unrealistic for most purposes cause not everyone comes from the same background, and this typically means they don't come from a particularly technical background.

Post links or docs that you find very coherent and straightforward for anything related to resource reversal.

Maybe more people will be interested in picking up new skills compared to just a bunch of requests. I've seen a lot of people working on their own games but for the moat part there are about twice as many requests with no obvious support.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-14T21:32:39+00:00
- Post Title: good tutorials for anything relates to resource reversal

Not sure if we really need a thread in the tutorials section of a forum revolving around reversing data formats, calling for tutorials on reversing data formats.  But you seem to be making regular strides here in your own work. Have you backtracked your own steps to reference how you've come upon your knowledge? All the tutorials, people, and tidbits that have helped you along the way. Perhaps this would be a good place for you to sum them up and reference them for other newcomers.

For me, the path was just too long and treacherous to single out any particular tutorial(s) or people who have helped me. It's also been largely on-the-job experience for me, so I have my old bosses and even coworkers to thank more than anyone, and it's really quite difficult to replicate the results of all those experiences and conversations in the form of a tutorial. I think that's how it is for most people. As I covered in a post the other week (in the "tutorials on tutorials" thread), the ability to reliably reverse data of is a culmination of many different bodies of knowledge/experience. I think I summed up what those bodies are in the context of models pretty well in that post. Every different kind of data also has its own different set of knowledge prerequisites. There isn't really a silver bullet. You can't understand most data if you don't know how that data was constructed and/or what it's used for, and good luck reversing anything that you don't actually understand.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-03-15T20:35:19+00:00
- Post Title: good tutorials for anything relates to resource reversal

> Reply from MrAdults
>
> Not sure if we really need a thread in the tutorials section of a forum revolving around reversing data formats, calling for tutorials on reversing data formats.  But you seem to be making regular strides here in your own work. Have you backtracked your own steps to reference how you've come upon your knowledge? All the tutorials, people, and tidbits that have helped you along the way. Perhaps this would be a good place for you to sum them up and reference them for other newcomers.

For me, the path was just too long and treacherous to single out any particular tutorial(s) or people who have helped me. It's also been largely on-the-job experience for me, so I have my old bosses and even coworkers to thank more than anyone, and it's really quite difficult to replicate the results of all those experiences and conversations in the form of a tutorial. I think that's how it is for most people. As I covered in a post the other week (in the "tutorials on tutorials" thread), the ability to reliably reverse data of is a culmination of many different bodies of knowledge/experience. I think I summed up what those bodies are in the context of models pretty well in that post. Every different kind of data also has its own different set of knowledge prerequisites. There isn't really a silver bullet. You can't understand most data if you don't know how that data was constructed and/or what it's used for, and good luck reversing anything that you don't actually understand.

...Which leads to perhaps the most powerful method of learning about these things: build them yourself. If you're looking for a deep understanding of a given type of format, as opposed to just trying to get format 477384 supported so you can do things with it, building a system that uses that format, and designing your own format from scratch, will teach you all sorts of things about how such formats are typically used and about some of the tradeoffs involved in various choices, that even the best and most thorough tutorials couldn't easily convey.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T14:32:20+00:00
- Post Title: good tutorials for anything relates to resource reversal

Ya, I guess I did go with the "build yourself" idea.
I can write programs so that made it easier to start with.

The metasequoia format provided a simple text format to understand how basic 3D ideas come together (materials, vertices, faces, and nothing else), and naturally provides a good start for parsing 3D formats.

After writing the first import and export plugins for MQO, I went on to work on another format which was also text, and imported that and exported to MQO.

Realizing that it was just too much work to keep writing the same MQO export plugin, I thought of ways to provide a standard interface that I could use, and ended up writing the Sanae3D converter which focused on a plugin architecture for importing and exporting formats just so I can be lazy and re-use my export plugin (much like how noesis is done, though at that time I didn't even know about noesis)

Binary formats came maybe a month after I started, and at the beginning it was like ya, what the heck is all this? Looking at chrrox's shaiya tutorial didn't get very far, but then after realizing how data is represented in hex and how structured 3D files tend to be (compared to other things like save files), it suddenly just all  makes sense.

Then the rest of it was just looking at formats one at a time and seeing different patterns.
