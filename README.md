# Hoppass

Hoppass provides Compass integration for Drupal.

## Installation

Install the module the usual way.

Make sure Compass is installed using 

```
gem install compass
```

Add

```
$conf['hoppass_always_refresh'] = TRUE;
```

to your `settings.php` (or `settings.local.php` for Kraftwagen) file when developing.

If you installed Ruby using RVM, you will need to create a RVM wrapper around
the compass executable, just like you would do for `init.d` scripts. Take a look
at https://rvm.io/integration/init-d/ for more information. After you created
the wrapper, add the following line to your `settings(.local.)php`.

```
$conf['hoppass_compass_bin'] = '/absolute/path/to/wrapper';
```

## Usage

Make sure that your SCSS files are stored in a subfolder of your theme, named `scss`. 

Add an SCSS file from your theme to your `.info` files, by adding it to the stylesheets list.

```
stylesheets[all][] = scss/style.scss
```

It is recommended to add just a few (or maybe just one) files to your `.info` file and include
the rest of the files using partials.

