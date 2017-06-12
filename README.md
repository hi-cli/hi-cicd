# hi-cicd 
hi-cicd is a hi-cli module for continuous integration and delivery based on Openshift

# Installation guide

* Install [hi-cli](https://github.com/hi-cli/hi-cli), please add sudo at the beginning of below installation commands if you are not root.
```
bash -c "$(curl -fsSL https://raw.githubusercontent.com/hi-cli/hi-cli/master/bin/install)"
```
* Install hi-cicd
```bash
hi package install cicd
```

# Usage

Please make sure you are install openshift client: [oc](https://github.com/openshift/origin/releases)

If you are using zsh, you can install [oc command completion](https://github.com/chmouel/oh-my-zsh-openshift)

* login openshift
```bash
oc login
```

* Switch to your project
```bash
oc project your-project
```

* switch to your working directory
```bash
cd your-app
```

* Init hi-cli
```bash
hi init
``` 

* Deploy java / nodejs new app to your-project-dev
```
hi cicd deploy new profile=dev
```

* Update java / nodejs app to your-project-dev
```
hi cicd deploy profile=dev
```

    hi: hi-cli
    cicd: hi-cicd 
    deploy: deploy command
    new: deploy as new application, if you d
    profile: dev, test, stage, prod

