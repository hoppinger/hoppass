# Hoppass

Hoppass provides Compass integration for Drupal.

## Dependencies
* Compass 0.12.7

## Installation

Install the module the usual way.

Make sure Compass is installed using 

```
gem install compass
```

```
$conf['hoppass_always_refresh'] = TRUE;
```

to your `settings.php` (or `settings.local.php` for Kraftwagen) file when developing.

### RVM
If you use rvm you can create a wrapper around the compass 0.12.7 gem so it doesn't conflict with other installs by doing the following

```sh
rvm use ruby-2.2.2 # or another compatible ruby
rvm gemset create drupal
rvm use ruby@drupal
gem install compass -v 0.12.7
rvm wrapper ruby@drupal compass
```
Then add the following line in your `settings.local.php`
```
$conf['hoppass_compass_bin'] = '/home/mark/.rvm/wrappers/ruby-2.2.2@drupal/compass';
```

### RBENV
Create the following Gemfile in you project
```
source 'https://rubygems.org'

ruby '2.2.2'

gem 'compass', '0.12.6'
```
Then install the bundle and create the binaries
```sh 
bundle install`
bundle install —binstubs
```
Then add the following line to your `settings.local.php`
```
$conf['hoppass_compass_bin'] = '/path/to/project/bin/compass';`
```

## Usage

Make sure that your SCSS files are stored in a subfolder of your theme, named `scss`. 

Add an SCSS file from your theme to your `.info` files, by adding it to the stylesheets list.

```
stylesheets[all][] = scss/style.scss
```

It is recommended to add just a few (or maybe just one) files to your `.info` file and include
the rest of the files using partials.

