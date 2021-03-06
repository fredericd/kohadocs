.. include:: images.rst

Reports
=======

Reports in Koha are a way to gather data. Reports are used to generate
statistics, member lists, shelving lists, or any list of data in your
database.

-  *Get there:* More > Reports

`Custom Reports <#customreports>`__
-----------------------------------

Koha's data is stored in a MySQL database which means that librarians
can generate nearly any report they would like by either using the
`Guided Reports Wizard <#quidedreportwizard>`__ or writing their own
`SQL query <#reportfromsql>`__.

`Add Custom Report <#customreport>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

`Guided Report Wizard <#quidedreportwizard>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The guided report wizard will walk you through a six step process to
generate a report.

Step 1: Choose the module you want to report on. This will determine
what tables and fields are available for you to query.

'Report is public' should be left to the default of 'No' in most cases.
A report can be made public if you intend to allow access to it through
the JSON webservice interface. This is a system that can be used by
developers to make custom presentations of the data from the report, for
example displaying it using a graphing API. To learn more speak to your
local developer.

-  A public report is accessible via a URL that looks like this:
   http://MYOPAC/cgi-bin/koha/svc/report?id=REPORTID

Chose Module for Report
|image881|

    **Note**

    If your system administrator has set up memcache on your server you
    might see one more option for the Cache expiry. This is related to
    your public reports. If you make the report public then it's
    constantly running and will cause a large load on your system.
    Setting this value prevents that.Cache expiry

Step 2: Choose a report type. For now, Tabular is the only option
available.

Report Type
|image882|

Step 3: Choose the fields you want in your report. You can select
multiple fields and add them all at once by using CTRL+Click on each
item you want to add before clicking the Add button.

Select database fields to query
|image883|

Step 4: Choose any limits you might want to apply to your report (such
as item types or branches). If you don't want to apply any limits,
simply click Next instead of making an option.

Choose limits
|image884|

Step 5: Perform math functions. If you don't want to do any
calculations, simply click Next instead of making an option.

Choose math functions
|image885|

Step 6: Choose data order. If you want the data to print out in the
order it's found in the database, simply click Finish.

Choose ordering
|image886|

When you are finished you will be presented with the SQL generated by
the report wizard. From here you can choose to save the report by
clicking 'Save' or copy the SQL and make edits to it by hand.

Custom Report Confirmation
|image887|

If you choose to save the report you will be asked to name your report,
sort it in to groups and subgroups and enter any notes regarding it.

Save custom report
|image888|

Once your report is saved it will appear on the 'Use Saved' page with
all other saved reports.

Saved Reports list
|image889|

From here you can make edits, run the report, or schedule a time to have
the report run. To find the report you created you can sort by any of
the columns by clicking the on the column header (creation date is the
best bet for finding the report you just added). You can also filter
your results using the filter menu on the left or use the tabs to find
reports based on your custom groups.

`Report from SQL <#reportfromsql>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In addition to the report wizard, you have the option to write your own
queries using SQL. To find reports written by other Koha users, visit
the Koha Wiki: http://wiki.koha-community.org/wiki/SQL_Reports_Library.
You can also find your database structure in
/installer/data/mysql/kohastructure.sql or online at:
`http://schema.koha-community.org <http://schema.koha-community.org/>`__.

To add your query, click the link to 'Create from SQL' on the main
reports module or the 'New report' button at the top of the 'Saved
reports' page.

New SQL Report
|image890|

Fill in the form presented

Create Report from SQL
|image891|

-  The 'Name' is what will appear on the Saved Reports page to help you
   identify the report later. It will also be searchable using the
   filters found the left of the Saved Reports page.

-  You can use the 'Report group' to organize your reports so that you
   can easily filter reports by groups. Report groups are set in the
   `REPORT\_GROUP <#reportgroup>`__ authorized value category or can be
   added on the fly when creating the report by choosing the 'or create'
   radio button.Report groups set up in the authorised value category
   need to have unique authorised values and descriptions.

   -  **Note**

          If you're adding a report group on the fly, remember that you
          code should be fewer than 10 characters and should not include
          special characters or spaces.

