## Post #1
- Username: Oscar92player
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Feb 05, 2016 2:13 am
- Post datetime: 2016-04-25T21:17:39+00:00
- Post Title: FF9 Steam MPC file

Hello everyone!

With help of the Steam community, I've been able to extract the TTF font from FF9 Steam release, it's encrypted in a MPC file. The Unity Studio extracted it with a TXT format, but the real format is MPC. Inside it's a binary code.

The MPC file:
[https://mega.nz/#!IJEhCDBY!xpuilf1ZgVt_ ... qadHMOSk7k](https://mega.nz/#!IJEhCDBY!xpuilf1ZgVt_gbuIREGY4SEvn7-4NsuA4qadHMOSk7k)

A user from the Steam modding forums has given me a code, but I don't know how to use it. He has told me that it can be rewritten to QuickBMS.

```
{
long num1 = 1024;
long num2 = (long) bytes.Length;
long length = num2 - num1;
byte[] numArray = new byte[length];
long num3 = 0;
for (int index = 0; (long) index < length; ++index)
{
if (num3 < num1)
{
numArray[index] = bytes[num2 - num1 + num3];
++num3;
}
else if ((long) index < num2)
numArray[index] = bytes[index];
}
return numArray;
}
```


I hope someone can help me with this. Thanks in advance!
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-25T23:56:30+00:00
- Post Title: FF9 Steam MPC file

all that code does is shift the last 1024 bytes to the top of the file
