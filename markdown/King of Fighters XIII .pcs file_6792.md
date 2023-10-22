## Post #1
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2011-06-16T17:19:30+00:00
- Post Title: King of Fighters XIII .pcs file

After getting my hands on KOF XIII, I was wondering if it was possible if the .pcs file (character file) was able to be looked into and possibly cracked?

The file is right [here](http://www.mediafire.com/?mjnaz506m59as6q). Included is the .lua file, which I assume is also part of the character file.

[Palettes are here, incase they're needed](http://www.mediafire.com/?817fvugczmq74iz)

Thanks
## Post #2
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-08-13T11:47:07+00:00
- Post Title: King of Fighters XIII .pcs file

> Reply from Nega
>
> After getting my hands on KOF XIII, I was wondering if it was possible if the .pcs file (character file) was able to be looked into and possibly cracked?

The file is right here. Included is the .lua file, which I assume is also part of the character file.

Palettes are here, incase they're needed

Thanks
i start modifiing lua decompiler for new file types (KoF and M2 i believe) so if i succes it should help understand what exactly is pcs file
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-16T16:34:14+00:00
- Post Title: King of Fighters XIII .pcs file

just a compressed block format

incomplete script because the data needs headers or something

```

for
  getdstring BLOCKNAME 8
  get BLOCKSIZE longlong
  savepos BLOCKPOS
  if BLOCKNAME == "TEXLIST"
    callfunction getTexList
  elif BLOCKNAME == "IMGLIST"
    callfunction getImgList
  else
    print "unhandled block %BLOCKNAME%"
    cleanexit
  endif

  savepos POS
  if POS == SIZE
    cleanexit
  endif

next

startfunction getTexList

  math BLOCKPOS += BLOCKSIZE

  for i = 1

    idstring "TEXTURE\0"
    get TEXSIZE longlong

    getdstring datakind 4
    idstring "ZIP\0"
    get un1 long
    get un2 long # 8
    get chunks long
    get un3 long # 4

    log MEMORY_FILE 0 0
    append

    for c = 0 < chunks
      get size long
      savepos pos
      clog MEMORY_FILE pos size 0x10000
      math pos += size
      goto pos
    next c

    append
    get size asize MEMORY_FILE
    string txt p= "texture_%s_%02i.dat" datakind i
    log txt 0 size MEMORY_FILE

    savepos POS
    if POS == BLOCKPOS
      break
    endif

  next i

endfunction

startfunction getImgList
  print "unhandled"
  cleanexit
endfunction

```
## Post #4
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2011-12-05T04:06:22+00:00
- Post Title: King of Fighters XIII .pcs file

Any advancements on this at all?
## Post #5
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-12-11T04:47:34+00:00
- Post Title: King of Fighters XIII .pcs file

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2011-12-11T12:41:37+00:00
- Post Title: King of Fighters XIII .pcs file

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-12-11T21:28:17+00:00
- Post Title: King of Fighters XIII .pcs file

> Reply from JohnGrimm
>
> 
Those texture files are really small and probably insignificant, I'd be willing to bet there's more files in the .pcs archives. Like WRS said the script is incomplete. Also, I'm still rather curious about what's in those texture files, but I can't seem to get them open. Tried messing around with headers in a Hex editor and tried opening them in the DirectX texture viewer, but it didn't work.

i thought they were small files too but they were in tha "fighter" folder which kinda made me automaticly think characters :D...
i checked tha other folders and they got palettes,bg stuff,shaders, and stuff thats on tha menu, like font and portiats.
in tha "fighter" folder theres 'bout 88 lua + pcs files. tha pcs are around 5-14mb

and i think it's just tha headers missing cuz tha "incomplete script".
## Post #8
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2011-12-12T12:53:45+00:00
- Post Title: King of Fighters XIII .pcs file

> Reply from protosk8
>
> i thought they were small files too but they were in tha "fighter" folder which kinda made me automaticly think characters ...
i checked tha other folders and they got palettes,bg stuff,shaders, and stuff thats on tha menu, like font and portiats.
in tha "fighter" folder theres 'bout 88 lua + pcs files. tha pcs are around 5-14mb

and i think it's just tha headers missing cuz tha "incomplete script".
The characters ARE in there, but the script doesn't extract all the files because more work needs to be done with it.
## Post #9
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-12-13T00:37:29+00:00
- Post Title: King of Fighters XIII .pcs file

> Reply from JohnGrimm
>
> protosk8 wrote:i thought they were small files too but they were in tha "fighter" folder which kinda made me automaticly think characters :D...
i checked tha other folders and they got palettes,bg stuff,shaders, and stuff thats on tha menu, like font and portiats.
in tha "fighter" folder theres 'bout 88 lua + pcs files. tha pcs are around 5-14mb

and i think it's just tha headers missing cuz tha "incomplete script".
The characters ARE in there, but the script doesn't extract all the files because more work needs to be done with it.

yea i gotcha kinda figured while i was typing x:
## Post #10
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2011-12-26T06:10:17+00:00
- Post Title: King of Fighters XIII .pcs file

So it doesn't look like anyone is interested in cracking these files, so if anyone can point me in the right direction on how to complete that script I'd like to undertake it myself.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-26T07:07:39+00:00
- Post Title: King of Fighters XIII .pcs file

> how to complete that script

I'm sure you probably already figured as much but you just need to fill out the else block in the main loop as well as the getImgList function.
