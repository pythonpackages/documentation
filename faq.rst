
Frequently Asked Questions
==========================

If your question is not answered here, please `open a ticket`_.

How does pythonpackages.com differ from the Python Package Index (PyPI)?
------------------------------------------------------------------------

pythonpackages.com is not a package index, i.e. we do not host any files for download. We consume their (PyPI) API to display useful information about packages, as well as provide additional services to Python programmers to help package and release their software.

How does pythonpackages.com differ from Bitbucket, GitHub, etc?
---------------------------------------------------------------

pythonpackages.com is not a software repository. We consume their (GitHub) API to provide services to Python programmers to help package and release their software.

.. _`open a ticket`: http://bitbucket.org/pythonpackages/pythonpackages.com/issues/new

How do you make money?
----------------------
Developers are encouraged to use the free plan which includes a single "package slot" to evaluate the service. If the service provides significant value, they are encouraged to purchase a paid plan which includes some number of paid slots, depending on the plan. Additionally, paid plans allow access to some number of GitHub organization repositories, depending on the plan.

Is pythonpackages.com open source?
----------------------------------

The web application that powers pythonpackages.com is not open source, however it uses open source software where and when applicable, and permissible by license, in order to facilitate its operation. Furthermore, pythonpackages.com has a large committment to the open source software community in general, and strives to contribute as much as possible. All of pythonpackages.com's open source offerings are made available here: https://github.com/pythonpackages. And if you are curious, please see :ref:`why-not-open-source`.

.. _why-not-open-source:

Why isn't pythonpackages.com open source?
-----------------------------------------

In order to create a "minimum viable product", we chose to start closed source and open source later, as needed or possible (vs. the opposite). And it's logistically much harder to engineer a commercial service when the core web application is open source.

What does pythonpackages.com do for me that I can't do myself?
--------------------------------------------------------------

In order to publish software, Python developers are required to know a tremendous amount of information about the available packaging framework(s) e.g. distutils, setuptools, distribute, etc. Many Python programmers simply do not know, or care to know, about the details of Python packaging. pythonpackages.com provides services to help decrease the amount of knowledge necessary to publish Python software. Additionally, pythonpackages.com enables so-called "cloud releases" in which publishing can be done entirely "in the cloud" i.e. without requiring a local development environment. One popular scenario::

    Developer "Mary" is the author of "Mary's Awesome App". Mary develops her application on GitHub, where she can easily collaborate with other like-minded developers.

    One day Mary is on vacation, but still checking her email on her iPhone, when she receives a "Pull request" from "Josh" who is another open source developer on GitHub. Josh has informed Mary of a critical bug fix he made to her software. Further, he indicates that the tests have passed on Travis CI and the request is ready to be merged and released.

    Mary is naturally skeptical at first. The "old" Mary would never have considered performing a release without testing it on her laptop first! However, since her code has 100% test coverage and Josh is a reliable community member and she can ensure that the tests have passed and she is able to review the code sanity and security online via GitHub, she happily agrees to perform the release.

    Using the mobile-friendly user interface of pythonpackages.com with her iPhone, Mary presses the "Tag and release" button to publish a new release of Mary's Awesome App from GitHub to the Python Package Index. Mary goes back to her vacation. Josh goes back to fixing bugs. Users of Mary's Awesome App are enjoying the new release. The world is a better place.

Are there any videos?
---------------------

Yes!

Alpha videos
~~~~~~~~~~~~

A `demo video`_ for the alpha release was created for PyCon 2012. While the user interface has improved since then, the video demonstrates the basic concept of cloning a repository from GitHub and publishing it to the Python Package Index "in the cloud". 

Beta videos
~~~~~~~~~~~

Since then, `demo two`_ and `demo three`_ have been produced. If you watch only one of these, please watch `demo three`_.

.. _`demo video`: http://www.youtube.com/watch?v=bDJJATpF3mE&feature=plcp
.. _`demo two`: http://www.youtube.com/watch?v=VQlkCo2R3rA
.. _`demo three`: http://www.youtube.com/watch?v=v80cAfxo8hg

What is a brown bag release?
----------------------------

A brown-bag release is a release that is badly broken and cannot be used by some of all of the end users [1]_

Is there a roadmap? If so, what is it?
--------------------------------------

Yes. Please see the :ref:`roadmap`.

Why are you executing untrusted code in setup.py?
-------------------------------------------------

We are relying on Heroku platform security to mitigate any associated risks:

- http://policy.heroku.com/security

In particular, dyno isolation:

- https://devcenter.heroku.com/articles/dynos

Why not use setuptools-git instead of MANIFEST.in to specify additional files to distribute?
--------------------------------------------------------------------------------------------

Because the files used to create the distribution are not cloned by git, they are copied to pythonpackages.com via GitHub APIv3 [2]_

.. include:: disqus.html

.. [1] http://guide.python-distribute.org/specification.html#pre-releases

.. [2] http://developer.github.com/v3/git/trees