-  You can use 'Report subgroup' to further organize your reports so
   that you can easily filter reports by groups and subgroups. Report
   subgroups are set in the `REPORT\_SUBGROUP <#reportsubgroup>`__
   authorized value category or can be added on the fly when creating
   the report by choosing the 'or create' radio button.  Report Subgroups
   are set up with unique values in Authorised Value, and Description. 
   The Description (OPAC) field needs to contain the authorised value for 
   the Report Group that the Subgroup falls under.

   Report subgroup
   |image892|

   -  **Note**

          If you're adding a report subgroup on the fly, remember that
          you code should be fewer than 10 characters and should not
          include special characters or spaces.

-  'Report is public' should be left to the default of 'No' in most
   cases. A report can be made public if you intend to allow access to
   it through the JSON webservice interface. This is a system that can
   be used by developers to make custom presentations of the data from
   the report, for example displaying it using a graphing API. To learn
   more speak to your local developer.

   -  A public report is accessible via a URL that looks like this:
      http://MYOPAC/cgi-bin/koha/svc/report?id=REPORTID

-  'Notes' will also appear on the Saved Reports page, this can be used
   to provide more details about the report or tips on how to enter
   values when it runs

-  The type should always be 'Tabular' at this time since the other
   formats have not been implemented

-  In the 'SQL' box you will type or paste the SQL for the report

-  If you feel that your report might be too resource intensive you
   might want to consider using runtime parameters to your query.
   Runtime parameters basically make a filter appear before the report
   is run to save your system resources.

   There is a specific syntax that Koha will understand as 'ask for
   values when running the report'. The syntax is <<Question to
   ask\|authorized\_value>>.

   -  The << and >> are just delimiters. You must put << at the
      beginning and >> at the end of your parameter

   -  The 'Question to ask' will be displayed on the left of the string
      to enter.

   -  The authorized\_value can be omitted if not applicable. If it
      contains an authorized value category, or branches or itemtype or
      categorycode or biblio\_framework, a list with the Koha authorized
      values will be displayed instead of a free field Note that you can
      have more than one parameter in a given SQL Note that entering
      nothing at run time won't probably work as you expect. It will be
      considered as "value empty" not as "ignore this parameter". For
      example entering nothing for : "title=<<Enter title>>" will
      display results with title='' (no title). If you want to have to
      have something not mandatory, use "title like <<Enter title>>" and
      enter a % at run time instead of nothing

   Examples:

   -  SELECT surname,firstname FROM borrowers WHERE branchcode=<<Enter
      patrons library\|branches>> AND surname like <<Enter filter for
      patron surname (% if none)>>

   -  SELECT \* FROM items WHERE homebranch = <<Pick your
      branch\|branches>> and barcode like <<Partial barcode value here>>

   -  SELECT title , author FROM biblio WHERE frameworkcode=<<Enter the
      frameworkcode\|biblio\_framework>>

       **Note**

       To generate a date picker calendar to the right of the field when
       running a report you can use the 'date' keyword like this:
       <<Enter Date\|date>>

       Date Picker
       |image893|

       **Note**

       You have to put "%" in a text box to 'leave it blank'. Otherwise,
       it literally looks for "" (empty string) as the value for the
       field.

       **Important**

       In addition to using any authorized value code to generate a
       dropdown, you can use the following values as well: Framework
       codes (biblio\_framework), Branches (branches), Item Types
       (itemtypes) and Patron Categories (categorycode). For example a
       branch pull down would be generated like this
       <<Branch\|branches>>

       Branch pull down
       |image894|

    **Note**

    There is a limit of 10,000 records put on SQL statements entered in
    Koha. To get around this you want to add 'LIMIT 100000' to the end
    of your SQL statement (or any other number above 10,000).

    **Note**

    If your system administrator has set up memcache on your server you
    might see one more option for the Cache expiry. This is related to
    your public reports. If you make the report public then it's
    constantly running and will cause a large load on your system.
    Setting this value prevents that.Cache expiry

Once everything is entered click the 'Save Report' button and you'll be
presented with options to run it. Once a report is saved you do not have
to recreate it you can simply find it on the Saved Reports page and
`run <#runcustomreport>`__ or `edit <#editcustomreports>`__ it.

`Duplicate Report <#duplicatereport>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Reports can also be added by duplicating an existing report. Visit the
'Saved reports' page to see all of the reports listed on your system
already.

Saved Reports
|image895|

To the right of every report there is an 'Actions' pull down. Clickin
that and choose 'Duplicate' to use an existing report as the basis for
your new report. That will populate the new report form with the
existing SQL for easy editing and resaving.

`Edit Custom Reports <#editcustomreports>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Every report can be edited from the reports lists. To see the list of
reports already stored in Koha, click 'Use Saved.'

