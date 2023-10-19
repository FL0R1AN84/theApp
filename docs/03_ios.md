# iOS Development

## General infos for local development

For the first build (includes livereload) on local simulator devices

```bash
npm run build
```

### Requirements

- Ruby 3.2.2

```bash
brew install rbenv ruby-build
```

.zshrc

```text
# Ruby environment
eval "$(rbenv init - zsh)"
```

```bash
rbenv install 3.2.2
```

```bash
rbenv global 3.2.2
```

- CocoaPods

```bash
brew install cocoapods
```

```bash
npm install @capacitor/ios
```

```bash
npx cap add ios
```

### Device simulator

```bash
npx cap run ios
```

[back to Index](../README.md)
