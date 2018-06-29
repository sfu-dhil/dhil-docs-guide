.. _authentication:

===============
Authentication
===============

Most Symfony projects at DHIL require users to login in order to have access to database content and editing features.
The login process is handled by Symfony's authentication controllers. Problems occur when Symfony and MySQL parameters are not configured correctly.
Here we mention basic steps for troubleshooting.

**1) Make sure your credentials are right**

It would not hurt to re-check your user name and password. Find the table *Nines_user* in your database to see if the user exists.
Then setup your password again with:

.. code-block:: console

      php bin/console fos:user:change-password [username] [password]

**2) See if the cookies are loaded**

Go to the login page and open the developer console (or something equivalent). Attempt to login and then
see if the cookie PHP_SESSION_[ApplicationName] is loaded. Don't forget to clear your cache if needed.

**3) Make sure that your parameters file is setup correctly**

The config file is located at [ApplicationName]/app/config. Things to make sure:

    * database host -must be numerical i.e. *127.0.0.1*
    * database port -must be left as *~*
    * router.request_context.host -must be same with *database_host*.

    .. Note:: The address you type on browser must match these

    * router.request_context.base_url -should be left as */*

**5) Check the database connection & port numbers**

Make sure the application is connected to the database. Try this to see:

.. code-block:: console

    php bin/console doctrine:schema:update —dump-sql

Also a good practice is to terminate unnecessary servers and programs that might create interference

Sometimes a simple restart can solve these issues.

.. Note:: if you are using a third-party application like XAMPP to run mysql, keep in mind that PHP's built-in web server is distinct from XAMPP's web server (and hence, they use different ports).

**6) Refer to the log file**

Error messages can shorten the job considerably. You can then search the net for similar issues.
Symfony log files are located in [ProjectName]/var/logs/. Clear the log file and then try to login again.

.. Note:: Make sure you are checking the log file for the environment you are in i.e. if dev, then dev.log
