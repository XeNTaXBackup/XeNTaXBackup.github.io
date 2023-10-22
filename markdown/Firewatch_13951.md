## Post #1
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-10T00:58:49+00:00
- Post Title: Firewatch

Hi i translated this game my language.Open the resources.assets but i can't find language file.

Here opened resources file;
[http://www96.zippyshare.com/v/58c8PgoC/file.html](http://www96.zippyshare.com/v/58c8PgoC/file.html)

Edit:I think language files "resources_****.-2" files.How can we open .-2 files?
## Post #2
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2016-02-10T13:30:20+00:00
- Post Title: Firewatch

Yes, it seems that "resources_****.-2" files contain texts from the game, yet I failed to see any changes when I edited them with hex editor, and used Unity Assets Explorer to import them back.
Edit: Changing the Russian parts seems to be crashing game for me.
## Post #3
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-10T16:45:31+00:00
- Post Title: Firewatch

> Reply from qabRieL
>
> Yes, it seems that "resources_****.-2" files contain texts from the game, yet I failed to see any changes when I edited them with hex editor, and used Unity Assets Explorer to import them back.
Edit: Changing the Russian parts seems to be crashing game for me.
Because there is a charecter limit on the word.And swuforce write open the .-5 files.Maybe write opened .-2 files.
## Post #4
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2016-02-10T17:16:13+00:00
- Post Title: Firewatch

I paid attention to that. Probably happened because of the Russian encoding system which something I dont understand at all. 
What did you mean there exactly?
Başka dosyaları açmak için program mi yazmış, oyleyse nerde gördün?
## Post #5
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-10T17:26:53+00:00
- Post Title: Firewatch

> Reply from qabRieL
>
> I paid attention to that. Probably happened because of the Russian encoding system which something I dont understand at all. 
What did you mean there exactly?
Başka dosyaları açmak için program mi yazmış, oyleyse nerde gördün?
Türk olduğumu nerden anladın bilmiyorum ama iyiki anladın  Punch club da aynı şekilde resources.assets içinde böyle resources_***.-5 diye dil dosyası var.Yani hemen hemen benziyor dosya yapısı birbirine.Fakat bu oyunda .-5 değilde .-2 yani swuforce tools yapabilir diyorum
## Post #6
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2016-02-10T18:08:44+00:00
- Post Title: Firewatch

> Reply from MitiSen
>
> qabRieL wrote:I paid attention to that. Probably happened because of the Russian encoding system which something I dont understand at all. 
What did you mean there exactly?
Başka dosyaları açmak için program mi yazmış, oyleyse nerde gördün? 
Türk olduğumu nerden anladın bilmiyorum ama iyiki anladın  Punch club da aynı şekilde resources.assets içinde böyle resources_***.-5 diye dil dosyası var.Yani hemen hemen benziyor dosya yapısı birbirine.Fakat bu oyunda .-5 değilde .-2 yani swuforce tools yapabilir diyorum
Hatalar bağırıyor    Şaka şaka, adres yolundaki gereksizlerden   
Onda baktığım kadarıyla sadece İngilizce dili var dosyada, Firewatch'ta ise Rusça da var, o yüzden kodun biraz değişmesi gerek.
Ama dediğim gibi hex düzenleyiciyle çevirip attıktan sonra görmüyor oyunda, başka bir yol düşünmek de gerekebilir.
## Post #7
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-10T18:12:12+00:00
- Post Title: Firewatch

Yok yok punc club'tada rusça dil seçeneği var ve o oyundada karakter limiti vardı.Kodlamada nasıl bi değişiklik olur bilmiyorum ama swuforce daha önceden bu tarz birşey yaptığı için pek zorlanacağını düşünmüyorum
## Post #8
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2016-02-10T18:17:01+00:00
- Post Title: Firewatch

> Reply from MitiSen
>
> Yok yok punc club'tada rusça dil seçeneği var ve o oyundada karakter limiti vardı.Kodlamada nasıl bi değişiklik olur bilmiyorum ama swuforce daha önceden bu tarz birşey yaptığı için pek zorlanacağını düşünmüyorum
Bir dosyasına baktım sadece İngilizce vardı, ayrı ayrı dosyalardadır belki. Firewatch'ta ise ikisi tek dosyada. Ya da -2 dosyaları Rusça dili için, yanındaki yazılar da çevirmenler için bırakılan cümleler. Direk motordan veyahut başka dosyadan okuyor olabilir.
## Post #9
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-10T18:22:42+00:00
- Post Title: Firewatch

> Reply from qabRieL
>
> MitiSen wrote:Yok yok punc club'tada rusça dil seçeneği var ve o oyundada karakter limiti vardı.Kodlamada nasıl bi değişiklik olur bilmiyorum ama swuforce daha önceden bu tarz birşey yaptığı için pek zorlanacağını düşünmüyorum 
Bir dosyasına baktım sadece İngilizce vardı, ayrı ayrı dosyalardadır belki. Firewatch'ta ise ikisi tek dosyada. Ya da -2 dosyaları Rusça dili için, yanındaki yazılar da çevirmenler için bırakılan cümleler. Direk motordan veyahut başka dosyadan okuyor olabilir.

Punc club içinde şöyle mesela resources_0003.-5 rusça ise atıyorum gene resources_0004.-5 ise ingilizce dil dosyası şeklinde.Bu oyundada o şekilde anladığım kadarıyla.Birde o attığım dosyanın içinde indirdiysen localization.txt diye bir dosya var sanırım onun içinde dil dosyalarının nasıl açılacağını anlatmış tam anlamadım ben ama NGUI diye birşey geçiyor.Sanırım unity ile alakalı birşey ben pek anlamadım.Zenhax'tada konu açtım swuforce görür birşeyler yapar belki beklemedeyim şuan
## Post #10
- Username: Ogoshi
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Aug 11, 2014 12:44 pm
- Post datetime: 2016-02-10T23:03:47+00:00
- Post Title: Firewatch

English guys please, anyone can find these texts or any method for translate this game?
## Post #11
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-10T23:10:35+00:00
- Post Title: Firewatch

> Reply from Ogoshi
>
> English guys please, anyone can find these texts or any method for translate this game?
Sorry man.My english some bad and i see turkish somebody i can't hold mysefl and i write turkish.Anyway i think language files resources_***.-2 files.And character limit on word.So we need a tool translate this game.Swuforce write punch club tool open the .-5 files.Maybe he can write new tools open the -.2 files we waiting for swuforce write a tools
## Post #12
- Username: Ogoshi
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Aug 11, 2014 12:44 pm
- Post datetime: 2016-02-10T23:42:16+00:00
- Post Title: Firewatch

> Reply from MitiSen
>
> Ogoshi wrote:English guys please, anyone can find these texts or any method for translate this game?
Sorry man.My english some bad and i see turkish somebody i can't hold mysefl and i write turkish.Anyway i think language files resources_***.-2 files.And character limit on word.So we need a tool translate this game.Swuforce write punch club tool open the .-5 files.Maybe he can write new tools open the -.2 files we waiting for swuforce write a tools

HAHA Ok man! So, let's w8.
## Post #13
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-12T13:09:35+00:00
- Post Title: Firewatch

Tools made by swuforce.Thx a lot swuforce...

[http://www88.zippyshare.com/v/I6suvNyM/file.html](http://www88.zippyshare.com/v/I6suvNyM/file.html)
## Post #14
- Username: Ogoshi
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Aug 11, 2014 12:44 pm
- Post datetime: 2016-02-13T01:44:42+00:00
- Post Title: Firewatch

> Reply from MitiSen
>
> Tools made by swuforce.Thx a lot swuforce...

http://www88.zippyshare.com/v/I6suvNyM/file.html
WOW Nice! How can i use that tool?
## Post #15
- Username: Fixx1983
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Feb 13, 2016 11:20 pm
- Post datetime: 2016-02-13T15:21:41+00:00
- Post Title: Firewatch

I've extracted the resources.assets, then i've used export exe, and edited a couple of strings. But import doesn't work, it says "Subscript used on non-accessible variable." .
## Post #16
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-13T16:09:25+00:00
- Post Title: Re: Firewatch

[http://www8.zippyshare.com/v/YqFLuCsp/file.html](http://www8.zippyshare.com/v/YqFLuCsp/file.html)

Try this guys
## Post #17
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-02-13T17:01:03+00:00
- Post Title: Re: Firewatch

> Reply from MitiSen
>
> Hi i translated this game my language.Open the resources.assets but i can't find language file.

Valla hocam sırf bu girişten bile anlaşılıyor türk olduğun   Dosyayı açamadan çevirdim demişsin bir kere baştan hata.

Btw thanks for tool, i'll look.
## Post #18
- Username: Fixx1983
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Feb 13, 2016 11:20 pm
- Post datetime: 2016-02-13T17:26:06+00:00
- Post Title: Re: Firewatch

I'm able to extract, edit the TXT and reinsert it. But when I try to rebuild the .assets nothing happens, the game remains in english.
## Post #19
- Username: Ogoshi
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Aug 11, 2014 12:44 pm
- Post datetime: 2016-02-13T17:52:27+00:00
- Post Title: Re: Firewatch

> Reply from Fixx1983
>
> I'm able to extract, edit the TXT and reinsert it. But when I try to rebuild the .assets nothing happens, the game remains in english.
Can u explain how can i extract and reinsert the TXT please, first time using this tool...
## Post #20
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-02-13T18:56:22+00:00
- Post Title: Re: Firewatch

> Reply from Fixx1983
>
> ... the game remains in english.

Because game doesn't read english texts from resources.assets, but from level* files.
## Post #21
- Username: Fixx1983
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Feb 13, 2016 11:20 pm
- Post datetime: 2016-02-13T20:42:43+00:00
- Post Title: Re: Firewatch

> Reply from merlinsvk
>
> Fixx1983 wrote:... the game remains in english.

Because game doesn't read english texts from resources.assets, but from level* files.

So, fir the moment is not possible to translate the game?
## Post #22
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-02-13T21:26:32+00:00
- Post Title: Re: Firewatch

It is possible. You just have to translate texts in level* files, not in resources.assets. But, swuforce will have to modify his import/export tools a bit.
## Post #23
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-13T22:42:31+00:00
- Post Title: Re: Firewatch

> Reply from Fixx1983
>
> I'm able to extract, edit the TXT and reinsert it. But when I try to rebuild the .assets nothing happens, the game remains in english.

Translate russian section and select the game language english.

Edit:Sorry my bad i said select language english.Not english.Select game language russian
## Post #24
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-02-14T10:24:57+00:00
- Post Title: Re: Firewatch

Did you try it? Because, if you use non-cyrillic letter in russian text section, game will fallback into english. And again, it's not english from resouces.assets.
## Post #25
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-14T10:42:57+00:00
- Post Title: Re: Firewatch

it seems my team is also interest about this game, so i will have a look on that as well... Is there any confirm progress or do i need to do it all tools from scratch ? Can anyone summarize some conclusions for me in one post ?
## Post #26
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-14T11:00:29+00:00
- Post Title: Re: Firewatch

text is not taken from res files, but from level files ,where this are directly texts from UI controls, not good at all
## Post #27
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-14T11:39:00+00:00
- Post Title: Re: Firewatch

> Reply from merlinsvk
>
> Did you try it? Because, if you use non-cyrillic letter in russian text section, game will fallback into english. And again, it's not english from resouces.assets.
Yes i try it.First enter the game and select language english and exit game.Next copy original resources.assets and import in your edit resources.Next enter the game and select russian language.
## Post #28
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-02-14T12:25:33+00:00
- Post Title: Re: Firewatch

Well, it seems that you are lucky. It doesn't work with Slovak language.

[](http://www.uploadhouse.com/viewfile.php?id=22101336)
## Post #29
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-14T13:05:27+00:00
- Post Title: Re: Firewatch

> Reply from merlinsvk
>
> Well, it seems that you are lucky. It doesn't work with Slovak language.
Send me your edited resources.txt please?
## Post #30
- Username: Fixx1983
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Feb 13, 2016 11:20 pm
- Post datetime: 2016-02-15T15:35:43+00:00
- Post Title: Re: Firewatch

For italian it works good. Thanks
## Post #31
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-15T17:14:51+00:00
- Post Title: Re: Firewatch

> Reply from MitiSen
>
> merlinsvk wrote:Well, it seems that you are lucky. It doesn't work with Slovak language.


Send me your edited resources.txt please?

Can confirm it does not work..
## Post #32
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-02-15T19:46:56+00:00
- Post Title: Re: Firewatch

It works in latest game version, I had an older one (with some localization bugs).
