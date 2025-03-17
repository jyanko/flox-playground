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

After running these four commands, a basic rundeck server is up and available at http://localhost:4440 in about 30 seconds.

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

❯ flox services start rundeck
✅ Service 'rundeck' started.


❯ flox services logs rundeck --tail 5
[2025-03-13T12:02:14,636] INFO  rundeckapp.BootStrap [main] - workflowConfigFix973: applying...
[2025-03-13T12:02:14,642] INFO  rundeckapp.BootStrap [main] - workflowConfigFix973: No fix was needed. Storing fix application state.
[2025-03-13T12:02:14,951] INFO  rundeckapp.BootStrap [main] - Rundeck startup finished in 618ms
[2025-03-13T12:02:14,956] INFO  rundeckapp.Application [main] - Started Application in 24.775 seconds (JVM running for 26.796)
Grails application running at http://localhost:4440 in environment: production
```

Stop the rundeck service
```
❯ flox services stop rundeck
✅ Service 'rundeck' stopped

❯ flox services logs rundeck --tail 5
[2025-03-13T12:02:14,642] INFO  rundeckapp.BootStrap [main] - workflowConfigFix973: No fix was needed. Storing fix application state.
[2025-03-13T12:02:14,951] INFO  rundeckapp.BootStrap [main] - Rundeck startup finished in 618ms
[2025-03-13T12:02:14,956] INFO  rundeckapp.Application [main] - Started Application in 24.775 seconds (JVM running for 26.796)
Grails application running at http://localhost:4440 in environment: production
[2025-03-13T12:04:48,429] INFO  rundeckapp.BootStrap [SpringApplicationShutdownHook] - Rundeck Shutdown detected
```

See what package versions it installed
```
❯ flox list
gum: gum (0.14.5)
openjdk11: openjdk11 (11.0.24)
rundeck: rundeck (5.9.0-20250205)
```


