=======================
django-tutorial-starter
=======================

This is a functional implementation of the `official Django tutorial`__. It should only
be used for experimentation and demonstration purposes, it is unsuitable for use as a
base for production sites.

__ https://docs.djangoproject.com/en/dev/intro/tutorial01/


Running this project
====================

To get this project running::

    # Create and activate a virtualenv using your favourite method
    python -mvenv venv
    . venv/bin/activate

    # Clone and install requirements
    git clone https://github.com/radiac/django-tutorial-starter.git tutorial
    cd tutorial
    pip install -r requirements.txt

    # Run
    ./manage.py migrate
    ./manage.py createsuperuser
    ./manage.py runserver 0:8000


In this project
===============

The project aims to follow the official tutorial as closely as practical, while
tweaking things enough to be useful.

There are the following changes:

* Project requirements are defined in ``requirements.in`` and pinned to
  ``requirements.txt`` using `pip-tools <https://pypi.org/project/pip-tools/>`_.
* All ``polls`` templates have been wrapped in ``{% block content %}``, and extend
  ``mysite/templates/base.html``, which includes a placeholder static ``site.css`` and
  ``site.js``.
* No background image in ``polls/static/polls/style.css``.
* No admin template override (no file at ``templates/admin/base_site.html``).
* Root url ``/`` redirects to ``/polls/`` for convenience.
* Minor changes may be introduced by ``black`` and ``isort``.

We will aim to keep this repository up-to-date with the latest LTS release of Django.


Why does this exist?
====================

This repository is intended as a starting point for tutorials of third party apps.

Given its prominence, most Django developers will already be familiar with the official
tutorial, or at least the features it uses. Developers can point their users at this
repo to give them a tutorial foundation which is simple enough to be easy to understand,
but just complex enough to be well-suited to build into more advanced concepts.

It also serves as a good template for building an example project in your own repo.


Used by
=======

This project is currently used by:

* `django-fastview <https://github.com/radiac/django-fastview>`_ -
  `Tutorial <https://django-fastview.readthedocs.io/en/latest/tutorial/index.html>`_,
  `Example project <https://github.com/radiac/django-fastview/tree/develop/docs>`_


Changelog
=========

2022-01-15
----------

* Initial release using Django 3.2 and associated tutorial
