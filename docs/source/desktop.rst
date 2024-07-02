Exercise 4: Remote Desktop
=====

Enable the remote desktop experience.

1. Prepare the virtual machine

.. code-block:: bash

   sudo dnf install epel-release

2. Set up the Workstation environment

.. code-block:: bash

   sudo dnf group install "Workstation"

3. Set the graphical mode

.. code-block:: bash

   sudo systemctl set-default graphical

4. Update the Firewall

.. code-block:: bash

   sudo dnf install firewalld
   sudo systemctl start firewalld
   sudo firewall-cmd --permanent --add-port=3389/tcp
   sudo firewall-cmd --reload
   sudo firewall-cmd --list-all

5. Install Xrdp

.. code-block:: bash

   sudo dnf install xrdp
   sudo systemctl start xrdp
   sudo systemctl enable xrdp

6. Create a new user

.. code-block:: bash

   sudo useradd johnsmith
   sudo passwd johnsmith

7. Reboot the virtual machine

.. code-block:: bash

   sudo reboot