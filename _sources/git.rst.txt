Git
===

Batch Amendment
---------------

Overwrite author/committer name/email for all changesets.

.. code::

    git filter-branch -f --env-filter \
    "GIT_AUTHOR_NAME='Author Name'; GIT_AUTHOR_EMAIL='author@gmail.com'; \
    GIT_COMMITTER_NAME='Committer Name'; GIT_COMMITTER_EMAIL='committer@gmail.com';" HEAD

Unicode In Git Status
---------------------

Display unicode characters when git status command is issued. Refer this page
for more details.

.. code::

    git config --global core.quotePath false

Shallow Clone
-------------

Sometimes it takes a long time to clone a repository when it is huge. In such
cases, it is possible to limit the ``depth`` so that it only clones the
recent changesets. This significantly reduces the time it takes to clone the
repository. For example,

.. code::

    git clone --depth=50

This command will clone recent 50 commits as stated in ``git`` manual:

    Create a shallow clone with a history truncated to the specified number
    of commits. Implies ``--single-branch`` unless ``--no-single-branch`` is
    given to fetch the histories near the tips of all branches. If you want
    to clone submodules shallowly, also pass ``--shallow-submodules``.

Once cloned, one may wish to get the full history of the repository. Then one
may run the following command to retrieve the full commit history.

.. code::

    git clone --unshallow