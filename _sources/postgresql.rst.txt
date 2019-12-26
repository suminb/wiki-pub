PostgreSQL
==========

`PostgreSQL <https://www.postgresql.org/>`_ is a *de facto* solution for me
when I need a database, unless I have a compelling reason to use something
else. PostgreSQL offers a reasonable balance between the performance and the
richness of features.

Tips & Tricks
-------------

Show timing
~~~~~~~~~~~

.. code::

    => \timing
    Timing is on.

Show tables containing ``<keyword>``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    SELECT * FROM information_schema.tables WHERE column_name LIKE '%<keyword>%'

Show columns containing ``<keyword>``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

NOTE: There are a large number of columns.

.. code::

    SELECT table_catalog, table_schema, table_name, column_name FROM information_schema.columns WHERE column_name LIKE '%<keyword>%'
