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

# Download [Openshift Client Tools](https://github.com/openshift/origin/releases)

Download openshift client tools according to your OS, then extract the file 'oc' ('oc.exe') to /usr/bin/

* [openshift-origin-client-tools-v1.5.1-7b451fc-linux-32bit.tar.gz](https://github.com/openshift/origin/releases/download/v1.5.1/openshift-origin-client-tools-v1.5.1-7b451fc-linux-32bit.tar.gz)
* [openshift-origin-client-tools-v1.5.1-7b451fc-linux-64bit.tar.gz](https://github.com/openshift/origin/releases/download/v1.5.1/openshift-origin-client-tools-v1.5.1-7b451fc-linux-64bit.tar.gz)
* [openshift-origin-client-tools-v1.5.1-7b451fc-mac.zip](https://github.com/openshift/origin/releases/download/v1.5.1/openshift-origin-client-tools-v1.5.1-7b451fc-mac.zip)
* [openshift-origin-client-tools-v1.5.1-7b451fc-windows.zip](https://github.com/openshift/origin/releases/download/v1.5.1/openshift-origin-client-tools-v1.5.1-7b451fc-windows.zip)

#### For Chinese users, please download it from [here](http://pan.baidu.com/s/1jHFadoy)

# Usage

Please make sure that openshift client [oc](https://github.com/openshift/origin/releases) is installed on your bash (or git bash). 

type oc version to confirm if oc is installed.
```bash
oc version
```

If you are using zsh, you can install [oc command completion](https://github.com/chmouel/oh-my-zsh-openshift)

* login openshift
```bash
oc login
```

* make a directory that host your app
```bash
mkdir my-project
cd my-project
```

* Clone the source code
```
git clone git@github.com:my-project/my-app.git
```

* switch to your working directory, make sure your working directory is my-project/my-app/ (type pwd to check)
```bash
cd my-app
```

* Init hi-cli
```bash
hi init
``` 

* Deploy java / nodejs new app to my-project-dev
```
hi cicd deploy new
```

* Deploy java / nodejs app to my-project-stage using my-project/my-app:dev image stream
```bash
hi cicd deploy profile=stage
```

* hi cicd deploy command options
```bash
new:
    deploy as new application

profile:
    dev, test, stage, prod

    # default value is dev

    # e.g.: hi cicd deploy new profile=stage

image_stream:
    s2i-java, s2i-nodejs, s2i-nodejs:6.9.5

timezone:
    Asia/Shanghai is the default value

images_profile:
    dev, stage

    # default value is dev

postfix:
    [a-z] # used for blue-green deployment
    
    # default value is null

    # e.g. hi cicd deploy new build postfix=blue
```

