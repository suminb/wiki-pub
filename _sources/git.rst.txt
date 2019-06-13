Git
===

Overwrite author/committer name/email for all changesets.

.. code::

    git filter-branch -f --env-filter \
    "GIT_AUTHOR_NAME='Author Name'; GIT_AUTHOR_EMAIL='author@gmail.com'; \
    GIT_COMMITTER_NAME='Committer Name'; GIT_COMMITTER_EMAIL='committer@gmail.com';" HEAD

Display unicode characters when git status command is issued. Refer this page
for more details.

.. code::

    git config --global core.quotePath false
