# FONTCONFIG
Windows compatible font configuration for linux originated programs (ffmpeg, fontforge, inkscape, mpv, ...)

set those locally (in bat/cmd file) before running the applications

```cmd
set "FC_CONFIG_DIR=./fonts"
set "FONTCONFIG_PATH=./fonts"
set "FONTCONFIG_FILE=fonts.conf"
```

you can also use an explicit path, and just fixing it afterwards..

```cmd
set "FC_CONFIG_DIR=%~sdp0\fonts"
set "FONTCONFIG_PATH=%~sdp0\fonts"
set "FONTCONFIG_FILE=%~sdp0\fonts.conf"

set "FC_CONFIG_DIR=%FC_CONFIG_DIR:\=/%"
set "FONTCONFIG_PATH=%FONTCONFIG_PATH:\=/%"
set "FONTCONFIG_FILE=%FONTCONFIG_FILE:\=/%"
```

short path (8.3) is used, but you can try with just `%~dp0`.


`%~sdp0`, and `%~dp0` are pointing the the same folder the current batch file is running from.

<hr/>

a perfectly acceptable SIMPLER workaround to copy the font-file locally and just using its name (case sensitive),  
avoid spaces keep it a-z0-9 characters only.  

OR,  
use an explicit path with forward slash to the font filename, you must(!) escape the `:` character!

for example Courier New (Bold) - "courbd.ttf",  

`...... -vf "fps=25,drawtext=:fontfile=\'c\:/Windows/Fonts/courbd.ttf\':fontcolor=yellow:borderw=1:alpha=0.7" ......`  

