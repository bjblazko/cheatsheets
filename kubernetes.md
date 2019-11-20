# Installation

## Development (local)

### Minicube

See: https://minikube.sigs.k8s.io/docs/start/macos/

#### Install

Installs Minikube via Homebrew and sets Virtualbox as the default driver:

```bash
brew install minikube
minikube config set vm-driver virtualbox
```

Make sure that Virtualbox is installed and up to date.

#### Update

```bash
brew update
brew upgrade minikube
```

#### Basic operations

##### Start cluster

```bash
minikube start
```

##### Run dashboard

```bash
minikube Dashboard
```
