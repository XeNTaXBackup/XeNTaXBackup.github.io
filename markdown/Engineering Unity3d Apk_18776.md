## Post #1
- Username: aftech
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 06, 2018 7:44 pm
- Post datetime: 2018-09-06T11:50:15+00:00
- Post Title: Engineering Unity3d Apk

hello guys,
I want to ask you if there is some know how we can do "engineering unity3d apk" ?

Help us Please 

Thank you
## Post #2
- Username: ShinyAfro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 08, 2018 1:48 am
- Post datetime: 2018-10-07T18:09:24+00:00
- Post Title: Engineering Unity3d Apk

> Reply from aftech
>
> hello guys,
I want to ask you if there is some know how we can do "engineering unity3d apk" ?

Help us Please 

Thank you

Honestly you need to re-word yourself specifically, Its hard to grasp what you are asking.

judging by the apk you mean a mobile, online unityweb file.
If you're asking how to read a unityweb file, i can help. First you need QuickBMS [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)
And a simple script 

```

idstring "UnityWeb"
goto 0xD1
get OFFSET long
get SIZE long
get NAME_SZ long
getdstring NAME NAME_SZ
log NAME OFFSET SIZE
```


Also a hex editor.

See the second line?

```
goto 0xD1
```

This may or may not be valid, depending on the game. But to grab the value we need to open the file in a hex editor and find in the plaintext section "data.unity" 
Now pardon me people who actually know what they are doing, because honestly i don't so pardon me if i am wrong on the technical bits, but from what i understand in bitcode is that this is a header of sorts, and each file is proceeded by some identifiers to say where the data is in the file. a long seems to be 4 bytes in this case, the offset (where it starts in the file), the size (how long the data is) and the name_sz is the size of the name or some shit (not really sure but whatever, not really relevant)
each two hex characters is a representation of a byte. 4x3 = 12 (qwik maf) so we go back 12 spaces, and find the first hex code and find it's position in the file.

We replace goto 0xD1 with whatever value you found. 
so say you found F4, the line would be goto 0xF4" (0x just shows the pc we're talking in hex)

Anyway here's a drawing i did in paint to illustrate what's going on with the artistic grace of a 8 year old


Save the script, open QuickBMS, select the script and target the unityweb file you want to extract the unity3d from, then let it extract it.

Now just open it in Unity Studio [viewtopic.php?t=11807&f=10](http://forum.xentax.com/viewtopic.php?t=11807&f=10) and you're good.
