############################
Book File Hierarchy Proposal
############################

    *Note*: This is a first draft of a book file hierarchy. You're welcome to
    complain about, critique, destroy, or update any of the sections herein.
    Really. You can edit, fork, or otherwise co-opt it, too.

As a project, we should aim to include these three aspects of a text:

* The **pure content**, including plain text, raw images, and significant
  formatting details, depending on the genre of the work. E.g, in poetry and
  drama, line breaks are important and should be considered part of the work,
  whereas in most prose linebreaks are artifacts of the typesetting process.

* **Machine- and human-readable metadata**, including general text and author
  data, text history, and licensing information.
   
* Nicely-formatted **output** files based on the source text, or methods and
  tools to produce them. These may or may not be included in source
  distributions of a text - they don't belong in Git repositories, but they
  might be included in compressed archives of the source.


And so I suggest a file hierarchy similar to the one given below::

    example-book
    ├── .gitignore
    ├── README.rst
    ├── example-book.rst
    ├── license.txt
    ├── metadata.yml
    ├── output
    │   ├── ePub
    │   ├── html
    │   └── pdf
    └── resources
        ├── 001.png
        └── 002.flac

