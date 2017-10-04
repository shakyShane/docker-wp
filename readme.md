# Docker + Bedrock Development Environment

<!--crossbow-docs-start-->
## Crossbow tasks

The following tasks have been defined by this project's Crossbow configuration.
Run any of them in the following way
 
```shell
$ crossbow run <taskname>
```
|Task name|Description|
|---|---|
|<pre>`start`</pre>|Start all services. Note: this will auto-import any DB in the mysql folder|
|<pre>`up`</pre>|**Alias for:**<br>- `@sh docker-compose up --build -d`|
|<pre>`stop`</pre>|**Alias for:**<br>- `@sh docker-compose stop`|
|<pre>`down`</pre>|**Alias for:**<br>- `@sh docker-compose down`|
|<pre>`restart`</pre>|Take down all services, clean files and then restart. Note: this will re-import any DB in the mysql folder|
|<pre>`composer`</pre>|<strong>Run composer commands inside the PHP container.</strong> <br><br> So where you'd normally run the following commands:<br> `composer require some-plugin` <br> `composer remove some-plugin` <br><br> You can replace them with: (note the `--` terminator) <br> `cb composer -- require some-plugin`<br> `cb composer -- remove some-plugin`|
|<pre>`clean`</pre>|Remove `vendor`, `wp` & `plugin` files that are not tracked by git<br><br> Usage:<br>  `cb clean`|
|<pre>`copy-after-composer`</pre>|Copy files that could be affected by composer from the container back into your local directories|
|<pre>`copy`</pre>|Copy all vendor, WP & plugin files that were installed by composer inside the container back to your local machine|
|<pre>`cp:lock`</pre>|**Alias for:**<br>- `@sh docker cp $(docker-compose ps -q php):/var/www/composer.lock .`|
|<pre>`cp:composer-json`</pre>|**Alias for:**<br>- `@sh docker cp $(docker-compose ps -q php):/var/www/composer.json .`|
|<pre>`cp:vendor`</pre>|**Alias for:**<br>- `@sh docker cp $(docker-compose ps -q php):/var/www/vendor/. ./vendor`|
|<pre>`cp:plugins`</pre>|**Alias for:**<br>- `@sh docker cp $(docker-compose ps -q php):/var/www/$JH_APP_DIR/plugins/. ./$JH_APP_DIR/plugins`<br>- `@sh docker cp $(docker-compose ps -q php):/var/www/$JH_APP_DIR/mu-plugins/. ./$JH_APP_DIR/mu-plugins`|
|<pre>`cp:wp`</pre>|**Alias for:**<br>- `@sh docker cp $(docker-compose ps -q php):/var/www/$JH_WP_DIR/. ./$JH_WP_DIR`|
<!--crossbow-docs-end-->