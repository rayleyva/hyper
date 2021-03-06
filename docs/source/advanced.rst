.. _advanced:

Advanced Usage
==============

This section of the documentation covers more advanced use-cases for ``hyper``.

Multithreading
--------------

Currently, ``hyper``'s :class:`HTTP20Connection <hyper.HTTP20Connection>` class
is **not** thread-safe. Thread-safety is planned for ``hyper``'s core objects,
but in this early alpha it is not a high priority.

To use ``hyper`` in a multithreaded context the recommended thing to do is to
place each connection in its own thread. Each thread should then have a request
queue and a response queue, and the thread should be able to spin over both,
sending requests and returning responses. The stream identifiers provided by
``hyper`` can be used to match the two together.

SSL/TLS Certificate Verification
--------------------------------

By default, all HTTP/2.0 connections are made over TLS, and ``hyper`` uses the
system certificate authorities to verify the offered TLS certificates.
Currently certificate verification cannot be disabled.

Streaming Uploads
-----------------

Just like the ever-popular ``requests`` module, ``hyper`` allows you to perform
a 'streaming' upload by providing a file-like object to the 'data' parameter.
This will cause ``hyper`` to read the data in 1kB at a time and send it to the
remote server. You _must_ set an accurate Content-Length header when you do
this, as ``hyper`` won't set it for you.