Saved Reports
|image896|

To find the report you'd like to edit you can sort by any of the columns
by clicking the on the column header. You can also filter your results
using the filter menu on the left or use the tabs to find reports based
on your custom groups.

From this list you can edit any custom report by clicking 'Actions' to
the right of the report and choosing 'Edit' from the menu that appears.

Edit Report Option
|image897|

The form to edit the report will appear.

Edit SQL Form
|image898|

`Running Custom Reports <#runcustomreport>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Once custom reports are saved to Koha, you can run them by going to the
Saved Reports page and clicking the 'Actions' button to the right of the
report and choosing 'Run'.

Run Report
|image899|

When you report runs you will either be asked for some values

Enter report parameters
|image900|

or you will see the results right away

Report results
|image901|

From the results you can choose to rerun the report by clicking 'Run
report' at the top, edit the report by clicking the 'Edit' button or
starting over and creating a new report by using the 'New' button. You
can also download your results by choosing a file type at the bottom of
the results next to the 'Download the report' label and clicking
'Download.'

    **Note**

    A Comma Separated Text file is a CSV file and it can be opened by
    any spreadsheet application.

`Statistics Reports <#statsreports>`__
--------------------------------------

Statistic reports will show you counts and sums. These reports are all
about numbers and statistics, for reports that return more detailed
data, use the `Guided Report Wizard <#quidedreportwizard>`__. These
reports are limited in what data they can look at, so it's often
recommended to use `custom reports <#customreports>`__ for official end
of the year statistics.

`Acquisitions Statistics <#acqstats>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    **Note**

    These reports are limited in what data they can look at, so it's
    often recommended to use `custom reports <#customreports>`__ for
    official end of the year statistics.

Using the form provided, choose which value you would like to appear in
the Column and which will appear in the Row.

Acquisitions Statistics
|image902|

If you choose to output to the browser your results will print to the
screen.

Acquisitions Statistics Results
|image903|

You can also choose to export to a file that you can manipulate to your
needs.

When generating your report, note that you get to choose between
counting or summing the values.

Acquisitions Stats Options
|image904|

Choosing amount will change your results to appear as the sum of the
amounts spent.

Acquisitions statistics with totals
|image905|

`Patron Statistics <#patstats>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    **Note**

    These reports are limited in what data they can look at, so it's
    often recommended to use `custom reports <#customreports>`__ for
    official end of the year statistics.

Using the form provided, choose which value you would like to appear in
the Column and which will appear in the Row.

Patron Statistics Options
|image906|

If you choose to output to the browser your results will print to the
screen.

Patron Statistics Results
|image907|

Based on your selections, you may see some query information above your
results table. You can also choose to export to a file that you can
manipulate to your needs.

`Catalog Statistics <#catstats>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    **Note**

    These reports are limited in what data they can look at, so it's
    often recommended to use `custom reports <#customreports>`__ for
    official end of the year statistics.

Using the form provided, choose which value you would like to appear in
the Column and which will appear in the Row.

Catalog Statistics Form
|image908|

If you choose to output to the browser your results will print to the
screen.

Catalog Statistic Results
|image909|

You can also choose to export to a file that you can manipulate to your
needs.

`Circulation Statistics <#circstats>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    **Note**

    These reports are limited in what data they can look at, so it's
    often recommended to use `custom reports <#customreports>`__ for
    official end of the year statistics.

Using the form provided, choose which value you would like to appear in
the Column and which will appear in the Row.

Circulation Statistics
|image910|

If you choose to output to the browser your results will print to the
screen.

Circulation Statistic Results
|image911|

You can also choose to export to a file that you can manipulate to your
needs.

    **Note**

    To get a complete picture of your monthly or daily circulation, you
    can run the report twice, once for 'Type' of 'Checkout' and again
    for 'Renewal.'

    This report uses 'Period,' or date, filtering that allows you to
    limit to a month by simply selecting the first day of the first
    month through the first day of the next month. For example, 10/1 to
    11/1 to find statistics for the month of October.

    -  To find daily statistics, set your date range.</br> Example: "I
       want circulation data starting with date XXX up to, but not
       including, date XXX."

    -  For a whole month, an example range would be: 11/01/2009 to
       12/01/2009

    -  For a whole year, an example range would be: 01/01/2009 to
       01/01/2010

    -  For a single day, an example would be: 11/15/2009 to 11/16/2009
       to find what circulated on the 15th

