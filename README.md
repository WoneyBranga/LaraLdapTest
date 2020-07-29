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

4- Adequar tabela de usu�rios

Adequar a tabela o arquivo de migrate da tabela de usu�rios original para atender as necessidades do sistema. Normalmente inclui-se a coluna username.
No exemplo abaixo criamos a coluna username e a colocamos como unique, as colunas gerencia_id, equipe_id e ativo, as primeiras com possibilidade de ser nulas e a segunda com o valor padr�o verdadeiro.