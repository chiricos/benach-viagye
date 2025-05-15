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

# instalando tema basico
```shell
$ ddev composer require 'drupal/bootstrap_barrio:^5.5'
```

# instalando tema administrativo
```shell
$ ddev composer require 'drupal/gin:^4.0'
$ ddev drush theme:install gin
$ ddev drush en gin_toolbar
$ ddev drush cr
```

# Creación de un subtema con Bootstrap
```shell
$ ddev composer require 'drupal/bootstrap_barrio:^5.5'
$ composer require 'drupal/bootstrap_sass:^5.0'
$ mkdir web/themes/custom
$ mv web/themes/contrib/bootstrap_sass/ web/themes/custom/benach_viagye
$ cd themes/custom/benach-viagye
$ npm install
```

Dentro de la configuración de Gulp (archivo benach_viagye/gulpfile.js), tenemos que cambiar esta línea por el nombre de dominio de nuestro sitio:
```shell
  browserSync.init({
    proxy: "http://yourdomain.com",
  });
```
También podemos evitar que se ejecute browserSync cambiando esta línea:
```shell
  const build = gulp.series(styles, gulp.parallel(js, serve))
```
por esta otra:
```shell
const build = gulp.series(styles, gulp.parallel(js))
```
Por último, para compilar los cambios en JS y Sass, ejecutaremos el comando:
```shell
$ gulp
```
O, alternativamente:
```shell
$ ./node_modules/.bin/gulp
```

Iconos: Fontawesome https://fontawesome.com/icons?d=gallery&m=free