`Tracking in house use <#inhouseuse>`__
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Using the Circulation statistics reporting wizard you can run reports on
in house usage of items simply by choosing 'Local Use' from the 'Type'
pull down:

In House Use Stats
|image912|

`Serials Statistics <#serialstats>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    **Note**

    These reports are limited in what data they can look at, so it's
    often recommended to use `custom reports <#customreports>`__ for
    official end of the year statistics.

Using the form provided, choose how you would like to list the serials
in your system.

Serials Statistics
|image913|

If you choose to output to the browser your results will print to the
screen.

Serials Results
|image914|

You can also choose to export to a file that you can manipulate to your
needs.

`Holds Statistics <#holdstats>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    **Note**

    These reports are limited in what data they can look at, so it's
    often recommended to use `custom reports <#customreports>`__ for
    official end of the year statistics.

Using the form provided you can see statistics for holds placed, filled,
cancelled and more at your library. From the form choose what value you
want to display in the column and what value to show in the row. You can
also choose from the filters on the far right of the form.

Hold Statistics Form
|image915|

If you choose to output to the browser your results will print to the
screen.

Hold Stats Results
|image916|

You can also choose to export to a file that you can manipulate to your
needs.

`Patrons with the most checkouts <#mostcheckouts>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This report will simply list the patrons who have the most checkouts.

Patrons with the most checkouts form
|image917|

If you choose to output to the browser your results will print to the
screen.

Top checkouts results
|image918|

You can also choose to export to a file that you can manipulate to your
needs.

`Most Circulated Items <#mostcirculated>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This report will simply list the items that have the been checked out
the most.

Most Circulation Items Form
|image919|

If you choose to output to the browser your results will print to the
screen.

Top Circulation Items Results
|image920|

You can also choose to export to a file that you can manipulate to your
needs.

`Patrons with no checkouts <#patnocheckouts>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This report will list for you the patrons in your system who haven't
checked any items out.

Patrons with no Checkouts
|image921|

If you choose to output to the browser your results will print to the
screen.

Results for Patrons with no Checkouts
|image922|

You can also choose to export to a file that you can manipulate to your
needs.

`Items with no checkouts <#itemnocheckouts>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This report will list items in your collection that have never been
checked out.

Items with No Checkouts
|image923|

If you choose to output to the browser your results will print to the
screen.

Items with no checkouts results
|image924|

You can also choose to export to a file that you can manipulate to your
needs.

`Catalog by Item Type <#catbyitem>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This report will list the total number of items of each item type per
branch.

Catalog by Item Type
|image925|

If you choose to output to the browser your results will print to the
screen.

Total of Items by Type and Branch
|image926|

You can also choose to export to a file that you can manipulate to your
needs.

`Lost Items <#lostreport>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This report will allow you to generate a list of items that have been
marked as Lost within the system

Lost Items Report
|image927|

`Average Loan Time <#avloantime>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This report will list the average time items are out on loan based on
the criteria you enter:

Average Checkout Period Form
|image928|

If you choose to output to the browser your results will print to the
screen.

Average Checkout Period Results
|image929|

You can also choose to export to a file that you can manipulate to your
needs.

`Report Dictionary <#reportdic>`__
----------------------------------

The report dictionary is a way to pre-define common filters you'd like
to apply to your reports. This is a good way to add in filters that the
report wizard doesn't include by default. To add a new definition, or
filter, click 'New Definition' on the Reports Dictionary page and follow
the 4 step process.

Step 1: Name the definition and provide a description if necessary

Create a Definition
|image930|

Step 2: Choose the module that the will be queried.

Select Koha Module
|image931|

Step 3: Choose columns to query from the tables presented.

Choose columns
|image932|

Step 4: Choose the value(s) from the field(s). These will be
automatically populated with options available in your database.

Choose fields and values
|image933|

Confirm your selections to save the definition.

Confirm Definition
|image934|

Your definitions will all appear on the Reports Dictionary page

Reports Dictionary Listing
|image935|

Then when generating reports on the module you created the value for you
will see an option to limit by the definition at the bottom of the usual
filters.

Dictionary Limit Option
|image936|
