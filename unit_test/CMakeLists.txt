cmake_minimum_required (VERSION 2.8.2)
project (seqan_apps_imseq_unit_test)
message (STATUS "Configuring apps/imseq/unit_test")

# ----------------------------------------------------------------------------
# Test Suite Setup
# ----------------------------------------------------------------------------

seqan_register_tests ()

# ----------------------------------------------------------------------------
# Dependencies
# ----------------------------------------------------------------------------

# Search SeqAn and select dependencies.
#set (SEQAN_FIND_DEPENDENCIES NONE)
find_package (SeqAn REQUIRED)

# ----------------------------------------------------------------------------
# Build Setup
# ----------------------------------------------------------------------------

# Add include directories.
include_directories (${SEQAN_INCLUDE_DIRS})

# Add definitions set by find_package (SeqAn).
add_definitions (${SEQAN_DEFINITIONS})

# unit_tests_imseq executable
add_executable (unit_tests_imseq
    unit_tests_imseq.cpp
    unit_tests_imseq_barcode_correction.h
    unit_tests_imseq_fastq_io.h
    unit_tests_imseq_fastq_multi_record.h
    unit_tests_imseq_qc_basics.h
    )

# Add dependencies found by find_package (SeqAn).
target_link_libraries (unit_tests_imseq ${SEQAN_LIBRARIES})

# Add CXX flags found by find_package (SeqAn).
set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${SEQAN_CXX_FLAGS}")
