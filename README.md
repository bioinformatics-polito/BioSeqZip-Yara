A Yara fork for automatically expanding *BioSeqZip* collapsed sequences
=======================================================================
This repository contains a fork of the [Yara](https://github.com/seqan/seqan/tree/master/apps/yara) mapper (v0.9.11) from the [SeqAn2](https://github.com/seqan/seqan) library (v2.4.0). It works exactly as the original Yara tool, but it was hacked for automatically expanding SAM/BAM records after the mapping phase.

Notice that this works properly **ONLY** if the input file was previously collapsed with BioSeqZip as long as all read headers are supposed to have the BioSeqZip format (`BIOSEQZIP|ID:<id>|CN:<count>`)

## Prerequisites
A modern C++11 compiler with OpenMP 3.0 extensions is required to build Yara. If unsure, use GNU G++ 4.9 or newer.
* Git
* CMake 3.2 or newer
* G++ 4.9 or newer

## Install from source
The BioSeqZip-Yara tool can be installed executing the following commands:
```
# Download the repository
git clone https://github.com/bioinformatics-polito/BioSeqZip-Yara.git bsz_yara

# Make the build directory
mkdir bsz_yara/build
cd bsz_yara/build

# Configure and build the tool
cmake .. -DCMAKE_BUILD_TYPE=Release -DSEQAN_BUILD_SYSTEM=APP:yara
make

# Install the binaries
cp bin/yara* /usr/local/bin
```

## Contact
* Gianvito Urgese `gianvito.urgese@polito.it`
* Emanuele Parisi `emanuele.parisi@polito.it`
