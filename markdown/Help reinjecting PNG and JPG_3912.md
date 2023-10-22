## Post #1
- Username: absarhegde
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 21, 2008 2:52 am
- Post datetime: 2009-12-01T01:36:22+00:00
- Post Title: Help reinjecting PNG and JPG

Hello friends..am new to this site..found very helpful and great..
i downloaded two tool filestripper and jaednauber.
used them..both extracted graphics from a particular file...
but in filestripper it doesnot allow me to inject the graphics with different file size..it only except the original size..
and in jaednaub it reinjects with different size file but when i again extract the graphics..i get are all the originals files...
wonder why...
am i doing somthing wrong ?
or is there a program tht can ask me at wat size of image or graphic it shud create...
so tht i can use filestripper..as a choice..

thanks...
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-04T23:07:16+00:00
- Post Title: Help reinjecting PNG and JPG

So you seek a generic injector?
## Post #3
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-12-05T11:53:24+00:00
- Post Title: Help reinjecting PNG and JPG

there's a REASON why filestripper only allows to reinject the same size file...

if you would inject a file that is larger than the original the offsets of the filetable would be fucked up and not correct anymore, which could probably destroy the whole archive
## Post #4
- Username: absarhegde
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 21, 2008 2:52 am
- Post datetime: 2009-12-06T09:55:02+00:00
- Post Title: Help reinjecting PNG and JPG

so is there anyway i can make images or graphics..to have sames as original ..???
## Post #5
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2009-12-08T05:38:47+00:00
- Post Title: Help reinjecting PNG and JPG

If the new files are smaller than the original it should be no problem, just put them back in. If the tools you use don't allow that, simply fill the files up with zeroes until they're the same size as the original.
If they're bigger, well, you could try one or more of the following
- optimizing compression (pngcrush can help you there if it's PNG files that you're dealing with -- similar tools probably exist for GIF and JPG as well)
- reducing quality, wither by dithering or stronger jpeg compression

alternatively you can try to hack/fix the file offset table but this depends on the particular file archive that you're dealing with and is generally considered too hard for a n00b so I won't recommend it, you probably end up destroying your data files   

-Darkstar
## Post #6
- Username: absarhegde
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 21, 2008 2:52 am
- Post datetime: 2009-12-13T13:17:18+00:00
- Post Title: Help reinjecting PNG and JPG

thnx for the help darkstar

after trying hard..it was so simple..
i just chnged the log file and chnge the size to my own required one..
still i have not tested it..but arcive seems to be fine n wrking..
anyways thnx...
## Post #7
- Username: absarhegde
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 21, 2008 2:52 am
- Post datetime: 2009-12-14T17:40:20+00:00
- Post Title: Help reinjecting PNG and JPG

> simply fill the files up with zeroes until they're the same size as the original.

how can i do this ?
## Post #8
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2009-12-16T06:13:35+00:00
- Post Title: Help reinjecting PNG and JPG

Depends. On unix/linux there's a tool called "dd" that can do it. It should also be available on windows.
Any hexeditor should also be able to handle it (like frhed or hexedit32 on windows).
the third option involves some small C program to do it. sth. like this:

```
int main(int argc, char **argv)
{
  long i;
  FILE *f = fopen(argv[1], "a");
  fseek(f, 0, SEEK_END);
  for (i = 0; i < atol(argv[2]); i++)
  {
    fputc(0, f);
  }
  fclose(f);
  return 0;
}

```

Disclaimer: I just hacked this up so I don't guarantee that it'll work. call it like "./a.out <filename> <num-bytes-to-add>". Failure to supply 2 cmd line arguments will probably make it kill your cat or something 

-Darkstar
