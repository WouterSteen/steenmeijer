---
layout: post
title:  "Magento 2 themes: blank and luma"
date:   2015-09-18 19:48:08
categories: Magento 2
---

Magento 2 comes with 2 themes. Luma, as a demonstration theme and blank as a theme were you can build on.
The themes are located at `magento2/app/design/frontend/Magento/`

Alot has changed in Magento 2 theming. The biggest change is that all the files, including the static files, that you use for a module are in the correspondending module folder.
So if you created a module and want to add some template files you do this in `magento2/app/code/VENDOR/MODULE/view/frontend/templates`

Some other changes:

- Translation folder: i18n in the theme folder
- `etc/view.xml` to specify all the images on the storefrond
- default Less support
- Pushing to use composer (you dont have to, but you want to :))
- RequireJS
- Media folder that contains a preview
- Web folder that contains static files


Check out the [Frontend developer guide][magento] for more info on these themes. If you want to keep track of the changes visit the magento 2 [github page][magento-github] once in a while.

[magento]:      http://devdocs.magento.com/guides/v2.0/frontend-dev-guide/bk-frontend-dev-guide.html
[magento-github]: https://github.com/magento/magento2