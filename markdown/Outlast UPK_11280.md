## Post #1
- Username: xyzwrgba
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jun 21, 2011 8:39 pm
- Post datetime: 2014-03-04T22:23:57+00:00
- Post Title: Outlast UPK

I am looking for some help with the game Outlast.

I have used umodel.exe to unpack the UPK's but it seems that it did not unpack the required things, it only extracted some of the models but not all of them.

Can someone please tell me if its even possible to import an outlast level into 3ds max? That would be a dream of mine. What could I be doing wrong?

This is the script I am using:

```

:: Command file for batch export using the umodel


::-----------------------------------------------
:: Settings
:: For additional information look here:
:: http://www.gildor.org/smf/index.php/topic,1099.0.html
:: -----------------------------------------------

:: Feel free to override options below. You may fully comment the line or
:: use blank values ("set option=") here.

:: Specify game override. Use empty value for autodetection.
set game=

:: Specify directory with game files. May be either relative or absolute path.
:: Do not use quotes here!
set game_dir=..\OLGame\CookedPCConsole

:: Specify file masks to export. Note: usully Unreal package has extensions
:: whith starts with 'U' letter (*.u, *.ukx, *.upk), plus cooked packages
:: by default has extension *.xxx. Feel free to add other extensions here.
set file_mask=*.u* *.xxx *.bsm *.pcc *.gpk *.upk *.tfc

:: Specify compatibility options here - such as
:: -sounds -3rdparty -nomesh -noanim -nostat -notex -lzo -lzx -zlib
set compat=

:: Other umodel options
set options=-export -uncook -groups

:: Where to write exported contect. May be either relative or absolute path.
:: Do not use quotes here!
set out=.\Output

set log=%out%\output.log
set umodel=umodel.exe

:: End of settings block
::-----------------------------------------------

:: Debug
::set umodel=echo umodel

:: Prepare some options

if not "%game%" == "" set game_opt=-game=%game%
if not "%out%" == "" set out_opt=-out="%out%"
if "%file_mask%" == "" set file_mask=*.*

if not "%game_dir%" == "" (
	set path_opt=-path="%game_dir%"
	if not exist "%game_dir%" (
		echo ERROR: game directory "%game_dir%" is not valid
		exit
	)
)
:: export from the current directory by default
if "%game_dir%" == "" set game_dir=.

if not "%log%" == "" (
	set log_opt=-log="%log%"
	if exist "%log%" del %log%
)

:: Process ...
for /r "%game_dir%" %%a in (%file_mask%) do call :process "%%a"
goto :eof


::-----------------------------------------------
:: Function to process single package
::-----------------------------------------------
:process
echo Processing %1 ...
%umodel% %path_opt% %options% %compat% %game_opt% %out_opt% %log_opt% %1

```
