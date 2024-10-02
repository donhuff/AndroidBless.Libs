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
1. Build:
  1. `./gradlew :generated:anko-sdk21:build`
  1. `./gradlew :generated:anko-commons:build`
  1. `./gradlew generated:anko-appcompat-v7:build`
  1. `./gradlew generated:anko-support-v4:build`
  1. ./gradlew generated:anko-support-v4-commons:build
1. Copy `anko/library/generated/{library}/build/outputs/aar/anko-{library}-release.aar` to `libs/com.github.Kotlin.anko/v0.10.8`

1. Build: `./gradlew generated:anko:buildNeeded`

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
1. `./gradlew assemble`
1. Copy ./build/libs/asciidoctorj-groovy-dsl.jar

# QuickPermissions-Kotlin:0.4.1
1. Clone `git@github.com:QuickPermissions/QuickPermissions-Kotlin.git`
1. Copy source at tag: 0.4.1, commit: 98e176a to projects folder `projects/QuickPermissions-Kotlin`.
1. Build com.github.Kotlin.anko:commons:v0.10.5 to populate `projects/QuickPermissions-Kotlin/libs` folder.
1. `./gradlew quickpermissions-kotlin:assemble` Note: Do not need to build the `app` project
1. Copy `projects/QuickPermissions-Kotlin/quickpermissions-kotlin/build/outputs/aar/quickpermissions-kotlin-release.aar` to `libs/QuickPermissions-Kotlin-0.4.1` folder.

## com.github.Kotlin.anko:commons:v0.10.5
Anko-commons:v0.10.5 is required by QuickPermissions. Anko-commons:v0.10.8 does _not_ work here.

1. Clone `git@github.com:Kotlin/anko.git`
1. Copy source at tag: v0.10.5, commit: 0f99e9f to projects folder `projects/anko-0.10.5`.
1. Set `sdk.dir=/{your path}/Library/Android/sdk` in `projects/anko-0.10.5/local.properties'.
1. `./gradlew :generated:anko-commons:build`
1. Copy `projects/anko-0.10.5/anko/library/generated/commons/build/outputs/aar/anko-commons-release.aar` to `projects/QuickPermissions-Kotlin/libs` folder

# Koin 2.0.1
1. Clone `git@github.com:InsertKoinIO/koin.git`
1. Copy source at tag: 2.0.1, commit: 12e06086 to projects folder `projects/koin`.
1. `cd projects/koin/koin-projects`
1. Builds:
    1. `./gradlew koin-android:bundleReleaseAar`
    1. `./gradlew koin-android-scope:bundleReleaseAar`
    1. `./gradlew koin-android-viewmodel:bundleReleaseAar`
    1. `./gradlew koin-androidx-viewmodel:bundleReleaseAar`
    1. `./gradlew koin-core:assemble`
1. Copy built aar and jar files to `libs/koin/2.0.1` folder.
    1. koin-android-release.aar
    1. koin-android-scope-release.aar
    1. koin-android-viewmodel-release.aar
    1. koin-androidx-viewmodel-release.aar
    1. koin-core-2.0.1-javadoc.jar
    1. koin-core-2.0.1-sources.jar
    1. koin-core-2.0.1.jar
