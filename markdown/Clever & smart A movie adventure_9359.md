## Post #1
- Username: strizek
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Apr 07, 2012 2:34 am
- Post datetime: 2012-07-27T11:54:04+00:00
- Post Title: Clever & smart: A movie adventure

This adventure game looks very amazing... There are language files and German texts. Texts it seems to be in NKR fïles, but how to decrypt or edit. Please LOOK and HELP.

Thank you

Fïlip
[Textos.zip](https://xentaxbackup.github.io/file/5605_Textos.zip)
## Post #2
- Username: strizek
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Apr 07, 2012 2:34 am
- Post datetime: 2012-07-27T12:56:10+00:00
- Post Title: Clever & smart: A movie adventure

I found which characters in game are in HEX. But, when i translate whole files manually, then it will be for a long long time... Is there some utility, which convert tëxt files in right way ? HEX table on link bellow.

[http://s7.directupload.net/file/d/2964/sz4ymf99_jpg.htm](http://s7.directupload.net/file/d/2964/sz4ymf99_jpg.htm)
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-07-27T14:56:45+00:00
- Post Title: Clever & smart: A movie adventure

you got so close!

if you compared the values you wrote out against the ascii code for each letter ('A' == 0x41) then you might have caught on to the fact the values follow a simple pattern:

'A' (ascii 41) xor E2 == A3
'B' (ascii 42) xor E1 == A3

here is a bms script which can convert the nkr files to txt (to convert back, run the script on the file again, and change the extensions from .nkr.txt.txt to .nkr again)

```
get size asize
get fn filename
string fn += ".txt"
log fn 0 size
```


download quickbms here: [http://aluigi.altervista.org/papers/quickbms.zip](http://aluigi.altervista.org/papers/quickbms.zip)
## Post #4
- Username: strizek
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Apr 07, 2012 2:34 am
- Post datetime: 2012-07-27T16:30:26+00:00
- Post Title: Clever & smart: A movie adventure

Thank you for your quick answer, but it seems not to be so easy.

i make everything you say. Compiling and recompiling goes fine, but when i change something in txt file, then it is not working. I try add or delete characters - not working, i try only change characters (same place and lenght) - not working.

Try yourself - i upload zip file with uninstallator and right language file for it.
[un.zip](https://xentaxbackup.github.io/file/5606_un.zip)
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-07-27T21:55:02+00:00
- Post Title: Clever & smart: A movie adventure

Everything is fine.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-07-27T23:10:21+00:00
- Post Title: Clever & smart: A movie adventure

there looks to be a header at position 32 in the nkr file which consists of the xor key (0xA3) followed by the extension (".txt")

i updated my script, which is now split into an extractor and repacker: (see comments)

```
# WRS (xentax.com)

# read 5 byte info at position 32
goto 32
get nkr_xor byte
filexor nkr_xor
getdstring nkr_ext 4
get fn filename

# log initial data
log MEMORY_FILE 0 32

# log remaining data
get size asize
math size -= 37
append # enables for MEMORY_FILE
log MEMORY_FILE 37 size

get size asize MEMORY_FILE
string fn += nkr_ext
append # disables for logging
filexor 0 # remove xor key
log fn 0 size MEMORY_FILE
```


```
# WRS (xentax.com)

# save initial data
log MEMORY_FILE 0 32

# write 5 byte info
putvarchr MEMORY_FILE 32 0 # once xord this becomes the key
putvarchr MEMORY_FILE 33 '.'
putvarchr MEMORY_FILE 34 't'
putvarchr MEMORY_FILE 35 'x'
putvarchr MEMORY_FILE 36 't'

# save remaining data
get size asize
math size -= 37
append
log MEMORY_FILE 37 size
append

get fn basename
string fn += "_new.nkr"
get size asize MEMORY_FILE
filexor 0xA3
log fn 0 size MEMORY_FILE

```


Hope this helps you.
