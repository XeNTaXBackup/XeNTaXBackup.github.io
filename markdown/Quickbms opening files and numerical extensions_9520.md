## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T02:35:08+00:00
- Post Title: Quickbms opening files and numerical extensions

```
open FDDE "001"

```


quickbms is interpreting the "000" as a 0 and "001" as 1.
How can I deal with this?

Another issue I have related.
There is a short that stores which file I should be seeking in.

```
get FILENUM short

goto OFFSET FILENUM

```


FILENUM is 0, but quickbms is saying the file has not been opened yet.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-21T10:40:44+00:00
- Post Title: Quickbms opening files and numerical extensions

1)
in quickbms I use a way to handle strings like 001 as numbers for performance reasons.
exist some ways to bypass this feature like using the String command.

2)
the filenumber field used in the commands is ever a fixed number, it can't be a variable.

in your case I guess you want to handle a splitted archive so the best solution is opening the current FILENUM archive all the times:

```
open FDDE TMP 1
goto OFFSET 1
```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T17:59:09+00:00
- Post Title: Quickbms opening files and numerical extensions

Oh there was another issue I think but forgot about it until now.
I am using 0.5.13

When I use FDDE, it says it opens the other file assuming it is in the same folder as the input.

quickbms says it's trying to open _path_, but it says it couldn't open it.

I use a batch script which dumps the archives in a new folder (in case they don't have folder structure), and it is usually the name of the input file or just "out"

I move the files I want to open using FDDE into the "out" folder and then they are opened correctly.

...

I also have some files that use separate file table to index into another archive, except it uses the names

"{something}_header"
"{something}_data"

Where "something" can be anything (map, obj, tex, blah)
How can I deal with this?

I want to get the "base" name which is everything before the underscore and then just manually attach it like

```
basename = {something}
# now build the outName and open it
string outName = basename
string outName = basename + "_data"
open FDSE outName

```
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-21T22:34:05+00:00
- Post Title: Quickbms opening files and numerical extensions

do you have an image of the output of quickbms for the first case?
quickbms should show all the full paths tried for loading the file.

while for that basename you can use the "<" operator:

```
string NAME <= "_"
string NAME += "data"
print "%NAME%"
```
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T22:45:51+00:00
- Post Title: Quickbms opening files and numerical extensions

Weird, I can't seem to reproduce it. Hmm maybe when I run into the problem again lol

Is there a way for me to "try" to open a file, but if it doesn't exist just ignore it and continue?

```
                0 otherwise 1 (exists). by default QuickBMS terminates
                with an error if the file doesn't exist.

```


Alternatively, how can I avoid opening the same file multiple times?

Since I don't actually know how many split parts there might be (one part, two part, ...), I'm just opening the file as I go

```
if FILENUM == 0
   # open file 000 and read
elif FILENUM == 1
   # open file 001 and read
elif ...


```


Fortunately there is always at most 3 parts (002) so I can do something like what I am doing above.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-21T23:18:23+00:00
- Post Title: Quickbms opening files and numerical extensions

```
if IS_ALIVE != 0
    do your stuff
endif
```
don't worry about opening the files, open them when requested so without doing the "open them all at the same time" as you want to do.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-24T20:53:50+00:00
- Post Title: Quickbms opening files and numerical extensions

Oh, it takes a variable. lol I was passing in a constant number.

Thanks it works great now.
