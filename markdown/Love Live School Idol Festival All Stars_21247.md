## Post #1
- Username: anime663
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-14T16:48:42+00:00
- Post Title: Love Live School Idol Festival All Stars

Love Live School Idol Festival All Stars
ラブライブ！スクールアイドルフェスティバルALL STARS 
decryption script
Must use quickbms_4gb_files.exe
also must use command line -n -C
example
c:\quickbms\quickbms_4gb_files.exe -n -C C:\LL.bms . C:\output_folder

```
# by chrrox
# script for QuickBMS http://quickbms.aluigi.org
# original code from https://gist.github.com/esterTion/ff57aafd8dc950216041ac004fc25536

quickbmsver "0.8.0"
set MEMORY_FILE10 string "
typedef unsigned char uchar;
typedef unsigned int uint;

int ll_decrypt(unsigned char *data, int size, int keys_0, int keys_1, int keys_2) {
    int     i;
    for(i = 0; i < size; i++) {
        uchar c = data[i];
        data[i] = data[i] ^ (((keys_1 ^ keys_0 ^ keys_2) >> 24) & 0xff);
        keys_0 = (0x343fd * keys_0 + 0x269ec3) & 0xFFFFFFFF;
        keys_1 = (0x343fd * keys_1 + 0x269ec3) & 0xFFFFFFFF;
        keys_2 = (0x343fd * keys_2 + 0x269ec3) & 0xFFFFFFFF;
    }
}
"
comtype zlib_dynamic

set URLBASE string "https://jp-real-prod-v4tadlicuqeeumke.api.game25.klabgames.net/ep1002/static/f141c313a139e1e6/"
open "." "https://jp-real-prod-v4tadlicuqeeumke.api.game25.klabgames.net/ep1002/static/f141c313a139e1e6/masterdata_a_ja"
get SIZE asize
log MEMORY_FILE 0 SIZE
goto 0x14 MEMORY_FILE
get NSIZE byte MEMORY_FILE
getdstring VERSION NSIZE MEMORY_FILE
get NSIZE byte MEMORY_FILE
getdstring LANG NSIZE MEMORY_FILE
get FILES byte MEMORY_FILE
print "%VERSION% %LANG% %FILES%"
for i = 0 < files
math constKeys_0 =   0x3039  // 12345
math constKeys_1 =   0x10932 // 67890
math constKeys_2 =   0x7AB7  // 31415
set MEMORY_FILE2 ""
get NSIZE byte MEMORY_FILE
getdstring FNAME NSIZE MEMORY_FILE
get NSIZE byte MEMORY_FILE
getdstring KEY0 8 MEMORY_FILE
getdstring KEY1 8 MEMORY_FILE
getdstring KEY2 8 MEMORY_FILE
getdstring CRC 16 MEMORY_FILE
#print "%FNAME% %KEY0% %KEY1% %KEY2% %CRC%"
set TMP string "$"
string TMP += KEY0
set KEY0 long TMP

set TMP string "$"
string TMP += KEY1
set KEY1 long TMP

set TMP string "$"
string TMP += KEY2
set KEY2 long TMP
#print "%FNAME% %KEY0% %KEY1% %KEY2% %CRC%"
set URL URLBASE
string URL + FNAME
print "Downloading %URL%"
xmath keys_0 "constKeys_0 ^ KEY0"
xmath keys_1 "constKeys_1 ^ KEY1"
xmath keys_2 "constKeys_2 ^ KEY2"
open "." URL
get SIZE asize
log MEMORY_FILE2 0 SIZE
calldll MEMORY_FILE10 "ll_decrypt" "tcc" RET MEMORY_FILE2 SIZE keys_0 keys_1 keys_2
string FNAME + ".sqlite"
clog FNAME 0 SIZE SIZE MEMORY_FILE2
next i


```
## Post #2
- Username: Unari
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jan 31, 2019 12:53 pm
- Post datetime: 2019-11-01T12:23:28+00:00
- Post Title: Love Live School Idol Festival All Stars

