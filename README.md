# FusionPBX + ASTPP Ansible Role

An ansible role to install [FusionPBX](http://www.fusionpbx.com/) and [ASTPP](http://www.astpp.org/)
on a debian-based system using the FusionPBX and FreeSWITCH debian packages. While not perfect, it's
pretty good and improving. Pull requests are always welcome, issues as well (although I may not get
right on fixing them).

*The ASTTP branch is untested and still under development. Many ASTPP things are hard-coded to use
their silly file paths, so this scripts edits those. Most of them are configurable from the vars.*


TODO
----
- [ ] Perl executables are stores at `{{ ASTPP_exec_directory }}` instead of `/usr/local/astpp/` and the following files need to be fixed:
 - `freeswitch/astpp/astpp-fs-xml.cgi`
 - `freeswitch/astpp-callingcards.pl`
 - `freeswitch/astpp/astpp-cdr-xml.cgi`
- [ ] Sounds are stored at {{ ASTPP_sounds_directory }} instead of `/usr/local/freeswitch/sounds/en/us/callie` and the following files need to be made aware of this change:
 - `freeswitch/astpp-callingcards.pl`
 - `freeswitch/astpp/astpp-dialplan-xml.pl`
 - `astpp-2.0.sql` needs several updates, can possibly happen post-import
- [ ] Config is `{{ ASTPP_config_directory }}/astpp-config.conf` instead of /var/lib/astpp/astpp-config.conf and the following files need to be updated:
 - `web_interface/astpp/application/config/cron.php`
 - `web_interface/astpp/application/config/database.php`
 - `web_interface/astpp/application/modules/systems/controllers/systems.php`
 - `web_interface/astpp/application/config/config.php`
- [ ] The install instructions say to do `chmod -Rf 777 /usr/local/freeswitch/sounds/en/us/callie/` - I decided to just not touch the directory permissions yet, but I suspect an ownership of `www-data:freeswitch` with permissions 640 would be fine (of course on `{{ ASTPP_sounds_directory }}`)
- [ ] Still haven't even started with the nginx configuration
- [ ] Still haven't even started with the MySQL crap
