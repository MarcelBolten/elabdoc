.. _user-guide:

User guide
==========

This guide assumes you already have a working installation of eLabFTW on a server.

General overview
----------------

The principles
~~~~~~~~~~~~~~
By default, experiments and database items are restricted to a team. But users can choose to extend this to all registered users.

Experiments showed on the Experiments tab (the main tab) are yours only. To see experiments from other people in the team use the Search page or enable it from your User Control Panel.

Database items are common to the team and can be edited by anyone from the team.

Creating an account
~~~~~~~~~~~~~~~~~~~
New users need to register an account on the register page (`/register.php`), accessible from the login page. They need to select a team from the list.

By default, newly created accounts are disabled. The admin of the team needs to validate them by going into the admin panel and activate new users.

Experiments
-----------
Once logged in, you can create an experiment by clicking the «Create» button on the top right of the screen. You will be presented with an «edition» page (you can see 'mode=edit' in the URL); the two other modes being 'view': display a single experiment, and 'show': display a list of experiments.

See the getting started video:

.. raw:: html

    <iframe width="560" height="315" src="https://www.youtube.com/embed/k30uyH2_LMM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Templates
~~~~~~~~~
Each user can have his own Experiments templates. Go to your user panel to create/edit your templates. You can export them as .elabftw.tpl files, and import them, too! They will be accessible from the «Create new» dropdown menu.

Edit mode
~~~~~~~~~

Tags
````
The tags allow you to easily group experiments together. You can think of it as folders, but more powerful because each experiment can have many tags, thus allowing you to cross-search efficiently!
All experiments with the same tag will be accessible by clicking this tag or searching for it. To validate a tag, press Enter or click outside the input field. It is saved immediatly. The number of tags is not limited. Click on a tag to remove it (in edit mode). Tags are common to a team. Autocompletion favors the reuse of existing tags.

.. image:: img/quick_tags.gif

Date
````
The date is today's date by default, in the format YYYYMMDD. You can edit it as you wish. The real creation date/time is stored in the database in another column.

Status
``````
This useful feature lets you set the 'status' of an experiment. By default you can have :

- Running (selected upon creation)
- Need to be redone
- Success
- Fail

These status can be modified completely by the admin in the admin panel.

Title
`````
The title of your experiment. A duplicated experiment will have a «I» character appended to the title upon creation.

Experiment (body)
`````````````````
This is where you describe your experiment and write your results. It is a rich text editor where you can have formatting, tables, colors, images, links, etc… To insert an image in this field, first upload it by dragging it in the 'Attach files' block. Then you will see a new block appear just below, with a thumbnail of the file, its name and size. Right click on the image and select «Copy link location». Next, click on the «Insert/edit image» button in the toolbar of the rich text editor (third button before the last).
Paste the link location. Press OK. That's it, you have an image inside your main text.

Make sure to right click on the thumbnail and not on the name!

Steps
`````
Steps are a way to list the things one need to do during the experiment. So you can write several steps, and once they are done, click the checkbox to declare them finished. This is quite useful for long experiments spanning over several days, where the "Next step" will be shown in Show mode (index list), so you can see at one glance what is the next thing to do for this particular experiment.

Note that you can also declare steps in a template.

Linked items
````````````
This field allows you to link an item from the database. Just begin to type the name of what you want to link and you will see an autocompletion list appear. Select the one you want and press Enter. The number of links is not limited.

This feature can also be used to link an experiment to a particular Project. If you have a «Project» Item Type and have a Project item in your database, you will then be able to see all experiments linked to this project by clicking the Link icon.

Attach a file
`````````````
You can click this region to open a file browser, or drag-and-drop a file inside. The file size limit depends on the server configuration, and there is no limit on file type. If you upload an image, a thumbnail will be created. There is no limit on the number of files you can attach to an experiment.

When you are done, click the «Save and go back» button.

You are now in view mode.

Ellipsis menu (the three dots on the top right)
```````````````````````````````````````````````
This menu contains an entry to Manage Permissions, allowing you to restrict or extend the read and write permissions for that experiment.
By default, all experiments can be viewed by other team members. If you wish to restrict viewing of a particular experiment, set this to 'Only me'. An admin can also create groups of users, and users can set the visibility of experiments to this group only.

The Switch Editor entry will switch from the WYSIWYG editor (TinyMCE) to the markdown editor. And the Delete entry is to remove the experiment.

View mode of experiment
~~~~~~~~~~~~~~~~~~~~~~~
In the view mode, several actions are accessible under the date.

Edit
````
Go into edit mode.

Duplicate
`````````
Duplicating an experiment allows you to create a new item with the same Title, tags, body and links, but with today's date and a running status. Uploaded files are not duplicated. A «I» character will be added to the title to denote that it is a replicate.

