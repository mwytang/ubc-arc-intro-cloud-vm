UBC ARC 2024 Summer School: Introduction to Cloud and Virtual Machines
===================================

In the afternoon session, participants will have the opportunity to have hands-on experience launching virtual machines and other resources in the community cloud.

Resources
--------
* **The Alliance Cloud Quick Start:** https://docs.alliancecan.ca/wiki/Cloud_Quick_Start
* **The Alliance Cloud Status (Health):** https://status.alliancecan.ca/ 
* **Rapid Access Service (RAS):** https://docs.alliancecan.ca/wiki/Cloud_RAS_Allocations
* **Nextcloud:** https://docs.alliancecan.ca/wiki/Nextcloud
* **UBC ARC Support:** arc.support@ubc.ca 

Virtual Machine
---------------
For the exercises in this workshop, a virtual machine with the following configuration is required.

* Cores: 2 cores
* Memory: 3 GB
* Operating System: Rocky 9

Connect to the Virtual Machine
------------------------------

.. code-block:: bash

   ssh -i /path/to/private/key/<key>.pem rocky@<public ip>

If using Windows Subsystem for Linux, you may need update the permissions


.. code-block:: bash

   chmod 600 <name of private key file>

Exercises
--------
.. toctree::

   data-transfer
   rstudio
   jupyterlab
   desktop
