# hi-cicd 
hi-cicd is a hi-cli module for continuous integration and delivery based on Openshift

# Installation guide

* Install [hi-cli](https://github.com/hi-cli/hi-cli), please add sudo at the beginning of below installation commands if you are not root.
```
bash -c "$(curl -fsSL https://raw.githubusercontent.com/hi-cli/hi-cli/master/bin/install/init)"
```
* Install hi-cicd
```bash
hi install cicd
```

# Usage

Please make sure that openshift client [oc](https://github.com/openshift/origin/releases) is installed on your bash (or git bash). 

type oc version to confirm if oc is installed.
```bash
oc version
```

If you are using zsh, you can install [oc command completion](https://github.com/chmouel/oh-my-zsh-openshift)

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
