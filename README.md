# magento
confs - tips and trick for magento 2.X


Tricks:
# mysql conf
vim app/etc/env.php  
# get details from that file:
grep dbname -A2 -B1 public_html/app/etc/env.php 
# baseurl SSL only
UPDATE core_config_data SET value = 'http://www.example.com/' WHERE path LIKE 'web/unsecure/base_url';
UPDATE core_config_data SET value = 'https://www.example.com/' WHERE path LIKE 'web/secure/base_url';
UPDATE core_config_data SET value = '1' WHERE path LIKE 'web/secure/use_in_adminhtml';
UPDATE core_config_data SET value = '1' WHERE path LIKE 'web/secure/use_in_frontend';
# packages:
apt-get install php7.0-intl php7.0-xsl php7.0-mbstring php7.0-zip php7.0-bcmath php7.0-soap
# Cache
php /home/user/public_html/bin/magento indexer:reindex 
php /home/user/public_html/bin/magento cache:flush 
php /home/user/public_html/bin/magento cache:clean 