Make a pdf
``````````
Clicking this will create a pdf from your experiment. The generated pdf will contain all the information related to the experiment.

Make a zip archive
``````````````````
A zip archive will contain the generated pdf of the experiment + any attached files present.

Lock
````
Once locked, an experiment cannot be modified anymore. Unless you unlock it. If it is locked by someone with locking powers (the PI), you will not be able to unlock it.

Timestamp
`````````
An experiment can be timestamped if its status is timestampable (the default 'Running' status is not). Once timestamped it cannot be edited anymore.

What happens when you timestamp an experiment :

- a pdf is generated
- a sha256 sum of this pdf is generated
- this data is sent to the Time Stamping Authority (TSA)
- they timestamp it
- we get a token back

More info here: https://en.wikipedia.org/wiki/Trusted_timestamping

eLabFTW uses :rfc:`3161` for timestamping. So any TSA providing a :rfc:`3161` compatible way of timestamping will work.

By default, eLabFTW is configured to use the timestamping server of `pki.dfn.de <https://www.pki.dfn.de/zeitstempeldienst/>`_. It allows you to timestamp your experiments for free if you are doing research.

You can also use a different timestamping provider. For instance `SafeCreative <https://tsa.safecreative.org/>`_ is known to work. Download their `certificate <https://tsa.safecreative.org/certificate>`_ in the elabftw folder and configure your timestamping settings to use that file. The URL is `https://tsa.safecreative.org <https://tsa.safecreative.org>`_. You are limited to 5 timestamps by day and IP address.

elabid
``````
In the bottom right part of the experiment, you can see something like: «Unique elabid: 20150526-e72646c3ecf59b4f72147a52707629150bca0f91». This number is unique to each experiment. You can use it to reference an experiment with an external database.

Comments
````````
People can leave comments on experiments. They cannot edit your experiment, but they can leave a comment. The owner of the experiment will receive an email if someone comment their experiment.

Database
--------
Same as experiments for a lot of things, except there is no status, but a rating system (little stars). You can store any type of items inside, the admin can edit the available types of items.

In view mode, click the link icon to show all experiments linked with this item.

Examples of database items types:

* antibodies
* microscopes
* plasmids
* drugs
* chemicals
* equipment
* projects

Team
----
This page presents the members and some statistics about the team. You'll also find here a molecule drawer. Note: this molecule drawer can be displayed when you create an experiment. Go to your user control panel to adjust this setting.

Scheduler
~~~~~~~~~
Since version 1.3.0, a scheduler is available to book equipment. First you need to set some item types as bookable from the Admin Panel. After you select an item from the Scheduler page, and use the calendar to book it.

See the video about the scheduler below:

.. raw:: html

   <iframe width="560" height="315" src="https://www.youtube.com/embed/lGESXKV2-CM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

User panel
----------

The user panel is where you can adjust preferences for your account. You can access it by clicking the link in the bottom left of every page, or through the user menu in the top right.

Preferences tab
~~~~~~~~~~~~~~~
From here you can select a language, adjust the display settings, change the keyboard shortcuts, modify the PDF settings, select a different text editor and set the default permission settings.

Account tab
~~~~~~~~~~~
Modify your password, name and contact information.
You can also enable/disbale :ref:`two-factor authentication <faq2fa>` (2FA).

Templates tab
~~~~~~~~~~~~~
Manage your templates. Once a template has been created, you can add tags, steps and links to it. It will then be available from the Create menu.

Api keys tab
~~~~~~~~~~~~
Create an API key for your account from this page. API keys are needed if you wish to access resources through the REST API.

Miscellaneous
-------------

You can export experiments in .zip. If the experiment was timestamped you will find in the archive the timestamped pdf and the corresponding .asn1 token.

You can export and import items from the database (it can be several items).

Press 't' to have a TODO list.

.. raw:: html

   <iframe width="560" height="315" src="https://www.youtube.com/embed/maylkcTAarg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

In the editor, press Ctrl+shift+d to get today's date inserted at cursor position.
