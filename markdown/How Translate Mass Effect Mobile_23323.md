## Post #1
- Username: otaviotr8765
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Nov 30, 2020 12:59 pm
- Post datetime: 2021-01-17T22:30:43+00:00
- Post Title: How Translate Mass Effect Mobile?

The translation of the game is in this "masseffect.bin" file but I cannot export or import the translation file.

File Text:[https://www.mediafire.com/file/io4odva7 ... t.bin/file](https://www.mediafire.com/file/io4odva7oc3ezh8/masseffect.bin/file)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-18T09:15:40+00:00
- Post Title: How Translate Mass Effect Mobile?

First of all, don't make spam topics. You have created 3 topics in 2 days
regarding some mobile games. Just focus on one game at a time and try to finish what you have started.

Secondly, text block is on the end of your bin file inside "CDAT" chunk. All strings are null terminated.
That should be easy to export/import, but if you don't know how to deal
with that, just hire a programmer who will be able to help you.
If there is no existing tool already, custom tool needs to be created.
## Post #3
- Username: otaviotr8765
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Nov 30, 2020 12:59 pm
- Post datetime: 2021-01-18T16:53:42+00:00
- Post Title: How Translate Mass Effect Mobile?

> Reply from ikskoks ↑Mon Jan 18, 2021 5:15 pm at Mon Jan 18, 2021 5:15 pm
>
> 
First of all, don't make spam topics. You have created 3 topics in 2 days
regarding some mobile games. Just focus on one game at a time and try to finish what you have started.

Secondly, text block is on the end of your bin file inside "CDAT" chunk. All strings are null terminated.
That should be easy to export/import, but if you don't know how to deal
with that, just hire a programmer who will be able to help you.
If there is no existing tool already, custom tool needs to be created.

Sorry this was not my intention to spam.

How do I export and import the text file?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-18T17:03:24+00:00
- Post Title: How Translate Mass Effect Mobile?

As I said, there is a text block on the end with format

```
1 byte - null terminator
```


and someone with programming knowledge can create some custom tool to deal with that.

As far as I know there are no tools for this bin file.
Maybe you should start with games where tools already exist like Mass Effect 2 for example [https://github.com/jgoclawski/me2-tlk-tool](https://github.com/jgoclawski/me2-tlk-tool)
## Post #5
- Username: otaviotr8765
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Nov 30, 2020 12:59 pm
- Post datetime: 2021-01-18T21:57:30+00:00
- Post Title: How Translate Mass Effect Mobile?

> Reply from ikskoks ↑Tue Jan 19, 2021 1:03 am at Tue Jan 19, 2021 1:03 am
>
> 
As I said, there is a text block on the end with format
Code: Select allx bytes - text string
1 byte - null terminator

and someone with programming knowledge can create some custom tool to deal with that.

As far as I know there are no tools for this bin file.
Maybe you should start with games where tools already exist like Mass Effect 2 for example https://github.com/jgoclawski/me2-tlk-tool

Ok thanks
