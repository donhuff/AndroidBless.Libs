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
1. Perform shadow build.
1. `./gradlew :generated:anko-sdk21:build`
1. Copy `anko/library/generated/sdk21/build/outputs/aar/anko-sdk21-release.aar` to `libs/com.github.Kotlin.anko/sdk21/v0.10.8`
1. `./gradlew :generated:anko-commons:build`
1. Copy `anko/library/generated/commons/build/outputs/aar/anko-commons-release.aar` to `libs/com.github.Kotlin.anko-v0.10.8`

## com.github.jengelman.gradle.plugins:shadow:2.0.4
1. Clone `git@github.com:GradleUp/shadow.git`
1. Copy source at tag: 2.0.4, commit: 477db403 to projects folder.
1. Switch to Java 8. Sample: `export JAVA_HOME="/Users/dhuff/Library/Java/JavaVirtualMachines/corretto-1.8.0_422/Contents/Home"`
1. Perform asciidoctorj-groovy-dsl build.
1. `./gradlew build` to build and test. Verify tests pass.
1. Copy `build/libs/*.jar` to `../anko/libs`

### org.asciidoctor:asciidoctorj-groovy-dsl:1.0.0.preview2
These steps are performed to build `shadow`.
1. Clone `git@github.com:asciidoctor/asciidoctorj-groovy-dsl.git`
1. Copy source at tag: 1.0.0.preview2, commit: b18abb1 to projects folder.
1. `./gradlew tasks assemble`
1. Copy ./build/libs/asciidoctorj-groovy-dsl.jar
