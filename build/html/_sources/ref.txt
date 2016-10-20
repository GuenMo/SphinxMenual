
    This is a normal text paragraph again.

The handling of the ``::`` marker is smart:

* If it occurs as a paragraph of its own, that paragraph is completely left
  out of the document.
* If it is preceded by whitespace, the marker is removed.
* If it is preceded by non-whitespace, the marker is replaced by a single
  colon.

That way, the second sentence in the above example's first paragraph would be
rendered as "The next paragraph is a code sample:" (single colon at the end).


.. syntax-highlighting:

Syntax Highlighting
-------------------

Instead of using the special marker ``::``, you may prefer the ``code-block``
directive which lets you highlight the code for a specific language:

.. code-block:: restructuredtext

    .. code-block:: php

        <?php
        $foo = 'bar';
        ?>

to get:

.. code-block:: php

    <?php
    $foo = 'bar';
    ?>

You may number lines as well and emphasize one or more lines:

.. code-block:: restructuredtext
   :emphasize-lines: 2-3

    .. code-block:: yaml
        :linenos:
        :emphasize-lines: 1,4-5

        conf.py:
          copyright: 2013-2014
          project: Sphinx Python Documentation Generator and Viewer
          version: 1.3
          release: 1.3.0

which shows as:

.. code-block:: yaml
    :linenos:
    :emphasize-lines: 1,4-5

    conf.py:
      copyright: 2013-2014
      project: Sphinx Python Documentation Generator and Viewer
      version: 1.3
      release: 1.3.0

See http://pygments.org/docs/lexers/ for a list of supported languages (please
note that 'typoscript' is supported as well).
