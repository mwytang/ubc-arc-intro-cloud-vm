Exercise 2: RStudio
===================

Install RStudio. RStudio is a powerful and user-friendly environment for R and Python data science.

1. Prepare the virtual machine

.. code-block:: console

   $ sudo dnf update
   $ sudo dnf install epel-release
   $ sudo dnf config-manager --set-enabled crb

2. Install R

.. code-block:: console

   $ sudo dnf install R

3. Check the installed version of R

.. code-block:: console

   $ R --version

4. Install OpenSSL 1.1.0

.. code-block:: console

   $ sudo yum install -y make gcc perl-core pcre-devel wget zlib-devel
   $ wget https://www.openssl.org/source/openssl-1.1.0i.tar.gz
   $ tar -zxf openssl-1.1.0i.tar.gz
   $ cd openssl-1.1.0i

.. code-block:: console

   $ ./config
   $ make test
   $ make
   $ sudo make install

5. Export the PATH

.. code-block:: console

   $ export LD_LIBRARY_PATH=/usr/local/lib:/usr/local/lib64
   $ echo "export LD_LIBRARY_PATH=/usr/local/lib:/usr/local/lib64" >> ~/.bashrc
   $ source ~/.bashrc

6. Check the installed version

.. code-block:: console

   $ openssl version

7. Install RStudio

.. code-block:: console

   $ wget https://download2.rstudio.org/server/rhel9/x86_64/rstudio-server-rhel-2024.04.2-764-x86_64.rpm
   $ sudo yum install rstudio-server-rhel-2024.04.2-764-x86_64
   $ sudo systemctl status rstudio-server.service
   $ sudo systemctl enable rstudio-server.service

8. Update the firewall

.. code-block:: console

   $ sudo firewall-cmd --permanent --add-port=8787/tcp
   $ sudo firewall-cmd --reload
   $ semanage fcontext -a -t bin_t '/usr/lib/rstudio-server/bin(/.*)?'
   $ restorecon -r /usr/lib/rstudio-server/bin/
   $ systemctl restart rstudio-server

9. Create a new user

.. code-block:: console

   $ sudo useradd johnsmith
   $ passwd rock

9. Login to http://<Floating IP>:8787 with your preferred web browser
