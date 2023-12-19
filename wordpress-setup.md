
# Project Setup
This guide outlines the necessary steps to set up and configure the WordPress environment along with additional plugins, themes, and dependencies.

## Prerequisites
- [Node.js](https://nodejs.org/)
- [Yarn](https://yarnpkg.com/)
- [Gulp](https://gulpjs.com/)
- [Homebrew (brew)](https://brew.sh/)
- [WP-CLI](https://wp-cli.org/)
- [PHP (brew)](https://formulae.brew.sh/formula/php)

## Plugin Installation
To install the required plugins, execute the following command:


```sh
# Install and activate plugins
wp plugin install contact-form-7 contact-form-cfdb7 tinymce-advanced custom-post-type-ui svg-support wordpress-seo wp-mail-smtp wp-migrate-db --activate

# Install Advanced Custom Fields Pro
wp plugin install "http://connect.advancedcustomfields.com/index.php?p=pro&a=download&k=b3JkZXJfaWQ9Nzg5MDd8dHlwZT1kZXZlbG9wZXJ8ZGF0ZT0yMDE2LTA0LTA1IDEzOjQwOjQw" --activate
```

## Theme Installation
Install the theme and configure basic settings:

```sh
# Install the theme
wp theme install https://github.com/kleytoncaires/wp-theme/archive/main.zip

# Rename the theme folder (replace 'theme-name' with the desired name)
mv wp-content/themes/wp-theme wp-content/themes/theme-name

# Activate the theme (replace 'theme-name' with the desired name)
wp theme activate theme-name
```

## Cleanup
Remove unnecessary files and themes:

```sh
# Remove unnecessary files
wp theme delete twentytwentytwo twentytwentythree twentytwentyfour
rm -rf wp-config-sample.php readme.html license.txt
```

# Set up language and timezone
```sh
wp language core install pt_BR
wp site switch-language pt_BR
wp option update timezone_string 'America/Sao_Paulo'

# Create a homepage
wp post create --post_type=page --post_title='Home' --post_status=publish

# Set the show_on_front option to 'page'
wp option update show_on_front page

# Get the ID of the newly created page
wp post list --post_type=page --field=ID --home

# Update the page_on_front option with the ID of the homepage (Make sure to replace [ID] with the ID of the page obtained in previous step)
wp option update page_on_front [ID]
```

## Run Project in VSCode
```sh
cd wp-content/themes/theme-name
code .
```

## Dependency Installation
Install project dependencies using Yarn:
```sh
yarn add @fancyapps/ui @fortawesome/fontawesome-free bootstrap jquery jquery-mask-plugin popper.js swiper --save
```

## Task Execution
Execute tasks using Yarn:
```sh
yarn start
```

