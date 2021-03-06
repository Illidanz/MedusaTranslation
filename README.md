# Medusa Translation
This repository is for the tool used to translate the game. If you're looking for the English patch, click [here](http://www.romhacking.net/translations/5558/).  
## Setup
Create a "data" folder and copy the rom as "medusa.nds" in it.  
(Optional, only for PSD export) Install [ImageMagick](https://imagemagick.org/script/download.php#windows), check "Add application directory to your system path" while installing.  
## Run from binary
Download the latest [release](https://github.com/Illidanz/MedusaTranslation/releases) outside the data folder.  
Run `tool extract` to extract everything and `tool repack` to repack after editing.  
Run `tool extract --help` or `tool repack --help` for more info.  
## Run from source
Install [Python 3.8](https://www.python.org/downloads/) and pipenv.  
Download [ndstool.exe](https://www.darkfader.net/ds/files/ndstool.exe).  
Download xdelta.exe.  
Run `pipenv install`.  
Run the tool with `pipenv run tool.py` or build with `pipenv run pyinstaller tool.spec`.  
## Text Editing
Rename the \*\_output.txt files to \*\_input.txt (bin_output.txt to bin_input.txt, etc) and add translations for each line after the "=" sign.  
The text in cnut_input is automatically wordwrapped, but a `|` can be used to force a line break.  
New textboxes can be added by appending `>>` followed by the new text.  
Control codes are specified as `\<XX\>` or `UNK(XXXX)`, they should usually be kept. Line breaks are specified as `|` or `<0A>` depending on the file.  
To blank out a line, use a single `!`. If just left empty, the line will be left untranslated.  
Comments can be added at the end of lines by using `//`  
## Image Editing
Rename the out\_\* folders to work\_\* (out_NCGR to work_NCGR, etc).  
Edit the images in the work folder(s). The palette on the right should be followed but the repacker will try to approximate other colors to the closest one.  
If an image doesn't require repacking, it should be deleted from the work folder.  
