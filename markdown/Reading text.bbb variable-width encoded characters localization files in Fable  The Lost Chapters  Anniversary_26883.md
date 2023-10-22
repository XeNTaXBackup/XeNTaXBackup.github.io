## Post #1
- Username: ILOVEMODDING
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 03, 2023 7:03 am
- Post datetime: 2023-06-20T11:26:41+00:00
- Post Title: Reading text.bbb variable-width encoded characters localization files in Fable / The Lost Chapters / Anniversary

Hi, I want to get all the text in all the languages out of Fable Anniversary. It is stored in text.bbb files of 14 or so different languages.

Link to zip with all BBB files: [https://mega.nz/file/rEVFgIgb#CydxeMXm6 ... npF7fD4bMY](https://mega.nz/file/rEVFgIgb#CydxeMXm6a1uOH3uLG3lH_56-2lthzt-UnpF7fD4bMY) ("Chinese" and "SimplifiedChinese" seem to be the same as English, no idea what's up with that)

English looks like this:


Traditional Chinese looks like this:


Russian looks like this:


It looks like the first 32 bytes are the header and every letter in the text section is finalized by \x00.

However, I have no clue how to convert or figure out the encoding of for example RU/ZH. I'm working with Python, just reading chunk after chunk (length = 1)

I'm still trying to figure out how to determine where text ends and metadata starts but just counting repeats of \x00 might do it

Does this look familiar to anybody who might have hints to share?
## Post #2
- Username: kamuline
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 02, 2009 2:11 am
- Post datetime: 2023-06-20T18:16:21+00:00
- Post Title: Reading text.bbb variable-width encoded characters localization files in Fable / The Lost Chapters / Anniversary

This is a quickbms script by aluigi from zenhax

```
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get OFFSET long
goto OFFSET

get DUMMY long
get DUMMY long  # 0
get FILES long
get DUMMY long  # 1
get DUMMY long  # 83c

for i = 0 < FILES
    get DUMMY long
    if DUMMY != 0
        get DUMMY long
    endif
    get DUMMY long  # 2a
    get FILE_NUM long
    get DUMMY long  # 0
    get SIZE long
    get OFFSET long
    get DUMMY long  # 0
    get NAMESZ long
    getdstring NAME NAMESZ
    get DUMMY long  # 0
    get DUMMY long  # 0

    # make your choice
    #log NAME OFFSET SIZE   # dump to file
    callfunction DUMP 1     # dump to screen
next i

startfunction DUMP
    savepos TMP
    goto OFFSET
    get STR unicode
    print "%NAME%=%STR%"
    goto TMP
endfunction
```
## Post #3
- Username: ILOVEMODDING
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 03, 2023 7:03 am
- Post datetime: 2023-06-20T19:29:38+00:00
- Post Title: Reading text.bbb variable-width encoded characters localization files in Fable / The Lost Chapters / Anniversary

> Reply from kamuline ↑Wed Jun 21, 2023 2:16 am at Wed Jun 21, 2023 2:16 am
>
> 
This is a quickbms script by aluigi from zenhax
Code: Select allidstring "BBBB"
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get OFFSET long
goto OFFSET

get DUMMY long
get DUMMY long  # 0
get FILES long
get DUMMY long  # 1
get DUMMY long  # 83c

for i = 0 < FILES
    get DUMMY long
    if DUMMY != 0
        get DUMMY long
    endif
    get DUMMY long  # 2a
    get FILE_NUM long
    get DUMMY long  # 0
    get SIZE long
    get OFFSET long
    get DUMMY long  # 0
    get NAMESZ long
    getdstring NAME NAMESZ
    get DUMMY long  # 0
    get DUMMY long  # 0

    # make your choice
    #log NAME OFFSET SIZE   # dump to file
    callfunction DUMP 1     # dump to screen
next i

startfunction DUMP
    savepos TMP
    goto OFFSET
    get STR unicode
    print "%NAME%=%STR%"
    goto TMP
endfunction

That's amazing! RIP zenhax (but hopefully not really).

I saved the script as `fablebbb.bms` and ran

```
./quickbms.exe -0 fablebbb.bms text.bbb > en.txt
```


and then ran renamed all bbb files, moved to one folder and ran a loop over them

Turns out a bunch of languages aren't actually supported but have folders and files, which are nearly identical to the English language pack. Not sure what's up with that, perhaps some slipped through the management cracks of getting the game out on time.

Everything looks great! Except for Portuguese. The folder is named specifically EuropeanPortuguese but on Steam, Fable is listed with Portuguese - Brazil and there are huge amounts of texts that are in [English] (see below).

EN:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=If you get three hits in a row without reply, you can Flourish by pressing [GAME_ACTION_SPECIAL_ATTACK]. Try it in this battle.
>
> TEXT_QST_067_INFECTED_BANTER_30=I've been thinking, you shouldn't worry. If I'm the only one who makes it, I'll take care of your wares.
>
> TEXT_CS_B13_SEX_SOPHIA_20=Take me with you!
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=I'd better make a move now and check on the damage.
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=Skip
>
> TXT_STORY_12=This satirical pamphlet purports to be a journal of a Zero in training, and is a thinly veiled attack on the Guild, the self-claimed superiority of its members and the cult of celebrity that surrounds them. The author disappeared shortly after its publication.
>
> TXT_NAME_16=Name 16
ES:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=Si logras tres impactos seguidos sin respuesta, podrás hacer una floritura pulsando [GAME_ACTION_SPECIAL_ATTACK]. Inténtalo en esta batalla.
>
> TEXT_QST_067_INFECTED_BANTER_30=He estado pensando, no deberíais preocuparos. Si soy el único que logra llegar, yo me encargaré de vuestras mercancías.
>
> TEXT_CS_B13_SEX_SOPHIA_20=¡Llevadme con vos!
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=Mejor que me ponga a trabajar ya y compruebe los daños.
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=Saltar
>
> TXT_STORY_12=Este panfleto satírico pretende ser un diario de un aprendiz de cero, y es un ataque poco disimulado al Gremio, la autoproclamada superioridad de sus miembros y el culto a la fama que los rodea. El autor desapareció poco después de su publicación.
>
> TXT_NAME_16=Nombre 16
>
> TXT_NAME_03=Nombre 3
ZH-CHT:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=如果您連續擊中敵人 3 次，而且沒遭到反擊，您就可以按下 [GAME_ACTION_SPECIAL_ATTACK] 來使出重擊。您可以在這場戰鬥中試試看。
>
> TEXT_QST_067_INFECTED_BANTER_30=我一直在想，其實你不用擔心。如果我是當事人，我也會好好看管你的東西。
>
> TEXT_CS_B13_SEX_SOPHIA_20=帶我一起走吧！
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=我最好趕緊去看一下，損失嚴不嚴重。
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=跳過場景
>
> TXT_STORY_12=這本帶有批判性的小冊子原本是某個狗熊的受訓日誌。有人拿它來攻擊公會及公會成員，認為這些人的權威名不符實，作者在本書出版沒多久後就不見蹤影。
>
> TXT_NAME_16=名稱 16
KO:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=반격을 당하지 않고 세 번의 공격을 연속으로 성공시키면, [GAME_ACTION_SPECIAL_ATTACK]를 눌러 특수 공격을 사용할 수 있습니다. 이번 전투에서 특수 공격을 시도해 보십시오.
>
> TEXT_QST_067_INFECTED_BANTER_30=쭉 생각해 봤는데 걱정할 필요 없어요. 내가 그걸 만드는 유일한 사람이라면 당신의 물건을 잘 봐줄게요.
>
> TEXT_CS_B13_SEX_SOPHIA_20=날 가져요!
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=저는 피해가 얼마나 되는지 어서 확인해 봐야겠습니다.
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=건너뛰기
>
> TXT_STORY_12=이 풍자집은 길드에서 훈련을 받는 제로라는 인물이 쓴 일기 형식으로 된 소책자로서, 길드와 길드 회원들이 스스로 주장하는 우월성과 그들 주위의 명성을 숭배하는 무리들에 대해 은근히 비판하는 글입니다. 작가는 출간 후 곧 행방불명되었습니다.
>
> TXT_NAME_16=이름 16
JA:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=反撃をかわしながら、攻撃が敵に 3 回連続してヒットしたら、[GAME_ACTION_SPECIAL_ATTACK] ボタンを押してフラッシュムーブを発動します
>
> TEXT_QST_067_INFECTED_BANTER_30=なあ、心配するなって。みんなやられちまったとしても、あんたたちの商品は俺が面倒みるからさ。
>
> TEXT_CS_B13_SEX_SOPHIA_20=香りに集中して...
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=さあて、さっそく被害を調べるとするか。
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=スキップ
>
> TXT_STORY_12=この風刺的な小冊子は、ギルドで修行中の、とある英雄見習いの日記だと言われており、己の優越を公言してはばからないごう慢なギルド出身者たちや、彼らを取り巻く熱烈なファンに対する痛烈な批判が見え隠れしています。著者はこの冊子を出版後、まもなく消息を絶ちました。
>
> TXT_NAME_16=名前 16
IT:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=Se metti a segno tre colpi consecutivi senza risposta, puoi usare la mossa fiorente premendo [GAME_ACTION_SPECIAL_ATTACK]. Prova a farlo in battaglia.
>
> TEXT_QST_067_INFECTED_BANTER_30=Stavo pensando che non hai di che preoccuparti. Se dovessi essere l'unico a sopravvivere, mi occuperò io della tua roba.
>
> TEXT_CS_B13_SEX_SOPHIA_20=Portami via con te!
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=Farei meglio ad agire, ora, e verificare i danni.
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=Salta
>
> TXT_STORY_12=Questo libello satirico vuole essere il diario di un allievo incapace nell'addestramento e rappresenta un velato attacco alla gilda, alla presunta superiorità dei suoi membri e all'aura di celebrità che li avvolge. L'autore scomparve poco dopo la pubblicazione del libro.
>
> TXT_NAME_16=Nome 16
RU:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=После трех ударов, которые противник не смог блокировать, можно использовать замах, нажав [GAME_ACTION_SPECIAL_ATTACK]. Опробуйте это в битве!
>
> TEXT_QST_067_INFECTED_BANTER_30=Я тут подумал, что тебе не стоит волноваться. Если я один выживу, то позабочусь о твоем товаре.
>
> TEXT_CS_B13_SEX_SOPHIA_20=Забери меня с собой!
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=Я, пожалуй, пойду проверю, что уцелело.
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=Пропустить
>
> TXT_STORY_12=Этот сатирический памфлет - дневник тренировок Отстоя, содержащий тонко завуалированную критику Гильдии, а так же надуманного превосходства ее членов над остальными людьми и культа личности, который окружает всех гильдейских героев. Автор исчез вскоре после публикации книги.
>
> TXT_NAME_16=Имя 16
DE:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=Wenn Euch drei Treffer in Folge ohne Gegentreffer gelingen, könnt Ihr mit [GAME_ACTION_SPECIAL_ATTACK] eine Abschlussbewegung ausführen. Probiert es mal in diesem Kampf.
>
> TEXT_QST_067_INFECTED_BANTER_30=Ich finde, Ihr solltet Euch keine Sorgen machen. Wenn nur ich überlebe, kümmere ich mich gern um Eure Waren.
>
> TEXT_CS_B13_SEX_SOPHIA_20=Nehmt mich mit!
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=Ich sollte mir den Schaden ansehen.
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=Auslassen
>
> TXT_STORY_12=Diese satirische Schrift gibt vor, das Notizbuch einer kompletten Null im Training zu sein. Es handelt sich um einen kaum verhüllten Angriff auf die Gilde, die selbstherrliche Überlegenheit ihrer Mitglieder und den ruhmsüchtigen Kult, der sie umgibt. Der Autor verschwand kurz nach der Veröffentlichung.
>
> TXT_NAME_16=Name 16
FR:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=Si vous portez trois coups d'affilée sans être touché en retour, vous pouvez exécuter une Botte en appuyant sur la touche [GAME_ACTION_SPECIAL_ATTACK]. Essayez dans ce combat.
>
> TEXT_QST_067_INFECTED_BANTER_30=J'ai bien réfléchi : si je suis seul survivant, pas de souci, je m'occupe de vos marchandises.
>
> TEXT_CS_B13_SEX_SOPHIA_20=Prends-moi avec toi !
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=Il faut que j'aille évaluer l'étendue des dégâts.
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=Passer
>
> TXT_STORY_12=Ce pamphlet, qui se présente sous la forme d'un journal et s'intitule La Guilde des Zéros constitue une attaque contre la Guilde à peine dissimulée, la supériorité autoproclamée de ses membres et le culte de la célébrité qu'elle favorise. L'auteur de cet ouvrage disparut peu après sa publication.
>
> TXT_NAME_16=Nom 16
PT:

> TEXT_QST_028_ONSCREENHELP_FLOURISH_BASIC=Se acertar três vezes seguidas e não obtiver resposta, você poderá fazer um Floreio pressionando [GAME_ACTION_SPECIAL_ATTACK]. Experimente fazer isso nesta batalha.
>
> TEXT_QST_067_INFECTED_BANTER_30=Eu estive pensando, você não devia se preocupar. Se eu for o único a sair dessa, eu vou cuidar das suas mercadorias.
>
> TEXT_CS_B13_SEX_SOPHIA_20=[Take me with you! !!! !!! ]
>
> TEXT_GUI_TLC_CRE_3040=Katie Roberts
>
> TEXT_CS_035_END_30=É melhor eu me mexer agora e verificar os danos.
>
> TEXT_GUI_CRE_6230=Mike Minahan
>
> TEXT_GUI_CRE_774= 
>
> TEXT_GUI_CRE_330=Guillaume Portes
>
> TEXT_GUI_SKIP=[Skip !!!]
>
> TXT_STORY_12=Este panfleto satírico propõe-se a ser o diário de um "Zerói" em treinamento e é uma crítica mal velada à Guilda, à superioridade autoadquirida de seus integrantes e ao culto à celebridade que os rodeia. O autor desapareceu pouco tempo após a publicação.
>
> TXT_NAME_16=Nome 16

About 550 lines of the ~27670 lines total seem to have some nonprintable characters as the text value but perhaps that's unused or means some command or something.

Merci beaucoup!
