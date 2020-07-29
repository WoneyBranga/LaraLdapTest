# Simulacao implementacao Lara + Ldap

Etapas: 

1- Install Lara
    `$ composer create-project --prefer-dist laravel/laravel teste`
2- Ajustar Permissao da estrutura de diretorios
    Mais em https://laravel.com/docs/7.x/installation#configuration.
    Alterar permiss�es da �rvore de diret�rios storage e bootstrap/cache
```bash
touch storage/logs/laravel.log
chmod -R 0777 storage bootstrap/cache
```
3- Gera��o da UI
```bash
$ composer require laravel/ui
$ php artisan ui bootstrap --auth
$ npm install && npm run dev
```