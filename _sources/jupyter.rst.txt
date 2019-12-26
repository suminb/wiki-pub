Jupyter Notebook
================

Installation
------------

There are multiple options available when it comes to Installation, but we
will introduce two of them in this article.

PIP
~~~

.. code::

    pip install jupyter

Once ``jupyter`` package is installed, one may run the notebook server as
follows:

.. code::

    jupyter notebook

Once the notebook is up and running, it can be accessed via
http://localhost:8888.

Docker
~~~~~~

If installing ``jupyter`` package via ``pip`` command is not a viable option,
a pre-built Docker image could be a good alternative.

.. code::

    docker run -p 8888:8888 jupyter/scipy-notebook

However, we may want to preserve your notebook files when the server is
terminated. In such cases, we want to mount your local directory to the
Docker instance. Suppose we have ``$HOME/jupyter`` directory.

.. code::

    docker run \
        --name jupyter \
        -p 8888:8888 \
        -v "$PWD/jupyter":/home/jovyan/work \
        jupyter/scipy-notebook

If ``jupyter/scipy-notebook`` image is locally unavailable, Docker will
automatically fetch it from the hub.

Once the Docker container is running the following log messages (or something
similar) will be visible. We will need the ``token`` value for authentication.

.. code::

    To access the notebook, open this file in a browser:
        file:///home/jovyan/.local/share/jupyter/runtime/nbserver-8-open.html
    Or copy and paste one of these URLs:
        http://(3c35b924b646 or 127.0.0.1):8888/?token=061d7c374a685b628beb12b4ad0381444955826f6348d622

If Docker container is running as a daemon (no console output), we can still
check the log as follows:

.. code::

    $ docker logs jupyter
    Executing the command: jupyter notebook
    [I 07:37:29.301 NotebookApp] Writing notebook server cookie secret to /home/jovyan/.local/share/jupyter/runtime/notebook_cookie_secret
    [I 07:37:30.336 NotebookApp] JupyterLab extension loaded from /opt/conda/lib/python3.7/site-packages/jupyterlab
    [I 07:37:30.336 NotebookApp] JupyterLab application directory is /opt/conda/share/jupyter/lab
    [I 07:37:30.348 NotebookApp] Serving notebooks from local directory: /home/jovyan
    [I 07:37:30.348 NotebookApp] The Jupyter Notebook is running at:
    [I 07:37:30.349 NotebookApp] http://(3c35b924b646 or 127.0.0.1):8888/?token=061d7c374a685b628beb12b4ad0381444955826f6348d622
    [I 07:37:30.350 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
    [C 07:37:30.365 NotebookApp]

        To access the notebook, open this file in a browser:
            file:///home/jovyan/.local/share/jupyter/runtime/nbserver-8-open.html
        Or copy and paste one of these URLs:
            http://(3c35b924b646 or 127.0.0.1):8888/?token=061d7c374a685b628beb12b4ad0381444955826f6348d622

Tips & Tricks
-------------

Turn off auto-bracket
~~~~~~~~~~~~~~~~~~~~~

.. code::

    from notebook.services.config import ConfigManager
    c = ConfigManager()
    c.update('notebook', {"CodeCell": {"cm_config": {"autoCloseBrackets": False}}})
