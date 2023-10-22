## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-19T18:50:35+00:00
- Post Title: experimental QuickBMS encryption scanner

I have just created a bat+bms solution like the comtype_scan one but this time for the encryption algirithms.
probably it's not much useful but who knows.

you need the new version of quickbms to use it:
[http://quickbms.aluigi.org](http://quickbms.aluigi.org)
[http://aluigi.org/papers/bms/encryption_scan.bat](http://aluigi.org/papers/bms/encryption_scan.bat)
[http://aluigi.org/papers/bms/encryption_scan.bms](http://aluigi.org/papers/bms/encryption_scan.bms)

examples:

```

encryption_scan.bat c:\encryption_scan.bms c:\dump.dat c:\output_folder "\x31\x32\x33\x34\x35\x36\x37\x38"

encryption_scan.bat c:\encryption_scan.bms c:\dump.dat c:\output_folder "this_is_my_key12" "this_is_my_ivecx"
```

it can be useful in some very rare cases where we have the key but don't know the algorithm or something similar... after all it costed me nothing to make this bat+bms so it's just to spend some time :)
