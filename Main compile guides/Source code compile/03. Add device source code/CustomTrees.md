Custom Trees
============

Navigator
---------
[Creating roomservice.xml](#creating-roomservice-xml)

Creating roomservice.xml
------------------------
Here's a roomservice.xml:

<iframe src='https://raw.githubusercontent.com/TipzTeam/android_development_guide/master/Main%20compile%20guides/Source%20code%20compile/03.%20Add%20device%20source%20code/examplecustom.xml' scrolling='no' frameborder='0'></iframe>

roomservice.xml starts with `<?xml version="1.0" encoding="UTF-8"?>` like any other xml files.

Than `<manifest>` is required to make it a manifest file.

After that, it is all `<remote>`, than there will be arguments, here's a list of common arguments:

Argument|Usage
--------|-----
name|Remote name
fetch|Git server
review|Review server
revision|Branches or revision

Than, it is all `<project>`, than there will be arguments, here's a list of common arguments:

Argument|Usage
--------|-----
name|Project name
path|Sync to path
remote|Use remote

Some devices need repo replacements, so we have to first remove them, use `<remove-project>`:

Argument|Usage
--------|-----
name|Project name

You can than use `<project>` to sync the replacements. Than end the roomservice with `</manifest>`.

Resync time
-----------

Than, a resync will do what you have added with roomservice.

If you have to sync project replacements, just add `--force-sync` when you are resyncing.
