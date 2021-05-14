# Instrukcja uruchomienia

## Wymagania systemowe

1. Binarka `symfony` - https://symfony.com/download
   > Technicznie rzecz biorąc nie jest to wymagane ale dla wersji 5 symfony jest to najszybsza i chyba najprostsza
   > możliwość uruchomienia projektu.
2. PHP w wersji >=7.2.5
3. composer - https://getcomposer.org/
4. yarn - https://yarnpkg.com/
5. git

## Uruchomienie

1. Sklonowanie repozytorium

   `git clone https://github.com/jerzy-dudzic/saleson_test.git`
2. `cd saleson_test`
3. `composer install`
4. `yarn install`
5. `yarn run dev`
6. `symfony server:start`
7. `symfony console doctrine:database:create`
   > To nie powinno być konieczne. Trzeba jednak odpalić jakby występowały błędy z błędnie skonfigurowaną bazą danych

## Uruchomienie - docker

1. `git clone https://github.com/jerzy-dudzic/saleson_test.git`
2. `cd saleson_test`
3. `sudo docker-compose up`
4. W innej konsoli: `sudo docker exec -it demo-php bash`
5. Po otworzeniu się basha w nowootwartej konsoli: `composer install && yarn install && yarn run dev`
6. Strona jest dostępna pod adresem: http://localhost:9876/ 