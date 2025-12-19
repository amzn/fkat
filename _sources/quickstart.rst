Quickstart
==========

This quickstart guide helps you quickly install and get ready to use FKAT.

Installing from PyPI
--------------------

.. code-block:: shell

   pip install amzn-fkat

Installing Locally for Development
-----------------------------------

#. Clone the repository
#. Install hatch:

   .. code-block:: shell

      pip install hatch

#. Create environment:

   .. code-block:: shell

      hatch env create

#. Build:

   .. code-block:: shell

      hatch build

#. Install:

   .. code-block:: shell

      pip install build/amzn_fkat-*.whl

#. In editable mode:

   .. code-block:: shell

      pip install -e ".[test]"

#. Enable `pre-commit <https://pre-commit.com>`_ hooks for contributions:

   .. code-block:: shell

      pip install -U pre-commit && pip install -U pre-commit-hooks && pre-commit install
