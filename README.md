# Start working on the project

1. Install [DDEV](https://ddev.readthedocs.io/en/latest/users/install/ddev-installation/)
2. Create you `settings.local.php` from example file `$ cp web/sites/default/example.settings.local.php web/sites/default/settings.local.php`
3. Create you `services.local.yml` from example file `$ cp web/sites/default/example.services.local.yml web/sites/default/services.local.yml`
4. [Start containers](#start-containers)
5. Install composer dependencies `$ ddev composer install`
6. [Share ssh keys with host](#share-ssh-keys-with-host)
7. [Import a database dump](#import-a-database-dump)
8. [Generate css](#run-watcher-for-compiling-css)
9. Rebuild cache `ddev drush cr`
10. Import configuration from code `ddev drush cim`
11. Generate login link `ddev drush uli`
12. Enjoy!

# Start containers
```shell
$ ddev start
```

