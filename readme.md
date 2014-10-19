this will build slimrom for ville

"" are to show what to type in terminal, you dont include the ""

start by opening terminal and type  "mkdir slim"
"cd slim"
"repo init -u git://github.com/SlimRoms/platform_manifest.git -b kk4.4-caf"
"cd .repo"
"git clone https://github.com/SlimRoms/platform_manifest local_manifest"
"cd ~/slim"
"repo sync"
when thats done, takes forever, first we build 2.15 hboot

". build/envsetup.sh && time brunch ville" you can add -j# where #=twice your cpu core count ex. i have i7 quadcore so i would do "time brunch ville -j8"

once that is done we can build 2.16 support

rename the out/target/product/ville folder to ville215, you can do this in terminal "cd ~/slim && mv out/target/product/ville out/target/product/ville215"

now cd "~/slim/device/htc/ville && git checkout kk4.4-216 && cd ~/slim && time brunch ville"

now youll have two folders in out/target/product ville215 and ville the ville one will be for 2.16 hboot
