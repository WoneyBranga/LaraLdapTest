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