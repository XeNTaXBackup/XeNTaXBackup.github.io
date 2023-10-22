## Post #1
- Username: WARP ItSelf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 3:14 pm
- Post datetime: 2009-11-15T05:35:42+00:00
- Post Title: Plugin encoding

I'm currently trying to call rpm plugins to view file contents, but I'm expecting a problem. I see no way to open a file with non-English name. I converted filename to ANSI, since Delphi uses ANSI (I also tried OEM, but with no luck either). The problem is with the GE plugin. It just crashes with Java exceptions, and the filename in it's log is bad. Is it a plugin error (GE) or I miss something?
## Post #2
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-11-24T23:53:17+00:00
- Post Title: Plugin encoding

Could you please provide an example?
## Post #3
- Username: WARP ItSelf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 3:14 pm
- Post datetime: 2009-11-25T08:18:17+00:00
- Post Title: Plugin encoding

It's hard to provide an example, since I call multiex plugins externally. The easiest way as I see it.

1. Create a console application.
2. Load GEPlugins.mxp.
3. Call mpIsFileAnArchive on any file, which name is not English (in my case it's Russian), you may use "русское имя" as a reference. Converting this name OEM->ANSI and ANSI->OEM doesn't help. (But it shold work with ANSI as I understand).
4. You'll see a crash in console.

You may also try to open a file named "C:\русское имя.zip" (rename any real zip file) from MultiEx as "18 wheels of steel : Across America [GE] (*.zip)". There will be no crash, but an RPM error. The same file with "C:\english name.zip" will work. If you choose "_ZIP_Archives_" the russian name will work also. 

P.S. An a strange glich found in MultiEx file manager. It shows zip files twice in "C:\" (on a files panel).

P.P.S. Screenshots? Piece o'code?
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-11-26T04:00:38+00:00
- Post Title: Plugin encoding

> Reply from WARP ItSelf
>
> Converting this name OEM->ANSI and ANSI->OEM doesn't help. (But it shold work with ANSI as I understand).First, it would be Unicode, not ANSI or OEM. Make sure the filename arguments are in UTF-8. I don't use Delphi much, so I'm not sure how. I checked and I'm pretty sure that once you do that, it will work. If you are still having you can post your code and we'll look at it.

By the way, sorry for the rather late response
## Post #5
- Username: WARP ItSelf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 3:14 pm
- Post datetime: 2009-11-26T08:15:24+00:00
- Post Title: Plugin encoding

Hmm, UTF-8 is ok, and I don't use Delphi either. So GEPlugins.mxp uses UTF-8 in string arguments while all other plugins use ANSI? It's strange anyway. MultiEx will not work correcly this way (as I reported earlier). Unicode is great, but MultiEx does'nt look like a unicode-aware app, or am I wrong? Should I use UTF-8 to call all mpx plugins?
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-26T13:44:49+00:00
- Post Title: Plugin encoding

You should contact Rahly for any issues related to his pluginmanager (RPM) (the interface between MultiEx and the RPM-plugins).
## Post #7
- Username: WARP ItSelf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 3:14 pm
- Post datetime: 2009-11-27T11:15:40+00:00
- Post Title: Plugin encoding

I droped Rahly a letter, but anyway it seems to be a problem. As I mentioned earlier, GEPlugins.mxp doesn't work in conjunction with MexCom with non-English filenames. It uses UTF-8 for filenames, but I think MexCom will never give it a UTF-8 encdoded name.
## Post #8
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-11-28T18:51:35+00:00
- Post Title: Plugin encoding

> Reply from WARP ItSelf
>
> UTF-8 in string arguments while all other plugins use ANSI?Most of ANSI can be used in arguments that accept UTF-8. So it doesn't really matter that much. UTF-8 was meant to be backwards compatible with ANSI.

> Reply from WARP ItSelf
>
> It's strange anyway. MultiEx will not work correcly this way (as I reported earlier). Unicode is great, but MultiEx does'nt look like a unicode-aware app, or am I wrong? Should I use UTF-8 to call all mpx plugins?I would say that you probably aren't able to call all the other plugins with UTF-8. I only know that it's possible with GEPlugins though. And MexCom doesn't appear to have any Unicode support.

> Reply from WARP ItSelf
>
> As I mentioned earlier, GEPlugins.mxp doesn't work in conjunction with MexCom with non-English filenames. It uses UTF-8 for filenames, but I think MexCom will never give it a UTF-8 encdoded name.Correct.
## Post #9
- Username: WARP ItSelf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 3:14 pm
- Post datetime: 2009-11-29T14:59:46+00:00
- Post Title: Plugin encoding

UTF-8 is compatible with ANSI in first 128 chars only, but there are no national characters. So, string in Russian (German, Hebrew etc.) is not the same in UTF-8 and ANSI. It's not bad that GEPlugins.mxp uses UTF-8, but it's absolutely against the RPM plugins interface since MexCom uses ANSI and filenames are not English only. 

P.S. It's not a problem for me to make an exception for GEPlugins.mxp and call it using unicode strings (UTF-8). But it's strange, since it is a MexCom plugin and MexCom can't use it correcly.
## Post #10
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-12-04T00:13:43+00:00
- Post Title: Plugin encoding

> Reply from WARP ItSelf
>
> UTF-8 is compatible with ANSI in first 128 chars only, but there are no national characters. So, string in Russian (German, Hebrew etc.) is not the same in UTF-8 and ANSI.That's correct, but you're overlooking the fact that Russian and Hebrew cannot be expressed with ANSI. Plus, it would have been more work for me to convert it from ANSI to UTF-8. So I decided that having it accept UTF-8 was a more than fair trade-off.

> Reply from WARP ItSelf
>
> It's not bad that GEPlugins.mxp uses UTF-8, but it's absolutely against the RPM plugins interface since MexCom uses ANSI and filenames are not English only.I do realize this could be a problem (for ANSI chars 128-255), but no one has complained about it yet so I'm not worried. Although after a quick test it appears that for some reason it can even open file names that have chars 128-255.
## Post #11
- Username: WARP ItSelf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 3:14 pm
- Post datetime: 2009-12-04T06:03:47+00:00
- Post Title: Plugin encoding

MexCom does support Russian names (in ANSI encoding). And about "ANSI does not support Russian". Pure ANSI (1252) probably not. But in Windows terms ANSI is 1251 (CP_ACP) and OEM is 866 (CP_OEMCP) for Russian. The term "ANSI" is a bit overused currently. And Delphi is "Windows ANSI", not a pure one (and so MexCom). It just uses "ANSI names for file apis" (SetFileApisToANSI), while some apps use OEM apis (SetFileApisToOEM) (and some use UCS-2/UTF-16 unicode ones, of course). 

P.S. As I said, it will be enough for me, that GEPlugins.mxp will support real UTF-8. But 128-255 names in this plugin will not work under MexCom. Treat this part as a bugreport from MexCom user ("no one complained").
## Post #12
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-12-14T14:01:38+00:00
- Post Title: Plugin encoding

Oh, I'm sorry. Now I see what you're saying. I'll see if I can find a way to make it work correctly (though I'm not sure how soon).
