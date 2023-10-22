## Post #1
- Username: Ren07
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Oct 12, 2014 2:05 am
- Post datetime: 2017-10-26T18:04:50+00:00
- Post Title: [PC] ICEY (*.-167)

Hello.
Does anybody know how to extract all texts in the file? When I tried with Unity Text Reader Writer (UnityText), I can't extract all texts in the file. Some strings is missing.
I need your help. Thank you.
[ICEY Sample.7z](https://xentaxbackup.github.io/file/13494_ICEY Sample.7z)
## Post #2
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-10-27T13:08:26+00:00
- Post Title: [PC] ICEY (*.-167)

Edit UnityText.cfg. Example range:

```
		<SymbRange Start="$09" Stop="$0A" NotLetter="True"/>
		<SymbRange Start="$0D" Stop="$0D" NotLetter="True"/>
		<SymbRange Start="$20" Stop="$40" NotLetter="True"/>
		<SymbRange Start="$41" Stop="$5A" NotLetter="False"/>
		<SymbRange Start="$5B" Stop="$60" NotLetter="True"/>
		<SymbRange Start="$61" Stop="$7A" NotLetter="False"/>
		<SymbRange Start="$7B" Stop="$7E" NotLetter="True"/>
		<SymbRange Start="$A0" Stop="$BF" NotLetter="True"/>
		<SymbRange Start="$C0" Stop="$FF" NotLetter="False"/>
		<SymbRange Start="$0100" Stop="$017F" NotLetter="False"/>
		<SymbRange Start="$0401" Stop="$0401" NotLetter="False"/>
		<SymbRange Start="$0410" Stop="$044F" NotLetter="False"/>
		<SymbRange Start="$0451" Stop="$0451" NotLetter="False"/>
		<SymbRange Start="$2010" Stop="$205E" NotLetter="True"/>
		<SymbRange Start="$0370" Stop="$03FF" NotLetter="False"/>
		<SymbRange Start="$FF08" Stop="$FF09" NotLetter="True"/>
		<SymbRange Start="$E000" Stop="$E021" NotLetter="True"/>
		<SymbRange Start="$2190" Stop="$2193" NotLetter="True"/>
		<SymbRange Start="$3000" Stop="$3000" NotLetter="True"/>
	</ScanParam>
```

[Russian resources_00001.-167.rar](https://xentaxbackup.github.io/file/13497_Russian resources_00001.-167.rar)
## Post #3
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-10-27T13:22:59+00:00
- Post Title: [PC] ICEY (*.-167)

To translate .cfg for you language: <Components>bla-bla-bla</Components> 

```
btnOptions Hint = 'Options' Caption = 'O'
btnFilter Caption = 'Filter'
btnHelp Caption = '?'
btnExport Caption = 'Export'
btnPack Caption = 'Pack'
btnScan Caption = 'Scan Mode'
grpSearch Caption = 'Search'
btnNextSearch Caption = '>'
grpPath Caption = 'Path to files'
btnPath Caption = '...'
btnCsv Caption = 'csv'
grpResult Caption = 'Result'
grpFilter Caption = 'Filter'
seMinLength Hint = 'Text with length less'#13#10'this value is ignored.'
lblMinLength Hint = 'Text with length less'#13#10'this value is ignored.' Caption = 'Min Len'
btnFilterInfo Hint = 'Applies when this panel is visible and'#13#10'for binary data only. Filtered text is'#13#10'skipped. Filtering is case-sensitive.' Caption = 'i'
btnFilterMark Hint = 'Highlight the text in Results' Caption = 'M'
btnFilterReload Hint = 'Reload data' Caption = 'R'
lblMaxLength Hint = 'File containing text with length more'#13#10'than this value will be passed.'#13#10#13#10'Total number of characters in a cell:'#13#10'MS Excel - 32 759'#13#10'OO Calc, Google Spreadsheet - 50 000' Caption = 'Max Len'
seMaxLength Hint = 'File containing text with length more'#13#10'than this value will be passed.'#13#10#13#10'Total number of characters in a cell:'#13#10'MS Excel - 32 759'#13#10'OO Calc, Google Spreadsheet - 50 000'
grpOptions Caption = 'Options'
seSubstLen Hint = 'Substring length into which to be splitted text when scanning.'#13#10#13#10'If text length is in limits of this value and text completely consists'#13#10'of characters marked as "Not Letter", then such text will be ignored.'
seFrequency Hint = 'The fixed check frequency of characters of substring.'#13#10#13#10'For example for value equal 4,'#13#10'for first substring every first character is validated'#13#10'for second - every second,'#13#10'for third - every third,'#13#10'for fourth - every fourth,'#13#10'for fifth - every fourth,'#13#10'for sixth - every fourth,'#13#10'etc.'
lblSearchDepth Hint = 'Depth (count of subfolders levels) of file search' Caption = 'Search Depth'
seSearchDepth Hint = 'Depth (count of subfolders levels) of file search'
lblFrequency Hint = 'The fixed check frequency of characters of substring.'#13#10#13#10'For example for value equal 4,'#13#10'for first substring every first character is validated'#13#10'for second - every second,'#13#10'for third - every third,'#13#10'for fourth - every fourth,'#13#10'for fifth - every fourth,'#13#10'for sixth - every fourth,'#13#10'etc.' Caption = 'Frequency'
lblMaxFileSize Hint = 'Files which size in bytes is more'#13#10'than this value won'#39't be scanned.' Caption = 'Max File Size'
lblSubstLen Hint = 'Substring length into which to be splitted text when scanning.'#13#10#13#10'If text length is in limits of this value and text completely consists'#13#10'of characters marked as "Not Letter", then such text will be ignored.' Caption = 'Substring Length'
seMaxFileSize Hint = 'Files which size in bytes is more'#13#10'than this value won'#39't be scanned.'
nExportAfterOpening Caption = 'Export after data loading'
nError Caption = 'Error'
nEndian Caption = 'Little/Big Endian' Hint = 'Checked - '#39'Little Endian'#39' mode, unchecked - 								'#39'Big Endian'#39' mode'
```
