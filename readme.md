This repository contains the libraries and build steps required due to the JCenter repository decommissioning.

# me.dm7.barcodescanner:zxing:1.19.13
1. Clone `git@github.com:dm77/barcodescanner.git`
1. Copy source at v1.19.13 commit 8d5d347 to projects folder.
1. Set JAVA_HOME to JDK 11. My local example: `export JAVA_HOME="/Users/dhuff/Library/Java/JavaVirtualMachines/corretto-11.0.24/Contents/Home"`
1. `./gradlew build`
1. Copy ./[core|zbar|xzing]/build/outputs/aar/[core|zbar|xzing]-release.aar to common libs location.
