
# important magento2 cli commands
 
## Important commands for using php and composer in plesk cli:

**for plesk to specify php version in ssh:**
echo "alias php='/opt/plesk/php/7.3/bin/php'" >> ~/.bashrc

**for plesk to specify the composer php version:**
echo "alias composer='/opt/plesk/php/7.3/bin/php -d memory_limit=2048M /usr/lib/plesk-9.0/composer.phar'" >> ~/.bashrc



## useful Magento 2 CLI commands:

**Prepare The Cron in Crontab:**
php bin/magento cron:install

**Check The Module Status:**
php bin/magento module:status

**Disable Module:**
php bin/magento module:disable VENDOR_MODULENAME

**Enable Module:**
php bin/magento module:enable VENDOR_MODULENAME

**Cache Operations:**
php bin/magento cache:status
php -d memory_limit=2048M bin/magento cache:flush
php -d memory_limit=2048M bin/magento cache:clean

**Indexer ( Reindex | Reset ):**
php -d memory_limit=2048M bin/magento indexer:reindex
php bin/magento indexer:reset

**Setup Upgrade:**
php -d memory_limit=2048M bin/magento setup:upgrade

**Setup Compile:**
php -d memory_limit=2048M bin/magento setup:di:compile

**Static Content Deploy:**
php -d memory_limit=2048M bin/magento setup:static-content:deploy

**Catalog Images Resize:**
php bin/magento catalog:image:resize

**Deploy Mode Functions:**
php bin/magento deploy:mode:show
php bin/magento deploy:mode:set production ( default | production | develop )

**Some Config Set from CLI:**
php bin/magento config:set dev/js/enable_js_bundling 1
php bin/magento config:set dev/js/minify_files 1
php bin/magento config:set dev/static/sign 1
php bin/magento config:set dev/js/merge_files 1