What file do you use this script on, and where may I find it? (Thanks in advance)
## Post #3
- Username: sunnydoll
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Nov 09, 2018 7:22 am
- Post datetime: 2020-05-05T13:57:47+00:00
- Post Title: Love Live School Idol Festival All Stars

Hello everyone   
I was digging a bit and I though it would be good to post here a list so that everyone can find easier what he/she is looking for   
I have also linked the pictures of the girls + the outfit 

suit:301013001 Chika Takami - [Leo Star Bright](https://i.idol.st/u/card/art/2x/137Takami-Chika-Surrounded-by-Shooting-Stars-UR-POIwqg.png)

suit:401083001 Mari Ohara - [Whistle of the Morning Star](https://i.idol.st/u/card/art/2x/146Ohara-Mari-Alright-Let-s-Go-UR-bW9A56.png)

suit:401093001 Ruby Kurosawa - [Little Rabbit
](https://i.idol.st/u/card/art/2x/114Kurosawa-Ruby-L-Like-This-UR-HC6H7r.png)

suit:402023001 Kasumi Nakasu - [Magical☆Fever](https://i.idol.st/u/card/art/2x/201UR-Nakasu-Kasumi-I-ll-show-you-Magical-Fever-8Iq9AY.png)

suit:400083001 Hanayo Koizumi - [Fleur Rêvé](https://i.idol.st/u/card/art/2x/121Koizumi-Hanayo-%E4%B8%80%E6%AD%A9%E3%81%8D%E3%82%8A%E3%81%A7%E7%B5%82%E3%82%8F%E3%82%89%E3%81%9B%E3%81%AA%E3%81%84%E3%82%88%E3%81%86%E3%81%AB-UR-Ajb3Ph.png)

suit:200033001 Kotori Minami - [Humming Angel](https://i.idol.st/u/card/art/2x/149Minami-Kotori-This-Swimsuit-s-my-Favorite-UR-Hz3cLb.png)

suit:200063001 Maki Nishikino

suit:200093001 Nico Yazawa - [Smiley Angel](https://i.idol.st/u/card/art/2x/167Yazawa-Nico-Thank-you-UR-4Gd5em.png)

suit:201053001 You Watanabe - [Splash Marine](https://i.idol.st/u/card/art/2x/133Watanabe-You-Coming-to-the-Sea-Together-UR-9qXg5E.png)

suit:201063001 Yoshiko Tsushima - [Devil Rocker](https://i.idol.st/u/card/art/2x/151Tsushima-Yoshiko-If-I-m-with-You-UR-wVhvMf.png)

suit:201083001 Mari Ohara - [Royal Princess](https://i.idol.st/u/card/art/2x/185Ohara-Mari-I-ll-support-you-UR-sjyAUK.png)

suit:202063001 Kanata Konoe - [Angel's Lullaby](https://i.idol.st/u/card/art/2x/186Konoe-Kanata-It-s-my-turn-next-UR-e8Wes0.png)

suit:202083001 Emma Verde - [Delightful Waltz](https://i.idol.st/u/card/art/2x/168Verde-Emma-A-flower-crown-You-made-it-UR-dCOz0b.png)

suit:300013001 Honoka Kousaka

suit:300023001 Eli Ayase - [Forest Fairy](https://i.idol.st/u/card/art/2x/126Ayase-Eli-T-Those-bushes-just-shook-UR-8d6zQw.png)

suit:300033001 Kotori Minami - [Welcome to the Party](https://i.idol.st/u/card/art/2x/104Minami-Kotori-%E3%81%93%E3%81%A3%E3%81%A1%E6%89%8B%E4%BC%9D%E3%81%A3%E3%81%A6%E3%81%8F%E3%82%8C%E3%82%8B-UR-eksYsr.png)

suit:300043001 Umi Sonoda - [Blue Amor](https://i.idol.st/u/card/art/2x/116Sonoda-Umi-One-Shot-in-Your-Soul-UR-XbAeAB.jpg)

suit:300053001 Rin Hoshizora - [After School Cat](https://i.idol.st/u/card/art/2x/141Hoshizora-Rin-%E3%81%93%E3%81%A3%E3%81%A1%E3%81%93%E3%81%A3%E3%81%A1%E6%97%A9%E3%81%8F%E3%81%99%E3%82%8B%E3%81%AB%E3%82%83-UR-lhTbCP.png)

suit:300073001 Nozomi Toujou - [Magical☆Fever](https://i.idol.st/u/card/art/2x/197UR-Toujou-Nozomi-Pain-Pain-Go-Away-Magical-Fever-lnWXbU.png)

suit:300083001 Hanayo Koizumi - [Happy Parade](https://i.idol.st/u/card/art/2x/159Koizumi-Hanayo-Aw-you-re-too-cute-UR-uvN2Ba.png)

suit:300093001 Nico Yazawa - [Whistle of the Morning Star](https://i.idol.st/u/card/art/2x/143Yazawa-Nico-How-s-Nico-s-Special-Lunches-UR-k8SYLM.png)

suit:301023001 Riko Sakurauchi - [Blossom Prelude](https://i.idol.st/u/card/art/2x/125Sakurauchi-Riko-Clear-Melody-with-no-Hesitation-UR-cmO64g.png)

suit:301033001 Kanan Matsuura - [Blue Rêvé](https://i.idol.st/u/card/art/2x/120Matsuura-Kanan-%E3%81%A1%E3%82%83%E3%82%93%E3%81%A8%E7%B9%8B%E3%81%8C%E3%82%8C%E3%81%9F%E3%82%93%E3%81%A0%E3%81%8B%E3%82%89-UR-zSTlOK.png)

suit:301043001 Dia Kurosawa - [Little Rabbit](https://i.idol.st/u/card/art/2x/112Kurosawa-Dia-What-Shall-the-Next-Pose-Be-Like-UR-JB6dE6.png)

suit:301053001 You Watanabe - [Miracle voyage](https://i.idol.st/u/card/art/2x/153Watanabe-You-%E3%81%93%E3%81%AE%E3%82%A2%E3%83%88%E3%83%A9%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3-%E9%9D%A2%E7%99%BD%E3%83%BC%E3%81%84-UR-vO751f.png)

suit:301063001 Yoshiko Tsushima - [Twilight Demon](https://i.idol.st/u/card/art/2x/110Tsushima-Yoshiko-The-descent-of-the-fallen-angel-UR-UfcrCF.png)

suit:301093001 Ruby Kurosawa - [Sweets Deco](https://i.idol.st/u/card/art/2x/161Kurosawa-Ruby-It-looks-delicious-UR-cEAVpQ.png)

suit:302023001 Kasumi Nakasu - [Flower Symphony](https://i.idol.st/u/card/art/2x/171Nakasu-Kasumi-Thanks-for-Waiting-UR-DmTt3R.png)

suit:302043001 Karin Asaka - [Celebrity Blue](https://i.idol.st/u/card/art/2x/196UR-Asaka-Karin-Did-I-make-your-heart-skip-a-beat-Celebrity-Blue-9bxvW4.png)

suit:302083001 Emma Verde - [Little Red Riding Hood](https://i.idol.st/u/card/art/2x/190UR-Emma-Verde-I-brought-it-here-Innocent-Little-Red-Riding-Hood-fTQ3lq.png)


Please consider, that this is not the full list. It is just what I have opened so far. I will continue to update this list
## Post #4
- Username: nosyrbllewe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 23, 2019 4:54 am
- Post datetime: 2020-05-06T06:16:04+00:00
- Post Title: Love Live School Idol Festival All Stars

Mind sharing how you got the files? When I run the script (after updating the URL endpoint) I get the masterdata, dictionary, and asset databases, though they still seem to be encrypted. Did the encryption change?
## Post #5
- Username: sunnydoll
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Nov 09, 2018 7:22 am
- Post datetime: 2020-05-06T16:39:23+00:00
- Post Title: Love Live School Idol Festival All Stars

> Mind sharing how you got the files? When I run the script (after updating the URL endpoint) I get the masterdata, dictionary, and asset databases, though they still seem to be encrypted. Did the encryption change?

For me it has been a very complicated process. Back then I joined the XenTax discord and texted chrrox on private.
He spend a full day helping me to get everything right. I would recommend you to do the same. I am not good in extracting models from games at all. I am a 3D animator and want the models from making fan art/ fan renders and fan videos.

Yesterday I could finally found the motion/ animation data! 
So I came back here to make a short update for the dances 

Pack name "g0f35p" is Doki Pipo ☆ Emotion dance.

Pack name "d2l7pk" is Nemureru Mori ni Ikitai na dance.

Pack name "sk5ftx" is Meccha Going dance.

For now it is a bit random... u don't know what u will get xD
The motions works also very good once applied on the models.
The only thing making me problems are the faces (eyes and mouth parts) and their motions.
But at least I could make the body moving.
## Post #6
- Username: Hani Seolhyun
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 04, 2020 1:23 pm
- Post datetime: 2020-06-04T05:28:45+00:00
- Post Title: Love Live School Idol Festival All Stars

> Reply from sunnydoll ↑Thu May 07, 2020 12:39 am at Thu May 07, 2020 12:39 am
>
> 
Mind sharing how you got the files? When I run the script (after updating the URL endpoint) I get the masterdata, dictionary, and asset databases, though they still seem to be encrypted. Did the encryption change?

For me it has been a very complicated process. Back then I joined the XenTax discord and texted chrrox on private.
He spend a full day helping me to get everything right. I would recommend you to do the same. I am not good in extracting models from games at all. I am a 3D animator and want the models from making fan art/ fan renders and fan videos.

Yesterday I could finally found the motion/ animation data! 
So I came back here to make a short update for the dances 

Pack name "g0f35p" is Doki Pipo ☆ Emotion dance.

Pack name "d2l7pk" is Nemureru Mori ni Ikitai na dance.

Pack name "sk5ftx" is Meccha Going dance.

For now it is a bit random... u don't know what u will get xD
The motions works also very good once applied on the models.
The only thing making me problems are the faces (eyes and mouth parts) and their motions.
But at least I could make the body moving.

I want to know how you did it, I can't decrypt the files
## Post #7
- Username: sunnydoll
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Nov 09, 2018 7:22 am
- Post datetime: 2020-06-07T06:28:07+00:00
- Post Title: Love Live School Idol Festival All Stars

@Hani Seolhyun
It is best to contact chrrox if you have questions or difficulties.
I also contacted chrrox and received a lot help 
The script is working very good. But you have to edit always the key1 and key2 information. Every 3D model has different keys.
## Post #8
- Username: Hani Seolhyun
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 04, 2020 1:23 pm
- Post datetime: 2020-06-15T22:05:04+00:00
- Post Title: Love Live School Idol Festival All Stars

> Reply from sunnydoll ↑Sun Jun 07, 2020 2:28 pm at Sun Jun 07, 2020 2:28 pm
>
> 
@Hani Seolhyun
It is best to contact chrrox if you have questions or difficulties.
I also contacted chrrox and received a lot help 
The script is working very good. But you have to edit always the key1 and key2 information. Every 3D model has different keys.

ok thanks  

I can contact you on a social network is for something private
## Post #9
- Username: HagumiBoi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 15, 2020 9:31 pm
- Post datetime: 2020-07-30T02:20:31+00:00
- Post Title: Love Live School Idol Festival All Stars

Game updated 1.7.1
Some files has changed key, any working script 2020?
## Post #10
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-08-04T01:17:31+00:00
- Post Title: Love Live School Idol Festival All Stars

Anyone have any guide of sorts(preferred video)? I don't even know where to start with this game
## Post #11
- Username: sunnydoll
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Nov 09, 2018 7:22 am
- Post datetime: 2020-12-01T17:44:26+00:00
- Post Title: Love Live School Idol Festival All Stars

Hello guys.
I am so sorry that I see this all sooo late!!
yes - everyone of you can add me on discord and I wanna try to help all and to pass the knowledge chrrox taught me.
I still have some of the old models + some old dances.

This is my discord:
N a t a l i a#2123
## Post #12
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2020-12-19T09:17:18+00:00
- Post Title: Love Live School Idol Festival All Stars

> Reply from sunnydoll ↑Wed Dec 02, 2020 1:44 am at Wed Dec 02, 2020 1:44 am
>
> 
Hello guys.
I am so sorry that I see this all sooo late!!
yes - everyone of you can add me on discord and I wanna try to help all and to pass the knowledge chrrox taught me.
I still have some of the old models + some old dances.

This is my discord:
N a t a l i a#2123

I look for how to rip the models of this game, but I can't know how to do it
## Post #13
- Username: sunnydoll
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Nov 09, 2018 7:22 am
- Post datetime: 2021-01-21T15:20:49+00:00
- Post Title: Love Live School Idol Festival All Stars

Ohh yes, I changed my discord.
If you still need help: Наталия#9262
## Post #14
- Username: amnesia567
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 10, 2018 3:40 am
- Post datetime: 2021-03-03T02:23:18+00:00
- Post Title: Love Live School Idol Festival All Stars

> Reply from sunnydoll ↑Thu Jan 21, 2021 11:20 pm at Thu Jan 21, 2021 11:20 pm
>
> 
Ohh yes, I changed my discord.
If you still need help: Наталия#9262
Hi!, I'm trying to add you in discord but I can't and I really want to extract models from this game.
Also my Discord Nickname: Amnesia567#7421
## Post #15
- Username: Coffi9724
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 09, 2021 5:38 am
- Post datetime: 2021-05-08T21:42:03+00:00
- Post Title: Love Live School Idol Festival All Stars

> Reply from sunnydoll ↑Thu Jan 21, 2021 11:20 pm at Thu Jan 21, 2021 11:20 pm
>
> 
Ohh yes, I changed my discord.
If you still need help: Наталия#9262

I would also like help learning how to rip the models from this game.
## Post #16
- Username: Atlus
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 31, 2021 5:52 pm
- Post datetime: 2021-07-20T05:27:41+00:00
- Post Title: Re: Love Live School Idol Festival All Stars

Me too, i also want to learn how to extract the models from the game, here are my discord nicknames:

Shangri-Spa Shyguy#1327

Fishy Boopkins#0406
## Post #17
- Username: loveliverichiban
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 18, 2021 5:59 am
- Post datetime: 2021-11-17T22:02:51+00:00
- Post Title: Re: Love Live School Idol Festival All Stars

> Reply from sunnydoll ↑Wed Dec 02, 2020 1:44 am at Wed Dec 02, 2020 1:44 am
>
> 
Hello guys.
I am so sorry that I see this all sooo late!!
yes - everyone of you can add me on discord and I wanna try to help all and to pass the knowledge chrrox taught me.
I still have some of the old models + some old dances.

This is my discord:
N a t a l i a#2123

I want to learn also my discord is "Ishmael#4185"
## Post #18
- Username: caret
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 03, 2021 4:48 am
- Post datetime: 2021-12-17T05:01:18+00:00
- Post Title: Re: Love Live School Idol Festival All Stars

[https://github.com/641i130/klbvfs](https://github.com/641i130/klbvfs)
