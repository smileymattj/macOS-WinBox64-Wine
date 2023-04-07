# macOS-WinBox64-Wine
Run MikroTik WinBox64 Client on macOS Catalina (64-bit only) or later


## Resource Links ##
https://youtu.be/PLACE_HOLDER

https://www.xquartz.org<br>
https://github.com/Gcenx/WineskinServer/releases<br>
https://mikrotik.com/download<br>
https://www.nirsoft.net/utils/resources_extract.html<br>


## Create Temp Working Directory ##
mkdir WineBuilds<br>
cd WineBuilds<br>


## Download Assets ##
curl -O -L https://github.com/XQuartz/XQuartz/releases/download/XQuartz-2.8.5/XQuartz-2.8.5.pkg<br>
curl -O -L https://github.com/Gcenx/WineskinServer/releases/download/V1.8.4.2/WS11WineCX21.2.0.tar.7z<br>
curl -O -L https://download.mikrotik.com/winbox/3.37/winbox64.exe<br>
curl -O -L https://www.nirsoft.net/utils/resourcesextract.zip<br>

curl -O -L https://raw.githubusercontent.com/smileymattj/macOS-WinBox64-Wine/master/WinBox.app/Contents/Info.plist<br>
curl -O -L https://raw.githubusercontent.com/smileymattj/macOS-WinBox64-Wine/master/WinBox.app/Contents/MacOS/WinBox<br>


## Install XQuartz
open XQuartz-2.8.5.pkg<br>


## Install Wine ##
open WS11WineCX21.2.0.tar.7z<br>

cd wswine.bundle<br>
rm -r share/wine/gecko<br>
sudo mkdir /usr/local/wine<br>
sudo mv * /usr/local/wine/<br>
cd ..<br>


## Install WinBox ##
mkdir -p ~/.wine/drive_c/Program\ Files/WinBox/<br>

cp winbox64.exe ~/.wine/drive_c/Program\ Files/WinBox/<br>


## Create Application Shortcut ##
mkdir -p WinBox.app/Contents/MacOS<br>
mkdir -p WinBox.app/Contents/Resources<br>

mv Info.plist WinBox.app/Contents/<br>
mv WinBox WinBox.app/Contents/MacOS/<br>
chmod +x WinBox.app/Contents/MacOS/WinBox<br>


## Extract & Set Icon ##
unzip resourcesextract.zip<br>

/usr/local/wine/bin/wine32on64 ResourcesExtract.exe<br>

open WinBox_200.ico<br>

mkdir Icon.iconset<br>
mv icon_128x128.png Icon.iconset/<br>

iconutil -c icns Icon.iconset<br>

mv Icon.icns WinBox.app/Contents/Resources/<br>


## Install WinBox Application ## 
mv WinBox.app /Applications/<br>

## Cleanup ##
cd ..<br>
rm -r WineBuilds<br>
