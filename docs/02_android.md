## General infos for local development

For the first build (includes livereload) on local simulator devices

```console
npm run build
```

### Requirements

```console
npm install @capacitor/android
```

```console
npx cap add android
```

- Java max. Version 20
  - Currently, you cannot run Gradle on Java 21 because Kotlin lacks support for JDK 21. However, support for running Gradle with Java 21 is expected in future versions.
  - Java version can be changed in Android Studio ->[read more](04_java.md)
- Android Studio

```console
brew install --cask android-studio
```

.zshrc

```zsh
# Android SDK
alias adb="/Users/$USER/Library/Android/sdk/platform-tools/./adb"
export ANDROID_SDK_ROOT="/Users/$USER/Library/Android/sdk"
export PATH=$PATH:$ANDROID_SDK_ROOT/emulator/
export PATH=$PATH:$ANDROID_SDK_ROOT/cmdline-tools/latest/bin/
export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools/
export JAVA_HOME=/Applications/Android\ Studio.app/Contents/jbr/Contents/Home
```

### Device simulator

```console
npx cap run android
```

[back to Index](../README.md)
