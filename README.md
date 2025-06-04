# flox-playground
```
❯ tree -L 1
.
├── README.md
└── flox-rundeck
```

## prerequisites 
Must have `flox` installed to your system to use the following methods to activate a dev environment

Flox may be installed in several ways depending on the system you are running (ie: dpkg, rpm, homebrew, etc...)

Reference:
- https://flox.dev
- https://flox.dev/docs/install-flox/
  

## flox-rundeck

Simple demonstration of fresh clone of git repo to a stood up vanilla rundeck server in 4 commands. 

- This starts up rundeck locally
  - with default user/pass
  - with local h2 db - not suitable for prod use
  - use this method for dev/testing only
- Rundeck Docs
  - [Getting Started](https://docs.rundeck.com/docs/learning/getting-started)
  - [Administrator Guide](https://docs.rundeck.com/docs/administration)

After running these first four commands, a basic rundeck server is up and available at http://localhost:4440 in about 30 seconds.

**Clone repo and activate flox env**
```
❯ git clone git@github.com:jyanko/flox-playground.git

❯ cd flox-playground/flox-rundeck
  
❯ flox activate
✅ You are now using the environment 'flox-rundeck'.
To stop using this environment, type 'exit'

  ╔══════════════════════════════════════════════════╗
  ║                                                  ║
  ║                                                  ║
  ║            It's gettin' Flox in here             ║
  ║                                                  ║
  ║                                                  ║
  ╚══════════════════════════════════════════════════╝
```

**Start the rundeck service**
```
❯ flox services start rundeck
✅ Service 'rundeck' started.

```

**View services status**
```
❯ flox services status
NAME       STATUS       PID
rundeck    Running    39992
```

**Stop the rundeck service**
```
❯ flox services stop rundeck
✅ Service 'rundeck' stopped

```

**Monitor console log after service is started**
```
❯ flox services logs rundeck --tail 5
[2025-03-13T12:02:14,636] INFO  rundeckapp.BootStrap [main] - workflowConfigFix973: applying...
[2025-03-13T12:02:14,642] INFO  rundeckapp.BootStrap [main] - workflowConfigFix973: No fix was needed. Storing fix application state.
[2025-03-13T12:02:14,951] INFO  rundeckapp.BootStrap [main] - Rundeck startup finished in 618ms
[2025-03-13T12:02:14,956] INFO  rundeckapp.Application [main] - Started Application in 24.775 seconds (JVM running for 26.796)
Grails application running at http://localhost:4440 in environment: production

❯ flox services logs --follow rundeck
rundeck: [2025-06-04T11:11:16,934] INFO  rundeckapp.Application [main] - The following 1 profile is active: "production"
rundeck: [2025-06-04T11:11:38,168] INFO  liquibase.database [main] - Set default schema name to PUBLIC
rundeck: [2025-06-04T11:11:38,270] INFO  liquibase.lockservice [main] - Successfully acquired change log lock
rundeck: [2025-06-04T11:11:40,094] INFO  liquibase.changelog [main] - Reading from PUBLIC.DATABASECHANGELOG
rundeck: [2025-06-04T11:11:40,163] INFO  liquibase.servicelocator [main] - Cannot load service: liquibase.hub.HubService: Provider liquibase.hub.core.StandardHubService could not be instantiated
...
```
**See what package versions flox installed**
```
❯ flox list
gum: gum (0.14.5)
openjdk11: openjdk11 (11.0.24)
rundeck: rundeck (5.9.0-20250205)
```


