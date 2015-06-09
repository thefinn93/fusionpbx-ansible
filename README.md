# FusionPBX Ansible Role

An ansible role to install [FusionPBX](http://www.fusionpbx.com/) on a debian-based system using the
debian packages. While not perfect, it's pretty good and improving. Pull requests are always
welcome, issues as well (although I may not get right on fixing them). The primary difference in the
final product from the official install scripts is that Freeswitch runs as it's own user. This can
cause some issues, the only one I've encountered is with fax inboxes. To make it exactly like the
FusionPBX install scripts, set `freeswitch_user: www-data` in the variables.
