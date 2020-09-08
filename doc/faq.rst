.. _faq:

Frequently asked questions
==========================

Is it totally free?
-------------------

YES. eLabFTW is free/libre software, so it is totally free of charge and always will be. `Read more about the free software philosophy <https://www.gnu.org/philosophy/free-sw.html>`_.

But how is it better than something I can buy?
----------------------------------------------

The difference is huge. Because eLabFTW is not only free (as in beer), but it is free (as in speech). This means that you can have a look at the code (and improve it) and you can also redistribute the code with your improvements.

But more importantly, you cannot trust your data with something that acts like a **black box**. What if the data you upload on the server of a company can be read by someone else? With eLabFTW, you install it on your own server, and you are the master of your data at all time.

What about patents and intellectual property?
---------------------------------------------

Since March 2013, the USA modified their law (see `America Invents Act <https://www.uspto.gov/patent/laws-and-regulations/leahy-smith-america-invents-act-implementation>`_) to switch from first-to-invent to first-inventor-to-file. This means that proving that you did this experiment before someone else has become less critical. It is only needed if you invented something, before someone put a patent on it (and you can prove it), and you want to keep using it as **prior user**.

Fortunately, eLabFTW allows rock solid `timestamping of your experiments <https://en.wikipedia.org/wiki/Trusted_timestamping#Trusted_.28digital.29_timestamping>`_. With just one click of a mouse, and for free, you can timestamp your work.

If needed, you can also choose another TimeStamping Authority allowing :rfc:`3161` timestamping.

Why use eLabFTW?
----------------

