Exercise 2: RStudio
===================

Install RStudio. RStudio is a powerful and user-friendly environment for R and Python data science.

#. Prepare the virtual machine

.. code-block:: console

   $ sudo dnf update
   $ sudo dnf install epel-release
   $ sudo dnf config-manager --set-enabled crb

#. Install R

.. code-block:: console
   $ sudo dnf install
   
Dependency Tree:

.. code-block:: bash
   ....
	Transaction Summary
	================================================================================
	Install  544 Packages
	
	Total download size: 540 M
	Installed size: 1.4 G
	Is this ok [y/N]: y

Check the installed version

.. code-block:: console
   $ R --version
