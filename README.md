# Criando uma aplicação Quarkus

PoC de uma aplicação simples utilizando Quarkus

## Inicializando um novo projeto em Quarkus

`mvn io.quarkus:quarkus-maven-plugin:1.9.0.Final:create`

## Compilando o projeto local

`mvn compile`

## Rodando o projeto local pela command line

`mvn quarkus:dev`

```
[INFO] Scanning for projects...
[INFO]
[INFO] ------------------< com.quarkus.sample:user-service >-------------------
[INFO] Building user-service 1.0-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- quarkus-maven-plugin:1.9.2.Final:dev (default-cli) @ user-service ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 2 resources
[INFO] Nothing to compile - all classes are up to date
Listening for transport dt_socket at address: 5005
__  ____  __  _____   ___  __ ____  ______
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/
 -/ /_/ / /_/ / __ |/ , _/ ,< / /_/ /\ \
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/
2020-11-22 14:28:30,047 INFO  [io.quarkus] (Quarkus Main Thread) user-service 1.0-SNAPSHOT on JVM (powered by Quarkus 1.9.2.Final) started in 1.345s. Listening on: http://0.0.0.0:8080
2020-11-22 14:28:30,062 INFO  [io.quarkus] (Quarkus Main Thread) Profile dev activated. Live Coding activated.
2020-11-22 14:28:30,062 INFO  [io.quarkus] (Quarkus Main Thread) Installed features: [cdi, resteasy]

```

## Compilando o projeto com OS nativo

`mvn clean compile package -Pnative`

Esse comando irá criar o arquivo runner com o nome **user-service-1.0-SNAPSHOT-runner**

## Rodando o projeto nativo

`./user-service/target/user-service-1.0-SNAPSHOT-runner`

```
__  ____  __  _____   ___  __ ____  ______
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/
 -/ /_/ / /_/ / __ |/ , _/ ,< / /_/ /\ \
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/
2020-11-22 14:20:27,518 INFO  [io.quarkus] (main) user-service 1.0-SNAPSHOT native (powered by Quarkus 1.9.2.Final) started in 0.083s. Listening on: http://0.0.0.0:8080
2020-11-22 14:20:27,519 INFO  [io.quarkus] (main) Profile prod activated.
2020-11-22 14:20:27,519 INFO  [io.quarkus] (main) Installed features: [cdi, resteasy]
```

## Testando o funcionamento do serviço

`curl http://localhost:8080/user`

```
Response status 200:

hello world!
```
