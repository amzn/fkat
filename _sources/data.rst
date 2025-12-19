:mod:`data`
===========

This module provides specialized data loading components for efficient handling and processing of datasets.

.. toctree::
   :maxdepth: 1

   data/datasets
   data/samplers
   data/shm
   data/sharded

.. automodule:: fkat.data
.. currentmodule:: fkat.data


DictDataLoader
--------------

.. autoclass:: DictDataLoader
   :members:


DataModule
----------

.. autoclass:: DataModule
   :members:

.. autoclass:: PersistStates
   :members:

.. autoclass:: RestoreStates
   :members:


ShmDataLoader
-------------

.. autoclass:: ShmDataLoader
   :members:


ShardedDataLoader
-----------------

.. autoclass:: ShardedDataLoader
   :members:
