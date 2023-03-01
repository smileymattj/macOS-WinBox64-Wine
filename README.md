# macOS-WinBox64-Wine
Run MikroTik WinBox64 Client on macOS Catalina (64-bit only) or later


## Resource Links ##
https://www.youtube.com/watch?v=kU1UtPcQlzQ<br>

https://mikrotik.com/download<br>
https://dl.winehq.org/wine-builds/macosx/download.html<br>
https://www.xquartz.org/<br>
https://www.nirsoft.net/utils/resources_extract.html<br>


## Create Application Shortcut ##
cd /Applications

mkdir -p WinBox.app/Contents/MacOS<br>
mkdir -p WinBox.app/Contents/Resources<br>

touch WinBox.app/Contents/Info.plist<br>
touch WinBox.app/Contents/MacOS/WinBox<br>
<b>chmod +x WinBox.app/Contents/MacOS/WinBox</b><br>


## Create Icon ##
cd ~/Desktop<br>
mkdir Icon.iconset

iconutil -c icns Icon.iconset
