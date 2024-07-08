Exercise 1: Data Transfer
=====

Transfer data to the virtual machine.

1. In the same folder as your Private Key, create a text file. On Windows, you can Notepad or Notepad++

.. code-block:: bash

  nano helloworld.txt

2. Transfer the text file to your virtual machine

.. code-block:: bash

  scp -i <ssh-key>.pem helloworld.txt rocky@<IP Address>:/home/rocky
