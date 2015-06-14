# FusionPBX + ASTPP Ansible Role

An ansible role to install [FusionPBX](http://www.fusionpbx.com/) and [ASTPP](http://www.astpp.org/)
on a debian-based system using the FusionPBX and FreeSWITCH debian packages. While not perfect, it's
pretty good and improving. Pull requests are always welcome, issues as well (although I may not get
right on fixing them).

*The ASTTP branch is untested and still under development. Many ASTPP things are hard-coded to use
their silly file paths, so this scripts edits those. Most of them are configurable from the vars.*


TODO
----
- [ ] Convert all replacement that is does with regexp/sed into a nice patchfile.
- [ ] The install instructions say to do `chmod -Rf 777 /usr/local/freeswitch/sounds/en/us/callie/` - I decided to just not touch the directory permissions yet, but I suspect an ownership of `www-data:freeswitch` with permissions 640 would be fine (of course on `{{ ASTPP_sounds_directory }}`)
- [ ] Still haven't even started with most of the nginx configuration
