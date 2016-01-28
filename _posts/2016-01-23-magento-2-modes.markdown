---
layout: post
title:  "Magento 2 modes: default, developer and production"
date:   2016-01-23 10:20:08
categories: Magento 2
---

In Magento 2 there is a extra mode were you can run Magento in. We now have the following options:

- Developer mode
- Production mode
- Default mode

In Magento 1 we could set the mode in index.php so we could quickly change the mode were we run magento in.
Magento 2 forces us to set webserver environmental variable.

When you install magento 2 it will run in the default mode.

Default mode
------
Lets just state this. Default mode is weird. More info under 'Production mode'.
Its a form between production and development mode.
Exceptions are written to the log files and static file caching is enabled.


Developer mode
------
The mode to develop in magento 2. Verbose logging, exceptions in the browser, static files not cached, etc.
This is what you want when you develop in magento 2.

Production mode
------
You have to use this in for a shop in production, this is awesome. This mode is also the reason why the default mode is weird.
Biggest win here is that static files dont run trough the fallback system. They are generated with the static view files deployment tool.
Errors are logged with a file, and never displayed to a user.
Question arises, why on earth would you want to run in default mode?

Notes
-----
As said before magento 2 will run in default mode after installing.

In magento 1 you can set the mode in index.php (or, in your htacces/vhost).
Because I'm lazy I want to set this setting globally in the vhost:

`SetEnv MAGE_IS_DEVELOPER_MODE true`

In magento 2 we can only set the mode in the htaccess or vhost with:

`SetEnv MAGE_MODE developer`

When you put this in your vhost, depending on your configuration, you will set this globally.

You can also use the magento CLI. (AWESOME!)
Use `magento deploy:mode:show` to show the mode your magento 2 instance is in.
When you want to change the mode use: `magento deploy:mode:set production`