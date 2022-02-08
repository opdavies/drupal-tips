Drupal tips
###########

A collection of tips and tricks for working with `Drupal <https://www.drupal.org>`_ code. Ideas and PRs welcome.

Inspired by https://github.com/PovilasKorop/laravel-tips.

.. contents::
  :depth: 2

Services
========

Using a class name as a service name
------------------------------------

Before:

.. code:: yaml

  # my_module.services.yml

  services:
    my_module.example_service:
      class: Drupal\my_module\Service\ExampleService

After:

.. code:: yaml

  # my_module.services.yml

  services:
    Drupal\my_module\Service\ExampleService: []

Automatically inject dependencies with autowiring
-------------------------------------------------

Before:

.. code:: yaml

  # my_module.services.yml

  services:
    Drupal\my_module\Service\ExampleService:
      arguments: ['@entity_type.manager']

After:

.. code:: yaml

  # my_module.services.yml

  services:
    Drupal\my_module\Service\ExampleService:
      autowire: true

Automated testing
=================

* `Workshop notes <https://github.com/opdavies/workshop-drupal-automated-testing>`_
* `Workshop code <https://github.com/opdavies/workshop-drupal-automated-testing-code>`_
