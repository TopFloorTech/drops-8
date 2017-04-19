Configuration files

Drupal 8 installation profiles can contain configuration files. You can start by taking the configuration directory
(config folder) of an installed, configured site and copying it into the config/install folder in your profile.

Once that's in place, there are some other required tasks:

- Copy all of the modules and themes listed within core.extension.yml into your profile's info file (using the new info
  file's format).
- Delete core.extension.yml (and possibly some other config files).
- Remove all of the UUIDs from your config files so that they don't conflict with those of new sites. This can be done
  quite easily on the command line like so all on one line:
  find /path/to/PROFILE_NAME/config/install/ -type f -exec sed -i '' -e '/^uuid: /d' {} \;

If you just want to grab an existing site's configuration, and don't need to end up with a formal installation profile
(for sharing on Drupal.org, for example), you can use the Configuration Installer installation profile to install a new
site from the configuration of another site.

See: https://www.drupal.org/docs/8/creating-distributions/how-to-write-a-drupal-8-installation-profile