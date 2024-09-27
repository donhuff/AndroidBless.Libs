This repository contains the libraries and build steps required due to the JCenter repository decommissioning.

# me.dm7.barcodescanner:zxing:1.19.13
1. Clone `git@github.com:dm77/barcodescanner.git`
1. Copy source at v1.19.13 commit 8d5d347 to projects folder.
1. Set JAVA_HOME to JDK 11. My local example: `export JAVA_HOME="/Users/dhuff/Library/Java/JavaVirtualMachines/corretto-11.0.24/Contents/Home"`
1. `./gradlew build`
1. Copy ./[core|zbar|xzing]/build/outputs/aar/[core|zbar|xzing]-release.aar to common libs location.

# com.github.Kotlin.anko:sdk21:v0.10.8
1. Clone `git@github.com:Kotlin/anko.git`
1. Copy source at tag: v0.10.8, commit: e12c5cb to projects folder.

## com.github.jengelman.gradle.plugins:shadow:2.0.4
1. Clone `git@github.com:GradleUp/shadow.git`
1. Copy source at tag: 2.0.4, commit: 477db403 to projects folder.
1. Switch to Java 8. Sample: `export JAVA_HOME="/Users/dhuff/Library/Java/JavaVirtualMachines/corretto-1.8.0_422/Contents/Home"`
