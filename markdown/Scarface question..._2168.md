## Post #1
- Username: ChuckBronson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 23, 2006 6:20 pm
- Post datetime: 2006-10-23T10:26:52+00:00
- Post Title: Scarface question...

The extracting program from [viewtopic.php?t=2143](http://forum.xentax.com/viewtopic.php?t=2143) works great, but I have a question: it extracts all files with goofy random names (e.g. 6dacdb8b62878b4d.rsd) But inside every file, in the beginning of its header (always at offset 018h), is a path that contains the file's real name and the directory that defines its "type" and use in the game (for example: c:\scarface\art\sound\music\score\story\sm_comb_04_lp.wav)
Is it possible to use this data to give the extracted files their real names, for example in a plugin script? (I guess it should be relatively simple to write a small routine to do that in e.g. C++ but I don't know how to...  If I did, I would have probably written something that would name and "catalogue" all these files based on the directory names in their headers... e.g. "score-story", "tapeplayer", etc...)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-23T11:22:29+00:00
- Post Title: Scarface question...

> 6dacdb8b62878b4d.rsd
The rsd are the oggvorbis, and i thinks its the name of the file need to call, the programmers team of scarface did it
## Post #3
- Username: Nikolai
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Feb 16, 2007 12:23 am
- Post datetime: 2007-02-15T16:57:37+00:00
- Post Title: Scarface question...

Well, I'm not interested in other sounds than Scarface tapeplayer (i.e. game soundtrack). So here is what I did. First of all I extracted all files from sound1.rcf and sound2.rcf. Then I searched for all .rsd files containing text "tapeplayer" among the extacted files (using [Total Commander](http://www.ghisler.com/)). That way I've found 116 songs. I moved them to a separate folder.

Then I wrote little console application on [Free Pascal](http://www.freepascal.org/) called rsd2ogg. It scans .rsd files in current folder for a track name, then removes 2048-byte RSD-header and renames file to a proper name with .ogg extension. Here is the source of "rsd2ogg.pp":
```
var
  f_rec:searchrec;
  f:file of char;
  i_found,i_done,p:word;
  c:char;
  s:string;
  Fin,Fout:file; {untyped}
  NumRead,NumWritten:word;
  Buf:array[1..2048]of byte;
begin
  i_found:=0; {files found}
  i_done:=0;  {successful operations count}
  findfirst('*.rsd',anyfile,f_rec); {in current dir}
  while doserror=0 do begin
    inc(i_found);
    write(f_rec.name);
    assign(f,f_rec.name);
    reset(f);
    s:='';
    for p:=0 to 7 do begin
      seek(f,p);
      read(f,c);
      s:=s+c;
    end;
    for p:=20 to 65 do begin
      seek(f,p);
      read(f,c);
      s:=s+c;
    end;
    if s='RSD6OOGV****c:\scarface\art\sound\music\tapeplayer\tp_' then begin
      inc(i_done);
      s:='';
      p:=66; {position}
      seek(f,p);
      read(f,c);
      repeat
        s:=s+c;
        p:=p+1;
        seek(f,p);
        read(f,c);
      until c='.';
      close(f);
      s:=s+'.ogg';
      Assign(Fin, f_rec.name);
      Assign(Fout,s);
      Reset(Fin,1);
      Rewrite(Fout,1);
      BlockRead(Fin,buf,Sizeof(buf),NumRead);
      repeat
        BlockRead(Fin,buf,Sizeof(buf),NumRead);
        BlockWrite(Fout,Buf,NumRead,NumWritten);
      until (NumRead=0) or (NumWritten<>NumRead);
      close(Fin);
      erase(Fin);
      close(Fout);
      write(' -> ',s);
    end;{if}
    writeln;
    findnext(f_rec);
  end;{while}
  findclose(f_rec);
  writeln;
  write('processed ',i_done,' of ',i_found,' files');
  readln(s);
end.
```

Also I'll try to attach a compiled program to this post.
[rsd2ogg.zip](https://xentaxbackup.github.io/file/1056_rsd2ogg.zip)
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-02-15T22:19:41+00:00
- Post Title: Scarface question...

Thanks! here a another example how to remove the 2048bytes of the "header" (it's a silly example, but works)

Do:

```
tail -c +9 kk_in.raw > kk_out.raw
```
 
The +"9"  it's ner of bytes ti cut and the .raw it's the it output filename

And you can make a .bat with a FOR sentence  

I recommend to use GNU/Linux tools are very good
[tail.rar](https://xentaxbackup.github.io/file/1057_tail.rar)
## Post #5
- Username: Nikolai
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Feb 16, 2007 12:23 am
- Post datetime: 2007-02-25T09:02:01+00:00
- Post Title: Scarface question...

> Reply from Savage
>
> Thanks! here a another example how to remove the 2048bytes of the "header" (it's a silly example, but works)
But my rsd2ogg tool not just removes the header. It also renames the file according to the information in this header, which is more important.
## Post #6
- Username: doeboy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 14, 2007 1:30 am
- Post datetime: 2007-04-05T02:44:33+00:00
- Post Title: Scarface question...

this is a message that was sent to Xentax


doeboy wrote:
Your Pascal program worked like a champ and I am now converting all the .ogg to .mp3 using dbpoweramp. I had looked for a solid week trying to find a method to get that soundtrack out of those files. I really appreciate the posts on the forum as well as your already compiled Pascal prog. I am putting these on a cd for my car so I can jam out to some old skewl shit and bump reallly loud and get people to look hahahahah.... anyways you have a great day!

Can you copy your message to the topic please? Wink

It's great that someone considers my utility useful. I've found this forum by accident (probably as you too) and discovered ScarfaceExplorer. My goal was to extract the soundtrack. I hope rsd2ogg tool will extend functionality of ScarfaceExplorer a little bit
## Post #7
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2007-05-20T07:56:52+00:00
- Post Title: Scarface question...

i want a tools for build ".rf" file or repack ".rf" 
do u help me...
## Post #8
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-05-28T19:52:35+00:00
- Post Title: Scarface question...

Can you tell me how do i extract the score please or tweka your prog?
## Post #9
- Username: Nikolai
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Feb 16, 2007 12:23 am
- Post datetime: 2007-06-24T20:42:25+00:00
- Post Title: Scarface question...

> Reply from kimkalisto
>
> Can you tell me how do i extract the score please or tweka your prog?
That is not hard at all. I only changed 4 lines of code to do it. Other thing - a had to redownload 4 GB of game for this 

Ok, here is instructions for score music (they are much the same as for the tapeplayer):
1. Extract all files from sound1.rcf and sound2.rcf with ScarfaceExplorer.
2. Search for all .rsd files containing text "score" among the extacted files (using Total Commander). I've found 158 files. Move them to a separate folder.
3. Use modified utility rsd2ogg_score. Here is the source code:

```
var
  f_rec:searchrec;
  f:file of char;
  i_found,i_done,p:word;
  c:char;
  s:string;
  Fin,Fout:file; {untyped}
  NumRead,NumWritten:word;
  Buf:array[1..2048]of byte;
begin
  i_found:=0; {files found}
  i_done:=0;  {successful operations count}
  findfirst('*.rsd',anyfile,f_rec); {in current dir}
  while doserror=0 do begin
    inc(i_found);
    write(f_rec.name);
    assign(f,f_rec.name);
    reset(f);
    s:='';
    for p:=0 to 7 do begin
      seek(f,p);
      read(f,c);
      s:=s+c;
    end;
    for p:=20 to 57 do begin
      seek(f,p);
      read(f,c);
      s:=s+c;
    end;
    if s='RSD6OOGV****c:\scarface\art\sound\music\score\' then begin
      inc(i_done);
      s:='';
      p:=58; {position}
      seek(f,p);
      read(f,c);
      repeat
        if c='\' then c:='-';
        s:=s+c;
        p:=p+1;
        seek(f,p);
        read(f,c);
      until c='.';
      close(f);
      s:=s+'.ogg';
      Assign(Fin, f_rec.name);
      Assign(Fout,s);
      Reset(Fin,1);
      Rewrite(Fout,1);
      BlockRead(Fin,buf,Sizeof(buf),NumRead);
      repeat
        BlockRead(Fin,buf,Sizeof(buf),NumRead);
        BlockWrite(Fout,Buf,NumRead,NumWritten);
      until (NumRead=0) or (NumWritten<>NumRead);
      close(Fin);
      erase(Fin);
      close(Fout);
      write(' -> ',s);
    end;{if}
    writeln;
    findnext(f_rec);
  end;{while}
  findclose(f_rec);
  writeln;
  write('processed ',i_done,' of ',i_found,' files');
  readln(s);
end.
```

[rsd2ogg_score.zip](https://xentaxbackup.github.io/file/1234_rsd2ogg_score.zip)
## Post #10
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-06-25T02:00:40+00:00
- Post Title: Scarface question...

I only found 117 for the PC version.
## Post #11
- Username: Nikolai
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Feb 16, 2007 12:23 am
- Post datetime: 2007-06-25T19:47:10+00:00
- Post Title: Scarface question...

That doesn't matter. Did my tool work rigth?
## Post #12
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-06-27T04:03:53+00:00
- Post Title: Scarface question...

Yep worked perfectly thanks.
## Post #13
- Username: solterio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 06, 2007 5:19 am
- Post datetime: 2007-07-05T21:36:40+00:00
- Post Title: Scarface question...

[](http://img514.imageshack.us/my.php?image=image1vn8.gif)
this tool did not work

should i use a parameter?
## Post #14
- Username: myr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 26, 2007 7:09 pm
- Post datetime: 2007-11-26T12:53:05+00:00
- Post Title: Scarface question...

this tool did not work
should i use a parameter?


Not necessary. Only copy rsd2oggscore.exe in the folder, where you have extracted files. Then run rsd2oggscore.exe, wait and it will make .ogg files in the same folder.
Simple
