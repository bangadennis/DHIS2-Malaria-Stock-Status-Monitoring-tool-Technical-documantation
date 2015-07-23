Development tools
============================
Below is a description of the development tools and technologies used for the test
instance.

MySQL database
-------------
A MySQL database is used to store data.

However, another database like PostgreSQL can also be used.

The choice was purely due to the rapid turn around time.


PHP and Apache2 for the server side
-----------------------------------
The scripting language PHP and web server Apache2 were used for the server
side logic.

No PHP framework is used.

DHIS2 Web API Querying - JavaScript, AJAX, jQuery
------------------------
To query the JSON API for data, JavaScript and jQuery were used.

AJAX asynchronous POST was used to send data to the PHP scripts to commit
to the database.


HTML5, Bootstrap, Font-Awesome, JavaScript, jQuery for user interface
---------------------------------------------------------------------
Since this is a Web APP, the interface is coded in HTML5 with Bootstrap &
Font-Awesome frameworks incorporated to provide a better user experience
JavaScript and jQuery are also used to make the interface responsive and
event/data driven.




.. The ``.env`` file holds confidential configuration information. For that
.. reason, it is not tracked in version control ( version control has an example
.. ``.env`` whose values should **not** be used in production ).

.. A proper ``.env`` file should set the following values up:

.. .. code-block:: text

..     SECRET_KEY=pleasechangetoanewlygeneratedsecretkey
..     DEBUG=off  # NEVER run with Debug=True in production

..     # Use real email settings here e.g from Amazon SES
..     EMAIL_HOST=''
..     EMAIL_HOST_USER=''
..     EMAIL_HOST_PASSWORD=''


..     # Here because the original user was too lazy to write ruby code for the VagrantFile
..     DATABASE_USER=mfl  # Change this
..     DATABASE_PASSWORD=mfl  # **CHANGE** this, no matter how lazy you feel
..     DATABASE_NAME=mfl  # Change this

..     # Make sure you change this in lockstep with the three DATABASE_* vars above
..     DATABASE_URL='postgres://mfl:mfl@localhost:5432/mfl'


..     # Location where the administration frontend is running
..     FRONTEND_URL='http://localhost:8062'


.. .. _Twelve-Factor App: http://12factor.net/

.. .. warning::

..     Please make sure that you have set up secure values.

..     You will need to save a copy of the ``.env`` at a secure location ( not in
..     the code repository ). If you loose the ``.env`` / forget the values, you
..     could lose the ability to maintain the deployed production system.

.. The pre-deploy checklist
.. ---------------------------
.. You **MUST** work your way through the `Django deployment checklist`_.

.. .. _`Django deployment checklist`: https://docs.djangoproject.com/en/1.8/howto/deployment/checklist/

.. Configuring the ansible inventory
.. -------------------------------------
.. There is an ``inventory`` file in the ``playbooks`` folder. This file should
.. be edited to have a line for each server that is managed by Ansible.

.. The following is an example:

.. .. code-block:: text

..     azure_test_server             ansible_ssh_host=mfl.azure.slade360.co.ke     ansible_ssh_port=22     ansible_ssh_user=azureuser     ansible_ssh_private_key_file=/home/ngurenyaga/.ssh/id_rsa

.. The template breaks down roughly to this:

.. .. code-block:: text

..     <a descriptive name we choose for the server>
..     ansible_ssh_host=<an IP address or host name>
..     ansible_ssh_port=<the port over which the SSL daemon is listening on the remote machine>
..     ansible_ssh_user=<the username to log in with on the remote machine>
..     ansible_ssh_private_key_file=<a path to a local SSH private key>

.. .. warning::

..     The SSH private key must be kept private.

.. .. warning::

..     If you are working off a recent Ubuntu Linux on your laptop, you should
..     comment out ``SendEnv LANG LC_*`` in ``/etc/ssh/ssh_config``.

..     The forwarding of language environment variables from the local computer
..     is known to cause mischief on the remote server.

.. .. warning::

..     This server should only be run on a non-threaded server e.g ``gunicorn``
..     in the standard multi-process configuration.

..     This is because the geographic features rely on ``GDAL``, which is not
..     thread safe.


.. toctree::
    :maxdepth: 2
