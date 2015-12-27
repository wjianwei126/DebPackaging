# DebPackaging
Deb Packaging about bcloud

# Bcloud

I do all the instructions from https://wiki.debian.org/IntroDebianPackaging.

## The packaging work flow

The packaging work flow is usually like this:

### Rename the upstream tarball

    git clone https://github.com/LiuLang/bcloud
    tar -zcvf bcloud_3.8.2.tar.gz bcloud/
    mv bcloud_3.8.2.tar.gz bcloud_3.8.2.orig.tar.gz

### Unpack the upstream tarball

    tar -xvf bcloud_3.8.2.orig.tar.gz
    
    
### Add the Debian packaging files

Add files in bcloud/debian/.

### Build the package

    debuild -us -uc

### Install the package
    
    sudo dpkg -i bcloud_3.8.2-1_all.deb
    
Then you can test your package on your computer.

## Errors and Warnings

```
Now running lintian...
W: bcloud source: changelog-should-mention-nmu
W: bcloud source: source-nmu-has-incorrect-version-number 3.8.2-1
W: bcloud source: missing-license-paragraph-in-dep5-copyright gplv3 (paragraph at line 5)
W: bcloud source: invalid-short-name-in-dep5-copyright gplv3 (paragraph at line 5)
W: bcloud: new-package-should-close-itp-bug
W: bcloud: duplicate-changelog-files usr/share/doc/bcloud/HISTORY.gz usr/share/doc/bcloud/changelog.gz
W: bcloud: extra-license-file usr/share/doc/bcloud/LICENSE.gz
W: bcloud: binary-without-manpage usr/bin/bcloud-gui
Finished running lintian.
```
