
# Project Setup
This guide outlines the necessary steps to set up and configure the WordPress environment along with additional plugins, themes, and dependencies.

## Prerequisites
- [Node.js](https://nodejs.org/)
- [Homebrew (brew)](https://brew.sh/)
- [Yarn](https://yarnpkg.com/)
- [Gulp](https://gulpjs.com/)
- [WP-CLI](https://wp-cli.org/)
- [PHP (brew)](https://formulae.brew.sh/formula/php)


## Plugin Installation
To install the required plugins, execute the following command:
```bash
wp plugin install contact-form-7 contact-form-cfdb7 tinymce-advanced custom-post-type-ui svg-support wordpress-seo wp-mail-smtp wp-migrate-db --activate
wp plugin install "http://connect.advancedcustomfields.com/index.php?p=pro&a=download&k=b3JkZXJfaWQ9Nzg5MDd8dHlwZT1kZXZlbG9wZXJ8ZGF0ZT0yMDE2LTA0LTA1IDEzOjQwOjQw" --activate
```
## Theme Installation
Install the theme using the following command:
```bash
wp theme install https://github.com/kleytoncaires/wp-theme/archive/main.zip --activate
wp theme delete twentytwentytwo twentytwentythree twentytwentyfour
```

## Cleanup
Remove unnecessary files (e.g., Git repository) with the following command:
```bash
rm -rf wp-config-sample.php readme.html license.txt
rm -rf wp-content/themes/wp-theme/.git
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

