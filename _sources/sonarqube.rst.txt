SonarQube
=========
`SonarQube <https://sonarqube.org>`_ is a static code analyzer.

SonarQube Server
----------------
You need a SonarQube server running. The server can be easily run with
Docker, but this is for testing purposes only, not intended for extended
usage scenarios.

.. code::

    docker run -d --name sonarqube -p 9000:9000 sonarqube

Once the Docker container is up and running, the UI can be access via
http://localhost:9000

Installation
------------

OS X
~~~~
.. code::

    https://formulae.brew.sh/formula/sonar-scanner

Running
~~~~~~~
Gradle plugin is available: https://plugins.gradle.org/plugin/org.sonarqube

.. code::

    ./gradlew sonarqube \
            -Dsonar.projectKey=<project-name> \
            -Dsonar.host.url=http://localhost:9000 \
            -Dsonar.login=admin \
            -Dsonar.password=admin
