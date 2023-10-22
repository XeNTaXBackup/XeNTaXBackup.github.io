## Post #1
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2007-12-03T17:21:43+00:00
- Post Title: Best way to scan a file?

Well, I'm relatively new here, I don't know if this is the apropiate forum   

I'm coding a file ripper for a game (in C), but my problem is that it's just TOOO slow   

My method is just: Get a DWORD, compare it with the magic. If it coincides, extract the file. If not, just go back 3 characters and return to scanning.

But If I just do this on Hex Workshop, it gives me the result much faster. What's the secret? Checking it character by character?

The question is just... what's the best way to scan a big file?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-03T18:21:32+00:00
- Post Title: Best way to scan a file?

Well this is a string matching problem. You can decrease scanning time by preprocessing the search string. An example is the [Knuth-Morris-Pratt algorithm](http://en.wikipedia.org/wiki/Knuth%E2%80%93Morris%E2%80%93Pratt_algorithm) that 
> searches for occurrences of a "word" W within a main "text string" S by employing the observation that when a mismatch occurs, the word itself embodies sufficient information to determine where the next match could begin, thus bypassing re-examination of previously matched characters

This algorithm already gives a good improvement on speed.
But a (general) file ripper needs to compare many signatures so you might want to have a look at other algos just like [Aho-Corasick](http://en.wikipedia.org/wiki/Aho-Corasick_algorithm).
I personally used this one as a test in my own small scanning engine
## Post #3
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2007-12-04T14:56:03+00:00
- Post Title: Best way to scan a file?

I, too, would use Aho-Corasick. You don't have to worry about storing the generated graph somehow: just use the canonical algorithm to build the scanning-graph on runtime. Normally, you have only a few hundred signatures at most, so the time it takes to build the graph is quite small compared to the search time itself.

Advantages:
Aho-Corasick trivially supports multiple matching patterns (i.e. if you have a file magic ABCD and another one BCD it will find both in the string XXABCDYY)
It's blazingly fast, especially when combined with a smart buffering algorithm (so that you don't have to read each byte from the file by itself). The stdio buffers work well enough in practice.
The time it takes to scan does not depend on the number of patterns that you're searching for (however, more patterns take longer time to build the graph for them). You only have to take one step in the graph for each byte read, and that takes constant time.

BTW, does anyone know if there are other similar parallel-matching agorithms available? Aho-Corasick was the only one I could find.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-04T15:58:53+00:00
- Post Title: Best way to scan a file?

How do you implement the graph? The simple way is to use bidimensional arrays, linear lists are also possible and I found an interesting approach here: [http://linux.thai.net/~thep/datrie/datrie.html](http://linux.thai.net/~thep/datrie/datrie.html)

I don't know any other algorithm like AC. In the end it simply combines tries with the "failure function" idea from KMP.

I thought a lot about how to efficiently implement matching with wildcards to support signatures like 5A 78 ?? FF ?? ??. I found some ideas in those slides: [http://www.cs.uku.fi/~kilpelai/BSA05/le ... ides04.pdf](http://www.cs.uku.fi/~kilpelai/BSA05/lectures/slides04.pdf)
The drawback is you need an array as big as the text to store occurence counts. I wonder if this is possible without much memory usage
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-06T12:06:18+00:00
- Post Title: Best way to scan a file?

> Reply from Rheini
>
> I thought a lot about how to efficiently implement matching with wildcards to support signatures like 5A 78 ?? FF ?? ??. I found some ideas in those slides: http://www.cs.uku.fi/~kilpelai/BSA05/le ... ides04.pdf
The drawback is you need an array as big as the text to store occurence counts. I wonder if this is possible without much memory usage
Another problem is that there approach is only able to search for a single string with wildcards. And you have to go through the whole array and check the counts after the scan. So it also doubles the needed time.

I got an idea that theoretically solves most problems. Why not using a kind of sliding window (implemented as a circular buffer) to store occurence counts?
Every time something is written into the buffer the field that is overwritten is checked for a match.
Since we want to use more than 1 search string we have to store an identifier for the keyword besides the occurence count.
So what if there are 2 strings with the same beginning or something similar? This could be solved by using an array of linked lists.

Hope this is somewhat understandable. If you find any flaws in my idea please tell me.
## Post #6
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2007-12-10T10:05:57+00:00
- Post Title: Best way to scan a file?

> Reply from Rheini
>
> How do you implement the graph? The simple way is to use bidimensional arrays, linear lists are also possible and I found an interesting approach here: http://linux.thai.net/~thep/datrie/datrie.html
I'm currently using real heap objects for each node (liked to each other by pointers) but I'm moving it to a simple linear array (each node is an entry into the array). The Trie-method sounds interesting. But I guess until I implement lots and lots of patterns, I won't notice any relevant speed gain (my ripper currently contains about 50 magics for some 10 different file formats)

> Reply from Rheini
>
> I thought a lot about how to efficiently implement matching with wildcards to support signatures like 5A 78 ?? FF ?? ??.
In my implementation I avoid the problem by shortening the pattern to (in your example) 5A 78, and then let the extractor-function handle the final validation. It creates a few false positives (few meaning a few hundreds to a few thousands in a normal file), but since I have to check the format for validity anyways (some file formats have very generic magics like "M.K." or hex 00 01 or something) it's a simple "hack" to add the "false positive checking" stage to them.
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-10T12:52:19+00:00
- Post Title: Best way to scan a file?

> Reply from Darkstar
>
> I'm currently using real heap objects for each node (liked to each other by pointers) but I'm moving it to a simple linear array (each node is an entry into the array).
So you mean an array of linked lists?
AC suggests using an array for more often used states like the root state and using linked lists for the other ones btw.

> In my implementation I avoid the problem by shortening the pattern to (in your example) 5A 78, and then let the extractor-function handle the final validation.
Ok I guess this is the best way for file rippers cause, as you said, the format has to be validated anyway. But wildcard support is necessary for other applications I think.
## Post #8
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-12-15T18:45:43+00:00
- Post Title: Best way to scan a file?

You guys missed the obvious.

You should read from the disk in bulk reads, not by DWORD.  Disk IO is attrocious in terms of speed.  By creating a larger buffer you can remove that speed back to the user.  Although buffer size is largely opinionist.  The optimal reading should be the number of sectors for that track.  Reading one track at a time is generally the fastest method, but IMO you should at least read by blocks of sector sizes.  Disks use cache-ahead analysis, so by reading back 3 bytes, causes a cache miss hit and a reread.

So, if your sector size is 4k, then say a buffer size of 10*4096, or 10 sectors, would seriously improve your speed.  For algorythmic searching, you might wanna do a small calculation so you don't have to read back 3 characters.  There are many "string" searching algos like the one they posted, that fly through chunks of data.

P.S. Shouldn't this be in the coding forum?
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-15T20:30:52+00:00
- Post Title: Best way to scan a file?

File Mapping is a considerable possibility. [http://msdn2.microsoft.com/en-us/library/aa366556.aspx](http://msdn2.microsoft.com/en-us/library/aa366556.aspx)
## Post #10
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2007-12-16T19:17:01+00:00
- Post Title: Best way to scan a file?

Disk buffering is indeed helpful. The stdlib does it's own little buffering scheme with a few bytes/kbytes, so that's a first step ahead. When in doubt, you can also open the file with a special "sequential" flag which optimizes disk I/O for this special case.

File mapping is indeed a nice option because it handles files in 4k blocks at the lowest level possible (on a page basis), and because you can access the file with standard stdlib routines (strstr, strchr, ...).
However, in a 32bit OS, it's not possible to mmap() more than 1-2 gbytes at once, so for bigger files it's a bit more complicated to handle mmap()
