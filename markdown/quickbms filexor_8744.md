## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-10T21:25:55+00:00
- Post Title: quickbms filexor

When I write something like

```
filexor KEY
get LEN long
```


The value I just read is correct.

However if I did something like

```
filexor key
get LEN long

```


It's not right. What's wrong with the second one?

I need to constantly change the key by doing some math operations, like multiply by 3 and add 7 after each read operation, so I thought of just storing the key as a number rather than a string.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-11T23:20:01+00:00
- Post Title: quickbms filexor

filexor supports bytes, you can't pass a 32bit number.
anyway it looks a very interesting (and easy to realize) idea so I may implement it in the next version of quickbms
