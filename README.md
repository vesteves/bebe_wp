# bebe_wp
Recordações de meu bebê
Pai: Vitor Esteves
Mãe: Carol Martins


PASSOS para configurar o ambiente:
1- a2enmod rewrite
2- Alterar o .htaccess
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteBase /
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule . /index.php [L]
</IfModule>
3- sudo nano /etc/apache2/apache2.conf
4- Control W e procurar por <Directory /var/www/>
5- Alterar para AllowOverride All
6- service apache2 restart
7- Copiar o wp-config-sample.php para wp-config.php
8- Alterar com as informações da conexão com o banco

PASSOS para configurar o banco:
1- SELECT * FROM wp_options WHERE option_value LIKE "%http://%";
2- Alterar os 2 primeiros links.
3- UPDATE wp_posts SET guid = REPLACE(guid, 'VELHO/', 'NOVO/');
4- UPDATE wp_posts SET post_content = REPLACE(post_content,'http://VELHO/','http://NOVO/');
