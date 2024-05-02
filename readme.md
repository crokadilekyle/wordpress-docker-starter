# WordPress Docker Starting Point

## Dependencies

This repo uses `wp-env` to handle the docker stuffs.  To learn more about it and all of it's features [you can go here](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-env/).

```
npm i -g wp-env
```

```
wp-env start
```

This will fire up a basic WordPress site running at localhost:8888.  The database port is randomly selected.  It may take a little while the first time you do it or if you need to pull a new version of WordPress.

To bring down the site you can run

```
wp-env stop
```

This repo also uses composer to install plugins.  The composer.json file is set up to install plugins into the `plugins` folder.  There are some examples in there to give you an idea of how to install plugins.  To install your plugins update the `composer.json` file and run 

```
composer install
```

## File Structure

The `.wp-env.json` file can be used for a lot of different configuration values.  The `mappings` property allows you to set where your local directories will map into the Docker container.  In the example `.wp-env.json` provided, we're mapping our local plugins folder to the plugins folder in the Docker container.  We're also mapping the current working directory to `themes/{our theme's name}.  This way, our current working directory will be treated as a theme.

## Accessing the site

The default credentials are:

u: admin
p: password

The default database credentials are:

host: 127.0.0.1
port: {will be displayed in the command line}
u: root
p: password

When the site first fires up it will be using a default WordPress theme. But if you log in you should be able to find your theme and activate it.

If you installed any plugins you should see those in the admin as well.
