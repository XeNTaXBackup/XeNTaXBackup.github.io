## Post #1
- Username: SecretAgent2001
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 18, 2016 11:18 am
- Post datetime: 2017-08-05T10:10:23+00:00
- Post Title: QuickBMS Script quick fix?

I've created this script to extract the sounds of the iOS application Angry Birds GO!, but some flaws with it include getting the file names muddled up and some of the sounds not playing. Can someone fix it for me?
Here's the file I'm trying to extract: [https://mega.nz/#!v1xUgIhB!P8FZpIj-wk26 ... XvovkEa5Z4](https://mega.nz/#!v1xUgIhB!P8FZpIj-wk26NhdiMHIfKoRoZ6bpZix9SXvovkEa5Z4)
And here's the script that I'm using:

```
goto 1
idstring "KPX"
get FOLDERS long
get FILES long
get NAMESTABLESIZE long

math FOLDER_BASE = 16
math FILE_BASE = 0x0480
math NAME_BASE = 0x8454

goto FILE_BASE
for i = 0 < FILES
    get OFFSET long
    get FLAG long
    get NULL long
    get SIZE long
    get NULL long
    get NAMEOFF long
    get NULL long
    get ZSIZE long
    savepos TEMP
   
    math NAMEJUMP = NAME_BASE
	math NAMEJUMP += NAMEOFF
	goto NAMEJUMP
	get NAME string
	log NAME OFFSET SIZE
    goto TEMP
next i

```

Help is appreciated.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-06T03:16:32+00:00
- Post Title: QuickBMS Script quick fix?

looks like aluigi has seen these types before here
[http://zenhax.com/viewtopic.php?f=9&t=3533&p=19442](http://zenhax.com/viewtopic.php?f=9&t=3533&p=19442)
you should post there your sample so he can update the script
## Post #3
- Username: SecretAgent2001
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 18, 2016 11:18 am
- Post datetime: 2017-08-06T03:49:33+00:00
- Post Title: QuickBMS Script quick fix?

Posted a thread on zenhax just then. You can view it here: [http://zenhax.com/viewtopic.php?f=9&t=4731](http://zenhax.com/viewtopic.php?f=9&t=4731)
