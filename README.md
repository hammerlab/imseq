# IMSEQ - An immunogenetic sequence analysis tool

This is the source code repository for **IMSEQ**. For information about **IMSEQ** and release downloads visit www.imtools.org!

## Build instructions

  1. `mkdir build && cd build`
  2. `cmake .. -DCMAKE_MODULE_PATH=../../seqan/util/cmake -DSEQAN_INCLUDE_DIRS_MAIN=../../seqan/include  -DSEQAN_FIND_DEBUG=ON`
      Adjust paths as necessary to seqan.
  3. `make`
