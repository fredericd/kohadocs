.. include:: images.rst

Plugin System
=============

Koha's Plugin System allows for you to add additional tools and reports
to Koha that are specific to your library. Plugins are installed by
uploading KPZ ( Koha Plugin Zip ) packages. A KPZ file is just a zip
file containing the perl files, template files, and any other files
necessary to make the plugin work.

The plugin system needs to be turned on by a system administrator.

`Set up <#pluginsetup>`__
-------------------------

To set up the Koha plugin system you must first make some changes to
your install.

-  Change <enable\_plugins>0</enable\_plugins> to
   <enable\_plugins>1</enable\_plugins> in your koha-conf.xml file

-  Restart your webserver

Once set up is complete you will need to alter your
`UseKohaPlugins <#UseKohaPlugins>`__ system preference. On the Tools
page you will see the Tools Plugins and on the Reports page you will see
the Reports Plugins.

Search History
==============

If you have your `EnableSearchHistory <#EnableSearchHistory>`__
preference set to keep your search history then you can access this
information by clicking on your username in the top right of the staff
client and choosing 'Search history'.

Search history
|image1062|

From this page you will see your bibliographic search history

Bibliographic search history
|image1063|

And your authority search history.

Authority search history
|image1064|

About Koha
==========

The 'About Koha' area will give you important server information as well
as general information about Koha.

-  *Get there:* More > About Koha

`Server Information <#aboutserver>`__
-------------------------------------

Under the 'Server Information' tab you will find information about the
Koha version and the machine you have installed Koha on. This
information is very important for debugging problems. When reporting
issues to your support provider or to the various other support avenues
(mailing lists, chat room, etc), it's always good to give the
information from this screen.

Server Information on Koha
|image1065|

`Perl Modules <#aboutserverperl>`__
-----------------------------------

In order to take advantage of all of the functionalities of Koha, you
will need to keep your Perl modules up to date. The 'Perl Modules' tab
will show you all of the modules required by Koha, the version you have
installed and whether you need to upgrade certain modules.

Perl Modules
|image1066|

Items listed in bold are required by Koha, items highlighed in red are
missing completely and items highlighted in yellow simply need to be
upgraded.

`System Information <#aboutsystem>`__
-------------------------------------

This tab will provide you with warnings if you are using system
preferences that have since been deprecated or system preferences that
you have set without other required preferences

System Information
|image1067|
