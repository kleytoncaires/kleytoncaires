
# Project Setup
This guide outlines the necessary steps to set up and configure the WordPress environment along with additional plugins, themes, and dependencies.

## Prerequisites
- [Node.js](https://nodejs.org/)
- [Yarn](https://yarnpkg.com/)
- [Gulp](https://gulpjs.com/)
- [Homebrew (brew)](https://brew.sh/)
- [WP-CLI](https://wp-cli.org/)
- [PHP (brew)](https://formulae.brew.sh/formula/php)

## Theme Installation
Install the theme and configure basic settings:

### Install the theme
```bash
wp theme install https://github.com/kleytoncaires/wp-theme/archive/main.zip --activate
```

### Set up language and timezone
```bash
wp language core install pt_BR
wp site switch-language pt_BR
wp option update timezone_string 'America/Sao_Paulo'
```

### Create a homepage
```bash
wp post create --post_type=page --post_title='Home' --post_status=publish
wp option update show_on_front page
wp option update page_on_front 5
```

## Plugin Installation
To install the required plugins, execute the following command:

### Install and activate plugins
```bash
wp plugin install contact-form-7 contact-form-cfdb7 tinymce-advanced custom-post-type-ui svg-support wordpress-seo wp-mail-smtp wp-migrate-db --activate
```

### Install Advanced Custom Fields Pro
```bash
wp plugin install "http://connect.advancedcustomfields.com/index.php?p=pro&a=download&k=b3JkZXJfaWQ9Nzg5MDd8dHlwZT1kZXZlbG9wZXJ8ZGF0ZT0yMDE2LTA0LTA1IDEzOjQwOjQw" --activate
```

## Cleanup
Remove unnecessary files and themes:

### Remove unnecessary files
```bash
wp theme delete twentytwentytwo twentytwentythree twentytwentyfour
rm -rf wp-config-sample.php readme.html license.txt
```

### Rename the theme folder (replace 'theme-name' with the desired name)
```bash
mv wp-content/themes/wp-theme wp-content/themes/theme-name
```

### Remove the Git repository from the theme folder
```bash
rm -rf wp-content/themes/theme-name/.git
```

## Run Project in VSCode
```bash
cd wp-content/themes/theme-name
code .
```

## Dependency Installation
Install project dependencies using Yarn:
```bash
yarn add @fancyapps/ui @fortawesome/fontawesome-free bootstrap jquery jquery-mask-plugin popper.js swiper --save
```

## Task Execution
Execute tasks using Yarn:
```
yarn start
```

