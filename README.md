https://mikrotik.com/download
https://dl.winehq.org/wine-builds/macosx/download.html
https://www.xquartz.org/
https://www.nirsoft.net/utils/resources_extract.html

cd /Applications
mkdir -p WinBox.app/Contents/MacOS
mkdir -p WinBox.app/Contents/Resources

touch WinBox.app/Contents/Info.plist
touch WinBox.app/Contents/MacOS/WinBox
chmod +x WinBox.app/Contents/MacOS/WinBox

cd ~/Desktop
mkdir Icon.iconset

iconutil -c icns Icon.iconset
