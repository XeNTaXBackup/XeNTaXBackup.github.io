## Post #1
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2010-08-28T15:01:49+00:00
- Post Title: Call Perl function (help with code)

Hi there! 

Well, I have a perl script downloaded from here: [http://pastebin.com/b3EHJJ2g](http://pastebin.com/b3EHJJ2g) or this link [http://www.mediafire.com/?a451ee6h6egzqo8](http://www.mediafire.com/?a451ee6h6egzqo8) that uncompress some type of LZE compressed files (like the LZE file that I have). This script has two functions, unlze(); and compress_lze(); I haven't got any perl knowledges, but I need to decompress that LZE file no matter what.  

So, here are my questions: 

1º- How can I call a function in perl? I suppose that is writing "unlze();", no? 
2º- In this script, how/where can I indicate the path of compressed file? 
3º- Could someone write those functions in C please?

Greetings.
## Post #2
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-08-28T18:53:20+00:00
- Post Title: Call Perl function (help with code)

It seems that the two functions expect a reference to a bytestring as input. So you could write a perl script like this (I added some comments (#) to make things a little more clearer...)

```

open FILE, $ARGV[0] or die "Couldn't open file: $!";  #opens the file you want to decompress
binmode FILE;                                         #use binary mode
read (FILE, $string, -s $ARGV[0]);                    #read the whole file into the string variable $string
$decompressed=unlze(\$string);   #if you want compression: $compressed=compress_lze(\$string);
#.....do things with $decompressed here....
close FILE;                            

#copy here the functions from your link
sub unlze {
 #....
}

sub compress_lze {
  #....
}
```


Name this script for example lze.pl and start it from the command line prompt with e.g.
lze.pl c:\mydata\mycompressedfile
Of course, you got to have a perl interpreter installed...

To all Perl experts: I know I should have used "use warnings" and strict and File:Slurp and stuff, but I wanted to keep it as simple /understandable as possible and without extra modules...
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-08-29T13:34:17+00:00
- Post Title: Call Perl function (help with code)

Just for curiosity i wrote

```
binmode DEC;
print DEC $decompressed;
close DEC;  

```


where you put #.....do things with $decompressed here....

but it doesn't do anything, even if it seems to work becuase it doesn't give errors...suggestions?
## Post #4
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-08-29T16:38:18+00:00
- Post Title: Call Perl function (help with code)

> Reply from Vash
>
> Just for curiosity i wrote
Code: Select allopen DEC, $ARGV[1] or die "Couldn't open file: $!";
binmode DEC;
print DEC $decompressed;
close DEC;  


where you put #.....do things with $decompressed here....Looks good...I think you just forgot to open the output file explicitly for writing (strange that you didn't receive an error message from the 'print' command). Just try instead:

```
binmode DEC;
print DEC $decompressed;
close DEC;  

```

Now the script can be called like this:
lze.pl compressedInputFile decompressedOutputFile

This should work... 
I just tried compressing a 35KB text file. The compressed output file had 17 KB. Decompressing the output file again delivered the original file
## Post #5
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2010-08-29T20:45:09+00:00
- Post Title: Call Perl function (help with code)

Thanks for all!!! Now all work!!

Liandril, Vash, thanks ^^.
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-08-30T13:40:36+00:00
- Post Title: Call Perl function (help with code)

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-08-30T20:54:11+00:00
- Post Title: Call Perl function (help with code)

> Reply from Vash
>
> I compiled a compressor and a decompressor if someone need them:
Good idea, thanks Vash  And hey: only 450KB for each file... Perl2Exe seems to produce very small executables (I tried Activstates Perl Dev Kit.. the resulting binaries were at least 1.3 MB). Unfortunately, Perl2Exe won't compile the Perl script I'm [currently working](http://forum.xentax.com/viewtopic.php?f=17&t=4942) on... but that's a different topic.
## Post #8
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-08-30T22:15:34+00:00
- Post Title: Call Perl function (help with code)

the pro version make an even little executbale, or so they say...
## Post #9
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-08-31T13:00:40+00:00
- Post Title: Call Perl function (help with code)

> Reply from Vash
>
> the pro version make an even little executbale, or so they say...
So that means: "Pay more - get less"
