# adobegarbage
notes and procedures and scripts on working through the HELL that is adobe installers

here's the wrong way to import all installers sequentially into Munki after downloading, putting into a common directory, and CRITICALLY unquarantining with `xattrs -c -r`

```OIFS=$IFS;IFS=$'\n';for file in `find Downloads/adobe -name "*_Install.pkg"`; do; echo "file = $file"; munkiimport --unattended_install --unattended_uninstall -c testing --developer="Adobe" $file; done;IFS=$OIFS```
this could use a lot of tweaking...

credit to https://macosxbytes.wordpress.com/2021/02/10/multiple-adobe-package-downloader-app-runs-and-big-sur/ on a trick to change the User Agent of a browser to avoid the stupid single-stream Adobe Downloader
`Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_6) AppleWebKit/601.7.8 (KHTML, like Gecko) Version/10.1.1 Safari/603.2.5`
