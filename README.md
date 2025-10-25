
# important-magento-cli-commands

**Important commands for using php and composer in plesk cli ( DON'T TRY ON WHM/CPANEL ):**

**for plesk to specify php version in ssh:**
```bash
echo "alias php='/opt/plesk/php/8.1/bin/php'" >> ~/.bashrc
```
**for plesk to specify the composer php version:**

```bash
echo "alias composer='/opt/plesk/php/8.1/bin/php -d memory_limit=2048M /usr/lib/plesk-9.0/composer.phar'" >> ~/.bashrc
```
**for plesk load .bashrc after ssh login:**

create ~/.profile and insert this in it:
```bash
~/.profile: executed by Bourne-compatible login shells.

if [ "$BASH" ]; then

  if [ -f ~/.bashrc ]; then

    . ~/.bashrc

  fi

fi
```




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

php bin/magento deploy:mode:set production ( default | production | developer )
 

**Some Config Set from CLI:**

php bin/magento config:set dev/js/enable_js_bundling 1

php bin/magento config:set dev/js/minify_files 1

php bin/magento config:set dev/static/sign 1

php bin/magento config:set dev/js/merge_files 1


## Additional Important Magento 2 Commands:


**Maintenance Mode Management:**

php bin/magento maintenance:enable

php bin/magento maintenance:disable

php bin/magento maintenance:status

php bin/magento maintenance:allow-ips 192.168.1.1 --none


**Database Operations:**

php bin/magento setup:db-schema:upgrade

php bin/magento setup:db-data:upgrade

php bin/magento setup:db:status


**Admin User Management:**

php bin/magento admin:user:create

php bin/magento admin:user:unlock <username>


**Configuration Management (Deployment Pipeline):**

php bin/magento app:config:dump

php bin/magento app:config:import

php bin/magento app:config:status


**Advanced Indexer Management:**

php bin/magento indexer:status

php bin/magento indexer:info

php bin/magento indexer:set-mode {realtime|schedule} [indexer]

php bin/magento indexer:show-mode [indexer]


**Advanced Cache Management:**

php bin/magento cache:enable [type]

php bin/magento cache:disable [type]


**Cron Management:**

php bin/magento cron:run

php bin/magento cron:remove


**Queue Consumers (Async Operations):**

php bin/magento queue:consumers:list

php bin/magento queue:consumers:start <consumer_name>


**Customer Operations:**

php bin/magento customer:hash:upgrade


**Store & Config Operations:**

php bin/magento config:show [path]

php bin/magento config:sensitive:set [path] [value]

php bin/magento store:list

php bin/magento store:website:list


**Sitemap Generation:**

php bin/magento sitemap:generate


**Advanced Static Content Deployment:**

php bin/magento setup:static-content:deploy -f

php bin/magento setup:static-content:deploy en_US en_GB --theme Vendor/theme

php bin/magento setup:static-content:deploy --area adminhtml


**Backup Operations:**

php bin/magento setup:backup --code --db --media


**Developer Tools:**

php bin/magento dev:query-log:enable

php bin/magento dev:query-log:disable

php bin/magento dev:profiler:enable

php bin/magento dev:profiler:disable

php bin/magento dev:template-hints:enable

php bin/magento dev:template-hints:disable


**Advanced Upgrade Commands:**

php bin/magento setup:upgrade --keep-generated

php bin/magento setup:upgrade --safe-mode


**Performance & Optimization:**

php bin/magento catalog:images:resize

php bin/magento varnish:vcl:generate

php bin/magento setup:performance:generate-fixtures


**Security & Encryption:**

php bin/magento encryption:payment-data:update

php bin/magento security:tfa:google:set-secret <user> <secret>


**Import/Export:**

php bin/magento import:run

php bin/magento import:list


**Module Uninstall:**

php bin/magento module:uninstall VENDOR_MODULENAME

php bin/magento module:uninstall VENDOR_MODULENAME --remove-data
