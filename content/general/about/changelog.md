# Changelog

## 2.1.2 - June 4, 2012

### Security Patches

* Fixed minor XSS issue in blog categories module
* Patched a XSS hole where redirect_to could contain a malicious URL

### Bug Fixes

* Fixed bug with admin menu where Manage Users only showed when on the Users page.
* Fixed bug where username became foo123 instead of foo3
* Fixed a bug where the Publish and Delete buttons didn't work on the blog index page
* Make error reporting be always true, just HIDE errors in production.
* Added cookie prefix config to the installer. __Note:__ If you've recently installed from develop you may want to update your config file
* Fixed issue where if a page was loaded in HTTPS it would set the cache and other users would be sent to HTTPS, which lead to unexpected behaviour
* The Files library wasn't returning all pertinant information when moving files to the cloud
* Set the email length to 60 in the database for new installs
* Fixes ordering of javascript assets in the wysiwyg picker
* Fixed a bug in the wysiwyg controller that only showed to non-admins
* Added image ID to output for those who like to use built-in files resizing

## 2.1.1 - May 4, 2012

### Improvements

* Updated the widgets area boxes with a friendly little hand
* Add support to slug field\_type to select fields. Slugifies on\_change
* Non admins with permissions to edit users cannot edit admin user accounts
* Added order-by attribute to {{ noparse }}{{ files:listing }}{{ /noparse }} to allow sorting list
* Added expiration attribute to the integration plugin

### Bugs 

* Fixing WYSIWYG assets for the front end entry form
* Fixing old variable call in Streams core fields library
* Fixed a bug with the {{ noparse }}{{ pages:chunk }}{{ /noparse }} tag when used with markdown
* Fixed the non-english string showing in the Groups module description
* Fixed a bug in the files module that showed when the last item was deleted
* Fixed #1386. Support for less/sass in the {{ noparse }}{{ theme:css }}{{ /noparse }} tag

## 2.1.0 - April 23, 2012

### Features

* Added modular REST API system, only available for Professional.
* Re-built Files module with Cloud Storage and new interface.
* Upgraded jQuery to 1.7.1.
* Upgraded CodeIgniter to latest 3.0-dev.
* Upgraded Curl library to Curl Spark v1.2.1.
* Added a post count plugin for the blog
* Started adding a feature to make CKEditor configurable via the Control Panel
* Added a tag: {{ noparse }}{{ helper:config item="default_language" }}{{ /noparse }}
* Added TwitterOAuth and OAuth library. This should really only be a temporary measure until a worker Twitter library with a nice abstract interface matching Facebook and other providers is developed. There's talk of it happening from a few people, but for now we have this. Be careful about building modules around it.
* Disable user registration from settings
* Implemented Asset minification and combination for the Control Panel. 
* Added the asset cache folder. Dont forget to chmod.
* Use display_name instead of first + last on profile
* Added Slovenian translation
* Added 42 triggers, passed ids or data where applicable
* Adding some more greek characters in the foreign_chars.php Added the greek characters in the Javascript Regexp test string so that they can be caught in it and the slug creation can be triggered.
* Removed Google CDN jQuery from themes and Control Panel, not a good default.
* Added Module::install_tables() so that every table installation logic can be handled more centrally.
* Allow admins to see profiler if they set ?debug=1 on any page.
* Converted modules to install using CodeIgniters DBForge. 
* Added download counter to Files.
* Hide Google Analytics message on Dashboard unless settings have been added.
* Removed duplication of views in Blog module. Lists of Blog posts (index.php or cateogry.php) now delegate to posts.php for the list of posts.
* Large update to datetime field type to allow drop down data intake of month/day/year. Still needs testing and more updates.
* Page Chunks can now be sorted.
* Added portuguese translation.
* Added an option to widgets so that a widget title can be hidden via the interface.
* Added ajax login/logout capability.
* Redirects will now have 301 or 302 dropdown in redirects. Redirects will now support \* wildcard in from field and optionally $1,$2... in to field.

#### Bugs

