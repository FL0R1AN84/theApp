# iOS Development

## General infos for local development

For the first build (includes livereload) on local simulator devices

```console
npm run build
```

### Requirements

- Ruby 3.2.2

```console
brew install rbenv ruby-build
```

.zshrc

```zsh
# Ruby environment
eval "$(rbenv init - zsh)"
```

```console
rbenv install 3.2.2
```

```console
rbenv global 3.2.2
```

- CocoaPods

```console
brew install cocoapods
```

```console
npm install @capacitor/ios
```

```console
npx cap add ios
```

### Device simulator

```console
npx cap run ios
```

[back to Index](../README.md)
