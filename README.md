Seqhax
======

A seqtk-style toolkit for sequence analysis. By no means feature complete. In
fact largely contains features other authors have not merged into their
respective tools.

Installation
============

Install zlib version >=1.2.5, then:

```bash
git clone https://github.com/kdmurray91/seqhax.git
cd seqhax
mkdir build && cd build
cmake ..
make
make install
```

Any other issues, file a [bug report on
github](https://github.com/kdmurray91/seqhax/issues).

Documentation
=============

The `seqhax` command has many subcommands. The commands, along with a synopsis
of their actions, are displayed when one types `seqhax` with no arguments. 
At the time of writing, these were:

```
$ seqhax
USAGE:
    seqhax PROGRAM [options]

where PROGRAM is one of:
    anon       -- Rename sequences by a sequential number
    filter     -- Filter reads from a sequence file
    pairs      -- (De)interleave paired end reads
    preapp     -- Prepend or append string to sequences
    randseq    -- Generate a random sequence file
    trunc      -- Truncate sequences
```

The usage of each subcommand can be obtained using the `-h` flag to that
subcommand, e.g. `seqhax seq -h`.


## Sub-commands


#### `anon`

Re-name sequences with a sequential numeric ID.


#### `filter`

Removes sequences based on certain criteria:

- Length
* Pairing

#### `pairs`

Interleaves or de-interleaves paired reads. Converts between the following
forms:

- Separate R1/R2 paired files and single read read file.
- "Strict" interleaved file, where failed/missing reads are replaced with a
  single 'N'.
* "Broken paired" interleaved files, where failed/missing reads are simply not
  present.


#### `preapp`

Addition of a constant prefix and/or suffix to each sequence.

#### `randseq`

Generates a fasta or fastq file containing sequences with random sequences.


#### `trunc`

Truncates reads at given length.


# License

GPL v3 (see ./LICENSE).

Copyright (c) 2014-2016 Kevin Murray.
