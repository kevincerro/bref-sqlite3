# Bref SQLite3

## SQLite3 binary
`sqlite3 --version`

3.46.0 2024-05-23 13:25:27 96c92aba00c8375bc32fafcdf12429c58bd8aabfcadab6683e35bbb9cdebf19e (64-bit)

## pdo_sqlite or sqlite3 from php

`php -r 'echo "SQLite version: " . SQLite3::version()["versionString"] . PHP_EOL;`

SQLite version: 3.7.17

## PHPUnit tests with old SQLite version

`vendor/phpunit/phpunit/phpunit --testdox`

Doctrine\DBAL\Exception\SyntaxErrorException: An exception occurred while executing a query: SQLSTATE[HY000]: General error: 1 near "(": syntax error
