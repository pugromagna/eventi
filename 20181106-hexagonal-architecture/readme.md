Hexagonal Architecture refactoring
=====

# Slide
https://matiux.github.io/slides/hexagonal-architecture

# Codice di esempio
Basandomi sul libro *Domain-Driven Design in PHP*, mostro un processo di refactoring da spaghetti code a organizzazione del codice tramite l'architettura esagonale

L'architettura esagonale consente a un'applicazione di essere ugualmente guidata da utenti, programmi, test automatizzati o script batch e di essere sviluppata e testata separatamente dai suoi eventuali dispositivi e database.

### Scaricare il progetto
`git clone https://github.com/matiux/hexagonal-architecture.git`

### Docker
`dc` è una scorciatoia per `docker-compose`
```
./dc up -d (docker-compose up -d)
./dc enter (docker-compose exec -u utente php /bin/zsh)
./dc down -v --rmi=all (docker-compose down -v --rmi=all)
```

#### Database MySql
```
Adminer: localhost:8081
Host dentro al container: servicedb:3306
Host fuori dal container: 127.0.0.1:3307
Utente: user
Password: password
```
#### Preparare il database per far girare gli esempi
```
./dc enter
composer install
php src/build.php
```

#### Da eseguire all'interno del container

I primi 3 step di refactoring
```
./dc enter
php src/Step01/client.php
php src/Step02/client.php
php src/Step03/client.php
```
Step finale con implementazione con vari delivery e test
```
php src/Step04/client.php
php src/Step04/console app:create-idea 'Flying pig' Matiux
vendor/bin/phpunit
```
