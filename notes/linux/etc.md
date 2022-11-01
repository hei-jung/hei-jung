## how to convert `*.7z` to `*.zip`

```shell
#!/bin/bash

TMPDIR=tempdir_$$

for x in `ls *.7z`; do
    mkdir $TMPDIR
    cd $TMPDIR
    cp ../$x .
    p7zip -d $x
    zip -r ../${x%.7z}.zip *
    cd ..
    rm -rf $TMPDIR    
done
```

comment: You don't need for x in `ls *.7z`;. You can simply do: for x in *.7z;. Bonus: the second version will correctly handle filenames with spaces, while the first one wont. 

[출처](https://superuser.com/questions/1115548/repack-7z-files-to-zip-files-in-linux)
