## Post #1
- Username: NeSo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 04, 2017 4:08 pm
- Post datetime: 2017-08-04T08:16:17+00:00
- Post Title: Krater COllector Edition (PC)

Hello everyone,

I went here because I really need help...

Following this topic : [https://forum.xentax.com/viewtopic.php?f=10&t=9084](https://forum.xentax.com/viewtopic.php?f=10&t=9084) I try to decompile files in order to translate in french. But, the tool given in this topic ([https://github.com/hhrhhr/Lua-utils-for-Krater/tags](https://github.com/hhrhhr/Lua-utils-for-Krater/tags)) isn't working because game use LuaJIT now and decompiling return an error (show page 2, post from lostprophet with screenshot).

I try to modify tools or script but without success...

If any charitable soul is here and want to help me...  

EDIT : I think error comes from this file, especially when we add "c" at the end of file : 

```
get filesCount long

for i = 0 < filesCount
  get hash1l long  // low bits
  get hash1h long  // high bits, 64-bit hash of unitName
  get hash2l long  // low bits
  get hash2h long  // high bits, 64-bit hash of resourceName
  get lang long    // language flag, 0-english, 1, 2, 4, 8...
  get nam2 long
  get nam1 long
  get lnk2 long
  get lnk1 long

  if hash1h == 0xA14E8DFA
    if hash1l == 0x2CD117E2
      string name p= "%08x%08x" nam1 nam2
      set dirXX string name
      string dirXX -= -2
//      string path p= "data %s %s" dirXX name
      set path string data\
      string path += dirXX
      string path += \
      string path += name

      open FDSE path 1
      get size ASIZE 1

      goto 21 1
      get name string 1
      string name += "c"    // .lua + c = .luac
      set offset 4
      math size -= 4

      log name offset size 1
    endif
  endif
next i
```


Am I right?
## Post #2
- Username: NeSo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 04, 2017 4:08 pm
- Post datetime: 2017-08-04T11:27:37+00:00
- Post Title: Krater COllector Edition (PC)

Hello me,

The first tool extract strings to text from game. Is any way to re-import them after modification without other steps?