* **It's free and open source software**
* It improves the value of your experiments by allowing you to keep a good track of it
* It makes searching your data as easy as a google search
* Everything can be organized in your lab
* It makes it easy to share information between co-workers or collaborators
* It is simple to install and to keep up to date
* **It works for Windows, Mac OS X, Linux, BSD, Solaris, etc…**
* Protected access with login/password (password is very securely stored as salted SHA-512 sum)
* It can be used by multiple users at the same time
* **It can be used by multiple teams**
* You can have templates for experiments you do often
* **You can export an experiment as a PDF**
* **You can timestamp an experiment so it is legally strong**
* You can export one or several experiments as a ZIP archive
* You can duplicate experiments in one click
* There is advanced search capabilities
* You can write in Markdown
* The tagging system allows you to keep track of family of experiments
* Experiments can have color coded statuses (that you can edit at will)
* You can link an experiment with an item from the database to retrieve in a click the plasmid/sirna/antibody/chemical you used
* And it works the other way around, you can find all experiments done with a particular item from the database!
* There is a locking mechanism preventing further edition
* You can comment on an experiment (if it's not your experiment)
* You can import your old database stored in an excel file
* You can use it in your language
* :doc:`and much more… <features>`

You also have to consider the fact that installing eLabFTW on your own server means that no one will be able to snoop on your data. If you have ever used Evernote or basically any online ELN that says «Free», read carefully the privacy policy, you might be surprised what they allow themselves to do under the cover of «to improve your experience»…


Is this system stable? Can I trust my data with it?
---------------------------------------------------

Yes. It is used in numerous research centers all over the world since a few years now and if an issue is found it is quickly reported and fixed.

However, having an automated :ref:`backup <backup>` strategy is mandatory in order to be sure **nothing will be lost**.

Being able to do backups is yet another advantage over paper (you can't backup paper!).

Who else is using it?
---------------------

Here are some places running eLabFTW (non-exhaustive list):

* Cardiff University
* Hannover Medical School
* Helmholtz Zentrum Berlin für Materialien und Energie GmbH
* Indian Institute of Science, Bangalore
* Indian Institute of Technology, Delhi
* INRIA
* Institut Curie
* Karolinska Institutet
* Kuwait University
* Max-Planck-Institute of Quantum Optics
* Texas Tech University
* UMC Utrecht
* University of Alberta
* University of California
* University of Chicago
* University of Helsinki
* University of North Dakota
* University of Tennessee
* University of Warwick
* Uppsala University
* Washington University
* Weizmann Institute

Is the data encrypted?
----------------------

The data is encrypted when travelling from your browser to the server with the highest quality encryption currently available (TLSv1.2 with modern ciphers).

The passwords are not recoverable in case of a breach.

Only manually validated accounts can interact with the software. It is secure by default.

Is eLabFTW still maintained?
----------------------------

As of |today| I'm still actively working on it. Improvements are coming in a steady flow. There are good chances that I will continue to do so for a few years. In the unlikely event I'm not able to work on it anymore, anyone can continue the work, as the source code is available and well commented.

Will I be able to import my plasmids/antibodies/whatever in the database from a Excel file?
-------------------------------------------------------------------------------------------

Yes, in the admin panel, click on the Import CSV link and follow the instructions.

Can I try it before I install it?
---------------------------------

Sure, there is a demo online here: `eLabFTW live DEMO <https://demo.elabftw.net>`_

Is it compliant to 21CFR Part 11?
---------------------------------

1. Closed system: eLabFTW requires unique credentials to access the system. A system of permissions and roles allow fine control of what can be seen by whom.

2. Experiments and database items (protocols, reagents, cell lines...) are considered signable by the locking mechanism that timestamps and locks an entity in place.

3. Trusted timestamping: RFC3161 Trusted Timestamping is available for experiments. A specific PDF is generated and timestamped cryptographically to prove anteriority if needed in a court of law.

4. Audit trail: changes to entries are internally recorded and cannot be tampered with by users. A version history is available.

5. Retention of records: a setting allows to disable the possibility to delete records entirely.

6. Copies of records: you can export your data in PDF, ZIP archives or CSV files very easily.

7. Password policy: passwords are securely stored in the database and security mechanisms such as preventing too many authentication tries are in place.

What about compliance to standards?
-----------------------------------
eLabFTW tries to comply to the following standards :

* `Code of Federal Regulations Title 21, paragraph 11 <http://www.accessdata.fda.gov/scripts/cdrh/cfdocs/cfcfr/CFRSearch.cfm?CFRPart=11>`_
* `FERPA <http://www2.ed.gov/policy/gen/guid/fpco/ferpa/index.html>`_
* `HIPAA <http://www.hhs.gov/ocr/privacy/>`_
* `FISMA <https://en.wikipedia.org/wiki/Federal_Information_Security_Management_Act_of_2002#Compliance_framework_defined_by_FISMA_and_supporting_standards>`_

What are the technical specifications?
--------------------------------------

eLabFTW is a server software that should be installed on a server.

**Requirements for the server**

The operating system of the server can be any. At least 2Gb of RAM, a decent processor (> 2GHz) and an SSD disk with at least 1 Gb free.

The best is to have `Docker <https://www.docker.com>`_ installed. Otherwise, make sure to have:

* a webserver (nginx, apache, cherokee, lighttpd, …) with HTTPS enabled
* `PHP <https://secure.php.net/>`_ version > 7.3
* `Composer <https://getcomposer.org/>`_
* `MySQL <https://www.mysql.com/>`_ version > 5.5

**Requirements for the client**
- Any operating system with any browser (recent version).

How to have folders or projects grouping experiments?
-----------------------------------------------------

First, forget about folders, use tags. They are much more powerful! Because an experiment can have many tags, whereas it can only be in one folder. Tags can be used to group experiments by project, by microscope, by collaborator, by whatever you want, all at the same time, allowing you to do cross-searchs.

Next, go to the Admin Panel and create a type of item: "Project". Go to the Database tab and create a new "Project" describing a group of experiments. Go to the Experiments tab and create an experiment. In the field "Link to database", type the name of the project and click on the autocompletion field appearing, and press enter (or click outside). This experiment is now linked to the project. So you can easily go to the project description from the experiment, but more importantly, you can from the Project entry, click the "Show related" icon (chainlink) and display all experiments linked to this project!

Another solution is to create an experiment that would be sort of a meta experiment, listing all the sub-experiments pertaining to the project, with links (you can create links in the body easily by typing '#' and some words from the title).

Select the approach that you prefer :)

--------------------

.. This was the common errors page, but it is deprecated now thanks to Docker :) I moved it in FAQ to avoid cluttering the left pane.

