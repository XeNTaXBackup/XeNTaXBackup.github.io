## Post #1
- Username: fuvegotado
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 24, 2019 1:30 am
- Post datetime: 2023-07-05T16:51:39+00:00
- Post Title: Extracting Dishonored 2 and 3 (The Death of the Outsider) localization text files

Hi, in Dishonored 1 (definitive edition), the files are available as txt files: [viewtopic.php?p=192993#p192993](https://forum.xentax.com/viewtopic.php?p=192993#p192993)

In DH2 and DOTO aka DH3, that is not the case.

In the GOG version of DH2, based on which language version I have installed, I see .pck files with -english and -otherlanguage in Dishonored 2\base\pck like for example:

```
main-common-french.pck
main-game2-boat_dunwall_return_p-english.pck
main-game2-boat_dunwall_return_p-french.pck
```


These are audio packages easily extracted with [https://github.com/Vextil/Wwise-Unpacker](https://github.com/Vextil/Wwise-Unpacker)

Using quickbms (the +4gb exe) with dishonored2.bms from the site in Dishonored 2\base and *resources, I patiently wait for all to extract.

The strings/ folder contains:

```
chinese_m.lang
english_m.lang
french_m.lang
german_m.lang
italian_m.lang
japanese_m.lang
mexican_m.lang
polish_m.lang
russian_m.lang
spanish_m.lang
```


All are around 800-1300KB.

These are nicely formatted text files. For example the italian one starts with:

```
//

{
	"#number_0"	"0"
	"#number_1"	"1"
	"#number_2"	"2"
	"#number_3"	"3"
	"#number_4"	"4"
	"#number_5"	"5"
	"#number_6"	"6"
	"#number_7"	"7"
	"#number_8"	"8"
	"#number_9"	"9"
	"#str_key_apostrophe"	"’"
	"#str_key_apps"	"TASTO MENU"
```


and continues to stuff like 

```
	"Note_DD_SilverTeeth_body"	"<p>Tirare avanti qui a Karnaca è difficile?</p><br><p>Ti hanno curato i denti cariati con otturazioni d’argento?</p><br><section><p>Allora ho la soluzione per te!</p></section><p>Compro denti d’argento in qualsiasi stato. Una moneta per dente.</p><br><p>Vieni in Vico Valia il primo giorno di ogni mese.</p><br><p>Strumenti di estrazione puliti. Porta pure il tuo whiskey, se vuoi!</p>"
	"Note_DD_SilverTeeth_title"	"Denti d’argento cercasi"
	"Note_DD_ThirteenMonths_body"	"<p>Come stabilito tempo fa, i mesi sono tredici, di 28 giorni l’uno. Nelle ultime ore dell’ultimo anno, l’Alto Sacerdote suonerà la Festa della Fuga</p><br>I tredici mesi:<br>1. Il Mese della Terra<br>2. Il Mese dei Raccolti<br>3. Il Mese delle Reti<br>4. Il Mese delle Piogge<br>5. Il Mese dei Venti<br>6. Il Mese delle Tenebre<br>7. Il Mese dei Grandi Freddi<br>8. Il Mese delle Gelate<br>9. Il Mese dei Focolari<br>10. Il Mese dei Semi<br>11. Il Mese del Legname<br>12. Il Mese dei Clan<br>13. Il Mese dei Canti"
	"Note_DD_ThirteenMonths_title"	"I tredici mesi"
```


and ends with

```
	"ui_triple_buffering"	"Buffering triplo"
	"ui_unassign"	"Togli"
	"ui_uncappedframerate_warning"	"Potrebbero verificarsi importanti variazioni di framerate."
	"ui_vsync_half"	"Metà"
	"ui_xb1_switchProfile"	"Cambia profilo"

}

```


Dishonored DOTO has the same process. Even bigger .resource files. Another strings folder. 1-1.7MB files.
