## Post #1
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2019-01-31T18:43:35+00:00
- Post Title: Opening resS Files

Is there a way to extract the contents of a resS file? Please respond as soon as possible.
## Post #2
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-31T18:47:19+00:00
- Post Title: Opening resS Files

> Reply from offering7866
>
> Is there a way to extract the contents of a resS file? Please respond as soon as possible.

If it's a Unity games, then use UABE / Unity Asset Bundle Extractor.
## Post #3
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2019-01-31T19:40:09+00:00
- Post Title: Opening resS Files

> Reply from GHFear
>
> offering7866 wrote:Is there a way to extract the contents of a resS file? Please respond as soon as possible.

If it's a Unity games, then use UABE / Unity Asset Bundle Extractor.
I've tried using the 2.2B version of Unity Assets Bundle Extractor, but all I got was this message that said "Unable to read the bundle file! (Invalid file or unknown version?)". What gives?
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2019-02-05T06:34:35+00:00
- Post Title: Opening resS Files

You can't open unity .resS files directly, they are just raw data storage without any headers, all references and offsets and file information is held on the assets files (which you use to extract .resS contents) and if those bundles/assets files will not open by those tools, you got a big problem in achieving this at all and its possible the asset files have been ciphered.