Failed creating *uploads/* directory
------------------------------------

If eLabFTW couldn't create an *uploads/* or *cache/* folder, that's because the httpd user (www-data on Debian/Ubuntu) didn't have the necessary rights. To fix it you need to:

1. Find what is the user/group of the web server. There is a good chance that it is www-data. But it might also be something else.

2. Now that you know the user/group of the webserver, you can do that (example is shown with www-data, but adapt to your need):

.. code-block:: bash

    cd /path/to/elabftw
    mkdir uploads cache
    chown www-data:www-data uploads cache
    chmod 400 config.php

The last line is to keep your config file secure. It might fail because the file is not there yet. Finish the install and do it after then.

I can't upload a file bigger than 2 Mb
--------------------------------------

Edit the file php.ini and change the value of upload_max_filesize to something bigger, example:

.. code-block:: bash

    upload_max_filesize = 128M

.. warning:: Don't forget to remove the `;` at the beginning of the line!

I can't export my (numerous) experiments in zip, I get an error 500
-------------------------------------------------------------------

Edit the file `/etc/php/php.ini` or any file called php.ini somewhere on your filesystem. Try `sudo updatedb;locate php.ini`. For XAMPP install, it is in the config folder of XAMPP.
Now that you have located the file and opened it in a text editor, search for `memory_limit` and increase it to what you wish. `Official documentation on memory_limit <http://php.net/manual/en/ini.core.php#ini.memory-limit>`_.

You can also increase the value of max_execution_time and max_input_time.
Then restart your webserver:

.. code-block:: bash

    sudo service apache2 restart

For nginx, you can also add `fastcgi_read_timeout 300;` in the `http` section.

Languages don't work
--------------------

eLabFTW uses `gettext <https://en.wikipedia.org/wiki/Gettext>`_ to translate text. This means that you need to have the associated locales on the server.
To see what locale you have::

    locale -a

To add a locale, edit the file `/etc/locale.gen` and uncomment (remove the #) the locales you want. If you don't find this file you can try directly the command::

    locale-gen fr_FR.UTF-8

Replace with the locale you want, of course.
See :doc:`here <contributing>` to see a list of languages (and locales) supported by eLabFTW.
Then do::

    sudo locale-gen

And reload the webserver.

Time is wrong
-------------

Make sure you configured properly the TZ environment variable for both docker images. See `example config <https://github.com/elabftw/elabimg/blob/master/src/docker-compose.yml-EXAMPLE>`_.

How to change the team of a user?
---------------------------------

There is two ways to do that:

* if the user registered in the wrong team, the Sysadmin can simply change the team from the Sysadmin panel
* if the user switched team, old team needs to Archive the user (from the Admin panel), and user needs to register a new account (same email can be used) in the new team

Can I change the date format?
-----------------------------

No. The date in eLabFTW (YYYYMMDD) follows ISO 8601 standard and allowing a user to change the format would only bring confusion.

.. _faq2fa:

What App can I use for two-factor authentication (2FA) and what settings are used?
----------------------------------------------------------------------------------

It should be possible to use nearly any available 2FA app (`Play Store <https://play.google.com/store/search?q=2FA&c=apps>`_ and `App Store <https://theappstore.org/search.php?search=2fa&platform=software>`_) that supports the time-based one-time password algorithm (TOTP). Setting up 2FA is very easy, you only need to scan the QR-code. However, also a manual set up is possible with the provided secret. eLabFTW employs commonly used settings (HMAC-SHA-1 algorithm, 6 digits and a period of 30 seconds). Under the hood eLabFTW uses the `PHP library for Two Factor Authentication <https://github.com/RobThree/TwoFactorAuth>`_.

What is the meaning of 'FTW'?
-----------------------------

One of those:

- For The World
- For Those Wondering
- For The Worms
- Forever Two Wheels
- Free The Wookies
- Forward The Word
- Forever Together Whenever
- Face The World
- Forget The World
- Free To Watch
- Feed The World
- Feel The Wind
- Feel The Wrath
- Fight To Win
- Find The Waldo
- Finding The Way
- Flying Training Wing
- Follow The Way
- For The Wii
- For The Win
- For The Wolf
- Free The Weed
- Free The Whales
- From The Wilderness
- Freedom To Work
- For The Warriors
- Full Time Workers
- Fabricated To Win
- Furiously Taunted Wookies
- Flash The Watch
