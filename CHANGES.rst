============
 Change log
============

Significant or incompatible changes listed here.

Changes in development version
------------------------------

* ``Money.__round__()`` added to support ``round(money, [ndigits])``.
  Uses ``decimal.ROUND_HALF_EVEN`` by default, but this can be overriden
  by setting ``rounding`` in the ``decimal`` context before calling ``round()``.

  ``round()`` on Python 2 does not support the ``__round__()`` method,
  so rounding of ``Money`` with ``round()`` is only available in Python 3.

  Calling ``round(money)`` without ``ndigits`` specified is not supported,
  and throws a ``TypeError`` as it would coerce the ``Money`` instance to an
  ``int`` and this loose the currency information. Use ``round(money, 0)`` to
  round the amount to the closest whole number, while preserving the currency
  information.


Changes in v0.7
---------------

* Money.__str__ changed under Python 2 to use only ASCII characters.
  This means that currency codes, rather than symbols, are used.

* Lots of additional locales supported out of the box.

* Python 3.5 supported

* Fixed #70 - format_money error when the locale is not in the formatting
  definitions: the default is not used.

* Various other bug fixes


Changes in v0.6 and earlier
---------------------------

* See VCS logs.
