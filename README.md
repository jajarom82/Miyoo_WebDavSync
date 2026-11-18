# Miyoo_WebDavSync
A small script used to synchronize a folder on the Miyoo (mini, mini+, etc) with a WebDav folder (in my case a folder in my OwnCloud server).
* Interactive: in case of conflict it asks what to do (and you can apply same answer for all).
* English or french (install the right script for you)

## Installation
* Unzip all the files to the root of your SD card
* edit App/WebDavSync/config.conf and set your server + folder (SERVER), the credentials (AUTH, in the form "account:password"), the local dir to which you want to sync, and your filetypes (space-separated)
* keep only launch_fr.sh (french) or launch_en.sh (english), and rename it to launch.sh

## Config Example:
SERVER="https://my-server.fr/remote.php/dav/files/my_account/books"  
AUTH="my_account:Uber_pazzw0rd"  
LOCALDIR="/mnt/SDCARD/Media/Books"  
INSECURE="1"  
FILETYPES="epub pdf"  

"Insercure" means that the certificate will not be verified. If you want to activate certificate check:
* download  https://curl.se/ca/cacert.pem, put it in same directory as the script
* set INSECURE="0"
* set CACERT="/mnt/SDCARD/App/WebDavSync/cacert.pem"
* You will have to periodically (once a year or every 2 years) update this cert file, this is why it make no sense to have it included in this repository, and I prefer not to activate it by default so that you can have a working solution out of the box.
