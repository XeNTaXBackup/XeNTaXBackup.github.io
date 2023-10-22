## Post #1
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-12-03T23:00:55+00:00
- Post Title: Elune Saga (txt-files)

There mime-encoding+GZip-compressed

Use Total Commander
1. Open txt-file and write:

```
Content-Type: application/octet-stream; name="script.txt.txt"
Content-Transfer-Encoding: base64
Content-Disposition: attachment; filename="script.txt.txt"

<original file>
```

2. In Total Commander: Files→Decode MIME/UUE/XXE/BinHex
3. Rename in *.gz and unpack this file =)
You will get normal txt-file

Examples:
[http://rghost.ru/59411503](http://rghost.ru/59411503) / [http://sendfile.su/1056463](http://sendfile.su/1056463)
