Exercise 3: JupyterLab
=====

Install JupyterLab. JupyterLab is an extensible environment for interactive and reproducible computing, based on the Jupyter Notebook and Architecture.

1. Prepare the virtual machine

.. code-block:: bash

   sudo dnf install wget curl nano unzip yum-utils

2. Install Nginx

.. code-block:: bash

   sudo nano /etc/yum.repos.d/nginx.repo

.. code-block:: bash

   [nginx-stable]
   name=nginx stable repo
   baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
   gpgcheck=1
   enabled=1
   gpgkey=https://nginx.org/keys/nginx_signing.key
   module_hotfixes=true

   [nginx-mainline]
   name=nginx mainline repo
   baseurl=http://nginx.org/packages/mainline/centos/$releasever/$basearch/
   gpgcheck=1
   enabled=0
   gpgkey=https://nginx.org/keys/nginx_signing.key
   module_hotfixes=true

.. code-block:: bash

   sudo dnf install nginx
   nginx -v
   sudo systemctl enable nginx --now
   sudo systemctl status nginx

3. Install the PIP package manager

.. code-block:: bash

   sudo dnf install python3-pip

4. Install JupyterLab

.. code-block:: bash

   mkdir jupyterlab
   cd ~/jupyterlab
   python3 -m venv --system-site-packages jupyterlab_env
   source jupyterlab_env/bin/activate
   pip install --upgrade pip
   pip install jupyterlab

5. Update the Firewall

.. code-block:: bash

   sudo dnf install firewalld
   sudo systemctl start firewalld
   sudo firewall-cmd --permanent --add-port=8888/tcp
   sudo firewall-cmd --reload
   sudo firewall-cmd --list-all

6. Start JupyterLab

JupyterLab should open via your web browser. If it doesn't open, go to http://<Floating IP>:8888 with your web browser

.. code-block:: bash

   jupyter lab --ip 0.0.0.0