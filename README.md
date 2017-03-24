# Customizations for [vccw](http://vccw.cc/), a Vagrant environment for Wordpress

These are some personal workflow customizations and additional files I'm using for vccw. You may find them useful too.

Primary items of note are:

1. Automatic database dump and import on destroy and provision
2. Movefile has more exclusions, local environment is https, and minor syntax changes to help reduce certain errors.
3. A .gitignore for wordpress theme development
4. SSL admin forced in site.yml

This is currently based on vccw version 3.2.0. Adjust as necessary on future versions.

## Instructions

The database export on `vagrant destroy` requires Vagrant triggers. Install if you haven't already.

`vagrant plugin install vagrant-triggers`

Before first provision, copy 'Vagrantfile', 'provision-post.sh', and 'site.yml' to your vccw directory.

*The trigger for the db export on destroy is located at the end of Vagrantfile. The db import on provision is in provision-post.sh, and the only change to site.yml from default is to force ssl admin.*

After first provision, replace the generated Movefile if you plan to use wordmove.

If desired, copy '.gitignore_wordpress_theme' into the generated 'wordpress' shared directory and rename to '.gitignore'.
