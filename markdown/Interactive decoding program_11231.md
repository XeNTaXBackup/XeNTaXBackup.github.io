## Post #1
- Username: anahuj
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 21, 2011 11:48 pm
- Post datetime: 2014-02-20T23:40:28+00:00
- Post Title: Interactive decoding program?

I would like to have an interactive program for decoding files
and for figuring out their structure. Anyone?

I wrote a simple program in GNU/Linux but failed to implement
the structure system. The program starts with text "<filesize>
unknown bytes", and then user may test and convert the
unknown bytes to various formats: hex lines, ints, floats, strings.
User may give name to these objects.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-03-12T18:40:15+00:00
- Post Title: Interactive decoding program?

How would that differ from opening it in a decent hex editor that automatically converts the bytes in front of you into a bunch of different data types?

I don't remember how things are like when I first started looking at unknown archive or model formats but at this point, it's not important to me whether something is an int or a float because hex editors tell me that already.

I need a quick way to detect patterns and narrow down the structure of the format and then figure out how different parts are related to each other.
## Post #3
- Username: anahuj
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 21, 2011 11:48 pm
- Post datetime: 2014-03-13T12:08:23+00:00
- Post Title: Interactive decoding program?

My major work is an independent decoding of Oblivion and Fallout 3
ESM/ESP file format. (I'm not involved in TES4Edit etc projects.)

If I start from "<N> unknown bytes", I would find out first the
record block format: <record id> <record data size>, sort of.

I should be able to define the record format as know at this
point, and define how to reach the next record.

The decoder program would now be able to list all records
by their ID, size, number of unknown bytes inside the record.

Now I should be able to define subdecodings for every
record, per ID.

I have written an interactive browser but the format is
defined by writing the format manually in text format.

There are more in this than I have now explaned, of course.
For example, I should now have a C/C++ library for loading,
browsing, modifying, and saving the game data.
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-05-14T21:54:05+00:00
- Post Title: Interactive decoding program?

The hex editor I use on Windows, i.Hex, has a feature where you can define structures and it'll parse it out for you. It tends to crash if you make a mistake and load a large number of bytes, but in any other case it's a cinch if you don't want to spend time writing a parser. It doesn't show values in float or double when editing, but it does show char, short, and int, signed and unsigned, big- and little-endian. You can have it show float/double on the side if you define it in a struct. It doesn't have any library loading functions, though (what do you expect, it's a hex editor).
## Post #5
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-05-19T00:35:33+00:00
- Post Title: Interactive decoding program?

[http://www.yole.ru/projects/structorian/](http://www.yole.ru/projects/structorian/)
[http://www.sweetscape.com/010editor/](http://www.sweetscape.com/010editor/)


010 is  not free tho and the structorian is quite outdated - he never finished the newer version, only source remains. But it is a great structure based tool to analyze unknown formats.
