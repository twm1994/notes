### find and replace recursively
`find dir -name '*.surfix' -type f -exec sed -i -e 's/regex/replacement/g' -- {} +`

### find and delete file with givn pattern
`find . -type f -name 'pattern' -delete`

### find files with given pattern recursively
`grep --include=\*.{suffixes} -rnw '/path/to/somewhere/' -e "pattern"`

### application folder
### https://wiki.gnome.org/HowDoI/AppFolders
`gsettings get org.gnome.desktop.app-folders folder-children`

### zip all file in current directory
`zip -r myfiles.zip .`

### zip all contents without including the root folder
```sh
cd rootfolder
zip -r ../package.zip .
```
### add a file to a archive
`zip -u <archivename>.zip <filename>`

### unzip view files
`unzip -l <archivename>.zip`

### unzip archive or files in the archive
`unzip <archivename>.zip [file1|file2|...] [-d <directory>]

### install Node.js
`sudo snap install node --classic --channel={version}`

### install maven
`sudo apt install maven`
