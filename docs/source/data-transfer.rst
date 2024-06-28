Exercise 1: Data Transfer
=====

1. In the same folder as your Private Key, create a text file

.. code-block:: bash

  vi helloworld.txt

2. Transfer the text file to your virtual machine

.. code-block:: bash

  scp -i <ssh-key>.pem helloworld.txt rocky@<IP Address>:/home/rocky
