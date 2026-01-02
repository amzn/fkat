Crash Detector
===============

.. autoclass:: fkat.pytorch.callbacks.monitoring.CrashDetector
   :members:
   :undoc-members:
   :show-inheritance:

Overview
--------

The ``CrashDetector`` callback monitors for process crashes during training and logs detailed error information including PID, rank, error messages, and stack traces.

Usage
-----

Basic usage:

.. code-block:: python

   from fkat.pytorch.callbacks.monitoring import CrashDetector
   import lightning as L

   callback = CrashDetector()
   trainer = L.Trainer(callbacks=[callback])

Custom tags:

.. code-block:: python

   callback = CrashDetector(
       error_tag="training_error",
       crash_info_tag="crash_details"
   )

Features
--------

- **Process monitoring**: Monitors main training process for crashes
- **Detailed crash info**: Captures PID, rank, exit code, signal, and timestamp
- **Exception handling**: Logs full stack traces for exceptions
- **MLflow artifacts**: Automatically logs crash info to MLflow artifacts (if MLflow logger is configured)
- **Rank-aware**: Only runs on local rank 0
- **Queue-based**: Uses multiprocessing queue for crash reporting

Crash Information
-----------------

When a crash is detected, the following information is logged:

- ``pid``: Process ID of the crashed process
- ``rank``: Global rank of the process
- ``exit_code``: Exit code of the process
- ``signal``: Signal that terminated the process (if any)
- ``error``: Error message (for exceptions)
- ``stacktrace``: Full stack trace (for exceptions)
- ``timestamp``: UTC timestamp of the crash

MLflow Integration
------------------

If an MLflow logger is configured, crash information is automatically logged as an artifact in the ``crashes/`` directory. This allows you to review crash details in the MLflow UI alongside other training metrics and artifacts.
