.. include:: images.rst

Administration
==============

`Global System Preferences <#globalsysprefs>`__
-----------------------------------------------

Global system preferences control the way your Koha system works in
general. Set these preferences before anything else in Koha.

-  *Get there:* More > Administration > Global System Preferences

Global System Preferences Link and Search
|image0|

System preferences can be searched (using any part of the preference
name or description) using the search box on the 'Administration' page
or the search box at the top of each system preferences page.

Preferences search at the top of System Preference page
|image1|

When editing preferences a '(modified)' tag will appear next to items
you change until you click the 'Save All' button:

After editing TagsModeration the '(modified)' label appears
|image2|

After saving your preferences you'll get a confirmation message telling
you what preferences were saved:

Preference save confirmation message
|image3|

Each section of preferences can be sorted alphabetically by clicking the
small down arrow to the right of the word 'Preference' in the header
column

Sort option at the top right of each section of preferences
|image4|

If the preference refers to monetary values (like
`maxoutstanding <#maxoutstanding>`__) the currency displayed will be the
default you set in your :ref:`Currencies and Exchange Rates` 
administration area. In the examples to
follow they will all read USD for U.S. Dollars.

    **Important**

    For libraries systems with unique URLs for each site the system
    preference can be overridden by editing your koha-http.conf file
    this has to be done by a system administrator or someone with access
    to your system files. For example if all libraries but one want to
    have search terms highlighted in results you set the
    OpacHighlightedWords preference to 'Highlight' then edit the
    koha-http.conf for the library that wants this turned off by adding
    'SetEnv OVERRIDE\_SYSPREF\_OpacHighlightedWords "0"'. After
    restarting the web server that one library will no longer see
    highlighted terms. Consult with your system administrator for more
    information.

`Acquisitions <#acqprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences >
Acquisitions

`Policy <#acqprefspolicy>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AcqCreateItem <#AcqCreateItem>`__
''''''''''''''''''''''''''''''''''

Default: placing an order

Asks: Create an item when \_\_\_.

Values:

-  cataloging a record

-  placing an order

-  receiving an order

Description:

-  This preference lets you decide when you'd like to create an item
   record in Koha. If you choose to add an item record when 'placing an
   order' then you will enter item information in as you place records
   in your basket. If you choose to add the item when 'receiving an
   order' you will be asked for item record information when you're
   receiving orders in acquisitions. If you choose to add the item when
   'cataloging a record' then item records will not be created in
   acquisitions at all, you will need to go to the cataloging module to
   add the items.

`AcqEnableFiles <#AcqEnableFiles>`__
''''''''''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ enable the ability to upload and attach arbitrary files to
invoices.

Values:

-  Do

-  Don't

Description:

-  This preference controls whether or not you allow the uploading of
   invoice files via the acquisitions module.

`AcqItemSetSubfieldsWhenReceiptIsCancelled <#AcqItemSetSubfieldsWhenReceiptIsCancelled>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Upon cancelling a receipt, update the item's subfields if they
were created when placing an order (e.g. o=5\|a="bar foo""). \_\_\_

Description:

-  This preference is used in conjunction with the
   :ref:`AcqItemSetSubfieldsWhenReceived`
   preference. If you have the system set to enter default values when
   you receive you will want to have those values revert back if reeipt
   is cancelled. This preference allows you to do that.

`AcqItemSetSubfieldsWhenReceived`
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Upon receiving items, update their subfields if they were created
when placing an order (e.g. o=5\|a="foo bar"). \_\_\_

Description:

-  This preference allows you to set default values for items that you
   receive via acquisitions. Enter the data as subfield=value and split
   your values with a bar ( \| ). For example you can remove the Ordered
   status on the item automatically when you receive it just by entering
   7=0 in this preference. That will set the Not for Loan status
   (subfield 7) to 0 which is available.

`AcqViewBaskets <#AcqViewBaskets>`__
''''''''''''''''''''''''''''''''''''

Default: created by staff member

Asks: Show baskets \_\_\_

Values:

-  created by staff member

-  from staff member's branch

-  in system, regardless of owner

Description:

-  When in acquisitions this preference allows you to control whose
   baskets you can see when looking at a vendor. The default value of
   'created by staff member' makes it so that you only see the baskets
   you created. Choosing to see baskets 'from staff member's branch'
   will show you the baskets created by anyone at the branch you're
   logged in at. Finally, you can choose to set this preference to show
   you all baskets regardless of who created it ('in system, regardless
   of owner). Regardless of which value you choose for this preference,
   superlibrarians can see all baskets created in the system.

`AcqWarnOnDuplicateInvoice <#AcqWarnOnDuplicateInvoice>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Do not warn

Asks: \_\_\_ when the librarian tries to create an invoice with a
duplicate number.

Values:

-  Do not warn

-  Warn

`BasketConfirmations <#BasketConfirmations>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: always ask for confirmation

Asks: When closing or reopening a basket, \_\_\_.

Values:

-  always ask for confirmation

-  do not ask for confirmation

Descriptions:

-  This preference adds the option to skip confirmations on closing and
   reopening a basket. If you skip the confirmation, you do not create a
   new basket group.

`ClaimsBccCopy <#ClaimsBccCopy>`__
''''''''''''''''''''''''''''''''''

Default: Don't send

Asks: \_\_\_ blind copy (BCC) to logged in user when sending serial or
acquisitions claims notices.

Values:

-  Don't send

-  Send

Description:

-  When filing a claim in the :ref:`Claim Late Serials` or
   Acquisitions module this preference will allow for
   the sending of a copy of the email to the librarian.

`CurrencyFormat <#CurrencyFormat>`__
''''''''''''''''''''''''''''''''''''

Default: 360,000.00 (US)

Asks: Display currencies using the following format \_\_\_

Values:

-  360,000.00 (US)

-  360 000,00 (FR)

`gist <#gist>`__
''''''''''''''''

Default: 0

Asks: The default tax rate is \_\_\_

Description:

-  This preference will allow the library to define a default Goods and
   Services Tax rate. The default of value of 0 will disable this
   preference.

    **Note**

    Enter this value as a number (.06) versus a percent (6%).

`MarcFieldsToOrder <#MarcFieldsToOrder>`__
''''''''''''''''''''''''''''''''''''''''''

Asks: Set the mapping values for a new order line created from a MARC
record in a staged file.

Description:

-  This preference includes MARC fields to check for order information
   to use when you are trying to :ref:`Order from a staged file` in
   acquisitions. You can use the following fields: price, quantity,
   budget\_code, discount, sort1, sort2.

   For example:

   ::

       price: 947$a|947$c
       quantity: 969$h
       budget_code: 922$a

`MarcItemFieldsToOrder <#MarcItemFieldsToOrder>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Set the mapping values for new item records created from a MARC record
in a staged file.

`UniqueItemFields <#UniqueItemFields>`__
''''''''''''''''''''''''''''''''''''''''

Default: barcode

Asks:\_\_\_ (space-separated list of fields that should be unique for
items, must be valid SQL fields of
`items <http://schema.koha-community.org/tables/items.html>`__ table)

Description:

-  If this preference is left blank when adding items in acquisitions
   there will be no check for uniqueness. This means that a duplicate
   barcode can be created in acquisitions which will cause errors later
   when checking items in and out.

`Printing <#acqprefsprinting>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`OrderPdfFormat <#OrderPdfFormat>`__
''''''''''''''''''''''''''''''''''''

Default: pdfformat::layout2pages

Asks: Use \_\_\_ when printing basket groups.

`Administration <#adminprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

These preferences are general settings for your system.

*Get there:* More > Administration > Global System Preferences >
Administration

`CAS Authentication <#casauthentication>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The Central Authentication Service (CAS) is a single sign-on protocol
for the web. If you don't know what this is, leave these preferences set
to their defaults.

`casAuthentication <#casAuthentication>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't use

Asks: \_\_\_ CAS for login authentication.

`casLogout <#casLogout>`__
''''''''''''''''''''''''''

Default: Don't logout

Asks: \_\_\_ of CAS when logging out of Koha.

`casServerUrl <#casServerUrl>`__
''''''''''''''''''''''''''''''''

Asks: The CAS Authentication Server can be found at \_\_\_

`Google OpenID Connect <#googleopenid>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Visit the `Google Developers
Console <https://console.developers.google.com/>`__ to obtain OAuth 2.0
credentials such as a client ID and client secret that are known to both
Google and your application.Developers Console

-  Create a project, and give it some details to help you identify it
   later

   New Project
   |image5|

-  Next search for the Google Identity and Access Management API

   API Search
   |image6|

-  Enable the Google Identity and Access Management API

   Enable Google Identity
   |image7|

-  Go to 'Credentials' and set the OAuth cosent screen values

   OAuth Consent Screen
   |image8|

-  Next choose to 'Create credentials' from the 'Credentials' page

   Create credentials
   |image9|

-  Choose 'Web application' from the 'Application type' menu and fill in
   the form presented

   Create Client ID
   |image10|

   -  Set 'Authorized JavaScript origins' to your OPACBaseURL

   -  Change the 'Authorized Redirect URIs' to
      http://YOUROPAC/cgi-bin/koha/svc/auth/googleopenidconnect

-  You will be presented with your values for your client ID and your
   client secret after saving

   OAuth Client ID and Secret
   |image11|

`GoogleOAuth2ClientID <#GoogleOAuth2ClientID>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Google OAuth2 Client ID \_\_\_

`GoogleOAuth2ClientSecret <#GoogleOAuth2ClientSecret>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Google OAuth2 Client Secret \_\_\_

`GoogleOpenIDConnect <#GoogleOpenIDConnect>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't use

Asks \_\_\_ Google OpenID Connect login.

    **Important**

    You will need to select OAuth2 when creating an app in the google
    cloud console, and set the web origin to your\_opac\_url and the
    redirect url to
    your\_opac\_url/cgi-bin/koha/svc/auth/googleopenidconnect .

    Create Client ID
    |image12|

Values:

-  Don't use

-  Use

`GoogleOpenIDConnectDomain <#GoogleOpenIDConnectDomain>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Google OpenID Connect Restrict to domain (or subdomain of this
domain) \_\_\_.

    **Note**

    Leave blank for all google domains

`Interface options <#adminprefsinterface>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These preference are related to your Koha interface

`DebugLevel <#DebugLevel>`__
''''''''''''''''''''''''''''

Default: lots of

Asks: Show \_\_\_ debugging information in the browser when an internal
error occurs.

Values:

-  lots of - will show as much information as possible

-  no - will only show basic error messages

-  some - will show only some of the information available

Description:

-  This preference determines how much information will be sent to the
   user's screen when the system encounters an error. The most detail
   will be sent when the value level is set at 2, some detail will be
   sent when the value is set at 1, and only a basic error message will
   display when the value is set at 0. This setting is especially
   important when a system is new and the administration is interested
   in working out the bugs (errors or problems) quickly. Having detailed
   error messages makes quick fixes more likely in problem areas.

`DefaultToLoggedInLibraryCircRules <#DefaultToLoggedInLibraryCircRules>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: all libraries

Asks: When editing circulation rules show \_\_\_ the rules by default.

Values:

-  all libraries

-  logged in library's

Description:

-  This preference controls the default value in the branch pull down
   found at the top of the :ref:`Circulation and Fine
   Rules`.

`DefaultToLoggedInLibraryNoticesSlips <#DefaultToLoggedInLibraryNoticesSlips>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: all libraries

Asks: When editing notices and slips show the \_\_\_ notices and slips
by default.

Values:

-  all libraries

-  logged in library's

Description:

-  This preference controls the default value in the branch pull down
   found at the top of the :ref:`Notices & Slips` tool.

`DefaultToLoggedInLibraryOverdueTriggers <#DefaultToLoggedInLibraryOverdueTriggers>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: all libraries

Asks: When editing overdue notice/status triggers show the \_\_\_ rules
by default.

Values:

-  all libraries

-  logged in library's

Description:

-  This preference controls the default value in the branch pull down
   found at the top of the :ref:`Overdue Notice/Status Triggers`.

`delimiter <#delimiter>`__
''''''''''''''''''''''''''

Default: semicolons

Asks: Separate columns in an exported report file with \_\_\_ by
default.

Values:

-  #'s

-  backslashes

-  commas

-  semicolons

-  slashes

-  tabs

Description:

-  This preference determines how reports exported from Koha will
   separate data. In many cases you will be able to change this option
   when exporting if you'd like.

`KohaAdminEmailAddress <#KohaAdminEmailAddress>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

This is the default 'From' address for emails unless there is one for
the particular branch, and is referred to when an internal error occurs.

Asks: Use \_\_\_ as the email address for the administrator of Koha.

Description:

-  This preference allows one email address to be used in warning
   messages set to the OPAC. If no email address is set for the branch
   this address will receive messages from patrons regarding
   modification requests, purchase suggestions, and questions or
   information regarding overdue notices. It is recommended that a email
   address that can be accessed by multiple staff members be used for
   this purpose so that if one librarian is out the others can address
   these requests. This email address can be changed when needed.

`noItemTypeImages <#noItemTypeImages>`__
''''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ itemtype icons in the catalog.

Values:

-  Shows

-  Don't show

Description:

-  This preference allows the system administrator to determine if users
   will be able to set and see an :ref:`item type icon`
   the catalog on both the OPAC and the Staff Client. The images will
   display in both the OPAC and the Staff Client/Intranet. If images of
   item types are disabled, text labels for item types will still appear
   in the OPAC and Staff Client.

`ReplytoDefault <#ReplytoDefault>`__
''''''''''''''''''''''''''''''''''''

Asks: Use \_\_\_ as the email address that will be set as the replyto in
emails

Description:

-  By default replies to notice emails will go to the `library email
   address <#libraries-groups>`__, if you would like to specify a default
   email address for all replies to notices you can do that here.

`ReturnpathDefault <#ReturnpathDefault>`__
''''''''''''''''''''''''''''''''''''''''''

Asks: Use \_\_\_ as the email address set as the return path, if you
leave this empty the KohaAdminEmailAddress will be used.

Description:

-  The return path is the email address that bounces will be delivered
   to. By default bounced notices will go to the `library email
   address <#libraries-groups>`__, if you would like to specify a default
   email address for bounces to go to then fill in this preference.

`virtualshelves <#virtualshelves>`__
''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff and patrons to create and view saved lists of books.

Values:

-  Allow

-  Don't Allow

Description:

-  This preference controls whether the lists functionality will be
   available in the staff client and OPAC. If this is set to "Don't
   allow" then no one will be able to save items to public or private
   lists.

`Login options <#adminprefslogin>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These preferences are related to logging into your Koha system

`AutoLocation <#AutoLocation>`__
''''''''''''''''''''''''''''''''

Default: Don't require

Asks: \_\_\_ staff to log in from a computer in the IP address range
specified by their library (if any).

-  Set IP address range in the library administration area

   -  *Get there:* More > Administration > Basic Parameters > :ref:`Libraries & Groups`

Values:

-  Don't require

-  Require

Description:

-  This preference protects the system by blocking unauthorized users
   from accessing the staff client program and settings. Authorized and
   unauthorized users are determined by their computer's IP addresses.
   When the preference is set to 'Require', IP authorization is in
   effect and unauthorized IP addresses will be blocked. This means that
   staff cannot work from home unless their IP address has been
   authorized. When set to 'Don't require', anyone with a staff client
   login will have access no matter which IP address they are using.

`IndependentBranches <#IndependentBranches>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't prevent

Asks: \_\_\_ staff (but not superlibrarians) from modifying objects
(holds, items, patrons, etc.) belonging to other libraries.

Values:

-  Don't prevent

-  Prevent

Description:

-  This preference should only be used by library systems which are
   sharing a single Koha installation among multiple branches but are
   considered independent organizations, meaning they do not share
   material or patrons with other branches and do not plan to change
   that in the future. If set to 'Prevent' it increases the security
   between library branches by: prohibiting staff users from logging
   into another branch from within the staff client, filtering out
   patrons from patron searches who are not a part of the login branch
   conducting the search, limiting the location choices to the login
   branch when adding or modifying an item record, preventing users from
   other branch locations from placing holds or checking out materials
   from library branches other than their own, and preventing staff from
   editing item records which belong to other library branches. All of
   these security safeguards can be overridden only by the
   superlibrarian, the highest level of privileges.

    **Important**

    It is important that this value be set before going live and that it
    NOT be changed

`IndependentBranchesPatronModifications <#IndependentBranchesPatronModifications>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: No

Asks: Prevent staff (but not superlibrarians) from viewing and
approving/denying patron modification requests for patrons
belonging to other libraries. \_\_\_

Values:

-  No

-  Yes

`SessionRestrictionByIP <#SessionRestrictionByIP>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Enable

Asks: \_\_\_ check for change in remote IP address for session security.
Disable only when remote IP address changes frequently.

Values:

-  Disable

-  Enable

Description:

-  When this preference is set to 'Enable' Koha will log you out of the
   staff client if your IP address changes as a security measure. For
   some systems the IP address changes frequently so you'll want to set
   this preference to 'Disable' to prevent Koha from logging you out of
   the staff client every time that happens.

    **Important**

    This is meant to help those whose IP address changes several times
    during the day, setting this preference to 'Disable' is not
    recommended otherwise because it is removing important security
    features from your staff client.

`SessionStorage <#SessionStorage>`__
''''''''''''''''''''''''''''''''''''

Default: in the MySQL database

Asks: Store login session information \_\_\_

Values:

-  as temporary files

-  in the MySQL database

-  in the PostgreSQL database

   -  **Important**

          PostgreSQL is not yet supported

Description:

-  This preference allows administrators to choose what format session
   data is stored in during web sessions.

`timeout <#timeout>`__
''''''''''''''''''''''

Default: 12000000

Asks: Automatically log out users after \_\_\_ seconds of inactivity.

Description:

-  This preference sets the length of time the Staff Client or OPAC
   accounts can be left inactive before re-logging in is necessary. The
   value of this preference is in seconds. At this time, the amount of
   time before a session times out must be the same for both the Staff
   Client and the OPAC.

`SSL client certificate authentication <#sslclientcertificateauthenticationprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AllowPKIAuth <#AllowPKIAuth>`__
''''''''''''''''''''''''''''''''

Default: no

Asks: Use \_\_\_ field for SSL client certificate authentication

Values:

-  no

-  the common name

-  the email address

`Search Engine <#searchengineprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`SearchEngine <#SearchEngine>`__
''''''''''''''''''''''''''''''''

Default: Zebra

Asks: Use following search engine: \_\_\_

Values:

-  Elasticsearch

-  Zebra

`Share anonymous usage statistics <#heaprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

As an open source project Koha is used all over the world. These
preference will help us keep more accurate statistics on where Koha is
being used. If you choose to share your information, it will be
published on the `Hea Koha community
website <http://hea.koha-community.org>`__. You will need to enable the
:ref:`Share Usage Stats` cronjob to send this information at regular
intervals to the community.

`UsageStats <#UsageStats>`__
''''''''''''''''''''''''''''

Default: Don't share

Asks: \_\_\_ anonymous Koha usage data with the Koha community.

Values:

-  Don't share

-  Share

Description:

-  This data is stored to help track usage of Koha around the world. If
   you choose to share your information, it will be published on the
   `Hea Koha community website <http://hea.koha-community.org>`__. This
   information is sent using the :ref:`Share Usage Stats` cronjob.

`UsageStatsCountry <#UsageStatsCountry>`__
''''''''''''''''''''''''''''''''''''''''''

Asks: The country where your library is located: \_\_\_

Description:

-  This data is stored to help track usage of Koha around the world. If
   you choose to share your information, it will be published on the
   `Hea Koha community website <http://hea.koha-community.org>`__. This
   information is sent using the :ref:`Share Usage Stats` cronjob.

    **Important**

    This preference depends on the `UsageStats <#usagestats>`__
    preference. Set that to 'Share' to share your information.

`UsageStatsGeolocation <#UsageStatsGeolocation>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: blank

Asks: Geolocation of the main library: \_\_\_ Note that this value has no effect
if the `UsageStats <#UsageStats>`__ systemp preference is set to "Don't share"

`UsageStatsLibrariesInfo <#UsageStatsLibrariesInfo>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Do not Share

Asks: \_\_\_ libraries information (name, url, country) Note that this value
has no effect if the `UsageStats <#UsageStats>`__ system preference is set to
"Don't share"

Values:

-  Do not Share

-  Share

`UsageStatsLibraryName <#UsageStatsLibraryName>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: The library name \_\_\_ will be shown on the `Hea Koha community
website <http://hea.koha-community.org>`__.

Description:

-  This data is stored to help track usage of Koha around the world. If
   you choose to share your information, it will be published on the
   `Hea Koha community website <http://hea.koha-community.org>`__. This
   information is sent using the :ref:`Share Usage Stats` cron job.

    **Important**

    This preference depends on the `UsageStats <#usagestats>`__
    preference. Set that to 'Share' to share your information. If this
    field is empty data will be sent anonymously if you choose 'Share'
    for the `UsageStats <#usagestats>`__ preference.

`UsageStatsLibraryType <#UsageStatsLibraryType>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: public

Asks: The library type \_\_\_ will be shown on the `Hea Koha community
website <http://hea.koha-community.org>`__.

Values:

-  academic

-  corporate

-  government

-  private

-  public

-  religious organization

-  research

-  school

-  society or association

-  subscription

Description:

-  This data is stored to help track usage of Koha around the world. If
   you choose to share your information, it will be published on the
   `Hea Koha community website <http://hea.koha-community.org>`__. This
   information is sent using the :ref:`Share Usage Stats` cronjob.

    **Important**

    This preference depends on the `UsageStats <#usagestats>`__
    preference. Set that to 'Share' to share your information.

`UsageStatsLibraryUrl <#UsageStatsLibraryUrl>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Asks: The library URL \_\_\_ will be shown on the `Hea Koha community
website <http://hea.koha-community.org>`__.

Description:

-  This data is stored to help track usage of Koha around the world. If
   you choose to share your information, it will be published on the
   `Hea Koha community website <http://hea.koha-community.org>`__. This
   information is sent using the :ref:`Share Usage Stats` cronjob.

    **Important**

    This preference depends on the `UsageStats <#usagestats>`__
    preference. Set that to 'Share' to share your information.

`Authorities <#authprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences >
Authorities

`General <#generalauthorities>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AuthDisplayHierarchy <#AuthDisplayHierarchy>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't display

Asks: \_\_\_ broader term/narrower term hierarchies when viewing
authorities.

Values:

-  Display

   AuthDisplayHierarchy
   |image14|

-  Don't display

Description:

-  If your authority records includes 5xx fields with linked references
   to broader and/or narrower see also references this preference will
   turn on a display of those authorities at the top of the record.

`AuthorityMergeLimit <#AuthorityMergeLimit>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: 50

Asks: When modifying an authority record, do not update attached biblio
records if the number exceeds \_\_\_ records. (Above this limit, the merge_authority
cron job will merge them.)

`AuthorityMergeMode <#AuthorityMergeMode>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: loose

Asks: When updating biblio records from an attached authority record ("merging"),
handle subfields of relevant biblio record fields in \_\_\_ mode. In strict mode
subfields that are not found in the authority record, are deleted. Loose mode
will keep them. Loose mode is the historical behavior and still the default.

Values:

-  loose

-  strict

`AutoCreateAuthorities <#AutoCreateAuthorities>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: do not generate

Asks: When editing records, \_\_\_ authority records that are missing.

Values:

-  do not generate

-  generate

    **Important**

    `BiblioAddsAuthorities <#biblioaddsauthorities>`__ must be set to
    "allow" for this to have any effect

Description:

-  When this and `BiblioAddsAuthorities <#biblioaddsauthorities>`__ are
   both turned on, automatically create authority records for headings
   that don't have any authority link when cataloging. When
   BiblioAddsAuthorities is on and AutoCreateAuthorities is turned off,
   do not automatically generate authority records, but allow the user
   to enter headings that don't match an existing authority. When
   BiblioAddsAuthorities is off, this has no effect.

`BiblioAddsAuthorities <#BiblioAddsAuthorities>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: allow

Asks: When editing records, \_\_\_ them to automatically create new
authority records if needed, rather than having to reference existing
authorities.

Values:

-  allow

   -  This setting allows you to type values in the fields controlled by
      authorities and then adds a new authority if one does not exist

-  don't allow

   -  This setting will lock the authority controlled fields, forcing
      you to search for an authority versus allowing you to type the
      information in yourself.

`MARCAuthorityControlField008 <#MARCAuthorityControlField008>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: \|\| aca\|\|aabn \| a\|a d

Asks: Use the following text for the contents of MARC21 authority
control field 008 position 06-39 (fixed length data elements).

    **Important**

    Do not include the date (position 00-05) in this preference, Koha
    will calculate automatically and put that in before the values in
    this preference.

Description:

-  This preference controls the default value in the 008 field on
   Authority records. It does not effect bibliographic records.

`UNIMARCAuthorityField100 <#UNIMARCAuthorityField100>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: afrey50 ba0

Asks: Use the following text for the contents of UNIMARC authority field
100 position (fixed length data elements).

    **Important**

    Do not include the date (position 00-07) in this preference, Koha
    will calculate automatically and put that in before the values in
    this preference.

Description:

-  This preference controls the default value in the 100 field on
   Authority records cataloged in UNIMARC. It does not effect
   bibliographic records.

`UseAuthoritiesForTracings <#UseAuthoritiesForTracings>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't use

Asks: \_\_\_ authority record numbers instead of text strings for
searches from subject tracings.

Values:

-  Don't use

   -  Search links look for subject/author keywords (example:
      opac-search.pl?q=su:Business%20networks)

-  Use

   -  Search links look for an authority record (example:
      opac-search.pl?q=an:354)

Description:

-  For libraries that have authority files, they may want to make it so
   that when a link to an authorized subject or author is clicked on the
   OPAC or staff client it takes the searcher only to a list of results
   with that authority record. Most libraries do not have complete
   authority files and so setting this preference to 'Don't use' will
   allow searchers to click on links to authors and subject headings and
   perform a keyword search against those fields, finding all possible
   relevant results instead.

`Linker <#linkerauthorities>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These preferences will control how Koha links bibliographic records to
authority records. All bibliographic records added to Koha after these
preferences are set will link automatically to authority records, for
records added before these preferences are set there is a script
(misc/link\_bibs\_to\_authorities.pl) that your system administrator can
run to link records together.

`CatalogModuleRelink <#CatalogModuleRelink>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Do not

Asks: \_\_\_ automatically relink headings that have previously been
linked when saving records in the cataloging module.

Values:

-  Do

-  Do not

Description:

-  Longtime users of Koha don't expect the authority and bib records to
   link consistently. This preference makes it possible to disable
   authority relinking in the cataloging module only (i.e. relinking is
   still possible if link\_bibs\_to\_authorities.pl is run). Note that
   though the default behavior matches the previous behavior of Koha
   (retaining links to outdated authority records), it does not match
   the intended behavior (updating biblio/authority link after
   bibliographic record is edited). Libraries that want the intended
   behavior of authority control rather than the way Koha used to handle
   linking should set CatalogModuleRelink to 'Do'. Once setting this to
   'Do' the following preferences can also be set.

`LinkerKeepStale <#LinkerKeepStale>`__
''''''''''''''''''''''''''''''''''''''

Default: Do not

Asks: \_\_\_ keep existing links to authority records for headings where
the linker is unable to find a match.

Values:

-  Do

-  Do not

Description:

-  When set to 'Do', the linker will never remove a link to an authority
   record, though, depending on the value of
   `LinkerRelink <#LinkerRelink>`__, it may change the link.

`LinkerModule <#LinkerModule>`__
''''''''''''''''''''''''''''''''

Default: Default

Asks: Use the \_\_\_ linker module for matching headings to authority
records.

Values:

-  Default

   -  Retains Koha's previous behavior of only creating links when there
      is an exact match to one and only one authority record; if the
      `LinkerOptions <#LinkerOptions>`__ preference is set to
      'broader\_headings', it will try to link headings to authority
      records for broader headings by removing subfields from the end of
      the heading

-  First match

   -  Creates a link to the first authority record that matches a given
      heading, even if there is more than one authority record that
      matches

-  Last match

   -  Creates a link to the last authority record that matches a given
      heading, even if there is more than one record that matches

Description:

-  This preference tells Koha which match to use when searching for
   authority matches when saving a record.

`LinkerOptions <#LinkerOptions>`__
''''''''''''''''''''''''''''''''''

Asks: Set the following options for the authority linker \_\_\_

    **Important**

    This feature is experimental and shouldn't be used in a production
    environment until further expanded upon.

Description:

-  This is a pipe separated (\|) list of options. At the moment, the
   only option available is "broader\_headings." With this option set to
   "broader\_headings", the linker will try to match the following
   heading as follows:

   ::

       =600 10$aCamins-Esakov, Jared$xCoin collections$vCatalogs$vEarly works to 1800.

   First: Camins-Esakov, Jared--Coin collections--Catalogs--Early works
   to 1800

   Next: Camins-Esakov, Jared--Coin collections--Catalogs

   Next: Camins-Esakov, Jared--Coin collections

   Next: Camins-Esakov, Jared (matches! if a previous attempt had
   matched, it would not have tried this)

`LinkerRelink <#LinkerRelink>`__
''''''''''''''''''''''''''''''''

Default: Do

Asks: \_\_\_ relink headings that have previously been linked to
authority records.

Values:

-  Do

-  Do not

Description:

-  When set to 'Do', the linker will confirm the links for headings that
   have previously been linked to an authority record when it runs,
   correcting any incorrect links it may find. When set to 'Do not', any
   heading with an existing link will be ignored, even if the existing
   link is invalid or incorrect.

`Cataloging <#catprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences >
Cataloging

`Display <#catdisplayprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AcquisitionDetails <#AcquisitionDetails>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Display

Asks: \_\_\_ acquisition details on the biblio detail page.

Values:

-  Display

-  Don't display

Description:

-  This preference controls whether a tab will show on the detail page
   in the staff client that includes detailed acquisitions information
   for the title. This tab will include links to order information
   stored in the acquisitions module.

`AuthoritySeparator <#authoritysep>`__
''''''''''''''''''''''''''''''''''''''

Default: --

Asks: Separate multiple displayed authors, series or subjects with
\_\_\_.

`hide\_marc <#hide_marc>`__
'''''''''''''''''''''''''''

Default: Display

Asks: \_\_\_ MARC tag numbers, subfield codes and indicators in MARC
views.

Values:

-  Display -- shows the tag numbers on the cataloging interface

   MARC editor with tags showing
   |image15|

-  Don't display -- shows just descriptive text when cataloging

   MARC editor without tags showing
   |image16|

`IntranetBiblioDefaultView <#IntranetBiblioDefaultView>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: ISBD form

Asks: By default, display biblio records in \_\_\_

Values:

-  ISBD form -- displays records in the staff client in the old card
   catalog format

   -  See `ISBD <#isbdpref>`__ preference for more information

-  Labelled MARC form -- displays records in the staff client in MARC
   with text labels to explain the different fields

-  MARC form -- displays records in the staff client in MARC

-  normal form -- visual display in the staff client (for the average
   person)

Description:

-  This setting determines the bibliographic record display when
   searching the catalog on the staff client. This setting does not
   affect the display in the OPAC which is changed using the
   `BiblioDefaultView <#BiblioDefaultView>`__ preference under the OPAC
   preference tab. This setting changes the look of the record when
   first displayed. The MARC and ISBD views can still be seen by
   clicking in the sidebar.

`ISBD <#isbdpref>`__
''''''''''''''''''''

Default: `MARC21 Default Appendix <#isbddefault>`__ or `UNIMARC Default
Appendix <#unimarcdefault>`__

Asks: Use the following as the ISBD template:

Description:

-  This determines how the ISBD information will display in the staff
   client. Elements in the list can be reordered to produce a different
   ISBD view. ISBD, the International Standard Bibliographic
   Description, was first introduced by IFLA (International Federation
   of Library Associations) in 1969 in order to provide guidelines for
   descriptive cataloging. The purpose of ISBD is to aid the
   international exchange of bibliographic records for a variety of
   materials.

`LabelMARCView <#LabelMARCView>`__
''''''''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ collapse repeated tags of the same type into one tag entry.

Values:

-  Do -- will combine all identical tag numbers under one heading in the
   MARC view in the OPAC and Staff Client

   MARC View in the Staff Client with LabelMARCView set to Do
   |image17|

-  Don't -- will list all of the tags individually in the MARC view in
   the OPAC and Staff Client

   MARC View in the Staff Client with LabelMARCView set to Don't
   |image18|

`MergeReportFields <#MergeReportFields>`__
''''''''''''''''''''''''''''''''''''''''''

Asks: \_\_\_ fields to display for deleted records after merge

Description:

-  When merging records together you can receive a report of the merge
   process once it's done, this preference lets you set the default
   values for this report.

Example: '001,245ab,600' displays:

-  value of 001

-  subfields a and b of fields 245

-  all subfields of fields 600

`NotesBlacklist <#NotesBlacklist>`__
''''''''''''''''''''''''''''''''''''

Asks: Don't show these \_\_\_ note fields in title notes separator (OPAC
record details) and in the description separator (Staff client record
details).

Description:

-  This preference lets you define which of your note fields are hidden
   from the title notes (OPAC) and descriptions (Staff) tabs. Enter the
   values as a comma separated list. For example to hide the local note
   and the bibliography note in MARC21 enter 504, 590.

`OpacSuppression, OpacSuppressionByIPRange, OpacSuppressionRedirect, and OpacSuppressionMessage <#OpacSuppression>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

OpacSuppression Default: Don't hide

Asks: \_\_\_ items marked as suppressed from OPAC search results. Note
that you must have the Suppress index set up in Zebra and at least one
suppressed item, or your searches will be broken. Restrict the
suppression to IP adresses outside of the IP range \_\_\_ (Leave blank
if not used. Define a range like 192.168..) Redirect the opac detail
page for suppressed records to \_\_\_ Display the following message on
the redirect page for suppressed biblios \_\_\_.

OpacSuppression Values:

-  Don't hide

   -  Will show records in OPAC search results if they are marked
      suppressed

-  Hide

   -  Will not show records in OPAC search results if they're marked as
      suppressed

OpacSuppressionRedirect Values:

-  an explanatory page ('This record is blocked').

-  the 404 error page ('Not found').

Description:

-  These preferences control hiding of bibliographic records from
   display in the OPAC. Each bibliogrphic record you want to hide from
   the OPAC simply needs to have the value "1" in the field mapped with
   Suppress index (942$n field in MARC21, no official field in UNIMARC).
   The indexer then hides it from display in OPAC but will still display
   it in the Staff Client. If you want to further control suppression
   you can set an IP address range to still show suppressed items to.
   Define a range like 192.168.. If you don't want to limit suppression
   in this way, leave the IP field blank. You can also decide what the
   patrons will see in the OPAC when a title is suppressed by setting
   the OpacSuppressionRedirect and OpacSuppressionMessage preferences.
   You can either show the patron a 404 page if they try to see a
   suppressed record or you can create a custom page by entering the
   HTML in the OpacSuppressionMessage part of this preference.

       **Note**

       An `authorized value <#authorizedvalues>`__ for the MARC21 942$n
       field (or the equivalent UNIMARC field) should be set to
       eliminate errors. One example would be to create an authorized
       value titled SUPPRESS with a value of 0 for don't suppress and 1
       for suppress.

    **Important**

    If this preference is set to 'hide' and you have the 942n field set
    to 1, it will hide the entire bib record - not just an individual
    item.

    **Important**

    You must have the Suppress index set up in Zebra and at least one
    record with the value "1" in the field mapped with this index, or
    your searches will be completely broken in OPAC (you won't get any
    results at all).

    **Note**

    Suppressed records will show a note in the staff client indicating
    that they are suppressed from view in the OPAC.Suppressed in Staff

    This note can be styled by using the
    `IntranetUserCSS <#IntranetUserCSS>`__ preference to stand out more
    if you'd like.Style suppression note

`SeparateHoldings & SeparateHoldingsBranch <#SeparateHoldings>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

SeparateHoldings default: Don't separate

SeparateHoldingsBranch default: home library

Asks: \_\_\_ items display into two tabs, where the first tab contains
items whose \_\_\_ is the logged in user's library. The second tab will
contain all other items.

SeparateHoldings values:

-  Don't separate

-  Separate

SeparateHoldingsBranch values:

-  holding library

-  home library

Description:

-  This preference lets you decide if you would like to have the holding
   information on the bibliographic detail page in the staff client
   split in to multiple tabs. The default is to show all holdings on one
   tab.

   Separate holdings tabs
   |image19|

`URLLinkText <#URLLinkText>`__
''''''''''''''''''''''''''''''

Default: Online Resource

Asks: Show \_\_\_ as the text of links embedded in MARC records.

Description:

-  If the 856 field does not have a subfield 3 or y defined, the OPAC
   will say 'Click here to access online.' If you would like the field
   to say something else enter that in this field.

`UseControlNumber <#UseControlNumber>`__
''''''''''''''''''''''''''''''''''''''''

Default: Don't use

Asks: \_\_\_ record control number ($w subfields) and control number
(001) for linking of bibliographic records.

Values:

-  Don't use

   -  When clicking on links to titles that appear next to 'Continues'
      and 'Continued by' in the detail display Koha will perform a title
      search

-  Use

   -  When clicking on links to titles that appear next to 'Continues'
      and 'Continued by' in the detail display Koha will perform a
      control number (MARC field 001) search

    **Important**

    Unless you are going in and manually changing 773$w to match your
    rigorously-defined bibliographic relationships, you should set this
    preference to "Don't use" and instead set
    `EasyAnalyticalRecords <#EasyAnalyticalRecords>`__ to "Display"

Description:

-  If you have a serial called "Journal of Interesting Things" which has
   a separate record from when it was called "Transactions of the
   Interesting Stuff Society," you could add linking fields to indicate
   the relationship between the two records. UseControlNumber allows you
   to use your local accession numbers for those links. In MARC21, the
   relevant sections of the two records might look like this:

   ::

           =001    12345
           =110  2_$aInteresting Stuff Society.
           =245  10$aTransactions of the Interesting Stuff Society.
           =785  00$aInteresting Stuff Society$tJournal of Interesting Things.$w12346

           =001    12346
           =110  2_$aInteresting Stuff Society.
           =245  10$aJournal of Interesting Things.
           =780  00$aInteresting Stuff Society$tTransactions of the Interesting Stuff Society.$w12345

   With UseControlNumber set to 'Use', the 78x links will use the
   Control Numbers is subfield $w, instead of doing a title search on
   "Journal of Interesting Things" and "Transactions of the Interesting
   Stuff Society" respectively.

`Exporting <#catexportprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`BibtexExportAdditionalFields <#BibtexExportAdditionalFields>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Include following fields when exporting BibTeX

Description:

-  Use one line per tag in the format BT\_TAG: TAG$SUBFIELD ( e.g. lccn:
   010$a )

-  To specificy multiple marc tags/subfields as targets for a repeating
   BibTex tag, use the following format: BT\_TAG: [TAG2$SUBFIELD1,
   TAG2$SUBFIELD2] ( e.g. notes: [501$a, 505$g] )

-  All values of repeating tags and subfields will be printed with the
   given BibTeX tag.

-  Use '@' ( with quotes ) as the BT\_TAG to replace the bibtex record
   type with a field value of your choosing.

`RisExportAdditionalFields <#RisExportAdditionalFields>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Include following fields when exporting RIS

Description:

-  Use one line per tag in the format RIS\_TAG: TAG$SUBFIELD ( e.g. LC:
   010$a )

-  To specificy multiple marc tags/subfields as targets for a repeating
   RIS tag, use the following format: RIS\_TAG: [TAG2$SUBFIELD1,
   TAG2$SUBFIELD2] ( e.g. NT: [501$a, 505$g] )

-  All values of repeating tags and subfields will be printed with the
   given RIS tag.

-  Use of TY ( record type ) as a key will *replace* the default TY with
   the field value of your choosing.

`Importing <#catimportprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AggressiveMatchOnISBN <#AggressiveMatchOnISBN>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: don't

Asks: When matching on ISBN with the record import tool, \_\_\_ attempt
to match aggressively by trying all variations of the ISBNs in the
imported record as a phrase in the ISBN fields of already cataloged
records.

Values:

-  do

-  don't

Description:

-  This preference allows you to choose to alter the ISBN matching rule
   used when staging records for import to be more aggressive. This
   means that all text will be stripped from the ISBN field so that a
   pure number match is possible. If this preference is set to "Don't"
   then Koha will find a match only if the ISBN fields are identical.

    **Important**

    Note that this preference has no effect if
    `UseQueryParser <#UseQueryParser>`__ is on.

`AggressiveMatchOnISSN <#AggressiveMatchOnISSN>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: don't

Asks: When matching on ISSN with the record import tool, \_\_\_ attempt
to match aggressively by trying all variations of the ISSNs in the imported
record as a phrase in the ISSN fields of already cataloged records. Note that
this preference has no effect if `UseQueryParser <#UseQueryParser>`__ is on.

`Interface <#catinterfaceprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`advancedMARCeditor <#advancedMARCeditor>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Don't display

Asks: \_\_\_ descriptions of fields and subfields in the MARC editor.

Description:

-  This preference determines whether or not MARC field names will be
   present when editing or creating MARC records.

Values:

-  Display

   MARC editor with text labels
   |image20|

-  Don't display

   MARC editor without text labels
   |image21|

`DefaultClassificationSource <#DefaultClassificationSource>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Dewey Decimal System

Asks: Use \_\_\_ as the default classification source.

Values:

-  ANSCR (Sound Recordings)

-  Dewey Decimal Classification

-  Library of Congress Classification

-  Other/Generic Classification Scheme

-  SuDoc Classification (U.S. GPO)

-  Universal Decimal Classification

    **Note**
    
    Adding another classification under Administration > Classification Sources
    will make it show up in this list as well.

`EasyAnalyticalRecords <#EasyAnalyticalRecords>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't Display

Asks: \_\_\_ easy ways to create analytical record relationships

Values:

-  Display

-  Don't Display

    **Important**

    If you decide to use this feature you'll want to make sure that your
    `UseControlNumber <#UseControlNumber>`__ preference is set to "Don't
    use" or else the "Show analytics" links in the staff client and the
    OPAC will be broken.

Description:

-  An analytic entry in a catalog is one that describes a part of a
   larger work that is also described in the catalog. In bibliographic
   cataloging, analytic entries may be made for chapters in books or
   special issues of articles in periodicals. In archival cataloging,
   analytic entries may be made for series or items within a collection.
   This feature in Koha allows for an easy way of linking analytic
   entries to the host records, and this system preference adds several
   new menu options to the staff cataloging detail pages to allow that
   to happen.

`Record Structure <#catrecordprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AlternateHoldingsField & AlternateHoldingsSeparator <#AlternateHoldingsField>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Display MARC subfield \_\_\_ as holdings information for records
that do not have items, with the subfields separated by \_\_\_.

Description:

-  Sometimes libraries migrate to Koha with their holding info in the
   852 field (OCLC holdings information field) and choose not to
   transfer that information into the 952 (Koha holdings information
   field) because they don't plan on circulating those items. For those
   libraries or other libraries that have data in the 852 fields of
   their records that they want to display, these preferences let you
   choose to display holdings info from a field other than the 952
   field. The AlternateHoldingsField preference can contain multiple
   subfields to look in; for instance 852abhi would look in 852
   subfields a, b, h, and i.

-  With AlternateHoldingsField set to 852abhi and
   AlternateHoldingsSeparator set to a space the holdings would look
   like the following:

   Alternate Holdings Display
   |image22|

`autoBarcode <#autoBarcode>`__
''''''''''''''''''''''''''''''

Default: generated in the form <branchcode>yymm0001

Asks: Barcodes are \_\_\_

Values:

-  generated in the form <branchcode>yymm0001

-  generated in the form <year>-0001, <year>-0002

-  generated in the form 1, 2, 3

-  incremental EAN-13 barcodes

-  not generated automatically

Description:

-  This setting is for libraries wishing to generate barcodes from
   within Koha (as opposed to scanning in pre-printed barcodes or
   manually assigning them). The default behavior makes it so that when
   you click in the barcode field (952$p in MARC21) it will populate
   with the automatic barcode you have chosen. If you would rather it
   only enter an automatic barcode when you click on the plugin (the ...
   to the right of the field) you can change the plugin used for that
   field in the framework. Set the plugin for 952$p (if using MARC21 or
   equivalent field mapped to items.barcode in your local MARC format)
   for your frameworks to barcode\_manual.pl instead of barcode.pl.
   Learn more about editing frameworks under the `MARC Bibliographic
   Frameworks <#marcbibframeworks>`__ section of this manual.

`DefaultLanguageField008 <#DefaultLanguageField008>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Empty defaults to eng

Asks: Fill in the default language for field 008 Range 35-37 of MARC21
records \_\_\_.

Description:

-  This preference will allow you to set the language for your MARC21
   008 field by default. If this is left empty it will default to
   English (eng). See the `MARC Code List for
   Languages <http://www.loc.gov/marc/languages/language_code.html>`__
   for additional values for this preference.

    **Note**

    This preference won't have any effect if your records are in
    UNIMARC.

`item-level\_itypes <#item-level_itypes>`__
'''''''''''''''''''''''''''''''''''''''''''

Default: specific item

Asks: Use the item type of the \_\_\_ as the authoritative item type
(for determining circulation and fines rules, etc).

Values:

-  biblio record

-  specific item

Description:

-  This preference determines whether the item type Koha uses for
   issuing rules will be an attribute of the bibliographic record or the
   item record. Most libraries refer to the item record for item types.
   It also determines if the item type icon appears on the OPAC search
   results. If you have the preference set to 'biblio record' then Koha
   displays the item type icon on the search results to the left of the
   result info.

   Item Type Icons to the Left of Result Information
   |image23|

`itemcallnumber <#itemcallnumber>`__
''''''''''''''''''''''''''''''''''''

Default: 082ab

Asks: Map the MARC subfield to an item's callnumber.

    **Note**

    This can contain multiple subfields to look in; for instance 082ab
    would look in 082 subfields a and b.

Description:

-  This setting determines which MARC field will be used to determine
   the call number that will be entered into item records automatically
   (952$o). The value is set by providing the MARC field code (050, 082,
   090, 852 are all common in MARC21) and the subfield codes without the
   delimiters ($a, $b would be ab).

Examples:

-  Dewey: 082ab or 092ab; LOC: 050ab or 090ab; from the item record:
   852hi

`marcflavour <#marcflavour>`__
''''''''''''''''''''''''''''''

Default: MARC21

Asks: Interpret and store MARC records in the \_\_\_ format.

Values:

-  MARC21

   -  The standard style for the US, Canada, Australia, New Zealand,
      United Kingdom, Germany and other countries

-  UNIMARC

   -  The standard style used in France, Italy, Portugal, Russia, and
      other countries

-  NORMARC

   -  The standard style for Norway

Description:

-  This preference defines global MARC style (MARC21, UNIMARC or
   NORMARC) used for encoding.

    **Important**

    Changing the value of this preference will not convert your records
    from one MARC style to an other.

`MARCOrgCode <#MARCOrgCode>`__
''''''''''''''''''''''''''''''

Default: OSt

Asks: Fill in the MARC organization code \_\_\_ by default in new MARC21
records (leave blank to disable).

Description:

-  The MARC Organization Code is used to identify libraries with
   holdings of titles and more.

Learn more and find your library's MARC21 code on the `MARC Code list
for
Organizations <http://www.loc.gov/marc/organizations/orgshome.html>`__
or in Canada on the `Canadian Symbols
Directory <http://www.collectionscanada.gc.ca/illcandir-bin/illsear/l=0/c=1>`__.

    **Note**

    This preference won't have any effect if your records are in
    UNIMARC.

`NewItemsDefaultLocation <#NewItemsDefaultLocation>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: When items are created, give them the temporary location of \_\_\_
(should be a location code, or blank to disable).

`PrefillItem <#PrefillItem>`__
''''''''''''''''''''''''''''''

Default: the new item is not prefilled with last created item values.

Asks: When a new item is added \_\_\_

Values:

-  the new item is not prefilled with last created item values.

-  the new item is prefilled with last created item values.

Description:

-  This preference controls the behavior used when adding new items.
   Using the options here you can choose to have your next new item
   prefill with the values used in the last item was added to save time
   typing values or to have the item form appear completely blank. Using
   `SubfieldsToUseWhenPrefill <#SubfieldsToUseWhenPrefill>`__ you can
   control specifically which fields are prefilled.

`SubfieldsToAllowForRestrictedBatchmod <#SubfieldsToAllowForRestrictedBatchmod>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Define a list of subfields for which editing is authorized when
`items\_batchmod\_restricted <#items_batchmod_restricted>`__ permission
is enabled, separated by spaces. \_\_\_

Examples:

-  UNIMARC: "995$f 995$h 995$j"

-  MARC21: "952$a 952$b 952$c"

Description:

-  This preference lets you define what fields can be edited via the
   `batch item modification tool <#batchmodifyitems>`__ if the
   items\_batchmod\_restricted permission is enabled.

       **Note**

       The FA framework is excluded from the permission. If the pref is
       empty, no fields are restricted.

`SubfieldsToAllowForRestrictedEditing <#SubfieldsToAllowForRestrictedEditing>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Define a list of subfields for which editing is authorized when
edit\_items\_restricted permission is enabled, separated by spaces.
\_\_\_

Examples:

-  UNIMARC: "995$f 995$h 995$j"

-  MARC21: "952$a 952$b 952$c"

Description:

-  This preference lets you define what fields can be edited via
   cataloging if the
   `edit\_items\_restricted <#edit_items_restricted>`__ permission is
   enabled

       **Note**

       The Fast Add (FA) framework is excluded from the permission. If
       the pref is empty, no fields are restricted.

`SubfieldsToUseWhenPrefill <#SubfieldsToUseWhenPrefill>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Define a list of subfields to use when prefilling items \_\_\_

    **Important**

    Separate values with a space.

Description:

-  When the `PrefillItem <#PrefillItem>`__ preference is set to prefill
   item values with those from the last added item, this preference can
   control which fields are prefilled (and which are not). Enter a space
   separated list of fields that you would like to prefill when adding a
   new item.

`UNIMARCField100Language <#UNIMARCField100Language>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: fre

Asks: Use the language (ISO 690-2) \_\_\_ as default language in the
UNIMARC field 100 when creating a new record or in the field plugin.

`z3950NormalizeAuthor & z3950AuthorAuthFields <#z3950NormalizeAuthor>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Defaults: Don't copy & 701,702,700

Asks: \_\_\_ authors from the UNIMARC \_\_\_ tags (separated by commas)
to the correct author tags when importing a record using Z39.50.

Description for z3950NormalizeAuthor:

-  This preference allows for 'Personal Name Authorities' to replace
   authors as the bibliographic authority. This preference should only
   be considered by libraries using UNIMARC.

Values for z3950NormalizeAuthor:

-  Copy

-  Don't copy

Description for z3950AuthorAuthFields:

-  This preference defines which MARC fields will be used for 'Personal
   Name Authorities' to replace authors as the bibliographic
   authorities. This preference only applies to those using UNIMARC
   encoding. The MARC fields selected here will only be used if
   'z3950NormalizeAuthor' is set to "Copy". The default field are 700,
   701, and 702.

`Spine Labels <#catspineprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`SpineLabelAutoPrint <#SpineLabelAutoPrint>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: don't

Asks: When using the quick spine label printer, \_\_\_ automatically pop
up a print dialog.

Values:

-  do

-  don't

`SpineLabelFormat <#SpineLabelFormat>`__
''''''''''''''''''''''''''''''''''''''''

Default: <itemcallnumber><copynumber>

Asks: Include the following fields on a quick-printed spine label:
(Enter in columns from the biblio, biblioitems or items tables,
surrounded by < and >.)

`SpineLabelShowPrintOnBibDetails <#SpineLabelShowPrintOnBibDetails>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't display

Asks: \_\_\_ buttons on the bib details page to print item spine labels.

Values:

-  Display

   'Print Label' link appears on bibliographic record in the staff
   client
   |image24|

-  Don't display

`Circulation <#circprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences >
Circulation




`Article Requests <#articlerequestsprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`ArticleRequests <#ArticleRequests>`__
''''''''''''''''''''''''''''''''''''''

Default: Don't enable

Asks: \_\_\_ patrons to place article requests.

Values:

-  Enable

-  Don't enable

Description:

-  This preference controls whether or not article requests are allowed to be placed by patrons in the OPAC.

`ArticleRequestsMandatoryFields <#ArticleRequestsMandatoryFields>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: None selected

Asks: For records that are record level or item level requestable, make the following fields mandatory \_\_\_

Values:

-  [Select all]

-  Author

-  Chapters

-  Date

-  Issue

-  Pages

-  Title

-  Volume

Description:

-  This preference controls what fields must be filled in before an article request can be placed
   for either a record level or item level request. Choosing [Select all] indicates that all fields
   listed (Author, Chapters, Date, Issue, Pages, Title, Volume) must be completed before the article
   request can be placed.

`ArticleRequestsMandatoryFieldsItemsOnly <#ArticleRequestsMandatoryFieldsItemsOnly>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: None selected

Asks: For records that are only item level requestable, make the following fields mandatory \_\_\_

Values:

-  [Select all]

-  Author

-  Chapters

-  Date

-  Issue

-  Pages

-  Title

-  Volume

Description:

-  This preference controls what fields must be filled in before an article request can be placed
   for an item level request only. Choosing [Select all] indicates that all fields
   listed (Author, Chapters, Date, Issue, Pages, Title, Volume) must be completed before the article
   request can be placed.

`ArticleRequestsMandatoryFieldsRecordOnly <#ArticleRequestsMandatoryFieldsRecordOnly>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: None selected

Asks: For records that are only record level requestable, make the following fields mandatory \_\_\_

Values:

-  [Select all]

-  Author

-  Chapters

-  Date

-  Issue

-  Pages

-  Title

-  Volume

Description:

-  This preference controls what fields must be filled in before an article request can be placed
   for a record level request only. Choosing [Select all] indicates that all fields
   listed (Author, Chapters, Date, Issue, Pages, Title, Volume) must be completed before the article
   request can be placed.


`Batch Checkout <#batchcheckoutprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`BatchCheckouts <#BatchCheckouts>`__
''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ batch checkouts

Values:

-  Allow

-  Don't allow

`BatchCheckoutsValidCategories <#BatchCheckoutsValidCategories>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Patron categories allowed to checkout in a batch \_\_\_ (list of
patron categories separated with a pipe '\|')

`Checkin Policy <#checkinpolicyprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`BlockReturnOfWithdrawnItems <#BlockReturnOfWithdrawnItems>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Block

Asks: \_\_\_ returning of items that have been withdrawn.

Values:

-  Block

-  Don't block

Description:

-  This preference controls whether and item with a withdrawn status
   (952$0 in MARC21) can be checked in or not.

`CalculateFinesOnReturn <#CalculateFinesOnReturn>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Do

Asks: \_\_\_ calculate and update overdue charges when an item is
returned.

Values:

-  Do

-  Don't

Description:

-  If this preference is set to "Do" and the `fines cron
   job <#finescronjob>`__ is off then Koha will calculate fines only
   when items are returned. If you have the fines cron job on and this
   preference set to "Do" then this preference will calculate fines
   based on the cron (usually run nightly) and then again when you check
   the item in. This option is best for those who are doing hourly
   loans. If this preference is set to "Don't" then fines will only be
   accrued if the fines cron job is running.

    **Important**

    If you are doing hourly loans then you should have this set to 'Do'.

`CumulativeRestrictionPeriods <#CumulativeRestrictionPeriods>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't cumulate

Asks: \_\_\_ the restriction periods.

Values:

-  Don't cumulate

-  Cumulate

`UpdateNotForLoanStatusOnCheckin <#UpdateNotForLoanStatusOnCheckin>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: This is a list of value pairs. When an item is checked in, if the
not for loan value on the left matches the items not for loan value it
will be updated to the right-hand value. E.g. '-1: 0' will cause an item
that was set to 'Ordered' to now be available for loan. Each pair of
values should be on a separate line.

`Checkout Policy <#circcheckoutpolicy>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AgeRestrictionMarker <#AgeRestrictionMarker>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Restrict patrons with the following target audience values from
checking out inappropriate materials: \_\_\_

Description:

-  This preference defines certain keywords that will trigger Koha to
   restrict checkout based on age. These restrictions can be overridden
   by the `AgeRestrictionOverride <#AgeRestrictionOverride>`__
   preference. Enter in this field a series of keywords separated by bar
   (\|) with no spaces. For example PG\|R\|E\|EC\|Age\| will look for PG
   followed by an age number, R folllowed by an age number, Age followed
   by an age number, and so on. These values can appear in any MARC
   field, but Library of Congress recommends the 521$a (Target Audience
   Note). Whatever field you decide to use you must map the word
   agerestriction in the biblioitems table to that field in the `Koha to
   MARC Mapping <#kohamarcmapping>`__. When cataloging you can enter
   values like PG 13 or E 10 in the 521$a and Koha will then notify
   circulation librarians that the material may not be recommended for
   the patron based on their age.

       **Important**

       You must map the word agerestriction in the biblioitems table to
       the MARC field where this information will appear via the `Koha
       to MARC Mapping <#kohamarcmapping>`__ administration area.

`AgeRestrictionOverride <#AgeRestrictionOverride>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ staff to check out an item with age restriction.

Values:

-  Allow

   Allow age restriction override
   |image25|

-  Don't allow

   Don't allow age restriction override
   |image26|

Description:

-  When the `AgeRestrictionMarker <#AgeRestrictionMarker>`__ preference
   is set, Koha will try to warn circulation librarians before checking
   out an item that might have an age restriction listed in the MARC
   record. This preference asks if you would like the staff to be able
   to still check out these items to patrons under the age limit.

`AllFinesNeedOverride <#AllFinesNeedOverride>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Require

Asks: \_\_\_ staff to manually override all fines, even fines less than
`noissuescharge <#noissuescharge>`__.

Values:

-  Don't require

-  Require

Description:

-  This preference let's you decide if you want to always be warned that
   the patron has fines when checking out. If you have it set to
   'Require' then no matter how much money the patron owes a message
   will pop up warning you that the patron owes money.

`AllowFineOverride <#AllowFineOverride>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ staff to manually override and check out items to patrons
who have more than `noissuescharge <#noissuescharge>`__ in fines.

Values:

-  Allow

-  Don't allow

Description:

-  This preference lets you decide if you staff can check out to patrons
   who owe more money than you usually let them carry on their account.
   If set to 'Allow' staff will be warned that the patrons owes money,
   but it won't stop the staff from checking out to the patron.

`AllowItemsOnHoldCheckout <#AllowItemsOnHoldCheckout>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ checkouts of items reserved to someone else. If allowed do
not generate RESERVE\_WAITING and RESERVED warning. This allows self
checkouts for those items.

Values:

-  Allow

-  Don't allow

    **Important**

    This system preference relates only to SIP based self checkout, not
    Koha's web based self checkout.

Description:

-  When this preference is set to 'Allow' patrons will be able to use
   your external self check machine to check out a book to themselves
   even if it's on hold for someone else. If you would like Koha to
   prevent people from checking out books that are on hold for someone
   else set this preference to "Don't allow."
   
`AllowItemsOnHoldCheckoutSCO <#AllowItemsOnHoldCheckoutSCO>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ checkouts of items reserved to someone else in the SCO module.
If allowed do not generate RESERVE_WAITING and RESERVED warning. This
allows self checkouts for those items.

Values:

-  Allow

-  Don't allow

    **Important**
    
    This system preference relates only to Koha's web based self checkout.

Description:

-  When this preference is set to 'Allow' patrons will be able to use
   Koha's web based self checkout to check out a book to themselves
   even if it's on hold for someone else. If you would like Koha to
   prevent people from checking out books that are on hold for someone
   else set this preference to "Don't allow".

`AllowMultipleIssuesOnABiblio <#AllowMultipleIssuesOnABiblio>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to check out multiple items from the same record.

Values:

-  Allow

-  Don't allow

Description:

-  If this preference is set to 'Allow' then patrons will be able to
   check out multiple copies of the same title at the same time. If it's
   set to "Don't allow" then patrons will only be allowed to check out
   one item attached to a record at a time. Regardless of the option
   chosen in this preference records with subscriptions attached will
   allow multiple check outs.

       **Important**

       This will only effect records without a subscription attached.

`AllowNotForLoanOverride <#AllowNotForLoanOverride>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to override and check out items that are marked as
not for loan.

Values:

-  Allow

-  Don't allow

Description:

-  This parameter is a binary setting which controls the ability of
   staff (patrons will always be prevented from checking these items
   out) to check out items that are marked as "not for loan". Setting it
   to "Allow" would allow such items to be checked out, setting it to
   "Don't allow" would prevent this. This setting determines whether
   items meant to stay in the library, such as reference materials, and
   other library resources can be checked out by patrons.

`AllowRenewalLimitOverride <#AllowRenewalLimitOverride>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to manually override the renewal limit and renew a
checkout when it would go over the renewal limit.

Values:

-  Allow

-  Don't allow

Description:

-  This preference is a binary setting which controls the ability of
   staff to override the limits placed on the number of times an item
   can be renewed. Setting it to "Allow" would allow such limits to be
   overridden, setting it to "Don't allow" would prevent this. This is a
   preference in which if it is set to "allow" it would allow the
   library staff to use their judgment for overriding the renew limit
   for special cases, setting it to "Don't allow" prevents an
   opportunity for abuse by the library staff.

`AllowReturnToBranch <#AllowReturnToBranch>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: to any library

Asks: Allow materials to be returned to \_\_\_

Values:

-  either the library the item is from or the library it was checked out
   from.

-  only the library the item is from.

-  only the library the item was checked out from.

-  to any library.

Description:

-  This preference lets the library system decide how they will accept
   returns. Some systems allow for items to be returned to any library
   in the system (the default value of this preference) others want to
   limit item returns to only specific branches. This preference will
   allow you to limit item returns (checkins) to the branch(es) set in
   the value.

`AllowTooManyOverride <#AllowTooManyOverride>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to override and check out items when the patron has
reached the maximum number of allowed checkouts.

Values:

-  Allow

   Allow too many checkouts override
   |image27|

-  Don't allow

   Don't allow too many checkouts override
   |image28|

Description:

-  If this preference is set to "Allow" then staff all will be presented
   with an option to checkout more items to a patron than are normally
   allowed in the `Circulation and Fine Rules <#circfinerules>`__. If
   this preference is set to "Don't allow" then no staff member will be
   able to check out more than the circulation limit.

`AutomaticItemReturn <#AutomaticItemReturn>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Do

Asks: \_\_\_ automatically transfer items to their home branch when they
are returned.

Values:

-  Do

-  Don't

Description:

-  This preference is a binary setting which determines whether an item
   is returned to its home branch automatically or not. If set to
   "Don't", the staff member checking an item in at a location other
   than the item's home branch will be asked whether the item will
   remain at the non-home branch (in which case the new location will be
   marked as a holding location) or returned. Setting it to "Do" will
   ensure that items checked in at a branch other than their home branch
   will be sent to that home branch.

`AutoRemoveOverduesRestrictions <#AutoRemoveOverduesRestrictions>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Do not

Asks: \_\_\_ allow OVERDUES restrictions triggered by sent notices to be
cleared automatically when all overdue items are returned by a patron.

Values:

-  Do

-  Do not

Description:

-  Using the `Overdue Notice/Status Triggers <#noticetriggers>`__ you
   can restrict patrons after they receive an overdue notice. This
   preference lets you define whether Koha will automatically remove
   that restriction once the overdue items in question are returned or
   not.

`CircControl <#CircControl>`__
''''''''''''''''''''''''''''''

Default: the library the item is from

Asks: Use the checkout and fines rules of \_\_\_

Values:

-  the library the item is from

   -  The `circulation and fines policies <#circfinerules>`__ will be
      determined by the item's library where
      `HomeOrHoldingBranch <#HomeOrHoldingBranch>`__ chooses if item's
      home library is used or holding library is used.

-  the library the patron is from

   -  The `circulation and fines policies <#circfinerules>`__ will be
      determined the patron's home library

-  the library you are logged in at

   -  The `circulation and fines policies <#circfinerules>`__ will be
      determined by the library that checked the item out to the patron

`ConsiderOnSiteCheckoutsAsNormalCheckouts <#ConsiderOnSiteCheckoutsAsNormalCheckouts>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Consider

Asks: \_\_\_ on-site checkouts as normal checkouts. If enabled, the
number of checkouts allowed will be normal checkouts + on-site
checkouts. If disabled, both values will be checked separately.

Values:

-  Consider

-  Don't consider

Description:

-  This preference allows you to decide if checkouts that are
   `OnSiteCheckouts <#OnSiteCheckouts>`__ are counted toward the total
   checkouts a patron can have. You can also set your `circulation and
   fine rules <#circfinerules>`__ to allow only a certain number of
   normal and OnSite checkouts.

`DefaultLongOverdueChargeValue <#DefaultLongOverdueChargeValue>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Charge a lost item to the borrower's account when the LOST value
of the item changes to \_\_\_

Description:

-  Leave this field empty if you don't want to charge the user for lost
   items. If you want the user to be charged enter the `LOST authorized
   value <#lost>`__ you are using in the
   `DefaultLongOverdueLostValue <#DefaultLongOverdueLostValue>`__
   preference. This preference is used when the `longoverdue cron
   job <#longoverduecron>`__ is called without the --charge parameter.

`DefaultLongOverdueLostValue & DefaultLongOverdueDays <#DefaultLongOverdueLostValue>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: By default, set the LOST value of an item to \_\_\_ when the item
has been overdue for more than \_\_\_ days.

Description:

-  These preferences are used when the `longoverdue cron
   job <#longoverduecron>`__ is called without the --lost parameter. It
   allows users to set the values of the `longoverdue
   cron <#longoverduecron>`__ without having to edit the crontab.
   Setting the values to 1 and 30 for example will mark the item with
   the `LOST authorized value <#lost>`__ of 1 after the item is 30 days
   overdue.

`HoldsInNoissuesCharge <#HoldsInNoissuesCharge>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't include

Asks: \_\_\_ hold charges when summing up charges for noissuescharge.

Values:

-  Don't include

-  Include

`HomeOrHoldingBranch <#HomeOrHoldingBranch>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: the library the item was checked out from

Asks: Use the checkout and fines rules of \_\_\_

Values:

-  the library the item is from

   -  This is equivalent to 'home library'

-  the library the item was checked out from

   -  This is equivalent to 'holding library'

Description:

-  This preference does several things.

   -  If `CircControl <#CircControl>`__ is set to 'the library the item
      is from' then the `circulation and fines
      policies <#circfinerules>`__ will be determined by the item's
      library where HomeOrHoldingBranch chooses if item's home library
      is used or holding library is used.

   -  If `IndependentBranches <#IndependentBranches>`__ is set to
      'Prevent' then the value of this preference is used in figuring
      out if the item can be checked out. If the item's home library
      does not match the logged in library, the item cannot be checked
      out unless you are a `superlibrarian <#patronpermsdefined>`__.

    **Important**

    It is not recommend that this setting be changed after initial setup
    of Koha because it will change the behavior of items already checked
    out.

`InProcessingToShelvingCart <#InProcessingToShelvingCart>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't move

Asks: \_\_\_ items that have the location PROC to the location CART when
they are checked in.

Values:

-  Don't move

-  Move

Description:

-  This preference is used to manage automatically changing item
   locations from processing (PROC) to the book cart (CART). A `cron
   job <#proccartcron>`__ needs to be set to run at specified intervals
   to age items from CART to the permanent shelving location. (For
   example, an hourly cron entry of cart\_to\_shelf.pl --hours 3 where
   --hours is the amount of time an item should spend on the cart before
   aging to its permanent location.) More information can be found in
   the `related chapter <#processinglocations>`__ in this manual.

   -  **Note**

          If the `ReturnToShelvingCart <#ReturnToShelvingCart>`__ system
          preference is turned on, any newly checked-in item is also
          automatically put into the shelving cart, to be covered by the
          same script run.

   -  **Important**

          Checkins with confirmed holds will not go into the shelving
          cart. If items on the shelving cart are checked out, the cart
          location will be cleared.

`IssueLostItem <#IssueLostItem>`__
''''''''''''''''''''''''''''''''''

Default: display a message

Asks: When issuing an item that has been marked as lost, \_\_\_.

Values:

-  display a message

   Lost message when checking out
   |image29|

-  do nothing

   -  This option will just check the item out without notifying you
      that the item was marked lost.

-  require confirmation

   Confirm checkout of lost item
   |image30|

Description:

-  This preference lets you define how library staff are notified that
   an item with a lost status is being checked out. This will help staff
   mark items as 'available' if you choose to 'display a message' or
   'require confirmation.' If you choose to 'do nothing,' there will be
   no notification that the item being checked out is marked as 'lost.'

`IssuingInProcess <#IssuingInProcess>`__
''''''''''''''''''''''''''''''''''''''''

Default: Don't prevent

Asks: \_\_\_ patrons from checking out an item whose rental charge would
take them over the limit.

Values:

-  Don't prevent

-  Prevent

Description:

-  This preference determines if a patron can check items out if there
   is an overdue fine on the account and any of the materials the patron
   wishes to check out will potentially tip the account balance over the
   maximum fines policy the library has in place.

Example: Your library has a $5 limit set for 'fines' (ie, after
incurring $5 in fines, a patron can no longer check out items). A patron
comes to the desk with 5 items to check out (4 books and a video) The
patron has $4 in charges already on their account. One of the videos has
a rental charge of $1, therefore making the total fines on the patron's
account suddenly $5 (the limit).

`ManInvInNoissuesCharge <#ManInvInNoissuesCharge>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Include

Asks: \_\_\_ MANUAL\_INV charges when summing up charges for
noissuescharge.

Values:

-  Don't include

-  Include

Description:

-  This preference lets you decide if charges entered as manual invoices
   are included when calculating the
   `noissuescharge <#noissuescharge>`__. If this is set to include then
   Koha will include all manual invoices when deciding if the patron
   owes too much money to check anything else out of the library. If
   it's set to Don't include then Koha will ignore all manual invoice
   charges when figuring out if the patron owes too much money to
   checkout additional materials.

`maxoutstanding <#maxoutstanding>`__
''''''''''''''''''''''''''''''''''''

Default: 5

Asks: Prevent patrons from making holds on the OPAC if they owe more
than \_\_\_ USD in fines.

`noissuescharge <#noissuescharge>`__
''''''''''''''''''''''''''''''''''''

Default: 5

Asks: Prevent patrons from checking out books if they have more than
\_\_\_ USD in fines.

Description:

-  This preference is the maximum amount of money owed to the library
   before the user is banned from borrowing more items. Using the
   `ManInvInNoissuesCharge <#ManInvInNoissuesCharge>`__ and
   `RentalsInNoissuesCharge <#RentalsInNoissuesCharge>`__ preferences
   you can control which types of charges are considered in this total.
   This also coincides with `maxoutstanding <#maxoutstanding>`__ that
   limits patrons from placing holds when the maximum amount is owed to
   the library.

`NoIssuesChargeGuarantees <#NoIssuesChargeGuarantees>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Prevent a patron from checking out if the patron has guarantees
owing in total more than \_\_\_ USD in fines.

Description:

-  Allows a library to prevent patrons from checking out items if his or
   her guarantees owe too much in fines.

`NoRenewalBeforePrecision <#NoRenewalBeforePrecision>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: date

Asks: Calculate "No renewal before" based on \_\_\_.

Values:

-  date

-  exact time

    **Note**

    Only relevant for loans calculated in days, hourly loans are not
    affected.

Description:

-  This preference allows you to control how the 'No renewal before"
   option in the `Circulation and fine rules <#circfinerules>`__
   administration area.

`NoticeBcc <#NoticeBcc>`__
''''''''''''''''''''''''''''''''''''''''

Asks: Send all notices as a BCC to this email address \_\_\_

This preference makes it so that a librarian can get a copy of every
notice sent out to patrons.

    **Note**

    If you'd like more than one person to receive the blind copy you can
    simply enter in multiple email addresses separated by commas.

`OnSiteCheckouts <#OnSiteCheckouts>`__
''''''''''''''''''''''''''''''''''''''

Default: Disable

Asks: \_\_\_ the on-site checkouts feature.

Values:

-  Disable

-  EnableOnSiteCheckouts

Description:

-  This preference lets you check out items that are 'not for loan' to
   patrons. A checkbox is added to the checkout screen when this
   preference is set to 'Enable' labeled 'On-site checkout'. This allows
   you to track who's using items that are normally not for loan or are
   in a closed stack setting.

`OnSiteCheckoutsForce <#OnSiteCheckoutsForce>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Disable

Asks: \_\_\_ the on-site for all cases (Even if a user is debarred,
etc.).

Values:

-  Disable

-  Enable

   Force checkouts on restricted patrons
   |image31|

Description:

-  This preference lets the staff override any restrictions a patron
   might have and check out items for use within the library. The
   `OnSiteCheckouts <#OnSiteCheckouts>`__ preference must first be set
   to 'Enable' for this preference to be considered.

`OPACFineNoRenewalsBlockAutoRenew <#OPACFineNoRenewalsBlockAutoRenew>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: If a patron owes more than the value of `OPACFineNoRenewals <#OPACFineNoRenewals>`__,
\_\_\_ his/her auto renewals.

Values:

-  Allow

-  Block

`OverdueNoticeCalendar <#OverdueNoticeCalendar>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Ignore calendar

Asks: \_\_\_ when working out the period for overdue notices

Values:

-  Ignore calendar

   -  Notices do not take holidays into account, so they will be sent
      even if holidays have meant the item is not actually overdue yet

-  Use calendar

   -  Notices take holidays into account, so they will not be sent if
      holidays mean the item is not actually overdue yet

`OverduesBlockCirc <#OverduesBlockCirc>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Ask for confirmation

Asks: \_\_\_ when checking out to a borrower that has overdues
outstanding

Values:

-  Ask for confirmation

   -  Will not let you check an item out to patrons with overdues until
      a librarian confirms that it is okay

-  Block

   -  Block all patrons with overdue items from being able to check out

-  Don't block

   -  Allow all patrons with overdue items to continue to check out

`OverduesBlockRenewing <#OverduesBlockRenewing>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: allow renewing

Asks: When a patron's checked out item is overdue, \_\_\_

Values:

-  allow renewing

-  block renewing for all the patron's items

-  block renewing for only this item

`PrintNoticesMaxLines <#PrintNoticesMaxLines>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Include up to \_\_\_ item lines in a printed overdue notice.

    **Note**

    If the number of items is greater than this number, the notice will
    end with a warning asking the borrower to check their online account
    for a full list of overdue items.

    **Note**

    Set to 0 to include all overdue items in the notice, no matter how
    many there are.

    **Important**

    This preference only refers to the print notices, not those sent via
    email.

`RenewalPeriodBase <#RenewalPeriodBase>`__
''''''''''''''''''''''''''''''''''''''''''

Default: the old due date of the checkout

Asks: When renewing checkouts, base the new due date on \_\_\_

Values:

-  the old due date of the checkout

-  the current date

`RenewalSendNotice <#RenewalSendNotice>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't send

Asks: \_\_\_\_ a renewal notice according to patron checkout alert
preferences.

Values:

-  Don't send

-  Send

Description:

-  If a patron has chosen to receive a check out notice in their
   messaging preferences and this preference is set to 'Send' then those
   patrons will also receive a notice when they renew materials. You
   will want to set up a `new notice <#addnotices>`__ with the code of
   RENEWAL (if you don't already have it) with custom text for renewing
   items.

       **Important**

       This preference requires that you have
       `EnhancedMessagingPreferences <#EnhancedMessagingPreferences>`__
       set to 'Allow'

`RentalFeesCheckoutConfirmation <#RentalFeesCheckoutConfirmation>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: do not ask

Asks: When checking out an item with rental fees, \_\_\_ for
confirmation.

Values:

-  askRentalFeesCheckoutConfirmation

-  do not ask

Description:

-  If you are charging rental fees for items this preference will make
   it so that you can show (or not show) a confirmation before checking
   out an item that will incur a rental charge.

`RentalsInNoissuesCharge <#RentalsInNoissuesCharge>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Include

Asks: \_\_\_ rental charges when summing up charges for noissuescharge.

Values:

-  Don't include

-  Include

Description:

-  This preference lets you decide if rental charges are included when
   calculating the `noissuescharge <#noissuescharge>`__. If this is set
   to include then Koha will include all rental charges when deciding if
   the patron owes too much money to check anything else out of the
   library. If it's set to Don't include then Koha will ignore all
   rental charges when figuring out if the patron owes too much money to
   checkout additional materials.

`RestrictionBlockRenewing <#RestrictionBlockRenewing>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: If patron is restricted, \_\_\_ renewing of items.

Values:

-  Allow

-  Block

`ReturnBeforeExpiry <#ReturnBeforeExpiry>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Don't require

Asks: \_\_\_ patrons to return books before their accounts expire (by
restricting due dates to before the patron's expiration date).

Values:

-  Don't require

-  Require

Description:

-  This is preference may prevent a patron from having items checked out
   after their library card has expired. If this is set to "Require",
   then a due date of any checked out item can not be set for a date
   which falls after the patron's card expiration. If the setting is
   left "Don't require" then item check out dates may exceed the
   expiration date for the patron's library card.

`ReturnToShelvingCart <#ReturnToShelvingCart>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't move

Asks: \_\_\_ all items to the location CART when they are checked in.

Values:

-  Don't move

-  Move

Description:

-  More information can be found in the `related
   chapter <#processinglocations>`__ in this manual.

`StaffSearchResultsDisplayBranch <#StaffSearchResultsDisplayBranch>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: the library the item is held by

Asks: For search results in the staff client, display the branch of
\_\_\_

Values:

-  the library the item is from

-  the library the items is held by

`SwitchOnSiteCheckouts <#SwitchOnSiteCheckouts>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't switch

Asks: \_\_\_ on-site checkouts to normal checkouts when checked out.

Values:

-  Don't switch

-  Switch

`TransfersMaxDaysWarning <#TransfersMaxDaysWarning>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 3

Asks: Show a warning on the "Transfers to Receive" screen if the
transfer has not been received \_\_\_ days after it is sent.

Description:

-  The TransferMaxDaysWarning preference is set at a default number of
   days. This preference allows for a warning to appear after a set
   amount of time if an item being transferred between library branches
   has not been received. The warning will appear in the `Transfers to
   Receive <#transferstoreceive>`__ report.

`UseBranchTransferLimits & BranchTransferLimitsType <#UseBranchTransferLimits>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Defaults: Don't enforce & collection code

Asks: \_\_\_ branch transfer limits based on \_\_\_

UseBranchTransferLimits Values:

-  Don't enforce

-  Enforce

BranchTransferLimitsType Values:

-  collection code

-  item type

BranchTransferLimitsType Description:

-  This parameter is a binary setting which determines whether items are
   transferred according to item type or collection code. This value
   determines how the library manager is able to restrict what items can
   be transferred between the branches.

`useDaysMode <#useDaysMode>`__
''''''''''''''''''''''''''''''

Default: Don't include

Asks: Calculate the due date using \_\_\_.

Values:

-  circulation rules only.

-  the calendar to push the due date to the next open day.

-  the calendar to skip all days the library is closed.

Description:

-  This preference controls how scheduled library closures affect the
   due date of a material. The 'the calendar to skip all days the
   library is closed' setting allows for a scheduled closure not to
   count as a day in the loan period, the 'circulation rules only'
   setting would not consider the scheduled closure at all, and 'the
   calendar to push the due date to the next open day' would only effect
   the due date if the day the item is due would fall specifically on
   the day of closure.

Example:

-  The library has put December 24th and 25th in as closures on the
   calendar. A book checked out by a patron has a due date of December
   25th according to the circulation and fine rules. If this preference
   is set to 'circulation rules only' then the item will remain due on
   the 25th. If the preference is set to 'the calendar to push the due
   date to the next open day' then the due date will be December 26th.
   If the preference is set to 'the calendar to skip all days the
   library is closed' then the due date will be pushed to the 27th of
   December to accommodate for the two closed days.

The calendar is defined on a branch by branch basis. To learn more about
the calendar, check out the '`Calendar & Holidays <#calholidays>`__'
section of this manual.

`UseTransportCostMatrix <#UseTransportCostMatrix>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't use

Asks: \_\_\_ Transport Cost Matrix for calculating optimal holds filling
between branches.

Values:

-  Don't use

-  Use

Description:

-  If the system is configured to use the `Transport cost
   matrix <#transportcostmatrix>`__ for filling holds, then when
   attempting to fill a hold, the system will search for the lowest cost
   branch, and attempt to fill the hold with an item from that branch
   first. Branches of equal cost will be selected from randomly. The
   branch or branches of the next highest cost shall be selected from
   only if all the branches in the previous group are unable to fill the
   hold.

   The system will use the item's current holding branch when
   determining whether the item can fulfill a hold using the Transport
   Cost Matrix.

`Course Reserves <#coursereserveprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`UseCourseReserves <#UseCourseReserves>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't use

Asks: \_\_\_ course reserves

Values:

-  Don't use

-  Use

Description:

-  The `Course Reserves <#coursereserves>`__ module in Koha allows you
   to temporarily move items to 'reserve' and assign different
   circulation rules to these items while they are being used for a
   specific course.

`Fines Policy <#circfinespolicy>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`finesCalendar <#finesCalendar>`__
''''''''''''''''''''''''''''''''''

Default: not including the days the library is closed

Asks: Calculate fines based on days overdue \_\_\_

Values:

-  directly

-  not including the days the library is closed

Description:

-  This preference will determine whether or not fines will be accrued
   during instances when the library is closed. Examples include
   holidays, library in-service days, etc. Choosing "not including the
   days the library is closed" setting will enable Koha to access its
   `Calendar <#calholidays>`__ module and be considerate of dates when
   the library is closed. To make use of this setting the administrator
   must first access Koha's calendar and mark certain days as "holidays"
   ahead of time.

The calendar is defined on a branch by branch basis. To learn more about
the calendar, check out the '`Calendar & Holidays <#calholidays>`__'
section of this manual.

`FinesIncludeGracePeriod <#FinesIncludeGracePeriod>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Include

Asks: \_\_\_ the grace period when calculating the fine for an overdue
item.

Values:

-  Don't include

-  Include

Description:

-  This preference lets you control how Koha calculates fines when there
   is a grace period. If you choose to include the grace period when
   calculating fines then Koha will charge for the days in the grace
   period should the item be overdue more than those days. If you choose
   not to include the grace period then Koha will only charge for the
   days overdue after the grace period.

`finesMode <#finesMode>`__
''''''''''''''''''''''''''

Default: Calculate (but only for mailing to the admin)

Asks: \_\_\_ fines

Values:

-  Calculate (but only for mailing to the admin)

-  Calculate and charge

-  Don't calculate

    **Important**

    Requires that you have the fines cron job running
    (misc/cronjobs/fines.pl)

`HoldFeeMode <#HoldFeeMode>`__
''''''''''''''''''''''''''''''

Default: only if all items are checked out and the record has at least one hold already.

Asks: Charge a hold fee \_\_\_

Values:

-  any time a hold is collected.

-  any time a hold is placed.

-  only if all items are checked out and the record has at least one hold already.

`RefundLostOnReturnControl <#RefundLostOnReturnControl>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: check-in library.

Asks: If a lost item is returned, apply the refunding rules defined
in the \_\_\_

Values:

-  check-in library.

-  item holding branch.

-  item home branch.

`WhenLostChargeReplacementFee <#WhenLostChargeReplacementFee>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Charge

Asks: \_\_\_ the replacement price when a patron loses an item.

Values:

-  Charge

-  Don't charge

Description:

-  This preference lets you tell Koha what to do with an item is marked
   lost. If you want Koha can 'Charge' the patron the replacement fee
   listed on the item they lost or it can do nothing in reference to the
   patron and just mark the item lost in the catalog.

`WhenLostForgiveFine <#WhenLostForgiveFine>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't forgive

Asks: \_\_\_ the fines on an item when it is lost.

Values:

-  Don't forgive

-  Forgive

Description:

-  This preference allows the library to decide if fines are charged in
   addition to the replacement fee when an item is marked as lost. If
   this preference is set to 'Forgive' then the patron won't be charged
   fines in addition to the replacement fee.

`Holds Policy <#circholdspolicy>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AllowHoldDateInFuture <#AllowHoldDateInFuture>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ hold requests to be placed that do not enter the waiting
list until a certain future date.

Values:

-  Allow

-  Don't allow

`AllowHoldItemTypeSelection <#AllowHoldItemTypeSelection>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ hold fulfillment to be limited by itemtype.

Values:

-  Allow

-  Don't allow

`AllowHoldPolicyOverride <#AllowHoldPolicyOverride>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to override hold policies when placing holds.

Values:

-  Allow

-  Don't allow

Description:

-  This preference is a binary setting which controls whether or not the
   library staff can override the circulation and fines rules as they
   pertain to the placement of holds. Setting this value to "Don't
   allow" will prevent anyone from overriding, setting it to "Allow"
   will allow it. This setting is important because it determines how
   strict the libraries rules for placing holds are. If this is set to
   "Allow", exceptions can be made for patrons who are otherwise
   normally in good standing with the library, but there is opportunity
   for the staff to abuse this function. If it is set to "Don't allow",
   no abuse of the system is possible, but it makes the system entirely
   inflexible in respect to holds.

`AllowHoldsOnDamagedItems <#AllowHoldsOnDamagedItems>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ hold requests to be placed on damaged items.

Values:

-  Allow

-  Don't allow

Description:

-  This parameter is a binary setting which controls whether or not hold
   requests can be placed on items that are marked as "damaged" (items
   are marked as damaged by editing subfield 4 on the item record).
   Setting this value to "Don't allow" will prevent anyone from placing
   a hold on such items, setting it to "Allow" will allow it. This
   preference is important because it determines whether or not a patron
   can place a request for an item that might be in the process of being
   repaired or not in good condition. The library may wish to set this
   to "Don't allow" if they were concerned about their patrons not
   receiving the item in a timely manner or at all (if it is determined
   that the item is beyond repair). Setting it to "Allow" would allow a
   patron to place a hold on an item and therefore receive it as soon as
   it becomes available.

`AllowHoldsOnPatronsPossessions <#AllowHoldsOnPatronsPossessions>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_\_ a patron to place a hold on a record where the patron
already has one or more items attached to that record checked out.

Values:

-  Allow

-  Don't allow

Description:

-  By setting to "Don't allow," you can prevent patrons from placing
   holds on items they already have out, thus preventing them from
   blocking anyone else from getting an item.

`AllowRenewalIfOtherItemsAvailable <#AllowRenewalIfOtherItemsAvailable>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ a patron to renew an item with unfilled holds if other
available items can fill that hold.

Values:

-  Allow

-  Don't allow

`AutoResumeSuspendedHolds <#AutoResumeSuspendedHolds>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ suspended holds to be automatically resumed by a set date.

Values:

-  Allow

-  Don't allow

Description:

-  If this preference is set to 'Allow' then all suspended holds will be
   able to have a date at after which they automatically become
   unsuspended. If you have this preference set to 'Allow' you will also
   need the `Unsuspend Holds <#unsuspendholdcron>`__ cron job running.

    **Important**

    The holds will become unsuspended the date after that entered by the
    patron.

`canreservefromotherbranches <#canreservefromotherbranches>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ a user from one library to place a hold on an item from
another library

Description:

-  This preference is a binary setting which determines whether patrons
   can place holds on items from other branches. If the preference is
   set to "Allow" patrons can place such holds, if it is set to "Don't
   allow" they cannot. This is an important setting because it
   determines if users can use Koha to request items from another
   branch. If the library is sharing an installation of Koha with other
   independent libraries which do not wish to allow interlibrary
   borrowing it is recommended that this parameter be set to "Don't
   allow".

Values:

-  Allow

-  Don't allow (with `independent branches <#IndependentBranches>`__)

`ConfirmFutureHolds <#ConfirmFutureHolds>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: 0

Asks: Confirm future hold requests (starting no later than \_\_\_ days
from now) at checkin time.

Description:

-  When confirming a hold at checkin time, the number of days in this
   preference is taken into account when deciding which holds to show
   alerts for. This preference does not interfere with renewing,
   checking out or transferring a book.

    **Note**

    This number of days will be used too in calculating the default end
    date for the Holds to pull-report. But it does not interfere with
    issuing, renewing or transferring books.

    **Important**

    This preference is only looked at if you're allowing hold dates in
    the future with `AllowHoldDateInFuture <#AllowHoldDateInFuture>`__
    or `OPACAllowHoldDateInFuture <#OPACAllowHoldDateInFuture>`__

`decreaseLoanHighHolds, decreaseLoanHighHoldsDuration, decreaseLoanHighHoldsValue, decreaseLoanHighHoldsControl, and decreaseLoanHighHoldsIgnoreStatuses <#decreaseLoanHighHolds>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: \_\_\_ the reduction of loan period \_\_\_ to days for items with
more than \_\_\_ holds \_\_\_ . Ignore items with the following statuses
when counting items \_\_\_

decreaseLoanHighHolds default: Don't enable

decreaseLoanHighHoldsControl default: on the record

decreaseLoanHighHolds values:

-  Enable

decreaseLoanHighHoldsControl values:

-  over the number of holdable items on the records

-  on the record

decreaseLoanHighHoldsIgnoreStatuses values:

-  [Select All]

-  Damages

-  Lost

-  Not for loan

-  Withdrawn

Description:

-  These preferences let you change the loan length for items that have
   many holds on them. This will not effect items that are already
   checked out, but items that are checked out after the
   decreaseLoanHighHoldsValue is met will only be checked out for the
   number of days entered in the decreaseLoanHighHoldsDuration
   preference.

   Warning on checkout
   |image32|

`DisplayMultiPlaceHold <#DisplayMultiPlaceHold>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't enable

Asks: \_\_\_ the ability to place holds on multiple biblio from the
search results

Values:

-  Don't enable

-  Enable

`emailLibrarianWhenHoldIsPlaced <#emailLibrarianWhenHoldIsPlaced>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't enable

Asks: \_\_\_ sending an email to the Koha administrator email address
whenever a hold request is placed.

Values:

-  Don't enable

-  Enable

Description:

-  This preference enables Koha to email the library staff whenever a
   patron requests an item to be held. While this function will
   immediately alert the librarian to the patron's need, it is extremely
   impractical in most library settings. In most libraries the hold
   lists are monitored and maintained from a separate interface. That
   said, many libraries that allow on shelf holds prefer to have this
   preference turned on so that they are alerted to pull an item from
   the shelf.

    **Important**

    In order for this email to send you must have a
    `notice <#notices>`__ template with the code of HOLDPLACED

    **Important**

    This notice will only be sent if the `process\_message\_queue.pl
    cronjob <#msgqueuecron>`__ being run periodically to send the
    messages.
    
`ExcludeHolidaysFromMaxPickUpDelay <#ExcludeHolidaysFromMaxPickUpDelay>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ Closed days to be taken into account in reserves max pickup delay.

Values:

-  Don't allow

-  Allow

`ExpireReservesMaxPickUpDelay <#ExpireReservesMaxPickUpDelay>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ holds to expire automatically if they have not been picked
by within the time period specified in
`ReservesMaxPickUpDelay <#ReservesMaxPickUpDelay>`__

Values:

-  Allow

-  Don't allow

Description:

-  If set to 'allow' this will cancel holds that have been waiting for
   longer than the number of days specified in the
   `ReservesMaxPickUpDelay <#ReservesMaxPickUpDelay>`__ system
   preference. Holds will only be cancelled if the `Expire Holds cron
   job <#expiredholdscron>`__ is runnning.

`ExpireReservesMaxPickUpDelayCharge <#ExpireReservesMaxPickUpDelayCharge>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 0

Asks: If using
`ExpireReservesMaxPickUpDelay <#ExpireReservesMaxPickUpDelay>`__, charge
a borrower who allows his or her waiting hold to expire a fee of \_\_\_
USD

Description:

-  If you are expiring holds that have been waiting too long you can use
   this preference to charge the patron for not picking up their hold.
   If you don't charge patrons for items that aren't picked up you can
   leave this set to the default which is 0. Holds will only be
   cancelled and charged if the `Expire Holds cron
   job <#expiredholdscron>`__ is running.

`ExpireReservesOnHolidays <#ExpireReservesOnHolidays>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ expired holds to be cancelled on days the library is
closed.

Values:

-  Allow

-  Don't allow

`LocalHoldsPriority, LocalHoldsPriorityPatronControl, LocalHoldsPriorityItemControl <#LocalHoldsPriority>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: \_\_\_ priority for filling holds to patrons whose \_\_\_ matches
the item's \_\_\_

LocalHoldsPriority Values:

-  Don't give

-  Give

LocalHoldsPriorityPatronControl Values:

-  home library

-  pickup library

LocalHoldsPriorityItemControl Values:

-  holding library

-  home library

Description:

-  This feature will allow libraries to specify that, when an item is
   returned, a local hold may be given priority for fulfillment even
   though it is of lower priority in the list of unfilled holds.

`maxreserves <#maxreserves>`__
''''''''''''''''''''''''''''''

Default: 50

Asks: Patrons can only have \_\_\_ holds at once.

`OPACAllowHoldDateInFuture <#OPACAllowHoldDateInFuture>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to place holds that don't enter the waiting list
until a certain future date.

Values:

-  Allow

   -  `AllowHoldDateInFuture <#AllowHoldDateInFuture>`__ must also be
      enabled for this to work

-  Don't allow

`OPACAllowUserToChooseBranch <#OPACAllowUserToChooseBranch>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ a user to choose the branch to pick up a hold from.

Values:

-  Allow

-  Don't allow

Description:

-  Changing this preference will not prevent staff from being able to
   transfer titles from one branch to another to fill a hold, it will
   only prevent patrons from saying they plan on picking a book up at a
   branch other than their home branch.

`OPACHoldsIfAvailableAtPickup <#OPACHoldsIfAvailableAtPickup>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ to pickup holds at libraries where the item is available.

Values:

-  Don't allow

-  Allow

`OPACHoldsIfAvailableAtPickupExceptions <#OPACHoldsIfAvailableAtPickupExceptions>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: blank

Asks: Patron categories not affected by `OPACHoldsIfAvailableAtPickup <#OPACHoldsIfAvailableAtPickup>`__
\_\_\_ (list of patron categories separated with a pipe '|')

`ReservesControlBranch <#ReservesControlBranch>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: item's home library

Asks: Check the \_\_\_ to see if the patron can place a hold on the
item.

Values:

-  item's home library.

-  patron's home library.

`ReservesMaxPickUpDelay <#ReservesMaxPickUpDelay>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 7

Asks: Mark a hold as problematic if it has been waiting for more than
\_\_\_ days.

Description:

-  This preference (based on calendar days, not the `Koha holiday
   calendar <#calholidays>`__) puts an expiration date on an item a
   patron has on hold. After this expiration date the staff will have
   the option to release the unclaimed hold which then may be returned
   to the library shelf or issued to the next patron on the item's hold
   list. Items that are 'expired' by this preference are moved to the
   'Holds Over' tab on the '`Holds Awaiting Pickup <#holdspickup>`__'
   report.

`ReservesNeedReturns <#ReservesNeedReturns>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't automatically

Asks: \_\_\_ mark holds as found and waiting when a hold is placed
specifically on them and they are already checked in.

Values:

-  Automatically

-  Don't automatically

Description:

-  This preference refers to 'item specific' holds where the item is
   currently on the library shelf. This preference allows a library to
   decide whether an 'item specific' hold is marked as "Waiting" at the
   time the hold is placed or if the item will be marked as "Waiting"
   after the item is checked in. This preference will tell the patron
   that their item is 'Waiting' for them at their library and ready for
   check out.

`StaticHoldsQueueWeight, HoldsQueueSkipClosed & RandomizeHoldsQueueWeight <#holdqueueweight>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

StaticHoldsQueueWeight Default: 0

HoldsQueueSkipClosed Default: open or closed

RandomizeHoldsQueueWeight Default: in that order

Asks: Satisfy holds using items from the libraries \_\_\_ (as
branchcodes, separated by commas; if empty, uses all libraries) when
they are \_\_\_ \_\_\_.

HoldsQueueSkipClosed Values:

-  open or closed

-  open

RandomizeHoldsQueueWeight Values:

-  in random order

   -  If StaticHoldsQueueWeight is left at the default Koha will
      randomize all libraries, otherwise it will randomize the libraries
      listed.

-  in that order

   -  If StaticHoldsQueueWeight is left at the default then this will
      use all of your branches in alphabetical order, otherwise it will
      use the branches in the order that you entered them in the
      StaticHoldsQueueWeight preference.

Descriptions:

-  These preferences control how the `Holds Queue
   report <#holdsqueue>`__ is generated using `a cron
   job <#buildholdscron>`__.

   If you do not want all of your libraries to participate in the
   on-shelf holds fulfillment process, you should list the the libraries
   that \*do\* participate in the process here by inputting all the
   participating library's branchcodes, separated by commas ( e.g.
   "MPL,CPL,SPL,BML" etc. ).

   By default, the holds queue will be generated such that the system
   will first attempt to hold fulfillment using items already at the
   pickup library if possible. If there are no items available at the
   pickup library to fill a hold, build\_holds\_queue.pl will then use
   the list of libraries defined in StaticHoldsQueueWeight. If
   RandomizeHoldsQueueWeight is disabled ( which it is by default ), the
   script will assign fulfillment requests in the order the branches are
   placed in the StaticHoldsQueueWeight system preference.

   For example, if your system has three libraries, of varying sizes (
   small, medium and large ) and you want the burden of holds
   fulfillment to be on larger libraries before smaller libraries, you
   would want StaticHoldsQueueWeight to look something like
   "LRG,MED,SML".

   If you want the burden of holds fulfillment to be spread out equally
   throughout your library system, simply enable
   RandomizeHoldsQueueWeight. When this system preference is enabled,
   the order in which libraries will be requested to fulfill an on-shelf
   hold will be randomized each time the list is regenerated.

   Leaving StaticHoldsQueueWeight empty is contraindicated at this time.
   Doing so will cause the build\_holds\_queue script to ignore
   RandomizeHoldsQueueWeight, causing the script to request hold
   fulfillment not randomly, but by alphabetical order.

    **Important**

    The `Transport Cost Matrix <#transportcostmatrix>`__ takes
    precedence in controlling where holds are filled from, if the matrix
    is not used then Koha checks the StaticHoldsQueueWeight. To use the
    Transport Cost Matrix simply set your
    `UseTransportCostMatrix <#UseTransportCostMatrix>`__ preference to
    'Use'

`SuspendHoldsIntranet <#SuspendHoldsIntranet>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ holds to be suspended from the intranet.

Values:

-  Allow

-  Don't allow

Description:

-  The holds suspension feature can be turned on and off in the staff
   client by altering this system preference. If this is set to 'allow'
   you will want to set the
   `AutoResumeSuspendedHolds <#AutoResumeSuspendedHolds>`__ system
   preference.

`SuspendHoldsOpac <#SuspendHoldsOpac>`__
''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ holds to be suspended from the OPAC.

Values:

-  Allow

-  Don't allow

Description:

-  The holds suspension feature can be turned on and off in the OPAC by
   altering this system preference. If this is set to 'allow' you will
   want to set the
   `AutoResumeSuspendedHolds <#AutoResumeSuspendedHolds>`__ system
   preference.

`TransferWhenCancelAllWaitingHolds <#TransferWhenCancelAllWaitingHolds>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't transfer

Asks: \_\_\_ items when cancelling all waiting holds.

Values:

-  Don't transfer

-  Transfer

Description:

-  When TransferWhenCancelAllWaitingHolds is set to "Don't transfer", no
   branch transfer records are created. Koha will not allow the holds to
   be transferred, because that would orphan the items at the library
   where the holds were awaiting pickup, without any further instruction
   to staff as to what items are at the library or where they need to
   go. When that system preference set to "Transfer", branch transfers
   are created, so the holds may be cancelled.

`Housebound module <#circhouseboundmoduleprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`HouseboundModule <#HouseboundModule>`__
''''''''''''''''''''''''''''''''''''''''

Default: Disable

Asks: \_\_\_ housebound module

Values:

-  Disable

-  Enable

Description:

-  This preference enables or disables the Housebound module which
   handles management of circulation to Housebound readers.

`Interface <#circinterfaceprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AllowAllMessageDeletion <#AllowAllMessageDeletion>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ staff to delete messages added from other libraries.

Values:

-  Allow

-  Don't allow

`AllowCheckoutNotes <#AllowCheckoutNotes>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ patrons to submit notes about checked out items.

Values:

-  Don't allow

-  Allow

`AllowOfflineCirculation <#AllowOfflineCirculation>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Do not enable

Asks: \_\_\_ offline circulation on regular circulation computers.

Values:

-  Do not enable

-  Enable

Description:

-  Setting this preference to 'Enable' allows you to use the Koha
   interface for `offline circulation <#offlinecirc>`__. This system
   preference does not affect the `Firefox
   plugin <#firefoxofflinecirc>`__ or the `desktop
   application <#windowsofflinecirc>`__, any of these three options can
   be used for offline circulation without effecting the other.

`CircAutocompl <#CircAutocompl>`__
''''''''''''''''''''''''''''''''''

Default: Try

Asks: \_\_\_ to automatically fill in the member when entering a patron
search on the circulation screen.

Description:

-  This preference is a binary setting which determines whether
   auto-completion of fields is enabled or disabled for the circulation
   input field. Setting it to "Try" would enable a staff member to begin
   typing a name or other value into the field and have a menu pop up
   with suggestions for completing it. Setting it to "Don't try" would
   disable this feature. This preference can make staff members' jobs
   easier or it could potentially slow down the page loading process.

Values:

-  Don't try

-  Try

   When CircAutocompl is turned on search results will appear below the
   search box
   |image33|

`CircAutoPrintQuickSlip <#CircAutoPrintQuickSlip>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: open a print quick slip window

Asks: When an empty barcode field is submitted in circulation \_\_\_

Values:

-  clear the screen

-  open a print quick slip window

-  open a print slip window

Description:

-  If this preference is set to open a quick slip
   (`ISSUEQSLIP <#existingnotices>`__) or open a slip
   (`ISSUESLIP <#existingnotices>`__) for printing it will eliminate the
   need for the librarian to click the print button to generate a
   checkout receipt for the patron they're checking out to. If the
   preference is set to clear the screen then "checking out" an empty
   barcode will clear the screen of the patron you were last working
   with.
   
`CircSidebar <#CircSidebar>`__
''''''''''''''''''''''''''''''

Default: Deactivate

Asks: \_\_\_ the navigation sidebar on all Circulation pages.

Values:

-  Deactivate

-  Activate

`DisplayClearScreenButton <#DisplayClearScreenButton>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ a button to clear the current patron from the screen on the
circulation screen.

Values:

-  Don't show

   No X in the top right
   |image36|

-  Show

   X in the top right will clear the screen
   |image37|

`ExportCircHistory <#ExportCircHistory>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ the export patron checkout history options.

Values:

-  Don't show

-  Show

`ExportRemoveFields <#ExportRemoveFields>`__
''''''''''''''''''''''''''''''''''''''''''''

Asks: The following fields should be excluded from the patron checkout
history CSV or iso2709 export \_\_\_

Description:

-  This space separated list of fields (e.g. 100a 245b) will
   automatically be excluded when exporting the patron's current
   checkout history.

   ExportRemoveFields
   |image38|

`FilterBeforeOverdueReport <#FilterBeforeOverdueReport>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't require

Asks: \_\_\_ staff to choose which checkouts to show before running the
overdues report.

Description:

-  Koha's overdue report shows you all of the overdue items in your
   library system. If you have a large library system you'll want to set
   this preference to 'Require' to force those running the report to
   first limit the data generated to a branch, date range, patron
   category or other such filter. Requiring that the report be filtered
   before it's run prevents your staff from running a system heavy
   report and slowing down other operations in the system.

   Overdue Report Filters
   |image34|

Values:

-  Don't require

-  Require

`FineNotifyAtCheckin <#FineNotifyAtCheckin>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't notify

Asks: \_\_\_ librarians of overdue fines on the items they are checking
in.

Values:

-  Don't notify

-  Notify

Description:

-  With this preference set to 'Notify' all books that have overdue
   fines owed on them will pop up a warning when checking them in. This
   warning will need to acknowledged before you can continue checking
   items in. With this preference set to 'Don't notify,' you will still
   see fines owed on the patron record, you just won't have an
   additional notification at check in.

   Fine notification at checkin
   |image35|

`HoldsToPullStartDate <#HoldsToPullStartDate>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: 2

Asks: Set the default start date for the Holds to pull list to \_\_\_
day(s) ago.

Description:

-  The `Holds to Pull <#holdspull>`__ report in circulation defaults to
   filtering holds placed 2 days ago. This preference allows you to set
   this default filter to any number of days.

`itemBarcodeFallbackSearch <#itemBarcodeFallbackSearch>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't enable

Asks: \_\_\_ the automatic use of a keyword catalog search if the phrase
entered as a barcode on the checkout page does not turn up any results
during an item barcode search.

Values:

-  Don't enable

-  Enable

   Checkout by keyword
   |image40|

Description:

-  Sometimes libraries want to checkout using something other than the
   barcode. Enabling this preference will do a keyword search of Koha to
   find the item you're trying to check out. You can use the call
   number, barcode, part of the title or anything you'd enter in the
   keyword search when this preference is enabled and Koha will ask you
   which item you're trying to check out.

    **Important**

    While you're not searching by barcode a barcode is required on every
    title you check out. Only titles with barcodes will appear in the
    search results.

`itemBarcodeInputFilter <#itemBarcodeInputFilter>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't filter

Asks: \_\_\_ scanned item barcodes.

Values:

-  Convert from CueCat format

-  Convert from Libsuite8 form

-  Don't filter

-  EAN-13 or zero-padded UPC-A from

-  Remove spaces from

-  Remove the first number from T-prefix style

   -  This format is common among those libraries migrating from Follett
      systems

`NoticeCSS <#NoticeCSS>`__
''''''''''''''''''''''''''

Asks: Include the stylesheet at \_\_\_ on Notices.

    **Important**

    This should be a complete URL, starting with http://

Description:

-  If you would like to style your notices with a consistent set of
   fonts and colors you can use this preference to point Koha to a
   stylesheet specifically for your notices.

`numReturnedItemsToShow <#numReturnedItemsToShow>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 20

Asks : Show the \_\_\_ last returned items on the checkin screen.

`previousIssuesDefaultSortOrder <#previousIssuesDefaultSortOrder>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: earliest to latest

Asks: Sort previous checkouts on the circulation page from \_\_\_ due
date.

Values:

-  earliest to latest

-  latest to earliest

`RecordLocalUseOnReturn <#RecordLocalUseOnReturn>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't record

Asks: \_\_\_ local use when an unissued item is checked in.

Values:

-  Don't record

-  Record

Description:

-  When this preference is set to "Don't record" you can record local
   use of items by checking items out to the statistical patron. With
   this preference set to "Record" you can record local use by checking
   out to the statistical patron and/or by checking in a book that is
   not currently checked out.

`ShowAllCheckins <#ShowAllCheckins>`__
''''''''''''''''''''''''''''''''''''''

Default: Do not show

Asks: \_\_\_ all items in the "Checked-in items" list, even items that
were not checked out.

Values:

-  Do not show

-  Show

Description:

-  When items that are not currently checked out are checked in they
   don't show on the list of checked in items. This preference allows
   you to choose how you'd like the log of checked in items displays.

`SpecifyDueDate <#SpecifyDueDate>`__
''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to specify a due date for a checkout.

Due dates are calculated using your circulation and fines rules, but
staff can override that if you allow them to specify a due date at
checkout.

Description:

-  This preference allows for circulation staff to change a due date
   from the automatic due date to another calendar date. This option
   would be used for circumstances in which the due date may need to be
   decreased or extended in a specific circumstance. The "Allow" setting
   would allow for this option to be utilized by staff, the "Don't
   allow" setting would bar staff from changing the due date on
   materials.

Values:

-  Allow

   Specify Due Date Box Shows
   |image41|

-  Don't allow

   Specify Due Date Box Doesn't Show
   |image42|

`SpecifyReturnDate <#SpecifyReturnDate>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ staff to specify a return date for a check in.

Values:

-  AllowAllow return date edits

-  Don't allowDon't allow return date edits

Description:

-  This preference lets you decide if staff can specify an arbitrary
   return date when checking in items.

`todaysIssuesDefaultSortOrder <#todaysIssuesDefaultSortOrder>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: latest to earliest

Asks: Sort today's checkouts on the circulation page from \_\_\_ due
date.

Values:

-  earliest to latest

-  latest to earliest

`UpdateTotalIssuesOnCirc <#UpdateTotalIssuesOnCirc>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Do not

Asks: \_\_\_ update a bibliographic record's total issues count whenever
an item is issued

Values:

-  Do

       **Important**

       This increases server load significantly; if performance is a
       concern, use the `cron job <#updateissuescron>`__ to update the
       total issues count instead.

-  Do not

Description:

-  Koha can track the number of times and item is checked out and store
   that on the item record in the database. This information is not
   stored by default. Setting this preference to 'Do' will tell Koha to
   track that info everytime the item is checked out in real time.
   Otherwise you could use the `cron job <#updateissuescron>`__ to have
   Koha update that field nightly.

`WaitingNotifyAtCheckin <#WaitingNotifyAtCheckin>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't notify

Asks: \_\_\_ librarians of waiting holds for the patron whose items they
are checking in.

Values:

-  Don't notify

-  Notify

   Notification that a hold is waiting
   |image43|

Description:

-  When checking in books you can choose whether or not to have a notice
   pop up if the patron who returned the book has a hold waiting for
   pick up. If you choose 'Notify' for WaitingNotifyAtCheckin then every
   time a hold is found for the patron who had the book out last a
   message will appear on your check in screen.

`Self Checkout <#circscoprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AllowSelfCheckReturns <#AllowSelfCheckReturns>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ patrons to return items through web-based self checkout
system.

Values:

-  Allow

-  Don't allow

Description:

-  This preference is used to determine if you want patrons to be
   allowed to return items through your self check machines. By default
   Koha's self check interface is simply for checking items out.

`AutoSelfCheckAllowed, AutoSelfCheckID & AutoSelfCheckPass <#AutoSelfCheckAllowed>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

    **Important**

    Most libraries will want to leave this set to 'Don't allow.' This
    preference turns off the requirement to log into the self checkout
    machine with a staff username and password by storing the username
    and password for automatic login.

AutoSelfCheckAllowed Default: Don't allow

Asks: \_\_\_ the web-based self checkout system to automatically login
with this staff login \_\_\_ and this password \_\_\_ .

AutoSelfCheckAllowed Values:

-  Allow

-  Don't allow

AutoSelfCheckID Value:

-  The username of a staff patron with 'circulate'
   `permissions <#patronpermissions>`__.

AutoSelfCheckPass Value:

-  The password of a staff patron with 'circulate'
   `permissions <#patronpermissions>`__.

`SCOUserCSS <#SCOUserCSS>`__
''''''''''''''''''''''''''''

Asks: Include the following CSS on all pages in the web-based self
checkout

Description:

-  The CSS entered in this preference will be used on all of your Koha
   self checkout screens.

`SCOUserJS <#SCOUserJS>`__
''''''''''''''''''''''''''

Asks: Include the following JavaScript on all pages in the web-based
self checkout

Description:

-  The JavaScript entered in this preference will effect all of your
   Koha self checkout screens.

`SelfCheckHelpMessage <#SelfCheckHelpMessage>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Include the following HTML in the Help page of the web-based self
checkout system

Description:

-  Clicking the 'Help' link in the top right of the self checkout
   interface opens up a three step process for using the self check
   interface. Adding HTML to this system preference will print that
   additional help text above what's already included.

`SelfCheckoutByLogin <#SelfCheckoutByLogin>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Barcode

Asks: Have patrons login into the web-based self checkout system with
their \_\_\_

Values:

-  Barcode

   Self Checkout Patron Card Number
   |image44|

-  Username and password

   Shelf checkout by login
   |image45|

Description:

-  This preference lets you decide how your patrons will log in to the
   self checkout machine. Barcode is the patron's card number and their
   username and password is set using the opac/staff username and
   password fields on the patron record.

`SelfCheckReceiptPrompt <#SelfCheckReceiptPrompt>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ the print receipt popup dialog when self checkout is
finished.

Values:

-  Don't show

-  Show

Description:

-  This preference controls whether a prompt shows up on the web based
   self check out when the patron clicks the 'Finish' button.

`SelfCheckTimeout <#SelfCheckTimeout>`__
''''''''''''''''''''''''''''''''''''''''

Default: 120

Asks: Time out the current patron's web-based self checkout system login
after \_\_\_ seconds.

Description:

-  After the machine is idle for the time entered in this preference the
   self check out system will log out the current patron and return to
   the starting screen.

`ShowPatronImageInWebBasedSelfCheck <#ShowPatronImageInWebBasedSelfCheck>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ the patron's picture (if one has been added) when they use
the web-based self checkout.

Values:

-  Don't show

-  Show

`WebBasedSelfCheck <#WebBasedSelfCheck>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't enable

Asks: \_\_\_ the web-based self checkout system.

Values:

-  Don't enable

-  Enable

Enabling this preference will allow access to the `self
checkout <#selfcheckout>`__ module in Koha.

`Enhanced Content <#enhancedcontent>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences >
Enhanced Content

    **Important**

    Always read the terms of service associated with external data
    sources to be sure that you are using the products within the
    allowed limits.

    **Note**

    You cannot have more than one service for cover images (including
    local cover images) set up. If you set up more than one you will get
    multiple cover images. Instead choose only one source for cover
    images.

`All <#frbrenhancedprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`FRBRizeEditions <#FRBRizeEditions>`__
''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ other editions of an item on the staff client

Values:

-  Don't show

-  Show

   Editions tab in staff client
   |image46|

Description:

-  Using the rules set forth in the Functional Requirements for
   Bibliographic records, this option, when enabled, pulls all editions
   of the same title available in your collection regardless of material
   type. Items will appear under an 'Editions' tab on the detail page
   for the title in question.. According to *Libraries Unlimited's
   Online Dictionary for Library and Information Science*
   (http://lu.com/odlis/), FRBRizing the catalog involves collating MARC
   records of similar materials. FRBRization brings together entities
   (sets of Works, Expressions, or Manifestations), rather than just
   sets of Items. It can aid patrons in selecting related items,
   expressions, and manifestations that will serve their needs. When it
   is set to "Show", the OPAC will query one or more ISBN web services
   for associated ISBNs and display an Editions tab on the details
   pages. Once this preference is enabled, the library must select one
   of the ISBN options (`ThingISBN <#ThingISBN>`__ and/or
   `XISBN <#XISBN>`__). This option is only for the Staff Client; the
   `OPACFRBRizeEditions <#OPACFRBRizeEditions>`__ option must be enabled
   to have the Editions tab appear on the OPAC.

    **Important**

    Requires that you turn on one or more of the ISBN services
    (`ThingISBN <#ThingISBN>`__ and/or `XISBN <#XISBN>`__)

`OPACFRBRizeEditions <#OPACFRBRizeEditions>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ other editions of an item on the OPAC.

Description:

-  Using the rules set forth in the Functional Requirements for
   Bibliographic records, this option, when enabled, pulls all editions
   of the same title available in your collection regardless of material
   type. Items will appear under an 'Editions' tab on the detail page
   for the title in question.. According to *Libraries Unlimited's
   Online Dictionary for Library and Information Science*
   (http://lu.com/odlis/), FRBRizing the catalog involves collating MARC
   records of similar materials. FRBRization brings together entities
   (sets of Works, Expressions, or Manifestations), rather than just
   sets of Items. It can aid patrons in selecting related items,
   expressions, and manifestations that will serve their needs. When it
   is set to "Show", the OPAC will query one or more ISBN web services
   for associated ISBNs and display an Editions tab on the details
   pages. Once this preference is enabled, the library must select one
   of the ISBN options (`ThingISBN <#ThingISBN>`__ and/or
   `XISBN <#XISBN>`__). This option is only for the OPAC; the
   `FRBRizeEditions <#FRBRizeEditions>`__ option must be turned "On" to
   have the Editions tab appear on the Staff Client.

Values:

-  Don't show

-  Show

   Editions tab in the OPAC
   |image47|

This preference pulls all editions of the same title available in your
collection regardless of material type. Items will appear under an
'Editions' tab on the detail page for the title in question.

    **Important**

    Requires that you turn on one or more of the ISBN services
    (`ThingISBN <#ThingISBN>`__ and/or `XISBN <#XISBN>`__)

`Amazon <#amazonprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^

`AmazonAssocTag <#AmazonAssocTag>`__
''''''''''''''''''''''''''''''''''''

Asks: Put the associate tag \_\_\_ on links to Amazon.

    **Note**

    This can net your library referral fees if a patron decides to buy
    an item after clicking through to Amazon from your site.

Description:

-  An Amazon Associates Tag allows a library to earn a percentage of all
   purchases made on Amazon when a patron accesses Amazon's site via
   links on the library's website. More information about the Amazon
   Associates program is available at Amazon's Affiliate Program's
   website, https://affiliate-program.amazon.com/. Before a tag can be
   obtained, however, the library must first apply for an Amazon Web
   Services (AWS) account. Applications are free of charge and can be
   made at http://aws.amazon.com. Once an AWS account has been
   established, the library can then obtain the Amazon Associates Tag.

Sign up at: https://affiliate-program.amazon.com/

`AmazonCoverImages <#AmazonCoverImages>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ cover images from Amazon on search results and item detail
pages on the staff interface.

Values:

-  Don't show

-  Show

Description:

-  This preference makes it possible to either allow or prevent Amazon
   cover images from being displayed in the Staff Client. Cover images
   are retrieved by Amazon, which pulls the content based on the first
   ISBN number in the item's MARC record. Amazon offers this service
   free of charge. If the value for this preference is set to "Show",
   the cover images will appear in the Staff Client, and if it is set to
   "Don't show", the images will not appear. Finally, if you're using
   Amazon cover images, all other cover image services must be disabled.
   If they are not disabled, they will prevent AmazonCoverImages from
   functioning properly.

`AmazonLocale <#AmazonLocale>`__
''''''''''''''''''''''''''''''''

Default: American

Asks: Use Amazon data from its \_\_\_ website.

Value:

-  American

-  British

-  Canadian

-  French

-  German

-  Japanese

`OPACAmazonCoverImages <#OPACAmazonCoverImages>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ cover images from Amazon on search results and item detail
pages on the OPAC.

Values:

-  Don't show

-  Show

Description:

-  This preference makes it possible to either allow or prevent Amazon
   cover images from being displayed in the OPAC. Cover images are
   retrieved by Amazon, which pulls the content based on the first ISBN
   number in the item's MARC record. Amazon offers this service free of
   charge. If the value for this preference is set to "Show", the cover
   images will appear in the OPAC, and if it is set to "Don't show", the
   images will not appear. Finally, if you're using Amazon cover images,
   all other cover image services must be disabled. If they are not
   disabled, they will prevent AmazonCoverImages from functioning
   properly.

`Babelthèque <#Babelthequeprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`Babeltheque <#Babeltheque>`__
''''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ include information (such as reviews and citations) from
Babelthèque in item detail pages on the OPAC.

Description:

-  This preference makes it possible to display a Babeltheque tab in the
   OPAC, allowing patrons to access tags, reviews, and additional title
   information provided by Babeltheque. The information which
   Babeltheque supplies is drawn from the French language-based
   `Babelio.com <http://www.babelio.com/>`__, a French service similar
   to LibraryThing for Libraries. More information about Babeltheque is
   available through its website,
   `http://www.babeltheque.com <http://www.babeltheque.com/>`__.
   Libraries that wish to allow access to this information must first
   register for the service at http://www.babeltheque.com. Please note
   that this information is only provided in French.

Values:

-  Do

   Data from Babelthèque on the bib record
   |image48|

-  Don't

`Babeltheque\_url\_js <#Babeltheque_url_js>`__
''''''''''''''''''''''''''''''''''''''''''''''

Asks: \_\_\_ Defined the url for the Babeltheque javascript file (eg.
http://www.babeltheque.com/bw\_XX.js)

`Babeltheque\_url\_update <#Babeltheque_url_update>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: \_\_\_ Defined the url for the Babeltheque update periodically
(eq. http://www.babeltheque.com/.../file.csv.bz2).

`Baker & Taylor <#btcontentprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    **Important**

    This is a pay service, you must contact Baker & Taylor to subscribe
    to this service before setting these options.

`BakerTaylorBookstoreURL <#BakerTaylorBookstoreURL>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Baker and Taylor "My Library Bookstore" links should be accessed
at https:// \_\_\_ isbn

Description:

-  Some libraries generate additional funding for the library by selling
   books and other materials that are purchased from or have been
   previously leased from Baker & Taylor. These materials can be
   accessed via a link on the library's website. This service is often
   referred to as "My Library Bookstore." In order to participate in
   this program, the library must first register and pay for the service
   with Baker & Taylor. Additional information about this and other
   services provided by Baker & Taylor is available at the Baker &
   Taylor website, http://www.btol.com. The BakerTaylorBookstoreURL
   preference establishes the URL in order to link to the library's
   Baker & Taylor-backed online bookstore, if such a bookstore has been
   established. The default for this field is left blank; if no value is
   entered, the links to My Library Bookstore will remain inactive. If
   enabling this preference, enter the library's Hostname and Parent
   Number in the appropriate location within the URL. The "key" value
   (key=) should be appended to the URL, and https:// should be
   prepended.

This should be filled in with something like
koha.mylibrarybookstore.com/MLB/actions/searchHandler.do?nextPage=bookDetails&parentNum=10923&key=

    **Note**

    Leave it blank to disable these links.

    **Important**

    Be sure to get this information from Baker & Taylor when
    subscribing.

`BakerTaylorEnabled <#BakerTaylorEnabled>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Don't add

Asks: \_\_\_ Baker and Taylor links and cover images to the OPAC and
staff client. This requires that you have entered in a username and
password (which can be seen in image links).

Values:

-  Add

-  Don't add

Description:

-  This preference makes it possible to display Baker & Taylor content
   (book reviews, descriptions, cover images, etc.) in both the Staff
   Client and the OPAC. Libraries that wish to display Baker & Taylor
   content must first register and pay for this service with Baker &
   Taylor (http://www.btol.com). If Baker & Taylor content is enabled be
   sure to turn off other cover and review services to prevent
   interference.

    **Important**

    To use this you will need to also set the `BakerTaylorUsername &
    BakerTaylorPassword <#btuserpass>`__ system preferences

`BakerTaylorUsername & BakerTaylorPassword <#btuserpass>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Access Baker and Taylor using username \_\_\_ and password \_\_\_

Descriptions:

-  This setting in only applicable if the library has a paid
   subscription to the external Content Café service from Baker &
   Taylor. Use the box provided to enter in the library's Content Café
   username and password. Also, ensure that the
   `BakerTaylorBookstoreURL <#BakerTaylorBookstoreURL>`__ and
   `BakerTaylorEnabled <#BakerTaylorEnabled>`__ settings are properly
   set. The Content Café service is a feed of enhanced content such as
   cover art, professional reviews, and summaries that is displayed
   along with Staff Client/OPAC search results. For more information on
   this service please see the Baker & Taylor website:
   http://www.btol.com

    **Important**

    Be sure to get this information from Baker & Taylor when
    subscribing.

`Coce Cover images cache <#coceimages>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Coce is a remote image URL cache. With this option, cover images are not
fetched directly from Amazon, Google, and so on. Their URLs are
requested via a web service to Coce which manages a cache of URLs.

`Coce <#Coce>`__
''''''''''''''''

Default: Don't enable

Asks: \_\_\_ a Coce image cache service.

Values:

-  Don't enable

-  Enable

Description:

-  Coce has many benefits when it comes to choosing and displaying cover
   images in Koha:

   -  If a book cover is not available from a provider, but is available
      from another one, Koha will be able to display a book cover, which
      isn't the case now

   -  Since URLs are cached, it isn't necessary for each book cover to
      request, again and again, the provider, and several of them if
      necessary.

   -  Amazon book covers are retrieved with Amazon Product Advertising
      API, which means that more covers are retrieved (ISBN13).

       **Important**

       Coce does not come bundled with Koha. Your Koha install will not
       already have a Coce server set up. Before enabling this
       functionality you will want to be sure to have a Coce server set
       up. Instructions on installing and setting up Coce can be found
       on the official github page at https://github.com/fredericd/coce.

`CoceHost <#CoceHost>`__
''''''''''''''''''''''''

Asks: Coce server URL \_\_\_

Description:

-  This will be the full URL (starting with http://) to your Coce
   server.

`CoceProviders <#CoceProviders>`__
''''''''''''''''''''''''''''''''''

Asks: Use the following providers to fetch the covers \_\_\_

Values:

-  [Select all]

-  Amazon Web Services

-  Google Books

-  Open Library

Description:

-  The providers chosen here will be used to gather cover images for
   display in your Koha catalog.

`Google <#googleprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^

`GoogleJackets <#GoogleJackets>`__
''''''''''''''''''''''''''''''''''

Default: Don't add

Asks: \_\_\_ cover images from Google Books to search results and item
detail pages on the OPAC.

Values:

-  Add

-  Don't add

Description:

-  This setting controls the display of applicable cover art from the
   free Google Books database, via the Google Books API. Please note
   that to use this feature, all other cover services should be turned
   off.

`HTML5 Media <#html5>`__
^^^^^^^^^^^^^^^^^^^^^^^^

`HTML5MediaEnabled <#HTML5MediaEnabled>`__
''''''''''''''''''''''''''''''''''''''''''

Default: not at all

Asks: Show a tab with a HTML5 media player for files catalogued in field
856 \_\_\_

Values:

-  in OPAC and staff client

-  in the OPAC

   HTML5 Media in the OPAC
   |image49|

-  in the staff client

   HTML5 Media in the staff client
   |image50|

-  not at all

Description:

-  If you have media elements in the 856 of your MARC record this
   preference can run/show those media files in a separate tab using
   HTML5.

`HTML5MediaExtensions <#HTML5MediaExtensions>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: webm\|ogg\|ogv\|oga\|vtt

Asks: Media file extensions \_\_\_

Description:

-  Enter in file extensions separated with bar (\|)

`HTML5MediaYouTube <#HTML5MediaYouTube>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't embed

    **Important**

    To turn this on first enable
    `HTML5MediaEnabled <#HTML5MediaEnabled>`__

Asks: \_\_\_ YouTube links as videos.

Values:

-  Don't embed

-  Embed

Description:

-  This preference will allow MARC21 856$u that points to YouTube to
   appear as a playable video on the pages defined in
   `HTML5MediaEnabled <#HTML5MediaEnabled>`__.

`IDreamLibraries <#IDreamLibraries>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`IDreamBooks.com <http://idreambooks.com/>`__ aggregates book reviews by
critics to help you discover the very best of what's coming out each
week. These preferences let you integrated content from
`IDreamBooks.com <http://IDreamBooks.com>`__ in to your Koha OPAC.

    **Note**

    This is a new website and has limited content, so you may only see
    these features on new popular titles until the database grows some
    more.

`IDreamBooksReadometer <#IDreamBooksReadometer>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't add

Asks: \_\_\_ a "Readometer" that summarizes the reviews gathered by
IDreamBooks.com to the OPAC details page.

Values:

-  Add

   Readometer on the details page
   |image51|

-  Don't add

`IDreamBooksResults <#IDreamBooksResults>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Don't add

Asks: \_\_\_ the rating from IDreamBooks.com to OPAC search results.

Values:

-  Add

   iDreamBooks rating on search results
   |image52|

-  Don't add

`IDreamBooksReviews <#IDreamBooksReviews>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Don't add

Asks: \_\_\_ a tab on the OPAC details with book reviews from critics
aggregated by IDreamBooks.com.

Values:

-  Add

   Reviews tab on the detail page
   |image53|

-  Don't add

`LibraryThing <#librarythingprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

LibraryThing for Libraries is a pay service. You must first contact
LibraryThing directly for pricing and subscription information. Learn
more at http://www.librarything.com/forlibraries. Also, for further
configuration instructions please see the LibraryThing Wiki:
http://www.librarything.com/wiki/index.php/Koha

`LibraryThingForLibrariesEnabled <#LibraryThingForLibrariesEnabled>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ reviews, similar items, and tags from Library Thing for
Libraries on item detail pages on the OPAC.

Values:

-  Don't show

-  Show

Description:

-  This setting is only applicable if the library has a paid
   subscription to the external LibraryThing for Libraries service. This
   service can provide patrons with the display of expanded information
   on catalog items such as book recommendations. It also can offer
   advanced features like tagged browsing, patron written reviews, and a
   virtual library display accessed from the details tab.

    **Important**

    If this is set to 'show' you will need to enter a value in the
    '`LibraryThingForLibrariesID <#LibraryThingForLibrariesID>`__'
    system preference.

`LibraryThingForLibrariesID <#LibraryThingForLibrariesID>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Access Library Thing for Libraries using the customer ID \_\_\_

Description:

-  This setting is only applicable if the library has a paid
   subscription to the external LibraryThing for Libraries service. Use
   the box provided to enter in the library's LibraryThing for Libraries
   ID as provided to the library by LibraryThing. The ID number is a
   series of numbers in the form ###-#########, and can be found on the
   library's account page at LibraryThing for Libraries. This service
   can provide patrons with the display of expanded information on
   catalog items such as book recommendations and cover art. It also can
   offer advanced features like tagged browsing, patron written reviews,
   and a virtual library display accessed from the details tab.

`LibraryThingForLibrariesTabbedView <#LibraryThingForLibrariesTabbedView>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: in line with bibliographic information

Asks: Show Library Thing for Libraries content \_\_\_

Values:

-  in line with bibliographic information

-  in tabs

Description:

-  This setting is only applicable if the library has a paid
   subscription to the external LibraryThing for Libraries service. This
   service can provide patrons with the display of expanded information
   on catalog items such as book recommendations and cover art. It also
   can offer advanced features like tagged browsing, patron written
   reviews, and a virtual library display accessed from the details tab.

`ThingISBN <#ThingISBN>`__
''''''''''''''''''''''''''

Default: Don't use

Asks: \_\_\_ the ThingISBN service to show other editions of a title

Values:

-  Don't use

-  Use

Description:

-  Set to 'Use' to display an "Editions" tab on the item's detail page.
   Editions are listed, complete with cover art (if you have one of the
   cover services enabled) and bibliographic information. The feed comes
   from LibraryThing's ThingISBN web service. This is a free service to
   non-commercial sites with fewer than 1,000 requests per day.

    **Important**

    Requires `FRBRizeEditions <#FRBRizeEditions>`__ and/or
    `OPACFRBRizeEditions <#OPACFRBRizeEditions>`__ set to 'show'

    **Important**

    This is separate from Library Thing for Libraries and does not have
    a cost associated with it.

`Local Cover Images <#localimages>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AllowMultipleCovers <#AllowMultipleCovers>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ multiple images to be attached to each bibliographic
record.

Values:

-  Allow

-  Don't allow

Description:

-  If this preference is set to 'Allow' then you can upload multiple
   images that will appear in the images tab on the bib record in the
   OPAC and the staff client. This preference requires that either one
   or both `LocalCoverImages <#LocalCoverImages>`__ and
   `OPACLocalCoverImages <#OPACLocalCoverImages>`__ are set to
   'Display.'

   Multiple cover images
   |image54|

`LocalCoverImages <#LocalCoverImages>`__
''''''''''''''''''''''''''''''''''''''''

Default: Don't display

Asks: \_\_\_ local cover images on intranet search and details pages.

Values:

-  Display

-  Don't display

Description:

-  Setting this preference to 'Display' allows you to upload your own
   cover images to bib records and display them on the detail page in
   the staff client. At this time the cover will only show under the
   'Images' tab on the holdings table on the detail display, not next to
   the title at the top left or on the search results.

`OPACLocalCoverImages <#OPACLocalCoverImages>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't display

Asks: \_\_\_ local cover images on OPAC search and details pages.

Values:

-  Display

-  Don't display

Description:

-  Setting this preference to 'Display' allows you to upload your own
   cover images to bib records and display them on the detail page and
   search results in the OPAC.

`Novelist Select <#novelistselect>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Novelist Select is not a free service. Contact your Ebsco representitive
to get your log in information to embed this content in the OPAC.

    **Important**

    Novelist Select does not include cover images for the search results
    and bibliographic detail pages. You can choose any other cover image
    service for this content or you can contract with Ebsco to get
    access to the `Baker & Taylor Content Cafe <#btcontentprefs>`__ for
    an added fee.

`NovelistSelectEnabled <#NovelistSelectEnabled>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't add

Asks: \_\_\_ Novelist Select content to the OPAC.

Values:

-  Add

-  Don't add

    **Important**

    Enabling this requires that you have entered in a user profile and
    password in the `NovelistSelectProfile &
    NovelistSelectPassword <#NovelistSelectProfile>`__ preferences

Description:

-  Novelist Select from Ebsco is a subscription service that can provide
   additional content in the OPAC.

`NovelistSelectProfile & NovelistSelectPassword <#NovelistSelectProfile>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Access Novelist Select using user profile \_\_\_ and password
\_\_\_.

    **Important**

    This information will be visible if someone views the source code on
    your OPAC.

Description:

-  Novelist Select from Ebsco is a subscription service that can provide
   additional content in the OPAC.
   
`NovelistSelectStaffEnabled <#NovelistSelectStaffEnabled>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't add

Asks: \_\_\_ Novelist Select content to the Staff client (requires that
you have entered in a user profile and password, which can be seen in
image links).

Values:

-  Don't add

-  Add

`NovelistSelectStaffView <#NovelistSelectStaffView>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: in a tab

Asks: Display Novelist Select staff content \_\_\_.

Values:

-  above the holdings table

-  below the holdings table

-  in a tab

`NovelistSelectView <#NovelistSelectView>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: in an OPAC tab

Asks: Display Novelist Select content \_\_\_

Description:

-  Novelist Select provides a lot of content, for that reason you have
   four choices of where to display this content. The default view is in
   a tab in the holdings table.

   Novelist Select in a tab
   |image55|

   The content is the same if you choose to show it above the holdings
   table or below it. If shown in the right column of the page it's the
   same content, but displays a bit differently since space is limited.

   Novelist Select on the side
   |image56|

Values:

-  above the holdings table

-  below the holdings table

-  in an OPAC tab

-  under the Save Record dropdown on the right

`OCLC <#oclcprefs>`__
^^^^^^^^^^^^^^^^^^^^^

`OCLCAffiliateID <#OCLCAffiliateID>`__
''''''''''''''''''''''''''''''''''''''

Asks: Use the OCLC affiliate ID \_\_\_ to access the xISBN service.

Description:

-  This setting is only applicable if the library has an OCLC Affiliate
   ID. This allows WorldCat searching in the OPAC via the XISBN
   programming interface. Simply enter the library's OCLC Affiliate ID
   in the box provided. Please note that using this data is only
   necessary if `FRBRizeEditions <#FRBRizeEditions>`__ and/or
   `OPACFRBRizeEditions <#OPACFRBRizeEditions>`__ and `XISBN <#XISBN>`__
   settings are enabled. For more information on this service please
   visit the OCLC website:
   http://www.worldcat.org/affiliate/default.jsp.

    **Important**

    Unless you have signed up for an ID with OCLC, you are limited to
    1000 requests per day. Available at:
    http://www.worldcat.org/affiliate/webservices/xisbn/app.jsp

`XISBN <#XISBN>`__
''''''''''''''''''

Default: Don't use

Asks: \_\_\_ the OCLC xISBN service to show other editions of a title

Description:

-  Set to 'Use' to display an "Editions" tab on the item's detail page.
   Editions are listed, complete with cover art and bibliographic
   information. The feed comes from OCLC's xISBN web service. The feed
   limit for non-commercial sites is 1000 requests per day.

Values:

-  Don't use

-  Use

    **Important**

    Requires `FRBRizeEditions <#FRBRizeEditions>`__ and/or
    `OPACFRBRizeEditions <#OPACFRBRizeEditions>`__ set to 'show'

`XISBNDailyLimit <#XISBNDailyLimit>`__
''''''''''''''''''''''''''''''''''''''

Default: 999

Asks: Only use the xISBN service \_\_\_ times a day.

    **Important**

    Unless you have signed up for an ID with OCLC, you are limited to
    1000 requests per day. Available at:
    http://www.worldcat.org/affiliate/webservices/xisbn/app.jsp

`Open Library <#OpenLibraryPrefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`OpenLibraryCovers <#OpenLibraryCovers>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't add

Asks: \_\_\_ cover images from Open Library to search results and item
detail pages on the OPAC.

Values:

-  Add

-  Don't add

Description:

-  This setting controls the display of applicable cover art from the
   free Open Library database, via the Open Library API. Please note
   that to use this feature, all other cover services should be turned
   off.

`OpenLibrarySearch <#OpenLibrarySearch>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ search results from Open Library on the OPAC.

Values:

-  Don't show

-  ShowOpen Library results

`Overdrive <#overdriveprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

OverDrive is an pay service. You must first contact OverDrive directly
for pricing and subscription information. Enabling this service will
integrate Overdrive results in to your OPAC searches. You will have to
apply for these 3 pieces of information through an application as an API
developer. Overdrive API applications are evaluated once a week so you
may not be able to use this feature immediately after signing up. To
learn more please contact your OverDrive representative.

Overdrive results
|image57|

`OverDriveCirculation <#OverDriveCirculation>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't enable

Asks: \_\_\_ users to access their OverDrive circulation history, and circulate
items. If you enable access, you must register auth return url of
http(s)://my.opac.hostname/cgi-bin/koha/external/overdrive/auth.pl with OverDrive.

Values:

-  Don't enable

-  Enable

`OverDriveClientKey and OverDriveClientSecret <#OverDriveClientKey>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Include OverDrive availability information with the client key
\_\_ and client secret \_\_\_

Description:

-  OverDrive customers can get this information by visiting the
   `OverDrive Developer
   Portal <https://developer.overdrive.com/docs/getting-started>`__ and
   following the instructions found there to apply as an API developer.
   Once this data and the `OverDriveLibraryID <#OverDriveLibraryID>`__
   are populated you will see OverDrive results on your OPAC searches.

`OverDriveLibraryID <#OverDriveLibraryID>`__
''''''''''''''''''''''''''''''''''''''''''''

Asks: Show items from the OverDrive catalog of library # \_\_\_

Description:

-  OverDrive customers can get this information by visiting the
   `OverDrive Developer
   Portal <https://developer.overdrive.com/docs/getting-started>`__ and
   following the instructions found there to apply as an API developer.
   Once this data and the `OverDriveClientKey and
   OverDriveClientSecret <#OverDriveClientKey>`__ are populated you will
   see OverDrive results on your OPAC searches.

`Plugins <#pluginprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^

`UseKohaPlugins <#UseKohaPlugins>`__
''''''''''''''''''''''''''''''''''''

Default: Don't enable

Asks: \_\_\_ the ability to use Koha Plugins.

Values:

-  Don't enable

-  Enable

    **Note**

    The plugin system must also be enabled in the Koha configuration
    file to be fully enabled. Learn more in the `Plugins
    chapter <#pluginsystem>`__.

`Syndetics <#Syndeticsprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Syndetics is a pay service. You must first contact Syndetics directly
for pricing and subscription information.

`SyndeticsAuthorNotes <#SyndeticsAuthorNotes>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ notes about the author of a title from Syndetics on item
detail pages on the OPAC.

Values:

-  Don't show

-  Show

Description:

-  When this option is set to "Show", Syndetics provides notes and short
   author biographies for more that 300,000 authors, in both fiction and
   nonfiction. With this option enabled the library can display
   Syndetics Author Notes on the OPAC. According to the Syndetics
   Solutions website (http://www.bowker.com/syndetics/), Author Notes
   include lists of contributors for many multi-author texts and
   compilations. The `SyndeticsClientCode <#SyndeticsClientCode>`__ must
   be entered and the `SyndeticsEnabled <#SyndeticsEnabled>`__ option
   must be activated before this service can be used.

`SyndeticsAwards <#SyndeticsAwards>`__
''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ information from Syndetics about the awards a title has won
on item detail pages on the OPAC.

Values:

-  Don't show

-  Show

Description:

-  When this option is set to "Show", Syndetics provides its clients
   with a list of awards that any title has won. With this service
   enabled the library can display those awards for each book on its
   website. For each book or item that comes up during a user search,
   the list of awards for that title will be displayed. When a user
   clicks on a given award, information about that award is presented
   along with a list of the other titles that have won that award. If
   the user clicks on any title in the list, they will see holdings
   information about that title in their region. This option is a paid
   subscription service. The
   `SyndeticsClientCode <#SyndeticsClientCode>`__ must be entered and
   the `SyndeticsEnabled <#SyndeticsEnabled>`__ option must be activated
   before this service can be used.

`SyndeticsClientCode <#SyndeticsClientCode>`__
''''''''''''''''''''''''''''''''''''''''''''''

Asks: Use the client code \_\_\_ to access Syndetics.

Description:

-  Once the library signs up for Syndetics' services, Syndetics will
   provide the library with an access code. (Visit the Syndetics
   homepage at http://www.bowker.com/syndetics/ for more information.)
   This is the code that must be entered to access Syndetics'
   subscription services. Syndetics is a paid subscription service. This
   value must be entered before
   `SyndeticsEditions <#SyndeticsEditions>`__ can be enabled. If the
   code is lost, corrupted, or forgotten, a new one can be obtained from
   http://www.bowker.com/syndetics/.

    **Important**

    You will need to get your client code directly from Syndetics.

`SyndeticsCoverImages & SyndeticsCoverImageSize <#SyndeticsCoverImages>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

SyndeticsCoverImages Default: Don't show

SyndeticsCoverImageSize Default: medium

Asks: \_\_\_ cover images from Syndetics on search results and item
detail pages on the OPAC in a \_\_\_ size.

Descriptions:

-  When enabled, SyndeticsCoverImages, allows libraries to display
   Syndetics' collection of full-color cover images for books, videos,
   DVDs and CDs on their OPAC. For each book or item that comes up
   during a user search, the cover image for that title will be
   displayed. Since these cover images come in three sizes, the optimum
   size must be selected using the SyndeticsCoverImageSize preference
   after SyndeticsCoverImages are enabled. Syndetics cover images come
   in two sizes: mid-size (187 x 187 pixels), and large (400 x 400
   pixels). Syndetics is a paid subscription service. The
   `SyndeticsClientCode <#SyndeticsClientCode>`__ must be entered and
   the `SyndeticsEnabled <#SyndeticsEnabled>`__ option must be activated
   before this service can be used. Other cover image preferences should
   also be disabled to avoid interference.

SyndeticsCoverImages Values:

-  Don't show

-  Show

SyndeticsCoverImageSize Values:

-  medium

-  large

`SyndeticsEditions <#SyndeticsEditions>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ information about other editions of a title from Syndetics
on item detail pages on the OPAC

Description:

-  When enabled this option shows information on other editions of a
   title from Syndetics on the item detail pages of the OPAC. Syndetics
   is a paid subscription service. The
   `SyndeticsClientCode <#SyndeticsClientCode>`__ must be entered and
   the `SyndeticsEnabled <#SyndeticsEnabled>`__ option must be activated
   before this service can be used.

Values:

-  Don't show

-  Show

    **Important**

    Requires `OPACFRBRizeEditions <#OPACFRBRizeEditions>`__ set to
    'show'

`SyndeticsEnabled <#SyndeticsEnabled>`__
''''''''''''''''''''''''''''''''''''''''

Default: Don't use

Asks: \_\_\_ content from Syndetics.

Values:

-  Don't use

-  Use

Description:

-  When this option is enabled any of the Syndetics options can be used.

    **Important**

    Requires that you enter your
    `SyndeticsClientCode <#SyndeticsClientCode>`__ before this content
    will appear.

`SyndeticsExcerpt <#SyndeticsExcerpt>`__
''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ excerpts from of a title from Syndetics on item detail
pages on the OPAC.

Values:

-  Don't show

-  Show

Description:

-  This preference allows Syndetics to display excerpts given to them
   from selected publishers. The excerpts are available from prominently
   reviewed new titles, both fiction and non-fiction. The excerpts
   include poems, essays, recipes, forwards and prefaces. Automatic
   links provided by the ISBNs within local MARC records are required to
   integrate Syndetics secured, high-speed Internet servers to the
   library OPACs. For more information see
   (http://www.bowker.com/syndetics/).

`SyndeticsReviews <#SyndeticsReviews>`__
''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ reviews of a title from Syndetics on item detail pages on
the OPAC.

Values:

-  Don't show

-  Show

Description:

-  Syndetics Reviews is an accumulation of book reviews available from a
   variety of journals and serials. The reviews page displays colored
   images of reviewed books dust jackets, partnered with the names of
   the journal or serial providing the review. Clicking on an icon opens
   a window revealing the book title, author's name, book cover icon and
   the critic's opinion of the book. Automatic links provided by the
   ISBNs within local MARC records are required to integrate Syndetics
   secured, high-speed Internet servers to the library OPACs. For more
   information see (http://www.bowker.com/syndetics/).

`SyndeticsSeries <#SyndeticsSeries>`__
''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ information on other books in a title's series from
Syndetics on item detail pages on the OPAC.

Values:

-  Don't show

-  Show

Description:

-  Each fiction title within a series is linked to the complete series
   record. The record displays each title in reading order and also
   displays the publication order, if different. Alternate series titles
   are also displayed. Automatic links provided by the ISBNs within
   local MARC records are required to integrate Syndetics secured, high-
   speed Internet servers to the library OPACs. For more information see
   (http://www.bowker.com/syndetics/).

`SyndeticsSummary <#SyndeticsSummary>`__
''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ a summary of a title from Syndetics on item detail pages on
the OPAC.

Values:

-  Don't show

-  Show

Description:

-  Providing more than 5.6 million summaries and annotations derived
   from book jackets, edited publisher copy, or independently written
   annotations from Book News, Inc. Covering fiction and non-fiction,
   this summaries option provides annotations on both trade and
   scholarly titles. For more information see
   (http://www.bowker.com/syndetics/).

`SyndeticsTOC <#SyndeticsTOC>`__
''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ the table of contents of a title from Syndetics on item
detail pages on the OPAC.

Values:

-  Don't show

-  Show

Description:

-  This preference allows staff and patrons to review the Table of
   Contents from a wide variety of publications from popular self-help
   books to conference proceedings. Specific Information access is the
   main purpose for this option, allowing patrons guidance to their
   preferred section of the book. Special arrangements with selected
   book services is used to obtain the table of contents for new
   publications each year. Automatic links provided by the ISBNs within
   local MARC records are required to integrate Syndetics secured,
   high-speed Internet servers to the library OPACs. For more
   information see (http://www.bowker.com/syndetics/).

`Tagging <#taggingprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^

`TagsEnabled <#TagsEnabled>`__
''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons and staff to put tags on items.

Values:

-  Allow

-  Don't allow

Description:

-  Set to 'Allow' enable tagging. A tag is metadata, a word added to
   identify an item. Tags allow patrons to classify materials on their
   own. TagsEnabled is the main switch that permits the tagging
   features. TagsEnable must be set to 'Allow' to allow for other
   tagging features.

`TagsExternalDictionary <#TagsExternalDictionary>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Allow tags in the dictionary of the ispell executable \_\_\_ on
the server to be approved without moderation.

Description:

-  The dictionary includes a list of accepted and rejected tags. The
   accepted list includes all the tags that have been pre-allowed. The
   rejected list includes tags that are not allowed. This preference
   identifies the "accepted" dictionary used. Ispell is an open source
   dictionary which can be used as a list of accepted terms. Since the
   dictionary allows for accurately spelled obscenities, the libraries
   policy may dictate that modifications are made to the Ispell
   dictionary if this preference is use. For more information about
   Ispell http://www.gnu.org/software/ispell/ispell.html. Enter the path
   on your server to a local ispell executable, used to set
   $Lingua::Ispell::path.

`TagsInputOnDetail <#TagsInputOnDetail>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to input tags on item detail pages on the OPAC.

Values:

-  Allow

   Add Tags on Detail
   |image59|

-  Don't allow

`TagsInputOnList <#TagsInputOnList>`__
''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to input tags on search results on the OPAC.

Values:

-  Allow

   Tags on Search Results
   |image58|

-  Don't allow

`TagsModeration <#TagsModeration>`__
''''''''''''''''''''''''''''''''''''

Default: Don't require

Asks: \_\_\_ that tags submitted by patrons be reviewed by a staff
member before being shown.

Values:

-  Don't require

-  Require

Description:

-  When set to 'Require,' all tags to be first filtered by the tag
   moderator. Only approved tags will be visible to patrons. When set to
   'Don't require' tags will bypass the tag moderator and patrons' tags
   to be immediately visible. When this preference is enabled the
   moderator, a staff member, would approve the tag in the Staff Client.
   The moderator will have the option to approve or reject each pending
   tag suggestion.

When moderation is required all tags go through the tag moderation tool
before becoming visible.

-  *Get there:* More > Tools > `Tags <#tagsmoderation>`__

`TagsShowOnDetail <#TagsShowOnDetail>`__
''''''''''''''''''''''''''''''''''''''''

Default: 10

Asks: Show \_\_\_ tags on item detail pages on the OPAC.

    **Note**

    Set the value to 0 (zero) to turn this feature off.

`TagsShowOnList <#TagsShowOnList>`__
''''''''''''''''''''''''''''''''''''

Default: 6

Asks: Show \_\_\_ tags on search results on the OPAC.

    **Note**

    Set the value to 0 (zero) to turn this feature off.

`I18N/L10N <#l18nprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~

These preferences control your Internationalization and Localization
settings.

*Get there:* More > Administration > Global System Preferences >
I18N/L10N

`AddressFormat <#AddressFormat>`__
''''''''''''''''''''''''''''''''''

Default: US style ([Street number], [Address] - [City], [Zip/Postal
Code], [Country])

Asks: Format postal addresses using \_\_\_

Values:

-  German style ([Address] [Street number] - [Zip/Postal Code] [City] -
   [Country])

-  French style ([Street number] [Address] - [ZIP/Postal Code] [City] -
   [Country])

-  US style ([Street number], [Address] - [City], [Zip/Postal Code],
   [Country])

Description:

-  This preference will let you control how Koha displays patron
   addresses given the information entered in the various fields on
   their record.

`alphabet <#alphabet>`__
''''''''''''''''''''''''

Default: A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

Asks: Use the alphabet \_\_\_ for lists of browsable letters. This
should be a space separated list of uppercase letters.

Description:

-  This preference allows you define your own alphabet for browsing
   patrons in Koha.

   Alphabet browse on patron module
   |image60|

`CalendarFirstDayOfWeek <#CalendarFirstDayOfWeek>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Sunday

Asks: Use \_\_\_ as the first day of week in the calendar.

Values:

-  Sunday

-  Monday

-  Tuesday

-  Wednesday

-  Thursday

-  Friday

-  Saturday

Description:

-  Using this preference you can control what day shows as the first day
   of the week in the calendar pop ups throughout Koha and on the
   Calendar tool. If you change this preference and don't see a change
   in your browser try clearing your cache since it makes changes to the
   Javascript on these pages.

`dateformat <#dateformat>`__
''''''''''''''''''''''''''''

Default: mm/dd/yyyy

Asks: Format dates like \_\_\_

Values:

-  dd.mm.yyyy

-  dd/mm/yyyy

-  mm/dd/yyyy

-  yyyy/mm/dd

Description:

-  This preference controls how the date is displayed. The options are
   the United States method, mm/dd/yyyy (04/24/2010), the metric method,
   dd/mm/yyyy (24/04/2010) or ISO, which is the International Standard
   of Organization, yyyy/mm/dd (2010/04/24). The International Standard
   of Organization would primarily be used by libraries with locations
   in multiple nations that may use different date formats, to have a
   single display type, or if the library would be in a region that does
   not use the United States or metric method. More information
   regarding the ISO date format can be found at
   http://www.iso.org/iso/iso_catalogue.htm.

`language <#languagepref>`__
''''''''''''''''''''''''''''

Default: English

Asks: Enable the following languages on the staff interface

Values:

-  English

To install additional languages please refer to
http://wiki.koha-community.org/wiki/Installation_of_additional_languages_for_OPAC_and_INTRANET_staff_client

`opaclanguages <#opaclanguages>`__
''''''''''''''''''''''''''''''''''

Default: English

Asks: Enable the following languages on the OPAC

Values:

-  English

    **Note**

    To install additional languages you need to run
    misc/translation/install-code.pl. For example, to install French you
    would run the following command install-code.pl fr-FR to make the
    templates, once they exist and are in the right place then they will
    show up as an option in this preference.

`opaclanguagesdisplay <#opaclanguagesdisplay>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ patrons to select their language on the OPAC.

Values:

-  Allow

   -  Patrons can choose their language from a list at the bottom of the
      public catalog

      Language selector in OPAC
      |image61|

-  Don't allow

   -  The public catalog will not give an option to choose a language

Description:

-  Using the `OpacLangSelectorMode <#OpacLangSelectorMode>`__ preference
   you can decide where these language options will appear in the public
   catalog.

`TimeFormat <#TimeFormat>`__
''''''''''''''''''''''''''''

Default: 24 hour format

Asks: Format times in \_\_\_

Values:

-  12 hour format (eg 02:18PM)

-  24 hour format (eg 14:18)

`TranslateNotices <#TranslateNotices>`__
''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ notices to be translated. If set, notices will be translatable from
the "Notices and Slips" interface. The language used to send a notice to a patron
will be the one defined for the patron.

Values:

-  Don't allow

-  Allow

`Labs <#labsprefs>`__
~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences > Labs

The preferences in this section are for experimental features that need
additional testing and debugging.

`EnableAdvancedCatalogingEditor <#EnableAdvancedCatalogingEditor>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: Don't enable

Asks: \_\_\_ the advanced cataloging editor.

Description:

-  This preference will allow you to choose between a basic editor and a
   advanced editor for cataloging.

    **Important**

    This feature is currently experimental, and may have bugs that cause
    corruption of records. It also does not include any support for
    UNIMARC or NORMARC fixed fields. Please help us test it and report
    any bugs, but do so at your own risk.

`Local Use <#localprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~

These preferences are defined locally.

*Get there:* More > Administration > Global System Preferences > Local
Use

    **Note**

    Sometimes preferences which are either new or outdated will appear
    in this tab, if you didn't add any preferences to this tab then it's
    best to ignore preferences listed here.

`ArticleRequestsMandatoryFieldsItemsOnly <#ArticleRequestsMandatoryFieldsItemsOnly>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: blank

Asks: Comma delimited list of required fields for bibs where artciel requests
rule = "item_only"

`INTRAdidyoumean <#INTRAdidyoumean>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: blank

Asks: Did you mean? configuration for the Intranet. Do not change, as this is
controlled by /cgi-bin/koha/admin/didyoumean.pl.

`OPACdidyoumean <#OPACdidyoumean>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: blank

Asks: Did you mean? configuration for the OPAC. Do not change, as this is
controlled by /cgi-bin/koha/admin/didyoumean.pl.

`printcirculationships <#printcirculationships>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: ON

Asks: If ON, enable printing circulation receipts

Values:

-  ON

-  OFF

`UsageStatsID <#UsageStatsID>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: blank

Asks: This preference is part of Koha but it should not be deleted or
updated manually.

`UsageStatsLastUpdateTime <#UsageStatsLastUpdateTime>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: blank

Asks: This preference is part of Koha but it should not be deleted or
updated manually.

`UsageStatsPublicID <#UsageStatsPublicID>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: blank

Asks: Public ID for Hea website

`Version <#Version>`__
^^^^^^^^^^^^^^^^^^^^^^

Default: automatically generated

Asks: The Koha database version. WARNING: Do not change this value
manually. It is maintained by the webinstaller

`Logs <#logs>`__
~~~~~~~~~~~~~~~~

Logs keep track of transaction on the system. You can decide which
actions you want to log and which you don't using these preferences.
Logs can then be viewed in the `Log Viewer <#logviewer>`__ under Tools.

*Get there:* More > Administration > Global System Preferences > Logs

`Debugging <#debuggingprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`DumpTemplateVarsIntranet <#DumpTemplateVarsIntranet>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ dump all Template Toolkit variable to a comment in the html
source for the staff intranet.

Value:

-  Don't

-  Do

`DumpTemplateVarsOpac <#DumpTemplateVarsOpac>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ dump all Template Toolkit variable to a comment in the html
source for the OPAC.

Value:

-  Don't

-  Do

`Logging <#loggingprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AuthoritiesLog <#AuthoritiesLog>`__
''''''''''''''''''''''''''''''''''''

Default: Don't log

Asks: \_\_\_ changes to authority records.

Values:

-  Don't log

-  Log

`BorrowersLog <#BorrowersLog>`__
''''''''''''''''''''''''''''''''

Default: Log

Asks: \_\_\_ changes to patron records.

Values:

-  Don't log

-  Log

`CataloguingLog <#CataloguingLog>`__
''''''''''''''''''''''''''''''''''''

Default: Don't log

Asks: \_\_\_ any changes to bibliographic or item records.

Values:

-  Don't log

-  Log

    **Important**

    Since this occurs whenever a book is cataloged, edited, or checked
    in or out it can be very resource intensive - slowing down your
    system.

`CronjobLog <#CronjobLog>`__
''''''''''''''''''''''''''''

Default: Don't log

Asks: \_\_\_ information from cron jobs.

Values:

-  Don't log

-  Log

`FinesLog <#FinesLog>`__
''''''''''''''''''''''''

Default: Log

Asks: \_\_\_ when overdue fines are charged or automatically forgiven.

Values:

-  Don't log

-  Log

`HoldsLog <#HoldsLog>`__
''''''''''''''''''''''''

Default: Don't log

Asks: \_\_\_ any actions on holds (create, cancel, suspend, resume, etc.).

Values:

-  Don't log

-  Log

`IssueLog <#IssueLog>`__
''''''''''''''''''''''''

Default: Log

Asks: \_\_\_ when items are checked out.

Values:

-  Don't log

-  Log

`LetterLog <#LetterLog>`__
''''''''''''''''''''''''''

Default: Log

Asks: \_\_\_ when an automatic claim notice is sent.

Values:

-  Don't log

-  Log

    **Note**

    This log tracks all notices that go to patrons including the overdue
    notices.

`RenewalLog <#RenewalLog>`__
''''''''''''''''''''''''''''

Default:  Don't log

Asks: \_\_\_ when items are renewed.

Values:

- Don't log

- Log

`ReportsLog <#ReportsLog>`__
''''''''''''''''''''''''''''

Default: Don't log

Asks: \_\_\_ when reports are added, deleted or changed.

Values:

-  Don't log

-  Log

`ReturnLog <#ReturnLog>`__
''''''''''''''''''''''''''

Default: Log

Asks: \_\_\_ when items are returned.

Values:

-  Don't log

-  Log

`SubscriptionLog <#SubscriptionLog>`__
''''''''''''''''''''''''''''''''''''''

Default: Log

Asks: \_\_\_ when serials are added, deleted or changed.

Values:

-  Don't log

-  Log

`OPAC <#opacprefs>`__
~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences > OPAC

`Advanced Search Options <#advancedsearchopt>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`OpacAdvSearchMoreOptions <#OpacAdvSearchMoreOptions>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Select All

Asks: Show search options for the expanded view \_\_\_

Values:

-  [Select all]

-  Item types

-  Language

-  Location and availability

-  Publication date

-  Sorting

-  Subtypes

Description:

-  The settings in this preference will determine which search fields
   will show when the patron is using the 'More options' mode on the
   advanced search page.

`OpacAdvSearchOptions <#OpacAdvSearchOptions>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Item types, Language, Location and availability, Publication
date, Sorting

Asks: Show search options \_\_\_

Values:

-  [Select all]

-  Item types

-  Language

-  Location and availability

-  Publication date

-  Sorting

-  Subtypes

Description:

-  The settings in this preference will determine which search fields
   will show when the patron is using the 'Fewer options' mode on the
   advanced search page.

`Appearance <#opacappearanceprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These preferences control how things appear in the OPAC.

`AuthorisedValueImages <#AuthorisedValueImages>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ images for authorized values (such as lost statuses and
locations) in search results and item detail pages on the OPAC.

Values:

-  Don't show

-  Show

*Get there:* More > Administration > `Authorized
Values <#authorizedvalues>`__

`BiblioDefaultView <#BiblioDefaultView>`__
''''''''''''''''''''''''''''''''''''''''''

Default: in simple form

Asks: By default, show bib records \_\_\_

Values:

-  as specified in the ISBD template.

   -  See `ISBD <#isbdpref>`__ preference for more information

-  in simple form.

-  in their MARC format.

Description:

-  This preference determines the level of bibliographic detail that the
   patron will see on the OPAC detail page. The simple form displays the
   graphical interface; MARC format displays the MARC21 cataloging view;
   ISBD displays the ISBD (International Standard Bibliographic
   Description, AACR2) view.

`COinSinOPACResults <#COinSinOPACResults>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Include

Asks: \_\_\_ COinS / OpenURL / Z39.88 in OPAC search results.

Values:

-  Don't include

   -  If you choose not to include COinS on the search results, it will
      still be loaded on the individual bibliographic records.

-  Include

   -  Enabling this feature will slow OPAC search response times.

Description:

-  COinS stands for ContextObjects in Spans. COinS is a method to embed
   bibliographic metadata in the HTML code of web pages. This allows
   bibliographic software to publish machine-readable bibliographic
   items and client reference management software (such as Zotero) to
   retrieve bibliographic metadata. The metadata can also be sent to an
   OpenURL resolver. This allows, for instance, searching for a copy of
   a book in one's own library.

`DisplayOPACiconsXSLT <#DisplayOPACiconsXSLT>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: On pages displayed with XSLT stylesheets on the OPAC, \_\_\_ icons
for itemtype and authorized values.

    **Important**

    `OPACXSLTResultsDisplay <#OPACXSLTResultsDisplay>`__ and/or
    `OPACXSLTDetailsDisplay <#OPACXSLTDetailsDisplay>`__ must be set to
    use an XSLT stylesheet for this to show (default or custom)

Values:

-  Don't show

-  Show

   DisplayOPACiconsXSLT
   |image62|

    **Note**

    See the `XSLT Icon Guide <#XSLTiTypes>`__ for more information on
    these icons.

`GoogleIndicTransliteration <#GoogleIndicTransliteration>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ GoogleIndicTransliteration on the OPAC.

Values:

-  Don't show

-  Show

`hidelostitems <#hidelostitems>`__
''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ lost items on search and detail pages.

Description:

-  Items that are marked lost by the library can either be shown or not
   shown on the OPAC. By setting the value to "Don't show," the lost
   item is not shown on the OPAC. By setting the value "Show," the lost
   item is shown on the OPAC for patrons to view with a status of
   'lost.'

Values:

-  Don't show

-  Show

   Lost item showing in the OPAC
   |image63|

`HighlightOwnItemsOnOPAC & HighlightOwnItemsOnOPACWhich <#HighlightOwnItemsOnOPAC>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

HighlightOwnItemsOnOPAC Default: Don't emphasize

HighlightOwnItemsOnOPACWhich Default: patron's home library

Asks: \_\_\_ results from the \_\_\_ by moving the results to the front
and increasing the size or highlighting the rows for those results.

HighlightOwnItemsOnOPAC Values:

-  Don't emphasize

-  Emphasize

HighlightOwnItemsOnOPACWhich Values:

-  OPAC's branch based via the URL

   -  The library is chosen based on the Apache environment variable
      BRANCHCODE. For example, this could be added to the OPAC section
      of koha-httpd.conf: SetEnv BRANCHCODE "CPL"

-  patron's home library

   -  The items emphasized will be those of the same library as the
      patron's library. If no one is logged into the OPAC, no items will
      be highlighted.

    **Important**

    This preference will only effect sites that are not using an XSLT
    stylesheet. XSLT stylesheets are defined in the
    `OPACXSLTResultsDisplay <#OPACXSLTResultsDisplay>`__ and
    `OPACXSLTDetailsDisplay <#OPACXSLTDetailsDisplay>`__ preferences.

`LibraryName <#LibraryName>`__
''''''''''''''''''''''''''''''

Asks: Show \_\_\_ as the name of the library on the OPAC.

    **Note**

    This value will appear in the title bar of the browser

    **Note**

    Edit '`opacheader <#opacheader>`__' if you'd like to add a library
    name above your search box on the OPAC

Browser title and address bar
|image64|

`NoLoginInstructions <#NoLoginInstructions>`__
''''''''''''''''''''''''''''''''''''''''''''''

Asks: Show the following HTML on the OPAC login form when a patron is
not logged in:

Description:

-  This preference allows you to override the default text seen on the
   log in page in the Koha OPAC. The default HTML is:

   ::

       <h5>Don't have a password yet?</h5>
       <p> If you don't have a password yet, stop by the circulation desk the next time you're in the library. We'll happily set one up for you.</p>
       <h5>Don't have a library card?</h5>
       <p> If you don't have a library card, stop by your local library to sign up.</p>

   Any HTML in this box will replace the above text below the log in
   box.No login instructions

`OpacAdditionalStylesheet <#OpacAdditionalStylesheet>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Include the additional CSS stylesheet \_\_\_ to override specified
settings from the default stylesheet.

Description:

-  The preference can look for stylesheets in the template directory for
   your OPAC language, for instance: /koha-tmpl/opac-tmpl/prog/en/css.
   If you upload a custom file, opac-mystyles.css to this directory, you
   can specify it by entering opac-mystyles.css in your
   opaccolorstylesheet system preference. This adds your custom
   stylesheet as a linked stylesheet alongside the OPAC's default CSS
   files. This method is preferable because linked stylesheets are
   cached by the user's browser, meaning upon repeat visits to your site
   the user's browser will not have to re-download the stylesheet,
   instead using the copy in the browser's cache.

-  If you would rather, you can upload your CSS to another server and
   enter the full URL pointing to it's location remember to begin the
   URL with http://

    **Note**

    Leave this field blank to disable it

    **Note**

    This file will add a linked CSS, not replace the existing default
    CSS.

`OpacAddMastheadLibraryPulldown <#OpacAddMastheadLibraryPulldown>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't add

Asks: \_\_\_ a library select pulldown menu on the OPAC masthead.

Values:

-  Add

   Library select box on Koha OPAC
   |image65|

-  Don't Add

   No library select box on Koha OPAC
   |image66|

`OPACBaseURL <#OPACBaseURL>`__
''''''''''''''''''''''''''''''

Asks: The OPAC is located at \_\_\_

Description:

-  This preference is looking for the URL of your public catalog (OPAC)
   with the http:// in front of it (enter http://www.mycatalog.com
   instead of www.mycatalog.com). Once it is filled in Koha will use it
   to generate permanent links in your RSS feeds, for your social
   network share buttons and in your staff client when generating links
   to bib records in the OPAC.

    **Important**

    Do not include a trailing slash in the URL this will break links
    created using this URL. (example: http://www.google.com not
    http://www.google.com/)

    **Important**

    This must be filled in with the URL of your public catalog for RSS,
    unAPI, and search plugins to work.

    **Important**

    This must be filled in with the URL of your public catalog to show
    'OPAC View' links from bib records in the staff client:

With OPACBaseURL set, links to the OPAC will appear on each individual
bib record in the staff client
|image67|

`opaccredits <#opaccredits>`__
''''''''''''''''''''''''''''''

Asks: Include the following HTML in the footer of all pages in the OPAC:

    **Note**

    Click the 'Click to edit; link to enter HTML to appear at the bottom
    of every page in the OPAC

HTML version of a footer for your OPAC
|image68|

A sample of what can appear in your OPAC credits/footer
|image69|

Description:

-  This setting is for credits that will appear at the bottom of your
   OPAC pages. Credits traditionally encompass copyright information,
   last date updated, hyperlinks or other information represented in an
   HTML format. This is static information and any updates must be
   entered manually.

Learn more in the `OPAC Editable Regions <#editableopac>`__ section.

`OpacCustomSearch <#OpacCustomSearch>`__
''''''''''''''''''''''''''''''''''''''''

Asks: Replace the search box at the top of OPAC pages with the following
HTML

Description:

-  This preference allows you to replace the default search box at the
   top of the OPAC : Default search box

   with any HTML you would like :Edited search box area

`OPACDisplay856uAsImage <#OPACDisplay856uAsImage>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Neither details or results page

Asks: Display the URI in the 856u field as an image on: \_\_\_

Values:

-  Both results and details pages

   -  **Important**

          Not implemented yet

-  Detail page only

   -  **Important**

          `OPACXSLTDetailsDisplay <#OPACXSLTDetailsDisplay>`__ needs to
          have a value in it for this preference to work.

   Showing the 856u as an image
   |image70|

-  Neither details or results page

-  Results page only

   -  **Important**

          Not yet implemented

Description:

-  In addition to this option being set, the corresponding XSLT option
   must be turned on. Also, the corresponding 856q field must have a
   valid MIME image extension (e.g., "jpg") or MIME image type (i.e.
   starting with "image/"), or the generic indicator "img" entered in
   the field. When all of the requirements are met, an image file will
   be displayed instead of the standard link text. Clicking on the image
   will open it in the same way as clicking on the link text. When you
   click on the image it should open to full size, in the current window
   or in a new window depending on the value in the system pref
   `OPACURLOpenInNewWindow <#OPACURLOpenInNewWindow>`__.

   Sample 856 in MARC Record
   |image71|

`OpacExportOptions <#OpacExportOptions>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Default OpacExportOptions options

Asks: List export options that should be available from OPAC detail page
: \_\_\_

Description:

-  In the OPAC on the right of each bib record there is a menu that
   allows for saving the record in various formats. This patch will
   allow you to define which options are in the pull down menu.
   Available options are: BIBTEX (bibtex), Dublin Core (dc), MARCXML
   (marcxml), MARC-8 encoded MARC (marc8), Unicode/UTF-8 encoded MARC
   (utf8), Unicode/UTF-8 encoded MARC without local use -9xx, x9x, xx9-
   fields and subfields (marcstd), MODS (mods), and RIS (ris).

`OPACFallback <#OPACFallback>`__
''''''''''''''''''''''''''''''''

Default: bootstrap

Asks: Use the \_\_\_ theme as the fallback theme on the OPAC.

Description:

-  This preference has no use right now, as Koha has only one theme, but
   if your library has a custom theme it will show here as an option.
   The purpose of this preference is to provide a way to choose to what
   theme to fallback on when you have a partial theme in place.

`OpacFavicon <#OpacFavicon>`__
''''''''''''''''''''''''''''''

Asks: Use the image at \_\_\_ for the OPAC's favicon.

    **Important**

    This should be a complete URL, starting with http://

    **Note**

    Turn your logo into a favicon with the `Favicon
    Generator <http://antifavicon.com/>`__.

Description:

-  The favicon is the little icon that appears next to the URL in the
   address bar in most browsers. The default value for this field (if
   left blank) is the small 'K' in the Koha logo.

   Default Koha Favicon
   |image72|

`opacheader <#opacheader>`__
''''''''''''''''''''''''''''

Asks: Include the following HTML in the header of all pages in the OPAC

Sample HTML to be displayed at the top of my OPAC
|image73|

    **Note**

    This value will appear above the main content of your page

OPAC display of the value from 'opacheader'
|image74|

    **Note**

    Edit '`LibraryName <#LibraryName>`__' if you'd like to edit the
    contents of the <title> tag

Learn more in the `OPAC Editable Regions <#editableopac>`__ section.

`OpacHighlightedWords & NotHighlightedWords <#OpacHighlightedWords>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

OpacHighlightedWords Default: Don't highlight

NotHighlightedWords Default: and\|or\|not

Asks: \_\_\_ words the patron searched for in their search results and
detail pages; To prevent certain words from ever being highlighted,
enter a list of stopwords here \_\_\_ (separate columns with \|)

OpacHighlightedWords Values:

-  Don't highlight

-  Highlight

`OPACHoldingsDefaultSortField <#OPACHoldingsDefaultSortField>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: First column of the table

Asks: \_\_\_ is the default sort field for the holdings table

Values:

-  First column of the table

-  Holding library

-  Home library

`OpacKohaUrl <#OpacKohaUrl>`__
''''''''''''''''''''''''''''''

Default: Don't show

Values:

-  Don't show

-  Show

Description:

-  When this preference is set to 'Show' text will appear in the bottom
   right of the OPAC footer stating 'Powered by Koha' and linking to the
   official Koha website.

   Powered by Koha
   |image75|

`OpacLangSelectorMode <#OpacLangSelectorMode>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: only footer

Asks: Display language selector on \_\_\_.

Values:

-  both top and footer

-  only footer

-  top

Description:

-  If you have the `opaclanguagesdisplay <#opaclanguagesdisplay>`__
   preference set to display language options in the public catlaog,
   then this preference will allow you to control where the language
   selector shows. You can choose to show it only on the top or bottom
   or in both places.

`opaclayoutstylesheet <#opaclayoutstylesheet>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: opac.css

Asks: Use the CSS stylesheet /css/ \_\_\_ on all pages in the OPAC,
instead of the default

Description:

-  This setting's function is to point to the \*.css file used to define
   the OPAC layout. A \*.css file is a cascading stylesheet which is
   used in conjunction with HTML to set how the HTML page is formatted
   and will look on the OPAC. There are two stylesheets that come with
   the system; opac.css and opac2.css. A custom stylesheet may also be
   used. The stylesheets listed in the opaclayoutstylesheet preference
   are held on the Koha server.

    **Note**

    Leave this field blank to disable it and let Koha use the default
    file instead

    **Important**

    Using a custom value in this preference causes Koha to completely
    ignore the default layout stylesheet.

`OpacLocationBranchToDisplay <#OpacLocationBranchToDisplay>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: holding library

Asks: Display the \_\_\_ for items on the OPAC record details page.

Values:

-  holding library

-  home and holding library

-  home library

Description:

-  Defines whether to display the holding library, the home library, or
   both for the opac details page.

`OpacLocationBranchToDisplayShelving <#OpacLocationBranchToDisplayShelving>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: holding library

Asks: Display the shelving location under the \_\_\_ for items on the
OPAC record details page.

Values:

-  holding library

-  home and holding library

-  home library

Description:

-  Defines where the shelving location should be displayed, under the
   home library, the holding library, or both.

`OpacMaintenance <#OpacMaintenance>`__
''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ a warning that the OPAC is under maintenance, instead of
the OPAC itself.

    **Note**

    this shows the same warning as when the database needs to be
    upgraded, but unconditionally.

Description:

-  This preference allows the system administrator to turn off the OPAC
   during maintenance and display a message to users. When this
   preference is switched to "Show" the OPAC is not usable. The text of
   this message is not editable at this time.

Values:

-  Don't show

-  Show

   -  When this preference is set to show the maintenance message the
      ability to search the OPAC is disabled and a message appears. The
      default message can be altered by using the
      `OpacMaintenanceNotice <#OpacMaintenanceNotice>`__ preference.

      OPAC Maintenance Message
      |image76|

`OpacMaintenanceNotice <#OpacMaintenanceNotice>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Show the following HTML when OpacMaintenance is enabled

Descritpion:

-  This preference will allow you to set the text the OPAC displays when
   the `OpacMaintenance <#OpacMaintenance>`__ preference is set to
   'Show.'

`OpacMainUserBlock <#OpacMainUserBlock>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Welcome to Koha... <hr>

Asks: Show the following HTML in its own column on the main page of the
OPAC

Description:

-  HTML entered in this field will appear in the center of the main page
   of your OPAC

Sample OpacMainUserBlock appears below the search bar
|image77|

Learn more in the `OPAC Editable Regions <#editableopac>`__ section.

`OpacMaxItemsToDisplay <#OpacMaxItemsToDisplay>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 50

Asks: Display up to \_\_\_ items on the biblio detail page

Description:

-  This preference will help with slow load times on the bibliographic
   detail pages by limiting the number of items to display by default.
   If the biblio has more items than this, a link is displayed instead
   that allows the user to choose to display all items.

`OPACMySummaryHTML <#OPACMySummaryHTML>`__
''''''''''''''''''''''''''''''''''''''''''

Asks: Include a "Links" column on the "my summary" tab when a user is
logged in to the OPAC, with the following HTML (leave blank to disable).

Description:

-  In this preference you can enter HTML that will appear on the
   'Checked Out' tab on the 'My Summary' section when logged in to the
   OPAC. The placeholders {BIBLIONUMBER}, {TITLE}, {ISBN} and {AUTHOR}
   will be replaced with information from the displayed record. This can
   be used to enter in 'share' links for social networks or generate
   searches against other library catalogs.

   Example of 'Links' column with a value in the OPACMySummaryHTML
   preference
   |image78|

Sample Data:

::

    <p><a href="http://www.facebook.com/sharer.php?u=http://YOUROPAC.ORG/cgi-bin/koha/opac-detail.pl?biblionumber={BIBLIONUMBER}">Share on Facebook</a>
    <br />TITLE: {TITLE}
    <br />AUTHOR: {AUTHOR}
    <br />ISBN: {ISBN}
    <br />BIBLIONUMBER: {BIBLIONUMBER}</p>

`OPACMySummaryNote <#OPACMySummaryNote>`__
''''''''''''''''''''''''''''''''''''''''''

Asks: Note to display on the patron summary page.

Description:

-  This preference will display text above the patron's summary and
   below the welcome message when the patron logs in to the OPAC and
   view their 'my summary' tab.OPACMySummaryNote in the OPAC

`OpacNav <#OpacNav>`__
''''''''''''''''''''''

Default: Important links here.

Asks: Show the following HTML on the left hand column of the main page
and patron account on the OPAC (generally navigation links)

Sample navigation links
|image79|

Learn more in the `OPAC Editable Regions <#editableopac>`__ section.

`OpacNavBottom <#OpacNavBottom>`__
''''''''''''''''''''''''''''''''''

Asks: Show the following HTML on the left hand column of the main page
and patron account on the OPAC, after `OpacNav <#OpacNav>`__, and before
patron account links if available:

Description: When a patron is logged in to their account they see a
series of tabs to access their account information.
`OpacNav <#OpacNav>`__ appears above this list of tabs and OpacNavBottom
will appear below them. When not on the patron account pages the HTML in
OpacNavBottom will just appear right below `OpacNav <#OpacNav>`__.

OpacNav and OpacNavBottom on Patron Account
|image80|

`OpacNavRight <#OpacNavRight>`__
''''''''''''''''''''''''''''''''

Asks: Show the following HTML in the right hand column of the main page
under the main login form.

Description: HTML entered in this preference will appear on the right
hand side of the OPAC under the log in form. If the log in form is not
visible this content will move up on the right column.

OpacNavRight
|image81|

`OPACNoResultsFound <#OPACNoResultsFound>`__
''''''''''''''''''''''''''''''''''''''''''''

No Default

Asks: Display this HTML when no results are found for a search in the
OPAC

This HTML will display below the existing notice that no results were
found for your search.

HTML in OPACNoResultsFound will appear below lines that look like this
|image82|

    **Note**

    You can insert placeholders {QUERY\_KW} that will be replaced with
    the keywords of the query.

`OpacPublic <#OpacPublic>`__
''''''''''''''''''''''''''''

Default: Enable

Asks: \_\_\_ Koha OPAC as public. Private OPAC requires authentication
before accessing the OPAC.

Values:

-  Don't enable

-  Enable

Description:

-  This preference determines if your OPAC is accessible and searchable
   by anyone or only by members of the library. If set to 'Don't enable'
   only members who are logged into the OPAC can search. Most libraries
   will leave this setting at its default of 'Enable' to allow their
   OPAC to be searched by anyone and only require login for access to
   personalized content.

`OPACResultsLibrary <#OPACResultsLibrary>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: home library

Asks: For search results in the OPAC, show the item's \_\_\_. Please
note that this feature is currently available for MARC21 and UNIMARC.

Values:

-  current location

-  home library

`OPACResultsSidebar <#OPACResultsSidebar>`__
''''''''''''''''''''''''''''''''''''''''''''

Asks: Include the following HTML under the facets in OPAC search results

Description:

-  The HTML entered in this preference will appear on the search results
   pages below the list of facets on the left side of the screen.

`OPACSearchForTitleIn <#OPACSearchForTitleIn>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: <li><a href="http://worldcat.org/search?q={TITLE}"
target="\_blank">Other Libraries (WorldCat)</a></li> <li><a
href="http://www.scholar.google.com/scholar?q={TITLE}"
target="\_blank">Other Databases (Google Scholar)</a></li> <li><a
href="http://www.bookfinder.com/search/?author={AUTHOR}&title={TITLE}&st=xl&ac=qr"
target="\_blank">Online Stores (Bookfinder.com)</a></li>

Asks: Include a "More Searches" box on the detail pages of items on the
OPAC, with the following HTML (leave blank to disable)

    **Note**

    The placeholders {BIBLIONUMBER}, {CONTROLNUMBER}, {TITLE}, {ISBN},
    {ISSN} and {AUTHOR} will be replaced with information from the
    displayed record.

`OpacSeparateHoldings & OpacSeparateHoldingsBranch <#OpacSeparateHoldings>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

OpacSeparateHoldings default: Don't separate

OpacSeparateHoldingsBranch default: home library

Asks: \_\_\_ items display into two tabs, where the first tab contains
items whose \_\_\_ is the logged in user's library. The second tab will
contain all other items.

OpacSeparateHoldings values:

-  Don't separate

-  Separate

OpacSeparateHoldingsBranch values:

-  holding library

-  home library

Description:

-  This preference lets you decide if you would like to have the holding
   information on the bibliographic detail page in the OPAC split in to
   multiple tabs. The default is to show all holdings on one tab.

   Separate holdings tabs
   |image83|

`OPACShowBarcode <#OPACShowBarcode>`__
''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ the item's barcode on the holdings tab.

Values:

-  Don't show

   Barcode not shown in the OPAC
   |image84|

-  Show

   Barcode shown in the OPAC
   |image85|

Description:

-  This preference allows you to control whether patrons can see items'
   barcodes in the OPAC.

`OPACShowCheckoutName <#OPACShowCheckoutName>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ the name of the patron that has an item checked out on item
detail pages on the OPAC.

Values:

-  Don't show

-  Show

Description:

-  This preference allows all patrons to see who has the item checked
   out if it is checked out. In small corporate libraries (where the
   OPAC is behind a firewall and not publicly available) this can be
   helpful so coworkers can just contact the patron with the book
   themselves. In larger public and academic libraries setting this to
   'Show' would pose serious privacy issues.

`OPACShowHoldQueueDetails <#OPACShowHoldQueueDetails>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show any hold details

Asks: \_\_\_ to patrons in the OPAC.

Values:

-  Don't show any hold details

-  Show holds

   The holdings table on the bibliographic record will show the number
   of holds
   |image86|

-  Show holds and priority level

-  Show priority level

   Patron record in the OPAC shows where in line the patron waits for
   their hold.
   |image87|

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'allow'

`OpacShowRecentComments <#OpacShowRecentComments>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ a link to recent comments in the OPAC masthead.

Values:

-  Don't show

-  Show

Description:

-  If you have chosen to allow comments in your OPAC by setting
   `reviewson <#reviewson>`__ to 'Allow' you can include a link to the
   recent comments under the search box at the top of your OPAC with
   this preference.

   Recent Comments link on OPAC
   |image88|

`OPACShowUnusedAuthorities <#OPACShowUnusedAuthorities>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ unused authorities in the OPAC authority browser.

Values:

-  Do not show

-  Show

   -  **Important**

          Requires that the `OpacAuthorities <#OpacAuthorities>`__
          preference is set to 'Allow'

Description:

-  When patrons search your authority file via the OPAC they will see
   all authorities in your system even if you don't have them linked to
   any bibliographic records. This preference lets you determine what
   the default behavior is when searching authorities via the OPAC. If
   you choose 'Do not show' it will only show patrons authority records
   that are linked to bib records in the search results. Otherwise the
   system will show all authority records even if they aren't linked to
   records.

`OpacStarRatings <#OpacStarRatings>`__
''''''''''''''''''''''''''''''''''''''

Default: no

Asks: Show star-ratings on \_\_\_ pages.

Values:

-  no

-  only details

   Star Ratings on the Details Page
   |image89|

-  results and details

   OPAC Star Ratings on the Search Results
   |image90|

Description:

-  Star ratings are a way for your patrons to leave ratings without
   having to leave a full review. Patrons who are not logged in will
   only be able to see the stars, once logged in patrons can click on
   the stars on the details page to leave their own rating. Clicking on
   the stars on the search results will not submit a rating.

`OpacSuggestionManagedBy <#OpacSuggestionManagedBy>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ the name of the staff member who managed a suggestion in
OPAC.

Values:

-  Don't show

-  Show

Description:

-  If you're `allowing patrons to make purchase
   suggestions <#suggestionspref>`__ then they will see the 'my
   suggestions' tab when logged in. This tab shows the patron the
   librarian who approved or rejected the purchase suggestion. This
   preference controls if the patron sees the librarian's name or not.

`opacthemes <#opacthemes>`__
''''''''''''''''''''''''''''

Default: bootstrap

Asks: Use the \_\_\_ theme on the OPAC.

Values:

-  bootstrap

   Bootstrap Theme

   This theme is completely responsive

`OPACURLOpenInNewWindow <#OPACURLOpenInNewWindow>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: don't

Asks: When patrons click on a link to another website from your OPAC
(like Amazon or OCLC), \_\_\_ open the website in a new window.

Values:

-  do

-  don't

Description:

-  This preference determines if URLs in the OPAC will open in a new
   window or not. When clicking on a link in the OPAC, a patron does not
   need to worry about navigating away from their search results.

`OPACUserCSS <#OPACUserCSS>`__
''''''''''''''''''''''''''''''

Asks: Include the following CSS on all pages in the OPAC

Description:

-  OPACUserCSS allows the administrator to enter styles that will
   overwrite the OPAC's default CSS as defined in 'opaclayoutstylesheet'
   or 'opacstylesheet'. Styles may be entered for any of the selectors
   found in the default style sheet. The default stylesheet will likely
   be found at
   http://your\_koha\_address/opac-tmpl/bootstrap/css/opac.css. Unlike
   `OpacAdditionalStylesheet <#OpacAdditionalStylesheet>`__ and
   `opaclayoutstylesheet <#opaclayoutstylesheet>`__ this preference will
   embed the CSS directly on your OPAC pages.

`OPACUserJS <#opacuserjs>`__
''''''''''''''''''''''''''''

Asks: Include the following JavaScript on all pages in the OPAC

OPAC login box before OPACUserJS edit
|image91|

JavaScript in OPACUserJS to change the OPAC login box
|image92|

New OPAC login box after editing OPACUserJS
|image93|

Description:

-  This preference allows the administrator to enter JavaScript or
   JQuery that will be embedded across all pages of the OPAC.
   Administrators may use this preference to customize some of the
   interactive sections of Koha, customizing the text for the login
   prompts, for example. Sample JQuery scripts used by Koha libraries
   can be found on the wiki:
   http://wiki.koha-community.org/wiki/JQuery_Library.

`OPACXSLTDetailsDisplay <#OPACXSLTDetailsDisplay>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: default

Asks: Display OPAC details using XSLT stylesheet at \_\_\_

Values:

-  leave empty to not use the XSLT stylesheet

   -  In previous versions of Koha this was the setting that read
      'normally'

-  enter "default" for the default one

-  put a path to define a XSLT file

   -  ex: /path/to/koha/and/your/stylesheet.xsl

   -  If in a multi-language system you can enter {langcode} in the path
      to tell Koha to look in the right language folder

      -  ex:
         /home/koha/src/koha-tmpl/opac-tmpl/bootstrap/{langcode}/xslt/MARC21slim2OPACDetail.xsl

      -  ex. http://mykohaopac.org/{langcode}/stylesheet.xsl

-  put an URL for an external specific stylesheet

   -  ex: http://mykohaopac.org/stylesheet.xsl

Description:

-  XSLT stylesheets allow for the customization of the details shows on
   the screen when viewing a bib record. This preference will allow you
   either use the default look that comes with Koha or design your own
   stylesheet.
   
`OPACXSLTListsDisplay <#OPACXSLTListsDisplay>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: default

Asks: Display lists in the OPAC using XSLT stylesheet at \_\_\_

Values:

-  leave empty to not use the XSLT stylesheet

   -  In previous versions of Koha this was the setting that read
      'normally'

-  enter "default" for the default one

-  put a path to define a XSLT file

   -  ex: /path/to/koha/and/your/stylesheet.xsl

   -  If in a multi-language system you can enter {langcode} in the path
      to tell Koha to look in the right language folder

      -  ex:
         /home/koha/src/koha-tmpl/opac-tmpl/bootstrap/{langcode}/xslt/MARC21slim2OPACResults.xsl

      -  ex. http://mykohaopac.org/{langcode}/stylesheet.xsl

-  put an URL for an external specific stylesheet

   -  ex: http://mykohaopac.org/stylesheet.xsl

Description:

-  XSLT stylesheets allow for the customization of the details shows on
   the screen when viewing lists. This preference will
   allow you either use the default look that comes with Koha or design
   your own stylesheet.

`OPACXSLTResultsDisplay <#OPACXSLTResultsDisplay>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: default

Asks: Display OPAC results using XSLT stylesheet at \_\_\_

Values:

-  leave empty to not use the XSLT stylesheet

   -  In previous versions of Koha this was the setting that read
      'normally'

-  enter "default" for the default one

-  put a path to define a XSLT file

   -  ex: /path/to/koha/and/your/stylesheet.xsl

   -  If in a multi-language system you can enter {langcode} in the path
      to tell Koha to look in the right language folder

      -  ex:
         /home/koha/src/koha-tmpl/opac-tmpl/bootstrap/{langcode}/xslt/MARC21slim2OPACResults.xsl

      -  ex. http://mykohaopac.org/{langcode}/stylesheet.xsl

-  put an URL for an external specific stylesheet

   -  ex: http://mykohaopac.org/stylesheet.xsl

Description:

-  XSLT stylesheets allow for the customization of the details shows on
   the screen when viewing the search results. This preference will
   allow you either use the default look that comes with Koha or design
   your own stylesheet.

`Features <#opacfeaturesprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`numSearchRSSResults <#numSearchRSSResults>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: 50

Asks: Display \_\_\_ search results in the RSS feed.

Description:

-  By default the RSS feed that is automatically generated for every
   search results page will list 50 items. This can sometimes be too
   much for some RSS feed readers and for some people this isn't enough.
   This preference allows you to adjust this number to show the best
   number of results for your patrons.

`OPACAcquisitionDetails <#OPACAcquisitionDetails>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't display

Asks: \_\_\_ the acquisition details on OPAC detail pages.

Values:

-  DisplayAcquisitions details in the OPAC

-  Don't display

Description:

-  This preference shows the patrons how many items are on order in the
   Holdings tab if you have the `AcqCreateItem <#AcqCreateItem>`__ set
   to 'cataloging the record'

`OpacAuthorities <#OpacAuthorities>`__
''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to search your authority records.

Description:

-  This preference displays the link on the OPAC for the authority
   search. By setting the preference to "Allow" patrons can use this
   search link of the OPAC.

Values:

-  Allow

   -  A link labeled 'Authority search' will appear at the top of your
      OPAC under the search box

      'Browse by Subject' link under search box on OPAC
      |image94|

-  Don't allow

`opacbookbag <#opacbookbag>`__
''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to store items in a temporary "Cart" on the OPAC.

Values:

-  Allow

-  Don't allow

Description:

-  This preference allows the user to temporarily save a list of items
   found on the catalog. By using the Book Bag, or Cart, the user can
   print out or email a list of items found. The user does not need to
   be logged in. This list is temporary and will be emptied, or cleared,
   at the end of the session.

`OpacBrowser <#OpacBrowser>`__
''''''''''''''''''''''''''''''

    **Important**

    This preference only applies to installations using UNIMARC at this time.

Default: Don't allow

Asks: \_\_\_ patrons to browse subject authorities on OPAC

Values:

-  Allow

-  Don't allow

    **Important**

    run the `Authorities Browser Cron Job <#authbrowsercron>`__ to
    create the browser list

`OpacBrowseResults <#OpacBrowseResults>`__
''''''''''''''''''''''''''''''''''''''''''

Default: enable

Asks: \_\_\_ browsing and paging search results from the OPAC detail
page.

Values:

-  disable

-  enable

   Browsing and Paging Search Results
   |image95|

Description:

-  This preference will control the option to return to your results
   and/or browse them from the detail page in the OPAC.

`OpacCloud <#OpacCloud>`__
''''''''''''''''''''''''''

    **Important**

    This preference only applies to French systems at this time.

Default: Don't show

Asks: \_\_\_ a subject cloud on OPAC

Values:

-  Don't show

-  Show

    **Important**

    run the `Authorities Browser Cron Job <#authbrowsercron>`__ to
    create the browser list

`OPACFinesTab <#OPACFinesTab>`__
''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to access the Fines tab on the My Account page on
the OPAC.

Values:

-  Allow

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'allow'

-  Don't allow

`OpacHoldNotes <#OpacHoldNotes>`__
''''''''''''''''''''''''''''''''''

Default: Do not allow

Asks: \_\_\_ users to add a note when placing a hold.

Values:

-  Allow

   Holds notes in the OPAC
   |image96|

-  Do not allow

`OPACISBD <#OPACISBD>`__
''''''''''''''''''''''''

Default: `MARC21 Default Appendix <#opacisbdmarcdefault>`__

Asks: Use the following as the OPAC ISBD template:

Description:

-  This determines how the ISBD information will display in the OPAC.
   Elements in the list can be reordered to produce a different ISBD
   view. ISBD, the International Standard Bibliographic Description, was
   first introduced by IFLA (International Federation of Library
   Associations) in 1969 in order to provide guidelines for descriptive
   cataloging. The purpose of ISBD is to aid the international exchange
   of bibliographic records for a variety of materials.

`OpacItemLocation <#OpacItemLocation>`__
''''''''''''''''''''''''''''''''''''''''

Default: call number only

Asks: Show \_\_\_\_ for items on the OPAC search results.

Values:

-  call number only

-  collection code

-  location

Description:

-  This setting allows users of the OPAC results XSLT stylesheet to
   choose to display collection code or location in addition to call
   number.

`OpacNewsLibrarySelect <#OpacNewsLibrarySelect>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't display

Asks: \_\_\_ a branch selection list for news items in the OPAC.

Values:

-  Don't display

-  Display

`OpacPasswordChange <#OpacPasswordChange>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to change their own password on the OPAC.

Values:

-  Allow

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'allow'

-  Don't allow

    **Important**

    Enabling this will break LDAP authentication.

`OPACPatronDetails <#OPACPatronDetails>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to notify the library of changes to their contact
information from the OPAC.

Values:

-  Allow

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'allow'

-  Don't allow

Description:

-  If patrons are allowed to notify the library of changes to their
   account then staff will need to approve the changes via the staff
   client. Notification of patron account requests will appear on the
   dashaboard below the list of modules with other pending actions.

   Patrons requesting modifications
   |image97|

   Once you click the notification you will be presented with the
   changes the patron would like to make to their account and from there
   you can choose how to proceed.

   Patrons modifications
   |image98|

       **Note**

       You can control what fields patrons see and can modify via the
       OPAC by setting the
       `PatronSelfRegistrationBorrowerMandatoryField <#PatronSelfRegistrationBorrowerMandatoryField>`__
       `PatronSelfRegistrationBorrowerUnwantedField <#PatronSelfRegistrationBorrowerUnwantedField>`__
       preferences.

`OPACpatronimages <#OPACpatronimages>`__
''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ patron images on the patron information page in the OPAC.

Values:

-  Don't show

-  Show

Description:

-  If `patronimages <#patronimages>`__ is set to allow the upload of
   patron images via the staff client, then setting this preference to
   'show' will show the patron what image you have on file for them when
   they view their personal information on their account in the OPAC.

`OPACPopupAuthorsSearch <#OPACPopupAuthorsSearch>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't display

Asks: \_\_\_ the list of authors/subjects in a popup for a combined
search on OPAC detail pages.

Values:

-  Display

   Subject search pop up

   -  **Important**

          This will only display the pop up if you are not using an XSLT
          stylesheet. Review your
          `OPACXSLTDetailsDisplay <#OPACXSLTDetailsDisplay>`__ to find
          out what stylesheet you're using.

-  Don't display

   -  Authors and subjects will display as search links instead of pop
      up menus.

Description:

-  If this preference is set to 'Display' then clicking a subject or
   author from the details page in the OPAC will present the searcher
   with a pop up box. From this box you can check off any of the
   subjects or authors listed and search them all at once by clicking
   'Search' at the bottom of the pop up. The default behavior is for
   Koha to search just the clicked author or subject.

`OpacResetPassword <#OpacResetPassword>`__
''''''''''''''''''''''''''''''''''''''''''

Default: not allowed

Asks: Library users are \_\_\_ to recover their password via e-mail in
the OPAC.

Values:

-  allowedForgot your password link

-  not allowed

Description:

-  This preference controls whether you present users of the public
   catalog with a 'Forgot your password' link or not. Learn more in the
   `OPAC section <#resetpwopac>`__ of this manual.

`OpacTopissue <#OpacTopissue>`__
''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ patrons to access a list of the most checked out items on
the OPAC.

Values:

-  Allow

   -  A link to 'Most Popular' will appear at the top of your OPAC

      'Most Popular' link under the search box
      |image99|

-  Don't allow

Description:

-  This preference allows the administrator to choose to show the "Most
   Popular" link at the top of the OPAC under the search box. The "Most
   Popular" page shows the top circulated items in the library, as
   determined by the number of times a title has been circulated. This
   allows users to see what titles are popular in their community. It is
   recommended that you leave this preference set to 'Don't allow' until
   you have been live on Koha for a couple of months, otherwise the data
   that it shows will not be an accurate portrayal of what's popular in
   your library.

   Sample top issues page
   |image100|

`opacuserlogin <#opacuserlogin>`__
''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to log in to their accounts on the OPAC.

Values:

-  Allow

-  Don't allow

   -  The OPAC will still be searchable if patrons can't log in, this
      just disables the patron account access via the OPAC

`QuoteOfTheDay <#QuoteOfTheDay>`__
''''''''''''''''''''''''''''''''''

Default: Disable

Asks: \_\_\_ Quote of the Day display on OPAC home page

Values:

-  Disable

-  Enable

Description:

-  This feature will allow you to enter a series of quotes that will
   then show on the OPAC homepage in random order. To add/edit quotes,
   visit the `Quote of the Day Editor <#QOTDEditor>`__ under Tools.

`RequestOnOpac <#RequestOnOpac>`__
''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to place holds on items from the OPAC.

Values:

-  Allow

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'allow'

-  Don't allow

`reviewson <#reviewson>`__
''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to make comments on items on the OPAC.

Values:

-  Allow

   -  Patrons comments/reviews all require moderation before they appear
      in the OPAC

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'Allow'

-  Don't allow

Description:

-  This button allows the patrons to submit comments on books they have
   read via the OPAC. If this preference is set to "Allow" reviews are
   first sent to the staff client for staff approval before the review
   is displayed in the OPAC. The staff member who reviews and approves
   comments may find the pending comments on the
   `Comments <#comments>`__ tool. The staff member can then choose to
   approve or delete the comments.

`ShowReviewer <#ShowReviewer>`__
''''''''''''''''''''''''''''''''

Default: full name

Asks: Show \_\_\_ of commenter with comments in OPAC.

Values:

-  first name

-  first name and last initial

-  full name

-  last name

-  no name

-  username

Description:

-  If you would like to protect your patron's privacy in the OPAC you
   can choose to hide their names or parts of their names from any of
   the comments they leave on bib records in your system.
   `reviewson <#reviewson>`__ needs to be set to 'Allow' for this to
   preference to come in to play

`ShowReviewerPhoto <#ShowReviewerPhoto>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ reviewer's photo beside comments in OPAC.

Values:

-  Hide

-  Show

   -  `reviewson <#reviewson>`__ needs to be set to 'Allow' and
      `ShowReviewer <#ShowReviewer>`__ needs to be set to 'Show' for
      this to preference to come in to play

      ShowReviewerPhoto set to 'Show'
      |image101|

Description:

-  This system preference allows libraries to show avatars next to
   patron's comments in the OPAC. These avatars are pulled from the
   `Libravatar <https://www.libravatar.org>`__ library, an open source
   powered product that allows Internet users to choose a small icon to
   display next to their name on various different websites. The library
   has no control over the images the patron chooses to display.

`SocialNetworks <#SocialNetworks>`__
''''''''''''''''''''''''''''''''''''

Default: Disable

Asks: \_\_\_ social network links in opac detail pages

Values:

-  Disable

-  Enable

   Social Networks
   |image102|

Description:

-  This preference will enable a line of social network share buttons
   below the right hand column on the detail pages of records in the
   OPAC.

    **Important**

    In order for these share buttons to work when clicked you must have
    filled in your `OPACBaseURL <#OPACBaseURL>`__ preference.

`suggestion <#suggestionspref>`__
'''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to make purchase suggestions on the OPAC.

Values:

-  Allow

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'allow'
      unless `AnonSuggestions <#AnonSuggestions>`__ is set to 'allow'

-  Don't allow

`Payments <#opacpayments>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These preferences will allow you control the tools you use to accept
online payments from your patrons via the OPAC.

`EnablePayPalOpacPayments & PayPalSandboxMode <#EnablePayPalOpacPayments>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

EnablePayPalOpacPayments Default: Don't all

PayPalSandboxMode Default: Sandbox

Asks: \_\_\_ patrons to make payments from the OPAC via PayPal in \_\_\_
mode.

EnablePayPalOpacPayments values:

-  Allow

-  Don't allow

PayPalSandboxMode values:

-  Production

   -  Visit https://developer.paypal.com/ to get information for
      accepting payments in production

-  Sandbox

   -  Visit https://developer.paypal.com/developer/accounts/ to get
      information for your sandbox account

Description:

-  This preference will allow you to accept credit card payments via the
   OPAC for fines via PayPal. You will need to set up your PayPal
   account and it is recommended that you run tests before using this in
   production.

    **Important**

    PayPayl's terms of service state that you cannot charge your patrons
    for the processing fees and so this plugin will not add additional
    fees to the charges.

`PayPalChargeDescription <#PayPalChargeDescription>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Koha fee payment

Asks: The patron should see the charge description as \_\_\_

Description

-  This preference controls what the patron will see on their PayPal
   account/Bank account for this charge.

`PayPalPwd <#PayPalPwd>`__
''''''''''''''''''''''''''

Asks: The password for the PayPal account to receive payments is \_\_\_

`PayPalSignature <#PayPalSignature>`__
''''''''''''''''''''''''''''''''''''''

Asks: The signature for the PayPal account to receive payments is \_\_\_

`PayPalUser <#PayPalUser>`__
''''''''''''''''''''''''''''

Asks: The email address to receive PayPal payments is \_\_\_

`Policy <#opacpolicyprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AllowPurchaseSuggestionBranchChoice <#AllowPurchaseSuggestionBranchChoice>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ patrons to select branch when making a purchase suggestion

Values:

-  Allow

-  Don't allow

Description:

-  If your library system lets patrons make purchase suggestions for a
   specific branch you can set this preference to 'Allow' to add a
   branch selection option to the purchase suggestion form.

`BlockExpiredPatronOpacActions <#BlockExpiredPatronOpacActions>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't block

Asks: \_\_\_ expired patrons from OPAC actions such as placing a hold or
renewing.

Values:

-  Block

-  Don't block

Description:

-  This preference lets you set a default value for how Koha handles
   permissions for patrons who are expired. This preference can be
   overwritten by the setting on `individual patron
   categories <#patcats>`__.

`MaxOpenSuggestions <#MaxOpenSuggestions>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: blank

Asks: Limit patrons to \_\_\_ open suggestions. Leave empty for no limit.
**Note: this setting does not affect anonymous suggestions.

`OpacAllowPublicListCreation <#OpacAllowPublicListCreation>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ opac users to create public lists

Values:

-  Allow

-  Don't allow

Description:

-  Public lists are visible to anyone who visits your OPAC. With this
   preference you can control whether or now patrons are allowed to
   create these public lists. If this is set to "Don't allow" then only
   staff will be able to create public lists.

    **Important**

    This preference will only be taken in to account if you have
    `virtualshelves <#virtualshelves>`__ set to 'Allow'

`OpacAllowSharingPrivateLists <#OpacAllowSharingPrivateLists>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ opac users to share private lists with other patrons.

Values:

-  Allow

-  Don't allow

Description:

-  This feature will add the option for patrons to share their lists
   with other patrons. When this is set to 'Allow' patrons will see a
   share link at the top of their list. When they click that link it
   will ask for the email of the patron they would like to share with.
   Koha will then email the patron an invitation to see the list.

`OPACFineNoRenewals <#OPACFineNoRenewals>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: 99999

Asks: Only allow patrons to renew their own books on the OPAC if they
have less than \_\_\_ USD in fines

    **Note**

    Leave this field blank to disable

    **Important**

    To allow renewals in the OPAC, `opacuserlogin <#opacuserlogin>`__
    needs to be set to 'allow'

`OpacHiddenItems <#OpacHiddenItems>`__
''''''''''''''''''''''''''''''''''''''

Asks: Allows to define custom rules for hiding specific items at opac.

    **Note**

    See docs/opac/OpacHiddenItems.txt in your Koha install directory for
    more information

Description:

-  In this field you can enter criteria for items you would like to hide
   from display in the OPAC. This field takes any combination of item
   fields (from the items table in the Koha database) for blocking. For
   example a value of:

   ::

       itype: [07, 10]
       location: [STAFF, ISO]

   Will block items with an itype code of 07 or 10 as well as items that
   have a shelving location of STAFF or ISO.

   In items my items.itype 07 is defined in Item Types Administration as
   Staff Assigned My items.itype 10 in Item Types is Archival Copy The
   locations STAFF and ISO are in Authorized Values for category=LOC
   STAFF means it's assigned to the staff reading room and ISO means it
   is in the isolation room.

`OpacRenewalAllowed <#OpacRenewalAllowed>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ patrons to renew their own books on the OPAC.

Values:

-  Allow

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'allow'

-  Don't allow

   -  Staff will still be able to renew items for patrons via the staff
      client

Description:

-  This preference allows the administration to choose if patrons can
   renew their checked out materials via their checked out history in
   the OPAC. It allows patrons to renew their materials without having
   to contact the library or having to return to the library.

`OpacRenewalBranch <#OpacRenewalBranch>`__
''''''''''''''''''''''''''''''''''''''''''

Default: the branch the item was checked out from

Asks: Use \_\_\_ as branchcode to store in the statistics table

Values:

-  NULL

-  'OPACRenew'

-  the item's home branch

-  the patron's home branch

-  the branch the item was checked out from

Description:

-  This value is used in the statistics table to help with reporting.
   The statistics table in Koha keeps track of all checkouts and
   renewals, this preference defines which branch is entered in to the
   table when a patron renews an item for themselves via the OPAC.

`OPACSuggestionMandatoryFields <#OPACSuggestionMandatoryFields>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: blank

Asks: Fields that should be mandatory for patron purchase suggestions:
\_\_\_ Note: if none of the above options are selected, 'Title' field
would be mandatory anyway, by default.

Values:

-  [Select all]

-  Author

-  Collection title

-  Copyright or publication date

-  ISBN, ISSN or other standard number

-  Item type

-  Library or branch

-  Note

-  Patron reason

-  Publication place

-  Publisher name

-  Title

`OPACViewOthersSuggestions <#OPACViewOthersSuggestions>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ purchase suggestions from other patrons on the OPAC.

Values:

-  Don't show

-  Show

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'allow'

`SearchMyLibraryFirst <#SearchMyLibraryFirst>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't limit

Asks: \_\_\_ patrons' searches to the library they are registered at.

Values:

-  Don't limit

   -  Searching the OPAC will show results from all libraries

   -  If you're a one branch system, choose 'Don't limit'

-  Limit

   -  Patrons will still be able to search other libraries via the
      Advanced search page - but will be limited to searches for their
      library only from the basic search box

   -  `opacuserlogin <#opacuserlogin>`__ needs to be set to 'allow'

`Privacy <#opacprivacyprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AllowPatronToSetCheckoutsVisibilityForGuarantor <#AllowPatronToSetCheckoutsVisibilityForGuarantor>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ patrons to choose their own privacy settings for showing
the patron's checkouts to the patron's guarantor".

Values:

-  Allow

-  Don't allow

Description:

-  By default staff can see checkouts to family members via the staff
   client. This preference will allow guarantees (children) to grant
   permission to guarantors (guardians) to view their current checkouts
   via the public catalog. This preference requires that you allow
   patrons to se their own privacy with the
   `OPACPrivacy <#OPACPrivacy>`__ preference.

`AnonSuggestions <#AnonSuggestions>`__
''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ patrons that aren't logged in to make purchase suggestions.

    **Important**

    If set to 'Allow', suggestions are connected to the
    `AnonymousPatron <#AnonymousPatron>`__

Values:

-  Allow

-  Don't allow

`AnonymousPatron <#AnonymousPatron>`__
''''''''''''''''''''''''''''''''''''''

Default: 0

Asks: Use borrowernumber \_\_\_ as the Anonymous Patron (for anonymous
suggestions and reading history)

    **Note**

    Before setting this preference `create a patron <#addnewpatron>`__
    to be used for all anonymous suggestions and/or reading history
    items. This patron can be any type and should be named something to
    make it clear to you that they're anonymous (ex. Anonymous Patron).

    **Important**

    Remember to use the borrowernumber note the patron's cardnumber for
    this value. The borrowernumber can be found on the patron record
    under 'Library use' on the right.Borrowernumber

`EnableOpacSearchHistory <#EnableOpacSearchHistory>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Keep

Asks: \_\_\_ patron search history in the OPAC.

Values:

-  Don't keep

-  Keep

`OPACPrivacy <#OPACPrivacy>`__
''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ patrons to choose their own privacy settings for their
reading history.

    **Important**

    This requires `opacreadinghistory <#opacreadinghistory>`__ set to
    'Allow' and `AnonymousPatron <#AnonymousPatron>`__ to be set to your
    anonymous patron's borrowernumber.

Values:

-  Allow

-  Don't allow

Description:

-  The default privacy setting for each patron category can be set in
   the `Patrons Categories <#patcats>`__ area. If you set this
   preference to 'allow' then patrons can change that for themselves via
   the OPAC.

    **Important**

    If patron has chosen to have their reading history anonymized and
    you have `StoreLastBorrower <#StoreLastBorrower>`__ set to "Don't
    store" then as soon as the item is checked in the last borrower will
    be anonymized.

`opacreadinghistory <#opacreadinghistory>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ patrons to see what books they have checked out in the
past.

    **Important**

    Enabling this will make it so that patrons can view their
    circulation history in the OPAC unless you have
    `OPACPrivacy <#OPACPrivacy>`__ set to 'Allow.'

    **Important**

    This data is stored in the system regardless of your choice, unless
    your patrons have chosen to never have their reading history kept.

`StoreLastBorrower <#StoreLastBorrower>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't store

Asks: \_\_\_ the last patron to return an item.

Values:

-  Don't store

-  Store

Description:

-  This preference allows you to store the last patron to borrow an item
   even if the patron has chosen to have their reading history
   anonymized.

    **Note**

    This setting is independent of
    `opacreadinghistory <#opacreadinghistory>`__ and/or
    `AnonymousPatron <#AnonymousPatron>`__.

`TrackClicks <#TrackClicks>`__
''''''''''''''''''''''''''''''

Default: Don't track

Asks: \_\_\_ links that patrons click on.

Values:

-  Don't track

-  Track

-  Track anonymously

Description:

-  By setting this preference to one of the track options you will allow
   Koha to track every link clicked in Koha. This data will be stored in
   a database table so that you can run reports against that data. If
   you choose to 'Track' clicks then Koha will record both the link
   clicked and the logged in user who clicked the link. If you choose to
   'Track anonymously' then the borrowernumber will not be recorded, but
   the rest of the data will.

       **Note**

       Remember to update your local privacy policies and link to them
       from the OPAC to notify your users that you are tracking their
       information.

`Restricted Page <#opacrestrictedpg>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Using the following preference you can create a page within your Koha
system that is accessible by only specific IP addresses. This can be
used to house links to databases that can only be accessed from with the
library or other licensed content.

`RestrictedPageContent <#RestrictedPageContent>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: HTML content of your restricted page.

`RestrictedPageLocalIPs <#RestrictedPageLocalIPs>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Access from IP addresses beginning with \_\_\_ do not need to be
authenticated

Description:

-  You can enter individual IPS as a comma separated list (ex:
   '127.0.0,127.0.1') or just the beginning of the IP range allowed (ex:
   '127.0.')

`RestrictedPageTitle <#RestrictedPageTitle>`__
''''''''''''''''''''''''''''''''''''''''''''''

Asks: Use \_\_\_ as title of your restricted page

Description:

-  This title will appear in the breadcrumb and on the top of the
   restricted page.

`Self Registration <#opacselfregistrationprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`PatronSelfModificationBorrowerUnwantedField <#PatronSelfModificationBorrowerUnwantedField>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: password

Asks: The following `database
columns <http://schema.koha-community.org/tables/borrowers.html>`__ will
not appear on the patron self-modification screen: \_\_\_

Description:

-  This preference allows you to define what fields patrons can edit if
   you're allowing them to update their personal information via the
   public catalog with the `OPACPatronDetails <#OPACPatronDetails>`__
   preference.

    **Important**

    Separate columns with \|

`PatronSelfRegistration <#PatronSelfRegistration>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ library patrons to register an account via the OPAC.

Values:

-  Allow

-  Don't allow

Description:

-  Setting this preference to 'Allow' will provide a link on the OPAC to
   register for a new account. Using the other `Self
   Registration <#opacselfregistrationprefs>`__ system preferences you
   can control how this preference will function.

   Register link in the OPAC
   |image103|

    **Important**

    Patrons registering via the OPAC will not need to be approved by a
    librarian. For this reason it is recommended that you set up a
    provisional `patron category <#patcats>`__ with no `circulation
    rights <#circfinerules>`__. That way patrons will have to come in to
    the library to verify their identity before given circulation rights
    at the library. Once the patron confirms their identiy the library
    staff can change the category to one with permissions to check items
    out and place holds.

`PatronSelfRegistrationAdditionalInstructions <#PatronSelfRegistrationAdditionalInstructions>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Display the following additional instructions for patrons who self
register via the OPAC ( HTML is allowed ):

Description:

-  This preference takes any HTML you'd like to display on the page the
   patron sees after successfully registering for their library card.

`PatronSelfRegistrationBorrowerMandatoryField <#PatronSelfRegistrationBorrowerMandatoryField>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: surname\|firstname

Asks: The following database columns must be filled in on the patron
entry screen: \_\_\_

Description:

-  This preference allows you to define what fields patrons must fill in
   on their self regisration form. If any of the required fields are
   blank Koha will not let the patron register.

    **Important**

    Separate columns with \|

    **Note**

    For help with field names, ask your system administrator or `view
    the database
    structure <http://schema.koha-community.org/tables/borrowers.html>`__
    associated with the borrowers table.

    **Note**

    If you're going to require that patrons verify their accounts via
    email with the
    `PatronSelfRegistrationVerifyByEmail <#PatronSelfRegistrationVerifyByEmail>`__
    preference the email field will automatically be marked as required.

`PatronSelfRegistrationBorrowerUnwantedField <#PatronSelfRegistrationBorrowerUnwantedField>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: password

Asks: The following database columns will not appear on the patron entry
screen: \_\_\_

Description:

-  Using this preference you can hide fields from the patron registraion
   and update form in the OPAC.

    **Important**

    Separate columns with \|

    **Note**

    For help with field names, ask your system administrator or `view
    the database
    structure <http://schema.koha-community.org/tables/borrowers.html>`__
    associated with the borrowers table.

`PatronSelfRegistrationDefaultCategory <#PatronSelfRegistrationDefaultCategory>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Use the patron category code \_\_\_ as the default patron category
for patrons registered via the OPAC.

Description:

-  Enter in the patron category code for the category that all new
   patrons registered via the OPAC will be put in to.

    **Important**

    Patrons registering via the OPAC will not need to be approved by a
    librarian. For this reason it is recommended that you set up a
    provisional `patron category <#patcats>`__ with no `circulation
    rights <#circfinerules>`__. That way patrons will have to come in to
    the library to verify their identity before given circulation rights
    at the library. Once the patron confirms their identiy the library
    staff can change the category to one with permissions to check items
    out and place holds.

    **Important**

    If you leave this blank or enter in an invalid code your patrons
    will still be able to register but will not be given a username.
    There will be no errors on the page to explain this, so be sure to
    enter a valid patron category code.
    
`PatronSelfRegistrationEmailMustBeUnique <#PatronSelfRegistrationEmailMustBeUnique>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Do not consider

Asks: \_\_\_ patron's email (borrowers.email) as unique on self registering.
An email won't be accepted if it already exists in the database.

Values:

-  Do not consider

-  Consider

`PatronSelfRegistrationExpireTemporaryAccountsDelay <#PatronSelfRegistrationExpireTemporaryAccountsDelay>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 0

Asks: Delete patrons registered via the OPAC, but not yet verified after
\_\_\_ days.

Description:

-  This prefence links to the `delete\_expired\_opac\_registrations.pl
   cron job <#deleteexpiredregistrationcron>`__. If that cron is set to
   run nightly it will clean up any registrations that have not been
   verified via email in the number of days entered on this preference.
   This is dependent on
   `PatronSelfRegistrationVerifyByEmail <#PatronSelfRegistrationVerifyByEmail>`__
   preference.

`PatronSelfRegistrationLibraryList <#PatronSelfRegistrationLibraryList>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: blank

Asks: Enable the self registration for the following libraries: \_\_\_
(separate branchcode with |). If empty, all libraries will be listed.

`PatronSelfRegistrationPrefillForm <#PatronSelfRegistrationPrefillForm>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Display and prefill

Asks: \_\_\_ password and login form after a patron has self registered.

Values:

-  Do not display and prefill

-  Display and prefill

`PatronSelfRegistrationVerifyByEmail <#PatronSelfRegistrationVerifyByEmail>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't require

Asks: \_\_\_ that a self-registering patron verify his or herself via
email.

Values:

-  Don't require

-  Require

Description:

-  If you require patrons to verify their accounts via email they will
   not be able to log in to the OPAC until they acknowledge the email
   sent by Koha. If you don't require this then patrons will be able to
   log in as soon as they fill in the registration form. You can set the
   `PatronSelfRegistrationExpireTemporaryAccountsDelay <#PatronSelfRegistrationExpireTemporaryAccountsDelay>`__
   preference to delete the un-verified self registrations after a
   certain number of days.

    **Note**

    If you're going to require that patrons verify their accounts via
    email then the email field will automatically be marked as required.

`Shelf Browser <#shelfbrowseprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`OPACShelfBrowser <#OPACShelfBrowser>`__
''''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ a shelf browser on item details pages, allowing patrons to
see what's near that item on the shelf.

Values:

-  Don't show

-  Show

   OPACShelfBrowser
   |image104|

Description:

-  This preference allows patrons to view what is located on the shelf
   near the item they looked up. The shelf browser option appears on the
   details page to the right of each items' call number. Clicking the
   'Browse Shelf' link allows for a virtual shelf browsing experience
   via the OPAC and lets patrons see other books that may relate to
   their search and items that sit on the shelf near the item they are
   looking at.

    **Important**

    This uses up a fairly large amount of resources on your server, and
    should be avoided if your collection has a large number of items.

`ShelfBrowserUsesCcode <#ShelfBrowserUsesCcode>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't use

Asks: \_\_\_ the item collection code when finding items for the shelf
browser.

Values:

-  Don't use

-  Use

Description:

-  If your library uses collection codes then you might want the shelf
   browser to take into consideration what collection the books belong
   to when populating the virtual shelf browser.

`ShelfBrowserUsesHomeBranch <#ShelfBrowserUsesHomeBranch>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Use

Asks: \_\_\_ the item home branch when finding items for the shelf
browser.

Values:

-  Don't use

-  Use

Description:

-  If you have a multiple branch system you may want to make sure that
   Koha takes into consideration what branch owns the books when
   populating the virtual shelf browser for accuracy.

`ShelfBrowserUsesLocation <#ShelfBrowserUsesLocation>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Use

Asks: \_\_\_ the item location when finding items for the shelf browser.

Values:

-  Don't use

-  Use

Description:

-  If your library uses shelving locations then you might want the shelf
   browser to take into consideration what shelving location the books
   belong to when populating the virtual shelf browser.

`Patrons <#patronprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences > Patrons

`General <#generalpatronpref>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AllowStaffToSetCheckoutsVisibilityForGuarantor <#AllowStaffToSetCheckoutsVisibilityForGuarantor>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ staff to set the ability for a patron's checkouts to be
viewed by linked patrons in the OPAC.

Values:

-  Don't allow

-  Allow

`AutoEmailOpacUser <#AutoEmailOPACUser>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't send

Asks: \_\_\_ an email to newly created patrons with their account
details.

Description:

-  AutoEmailOpacUser allows library users to be notified by email of
   their account details when a new account is opened at the email
   address specified in the
   `AutoEmailPrimaryAddress <#AutoEmailPrimaryAddress>`__ preference.
   The email contains the username and password given to or chosen by
   the patron when signing up for their account and can be customized by
   editing the `ACCTDETAILS <#ACCTDETAILS>`__ notice.

Values:

-  Don't send

-  Send

`AutoEmailPrimaryAddress <#AutoEmailPrimaryAddress>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: alternate

Asks: Use \_\_\_ patron email address for sending out emails.

Values:

-  alternate

-  first valid

-  home

-  work

Description:

-  If you choose 'first valid' as the value for AutoEmailPrimaryAddress
   the system will check the email fields in this order: home, work,
   then alternate. Otherwise the system will use the email address you
   specify.

`autoMemberNum <#autoMemberNum>`__
''''''''''''''''''''''''''''''''''

Default: Do

Asks: \_\_\_ default the card number field on the patron addition screen
to the next available card number

Values:

-  Do

   -  If the largest currently used card number is 26345000012941, then
      this field will default to 26345000012942 for the next patron

-  Don't

Description:

-  This preference determines if the patron's barcode is automatically
   calculated. This prevents the person setting up the library card
   account from having to assign a number to the new card. If set to
   'Do' the system will calculate a new patron barcode by adding 1 to
   the maximum barcode already present in the database.

`BorrowerMandatoryField <#BorrowerMandatoryField>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: surname\|cardnumber\|barcode

Asks: The following database columns must be filled in on the patron
entry screen: \_\_\_

Description:

-  This preference enables the system administrator to choose which
   fields your library would like required for patron accounts. Enter
   field names separated by \| (bar). This ensures that basic
   information is included in each patron record. If a patron leaves one
   of the required fields blank an error message will issue and the
   account will not be created.

    **Important**

    Separate columns with \|

    **Note**

    For help with field names, ask your system administrator or `view
    the database
    structure <http://schema.koha-community.org/tables/borrowers.html>`__
    associated with the borrowers table.

`borrowerRelationship <#borrowerRelationship>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: father\|mother

Asks: Guarantors can be the following of those they guarantee \_\_\_

Description:

-  This preference enables the system administrator to define valid
   relationships between a guarantor (usually a parent) & a guarantee
   (usually a child). Defining values for this field does not make the
   guarantor field required when adding a guarantee type patron. This
   preference creates a drop down list identifying the relationship of
   the guarantor to the guarantee. To disable the ability to add
   children types in Koha you can leave this field blank.

    **Important**

    Input multiple choices separated by \|

`BorrowerRenewalPeriodBase <#BorrowerRenewalPeriodBase>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: current date

Asks: When renewing borrowers, base the new expiry date on \_\_\_

Values:

-  current date.

-  current membership expiry date.

Description:

-  This preference controls what the patron's new expiration date will
   be when you renew their card. Using the 'current date' will add the
   subscription period to today's date when calculating the new
   expiration date. Using 'current membership expiry date' will add the
   subscription period to the old expiration date for the patron when
   renewing their account.

`BorrowersTitles <#BorrowersTitles>`__
''''''''''''''''''''''''''''''''''''''

Default: Mr\|Mrs\|Miss\|Ms

Asks: Borrowers can have the following titles \_\_\_

Description:

-  This preference allows the staff to choose the titles that can be
   assigned to patrons. The choices present as a drop down list when
   creating a patron record.

    **Important**

    Input multiple choices separated by \|

`BorrowerUnwantedField <#BorrowerUnwantedField>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: The following database columns will not appear on the patron entry
screen: \_\_\_

Description:

-  This preference enables the system administrator to choose which
   fields your library doesn't need to see on the patron entry form.
   Enter field names separated by \| (bar).

    **Important**

    Separate columns with \|

    **Note**

    For help with field names, ask your system administrator or `view
    the database
    structure <http://schema.koha-community.org/tables/borrowers.html>`__
    associated with the borrowers table.

`CardnumberLength <#CardnumberLength>`__
''''''''''''''''''''''''''''''''''''''''

Asks: Card numbers for patrons must be \_\_\_ characters long.

Description:

-  The length can be a single number to specify an exact length, a range
   separated by a comma (i.e., 'Min,Max'), or a maximum with no minimum
   (i.e., ',Max'). If 'cardnumber' is included in the
   `BorrowerMandatoryField <#BorrowerMandatoryField>`__ list, the
   minimum length, if not specified here, defaults to one.

`checkdigit <#checkdigit>`__
''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ check and construct borrower card numbers in the Katipo
style.

Values:

-  Do

-  Don't

    **Important**

    This overrides `autoMemberNum <#autoMemberNum>`__ if on.
    
`CheckPrevCheckout <#CheckPrevCheckout>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Do not

Asks: \_\_\_ check borrower checkout history to see if the current item has been checked out before.

Values:

-  Do

-  Do not

-  Unless overridden, do

-  Unless overridden, do not

`DefaultPatronSearchFields <#DefaultPatronSearchFields>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: surname,firstname,othernames,cardnumber,userid

Asks: \_\_\_ Comma separated list defining the default fields to be used during a patron search

    **Important** possible values can be found in the borrowers table of Koha's schema
    located at http://schema.koha-community.org/

`EnableBorrowerFiles <#EnableBorrowerFiles>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ enable the ability to upload and attach arbitrary files to
a borrower record.

Values:

-  Do

-  Don't

Description:

-  When enabled this will add a 'Files' tab to the left of the patron
   detail page where you can view and upload files to the patron record.

`EnhancedMessagingPreferences <#EnhancedMessagingPreferences>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to manage which notices patrons will receive and when
they will receive them.

Values:

-  Allow

-  Don't allow

    **Important**

    This only applies to certain kinds of notices, overdue notices will
    be sent based on the library's rules, not the patron's choice.

    **Note**

    To manage if patrons have also access to these settings, use
    `EnhancedMessagingPreferencesOPAC <#EnhancedMessagingPreferencesOPAC>`__.

Description:

-  These messages are in addition to the overdue notices that the
   library sends. The difference between these notices and overdues is
   that the patron can opt-in and out of these. Setting this preference
   to 'Allow' will allow staff to choose for patrons to receive any one
   of the following messages:

   -  Item Checkout : A notice that lists all the of the items the
      patron has just checked out and/or renewed, this is an electronic
      form of the checkout receipt

   -  Item Due : A notice on the day and item is due back at the library

   -  Hold Filled : A notice when you have confirmed the hold is waiting
      for the patron

   -  Item Checkin : A notice that lists all the of the items the patron
      has just checked in

   -  Advanced Notice : A notice in advance of the patron's items being
      due (Staff can choose the number of days in advance)

`EnhancedMessagingPreferencesOPAC <#EnhancedMessagingPreferencesOPAC>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ patron messaging setting on the OPAC

Values:

-  Don't show

-  Show

    **Important**

    `EnhancedMessagingPreferences <#EnhancedMessagingPreferences>`__
    must be enabled for messaging options to show in the OPAC

Description:

-  These messages are in addition to the overdue notices that the
   library sends. The difference between these notices and overdues is
   that the patron can opt-in and out of these. Setting this preference
   to 'Allow' will allow patrons to choose to receive any one of the
   following messages:

   -  Item Checkout : A notice that lists all the of the items the
      patron has just checked out and/or renewed, this is an electronic
      form of the checkout receipt

   -  Item Due : A notice on the day and item is due back at the library

   -  Hold Filled : A notice when you have confirmed the hold is waiting
      for the patron

   -  Item Checkin : A notice that lists all the of the items the patron
      has just checked in

   -  Advanced Notice : A notice in advance of the patron's items being
      due (The patron can choose the number of days in advance)

`ExtendedPatronAttributes <#ExtendedPatronAttributes>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Enable

Asks: \_\_\_ searching, editing and display of custom attributes on
patrons.

Values:

-  Don't enable

-  Enable

   -  Define attributes in Koha administration

   -  Get there: More > Administration > `Patron Attribute
      Types <#patronattributetypes>`__

Description:

-  Patron attributes are library-defined custom fields that can be
   applied to patron records.

    **Note**

    Use custom attributes for fields that the default patron record does
    not support such as driver's license number or student ID number.

`FeeOnChangePatronCategory <#FeeOnChangePatronCategory>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Do

Asks: \_\_\_ charge a fee when a patron changes to a category with an
enrollment fee.

Values:

-  Do

-  Don't

`intranetreadinghistory <#intranetreadinghistory>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to access a patron's checkout history.

    **Important**

    If you have the `OPACPrivacy <#OPACPrivacy>`__ preference set to
    'Allow' and the patron has decided to not have their history kept
    staff will only see currently checked out items.

Values:

-  Allow

-  Don't allow

    **Important**

    Reading history is still stored, regardless of staff being allowed
    access or not unless the patron has chosen to have their history
    anonymized via their `privacy page <#opacmyprivacy>`__.

`MaxFine <#MaxFine>`__
''''''''''''''''''''''

Default: 9999

Asks: The late fine for all checkouts will only go up to \_\_\_ USD.

Description:

-  This preference controls the default cap on fines accrued by the
   patron. Leaving this preference blank means that there is no cap on
   the amount of fines a patron can accrue. If you'd like, single item
   caps can be specified in the `circulation rules
   matrix <#circfinerules>`__.

`MembershipExpiryDaysNotice <#MembershipExpiryDaysNotice>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Send an account expiration notice when a patron's card will expire
in \_\_\_ days.

Description:

-  If you would like to notify patrons that their accounts are about to
   expire then you can enter a number of days before expiration in this
   preference. The notice text can be customized in the `Notices &
   Slips <#notices>`__ tool.

    **Important**

    You will need to enable the `membership expiry cron
    job <#patronexpirycron>`__ for this notice to send.

`minPasswordLength <#minPasswordLength>`__
''''''''''''''''''''''''''''''''''''''''''

Default: 3

Asks: Login passwords for staff and patrons must be at least \_\_\_
characters long.

    **Important**

    This applies to both the staff login and the patron OPAC login.

`NotifyBorrowerDeparture <#NotifyBorrowerDeparture>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 30

Asks: Show a notice that a patron is about to expire \_\_\_ days
beforehand.

Description:

-  When the patron attempts to check out materials, a warning will
   appear in the check out window of the Staff Client telling the
   librarian that the patrons account is about to expire.

    **Important**

    This notice will appear on the patron's record in the staff client.

`patronimages <#patronimages>`__
''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ images to be uploaded and shown for patrons on the staff
client.

Values:

-  Allow

-  Don't allow

Description:

-  If this preference is set to 'Allow' the staff will be able to upload
   images of patrons either `one by one <#addpatronimages>`__ or `in
   bulk <#uploadpatronimages>`__. Patrons images will show on the detail
   page to the left of the patron information. They can also show in the
   OPAC if you set the `OPACpatronimages <#OPACpatronimages>`__ preference
   or in the self check out module if you set the
   `ShowPatronImageInWebBasedSelfCheck <#ShowPatronImageInWebBasedSelfCheck>`__
   preference.

`PatronQuickAddFields <#PatronQuickAddFields>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: blank

Asks: \_\_\_ (separate columns with |) add these fields to the patron
quick add form when entering a new patron. Displays only mandatory fields
and fields specified here. If applicable, the guarantor form will be shown
as well, individual fields in that form will be ignored.

`PatronsPerPage <#PatronsPerPage>`__
''''''''''''''''''''''''''''''''''''

Default: 20

Asks: By default, show \_\_\_ results per page in the staff client.

Description:

-  This preference will let you define how many patrons to show on
   patron search results pages.

`SMSSendDriver, SMSSendUsername, and SMSSendPassword <#SMSSendDriver>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Use the SMS::Send:: \_\_\_ driver to send SMS messages. Define a
username/login \_\_\_ and a password \_\_\_.

    **Important**

    Please refer to your national laws concerning the sending of bulk
    SMS messages before enabling this feature.

Descritpion:

-  There are two options for using SMS in Koha. You can use the Email
   protocol for free by entering 'Email' as the SMSSendDriver or you can
   pay for a SMS driver. Some examples of values for the driver are:

   -  SMS::Send::Us::Ipipi

   -  SMS::Send::US::TMobile

   -  SMS::Send::US::Verizon

   -  SMS::Send::IN::Unicel

   Additional values can be found here:
   http://search.cpan.org/search?query=sms%3A%3Asend&mode=all

       **Important**

       Only drivers available as Perl modules will work in this
       preference, so make sure a Perl module is available before
       choosing an SMS service.

   Once a driver is entered in the preference an option will appear in
   the staff client and the OPAC on the patron messaging form to choose
   to receive messages as SMS

   SMSSendDriver Options
   |image105|

    **Important**

    You must allow
    `EnhancedMessagingPreferences <#EnhancedMessagingPreferences>`__ for
    this to work.

`StatisticsFields <#StatisticsFields>`__
''''''''''''''''''''''''''''''''''''''''

Default: location\|itype\|ccode

Asks: Show the following fields from the items database table as columns
on the statistics tab on the patron record: \_\_\_

Statistics on Patron Record
|image106|

    **Important**

    Enter the values separated by bars (\|)

Description:

-  This preference lets you set which fields will show on the patron
   record on the Statistics tab.

`TalkingTechItivaPhoneNotification <#TalkingTechItivaPhoneNotification>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Disable

Asks: \_\_\_ patron phone notifications using Talking Tech i-tiva
(overdues, predues and holds notices currently supported).

Values:

-  Disable

-  Enable

Description:

-  To learn more about setting up this third party product view the
   `Talking Tech Appendix <#talkingtechappendix>`__.

    **Important**

    Requires that you have
    `EnhancedMessagingPreferences <#EnhancedMessagingPreferences>`__ set
    to Allow to use.
    
`TrackLastPatronActivity <#TrackLastPatronActivity>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ track last patron activity. Everytime a patron will connect,
the borrowers.lastseen will be updated with the current time.

Values:

-  Don't

-  Do

`uppercasesurnames <#uppercasesurnames>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ store and display surnames (last names) in upper case.

Values:

-  Do

-  Don't

`useDischarge <#useDischarge>`__
''''''''''''''''''''''''''''''''

Default: Don't allow

Asks: \_\_\_ librarians to discharge borrowers and borrowers to request
a discharge.

Values:

-  Allow

-  Don't allow

Description:

-  A discharge is a certificate that says the patron has no current
   checkouts, no holds and owe no money.

       **Note**

       In France a "quitus" ("discharge") is needed if you want to
       register for an account in a library or a university).

       **Note**

       Academic libraries often require that you have a clear record at
       the library before you can graduate.

`Norwegian patron database <#norwegianpref>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`FailedLoginAttempts <#FailedLoginAttempts>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: blank

Asks: Block a patron's account if it reaches \_\_\_ failed login attempts.

`NorwegianPatronDBEnable & NorwegianPatronDBEndpoint <#NorwegianPatronDBEnable>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

NorwegianPatronDBEnable Default: Disable

Asks: \_\_\_ the ability to communicate with the Norwegian national
patron database via the \_\_\_ endpoint.

Values:

-  Disable

-  Enable

`NorwegianPatronDBSearchNLAfterLocalHit <#NorwegianPatronDBSearchNLAfterLocalHit>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't

Asks: \_\_\_ search the Norwegian national patron database after a local
search result was found.

Values:

-  Do

-  Don't

`NorwegianPatronDBUsername & NorwegianPatronDBPassword <#NorwegianPatronDBUsername>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Communicate with the Norwegian national patron database using the
username \_\_\_ and the password \_\_\_.

Description:

-  You can get these from "Base Bibliotek", which is maintained by the
   Norwegian National Library.

`Searching <#searchingprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences >
Searching

`Features <#searchfeatureprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`EnableSearchHistory <#EnableSearchHistory>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't keep

Asks: \_\_\_ patron search history in the staff client.

Values:

-  Don't keep

-  KeepEnableSearchHistory

Description:

-  This preference controls whether the staff client keeps search
   history for logged in users. Search history will be accessible under
   the link to your account in the top right of the staff client.

`IncludeSeeFromInSearches <#IncludeSeeFromInSearches>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't include

Asks: \_\_\_ *see from* (non-preferred form) headings in bibliographic
searches.

Values:

-  Don't include

-  Include

Description:

-  When this preference is set to include the search engine indexer will
   insert *see from* headings from authority records into bibliographic
   records when indexing, so that a search on an obsolete term will turn
   up relevant records. For example when you search for cookery (the old
   term) you get titles with the heading of cooking (the new term).

    **Important**

    You will need to reindex your bibliographic database when changing
    this preference.

`OpacGroupResults <#OpacGroupResults>`__
''''''''''''''''''''''''''''''''''''''''

Default: Don't use

Asks: \_\_\_ PazPar2 to group similar results on the OPAC.

Values:

-  Don't use

-  Use

    **Important**

    This requires that `PazPar2 <http://www.indexdata.com/pazpar2>`__ is
    set up and running.

`QueryAutoTruncate <#QueryAutoTruncate>`__
''''''''''''''''''''''''''''''''''''''''''

Default: automatically

Asks: Perform wildcard searching (where, for example, Har would match
Harry and harp) \_\_\_ (The \* character would be used like so: Har\* or
\*logging.)

Values:

-  automatically

-  only if \* is added

Description:

-  This setting allows for searches to be automatically truncated or for
   additional characters to be added to the end of a search string. When
   set to "automatically" the search string automatically ends with a
   wildcard function. For example, a search for the word "invent" with
   auto truncation enabled will also retrieve results for inventor,
   invention, inventory, etc. If you don't want this to happen
   automatically you can still be perform wildcard searches manually by
   adding an asterisk (\*). Typing "invent\*" even with auto truncation
   disabled will retrieve the same inventor, invention, inventory
   results. Auto truncation bypasses the necessity to type long search
   strings in their entirety.

`QueryFuzzy <#QueryFuzzy>`__
''''''''''''''''''''''''''''

Default: Try

Asks: \_\_\_ to match similarly spelled words in a search (for example,
a search for flang would also match flange and fang)

Values:

-  Don't try

-  Try

Description:

-  This preference enables "fuzzy" searching, in which the search engine
   returns results that are similar to, but not exactly matching, the
   word or words entered by the user. This preference enables the search
   function to compensate for slightly misspelled names or phrases.

    **Important**

    Requires that `UseICU <#UseICU>`__ set to 'Not using'

`QueryStemming <#QueryStemming>`__
''''''''''''''''''''''''''''''''''

Default: Try

Asks: \_\_\_ to match words of the same base in a search

Values:

-  Don't try

-  Try

   -  A search for enabling would also match enable and enabled

Description:

-  This preference enables word stemming. Stemming allows the search
   function to return multiple versions of the same word, as well as
   related terms (i.e., both fish and fishing would be returned).

`QueryWeightFields <#QueryWeightFields>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Enable

Asks: \_\_\_ ranking of search results by relevance

Values:

-  Disable

-  Enable

`TraceCompleteSubfields <#TraceCompleteSubfields>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Force

Asks: \_\_\_ subject tracings in the OPAC and Staff Client to search
only for complete-subfield matches.

Values:

-  Don't force

   -  Searches for subject keywords (example:
      opac-search.pl?q=su:World%20Wide%20Web)

-  Force

   -  Searches for complete subject fields (example:
      opac-search.pl?q=su,complete-subfield:World%20Wide%20Web)

Description:

-  When TraceCompleteSubfields is set to "force," clicking on links in
   non-authority controlled subject tracings will only find other
   records where the entire subfields match. Leaving it at "don't force"
   does a keyword search of the subject indexes.

    **Important**

    This preference assumes that you're using XSLT stylesheets as set in
    the `OPACXSLTDetailsDisplay <#OPACXSLTDetailsDisplay>`__ preference.

`TraceSubjectSubdivisions <#TraceSubjectSubdivisions>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Include

Asks: \_\_\_ subdivisions for searches generated by clicking on subject
tracings.

Values:

-  Don't include

   -  Searches for subject keywords (example:
      opac-search.pl?q=su,complete-subfield:%22Web%20sites%22)

-  Include

   -  Searches for complete subject fields (example:
      opac-search.pl?q=(su,complete-subfield:%22Web%20sites%22)%20and%20(su,complete-subfield:%22Design.%22))

Description:

-  When TraceSubjectSubdivisions is set to "Include," if you click on a
   subject with subdivisions (subfields other than 'a') they will be
   searched along with the subject heading (subfield 'a'). To have only
   the subject heading (subfield 'a') searched, set this preference to
   "Don't include."

    **Important**

    This preference assumes that you're using XSLT stylesheets as set in
    the `OPACXSLTDetailsDisplay <#OPACXSLTDetailsDisplay>`__ preference.

`UseICU <#UseICU>`__
''''''''''''''''''''

Default: Not using

Asks: \_\_\_ ICU Zebra indexing.

Values:

-  Not using

-  Using

Description:

-  ICU is a set of code libraries providing Unicode and Globalization
   support for software applications. What this means is ICU Zebra
   indexing is only necessary if you use non-roman characters in your
   cataloging. If using ICU Zebra indexing you will want to not use
   `QueryFuzzy <#QueryFuzzy>`__.

    **Important**

    This setting will not affect Zebra indexing, it should only be used
    to tell Koha that you have activated ICU indexing if you have
    actually done so, since there is no way for Koha to figure this out
    on its own.

    **Important**

    Talk to your system administrator when changing this preference to
    make sure that your system is set up properly for this to work.

`UseQueryParser <#UseQueryParser>`__
''''''''''''''''''''''''''''''''''''

Default: Do not try

Asks: \_\_\_ to use the QueryParser module for parsing queries.

    **Note**

    Enabling this will have no impact if you do not have QueryParser
    installed, and everything will continue to work as usual.

Values:

-  Do not try

-  Try

Description:

-  This preference enables an experimental new query parser which opens
   the door for a more expressive and more-effective search syntax.

`Results Display <#searchresultsprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`defaultSortField & defaultSortOrder <#defaultSortField>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

defaultSortField Default: author

defaultSortOrder Default: ascending

Asks: By default, sort search results in the staff client by \_\_\_,
\_\_\_\_

Description:

-  These preferences set the default sort field and sort order for
   searches on the staff side. Regardless of your choice, the other sort
   options are still available in the drop down list on the advanced
   search page.

defaultSortField Values:

-  author

-  call number

-  date added

-  date of publication

-  relevance

-  title

-  total number of checkouts

defaultSortOrder Values:

-  ascending

-  descending

-  from A to Z

-  from Z to A

`displayFacetCount <#displayFacetCount>`__
''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ facet counts.

Description:

-  This preference lets you decide if you show how many times a facet is
   used in your search results in the OPAC and the staff client. The
   relevance of these numbers highly depends on the value of the
   `maxRecordsForFacets <#maxRecordsForFacets>`__ preference. Showing
   these numbers can potentially effect the performance of your
   searching, so test your system with different values for this
   preference to see what works best.

Values:

-  Don't show

-  Show

   Number of times each Facet is found in results
   |image107|

`DisplayLibraryFacets <#DisplayLibraryFacets>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: holding library

Asks: Show facets for \_\_\_

Values:

-  both home and holding library

-  holding library

-  home library

Description:

-  This preferenc controls the libraries facet that displays on search
   results in the staff and opac. The value selected here will determin
   which library(s) show in the facets when a search is run.

`FacetLabelTruncationLength <#FacetLabelTruncationLength>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 20

Asks: Truncate facets length to \_\_\_ characters, in OPAC/staff
interface.

Description:

-  In the OPAC and the staff client your facets are cut off at 20
   characters by default. Depending on your layout this may be too many
   or two few letters, this preference lets you decide what number is
   best for your library's design.

`FacetMaxCount <#FacetMaxCount>`__
''''''''''''''''''''''''''''''''''

Default: 20

Asks: Show up \_\_\_ to facets for each category.

Description:

-  This preference allows you to control how many possible limits show
   under each heading (Author, Series, Topics, etc) on the facets in the
   OPAC.

`maxItemsInSearchResults <#maxItemsInSearchResults>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 20

Asks: Show up to \_\_\_ items per biblio in the search results

Description:

-  This preference will let you set how many results display by default
   when a search is run on the Staff Client.

`maxRecordsForFacets <#maxRecordsForFacets>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: 20

Asks: Build facets based on \_\_\_ records from the search results.

Description:

-  By default Koha only bases facets on the first page of results
   (usually 20 results). This preference lets you tell Koha to based the
   facet descriptions and numbers on any number of search results
   returned. The higher this number the longer it will take for your
   search results to return, so test with various different values to
   find the best balance for your library.

`MaxSearchResultsItemsPerRecordStatusCheck <#MaxSearchResultsItemsPerRecordStatusCheck>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: 20

Asks: For records with many items, only check the availability status
for the first \_\_\_ items.

Description:

-  Availability statuses may show incorrectly in search results if a
   record has more items than the limit set. Statuses will display
   correctly in the record details. Leave empty for no limit.

`numSearchResults <#numSearchResults>`__
''''''''''''''''''''''''''''''''''''''''

Default: 20

Asks: By default, show \_\_\_ results per page in the staff client.

`OPACdefaultSortField & OPACdefaultSortOrder <#opacdefaultsort>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

OPACdefaultSortField Default: relevance

OPACdefaultSortOrder Default: ascending

Asks: By default, sort search results in the OPAC by \_\_\_, \_\_\_

Description:

-  These preferences set the default sort field and sort order for
   searches on the OPAC. Regardless of your choice, the other sort
   options are still available in the drop down list on the advanced
   search page.

OPACdefaultSortField Values:

-  author

-  call number

-  date added

-  date of publication

-  relevance

-  title

-  total number of checkouts

OPACdefaultSortOrder Values:

-  ascending

-  descending

-  from A to Z

-  from Z to A

`OPACItemsResultsDisplay <#OPACItemsResultsDisplay>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ an item's branch, location and call number in OPAC search
results.

Values:

-  Don't show

-  Show

Description:

-  This setting selects the information about an item that will display
   in the search results page of the OPAC. The results can display the
   status of an item and/or full details including branch, location, and
   call number. While the 'Show' option allows for more information to
   be displayed on the search results page, the information can be
   overwhelming for large collections with multiple branches.

`OPACnumSearchResults <#OPACnumSearchResults>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: 20

Asks: By default, show \_\_\_ results per page in the OPAC.

`SearchWithISBNVariations <#SearchWithISBNVariations>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: don't search

Asks: When searching on the ISBN index, \_\_\_ on all variations of the
ISBN.

Values:

-  don't search

-  search

Descriptions:

-  With this preference set to search you'll be able to search for ISBNs
   even if there are dashes or spaces in the field. So if you search for
   9781843345855 but the ISBN was cataloged as 978-1843345855 you'll
   still be able to find it if this preference is set to 'search'.

    **Important**

    This preference has no effect if
    `UseQueryParser <#UseQueryParser>`__ is on

`UNIMARCAuthorsFacetsSeparator <#UNIMARCAuthorsFacetsSeparator>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: , (comma)

Asks: Use the following text as separator for UNIMARC authors facets \_\_\_

`Search Form <#searchformprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AdvancedSearchLanguages <#AdvancedSearchLanguages>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Limit the languages listed in the advanced search drop-down to the
\_\_\_ ISO 639-2 language codes (separate values with \| or ,).

Description:

-  This preference will allow you to decide what languages show in the
   pull down menu on the advanced search page in the OPAC and the staff
   client. If this preference is left blank, all languages will show. To
   limit the languages that are shown enter their `ISO 639-2 language
   codes <http://www.loc.gov/standards/iso639-2/php/code_list.php>`__
   separated by comma ( , ) or bar ( \| ). For example to limit listing
   to French and Italian, enter ita\|fre.

`AdvancedSearchTypes <#AdvancedSearchTypes>`__
''''''''''''''''''''''''''''''''''''''''''''''

Default: itemtype

Asks: Show tabs in OPAC and staff-side advanced search for limiting
searches on the \_\_\_ fields (separate values with \|).

Description:

-  On the advanced search page you can choose to allow filters on one or
   all of the following: Item types (itemtypes), Collection Codes
   (ccode) and Shelving Location (loc). If you would like to be able to
   limit searches on item type and shelving location for example you
   would enter itemtypes\|loc in the preference input box. The order of
   these fields will determine the order of the tabs in the OPAC and
   staff client advanced search screens. Values within the search type
   are OR'ed together, while each different search type is AND'ed
   together in the query limits. The current stored values are supported
   without any required modification.Each set of advanced search fields
   are displayed in tabs in both the OPAC and staff client. The first
   value in the AdvancedSearchTypes syspref is the selected tab; if no
   values are present, "itemtypes" is used. For non-itemtype values, the
   value in AdvancedSearchTypes must match the Authorised Value name,
   and must be indexed with 'mc-' prefixing that name.

   Searching by Item Type and Shelving Location
   |image108|

`expandedSearchOption <#expandedSearchOption>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Default: don't show

Asks: By default, \_\_\_ "More options" on the OPAC and staff advanced
search pages.

Values:

-  don't show

-  show

`IntranetNumbersPreferPhrase <#IntranetNumbersPreferPhrase>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: don't use

Asks: By default, \_\_\_ the operator "phr" in the callnumber and
standard number staff client searches

Values:

-  don't use

-  use

Description:

-  When searching by call number and standard number (biblionumber) in
   Koha Staff Client you can choose to force the search to be a phrase
   search by setting this preference to 'use.' This will allow for more
   accurate results over doing a general keyword field search.

`LoadSearchHistoryToTheFirstLoggedUser <#LoadSearchHistoryToTheFirstLoggedUser>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Load

Asks: Load the unlogged history to the next user. \_\_\_ history to the next client.

Values:

-  Don't load

-  Load

`OPACNumbersPreferPhrase <#OPACNumbersPreferPhrase>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: don't use

Asks: By default, \_\_\_ the operator "phr" in the callnumber and
standard number OPAC searches

Values:

-  don't use

-  use

Description:

-  When searching by call number and standard number (biblionumber) in
   the Koha OPAC you can choose to force the search to be a phrase
   search by setting this preference to 'use.' This will allow for more
   accurate results over doing a general keyword field search.

`Serials <#serialsprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences > Serials

`makePreviousSerialAvailable <#makePreviousSerialAvailable>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: Do not make

Asks: \_\_\_ previous serial automatically available when receiving a
new serial issue. The previous issue can also be set to another item
type when receiving a new one. Please note that the `item-level\_itypes <#item-level_itypes>`__
syspref must be set to specific item.

Values:

-  Do not make

-  Make

`opacSerialDefaultTab <#opacSerialDefaultTab>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: Subscriptions tab

Asks: Show \_\_\_ as default tab for serials in OPAC.

Values:

-  Holdings tab

-  Serial Collection tab

       **Important**

       Please note that the Serial Collection tab is currently available
       only for systems using the UNIMARC standard.

   Serial Collection tab
   |image109|

-  Subscriptions tab

   Subscriptions tab
   |image110|

`OPACSerialIssueDisplayCount <#OPACSerialIssueDisplayCount>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: 3

Asks: Show the \_\_\_ previous issues of a serial on the OPAC.

Description:

-  This preference allows the administrator to select the number of
   recent issues for each serial which appear in the OPAC when the
   serial is accessed. This is just the default value, patrons can
   always click to see a full list of serials.

`RenewSerialAddsSuggestion <#RenewSerialAddsSuggestion>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: Don't add

Asks: \_\_\_ a suggestion for a biblio when its attached serial is
renewed.

Values:

-  Add

-  Don't add

Description:

-  If set to "Add", this preference will automatically add a serial to
   the Acquisitions Purchase Suggestions menu when clicking the 'renew'
   option. If you don't use the Acquisitions module to manage serials
   purchases it's best to leave this set as 'Don't add.'

`RoutingListAddReserves <#RoutingListAddReserves>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: Place

Asks: \_\_\_ received serials on hold if they are on a routing list.

Values:

-  Place

-  Don't place

`RoutingListNote <#RoutingListNote>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Asks: Include following note on all routing lists

Description:

-  Text entered in this box will appear below the routing list
   information.

`RoutingSerials <#RoutingSerials>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: Don't add

Asks: \_\_\_ received serials to the routing list.

Description:

-  This preference determines if serials routing lists are enabled or
   disabled for the library. When set to "Add", serials routing is
   enabled and a serial can be directed through a list of people by
   identifying who should receive it next. The list of people can be
   established for each serial to be passed using the Serials module.
   This preference can be used to ensure each person who needs to see a
   serial when it arrives at the library will get it. Learn more in the
   `routing list <#routinglist>`__ section of this manual.

Values:

-  Add

-  Don't add

`StaffSerialIssueDisplayCount <#StaffSerialIssueDisplayCount>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: 3

Asks: Show the \_\_\_ previous issues of a serial on the staff client.

Description:

-  This preference allows the administrator to select the number of
   recent issues for each serial which appear in the Staff Client when
   the serial is accessed. This is just the default value, staff members
   can always click to see a full list of serials.

`SubscriptionDuplicateDroppedInput <#SubscriptionDuplicateDroppedInput>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Asks: List of fields which must not be rewritten when a subscription is
duplicated (Separated by pipe \|) \_\_\_

Description:

-  When duplicating a subscription sometimes you don't want all of the
   fields duplicated, using this preference you can list the fields that
   you don't want to be duplicated. These field names come from the
   subscription table in the Koha database. Learn what fields are in
   that table on the `Koha DB
   Schema <http://schema.koha-community.org/tables/subscription.html>`__
   site.

`SubscriptionHistory <#SubscriptionHistory>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Default: full history

Asks: When showing the subscription information for a bibliographic
record, preselect \_\_\_ view of serial issues.

Values:

-  brief history

   Brief History
   |image111|

-  full history

   Full History
   |image112|

Description:

-  This preference determines what information appears in the OPAC when
   the user clicks the More Details option. The 'brief' option displays
   a one-line summary of the volume and issue numbers of all issues of
   that serial held by the library. The 'full' option displays a more
   detailed breakdown of issues per year, including information such as
   the issue date and the status of each issue.

`Staff Client <#staffprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences > Staff
Client

`Appearance <#staffappearprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`Display856uAsImage <#Display856uAsImage>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: Neither details or results page

Asks: Display the URI in the 856u field as an image on: \_\_\_

Values:

-  Both results and details pages

   -  **Important**

          Not implemented yet

-  Detail page only

   -  **Important**

          `XSLTDetailsDisplay <#XSLTDetailsDisplay>`__ needs to be on
          for this preference to work.

   Showing the 856u as an image
   |image113|

-  Neither details or results page

-  Results page only

   -  **Important**

          Not yet implemented

Description:

-  In addition to this option being set, the corresponding XSLT option
   must be turned on. Also, the corresponding 856q field must have a
   valid MIME image extension (e.g., "jpg") or MIME image type (i.e.
   starting with "image/"), or the generic indicator "img" entered in
   the field. When all of the requirements are met, an image file will
   be displayed instead of the standard link text. Clicking on the image
   will open it in the same way as clicking on the link text. When you
   click on the image it should open to full size, in the current window
   or in a new window depending on the value in the system pref
   `OPACURLOpenInNewWindow <#OPACURLOpenInNewWindow>`__.

   Sample 856 Field
   |image114|

`DisplayIconsXSLT <#DisplayIconsXSLT>`__
''''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ the format, audience, and material type icons in XSLT
MARC21 results and detail pages in the staff client.

    **Important**

    `XSLTResultsDisplay <#XSLTResultsDisplay>`__ and/or
    `XSLTDetailsDisplay <#XSLTDetailsDisplay>`__ must be set to use an
    XSLT stylesheet (default or custom) for these icons to show.

Values:

-  Don't show

-  Show

   DisplayIconsXSLT
   |image115|

    **Note**

    See the `XSLT Icon Guide <#XSLTiTypes>`__ for more information on
    these icons.

`intranet\_includes <#intranet_includes>`__
'''''''''''''''''''''''''''''''''''''''''''

Default: includes

Asks: Use include files from the \_\_\_ directory in the template
directory, instead of includes/. (Leave blank to disable)

`IntranetCirculationHomeHTML <#IntranetCirculationHomeHTML>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Show the following HTML in its own div on the bottom of the home
page of the circulation module: IntranetCirculationHomeHTML

`intranetcolorstylesheet <#intranetcolorstylesheet>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Include the additional CSS stylesheet \_\_\_ to override specified
settings from the default stylesheet

Description:

-  This preference is used to set the background color and style of the
   Staff Client. The value is a .css file. The system administrator
   should determine which file is appropriate. Enter just a filename, a
   full local path or a complete URL starting with http:// (if the file
   lives on a remote server). Please note that if you just enter a
   filename, the file should be in the css subdirectory for each active
   theme and language within the Koha templates directory. A full local
   path is expected to start from your HTTP document root.

    **Important**

    Leave this field blank to disable.

`IntranetFavicon <#IntranetFavicon>`__
''''''''''''''''''''''''''''''''''''''

Asks: Use the image at \_\_\_ for the Staff Client's favicon.

    **Important**

    This should be a complete URL, starting with http://

    **Note**

    Turn your logo into a favicon with the `Favicon
    Generator <http://antifavicon.com/>`__.

Description:

-  The favicon is the little icon that appears next to the URL in the
   address bar in most browsers. The default value for this field (if
   left blank) is the small 'K' in the Koha logo.

   Default Koha Favicon
   |image116|

`IntranetmainUserblock <#IntranetmainUserblock>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Show the following HTML in its own column on the main page of the
staff client

Sample HTML for IntranetmainUserblock
|image117|

Message from IntranetmainUserblock as it appears on the Staff Client
main page
|image118|

`IntranetNav <#IntranetNav>`__
''''''''''''''''''''''''''''''

Asks: Show the following HTML in the More menu at the top of each page
on the staff client (should be a list of links or blank)

`IntranetReportsHomeHTML <#IntranetReportsHomeHTML>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Show the following HTML in its own div on the bottom of the home
page of the reports module: HTML on Reports page

`IntranetSlipPrinterJS <#IntranetSlipPrinterJS>`__
''''''''''''''''''''''''''''''''''''''''''''''''''

Asks: Use the following JavaScript for printing slips.

Description:

-  The most logical use of this preference is in conjunction with the
   `jsPrintSetup <http://jsprintsetup.mozdev.org/>`__ Firefox add-on.
   Learn more about this preference and the add-on setup on the Koha
   wiki at
   http://wiki.koha-community.org/wiki/Setting_up_slip_printer_to_print_silently.

`intranetstylesheet <#intranetstylesheet>`__
''''''''''''''''''''''''''''''''''''''''''''

Asks: Use the CSS stylesheet \_\_\_ on all pages in the staff interface,
instead of the default css (used when leaving this field blank).

Description:

-  The Intranetstylesheet preference is a layout and design feature for
   the intranet or staff client. This preference allows a library to
   customize the appearance of the Staff Client. Enter just a filename,
   a full local path or a complete URL starting with http:// (if the
   file lives on a remote server). Please note that if you just enter a
   filename, the file should be in the css subdirectory for each active
   theme and language within the Koha templates directory. A full local
   path is expected to start from your HTTP document root.

`IntranetUserCSS <#IntranetUserCSS>`__
''''''''''''''''''''''''''''''''''''''

Asks: Include the following CSS on all pages in the staff client

`IntranetUserJS <#intranetuserjs>`__
''''''''''''''''''''''''''''''''''''

Asks: Include the following JavaScript on all pages in the staff
interface

Description:

-  This preference allows the administrator to enter JavaScript or
   JQuery that will be embedded across all pages of the Staff Client.
   Administrators may use this preference to customize some of the
   interactive sections of Koha, customizing the text for the login
   prompts, for example. Sample JQuery scripts used by Koha libraries
   can be found on the wiki:
   http://wiki.koha-community.org/wiki/JQuery_Library.

`SlipCSS <#SlipCSS>`__
''''''''''''''''''''''

Asks: Include the stylesheet at \_\_\_ on Issue and Reserve Slips.

    **Important**

    This should be a complete URL, starting with http://

Description:

-  If you would like to style your receipts or slips with a consistent
   set of fonts and colors you can use this preference to point Koha to
   a stylesheet specifically for your slips.

`staffClientBaseURL <#staffClientBaseURL>`__
''''''''''''''''''''''''''''''''''''''''''''

Asks: The staff client is located at http:// \_\_\_

`template <#template>`__
''''''''''''''''''''''''

Default: prog

Asks: Use the \_\_\_ theme on the staff interface.

Values:

-  prog

    **Important**

    Do not include a trailing slash in the URL this will break links
    created using this URL. (example: www.google.com not
    www.google.com/)

`XSLTDetailsDisplay <#XSLTDetailsDisplay>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: default

Asks: Display details in the staff client using XSLT stylesheet at
\_\_\_

Values:

-  leave empty to not use the XSLT stylesheet

   -  In previous versions of Koha this was the setting that read
      'normally'

      Detail display without XSLT stylesheets
      |image119|

-  enter "default" for the default one

   Detail display using XSLT stylesheets
   |image120|

-  put a path to define a XSLT file

   -  ex: /path/to/koha/and/your/stylesheet.xsl

   -  If in a multi-language system you can enter {langcode} in the path
      to tell Koha to look in the right language folder

      -  ex:
         /home/koha/src/koha-tmpl/intranet-tmpl/prog/{langcode}/xslt/intranetDetail.xsl

      -  ex. http://mykoha.org/{langcode}/stylesheet.xsl

-  put an URL for an external specific stylesheet

   -  ex: http://mykoha.org/stylesheet.xsl

Description:

-  XSLT stylesheets allow for the customization of the details shown on
   the screen when viewing a bib record. This preference will allow you
   either use the default look that comes with Koha or design your own
   stylesheet.
   
`XSLTListsDisplay <#XSLTListsDisplay>`__
''''''''''''''''''''''''''''''''''''''''

Default: default

Asks: Display lists in the staff client using XSLT stylesheet at
\_\_\_

Values:

-  leave empty to not use the XSLT stylesheet

   -  In previous versions of Koha this was the setting that read
      'normally'

-  enter "default" for the default one

-  put a path to define a XSLT file

   -  ex: /path/to/koha/and/your/stylesheet.xsl

   -  If in a multi-language system you can enter {langcode} in the path
      to tell Koha to look in the right language folder

      -  ex:
         /home/koha/src/koha-tmpl/intranet-tmpl/prog/{langcode}/xslt/intranetDetail.xsl

      -  ex. http://mykoha.org/{langcode}/stylesheet.xsl

-  put an URL for an external specific stylesheet

   -  ex: http://mykoha.org/stylesheet.xsl

Description:

-  XSLT stylesheets allow for the customization of the details shown on
   the screen when viewing a list. This preference will allow you
   either use the default look that comes with Koha or design your own
   stylesheet.

`XSLTResultsDisplay <#XSLTResultsDisplay>`__
''''''''''''''''''''''''''''''''''''''''''''

Default: default

Asks: Display results in the staff client using XSLT stylesheet at
\_\_\_

Values:

-  leave empty to not use the XSLT stylesheet

   -  In previous versions of Koha this was the setting that read
      'normally'

-  enter "default" for the default one

-  put a path to define a XSLT file

   -  ex: /path/to/koha/and/your/stylesheet.xsl

   -  If in a multi-language system you can enter {langcode} in the path
      to tell Koha to look in the right language folder

      -  ex:
         /home/koha/src/koha-tmpl/intranet-tmpl/prog/{langcode}/xslt/intranetDetail.xsl

      -  ex. http://mykoha.org/{langcode}/stylesheet.xsl

-  put an URL for an external specific stylesheet

   -  ex: http://mykoha.org/stylesheet.xsl

Description:

-  XSLT stylesheets allow for the customization of the details shown on
   the screen when viewing the search results. This preference will
   allow you either use the default look that comes with Koha or design
   your own stylesheet.

`Options <#staffoptsprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`AudioAlerts <#AudioAlerts>`__
''''''''''''''''''''''''''''''

Default: Don't enable

Asks: \_\_\_ audio alerts for events defined in the audio alerts section
of administration.

Values:

-  Don't enable

-  Enable

    **Important**

    This feature is not supported by all browsers. Requires an HTML5
    compliant browser.

`HidePatronName <#HidePatronName>`__
''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ the names of patrons that have items checked out or on hold
on detail pages or the "Place Hold" screen.

Values:

-  Don't show

-  Show

`intranetbookbag <#intranetbookbag>`__
''''''''''''''''''''''''''''''''''''''

Default: Show

Asks: \_\_\_ the cart option in the staff client.

Values:

-  Don't show

-  Show

`IntranetCatalogSearchPulldown <#IntranetCatalogSearchPulldown>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ a search field pulldown for 'Search the catalog' boxes.

Values:

-  Don't show

-  Show

`StaffDetailItemSelection <#StaffDetailItemSelection>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Enable

Asks: \_\_\_ item selection in record detail page.

Values:

-  Disable

-  Enable

Description:

-  This preference lets you choose to show (or not show) checkboxes to
   the left of every item in the holdings tab on the detail display of a
   record in the staff client. Showing these checkboxes allows the staff
   members to select multiple items to edit or delete at once.

   Items with the checkboxes enabled
   |image121|

`UseWYSIWYGinSystemPreferences <#UseWYSIWYGinSystemPreferences>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Don't show

Asks: \_\_\_ WYSIWYG editor when editing certain HTML system
preferences.

Values:

-  Don't show

-  ShowWYSIWYG Editor in Sys Prefs

Description:

-  This preference allows you to chang system preferences with HTML in
   them to WYSIWYG editors instead of plain text boxes.

`viewISBD <#viewISBD>`__
''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to view records in ISBD form on the staff client.

Values:

-  Allow

-  Don't allow

`viewLabeledMARC <#viewLabeledMARC>`__
''''''''''''''''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to view records in labeled MARC form on the staff
client.

Values:

-  Allow

-  Don't allow

`viewMARC <#viewMARC>`__
''''''''''''''''''''''''

Default: Allow

Asks: \_\_\_ staff to view records in plain MARC form on the staff
client.

Values:

-  Allow

-  Don't allow

`Tools <#toolsprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences > Tools

`Batch Item <#batchitemprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These preferences are in reference to the `Batch Item
Modification <#batchmodifyitems>`__ tool.

`MaxItemsForBatchDel <#MaxItemsForBatchDel>`__
''''''''''''''''''''''''''''''''''''''''

Default: 1000

Asks: Display up to \_\_\_ items in a single deletion batch.

Description:

-  In the `batch item delete tool <#batchdeleteitems>`__ this will
   prevent the display of more than the items you entered in this
   preference, but you will be able to delete more than the number you
   enter here.

`MaxItemsForBatchMod <#MaxItemsForBatchMod>`__
''''''''''''''''''''''''''''''''''''''''

Default: 1000

Asks: Process up to \_\_\_ items in a single modification batch.

Description:

-  In the `batch item modification
   tool <#batchmodifyitems>`__ this preference will prevent the editing
   of more than the number entered here.

`News <#newstoolprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^

`NewsAuthorDisplay <#NewsAuthorDisplay>`__
''''''''''''''''''''''''''''''''''''''''''

Default: not at all

Asks: Show the author for news items: \_\_\_

Values:

-  Both OPAC and staff client

-  Not at all

-  OPAC only

-  Staff client only

`Patron Cards <#patcardprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These preferences are in reference to the `Patron Card
Creator <#patroncardcreator>`__ tool.

`ImageLimit <#ImageLimit>`__
''''''''''''''''''''''''''''

Asks: Limit the number of creator images stored in the database to
\_\_\_ images.

`Reports <#reportsprefstools>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These preferences are in reference to the Reports module.

`NumSavedReports <#NumSavedReports>`__
''''''''''''''''''''''''''''''''''''''

Default: 20

Asks: By default, show \_\_\_ reports on the Saved Reports page.

`Upload <#uploadprefstools>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`UploadPurgeTemporaryFilesDays <#UploadPurgeTemporaryFilesDays>`__
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Default: blank

Asks: Automatically delete temporary uploads older than \_\_\_ days in
cleanup_database cron job.

`Web Services <#webserviceprefs>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Global System Preferences > Web
Services

`ILS-DI <#ilsdiprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^^

`ILS-DI <#ILS-DI>`__
''''''''''''''''''''

Default: Disable

Asks: \_\_\_ ILS-DI services for OPAC users

Values:

-  Disable

-  Enable

`ILS-DI:AuthorizedIPs <#ILS-DIAuthorized_IPs>`__
''''''''''''''''''''''''''''''''''''''''''''''''

Asks: \_\_\_ allowed IPs to use the ILS-DI services

`IdRef <#idrefprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^

`IdRef <#idref>`__
''''''''''''''''''

Default: Disable

Asks: \_\_\_ the IdRef webservice from the opac detail page. IdRef
allows to request authorities from the Sudoc database.

Values:

-  Disable

-  Enable

Description:

-  IdRef is a French service for Sudoc autorities. Using the `Sudoc
   database <http://www.sudoc.abes.fr/>`__, it allows to request /
   modify / add authorities. If a record comes from the Sudoc (so 009 is
   filled with an integer), at the OPAC you will see "Author: Idref" if
   a 7..$3 (unimarc author) if filled with a ppn. On clicking on the
   Idref link, a popup will display. IdRef link

   The Idref webservice is requested and all records (by roles) for this
   author will be displayedSudoc

   There is 1 line / record and 2 links at the end. 1 will request Koha
   (cgi-bin/koha/opac-search.pl?q=ident:003381862), the other one will
   redirect to the sudoc page (http://www.sudoc.fr/003381862).

-  **Important**

       Please note that this feature is available only for libraries
       using UNIMARC.

-  **Note**

       The French Sudoc database should not be confused with the US
       Superintendent of Documents (SuDocs) Classification Scheme.

`OAI-PMH <#oaiprefs>`__
^^^^^^^^^^^^^^^^^^^^^^^

`OAI-PMH <#OAI-PMH>`__
''''''''''''''''''''''

Default: Disable

Asks: \_\_\_ Koha's OAI-PMH server.

Values:

-  Disable

-  Enable

Description:

-  Once enabled you can visit http://YOURKOHACATALOG/cgi-bin/koha/oai.pl
   to see your file. For the Open Archives Initiative-Protocol for
   Metadata Harvesting (OAI-PMH) there are two groups of 'participants':
   Data Providers and Service Providers. Data Providers (open archives,
   repositories) provide free access to metadata, and may, but do not
   necessarily, offer free access to full texts or other resources.
   OAI-PMH provides an easy to implement, low barrier solution for Data
   Providers. Service Providers use the OAI interfaces of the Data
   Providers to harvest and store metadata. Note that this means that
   there are no live search requests to the Data Providers; rather,
   services are based on the harvested data via OAI-PMH. Koha at present
   can only act as a Data Provider. It can not harvest from other
   repositories. The biggest stumbling block to having Koha harvest from
   other repositories is that MARC is the only metadata format that Koha
   indexes natively. Visit
   http://www.oaforum.org/tutorial/english/page3.htm for diagrams of how
   OAI-PMH works.

Learn more about OAI-PMH at: http://www.openarchives.org/pmh/

`OAI-PMH:archiveID <#OAI-PMHarchiveID>`__
'''''''''''''''''''''''''''''''''''''''''

Default: KOHA-OAI-TEST

Asks: Identify records at this site with the prefix \_\_\_ :

`OAI-PMH:AutoUpdateSets <#OAI-PMHAutoUpdateSets>`__
'''''''''''''''''''''''''''''''''''''''''''''''''''

Default: Disable

Asks: \_\_\_ automatic update of OAI-PMH sets when a bibliographic
record is created or updated.

Values:

-  Disable

-  Enable

`OAI-PMH:ConfFile <#OAI-PMHConfFile>`__
'''''''''''''''''''''''''''''''''''''''

If this preference is left empty, Koha's OAI Server operates in normal
mode, otherwise it operates in extended mode. In extended mode, it's
possible to parameter other formats than marcxml or Dublin Core.
OAI-PMH:ConfFile specify a YAML configuration file which list available
metadata formats and XSL file used to create them from marcxml records.

For more information, see the `sample conf file <#oaiconfsample>`__ in
the appendix.

`OAI-PMH:DeletedRecord <#OAI-PMHDeletedRecord>`__
'''''''''''''''''''''''''''''''''''''''''''''''''

Default: will never be emptied or truncated (persistent)

Asks: Koha's deletedbiblio table \_\_\_

Values:

-  will never have any data in it (no)

-  will never be emptied or truncated (persistent)

-  might be emptied or truncated at some point (transient)

`OAI-PMH:MaxCount <#OAI-PMHMaxCount>`__
'''''''''''''''''''''''''''''''''''''''

Default: 50

Asks: Only return \_\_\_ records at a time in response to a ListRecords
or ListIdentifiers query.

Description:

-  This is the maximum number of records that would be returned based on
   ListRecord or ListIdentifier queries from harvesters. ListRecords
   harvest the entire records while the ListIdentifier is an abbreviated
   form of ListRecords, retrieving only headers rather than records.

`Reporting <#reportingservice>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`SvcMaxReportRows <#SvcMaxReportRows>`__
''''''''''''''''''''''''''''''''''''''''

Default: 10

Asks: Only return \_\_\_ rows of a report requested via the reports web
service.

Description:

-  This value will be used to limit the number of results returned by
   `public reports <#publicreport>`__.

`Basic Parameters <#basicparams>`__
-----------------------------------

*Get there:* More > Administration

    **Important**

    Configure all 'parameters' in the order they appear.

`Libraries & Groups <#libsgroups>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When setting up your Koha system you will want to add information for
every library that will be sharing your system. This data is used in
several areas of Koha.

-  *Get there:* More > Administration > Basic Parameters > Libraries and
   Groups

When visiting this page you are presented with a list of the libraries
and groups that have already been added to the system.

Library List
|image122|

Group Lists
|image123|

`Adding a Library <#addingalibrary>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To add a new library:

-  Click 'New Library'

-  The top of the form asks for some basics about the library

   Basic Library Info
   |image124|

   -  The library code should not contain any spaces and be 10 or fewer
      characters. This code will be used as a unique identifier in the
      database.

   -  The name will be displayed on the OPAC wherever the library name
      displays to the public and should be a name that makes sense to
      your patrons.

   -  If you have `groups <#addinglibgroup>`__ set up you can choose
      what group this library belongs to after entering in the code and
      name

-  Next you can enter basic contact info about the branch

   Library Contact Info
   |image125|

   -  The address and contact fields can be used to make notices custom
      for each library

   -  The email address field is not required, but it should be filled
      for every library in your system

      -  **Important**

             Be sure to enter a library email address to make sure that
             notices are sent to and from the right address

   -  If you'd like you can enter a different 'Reply-To' email address.
      This is the email address that all replies will go to.

      -  **Note**

             If you do not fill in this value Koha will use the address
             in the `ReplytoDefault <#ReplytoDefault>`__ preference

   -  If you'd like you can also enter a different 'Return-Path' email
      address. This is the email address that all bounced messages will
      go to.

      -  **Note**

             If you do not fill in this value Koha will use the address
             in the `ReturnpathDefault <#ReturnpathDefault>`__
             preference

   -  If the URL field is populated then the library name will be linked
      in the holdings table on the OPAC

      Linked Library Name
      |image126|

   -  The OPAC Info box is for you to put information about the library
      that will appear in the OPAC when the branch name is moused over
      in the holdings table

      OPAC Info
      |image127|

   -  IP Address does not have be filled in unless you plan on limiting
      access to your staff client to a specific IP Address

      -  **Important**

             An IP address is required if you have enabled
             `AutoLocation <#AutoLocation>`__

   -  Finally, if you have any notes you can put them here. These will
      not show in the OPAC

    **Note**

    Of the fields listed, only 'Library code' and 'Name' are required

`Editing/Deleting a Library <#editingalibrary>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You will be unable to delete any library that has patrons or items
attached to it.

Staff will be presented with a warning when trying to delete a library
that is being used
|image128|

Each library will have an 'Edit' link to the right of it. Click this
link to edit/alter details associated with the library in question.

    **Important**

    You will be unable to edit the 'Library code'

`Adding a group <#addinglibgroup>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To add a Search Domain or Library Property Group click the 'New Group'
button at the top of the screen

Add group form
|image129|

Give the group a 'Category type; of 'searchdomain' and if you would like
the group to show up in the library pull down at the top of the OPAC
(with
`OpacAddMastheadLibraryPulldown <#OpacAddMastheadLibraryPulldown>`__ set
to 'Add') and on the advanced search page you can check the 'Show in
search pulldown' box.

Of the fields on the group form, 'Category code', 'Name', and 'Category
type' are the only required fields

`Search Domain Groups <#searchdomaingroups>`__
''''''''''''''''''''''''''''''''''''''''''''''

Search Domain Groups allow you to search a group of libraries at the
same time instead of searching just one library or all libraries.

Search Domain Groups
|image130|

To see Search Domain Groups in action visit the staff client advanced
search page in your Koha system:

Library group search on staff client
|image131|

`Library Property Groups <#libpropertygroups>`__
''''''''''''''''''''''''''''''''''''''''''''''''

You can assign specific categories to your libraries by adding groups
for them

Library Property Groups
|image132|

Properties are then applied to libraries via the add or edit library
form

Groups on the Add/Modify library form
|image133|

`Item Types <#itemtypeadmin>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Koha allows you to organize your collection by item types and collection
codes.

-  *Get there:* More > Administration > Basic Parameters > Item Types

Item types typically refer to the material type (book, cd, dvd, etc),
but can be used in any way that works for your library.

Item Types
|image134|

`Adding Item Types <#additemtype>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To add a new item type, simply click the 'New Item Type' button at the
top of the Item Types page.

New Item Type
|image135|

-  In the 'Item Type' field, enter a short code for your item type

-  The description is the plain text definition of the item type (for
   those with multiple languages installed you can translate the item
   type description in to all of those languages using the 'Translate in
   to other languages' link)

-  Item types and can grouped together for searching at the same time.
   For example you can put DVDs and Bluray in to a group called Movie
   and then they can be searched together. These groups are defined in
   the ITEMTYPECAT authorized value.

-  You can choose to have an image associated with your item type

   -  You can choose from a series of image collections

   -  You can link to a remote image

   -  Or you can just have no image associated with the item type

   -  **Important**

          To have your item type images appear in the OPAC you need to
          set `noItemTypeImages <#noItemTypeImages>`__ to 'Show'

      -  *Get there:*\ More > Administration > Global System Preferences
         > `Admin <#adminprefs>`__

-  For items that you are suppressing from the OPAC you can hide their
   item type from being searched in the OPAC

-  For items that do not circulate, check the 'Not for loan' options

   -  Items marked 'Not for loan' will appear in the catalog, but cannot
      be checked out to patrons

-  For items that you charge a rental fee for, enter the total fee you
   charge in the 'Rental charge' field

   -  **Important**

          Do not enter symbols in this field, only numbers and decimal
          points (ex. $5.00 should be entered as 5 or 5.00)

   -  This will charge the patron on checkout

-  If you would like a message or alert to appear when items of this
   type are checked in you can enter that in the 'Checkin message' box

   Checkin message setup
   |image136|

   -  The Checkin message type can be a Message or an Alert. The only
      difference between these two is the styling. By default a Message
      is blue

      Checkin Message
      |image137|

      and an Alert is yellow.

      Checkin Alert
      |image138|

-  Some SIP devices need you to use a SIP-specific media type instead of
   Koha's item type (usually lockers and sorters need this media type),
   if you use a device like this you'll want to enter the SIP media
   type.

-  When finished, click 'Save Changes'

   -  **Note**

          All fields, with the exception of the 'Item Type' will be
          editable from the Item Types list

-  Your new item type will now appear on the list

   New DVD Item Type
   |image139|

`Editing Item Types <#edititemtype>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Each item type has an Edit button beside it. To edit an item simply
click the 'Edit' link.

    **Important**

    You will not be able to edit the code you assigned as the 'Item
    Type' but you will be able to edit the description for the item.

`Deleting Item Types <#deleteitemtype>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Each item has a Delete button beside it. To delete an item, simply click
the 'Delete' link.

    **Important**

    You will not be able to delete item types that are being used by
    items within your system.

Warning when you try to delete an item that is in use
|image140|

`Authorized Values <#authorizedvalues>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Authorized values can be used in several areas of Koha. One reason you
would add an authorized value category would be to control the values
that can be entered into MARC fields by catalogers.

-  *Get there:* More > Administration > Basic Parameters > Authorized
   Values

`Existing Values <#existingauthvalues>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Koha installs with pre-defined values that your library is likely to
use, for instance 'Lost'.

-  Asort1

   -  Used for acquisitions statistical purposes

-  Asort2

   -  Used for acquisitions statistical purposes

-  BOR\_NOTES

   -  Values for custom patron messages that appear on the circulation
      screen and the OPAC. The value in the Description field should be
      the message text and is limited to 200 characters.

      Borrower messages
      |image141|

-  Bsort1

   -  Values that can be entered to fill in the patron's sort 1 field

-  Bsort2

   -  Values that can be entered to fill in the patron's sort 2 field

-  CART

   -  Is the shelving cart location, used by
      `InProcessingToShelvingCart <#InProcessingToShelvingCart>`__ and
      `ReturnToShelvingCart <#ReturnToShelvingCart>`__

-  CCODE

   -  Collection codes (appears when cataloging and working with items)

-  DAMAGED

   -  Descriptions for items marked as damaged (appears when cataloging
      and working with items)

-  DEPARTMENT

   -  Departments are required by and will be used in the `Course
      Reserves <#coursereserves>`__ module

-  HINGS\_AS

   -  General Holdings: Acquisition Status Designator :: This data
      element specifies acquisition status for the unit at the time of
      the holdings report.

-  HINGS\_C

   -  General Holdings: Completeness Designator

-  HINGS\_PF

   -  Physical Form Designators

-  HINGS\_RD

   -  General Holdings: Retention Designator :: This data element
      specifies the retention policy for the unit at the time of the
      holdings report.

-  HINGS\_UT

   -  General Holdings: Type of Unit Designator

-  LOC

   -  Shelving location (usually appears when adding or editing an item)

-  LOST

   -  Descriptions for the items marked as lost (appears when adding or
      editing an item)

   -  **Important**

          Values given to lost statuses should be numeric and not
          alphabetical in order for statuses to appear properly

-  MANUAL\_INV

   -  Values for manual invoicing types

   -  **Important**

          The value set as the Authorized Value for the MANUAL\_INV
          authorized value category will appear as the Description and
          the Authorized Value Description will be used as the amount.
          Enter monetary amounts in the description without currency
          symbols.

-  NOT\_LOAN

   -  Reasons why a title is not for loan

   -  **Important**

          Values given to lost statuses should be numeric and not
          alphabetical in order for statuses to appear properly

   -  **Note**

          Negative number values will still allow holds (use for on
          order statuses for example) where as positive numbers will not
          allow holds or checkouts

-  ORDER\_CANCELLATION\_REASON

   -  Reasons why an order might have been cancelled

-  PROC

   -  The location to be used for
      `NewItemsDefaultLocation <#NewItemsDefaultLocation>`__ (change
      description as desired), also the location expected by
      `InProcessingToShelvingCart <#InProcessingToShelvingCart>`__.

-  REPORT\_GROUP

   -  A way to sort and filter your reports, the default values in this
      category include the Koha modules (Accounts, Acquitisions,
      Catalog, Circulation, Patrons)

      Report Groups
      |image142|

-  REPORT\_SUBGROUP

   -  Can be used to further sort and filter your reports. This category
      is empty by default. Values here need to include the authorized
      value code from REPORT\_GROUP in the Description (OPAC) field to
      link the subgroup to the appropriate group.

      Report Subgroups
      |image143|

-  RESTRICTED

   -  Restricted status of an item

-  ROADTYPE

   -  Road types to be used in patron addresses

-  SIP\_MEDIA\_TYPE

   -  Used when `creating <#additemtype>`__ or
      `editing <#edititemtype>`__ an item type to assign a SIP specific
      media type for devices like lockers and sorters.

-  SUGGEST

   -  List of patron suggestion reject or accept reasons (appears when
      managing suggestions)

-  WITHDRAWN

   -  Description of a withdrawn item (appears when adding or editing an
      item)

-  YES\_NO

   -  A generic authorized value field that can be used anywhere you
      need a simple yes/no pull down menu.

`Add new Authorized Value Category <#newauthvalcat>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In addition to the existing categories that come by default with Koha,
librarians can add their own authorized value categories to control data
that is entered into the system. To add a new category:

-  Click 'New Category'

   New Authorized Category form
   |image144|

-  Limit your Category to 10 characters (something short to make it
   clear what the category is for)

   -  **Important**

          Category cannot have spaces or special characters other than
          underscores and hyphens in it.

-  When adding a new category you're asked to create at least one
   authorized value

   -  Enter a code for your Authorized Value into the 'Authorized value'
      field

      -  **Important**

             Authorized value is limited to 80 characters and cannot
             have spaces or special characters other than underscores
             and hyphens in it.

   -  Use the Description field for the actual value that will be
      displayed. If you want something different to show in the OPAC,
      enter a 'Description (OPAC)'

   -  If you would like to limit this authorized value category to only
      specific libraries you can choose them from the 'Branches
      limitation' menu. To have it show for all libraries just choose
      'All branches' at the top of the list.

   -  If you have
      `StaffAuthorisedValueImages <#StaffAuthorisedValueImages>`__
      and/or `AuthorisedValueImages <#AuthorisedValueImages>`__ set to
      show images for authorized values you can choose the image under
      'Choose an icon'

-  Click 'Save'

-  Your new category and value will appear on the list of Authorized
   Values

   Custom Authorized Value on list of values
   |image145|

`Add new Authorized Value <#newauthval>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

New authorized values can be added to any existing or new category. To
add a value:

-  Click 'New authorized value for ...'

   New Authorized Value form
   |image146|

-  Enter a code for your Authorized Value into the 'Authorized value'
   field

   -  **Important**

          Authorized value is limited to 80 characters and cannot have
          spaces or special characters other than underscores and
          hyphens in it.

-  Use the Description field for the actual value that will be
   displayed. If you want something different to show in the OPAC, enter
   a 'Description (OPAC)'

-  If you would like to limit this authorized value category to only
   specific libraries you can choose them from the 'Branches limitation'
   menu. To have it show for all libraries just choose 'All branches' at
   the top of the list.

-  If you have
   `StaffAuthorisedValueImages <#StaffAuthorisedValueImages>`__ and/or
   `AuthorisedValueImages <#AuthorisedValueImages>`__ set to show images
   for authorized values you can choose the image under 'Choose an icon'

-  Click 'Save'

-  The new value will appear in the list along with existing values

   List of authorized values in MARC504 category
   |image147|

`Patrons & Circulation <#patscirc>`__
-------------------------------------

Settings for controlling circulation and patron information.

`Patron Categories <#patcats>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Patron categories allow you to organize your patrons into different
roles, age groups, and patron types.

-  *Get there:* More > Administration > Patrons & Circulation > Patron
   Categories

Patron category list
|image148|

Patrons are assigned to one of six main categories:

-  Adult

   -  Most common patron type, usually used for a general 'Patron'
      category.

-  Child

   -  Children patrons can have a guardian to be attached to them.

-  Staff

   -  Librarians (and library workers) should be assigned the staff
      category so that you can `set their
      permissions <#patronpermissions>`__ and give them access to the
      staff client.

-  Organizational

   -  Organizational patrons are organizations. Organizations can be
      used as guarantors for Professional patrons.

-  Professional

   -  Professional patrons can be linked to Organizational patrons

-  Statistical

   -  This patron type is used strictly for statistical purposes, such
      as in house use of items.

`Adding a patron category <#addingpatroncat>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To add a new patron category click 'New Category' at the top of the page

New patron category form
|image149|

-  The 'Category Code' is an identifier for your new code.

   -  **Important**

          The category code is limited to 10 characters (numbers and
          letters)

   -  **Important**

          This field is required in order to save your patron category.
          If left blank you will be presented with an error.

          Missing fields error
          |image150|

-  Enter a plain text version of the category in the 'Description'
   field.

   -  **Important**

          This field is required in order to save your patron category.
          If left blank you will be presented with an error.

          Missing fields error
          |image151|

-  Enrollment period (in months) should be filled in if you have a
   limited enrollment period for your patrons (eg. Student cards expire
   after 9 months or until a specific date)

   -  **Important**

          You cannot enter both a month limit and a date until. Choose
          to enter either one or the other.

   -  **Important**

          This field is required in order to save your patron category.
          If left blank you will be presented with an error.

          Missing fields error
          |image152|

-  Some patron categories can have a minimum age (in years) requirement
   associated with them, enter this age in the 'Age required'

   -  **Important**

          This value will only be checked if
          `BorrowerMandatoryField <#BorrowerMandatoryField>`__ defines
          the dateofbirth as a required field on the patron record

-  Patron categories can also have a maximum age (in years) associated
   with them (such as children), enter this age in the 'Upperage limit'

   -  **Important**

          This value will only be checked if
          `BorrowerMandatoryField <#BorrowerMandatoryField>`__ defines
          the dateofbirth as a required field on the patron record

-  If you charge a membership fee for your patrons (such as those who
   live in another region) you can enter that in the 'Enrollment fee'
   field.

   -  **Important**

          Only enter numbers and decimals in this field

   -  **Note**

          Depending on your value for the
          `FeeOnChangePatronCategory <#FeeOnChangePatronCategory>`__
          preference this fee will be charged on patron renewal as well
          as when they are first enrolled.

-  If you want your patron to receive overdue notices, set the 'Overdue
   notice required' to 'Yes'

-  You can decide on a patron category basis if lost items are shown in
   the staff client by making a choice from the 'Lost items in staff
   client' pull down

   Choose a value for 'Hide Lost Items'
   |image153|

   -  **Important**

          Note that this is only applicable in the staff client, so
          changing this value on patron categories who do not have
          access to the staff client won't make any difference

-  If you charge patrons for placing holds on items, enter the fee
   amount in the 'Hold fee' field.

   -  **Important**

          Only enter numbers and decimals in this field

-  In the 'Category type' field choose one of the six main parent
   categories

   Six main patron categories
   |image154|

   -  **Important**

          This field is required in order to save your patron category.
          If left blank you will be presented with an error.

          Missing fields error
          |image155|

-  The Branch Limitations let you limit this patron category to only
   some branches in your library system. Select 'All branches' if you
   would like any library to be able to use this category.

-  You can decide if this patron category is blocked from performing
   actions in the OPAC if their card is expired using the next option.
   By default it will follow the rule set in the
   `BlockExpiredPatronOpacActions <#BlockExpiredPatronOpacActions>`__
   preferenceBlock expired patrons

-  Next you can choose the default privacy settings for this patron
   category. This setting can be edited by the patron via the OPAC if
   you allow it with the `OPACPrivacy <#OPACPrivacy>`__ system
   preference.Default privacy

-  Finally you can assign advanced messaging preferences by default to a
   patron category

   -  **Important**

          Requires that you have
          `EnhancedMessagingPreferences <#EnhancedMessagingPreferences>`__
          enabled

   -  These defaults will be applied to new patrons that are added to
      the system. They will not edit the preferences of the existing
      patrons. Also, these can be changed for individual patrons, this
      setting is just a default to make it easier to set up messages for
      an entire category.

      -  **Note**

             After setting the default for the patron category you can
             force those changes to all existing patrons by running the
             *borrowers-force-messaging-defaults* script found in the
             *misc/maintenance* folder. Ask your system administrator
             for assistance with this script.

`Circulation and Fine Rules <#circfinerules>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

These rules define how your items are circulated, how/when fines are
calculated and how holds are handled.

-  *Get there:* More > Administration > Patrons & Circulation >
   Circulation and fines rules

The rules are applied from most specific to less specific, using the
first found in this order:

-  same library, same patron type, same item type

-  same library, same patron type, all item type

-  same library, all patron types, same item type

-  same library, all patron types, all item types

-  default (all libraries), same patron type, same item type

-  default (all libraries), same patron type, all item types

-  default (all libraries), all patron types, same item type

-  default (all libraries), all patron types, all item types

The `CircControl <#CircControl>`__ and
`HomeOrHoldingBranch <#HomeOrHoldingBranch>`__ also come in to play when
figuring out which circulation rule to follow.

-  If CircControl is set to "the library you are logged in at" circ
   rules will be selected based on the library you are logged in at

-  If CircControl is set to "the library the patron is from" circ rules
   will be selected based on the patron's library

-  If CircControl is set to "the library the item is from" circ rules
   will be selected based on the item's library where
   HomeOrHoldingBranch chooses if item's home library is used or holding
   library is used.

-  If `IndependentBranches <#IndependentBranches>`__ is set to 'Prevent'
   then the value of HomeOrHoldingBranch is used in figuring out if the
   item can be checked out. If the item's home library does not match
   the logged in library, the item cannot be checked out unless you are
   a `superlibrarian <#patronpermsdefined>`__.

    **Note**

    If you are a single library system choose your branch name before
    creating rules (sometimes having only rules for the 'all libraries'
    option can cause issues with holds)

    **Important**

    At the very least you will need to set a default circulation rule.
    This rule should be set for all item types, all libraries and all
    patron categories. That will catch all instances that do not match a
    specific rule. When checking out if you do not have a rule for all
    libraries, all item types and all patron types then you may see
    patrons getting blocked from placing holds. You will also want a
    rule for your specific library set for all item types and all patron
    types to avoid this holds issue. Koha needs to know what rule to
    fall back on.

`Default Circulation Rules <#defaultcircrules>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Using the issuing rules matrix you can define rules that depend on
patron/item type combos. To set your rules, choose a library from the
pull down (or 'all libraries' if you want to apply these rules to all
branches):

Libraries to apply the rules to
|image156|

From the matrix you can choose any combination of patron categories and
item types to apply the rules to

Setting issuing rules for your libraries
|image157|

-  First choose which patron category you'd like the rule to be applied
   to. If you leave this to 'All' it will apply to all patron categories

-  Choose the 'Item type' you would like this rule to apply to. If you
   leave this to 'All' it will apply to all item types

-  Limit the number of items a patron can have checked out at the same
   time by entering a number in the 'Current checkouts allowed' field

-  If you're allowing `OnSiteCheckouts <#OnSiteCheckouts>`__ then you
   may also want to set a limit on the number of items patron's can have
   onsite.

   -  **Note**

          This setting also depends on the
          `ConsiderOnSiteCheckoutsAsNormalCheckouts <#ConsiderOnSiteCheckoutsAsNormalCheckouts>`__
          preference

-  Define the period of time an item can be checked out to a patron by
   entering the number of units (days or hours) in the 'Loan period'
   box.

-  Choose which unit of time, Days or Hours, that the loan period and
   fines will be calculated in in the 'Unit' column

-  You can also define a hard due date for a specific patron category
   and item type. A hard due date ignores your usual circulation rules
   and makes it so that all items of the type defined are due on, before
   or after the date you specify.

-  'Fine amount' should have the amount you would like to charge for
   overdue items

   -  **Important**

          Enter only numbers and decimal points (no currency symbols).

-  Enter the 'Fine charging interval' in the unit you set (ex. charge
   fines every 1 day, or every 2 hours)

-  'When to charge' is most handy in libraries that have a fine charging
   interval of more than 1 day.

   -  End of interval

      -  Given a grace period of 2 days and a fine interval of 7 days,
         the first fine will appear 7 days after the due date, it will
         always take one fine interval (7 days), before the first fine
         is charged

   -  Start of interval

      -  Given a grace period of 2 days and a fine interval of 7 days,
         the first fine will appear 2 days after the due date and the
         second fine 7 days after the due date.

-  The 'Fine grace period' is the period of time an item can be overdue
   before you start charging fines.

   -  **Important**

          This can only be set for the Day unit, not in Hours

-  The 'Overdue fines cap' is the maximum fine for this patron and item
   combination

   -  **Important**

          If this field is left blank then Koha will not put a limit on
          the fines this item will accrue. A maximum fine amount can be
          set using the `MaxFine <#MaxFine>`__ system preference.

-  If you would like to prevent overcharging patrons for a lost items,
   you can check the box under 'Cap fine at replacement price.' This
   will prevent the patron's fines from going above the replacement
   price on the item.

   -  **Note**

          If the 'Overdue fines cap' is also set, the fine will be the
          lesser of the two, if both apply to the given overdue
          checkout.

-  If your library 'fines' patrons by suspending their account you can
   enter the number of days their fine should be suspended in the
   'Suspension in days' field

   -  **Important**

          This can only be set for the Day unit, not in Hours

-  You can also define the maximum number of days a patron will be
   suspended in the 'Max suspension duration' setting

-  Next decide if the patron can renew this item type and if so, enter
   how many times they can renew it in the 'Renewals allowed' box

-  If you're allowing renewals you can control how long the renewal loan
   period will be (in the units you have chosen) in the 'Renewal period'
   box

-  If you're allowing renewals you can control how soon before the due
   date patrons can renew their materials with the 'No renewals before'
   box.

   -  Items can be renewed at any time if this value is left blank.
      Otherwise items can only be renewed if the item is due after the
      number in units (days/hours) entered in this box.

   -  To control this value on a more granular level please set the
      `NoRenewalBeforePrecision <#NoRenewalBeforePrecision>`__
      preference.

-  You can enable automatic renewals for certain items/patrons if you'd
   like. This will renew automatically following your circulation rules
   unless there is a hold on the item

   -  **Important**

          You will need to enable the `automatic renewal cron
          job <#autorenewcron>`__ for this to work.

   -  **Important**

          This feature needs to have the "no renewal before" column
          filled in or it will auto renew everyday after the due date

-  If the patron can place holds on this item type, enter the total
   numbers of items (of this type) that can be put on hold in the 'Holds
   allowed' field

-  Next you can decide if this patron/item combo are allowed to place
   holds on items that are on the shelf (or available in the library) or
   not. If you choose 'no' then items can only be placed on hold if
   checked out

-  You can also decide if patrons are allowed to place item specific
   holds on the item type in question. The options are:

   -  Allow: Will allow patrons the option to choose next available or
      item specific

   -  Don't allow: Will only allow patrons to choose next available

   -  Force: Will only allow patrons to choose an specific item

-  Finally, if you charge a `rental fee <#rentalcharge>`__ for the item
   type and want to give a specific patron type a discount on that fee,
   enter the percentage discount (without the % symbol) in the 'Rental
   Discount' field

When finished, click 'Add' to save your changes. To modify a rule,
simply click the 'Edit' link to the right of the fule and edit the
values that appear filled in at the bottom of the form.

Edit circ and fine rule
|image158|

If you would like to delete your rule, click the 'Delete' link to the
right of the rule.

To save time you can clone rules from one library to another by choosing
the clone option above the rules matrix.

Circulation & Fine Rules Clone Tool
|image159|

After choosing to clone you will be presented with a confirmation
message.

Circulation & Fine Rules Successfully Cloned Message
|image160|

`Default Checkouts and Hold Policy <#defaultcheckoutpolicy>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can set a default maximum number of checkouts and hold policy that
will be used if none is defined below for a particular item type or
category. This is the fall back rule for defaults.

Default Checkouts and Hold Policy
|image161|

From this menu you can set a default to apply to all item types and
patrons in the library if no other option is set in the forms below.

-  In 'Total current checkouts allowed' enter the total number of items
   patrons can have checked out at one time

-  In 'Total current on-site checkouts allowed' enter the total number
   of items patrons can have checked out on site at a time
   (`OnSiteCheckouts <#OnSiteCheckouts>`__ needs to be set to 'Enable')

-  Control where patrons can place holds from using the 'Hold Policy'
   menu

   -  From Any Library: Patrons from any library may put this item on
      hold. (default if none is defined)

   -  From Home Library: Only patrons from the item's home library may
      put this book on hold.

   -  No Holds Allowed: No patron may put this book on hold.

-  Control if there is a limit to filling a hold based on the item's
   library

   -  any library

   -  item's home library

   -  item's holding library

   -  **Note**

          The patron's home library should not affect whether a patron
          can place the hold, instead the hold will only be fillable
          when an item matching the pickup location becomes available.

-  Control where the item returns to once it is checked in

   -  Item returns home

   -  Item returns to issuing branch

   -  Item floats

      -  When an item floats it stays where it was checked in and does
         not ever return 'home'

-  Once your policy is set, you can unset it by clicking the 'Unset'
   link to the right of the rule

`Checkouts Per Patron <#checkoutperpatron>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For this library, you can specify the maximum number of loans that a
patron of a given category can make, regardless of the item type.

Set default checkouts per patron category
|image162|

    **Note**

    If the total amount loanable for a given patron category is left
    blank, no limit applies, except possibly for a limit you define for
    a specific item type.

For example, if you have a rule in the matrix that says Board patrons
are allowed 10 books and 5 DVDs but you want to make it so that Board
patrons only have a total of 12 things checked out at once. If you enter
12 here and the patron has 10 books out already they will only be
allowed 2 DVDs to equal the 12 total they're allowed.

`Item Hold Policies <#holdpolicies>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For this library, you can edit hold and return policies for a given item
type, regardless of the patron's category.

Hold policies per item type
|image163|

The various Hold Policies have the following effects:

-  From Any Library: Patrons from any library may put this item on hold.
   (default if none is defined)

-  From Home Library: Only patrons from the item's home library may put
   this book on hold.

-  No Holds Allowed: No patron may put this book on hold.

    **Important**

    Note that if the system preference
    `AllowHoldPolicyOverride <#AllowHoldPolicyOverride>`__ set to
    'allow', these policies can be overridden by your circulation staff.

    **Important**

    These policies are based on the patron's home branch, not the branch
    that the reserving staff member is from.

Control if there is a limit to filling a hold based on the item's
library

-  any library

-  item's home library

-  item's holding library

-  **Note**

       The patron's home library should not affect whether a patron can
       place the hold, instead the hold will only be fillable when an
       item matching the pickup location becomes available.

The various Return Policies have the following effects:

-  Item returns home: The item will prompt the librarian to transfer the
   item to its home library

   -  **Important**

          If the `AutomaticItemReturn <#AutomaticItemReturn>`__
          preference is set to automatically transfer the items home,
          then a prompt will not appear

-  Item returns to issuing branch: The item will prompt the librarian to
   transfer the item back to the library where it was checked out

   -  **Important**

          If the `AutomaticItemReturn <#AutomaticItemReturn>`__
          preference is set to automatically transfer the items home,
          then a prompt will not appear

-  Item floats: The item will not be transferred from the branch it was
   checked in at, instead it will remain there until transferred
   manually or checked in at another branch

For example you might allow holds at your libraries but not what New
items or DVDs to be placed on hold by other branches so you can set the
'Hold policy' to 'From home library' so that those items can only be
placed on hold if the items' owning library and the patron's home
library are the same. You can also block holds completely on specific
item types from this form. This is also how you can set up floating item
types and types that remain with their home library.

`Patron Attribute Types <#patronattributetypes>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Patron attributes can be used to define custom fields to associate with
your patron records. In order to enable the use of custom fields you
need to set the `ExtendedPatronAttributes <#ExtendedPatronAttributes>`__
system preference.

-  *Get there:* More > Administration > Patrons & Circulation > Patron
   attribute types

A common use for this field would be for a student ID number or a
Driver's license number.

List of Patron Attributes
|image164|

`Adding Patron Attributes <#addpatattributes>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To add a new Patron Attribute Type, click the 'New Patron Attribute
Type' button at the top of the page

Add Patron Attribute Type form
|image165|

-  In the 'Patron attribute type code', enter a short code to identify
   this field

   -  **Important**

          This field is limited to 10 characters (numbers and letters
          only)

   -  **Important**

          This setting cannot be changed after an attribute is defined

-  In the 'Description' field, enter a longer (plain text) explanation
   of what this field will contain

-  Check the box next to 'Repeatable' to let a patron record have
   multiple values of this attribute.

   -  **Important**

          This setting cannot be changed after an attribute is defined

-  If 'Unique identifier' is checked, the attribute will be a unique
   identifier which means, if a value is given to a patron record, the
   same value cannot be given to a different record.

   -  Unique attributes can be used as match points on the `patron
      import tool <#patronimport>`__

   -  **Important**

          This setting cannot be changed after an attribute is defined

-  Check 'Allow password' to make it possible to associate a password
   with this attribute.

-  Check 'Display in OPAC' to display this attribute on a patron's
   details page in the OPAC.

-  Check 'Searchable' to make this attribute searchable in the staff
   patron search.

-  Check 'Display in check-out' to make this attribute visible in the
   patron's short detail display on the left of the checkout screen and
   other patron pages

   Show attribute in patron detail on the left
   |image166|

-  Authorized value category; if one is selected, the patron record
   input page will only allow values to be chosen from the authorized
   value list.

   -  You will first need to add an authorized value list for it to
      appear in this menu

      -  *Get there:*\ More > Administration > Basic Parameters >
         `Authorized Values <#authorizedvalues>`__

   -  **Important**

          an authorized value list is not enforced during batch patron
          import.

-  If you would like this attribute to only be used by specific branches
   you can choose those branches from the 'Branches limitation' list.
   Choose 'All branches' to show it for all libraries.

   -  **Important**

          Note that items with locations already set on them will not be
          altered. The branch limitation only limits the choosing of an
          authorized value based on the home branch of the current staff
          login. All authorized values for item records (LOC, LOST,
          CCODE, etc) will show in the OPAC for all patrons.

-  If you'd like to only show this attribute on patrons of one type
   choose that patron type from the 'Category' pull down

-  If you have a lot of attributes it might be handy to group them so
   that you can easily find them for editing. If you create an
   `Authorized Value <#authorizedvalues>`__ for PA\_CLASS it will show
   in the 'Class' pull down and you can then change your attributes page
   to have sections of attributes

   Patron Attributes Sorted
   |image167|

-  Click Save to save your new attribute

Once added your attribute will appear on the list of attributes and also
on the patron record add/edit form

Patron Attributes list on the Patron add/edit form
|image168|

If you have set up classes for organizing attributes they will appear
that way on the add/edit patron form

Grouped Attributes
|image169|

`Editing/Deleting Patron Attributes <#editpatattributes>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Each patron attribute has an edit and a delete link beside it on the
list of attributes.

Some fields in the attribute will not be editable once created:

-  Patron attribute type code

-  Repeatable

-  Unique identifier

You will be unable to delete an attribute if it's in use.

Warning when trying to delete an attribute that is in use
|image170|

`Library Transfer Limits <#libtransferlimits>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Limit the ability to transfer items between libraries based on the
library sending, the library receiving, and the collection code
involved.

-  *Get there:* More > Administration > Patrons & Circulation > Library
   Transfer Limits

These rules only go into effect if the preference
`UseBranchTransferLimits <#UseBranchTransferLimits>`__ is set to
'enforce'.

Before you begin you will want to choose which library you are setting
these limits for.

Choose the library you're setting limits for
|image171|

Transfer limits are set based on the collections codes you have applied
via the `Authorized Value <#authorizedvalues>`__ administration area.

Collection Code values assigned in the Authorized Value area
|image172|

Collection codes will appear as tabs above the checkboxes:

Collection Code tabs
|image173|

Check the boxes for the libraries that you accept checkins from for the
item type you have selected at the top (in the example below - FIC)

Example transfer limits set up
|image174|

In the above example, Centerville library will allow patrons to return
items from all libraries except Liberty and Franklin to their branch.

`Transport cost matrix <#transportcostmatrix>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The Transport cost matrix lets a library system define relative costs to
transport books to one another. In order for the system to use this
matrix you must first set the
`UseTransportCostMatrix <#UseTransportCostMatrix>`__ preference to
'Use'.

    **Important**

    The Transport cost matrix takes precedence in controlling where
    holds are filled from, if the matrix is not used then Koha checks
    the `StaticHoldsQueueWeight <#holdqueueweight>`__.

Costs are decimal values between some arbitrary maximum value (e.g. 1 or
100) and 0 which is the minimum (no) cost. For example, you could just
use the distance between each library in miles as your 'cost', if that
would accurately reflect the cost of transferring them. Perhaps post
offices would be a better measure. Libraries sharing a post office would
have a cost of 1, adjacent post offices would have a cost of 2, etc.

To enter transport costs simply click in the cell you would like to
alter, uncheck the 'Disable' box and enter your 'cost'

Transport cost matrix
|image175|

After entering in your cost, hit 'Enter' on your keyboard or click the
'Save' button at the bottom of the matrix to save your changes.

    **Note**

    A NULL value will make no difference where the From and To libraries
    are the same library. However, as a best practice, you should put a
    0 in there. For all other To/From combinations, a NULL value will
    cause that relationship to act as if it has been disabled. So, in
    summary, don't leave any of the values empty. It's best to always
    put a number in there ( even if you choose to disable that given
    To/From option ).

`Item Circulation Alerts <#itemcircalerts>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Libraries can decide if they want to have patrons automatically notified
of circulation events (check ins and check outs).

-  *Get there:* More > Administration > Patrons & Circulation > Item
   Circulation Alerts

These preferences are set based on patron types and item types.

    **Important**

    These preference can be overridden by changes in the individual
    patron's messaging preferences.

To set up circulation alerts:

-  Choose your library from the pull down at the top of the screen

   Libraries to set Circulation Alerts
   |image176|

   -  To set preferences for all libraries, keep the menu set to
      'Default'

-  By default all item types and all patrons are notified of check ins
   and check outs. To change this, click on the item/patron type combo
   that you would like to stop notices for.

   Circulation Alert Matrix
   |image177|

   -  In the above example, Juveniles and Kids will not receive check
      out notices.

`Cities and Towns <#citytowns>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To standardize patron input you can define cities or towns within your
region so that when new patrons are added librarians simply have to
select the town from a list instead of having to type the town and zip
(or postal) code information.

-  *Get there:* More > Administration > Patrons & Circulation > Cities
   and Towns

`Adding a City <#addingcity>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To add a new city, click the 'New City' button at the top of the page
and enter the city name, state, zip/postal code and country.

New city entry form
|image178|

One you click Submit, your city will be saved and will be listed on the
Cities and Towns page

List of Cities
|image179|

Cities can be edited or deleted at any time.

`Viewing Cities on Patron Add Form <#citiesonpatform>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you have defined local cities using the New city form, then when
adding or editing a patron record you will see those cities in a pull
down menu to make city selection easy.

Cities pull down on the patron record
|image180|

This will allow for easy entry of local cities into the patron record
without risking the potential for typos or mistaken zip/postal codes.

`Catalog Administration <#catadmin>`__
--------------------------------------

Set these controls before you start cataloging on your Koha system.

-  *Get there:* More > Administration > Catalog

`MARC Bibliographic Frameworks <#marcbibframeworks>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Think of Frameworks as templates for creating new bibliographic records.
Koha comes with some predefined frameworks that can be edited or
deleted, and librarians can create their own frameworks for content
specific to their libraries.

-  *Get there:* More > Administration > Catalog > MARC Bibliographic
   Frameworks

Frameworks List
|image181|

    **Important**

    Do not delete or edit the Default Framework since this will cause
    problems with your cataloging records - always create a new template
    based on the Default Framework, or alter the other Frameworks.

After clicking the 'MARC structure' link to the right of each framework
you can decide how many fields you want to see on one screen by using
the pagination options at the top of the table.

Pagination options
|image182|

`Add New Framework <#addframework>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To add a new framework

-  Click 'New Framework'

   Add Framework Form
   |image183|

   -  Enter a code of 4 or fewer characters

   -  Use the Description field to enter a more detailed definition of
      your framework

-  Click 'Submit'

-  Once your Framework is added click 'MARC structure' to the right of
   it on the list of Frameworks

   Choose basis for new Framework
   |image184|

   -  You will be asked to choose a Framework to base your new Framework
      off of, this will make it easier than starting from scratch

-  Once your Framework appears on the screen you can edit or delete each
   field by following the instructions for `editing
   subfields <#editsubfields>`__

`Edit Existing Frameworks <#editframeworks>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Clicking 'Edit' to the right of a Framework will only allow you to edit
the Description for the Framework:

Edit Framework
|image185|

To make edits to the fields associated with the Framework you must first
click 'MARC Structure' and then follow the instructions for `editing
subfields <#editsubfields>`__

`Add subfields to Frameworks <#addsubfieldsframework>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To add a field to a Framework click the 'New Tag' button at the top of
the Framework definition

New Tag Button
|image186|

This will open up a blank form for entering MARC field data

Add a new tag to framework
|image187|

Enter the information about your new tag:

-  The 'Tag' is the MARC field number

-  The 'Label for lib' is the text that will appear in the staff client
   when in the cataloging module

-  The 'Label for OPAC' is the text that will appear in the OPAC when
   viewing the MARC version of the record

-  If this field can be repeated, check the 'Repeatable' box

-  If this field is mandatory, check the 'Mandatory' box

-  If you want this field to be a pull down with limited possible
   answers, choose which 'Authorized value' list you want to use

When you're finished, click 'Save Changes' and you will be presented
with your new field

New tag and link to subfields
|image188|

To the right of the new field is a link to 'Subfields,' you will need to
add subfields before this tag will appear in your MARC editor. The
process of entering the settings for the new subfield is the same as
those found in the `editing subfields in frameworks <#editsubfields>`__
section of this manual.

`Edit Framework Subfields <#editsubfields>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Frameworks are made up of MARC fields and subfields. To make edits to
most Frameworks you must edit the fields and subfields. Clicking 'Edit'
to the right of each subfield will allow you to make changes to the text
associated with the field

Modify MARC Field
|image189|

-  Each field has a tag (which is the MARC tag) that is uneditable

   -  The 'Label for lib' is what will show in the staff client if you
      have `advancedMARCeditor <#advancedMARCeditor>`__ set to display
      labels

   -  The 'Label for OPAC' is what will show on the MARC view in the
      OPAC

   -  If you check 'Repeatable' then the field will have a plus sign
      next to it allowing you to add multiples of that tag

   -  If you check 'Mandatory' the record will not be allowed to save
      unless you have a value assigned to this tag

   -  'Authorized value' is where you define an `authorized
      value <#authorizedvalues>`__ that your catalogers can choose from
      a pull down to fill this field in

To edit the subfields associated with the tag, click 'Subfields' to the
right of the tag on the 'MARC Structure' listing

-  From the list of subfields you can click 'Delete' to the right of
   each to delete the subfields

-  To edit the subfields click 'Edit Subfields'

-  For each subfield you can set the following Basic constraint values

   Editing the 504 Subfield
   |image190|

   -  Text for librarian

      -  what appears before the subfield in the librarian interface

   -  Text for OPAC

      -  what appears before the field in the OPAC.

         -  If left empty, the text for librarian is used instead

   -  Repeatable

      -  the field will have a plus sign next to it allowing you to add
         multiples of that tag

   -  Mandatory

      -  the record will not be allowed to save unless you have a value
         assigned to this tag

   -  Managed in tab

      -  defines the tab where the subfield is shown. All subfields of a
         given field must be in the same tab or ignored. Ignore means
         that the subfield is not managed.

-  For each subfield you can set the following Advanced constraint
   values

   Advanced constraints
   |image191|

   -  Default value

      -  defines what you want to appear in the field by default, this
         will be editable, but it saves time if you use the same note
         over and over or the same value in a field often.

      -  **Note**

             If you would like a field to fill in with today's date you
             can use the YYYY MM DD syntax in the 'Default value'. For
             example: a default of "Year:YYYY Month:MM Day:DD" (without
             quotes) will print as "Year:2015 Month:11 Day:30"

   -  Visibility

      -  allows you to select from where this subfield is
         visible/hidden, simply check the boxes where you would like the
         field to show and uncheck the boxes where you would like it
         hidden.

         Framework visibility
         |image192|

   -  Is a URL

      -  if checked, it means that the subfield is a URL and can be
         clicked

   -  Link

      -  If you enter a field/subfield here (200b), a link appears after
         the subfield in the MARC Detail view. This view is present only
         in the staff client, not the OPAC. If the librarian clicks on
         the link, a search is done on the database for the
         field/subfield with the same value. This can be used for 2 main
         topics :

         -  on a field like author (200f in UNIMARC), put 200f here, you
            will be able to see all bib records with the same author.

         -  on a field that is a link (4xx) to reach another bib record.
            For example, put 011a in 464$x, will find the serials that
            are with this ISSN.

      -  **Warning**

             This value should not change after data has been added to
             your catalog. If you need to change this value you must ask
             your system administrator to run
             misc/batchRebuildBiblioTables.pl.

   -  Koha link

      -  Koha is multi-MARC compliant. So, it does not know what the
         245$a means, neither what 200$f (those 2 fields being both the
         title in MARC21 and UNIMARC). So, in this list you can "map" a
         MARC subfield to its meaning. Koha constantly maintains
         consistency between a subfield and its meaning. When the user
         want to search on "title", this link is used to find what is
         searched (245 if you're MARC21, 200 if you're UNIMARC).

-  For each subfield you can set the following Other option values

   |image193|

   -  Authorized value

      -  means the value cannot by typed by the librarian, but must be
         chosen from a pull down generated by the `authorized
         value <#authorizedvalues>`__ list

      -  In the example above, the 504a field will show the MARC504
         Authorized Values when cataloging

         Example of an Authorized Subfield
         |image194|

   -  Thesaurus

      -  means that the value is not free text, but must be searched in
         the authority/thesaurus of the selected category

   -  Plugin

      -  means the value is calculated or managed by a plugin. Plugins
         can do almost anything.

      -  Examples:

         -  For call numbers there is an option to add a call number
            browser next to the the call number subfield so that you can
            identify which call numbers are in use and which are not.
            Simply choose the cn\_browser.pl plugin. Learn more in the
            `cataloging section <#addingitems>`__ of this manual.

         -  If you'd like to let file uploads via cataloging you can
            choose the upload.pl plugin and this will allow you to
            `upload files to Koha to link to your
            records <#uploadbibfile>`__.

         -  In UNIMARC there are plugins for every 1xx fields that are
            coded fields. The plugin is a huge help for cataloger! There
            are also two plugins (unimarc\_plugin\_210c and
            unimarc\_plugin\_225a that can "magically" find the editor
            from an ISBN, and the collection list for the editor)

-  To save your changes simply click the 'Save Changes' button at the
   top of the screen

`Import/Export Frameworks <#importexportframeworks>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Next to each framework is a link to either import or export the
framework.

`Export Framework <#exportframeworks>`__
''''''''''''''''''''''''''''''''''''''''

To export a framework simply click the 'Export' link to the right of
framework title.

Export link next to framework
|image195|

When you click 'Export' you will be prompted to choose what format to
export the file in.

Export formats
|image196|

A framework exported this way can be imported into any other Koha
installation using the import framework option.

`Import Framework <#importframeworks>`__
''''''''''''''''''''''''''''''''''''''''

An easy way to create a new framework is to import one created for your
or another Koha installation. This framework would need to be exported
from the other system `using the instructions
above <#exportframeworks>`__ to be available for import here.

To import a framework you first need to create `a new
framework <#addframework>`__. Once you have that framework, click
'Import' to the right of the new framework.

Import link next to framework
|image197|

You will be prompted to find a file on your computer to import into the
framework.

Choose a file to import
|image198|

You will be asked to confirm your actions before the file is imported.

Confirm your desire to import
|image199|

As your file is uploaded you will see an image that will confirm that
the system is working.

Import timer
|image200|

Once your import is complete you will be brought to the framework edit
tool where you can make any changes you need to the framework you
imported.

`Koha to MARC Mapping <#kohamarcmapping>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

While Koha stores the entire MARC record, it also stores common fields
for easy access in various tables in the database. Koha to MARC Mapping
is used to tell Koha where to find these values in the MARC record. In
many cases you will not have to change the default values set by in this
tool on installation, but it is important to know that the tool is here
and can be used at any time.

-  *Get there:* More > Administration > Catalog > Koha to MARC Mapping

The Koha to MARC Mapping page offers you the option of choosing from one
of three tables in the database to assign values to.

Koha to MARC Mapping Table Pull Down
|image201|

After choosing the table you would like to view, click 'OK.' To edit any
mapping click on the 'Koha Filed' or the 'Edit' link.

Map MARC Field to Koha Field
|image202|

Choose which MARC field you would like to map to this Koha Field and
click the 'OK' button. If you would like to clear all mappings, click
the 'Click to "Unmap"' button.

    **Important**

    At this time you can map only 1 MARC field to 1 Koha field. This
    means that you won't be able to map both the 100a and the 700a to
    the author field, you need to choose one or the other.

`Keywords to MARC Mapping <#keywordmapping>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This tool will allow you to map MARC fields to a set of predefined
keywords.

-  *Get there:* More > Administration > Catalog > Keywords to MARC
   Mapping

    **Important**

    This tool only effects sites that are not using the XSLT
    Stylesheets.

At this time the only keyword in use is 'subtitle.'

Using this tool you can define what MARC field prints to the detail
screen of the bibliographic record using keywords. The following example
will use the subtitle field.

Using the Framework pull down menu, choose the
`Framework <#marcbibframeworks>`__ you would like to apply this rule to.
For example, the subtitle for books can be found in the 245$b field.

Assigning Book Subtitle
|image203|

However the subtitle for DVDs appears in 245$p

Assigning DVD Subtitle
|image204|

Using this tool you can tell Koha to print the right field as the
subtitle when viewing the bibliographic record in the OPAC.

Subtitle display in the OPAC
|image205|

This tool can be used to chain together pieces of the record as well. If
you want the series number to show in the title on your search results
you simply have to map 490 $v to 'subtitle' along with the 245 $b.

    **Note**

    Chain together the fields you want to show after the item title in
    the order in which you want them to appear.

Future developments will include additional keyword assigned fields.

`MARC Bibliographic Framework Test <#marcbibframeworkstest>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Checks the MARC structure.

-  *Get there:* More > Administration > Catalog > MARC Bibliographic
   Framework Test

If you change your MARC Bibliographic framework it's recommended that
you run this tool to test for errors in your definition.

Framework Test
|image206|

`Authority Types <#authoritiesadmin>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Authority Types are basically MARC Frameworks for Authority records and
because of that they follow the same editing rules found in the `MARC
Bibliographic Frameworks <#marcbibframeworks>`__ section of this manual.
Koha comes with many of the necessary Authority frameworks already
installed. To learn how to add and edit Authority Types, simply review
the `MARC Bibliographic Frameworks <#marcbibframeworks>`__ section of
this manual.

-  *Get there:* More > Administration > Catalog > Authority Types

`Classification Sources <#classificationsources>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Source of classification or shelving scheme is an `Authorized
Values <#authorizedvalues>`__ category that is mapped to field 952$2 and
942$2 in Koha's MARC Bibliographic frameworks and stored in the
items.cn\_source field in the database.

-  *Get there:* More > Administration > Catalog > Classification sources

Classification Sources
|image207|

Commonly used values of this field are:

-  ddc - Dewey Decimal Classification

-  lcc - Library of Congress Classification

If you chose to install classification sources during Koha's
installation, you would see other values too:

-  ANSCR (sound recordings)

-  SuDOC classification

-  Universal Decimal Classification

-  Other/Generic Classification

`Adding/Editing Classification Sources <#addingclasssource>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can add your own source of classification by using the New
Classification Source button. To edit use the Edit link.

Add classification source
|image208|

When creating or editing:

-  You will need to enter a code and a description.

-  Check the 'Source in use?' checkbox if you want the value to appear
   in the drop down list for this category.

-  Select the appropriate `filing rule <#classfilingrules>`__ from the
   drop down list.

`Classification Filing Rules <#classfilingrules>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Filing rules determine the order in which items are placed on shelves.

Values that are pre-configured in Koha are:

-  Dewey

-  LCC

-  Generic

Filing rules are mapped to `Classification
sources <#addingclasssource>`__. You can setup new filing rules by using
the New Filing Rule button. To edit use the Edit link.

When creating or editing:

-  Enter a code and a description

-  Choose an appropriate filing routine - dewey, generic or lcc

`Record Matching Rules <#recordmatchingrules>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Record matching rules are used when importing MARC records into Koha.

-  *Get there:* More > Administration > Catalog > Record Matching Rules

The rules that you set up here will be referenced with you `Stage MARC
Records for Import <#stagemarc>`__.

It is important to understand the difference between Match Points and
Match Checks before adding new matching rules to Koha.

Match Points are the criteria that you enter that must be met in order
for an incoming record to match an existing MARC record in your catalog.
You can have multiple match points on an import rule each with its own
score. An incoming record will be compared against your existing records
(‘one record at a time’) and given a score for each match point. When
the total score of the matchpoints matches or exceeds the threshold
given for the matching rule, Koha assumes a good match and
imports/overlays according your specifications in the import process. An
area to watch out for here is the sum of the match points. Doublecheck
that the matches you want will add up to a successful match.

Example:

Threshold of 1000

Match Point on 020$a 1000

Match Point on 022$a 1000

Match Point on 245$a 500

Match Point on 100$a 100

In the example above, a match on either the 020$a or the 022$a will
result in a successful match. A match on 245$a title and 100$a author
(and not on 020$a or 022$a) will only add up to 600 and not be a match.
And a match on 020$a and 245$a will result in 1500 and while this is a
successful match, the extra 500 point for the 245$a title match are
superfluous. The incoming record successfully matched on the 020$a
without the need for the 245$a match. However, if you assigned a score
of 500 to the 100$a Match Point, a match on 245$a title and 100$a author
will be considered a successful match (total of 1000) even if the 020$a
is not a match.

Match Checks are not commonly used in import rules. However, they can
serve a couple of purposes in matching records. First, match checks can
be used as the matching criteria instead of the match points if your
indexes are stale and out of date. The match checks go right for the
data instead of relying on the data in the indexes. (If you fear your
indexes are out of date, a rebuild of your indexes would be a great idea
and solve that situation!) The other use for a Match Check is as a
“double check” or “veto” of your matching rule. For example, if you have
a matching rule as below:

Threshold of 1000

Match Point on 020$a 1000

Match Check on 245$a

Koha will first look at the 020$a tag/subfield to see if the incoming
record matches an existing record. If it does, it will then move on to
the Match Check and look directly at the 245$a value in the incoming
data and compare it to the 245$a in the existing ‘matched’ record in
your catalog. If the 245$a matches, Koha continues on as if a match was
successful. If the 245$a does not match, then Koha concludes that the
two records are not a match after all. The Match Checks can be a really
useful tool in confirming true matches.

When looking to create matching rules for your authority records the
following indexes will be of use:

+--------------------------+--------------------+
| Index name               | Matches Marc Tag   |
+==========================+====================+
| LC-cardnumber            | 010$a              |
+--------------------------+--------------------+
| Personal-name            | 100$a              |
+--------------------------+--------------------+
| Corporate-name-heading   | 110$a              |
+--------------------------+--------------------+
| Meeting-name             | 111$a              |
+--------------------------+--------------------+
| Title-uniform            | 130$a              |
+--------------------------+--------------------+
| Chronological-term       | 148$a              |
+--------------------------+--------------------+
| Subject-topical          | 150$a              |
+--------------------------+--------------------+
| Name-geographic          | 151$a              |
+--------------------------+--------------------+
| Term-genre-form          | 155$a              |
+--------------------------+--------------------+

Table: Authority Indexes

`Adding Matching Rules <#addrecordmatchrule>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To create a new matching rule :

-  Click 'New Record Matching Rule'

   Add record matching rule
   |image209|

   -  Choose a unique name and enter it in the 'Matching rule code'
      field

   -  'Description' can be anything you want to make it clear to you
      what rule you're picking

   -  'Match threshold' is the total number of 'points' a biblio must
      earn to be considered a 'match'

   -  'Record type' is the type of import this rule will be used for -
      either authority or bibliographic

   -  Match points are set up to determine what fields to match on

   -  'Search index' can be found by looking at the ccl.properties file
      on your system which tells the zebra indexing what data to search
      for in the MARC data".  Or you can review the index for standard 
      index names used.  :ref:`Koha Search Indexes`

   -  'Score' - The number of 'points' a match on this field is worth.
      If the sum of each score is greater than the match threshold, the
      incoming record is a match to the existing record

   -  Enter the MARC tag you want to match on in the 'Tag' field

   -  Enter the MARC tag subfield you want to match on in the
      'Subfields' field

   -  'Offset' - For use with control fields, 001-009

   -  'Length' - For use with control fields, 001-009

   -  Koha only has one 'Normalization rule' that removes extra
      characters such as commas and semicolons. The value you enter in
      this field is irrelevant to the normalization process.

   -  'Required match checks' - ??

`Sample Bibliographic Record Matching Rule: Control Number <#samplerecordmatch>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

LOC Matching Rule
|image210|

-  Match threshold: 100

-  Record type: Bibliographic

   -  **Note**

          If you'd like a rule to match on the 001 in authority records
          you will need the repeat all of these values and change just
          the record type to 'Authority record'

-  Matchpoints (just the one):

-  Search index: Control-number

-  Score: 101

-  Tag: 001

   -  **Note**

          this field is for the control number assigned by the
          organization creating, using, or distributing the record

-  Subfields: a

-  Offset: 0

-  Length: 0

-  Normalization rule: Control-number

-  Required Match checks: none (remove the blank one)

   Remove match check
   |image211|

`OAI Sets Configuration <#oaisetsconfig>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

On this page you can create, modify and delete OAI-PMH sets

`Create a set <#oaicreate>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To create a set:

-  Click on the link 'Add a new set'

-  Fill the mandatory fields 'setSpec' and 'setName'

-  Then you can add descriptions for this set. To do this click on 'Add
   description' and fill the newly created text box. You can add as many
   descriptions as you want.

-  Click on 'Save' button'

`Modify/Delete a set <#oaimodify>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To modify a set, just click on the link 'Modify' on the same line of the
set you want to modify. A form similar to set creation form will appear
and allow you to modify the setSpec, setName and descriptions.

To delete a set, just click on the link 'Delete' on the same line of the
set you want to delete.

`Define mappings <#oaimapping>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Here you can define how a set will be build (what records will belong to
this set) by defining mappings. Mappings are a list of conditions on
record content. A record only need to match one condition to belong to
the set.

-  Fill the fields 'Field', 'Subfield' and 'Value'. For example if you
   want to include in this set all records that have a 999$9 equal to
   'XXX'. Fill 'Field' with 999, 'Subfield' with 9 and 'Value' with XXX.

-  If you want to add another condition, click on 'OR' button and repeat
   step 1.

-  Click on 'Save'

To delete a condition, just leave at least one of 'Field', 'Subfield' or
'Value' empty and click on 'Save'.

    **Note**

    Actually, a condition is true if value in the corresponding subfield
    is strictly equal to what is defined if 'Value'. A record having
    999$9 = 'XXX YYY' will not belong to a set where condition is 999$9
    = 'XXX'.

And it is case sensitive : a record having 999$9 = 'xxx' will not belong
to a set where condition is 999$9 = 'XXX'.

`Build sets <#oaibuild>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^

Once you have configured all your sets, you have to build the sets. This
is done by calling the script misc/migration\_tools/build\_oai\_sets.pl.

`Item search fields <#itemsearchadmin>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

From here you can add custom search fields to the `item
search <#searchguide-itemsearch>`__ option in the staff client. Item
search fields

To add a new search term simply click the 'New search field' buttonAdd
new field

-  Name is a field for you to identify the search term

-  Label is what will appear on the item search page

-  MARC field allows you to pick which field you'd like to search in

-  MARC subfield is the subfield you'd like to search in

-  Authorised values category can be used to turn this search field in
   to a pull down instead of a free text field

Once your new field is added it will be visible at the top of this page
and on the item search pageSearch option

`Acquisitions <#acqadmin>`__
----------------------------

The Koha Acquisitions module provides a way for the library to record
orders placed with vendors and manage purchase budgets.

Before using the `Acquisitions Module <#acqmodule>`__, you will want to
make sure that you have completed all of the set up.

-  *Get there:* More > Administration > Acquisitions

`Currencies and Exchange Rates <#currexchangeadmin>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you place orders from more than one country you will want to input
currency exchange rates so that your acquisitions module will properly
calculate totals.

-  *Get there:* More > Administration > Acquisitions > Currencies and
   Exchange Rates

Currencies
|image212|

    **Note**

    This data is not automatically updated, so be sure to keep it up to
    date so that your accounting is kept correct.

The ISO code you enter will be used when importing MARC files via the
staging tools, the tool will attempt to find and use the price of the
currently active currency.

The active currency is the main currency you use in your library. Your
active currency will have a check mark in the 'Active' column. If you
don't have an active currency you will see an error message telling you
to choose an active currency.

No active currency warning
|image213|

`Budgets <#budgetplanning>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Budgets are used for tracking accounting values related to acquisitions.
For example you could create a Budget for the current year (ex. 2015)
and then break that into `Funds <#funds>`__ for different areas of the
library (ex. Books, Audio, etc).

-  *Get there:* More > Administration > Acquisitions > Budgets

When visiting the main budget administration you will see two tabs, one
for active and one for inactive budgets.

Budgets List
|image214|

`Adding budgets <#addbudget>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Budgets can either be created `from scratch <#addnewbudget>`__, by
`duplicating the previous year's budget <#duplicatebudget>`__ or by
`closing a previous year's budget <#closebudget>`__.

`Add a new budget <#addnewbudget>`__
''''''''''''''''''''''''''''''''''''

If you haven't used Koha before for acquisitions then you'll need to
start fresh with a new budget. To add a new budget click the 'New
Budget' button.

New Budget Form
|image215|

-  Choose the time period this budget is for, whether it's an academic
   year, a fiscal year, a quarter, etc.

-  The Description should be something that will help you identify the
   budget when ordering

-  In the amount box do not use any symbols, simply enter the amount of
   the budget with numbers and decimals.

-  Marking a budget active makes it usable when placing orders in the
   acquisitions module, even if the order is placed after the budget end
   date. This will allow you to record orders that were places in a
   previous budget period.

-  Locking a budget means that Funds will not be able to be modified by
   librarians

Once you have made your edits, click the 'Save Changes' button. You will
be brought to a list of your existing budgets.

List of Budgets
|image216|

`Duplicate a budget <#duplicatebudget>`__
'''''''''''''''''''''''''''''''''''''''''

To duplicate a budget from a previous year, click on the link for the
budget name from the list of budgets

Budgets List
|image217|

On the screen listing the budget breakdown click the Edit button at the
top and choose to Duplicate budget

Duplicate Budget
|image218|

You can also click the 'Actions' button to the right of the budget and
choose 'Duplicate'.Duplicate budget

In both cases you will be presented with a form where you simply need to
enter the new start and end date and save the budget.

New Duplicate Budget
|image219|

Check the box for 'Mark the original budget as inactive' if the original
budget should no longer be used.

Check the box for 'Set all funds to zero' if you wish the new budget to
contain all the same fund structures as the previous budget but no
allocations until you manually enter an amount in the fund.

This will not only duplicate your budget, but all of the funds
associated with that budget so that you can reuse budgets and funds from
year to year and so that you can move unreceived orders and if desired
unspent funds from a previous budget to the new budget.

`Close a budget <#closebudget>`__
'''''''''''''''''''''''''''''''''

Close a budget to move or roll over unreceived orders and if desired
unspent funds from a previous budget to a new budget. Before closing
your budget you might want to `duplicate the previous year's
budget <#duplicatebudget>`__ so that you have somewhere for the
unreceived orders to roll to.

Find the previous budget with unreceived orders on the Active budgets or
the Inactive budgets tab and select 'Close' under 'Actions'. Close a
budget

    **Note**

    In order for the unreceived orders to be automatically moved to the
    new budget, the fund structures in the previous budget must exist in
    the new budget. Budgets without unreceived orders cannot be closed.

When you select 'Close' you will be presented with a form.Closing a
budget

Use the 'Select a budget' drop down to choose the new budget for the
unreceived orders.

Check the box for 'Move remaining unspent funds' to move the unspent
amounts from the funds of the budget being closed to the selected
budget.

Once you have made your choices, click the 'Move unreceived orders'
button. You will be presented with a dialog box that says 'You have
chosen to move all unreceived orders from 'Budget X' to 'Budget Y'. This
action cannot be reversed. Do you wish to continue?' Budget X is the
budget to be closed and Budget Y is the selected budget. Close warning

If everything seems correct click 'OK' and the unreceived orders and, if
selected, unspent funds will be moved.

Wait until the 'Report after moving unreceived orders from budget X to
Y' displays. This will list the order numbers which have been impacted
(grouped by fund) and detail if the unreceived order was moved or if
there was a problem. For example, if the new budget does not contain a
fund with the same name as the previous budget, the order will not be
moved.

Close report
|image220|

`Funds <#funds>`__
~~~~~~~~~~~~~~~~~~

-  *Get there:* More > Administration > Acquisitions > Funds

`Add a Fund <#addbudgetfund>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A fund is added to a budget.

    **Important**

    A `budget <#addbudget>`__ must be defined before a fund can be
    created.

To add a new fund click the New button and then choose which Budget you
would like to add the fund to.

Choose which budget to add a fund to
|image221|

In the form that appears you want to enter the basics about your fund.

New Fund Form
|image222|

The three first fields are required, the rest are optional

-  Fund Code is a unique identifier for your fund

-  The Fund Name should be something that librarians will understand

-  Amount should be entered with only numbers and decimals, no other
   characters

-  Warning at (%) or Warning at (amount) can be filled in to make Koha
   warn you before you spend a certain percentage or amount of your
   budget. This will prevent you from overspending.

-  You can choose to assign this fund to a librarian. Doing so will make
   it so that only that librarian can make changes to the Fund

-  Choose which library will be using this fund

-  You can restrict who can order from this fund by choosing either the
   'owner', 'owner and users' or 'owner, users and library' from the
   'Restrict access to' menu

   Restrict Fund Access
   |image223|

   -  **Important**

          Without an owner, the access restriction will be ignored, be
          sure to enter an owner as well as choose a restriction

-  Notes are simply for any descriptive notes you might want to add so
   that librarians know when to use this fund

-  Planning categories are used for statistical purposes. If you will be
   using the Asort1 and/or Asort2 authorised values lists to track your orders 
   you need to select them when setting up the fund.  Select the Asort1/Asort2
   option from the dropdown lists for the Statiscal 1 done on: and 
   Statistical 2 done on: fields.  
   
-  To learn more about planning categories, check out the `Planning Category
   FAQ <#planningcatfaq>`__.  

When complete, click 'Submit' and you will be brought to a list of all
of the funds for the budget.

List of funds
|image224|

The monetary columns in the fund table break down as follows:

1. Base-level allocated is the "Amount" value you defined when creating
   the fund

2. Base-level ordered is the ordered amount for this fund (without child
   funds)

3. Total ordered is the base-level ordered for this fund and all its
   child funds

4. Base-level spent is the spent amount for this fund (without child
   funds)

5. Total spent is the base-level spent for this fund and all its child
   funds

6. Base-level available is 1 - 2

7. Total available is 1 - 3

To the right of each fund you will find the 'Actions' button under which
you will find the 'Edit,' 'Delete,' and 'Add Child Fund' options.

Fund actions
|image225|

A child fund simply a sub-fund of the fund listed. An example would be
to have a fund for 'Fiction' and under that have a fund for 'New
Releases' and a fund for 'Science Fiction.' It is an optional way to
further organize your finances.

Funds with children will show with a small arrow to the left. Clicking
that will show you the children funds.

Child funds
|image226|

`Budget Planning <#fundsplanning>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

When viewing the list of funds click the 'Planning' button and choose
how you would like to plan to spend your budget.

Planning pull down menu
|image227|

If you choose 'Plan by MONTHS' you will see the budgeted amount broken
down by months:

Budget Planning Formula
|image228|

To hide some of the columns you can click the 'hide' link to the right
(or below as in the screenshot above) the dates. To add more columns you
can click the 'Show a column' link found below the 'Fund Remaining'
heading.

Choose columns to add
|image229|

From here you can plan your budget spending by manually entering values
or by clicking the 'Auto-fill row' button. If you choose to auto-fill
the form the system will try to divide the amount accordingly, you may
have to make some edits to split things more accurately.

Auto-filled columns
|image230|

Once your changes are made, click the 'Save' button. If you would like
to export your data as a CSV file you can do so by entering a file name
in the 'Output to a file named' field and clicking the 'Output' button.

Export planning as CSV
|image231|

`EDI Accounts <#ediaccounts>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

From here you can set up the information needed to connect to your
acquisitions vendors.

    **Note**

    Before you begin you will need at least one `Vendor set up in
    Acquisitions <#addacqvendor>`__.

To add account information click the 'New account' button.New account

In the form that appears you will want to enter your vendor information.

New account information

Each vendor will have one account.

`Library EANs <#libraryeans>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A library EAN is the identifier the vendor gives the library to send
back to them so they know which account to use when billing. One EDI
account can have multiple EANs.

To add an EAN click the 'New EAN' button.

New EAN

In the form that appears enter the information provided by your vendor.

New EAN Form

`Additional Parameters <#additionaladmin>`__
--------------------------------------------

-  *Get there:* More > Administration > Additional Parameters

`Z39.50/SRU servers <#z3950admin>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Z39.50 is a client–server protocol for searching and retrieving
information from remote computer databases, in short it's a tool used
for copy cataloging.

SRU- Search/Retrieve via URL - is a standard XML-based protocol for
search queries, utilizing CQL - Contextual Query Language - a standard
syntax for representing queries.

Using Koha you can connect to any Z39.50 or SRU target that is publicly
available or that you have the log in information to and copy both
bibliographic and/or authority records from that source.

-  *Get there:* More > Administration > Additional Parameters >
   Z39.50/SRU Servers

Koha comes with a default list of Z39.50/SRU targets set up that you can
add to, edit or delete

List of Z39.50 Servers in Koha
|image232|

To find additional Z39.50 targets you use IndexData's IRSpy:
`http://irspy.indexdata.com <http://irspy.indexdata.com/>`__ or the
Library of Congress's List of Targets http://www.loc.gov/z3950/

`Add a Z39.50 Target <#addztarget>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  From the main Z39.50 page, click 'New Z39.50 Server'

   New Z39.50 Server Form
   |image233|

   -  'Z39.50 server' should be populated with a name that will help you
      identify the source (such as the library name).

   -  'Hostname' will be the address to the Z39.50 target.

   -  'Port' tells Koha what port to listen on to get results from this
      target.

   -  'Userid' and 'Password' are only required for servers that are
      password protected.

   -  Check the 'Preselected' box if you want this target to always be
      selected by default.

   -  'Rank' lets you enter where in the list you'd like this target to
      appear.

      -  If this is left blank the targets will be in alphabetical
         order.

   -  'Syntax' is the MARC flavor you use.

   -  'Encoding' tells the system how to read special characters.

   -  'Timeout' is helpful for targets that take a long while. You can
      set the timeout so that it doesn't keep trying the target if
      results aren't found in a reasonable amount of time.

   -  'Record type' lets you define if this is a bibliographic or an
      authority target.

   -  'XSLT file(s)' lets enter one or more (comma-separated) XSLT file
      names that you want to apply on the search results.

      -  When retrieving records from external targets you may wish to
         automate some changes to those records. XSLT's allow you to do
         this. Koha ships with some sample XSLT files in the
         /koha-tmpl/intranet-tmpl/prog/en/xslt/ directory ready for use:

         -  Del952.xsl: Remove items (MARC21/NORMARC)

         -  Del995.xsl: Remove items (UNIMARC)

         -  Del9LinksExcept952.xsl: Remove $9 links. Skip item fields
            (MARC21/NORMARC)

         -  Del9LinksExcept995.xsl: Remove $9 links. Skip item fields
            (UNIMARC)

`Suggested Bibliographic Z39.50 Targets <#suggestztarget>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Koha libraries with open Z39.50 targets can share and find connection
information on the Koha wiki:
http://wiki.koha-community.org/wiki/Koha_Open_Z39.50_Sources. You can
also find open Z39.50 targets by visiting IRSpy:
http://irspy.indexdata.com.

The following targets have been used successfully by other Koha
libraries (in the Americas):

-  ACCESS PENNSYLVANIA 205.247.101.11:210 INNOPAC

-  CUYAHOGA COUNTY PUBLIC webcat.cuyahoga.lib.oh.us:210 INNOPAC

-  GREATER SUDBURY PUBLIC 216.223.90.51:210 INNOPAC

-  HALIFAX PUBLIC catalogue.halifaxpubliclibraries.ca:210 horizon

-  HALTON HILLS PUBLIC cat.hhpl.on.ca:210 halton\_hills

-  LIBRARY OF CONGRESS lx2.loc.gov: 210 LCDB

-  LONDON PUBLIC LIBRARY catalogue.londonpubliclibrary.ca:210 INNOPAC

-  MANITOBA PUBLIC library.gov.mb.ca:210 horizon

-  MILTON PL cat.mpl.on.ca:210 horizon

-  NATIONAL LIBRARY OF WALES cat.llgc.org.uk:210 default

-  NHUPAC 199.192.6.130:211 nh\_nhupac

-  OCEAN STATE LIBRARIES (RI) catalog.oslri.net:210 INNOPAC

-  OHIOLINK olc1.ohiolink.edu:210 INNOPAC

-  PUBCAT prod890.dol.state.vt.us:2300 unicorn

-  SAN JOAQUIN VALLEY PUBLIC LIBRARY SYSTEM (CA) hip1.sjvls.org:210
   ZSERVER

-  SEATTLE PUBLIC LIBRARY ZSERVER.SPL.ORG:210 HORIZON

-  TORONTO PUBLIC symphony.torontopubliclibrary.ca:2200 unicorn

-  TRI-UNI 129.97.129.194:7090 voyager

-  VANCOUVER PUBLIC LIBRARY z3950.vpl.ca:210 Horizon

`Suggested Authority Z39.50 Targets <#suggestauthz39>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The following targets have been used successfully by other Koha
libraries (in the Americas):

-  LIBRARIESAUSTRALIA AUTHORITIES
   z3950-test.librariesaustralia.nla.gov.au:210 AuthTraining Userid:
   ANLEZ / Password: z39.50

-  LIBRARY OF CONGRESS NAME AUTHORITIES lx2.loc.gov:210 NAF

-  LIBRARY OF CONGRESS SUBJECT AUTHORITIES lx2.loc.gov:210 SAF

`Add a SRU Target <#addsru>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  From the main Z39.50/SRU page, click 'New SRU Server'

   New SRU Server Form
   |image234|

   -  'Server name' should be populated with a name that will help you
      identify the source (such as the library name).

   -  'Hostname' will be the address to the Z39.50 target.

   -  'Port' tells Koha what port to listen on to get results from this
      target.

   -  'Userid' and 'Password' are only required for servers that are
      password protected.

   -  Check the 'Preselected' box if you want this target to always be
      selected by default.

   -  'Rank' lets you enter where in the list you'd like this target to
      appear.

      -  If this is left blank the targets will be in alphabetical
         order.

   -  'Syntax' is the MARC flavor you use.

   -  'Encoding' tells the system how to read special characters.

   -  'Timeout' is helpful for targets that take a long while. You can
      set the timeout so that it doesn't keep trying the target if
      results aren't found in a reasonable amount of time.

   -  'Additional SRU options' is where you can enter additional options
      of the external server here, like sru\_version=1.1 or
      schema=marc21, etc. Note that these options are server dependent.

   -  'SRU Search field mapping' lets you add or update the mapping from
      the available fields on the Koha search form to the specific
      server dependent index names.

      -  To further refine your searches, you could add the following
         index names to the SRU search field mappings. To do this, edit
         the server and click the Modify button next to this field.

         +---------------+---------------------------+
         | Title         | dc.title                  |
         +---------------+---------------------------+
         | ISBN          | bath.isbn                 |
         +---------------+---------------------------+
         | Any           | cql.anywhere              |
         +---------------+---------------------------+
         | Author        | dc.author                 |
         +---------------+---------------------------+
         | ISSN          | bath.issn                 |
         +---------------+---------------------------+
         | Subject       | dc.subject                |
         +---------------+---------------------------+
         | Standard ID   | bath.standardIdentifier   |
         +---------------+---------------------------+

         Table: SRU Mapping

   -  'XSLT file(s)' lets enter one or more (comma-separated) XSLT file
      names that you want to apply on the search results.

      -  When retrieving records from external targets you may wish to
         automate some changes to those records. XSLT's allow you to do
         this. Koha ships with some sample XSLT files in the
         /koha-tmpl/intranet-tmpl/prog/en/xslt/ directory ready for use:

         -  Del952.xsl: Remove items (MARC21/NORMARC)

         -  Del995.xsl: Remove items (UNIMARC)

         -  Del9LinksExcept952.xsl: Remove $9 links. Skip item fields
            (MARC21/NORMARC)

         -  Del9LinksExcept995.xsl: Remove $9 links. Skip item fields
            (UNIMARC)

`Did you mean? <#didyoumean>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*Get there:* More > Administration > Additional Parameters > Did you
mean?

Koha can offer 'Did you mean?' options on searches based on values in
your `authorities <#catauthorities>`__.

    **Important**

    Did you mean? only works in the OPAC at this time. The Intranet
    options are here for future development.

Using this page you can control which options Koha gives patrons on
their search results.

Did you mean?
|image235|

To turn on the 'Did you mean?' bar on your search results you need to
check the box next to each plugin you would like to use. The two plugins
you have to choose from are:

-  The ExplodedTerms plugin suggests that the user try searching for
   broader/narrower/related terms for a given search (e.g. a user
   searching for "New York (State)" would click the link for narrower
   terms if they're also interested in "New York (City)"). This is only
   relevant for libraries with highly hierarchical authority data.

-  The AuthorityFile plugin searches the authority file and suggests the
   user might be interested in bibs linked to the top 5 authorities

If you want one plugin to take priority over another you simply drag it
above the other.

Drag and drop options
|image236|

If you choose both plugins you will see several options at the top of
your search results

Both plugins
|image237|

If you choose just the AuthorityFile you'll see just authorities.

AuthorityFile
|image238|

`Column settings <#admincolumns>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This administration area will help you hide or display columns on fixed
tables throughout the staff client.

-  *Get there:* Administration > Additional Parameters > Column settings

Column settings
|image239|

Clicking on the module you'd like to edit tables for will show you the
options available to you.

This area lets you control the columns that show in the table in
question. If nothing is hidden you will see no check marks in the 'is
hidden by default' column.

Column settings
|image240|

And will see all of the columns when viewing the table on its regular
page.

Columns on currency table
|image241|

If columns are hidden they will have checks in the 'is hidden by
default' column.

Column settings
|image242|

And hidden when you view the table.

Columns on currency table
|image243|

You can also toggle columns using the 'Show/Hide Columns button in the
top right of the page

Toggle columns
|image244|

`Audio alerts <#audioadmin>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you have your `AudioAlerts <#AudioAlerts>`__ preference set to
'Enable' you will be able to control the various alert sounds that Koha
uses from this area.

-  *Get there:* More > Administration > Additional Parameters > Audio
   alerts

Each dialog box in Koha has a CSS class assigned to it that can be used
as a selector for a sound.Audio alerts

You can edit the defaults by clicking the 'Edit' button to the right of
each alertEdit alert

You can assign alerts to other CSS classes in Koha by entering that
information in the selector box. For example if you enter

::

    body:contains('Check in message')

Then when you visit the checkin page you will hear an alert.

Every page in Koha has a unique ID in the body tag which can be used to
limit a sound to a specific page

Any ID selector (where html contains id="name\_of\_id" ) and can also be
a trigger as: #name\_of\_selector

`SMS cellular providers <#smsadmin>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    **Important**

    This option will only appear if the
    `SMSSendDriver <#SMSSendDriver>`__ preference is set to 'Email'

From here you can enter as many cellular providers as you need to send
SMS notices to your patrons using the email protocol.SMS Providers

Some examples in the US are:

+---------------------+-----------------------------+
| Mobile Carrier      | SMS Gateway Domain          |
+=====================+=============================+
| Alltel              | sms.alltelwireless.com      |
+---------------------+-----------------------------+
| AT&T                | txt.att.net                 |
+---------------------+-----------------------------+
| Boost Mobile        | sms.myboostmobile.com       |
+---------------------+-----------------------------+
| Project Fi          | msg.fi.google.com           |
+---------------------+-----------------------------+
| Republic Wireless   | text.republicwireless.com   |
+---------------------+-----------------------------+
| Sprint              | messaging.sprintpcs.com     |
+---------------------+-----------------------------+
| T-Mobile            | tmomail.net                 |
+---------------------+-----------------------------+
| U.S. Cellular       | email.uscc.net              |
+---------------------+-----------------------------+
| Verizon Wireless    | vtext.com                   |
+---------------------+-----------------------------+
| Virgin Mobile       | vmobl.com                   |
+---------------------+-----------------------------+

Table: SMS Provider Examples

To add new providers enter the details in the form and click 'Add new'
to save.Add SMS Provider

These options will appear in the OPAC for patrons to choose from on the
`messaging tab <#opacmymsgs>`__ if you have
`EnhancedMessagingPreferences <#EnhancedMessagingPreferences>`__
enabled.Options for providers in the OPAC
