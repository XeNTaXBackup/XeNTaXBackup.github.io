## Post #1
- Username: HenryEx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 07, 2013 8:30 am
- Post datetime: 2014-08-12T16:03:40+00:00
- Post Title: Byte substitution cipher with QuickBMS?

So, Monster Hunter uses not only a xor-based encryption on their data and save files, but also a simple substitution cipher with a 256 bytes large table, where a byte with value %X is replaced with the value at table[%X].
To get at the 32bit xor key at the end of the file, you have to first put it through the substitution table TWICE.

I'm trying to do that, but i'm not sure how to best do it in QuickBMS. I thought the Encryption command with "charset" sounded like what i need, but it's not working. This is what i'm trying:

```
  goto -4 0
  get KEY long 0
  print "Stored key: %KEY%."

  Encryption charset MEMORY_FILE10  # MEMORY_FILE10 is the decryption table
  log MEMORY_FILE2 0x16A0FC 4 0  # 0x16A0FC is a position at the last 4 bytes, where the key is
  goto 0 MEMORY_FILE2
  get KEY long MEMORY_FILE2
  print "First ciphered key: %KEY%."

  log MEMORY_FILE2 0 4 MEMORY_FILE2
  goto 0 MEMORY_FILE2
  get KEY long MEMORY_FILE2
  print "Deciphered key: %KEY%."
  Encryption "" ""  # deactivate decryption

  log "key.bin" 0 4 MEMORY_FILE2

```


What happens is that the first Log instruction results in MEMORY_FILE2 containing 0x00000000, which then transforms into 0x4D4D4D4D. The failure of the first one os obvious, but that second one doesn't even seem right, because the first byte in the table (at position 00) is 0x56! So a byte with value 0x00 should be replaced with 0x56.

What's the problem here? Or is the "charset" encryption doing something other than what i thought it does?

/edit: Not sure if i can post the cipher table here. If it's okay, i'll attach it.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-08-13T07:41:29+00:00
- Post Title: Byte substitution cipher with QuickBMS?

Now there is an [official forum](http://zenhax.com/viewforum.php?f=13) for any help and suggestion/feedback regarding QuickBMS.
## Post #3
- Username: HenryEx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 07, 2013 8:30 am
- Post datetime: 2014-08-13T18:56:49+00:00
- Post Title: Byte substitution cipher with QuickBMS?

That's cool! I more or less solved this problem, but i'm going to bring up another one i have over there.
