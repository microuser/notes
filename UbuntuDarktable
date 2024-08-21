# Creating A Photo Ingress Server.
## ubuntu darktable installation instructions 

###Develop a naming scheme for the directory structure 
I know that "if" statements exist and I could have conditional directory structures with smarter organization.
but for now having a representation for  Y/M/D/h/m/s/exifdata/filename.ext in the simplest form of creating a directory without errors due to strings being empty. 2) not overflowing one directory. 3) not confusing 
The suggested above pattern creates massive issues because it push inodes to the max for fat32 file systems. This test system has ext4 and zfs disks. I calculate the folders to be deep, about 10.


###the directory pattern...
```
Y$(EXIF_YEAR-0000)/M$(EXIF_MONTH-00)/D$(EXIF_DAY-00)/h$(EXIF_HOUR-00)/m$(EXIF_MINUTE-00)/s$(EXIF_SECOND-00)/ISO$(EXIF_ISO)-EXP$(EXIF_EXPOSURE)-BIAS$(EXIF_EXPOSURE_BIAS)-AP$(EXIF_APERTURE)-x$(MAX_WIDTH-0)-y$(MAX_HEIGHT-0)
```

###and the filename.ext pattern being ...
```
$(FILE_NAME)-$(SEQUENCE).$(FILE_EXTENSION)
```


in the terminal 

I want to give thought and explanation of what we see. We see a zfs filesystem mounted at /Hexamir
we want to have (from user saving a file perspective) the files imported to ~/Pictures/Darktable in the user's home folder to actually be written on the other filesystem mounted to /Hexamir/Darktable , when browsing through the directory as a symbolic link. 

As for folder access I want to choose through correct contemplation which users and groups who can read , write, and/or browse these files. 
The owner should have directory permissions such they can read (+4) write (+2) browseExec (+1) goes--> 4+2+1 goes--> 7. 
With "groups": perspective, With group having read (+4) and browseExec(+1) permissions yielding a 5 of 750. 
With "guests": having no directory listing, or reading, or writing permissions yeilding the 0 of 750.
So in the order for cdmod being "owner group guests" number agreed upon to be 750. 

```txt
sudo mkdir /Hexamir/Darktable
 
sudo chmod 750 /Hexamir/Darktable/
sudo chown user:users /Hexamir/Darktable/
man ln 
cd ~/Pictures
ln -s /Hexamir/Darktable/
ls
echo notice that the symlink takes you to other disk.
cd ~/Pictures/Darktable

```

 I like this method, because it enforces the owner is not root mindset. This is a user level program, I want it to process the pictures as user not root.

 to verify that the darktable options have been correctly inserted. I use my terminal to verify the content of the options file, in this case it is like an ini format but it will be interpreted by what seems is bash shell interpreter. 
 
  view this in a text editor at the path of ~/.config/darktable/darktablerc
 
 ```sh
 cat ~/.config/darktable/darktablerc | grep 'session.*pattern' 
 #session/base_directory_pattern=$(PICTURES_FOLDER)/Darktable
 #session/filename_pattern=$(FILE_NAME)-$(SEQUENCE).$(FILE_EXTENSION)
 #session/sub_directory_pattern=Y$(EXIF_YEAR-0000)/M$(EXIF_MONTH-00)/D$(EXIF_DAY-00)/h$(EXIF_HOUR-00)/m$(EXIF_MINUTE-00)/s$(EXIF_SECOND-00)/ISO$(EXIF_ISO)-EXP$(EXIF_EXPOSURE)-BIAS$(EXIF_EXPOSURE_BIAS)-AP$(EXIF_APERTURE)-x$(MAX_WIDTH-0)-y$(MAX_HEIGHT-0)
 
 cat - ~/.config/darktable/darktablerc | grep 'session.*pattern'
 
 ```
 
 
 
