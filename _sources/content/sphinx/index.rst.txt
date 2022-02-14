######
Sphinx
######

..  contents:: :local:


**********
Directives
**********

Boxes
=====

..  seealso::

    Content


..  warning::

    Content


..  note::

    Content


..  admonition:: Custom title

    Content


..  admonition:: Custom title and style
    :class: tip

    Warning styles:

    - attention
    - caution
    - warning

    Error styles:

    - danger
    - error

    Success styles:

    - hint
    - important
    - tip

    Info styles:

    - note


..  code-block:: none

    ..  seealso::

        Content


    ..  warning::

        Content


    ..  note::

        Content


    ..  admonition:: Title

        Content


    ..  admonition:: Title and style
        :class: tip

        ...


Math
====

To enable support for LaTeX syntax add one of the following to the sphinx extensions:

-   ``sphinx.ext.mathjax``
-   ``sphinx.ext.imgmath``

..  math::

    (a + b)^2

..  code-block:: none

    ..  math::

        (a + b)^2

Tables
======

HTML
----

..  raw:: html
    :file: ./table.html

..  code-block:: none

    ..  raw:: html
        :file: ./table.html

CSV
---

..  csv-table:: Caption
    :header: "Name", "Age", ""
    :widths:  30, 10, 15

    "Martin", "30", "M"
    "Tommie", "27", "M"
    "Peter", "22", "M"

..  code-block:: none

    ..  csv-table:: Caption
        :header: "Name", "Age", "Sex"
        :widths:  30, 10, 15

        "Martin", "30", "M"
        "Tommie", "27", "M"
        "Peter", "22", "M"

Syntax highlighting
===================

Inline
------

..  code-block:: python

    l = [(3, 1, 2), (4, 10, 100), (73, 25, 25), (3, 4, 2)]
    for n, a, b in l:
        print ' '.join(map(str, sorted({a*(n-i-1)+b*i for i in xrange(0, n)})))

From a file
-----------

..  code-block:: none

    ..  literalinclude:: <file path>
        :language: python


Images
======

..  figure:: ./python.png
    :align: center
    :scale: 90 %
    :alt: Alternative text for thr figure.

    Caption of the figure.

..  code-block:: none

    ..  figure:: ./python.png
        :align: center
        :scale: 90 %
        :alt: Alternative text for thr figure.

        Caption of the figure.

References
==========

Named references
----------------
Named references end with a single underscore. They should have unique names, otherwise during a
documentation build the following warning will be displayed:

..  code-block:: none

    *WARNING: Duplicate explicit target name: <name>*

`Google <http://google.com>`_

..  code-block:: none

    `Google <http://google.com>`_

Anonymous references
--------------------
Anonymous references end with a double underscore.

`Google <http://google.com>`__

..  code-block:: none

    `Google <http://google.com>`__

References to headers within a document
---------------------------------------
Sphinx automatically creates header labels which available within a document as lowercased and
hyphenated headers.


`References to headers <#references-to-headers>`__

..  code-block:: none

    `References to headers <#references-to-headers>`__

References to any place in a documentation
------------------------------------------
In order to create a reference to a place in a documentation a label in that place has to be
created. Then it's possible to refer the label with ``ref`` directive. For example, a ``some_label``
label was defined below.

.. _some_label:

-   Reference to :ref:`some label <some_label>`

..  code-block:: none

    .. _some_label:

    -   Reference to :ref:`some label <some_label>`

Reference to footnotes
----------------------

First footnote [1]_
Second footnote [2]_

.. [1] First footnote content.
.. [2] Second footnote content.

..  code-block:: none

    First footnote [1]_
    Second footnote [2]_

    .. [1] First footnote content.
    .. [2] Second footnote content.

References to files
-------------------

..  code-block:: none

    :download:`Name <path>`


Table
===========

..  code-block:: none

    .. contents:: :local:

Functions
=========

..  py:function:: func(param1: int, param2: str=None) -> int

    Function description.

    :param param1: Parameter description.
    :type param1: int
    :param param2: Parameter description, defaults to None.
    :type param2: str, optional
    :raises CustomException: Error description.
    :returns: Return description.
    :rtype: int

..  code-block:: none

    ..  py:function:: func(param1: int, param2: str=None) -> int

        Function description.

        :param param1: Parameter description.
        :type param1: int
        :param param2: Parameter description, defaults to None.
        :type param2: str, optional
        :raises CustomException: Error description.
        :returns: Return description.
        :rtype: int


*******
Headers
*******

Suggested symbols for marking headers:

#. ``#`` + two blank lines before.
#. ``*`` + two blank lines before.
#. ``=``
#. ``-``
#. ``^``
#. ``"``

First and second level headers should be preceded by two blank lines.

..  code-block:: none

    ##################
    H1: document title
    ##################

    Content.


    **********
    H2: header
    **********

    Content.


    ******************
    H2: another header
    ******************

    Content.

    H3: header
    ==========

    Content.

    H4: header
    ---------

    Content.

    H5: header
    ^^^^^^^^^^

    Content.

    H6: header
    """"""""""

    Content.


**************
Export formats
**************

Export documentation to HTML format:

..  code-block::

    make html

Export documentation to PDF format:

..  code-block::

    make latexpdf
