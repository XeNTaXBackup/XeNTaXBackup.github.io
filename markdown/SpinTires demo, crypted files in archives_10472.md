## Post #1
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-05-30T12:53:00+00:00
- Post Title: SpinTires demo, "crypted" files in archives

all files in zip archives have a simple "crypt" algorithm:

```
    unsigned int i = 0;
    for (i; i < len; i++) {
        buf[i] += 251 - ((i * 14) & 255);
    }
};

void crypt(unsigned char *buf, unsigned int len) {
    unsigned int i = 0;
    for (i; i < len; i++) {
        buf[i] += ((i * 14) & 255) - 251;
    }
};

```
