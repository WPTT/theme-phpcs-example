# Example composer.json and phpcs.xml.dist files to theme development

This repository contains an example of the `composer.json` and `phpcs.xml.dist` file for theme developers to use in their themes.

You can use these as a starting point in your theme development.

### ⚠️ Be sure to replace the placeholder names in both files

These files correspond to the current directory. You'll want to have these files correspond to your theme and your repo. So for instance, in `composer.json`, you'd replace

```json
"name"       : "your-repo/your-theme-slug",
```

With your repository and theme name. You'd also change the description, homepage, and other meta data.

The set required PHP version is set to latest as of writing this (7.4), in order to promote using the latest PHP version. You can change this as well to suite your needs. You can also add additional packages from the Packagist repository. The world is your oyster 🙂.

The same stands for the `phpcs.xml.dist`. You can customize this to your needs. You should change the `ruleset`'s `name` property to match your own

```xml
<ruleset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" name="My Theme Name Coding Standards" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/squizlabs/PHP_CodeSniffer/master/phpcs.xsd">
```

You can add different rulesets, add or exclude different rules, change `testVersion` and `minimum_supported_wp_version` based on your prefernces.

You should change the `docroot` in these settings

```xml
<!-- Exclude WP Core folders and files from being checked. -->
<exclude-pattern>/docroot/wp-admin/*</exclude-pattern>
<exclude-pattern>/docroot/wp-includes/*</exclude-pattern>
<exclude-pattern>/docroot/wp-*.php</exclude-pattern>
<exclude-pattern>/docroot/index.php</exclude-pattern>
<exclude-pattern>/docroot/xmlrpc.php</exclude-pattern>
<exclude-pattern>/docroot/wp-content/plugins/*</exclude-pattern>
```

to match your docroot where WordPress is installed, based on where the vendor folder is located.

You can check the sample example on the [WPCS GitHub page](https://github.com/WordPress/WordPress-Coding-Standards/blob/develop/phpcs.xml.dist.sample). Also read the [PHPCS Annotated Ruleset](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Annotated-Ruleset) example and wikis from both [PHPCS](https://github.com/squizlabs/PHP_CodeSniffer/wiki) and [WPCS](https://github.com/WordPress/WordPress-Coding-Standards/wiki) for better understandment of using the PHP_CodeSniffer.
