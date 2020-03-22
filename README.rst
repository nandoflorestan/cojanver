===================================
Cojanver - client/server validation
===================================

What is Cojanver?
=================

Ever dream of a validation library that would work the same in the server as
in the client?

`colander <https://docs.pylonsproject.org/projects/colander/en/latest/>`_
is an awesome Python validation library.

`Transcrypt <https://www.transcrypt.org/>`_ is an awesome transpiler
from Python to Javascript.

This repository is an adaptation of colander such that it runs with Transcrypt.


What is the status?
===================

So far I have only removed the problematic parts from colander.  Now, together,
we should implement these parts again -- or the dependencies we are missing
for them to compile.

For instance, the *decimal* Python stdlib module does not transpile to JS yet
because it depends on the *locale* module which needs ``itertools.chain()``.

You can easily see what I did by perusing my latest commits in the *transcrypt*
branch.


Usage
=====

I recommend simply copying the ``colander/__init__.py`` module to your project,
renamed to ``cojanver.py``.  Then run Transcrypt on it.
