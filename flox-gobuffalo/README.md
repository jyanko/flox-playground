## flox-gobuffalo

Simple demonstration of fresh clone of git repo to a stood up vanilla gobuffalo dev env in 4 commands. 

- Sets up a go dev env
  - installs buffalo, soda, yarn, nodejs
  - sets up several env vars ie: GOPATH, GOBIN, GOENV, etc
  - sets up usefual shell aliases
- Buffalo Docs
  - [buffalo](https://gobuffalo.io/)
  - [buffalo: getting started](https://gobuffalo.io/documentation/getting_started/installation/) (gobuffalo:buffalo)
  - [gobuffalo/buffalo](https://github.com/gobuffalo/buffalo) :octocat:
  - [gobuffalo/pop/soda](https://github.com/gobuffalo/pop/tree/main/soda) :octocat:

After running these first four commands, a go dev env will be up and available in about 30 seconds.

**Clone repo and activate flox env**
```
❯ git clone git@github.com:jyanko/flox-playground.git

❯ cd flox-playground/flox-gobuffalo
  
❯ flox activate
✅ You are now using the environment 'flox-gobuffalo'.
To stop using this environment, type 'exit'
...
Installing Buffalo v0.18.14...
go: downloading github.com/gobuffalo/cli v0.18.14
go: downloading github.com/sirupsen/logrus v1.9.0
...
Installing buffalo pop (soda) latest...
go: downloading github.com/gobuffalo/pop v4.13.1+incompatible
go: downloading github.com/fatih/color v1.13.0
...                                                                                    
  ╔════════════════════════════════════════════════════════════════════════════════╗  
  ║                                                                                ║  
  ║                   FLOX :: Env Active: flox-gobuffalo                           ║  
  ║                                                                                ║  
  ╚════════════════════════════════════════════════════════════════════════════════╝  

go     : 1.24.6
yarn   : 0.18.14
buffalo: 0.18.14
node   : 22.18.0
nvm    : 0.40.3
flox   : 1.7.1
```

Using the floxEnv alias to view env info
```
❯ floxEnv
go     : 1.24.6
yarn   : 0.18.14
buffalo: 0.18.14
node   : 22.18.0
nvm    : 0.40.3
flox   : 1.7.1
GOBIN='~/GITCHECKOUT/flox-playground/flox-gobuffalo/go_temp/bin'
GOENV='~/GITCHECKOUT/flox-playground/flox-gobuffalo/go_temp/cache/goenv'
GOMOD='/dev/null'
GOMODCACHE='~/GITCHECKOUT/flox-playground/flox-gobuffalo/go_temp/pkg/mod'
GOPATH='~/GITCHECKOUT/flox-playground/flox-gobuffalo/go_temp'
GOPROXY='https://proxy.golang.org,direct'
GOROOT='/nix/store/rgmygksbfyy75iappxpinv0y8lxfq35x-go-1.24.6/share/go'
GOVERSION='go1.24.6'
FLOX_ENV          ~/GITCHECKOUT/flox-playground/flox-gobuffalo/.flox/run/aarch64-darwin.flox-gobuffalo.dev
FLOX_CONFIG_DIR   ~/.config/flox
FLOX_ENV_PROJECT  ~/GITCHECKOUT/flox-playground/flox-gobuffalo
```
Use buffalo to create a new buffalo framework app
- this will create a new app and try starting it
- app won't fully work yet as this demo does not perform db migrations or other config
- webserver will return at http://localhost:3000 ... error page will be seen at this point
```
buffalo new <mynewapp>
cd mynewapp
buffalo dev
```