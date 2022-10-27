# FakeBBB

sudo -s
apt install apache2
cd /var/www/html
rm index.html
git clone https://github.com/superexroid/FakeBBB.git .
nano /etc/apache2/apache2.conf
*******
<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>

to

<Directory /var/www/>
        Options FollowSymLinks
        AllowOverride All
        Require all granted
</Directory>
*******
service apache2 reload
nano /etc/apache2/conf-enabled/security.conf

change ServerTokens OS to ServerTokens Prod
change ServerSignature On to ServerSignature Off

sudo service apache2 restart
