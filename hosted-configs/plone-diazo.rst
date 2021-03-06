.. Note:: `View config on GitHub`_
  :class: alert alert-info

Plone + Diazo
=============

How to theme the award-winning, Python-based, Plone CMS. You want to take the new ``Diazo`` theming engine for ``Plone`` for a spin.

Part I: Setting up Plone
~~~~~~~~~~~~~~~~~~~~~~~~

Follow these steps::

    $ virtualenv-2.7 .
    $ bin/pip install zc.buildout
    $ bin/buildout init

Edit the contents of **buildout.cfg** to contain *only*::

    [buildout]
    extends = https://raw.github.com/pythonpackages/buildout-plone/master/4.3.x

    [plone]
    resources = ${buildout:directory}/resources

Then run::

    $ bin/buildout

Followed by::

    $ bin/plone fg

At which point you should see::

    2012-01-09 19:53:26 INFO ZServer HTTP server started at Mon Jan  9 19:53:26
    2012
        Hostname: 0.0.0.0
        Port: 8080
    2012-01-09 19:53:29 WARNING ZODB.blob (13380) Blob dir
    /Users/aclark/Developer/test-plone/var/blobstorage/ has insecure mode setting
    2012-01-09 19:53:35 INFO PloneHotfix20110928 Hotfix installed.
    2012-01-09 19:53:35 INFO Zope Ready to handle requests

Open the following URL in your web browser:

 - http://127.0.0.1:8080

You should see:

.. image:: https://github.com/pythonpackages/pythonpackages-docs/raw/master/hosted-configs/plone1.png
   :class: thumbnail

Create a new Plone site then move on to Part II.

Part II: Setting up a new theme
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Now CTRL-C Plone and do the following::

    $ mkdir -p resources/theme/my.theme
    $ touch resources/theme/my.theme/index.html
    $ touch resources/theme/my.theme/rules.xml

Now restart Plone. Click on `Site Setup -> Diazo theme -> Advanced settings`. Make your
fields look like this:

.. image:: https://github.com/pythonpackages/pythonpackages-docs/raw/master/hosted-configs/plone-diazo1.png
   :class: thumbnail

Save the form. Select `Basic settings`. Select `Other` and enable your theme:

.. image:: https://github.com/pythonpackages/pythonpackages-docs/raw/master/hosted-configs/plone-diazo2.png
   :class: thumbnail

Return to the site root. You should see… no change! One more step. Edit
index.html to contain::

    <div id="content"><h1>You can haz it!</h1></div>

And rules.xml to contain::

    <rules
        xmlns="http://namespaces.plone.org/diazo"
        xmlns:css="http://namespaces.plone.org/diazo/css"
        xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

        <theme href="index.html" />

        <append css:theme="#content" css:content="#content"/>

    </rules>

Open the following URL in your web browser:

 - http://localhost:8080/Plone

.. Note:: Note the change from 127.0.0.1 to localhost

You should see:

.. image:: https://github.com/pythonpackages/pythonpackages-docs/raw/master/hosted-configs/plone-diazo3.png
   :class: thumbnail

Conclusion
~~~~~~~~~~

This, along with http://diazo.org should be all any web-savvy person (who does not know any Python or Plone) needs to get started theming Plone.

.. include:: ../disqus.html

.. _`View config on GitHub`: https://github.com/pythonpackages/buildout-plone/blob/master/4.3.x