* Redirecting logged in users to home page when they try to access the registration page. Closes #1154.
* Fixed warnings with no tweets in the widget
* Fixed issue #1121: Upgraded CKEditor to 3.6.2 Also "fixed" random breaking
* Fixed issue where adding a category in blog would change the blog slug in the form
* Fixed issue #1248: Comments were not being deleted when a blog post or page was removed
* Removed strtolower on Keywords as it was causing problems for Greek characters. Closes #1064
* Closes #1072. Decode url encoded characters in blog tags. Closes #1252
* Closes #616. Pyrocache now creates separate cache files for each aliased domain
* Allow for more than one Google Maps per page.
* Fixed a bug with user profile viewing that caused the user's profile to not be displayed when using alternate routes
* Corrected the default user group to the singular form.
* Changed user profile view to hide information like email addresses by default
* Fixed the widget area views in the widgets module
* Updates admin user edit form to multipart. Closes #1319
* Fixed item placement when dragging widget instances in a long list. Closes #1308
* Removed unused pyro.lang.delete as it was causing IE to pitch a fit
* Removed iPad from the mobile array of the user_agent config file. It will now load the full version of a site as our documentation states it will.

## 2.0.4 - June 04, 2012

### Security Patches

* Fixed minor XSS issue in blog categories module
* Patched a XSS hole where redirect_to could contain a malicious URL

### Improvements

* Allow admins to see profiler, not just locally

## 2.0.3 - March 06, 2012

### Improvements

* Added inner_tag attribute to the navigation plugin
* Added a padding div to the page chunk
* Reduce unnecessary DB queries
* correct the wording in sl language
* When using the Fit option when creating thumbnails it made a black border around the thumb. Corrected so the crop is perfect
* Changed Pro Newsletters version number to match the stand-alone version
* Moved the theme options out of the modal and into a full page
* Turned off XSS filtering for Email Templates so that inline styles can be used
* Added "admin" option in navigation
* Removed the confirm password field to match the way the installer and user management does it
* Also shorted the site ref length requirement to 1 instead of 4
* Fixed incorrect salt object
* Update Spanish translations
* Update German translations
* Fix typo in users/language/german/user_lang.php
* Update UTF8 strings and files to UTF8 without BOM
* Fixed incorrect profile edit message and a bug when an admin edited another user's profile
* Teach ckeditor to handle the template vars url:base and url:site in img src
* Change SITE_URL to {{ noparse }}{{ site:url }}{{ /noparse }} when inserting files and images into ckeditor
* Updated PyroStreams to 2.1.3.
* Add ID to field generated by the contact module
* Rescued an Italian translation pull request
* Added a small delay to keep pages and navigation from being sorted accidentally on click
* Fix broken string interpolation in exception message

### Bug Fixes

* Fixed glob issue with installer
* Fixed the registration errors
* Corrected the overflow of analytics wrapper
* Fixed a bug in Newsletters where a fatal error could occur if Settings array was empty
* changed code style and division by zero
* Removed base="url" from the default theme favicon
* {{ noparse }}{{ pages:children }}{{ /noparse }} now handles page chunks properly
* Added missing permission check to Blog delete permissions
* Blog post author's display name is now selected when getting tagged posts
* Fix "Top" link in the footer of the default theme


## 2.0.2 - February 08, 2012

### Improvements

* Improved IE8 compatibility.
* Use display_name instead of first + last on profile
* Updated Dutch language

### Bug Fixes

* Fixed the display method to properly return the $pages data array as an index within another array.
* Fixed issue #1073: Folder drop-down is cut off when more than 3 folders exist.
* Fixed issue #1063: Database port number was not being sent in the installer ajax check
* Fixed issue #1113: Issue on install where some servers return FALSE from glob instead of an empty array.
* Made a few tweaks for better Social Integration support.
* Fixed a bug in the contact form where multiple drop-downs would end up with their values appended to the next one.
* Fixed issue #1089 to fix admin navigation bug with Users menu

## 2.0.1 - January 26, 2012

### New Features

* Added Indonesian Language

### Bug Fixes

* Fixed issue where a user's session would be randomly dropped 
* Fixed column display issue for Widgets module
* Fixed some display issues for IE8
* Fixed some positioning and subfolder dropdown style issues in the Files module
* Fixed PHP notices when the navigation plugin is used as a tag pair
* Fixed a bug where a user with permission to access the Newsletters module and not the Users module, would see a "Manage Users" link in the CP nav bar
* [Pro] Fixed an issue with the MSM that didn't record the correct migration version when creating a new site
* [Pro] Removed incorrect line in license that stated you could not remove the PyroCMS logo from PyroCMS Professional

### For Developers

* Added HTML5 Shim to the control panel
* Removed users\_m in favor of user\_m in the Users module
* Disabled persistent database connections by default
