.. index:: virtual hosts
   single: HTTP

.. _virtual_hosts-section:

==============
Virtual hosts
==============

Virtual hosting allows you to host multiple domain names on a single server. On |product|, from :guilabel:`Virtual hosts` page, it is possible to configure web sites as Apache named virtual hosts. 

Virtual host names (FQDN)
-------------------------

This is the list of Fully Qualified Domain Names that are associated with the virtual hosts. Values must be separated with a "," (comma).
To access a virtual host, you also needed a DNS record. If enabled under "Additional actions" an alias for the server is automatically created on "DNS > Server alias", but it's useful only for clients that use the server as DNS.

Configuring a web application
-----------------------------

When a new virtual host is created, its associated folder /var/lib/nethserver/vhost/`NAME` is also created.
If FTP access is enabled, it is possible to upload files to this folder using an FTP client using the virtual host name as the username.

.. warning:: FTP access is disabled by default, you will need to enable it from FTP configuration page

The HTTP authentication password should be different from the FTP one, because FTP is used for uploading content to the virtual host and HTTP is used to read content from the virtual host.

Apache permissions
------------------

FTP uploaded files are owned by the "apache" group. If you need to allow apache write or execute permissions, you can change group permissions using the FTP client.

.. warning:: If a virtual host contains executable code, such as PHP
             scripts, user permissions and security implications must
             be evaluated carefully.

