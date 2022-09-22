# Backup [10-sep-2022]
# Backup version - v5

## Combinations:
- read the `hints` provided.
- use the shared password manager to obtain the password.
- follow the steps and correct sequence.
- for key files, open using text editor or use terminal:
```
cat kesy/KEY_FILE
```
- generate the md5 using : 
```
md5sum images/FILE_NAME
```

## content generation process:

### images : 

- convert all the files to jpg/jpeg.
```
mogrify -format jpg *.png
```
- strip metadata:
``` 
for i in *; do exiftool -all= $i ; done
```
- remove original files:
```
rm *.*_original
```
- optimize the image files:
```
for i in *; do jpegoptim "$i" ; done

```

### keys :
- generate random content of 32 characters as key files:
```
for i in {1..2}; do LC_ALL=C tr -dc 'A-Za-z0-9!"#$%&'\''()*+,-./:;<=>?@[\]^_`{|}~' </dev/urandom | head -c 32  > $i.key; done
```

### obtain the key content:



### tools
- mogrify
- exiftool
- jpegoptim

![alt text](https://raw.githubusercontent.com/recovery-keys/sep2022/sep2022/sep-2022_flow.drawio.png)