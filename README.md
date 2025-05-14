# Genome-Reconstruction-from-Paired-Reads-Using-Eulerian-Cycles

This Python script reconstructs a genome sequence from paired reads (k,d)-mers by building and traversing a De Bruijn graph. It employs random cycle detection to find an Eulerian path, then reconstructs the original genome sequence.

# Features
* Constructs a De Bruijn graph from paired reads.
* Detects start and end nodes for Eulerian path traversal.
* Finds Eulerian cycles and paths using random exploration.
* Reconstructs genome sequence from the Eulerian path.
* Handles paired k-mers with a specified gap distance.

# Usage
* Define the parameters k (k-mer length) and d (distance between pairs).
* Provide a list of paired reads as tuples, e.g. ('GAGA', 'TTGA').
* Call reconstructGenome(pairs, k, d) to get the reconstructed genome string.

# Example

* Set the k-mer length k, the gap distance d, and the list of paired k-mers (k-mer, k-mer).
```
k = 4
d = 2
pairs = [
    ('GAGA', 'TTGA'),
    ('TCGT', 'GATG'),
    ('CGTG', 'ATGT'),
    ('TGGT', 'TGAG'),
    ('GTGA', 'TGTT'),
    ('GTGG', 'GTGA'),
    ('TGAG', 'GTTG'),
    ('GGTC', 'GAGA'),
    ('GTCG', 'AGAT')
]

result = reconstructGenome(pairs, k, d)
print(result)
```
# How it works
* Graph construction: builds a directed De Bruijn graph where nodes represent the prefixes of paired k-mers and edges connect nodes whose suffix matches the prefix of the next node.
* Start/end detection: identifies nodes with higher outdegree or indegree to determine the start and end points of the path.
* Cycle search: randomly traverses the graph to find cycles covering all edges, approximating an Eulerian path.
* Reconstruction: concatenates sequences from the pairs along the found path to obtain the original genomic sequence.

# Applications
* Genome assembly from paired-end sequencing data.
* Teaching and studying De Bruijn graphs and assembly algorithms.
* Basis for further improvements and adaptations in bioinformatics pipelines.

# License

This project is licensed under the MIT License.


