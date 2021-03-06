Release History
---------------

X.X.X (XXXX-XX-XX)
++++++++++++++++++

*This represents the current state of `master`.*

- Implemented logging. (`Issue #12`_)
- Stopped HTTP/2.0 special headers appearing in the response headers.
  (`Issue #16`_)
- `HTTP20Connection` objects are now context managers. (`Issue #13`_)


.. _Issue #12: https://github.com/Lukasa/hyper/issues/12
.. _Issue #16: https://github.com/Lukasa/hyper/issues/16
.. _Issue #13: https://github.com/Lukasa/hyper/issues/13

0.0.1 (2014-02-11)
++++++++++++++++++

- Initial Release
- Support for HTTP/2.0 draft 09.
- Support for HPACK draft 05.
- Support for HTTP/2.0 flow control.
- Verifies TLS certificates.
- Support for streaming uploads.
- Support for streaming downloads.
