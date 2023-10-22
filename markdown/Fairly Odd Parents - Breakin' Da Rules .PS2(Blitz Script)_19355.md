## Post #1
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-01-19T17:36:50+00:00
- Post Title: Fairly Odd Parents - Breakin' Da Rules *.PS2(Blitz Script)

Hi there,

Attempting to extract the *.PS2 files from the PS2 version of Fairly Odd Parents - Breakin' Da Rules using the "blitz_games" BMS script yields this error:


Linked below are samples... I'm not very good at tracing scripts, so if someone could help me update the script I'd appreciate it. Thanks!!

~Anexenaumoon

Files: [https://www.dropbox.com/s/6uewfkb9jf0wm ... ms.7z?dl=0](https://www.dropbox.com/s/6uewfkb9jf0wm0x/Streams.7z?dl=0)
(P.S. Haven't used Dropbox much, so if there's sharing errors, let me know!)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-01-20T03:51:08+00:00
- Post Title: Fairly Odd Parents - Breakin' Da Rules *.PS2(Blitz Script)

Open the script and locate to the part

```
        get ZERO long
        get CRC longlong
    endif

```

Change the value 0 to 1 like

```
        get ZERO long
        get CRC longlong
    endif

```
