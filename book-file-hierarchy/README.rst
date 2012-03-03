############################
Book File Hierarchy Proposal
############################

    *Note*: This is a first draft of a book file hierarchy. You're welcome to
    complain about, critique, destroy, or update any of the sections herein.
    Really. Edit, fork, or otherwise co-opt it.

As a project, we should aim to include these three aspects of a text:

* The **pure content**, including the text, raw images, and significant
  formatting details. E.g, in poetry and drama, line breaks are important and
  should be considered part of the work, whereas in most prose linebreaks are
  usually continued artifacts of the typesetting process.

* **Machine- and human-readable metadata**, including general text and author
  data, text history, and licensing information.
   
* Nicely-formatted **output files** based on the source text, or methods and
  tools to produce them. These may or may not be included in source
  distributions of a text - they don't belong in Git repositories, but they
  might be included in places like downloadable compressed archives.


And so I suggest a file hierarchy like this::

    example-book
    ├── readme.rst
    ├── example-book.rst
    ├── license.txt
    ├── metadata.yml
    ├── output
    │   ├── ePub
    │   ├── html
    │   ├── pdf
    │   └── et cetera
    └── resources
        ├── 001_image_one.png
        └── 002_my_song.flac

* ``example-book`` is a directory with the name of the given text

  * ``readme.rst`` should be a human-readable introduction to the text, perhaps
    with a note describing Project Alexandria. This will make the books a
    little nicer for Github, too.

    Note that the file extension choice is arbitrary here; ``.markdown`` or
    ``.txt`` would do just as well, for example.

  * ``example-book.rst`` is the source file of the text in one of the master
    formats. The choice of master format and file extension is beyond the
    scope of this proposal; restructuredtext is used as an example here.

  * ``license.txt`` can contain licensing information; I'm not sure what we
    need or want for texts borrowed from Project Gutenberg. 

  * ``metadata.yml`` should be a machine-readable (and, ideally, human-readable
    and -writable) metadata file containing fields like "author" and "title".
    YAML seems like the best idea here.

  * ``output`` is a directory of generated files, organized in subdirectories
    by their formats. This can be left out for source-only distributions and in
    Git repositories, but it's probably a good idea to have Git ignore it in
    order to keep version control directories and commit logs clean.

  * Binary content files should be contained in ``resources``. Ideally these
    should be as close to lossless as possible. Images should be the largest
    available; ideal sizes differ across devices and resizing can be done when
    texts are being reformated from the master format.
    
.. TODO: rationale; why should we have things this way?

.. TODO: specify metadata fields. maybe not here.

.. TODO: separate files for chapters or one big file? Maybe you could have
    multiple files but they need to be named sequentially so reformatting
    scripts can ``cat`` them.
