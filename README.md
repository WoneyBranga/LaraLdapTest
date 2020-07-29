# Simulacao implementacao Lara + Ldap

Etapas: 

1- Install Lara
    `$ composer create-project --prefer-dist laravel/laravel teste`
2- Ajustar Permissao da estrutura de diretorios
    Mais em https://laravel.com/docs/7.x/installation#configuration.
    Alterar permissões da árvore de diretórios storage e bootstrap/cache
```bash
touch storage/logs/laravel.log
chmod -R 0777 storage bootstrap/cache
```
3- Geração da UI
```bash
$ composer require laravel/ui
$ php artisan ui bootstrap --auth
$ npm install && npm run dev
```

4- Adequar tabela de usuários

Adequar a tabela o arquivo de migrate da tabela de usuários original para atender as necessidades do sistema. Normalmente inclui-se a coluna username.
No exemplo abaixo criamos a coluna username e a colocamos como unique, as colunas gerencia_id, equipe_id e ativo, as primeiras com possibilidade de ser nulas e a segunda com o valor padrão verdadeiro.

`php artisan migrate`

5- Adequar o controller de login
Alterar o arquivo /var/www/teste/app/Http/Controllers/Auth/LoginController.php para identificar o campo username ao invés do email.

6- Adequar a página de login
Alterar o arquivo /var/www/teste/resources/views/auth/login.blade.php para usar o username no lugar de email.

7- Validar credenciais no LDAP
Para possibilitar a validação de login no Active Directory ALVO, alterar o método validateCredentials de ./vendor/laravel/framework/src/Illuminate/Auth/EloquentUserProvider.php