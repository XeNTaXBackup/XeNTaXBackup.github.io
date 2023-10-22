## Post #1
- Username: gevolushn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 24, 2021 3:27 am
- Post datetime: 2021-03-23T19:33:29+00:00
- Post Title: Dishonored localization file reader

I am looking for certain dialogues, as well as content cut from the game. But I ran into a problem that I cannot read localized dialogues in a standard way. I open it through the editor, and there is an empty space. Hence, I am looking for an application or utility to read such files.
P. S. Sorry for my english.
## Post #2
- Username: fuvegotado
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 24, 2019 1:30 am
- Post datetime: 2023-07-05T11:37:35+00:00
- Post Title: Dishonored localization file reader

In Dishonored definitive edition, in DishonoredGame/Localization/[DEU/ESN/FRA/INT/ITA]/ there are files with the ending of the folder (lowercase). INT being English.

You can open them with Notepad++

Example:

```
m_ItemName="Observaciones de Sokolov sobre el sujeto de pruebas 312"
m_PluralItemName=""
m_Description="Sokolov graba los resultados de sus investigaciones y experimentos con un sujeto de pruebas humano, una mujer detenida por la Guardia y encerrada en casa de Sokolov."

[AbstractInv_Graphs.AG_Brothel_SlackJaw DisAbstractItemAudioLog]
m_ItemName="Últimas palabras de Crowley"
m_PluralItemName=""
m_Description=Slackjaw, soy yo, Crowley. Estoy grabando esto por si no vuelvo. Tenías razón, alguien te quiere muerto. Pretende hacerse con la destilería, con la banda de Bottle Street. Y tú tampoco creerás de quién se trata. Yo tampoco, al principio, por eso he tardado tanto. Quería asegurarme y... Ya lo estoy. Completamente seguro. Es... Eh, ¿qué es...? ¡Aah! ¡No! ¡Nooooooo! ¡Aaaah! (ruidos de violencia que se interrumpen bruscamente)"

[AbstractInv_Graphs.AG_DaudRegentDead DisAbstractItemAudioLog]
m_ItemName="Reflexiones sobre la muerte del lord Regente"
m_PluralItemName=""
m_Description="Comentarios de Daud sobre el destino del lord Regente."
```


from the top of AudioGraph_Twk.esn
